# CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)

- ea: `0x18007d200`
- end: `0x18007d253`
- name: `?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z`
- size: `83`
- prototype: `struct _CERT_EXTENSION *__fastcall(const char *, const struct _CERT_CONTEXT *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18007cc34`
- `0x18007d25c`
- `0x18007d448`

## callees

- `0x18002f324`
- `0x18007d200`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x18007d247`

## string_xrefs

- `0x18007d209`: `%s: FindExtensionByOid: pcszOid is NULL.`
- `0x18007d229`: `%s: FindExtensionByOid: pCertContext is NULL.`
- `0x18007d210`: `CertificateUtil::FindExtensionByOid`

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
0x18007d200  sub     rsp, 28h
0x18007d204  test    rcx, rcx
0x18007d207  jnz     short loc_18007D224
0x18007d209  lea     rcx, aSFindextension; "%s: FindExtensionByOid: pcszOid is NULL"...
0x18007d210  lea     rdx, aCertificateuti_1; "CertificateUtil::FindExtensionByOid"
0x18007d217  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007d21c  xor     eax, eax
0x18007d21e  add     rsp, 28h
0x18007d222  retn
0x18007d224  test    rdx, rdx
0x18007d227  jnz     short loc_18007D232
0x18007d229  lea     rcx, aSFindextension_0; "%s: FindExtensionByOid: pCertContext is"...
0x18007d230  jmp     short loc_18007D210
0x18007d232  mov     rdx, [rdx+18h]
0x18007d236  mov     r8, [rdx+0C8h]
0x18007d23d  mov     edx, [rdx+0C0h]
0x18007d243  add     rsp, 28h
0x18007d247  jmp     cs:__imp_CertFindExtension
```
