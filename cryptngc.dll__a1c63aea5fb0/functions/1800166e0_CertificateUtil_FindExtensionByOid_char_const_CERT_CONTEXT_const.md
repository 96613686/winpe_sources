# CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)

- ea: `0x1800166e0`
- end: `0x180016740`
- name: `?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z`
- size: `96`
- prototype: `struct _CERT_EXTENSION *__fastcall(const char *, const struct _CERT_CONTEXT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180015d54`
- `0x18002bcdc`

## callees

- `0x1800166e0`
- `0x180027448`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x180016703`

## string_xrefs

- `0x180016716`: `%s: FindExtensionByOid: pcszOid is NULL.`
- `0x18001670f`: `CertificateUtil::FindExtensionByOid`
- `0x180016729`: `CertificateUtil::FindExtensionByOid`
- `0x180016730`: `%s: FindExtensionByOid: pCertContext is NULL.`

## pseudocode

```c
PCERT_EXTENSION __fastcall CertificateUtil::FindExtensionByOid(const char *a1, const struct _CERT_CONTEXT *a2)
{
  if ( a1 )
  {
    if ( a2 )
    {
      return CertFindExtension(a1, a2->pCertInfo->cExtension, a2->pCertInfo->rgExtension);
    }
    else
    {
      Logger::TraceError(L"%s: FindExtensionByOid: pCertContext is NULL.", L"CertificateUtil::FindExtensionByOid");
      return 0;
    }
  }
  else
  {
    Logger::TraceError(L"%s: FindExtensionByOid: pcszOid is NULL.", L"CertificateUtil::FindExtensionByOid");
    return 0;
  }
}

```

## disassembly

```asm
0x1800166e0  sub     rsp, 28h
0x1800166e4  test    rcx, rcx
0x1800166e7  jz      short loc_18001670F
0x1800166e9  test    rdx, rdx
0x1800166ec  jz      short loc_180016729
0x1800166ee  mov     rdx, [rdx+18h]
0x1800166f2  mov     r8, [rdx+0C8h]
0x1800166f9  mov     edx, [rdx+0C0h]
0x1800166ff  add     rsp, 28h
0x180016703  jmp     cs:__imp_CertFindExtension
0x18001670a  add     rsp, 28h
0x18001670e  retn
0x18001670f  lea     rdx, aCertificateuti_1; "CertificateUtil::FindExtensionByOid"
0x180016716  lea     rcx, aSFindextension; "%s: FindExtensionByOid: pcszOid is NULL"...
0x18001671d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180016722  xor     eax, eax
0x180016724  add     rsp, 28h
0x180016728  retn
0x180016729  lea     rdx, aCertificateuti_1; "CertificateUtil::FindExtensionByOid"
0x180016730  lea     rcx, aSFindextension_0; "%s: FindExtensionByOid: pCertContext is"...
0x180016737  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001673c  xor     eax, eax
0x18001673e  jmp     short loc_18001670A
```
