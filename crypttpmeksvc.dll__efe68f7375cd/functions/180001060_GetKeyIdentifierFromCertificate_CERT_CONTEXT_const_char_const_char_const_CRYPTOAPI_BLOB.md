# _GetKeyIdentifierFromCertificate(_CERT_CONTEXT const *,char const *,char const *,_CRYPTOAPI_BLOB * *)

- ea: `0x180001060`
- end: `0x180001137`
- name: `?_GetKeyIdentifierFromCertificate@@YAKPEBU_CERT_CONTEXT@@PEBD1PEAPEAU_CRYPTOAPI_BLOB@@@Z`
- size: `215`
- prototype: `DWORD __fastcall(const struct _CERT_CONTEXT *, const char *, const char *, HLOCAL *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002310`

## callees

- `0x180001060`
- `0x180003750`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x18000108e`
- `CRYPT32!CertFindExtension` at `0x18000108e`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800010d7`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800010d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001115`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800010fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800010fa`

## pseudocode

```c
DWORD __fastcall _GetKeyIdentifierFromCertificate(
        const struct _CERT_CONTEXT *a1,
        const char *a2,
        const char *a3,
        HLOCAL *a4)
{
  unsigned int v6; // ebx
  PCERT_EXTENSION Extension; // rax
  DWORD cbData; // r9d
  const BYTE *pbData; // r8
  DWORD result; // eax
  HLOCAL v11; // rcx
  HLOCAL hMem[3]; // [rsp+40h] [rbp-18h] BYREF
  DWORD pcbStructInfo; // [rsp+60h] [rbp+8h] BYREF

  v6 = 0;
  Extension = CertFindExtension(a2, a1->pCertInfo->cExtension, a1->pCertInfo->rgExtension);
  if ( Extension )
  {
    cbData = Extension->Value.cbData;
    pbData = Extension->Value.pbData;
    hMem[0] = 0;
    pcbStructInfo = 0;
    if ( CryptDecodeObjectEx(1u, a3, pbData, cbData, 0x8001u, 0, hMem, &pcbStructInfo) )
    {
      *a4 = hMem[0];
    }
    else
    {
      ekTraceFmt(0xC1012C2u, 1, "ERROR: CryptDecodeObjectEx. Return=%d\n", 0);
      result = GetLastError();
      v11 = hMem[0];
      v6 = result;
      hMem[0] = 0;
      if ( !v11 )
        return result;
      LocalFree(v11);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180001060  mov     [rsp+arg_8], rbx
0x180001065  mov     [rsp+arg_10], rsi
0x18000106a  push    rdi
0x18000106b  sub     rsp, 50h
0x18000106f  mov     rax, rdx
0x180001072  mov     rsi, r8
0x180001075  mov     rdx, [rcx+18h]
0x180001079  mov     rdi, r9
0x18000107c  mov     rcx, rax; pszObjId
0x18000107f  xor     ebx, ebx
0x180001081  mov     r8, [rdx+0C8h]; rgExtensions
0x180001088  mov     edx, [rdx+0C0h]; cExtensions
0x18000108e  call    cs:__imp_CertFindExtension
0x180001094  test    rax, rax
0x180001097  jz      loc_180001125
0x18000109d  mov     r9d, [rax+10h]; cbEncoded
0x1800010a1  lea     rcx, [rsp+58h+arg_0]
0x1800010a6  mov     r8, [rax+18h]; pbEncoded
0x1800010aa  mov     rdx, rsi; lpszStructType
0x1800010ad  mov     [rsp+58h+pcbStructInfo], rcx; pcbStructInfo
0x1800010b2  lea     rcx, [rsp+58h+hMem]
0x1800010b7  mov     [rsp+58h+pvStructInfo], rcx; pvStructInfo
0x1800010bc  mov     ecx, 1; dwCertEncodingType
0x1800010c1  mov     [rsp+58h+pDecodePara], rbx; pDecodePara
0x1800010c6  mov     [rsp+58h+dwFlags], 8001h; dwFlags
0x1800010ce  mov     [rsp+58h+hMem], rbx
0x1800010d3  mov     [rsp+58h+arg_0], ebx
0x1800010d7  call    cs:__imp_CryptDecodeObjectEx
0x1800010dd  test    eax, eax
0x1800010df  jnz     short loc_18000111D
0x1800010e1  xor     r9d, r9d
0x1800010e4  lea     r8, aErrorCryptdeco_0; "ERROR: CryptDecodeObjectEx. Return=%d\n"
0x1800010eb  mov     edx, 1; unsigned int
0x1800010f0  mov     ecx, 0C1012C2h; unsigned int
0x1800010f5  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800010fa  call    cs:__imp_GetLastError
0x180001100  mov     rcx, [rsp+58h+hMem]; hMem
0x180001105  mov     ebx, eax
0x180001107  mov     [rsp+58h+hMem], 0
0x180001110  test    rcx, rcx
0x180001113  jz      short loc_180001127
0x180001115  call    cs:__imp_LocalFree
0x18000111b  jmp     short loc_180001125
0x18000111d  mov     rcx, [rsp+58h+hMem]
0x180001122  mov     [rdi], rcx
0x180001125  mov     eax, ebx
0x180001127  mov     rbx, [rsp+58h+arg_8]
0x18000112c  mov     rsi, [rsp+58h+arg_10]
0x180001131  add     rsp, 50h
0x180001135  pop     rdi
0x180001136  retn
```
