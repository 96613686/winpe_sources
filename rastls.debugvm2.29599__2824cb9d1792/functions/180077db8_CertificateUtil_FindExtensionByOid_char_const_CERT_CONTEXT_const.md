# CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)

- ea: `0x180077db8`
- end: `0x180077e05`
- name: `?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z`
- size: `77`
- prototype: `struct _CERT_EXTENSION *__fastcall(const char *, const struct _CERT_CONTEXT *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180077838`
- `0x180077e0c`
- `0x180077fe8`

## callees

- `0x18002ce0c`
- `0x180077db8`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x180077dfe`

## string_xrefs

- `0x180077dc8`: `CertificateUtil::FindExtensionByOid`
- `0x180077dc1`: `%s: FindExtensionByOid: pcszOid is NULL.`
- `0x180077de0`: `%s: FindExtensionByOid: pCertContext is NULL.`

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
0x180077db8  sub     rsp, 28h
0x180077dbc  test    rcx, rcx
0x180077dbf  jnz     short loc_180077DDB
0x180077dc1  lea     rcx, aSFindextension; "%s: FindExtensionByOid: pcszOid is NULL"...
0x180077dc8  lea     rdx, aCertificateuti_1; "CertificateUtil::FindExtensionByOid"
0x180077dcf  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077dd4  xor     eax, eax
0x180077dd6  add     rsp, 28h
0x180077dda  retn
0x180077ddb  test    rdx, rdx
0x180077dde  jnz     short loc_180077DE9
0x180077de0  lea     rcx, aSFindextension_0; "%s: FindExtensionByOid: pCertContext is"...
0x180077de7  jmp     short loc_180077DC8
0x180077de9  mov     rdx, [rdx+18h]
0x180077ded  mov     r8, [rdx+0C8h]
0x180077df4  mov     edx, [rdx+0C0h]
0x180077dfa  add     rsp, 28h
0x180077dfe  jmp     cs:__imp_CertFindExtension
```
