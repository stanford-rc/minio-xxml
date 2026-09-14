> ## Forked copy
>
> **This is a forked copy of `github.com/minio/xxml`**, maintained by Stanford Research Computing
> for use by Elm. It is not the upstream project and is not endorsed by its
> authors or by MinIO, Inc.
>
> Forked at upstream commit `1bfa62a`, dated 2022-08-10, and modified on
> **2026-04-09**. The only change is one line of `go.mod`: the module path,
> repointed so this copy and upstream cannot be confused in a build. No other
> file differs from upstream.
>
> **Licensing is unchanged.** This code is under the **BSD 3-Clause** license,
> copyright The Go Authors; see `LICENSE`, which is upstream's and is carried here
> intact.
>
> This notice is informational. BSD 3-Clause requires the copyright and license text to
> be retained, which `LICENSE` does; it does not require a statement that the
> work was modified, so nothing downstream depends on the wording here.
>
> Everything below this line is upstream's README.

---

# xxml

> NOTE: This package is a fork of 'encoding/xml' from https://github.com/golang/go.

Package xml implements a simple XML 1.0 parser that understands XML name spaces, 
along with extended support for control characters such as following

```
var controlCharactersMap = map[rune][]byte{
        '\x00': []byte("&#x0;"),
        '\x01': []byte("&#x1;"),
        '\x02': []byte("&#x2;"),
        '\x03': []byte("&#x3;"),
        '\x04': []byte("&#x4;"),
        '\x05': []byte("&#x5;"),
        '\x06': []byte("&#x6;"),
        '\x07': []byte("&#x7;"),
}
```

XML 1.0 spec does not allow these control characters. However this package intends 
to support these characters to satisfy MinIO's needs for AWS S3 compatiblity.
