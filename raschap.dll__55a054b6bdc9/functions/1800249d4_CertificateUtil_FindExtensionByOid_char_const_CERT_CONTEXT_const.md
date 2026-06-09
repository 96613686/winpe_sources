# CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)

- ea: `0x1800249d4`
- end: `0x180024a21`
- name: `?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z`
- size: `77`
- prototype: `struct _CERT_EXTENSION *__fastcall(const char *, const struct _CERT_CONTEXT *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180013084`
- `0x180024a28`
- `0x180024c04`

## callees

- `0x180010218`
- `0x1800249d4`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x180024a1a`

## string_xrefs

- `0x1800249e4`: `CertificateUtil::FindExtensionByOid`
- `0x1800249fc`: `%s: FindExtensionByOid: pCertContext is NULL.`
- `0x1800249dd`: `%s: FindExtensionByOid: pcszOid is NULL.`

## pseudocode

```c
PCERT_EXTENSION __fastcall CertificateUtil::FindExtensionByOid(const char *a1, const struct _CERT_CONTEXT *a2)
{
  if ( !a1 )
  {
    Logger::TraceError(L"%s: FindExtensionByOid: pcszOid is NULL.", L"CertificateUtil::FindExtensionByOid");
    return 0;
  }
  if ( !a2 )
  {
    Logger::TraceError(L"%s: FindExtensionByOid: pCertContext is NULL.", L"CertificateUtil::FindExtensionByOid");
    return 0;
  }
  return CertFindExtension(a1, a2->pCertInfo->cExtension, a2->pCertInfo->rgExtension);
}

```

## disassembly

```asm
0x1800249d4  sub     rsp, 28h
0x1800249d8  test    rcx, rcx
0x1800249db  jnz     short loc_1800249F7
0x1800249dd  lea     rcx, aSFindextension; "%s: FindExtensionByOid: pcszOid is NULL"...
0x1800249e4  lea     rdx, aCertificateuti_1; "CertificateUtil::FindExtensionByOid"
0x1800249eb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800249f0  xor     eax, eax
0x1800249f2  add     rsp, 28h
0x1800249f6  retn
0x1800249f7  test    rdx, rdx
0x1800249fa  jnz     short loc_180024A05
0x1800249fc  lea     rcx, aSFindextension_0; "%s: FindExtensionByOid: pCertContext is"...
0x180024a03  jmp     short loc_1800249E4
0x180024a05  mov     rdx, [rdx+18h]
0x180024a09  mov     r8, [rdx+0C8h]
0x180024a10  mov     edx, [rdx+0C0h]
0x180024a16  add     rsp, 28h
0x180024a1a  jmp     cs:__imp_CertFindExtension
```
