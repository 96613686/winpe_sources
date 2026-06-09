# IsValidCrlIssuerKeyUsage(_CERT_CONTEXT const *)

- ea: `0x1800189b0`
- end: `0x180018a65`
- name: `?IsValidCrlIssuerKeyUsage@@YAHPEBU_CERT_CONTEXT@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18000cfa0`
- `0x18000fb70`

## callees

- `0x18000a990`
- `0x1800189b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018a5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018a5d`
- `CRYPT32!CertFindExtension` at `0x1800189d9`
- `CRYPT32!CertFindExtension` at `0x1800189d9`
- `CRYPT32!CryptDecodeObjectEx` at `0x180018a1c`
- `CRYPT32!CryptDecodeObjectEx` at `0x180018a1c`

## pseudocode

```c
__int64 __fastcall IsValidCrlIssuerKeyUsage(const struct _CERT_CONTEXT *a1)
{
  PCERT_INFO pCertInfo; // rdx
  unsigned int v2; // ebx
  PCERT_EXTENSION Extension; // rax
  HLOCAL v4; // rcx
  DWORD pcbStructInfo; // [rsp+50h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp+10h] BYREF

  pCertInfo = a1->pCertInfo;
  v2 = 0;
  pcbStructInfo = 0;
  hMem = 0;
  Extension = CertFindExtension("2.5.29.15", pCertInfo->cExtension, pCertInfo->rgExtension);
  if ( Extension )
  {
    if ( CryptDecodeObjectEx(
           0x10001u,
           (LPCSTR)0xE,
           Extension->Value.pbData,
           Extension->Value.cbData,
           0x8005u,
           &PkiDecodePara,
           &hMem,
           &pcbStructInfo) )
    {
      v4 = hMem;
      if ( *(_DWORD *)hMem && (**((_BYTE **)hMem + 1) & 2) != 0 )
        goto LABEL_5;
      SetLastError(0x800B0106);
    }
    v4 = hMem;
    goto LABEL_6;
  }
  v4 = hMem;
LABEL_5:
  v2 = 1;
LABEL_6:
  operator delete(v4);
  return v2;
}

```

## disassembly

```asm
0x1800189b0  push    rbx
0x1800189b2  sub     rsp, 40h
0x1800189b6  mov     rdx, [rcx+18h]
0x1800189ba  xor     ebx, ebx
0x1800189bc  mov     [rsp+48h+arg_0], ebx
0x1800189c0  lea     rcx, a252915; "2.5.29.15"
0x1800189c7  mov     [rsp+48h+hMem], rbx
0x1800189cc  mov     r8, [rdx+0C8h]; rgExtensions
0x1800189d3  mov     edx, [rdx+0C0h]; cExtensions
0x1800189d9  call    cs:__imp_CertFindExtension
0x1800189df  test    rax, rax
0x1800189e2  jz      short loc_180018A51
0x1800189e4  mov     r9d, [rax+10h]; cbEncoded
0x1800189e8  lea     rcx, [rsp+48h+arg_0]
0x1800189ed  mov     r8, [rax+18h]; pbEncoded
0x1800189f1  lea     edx, [rbx+0Eh]; lpszStructType
0x1800189f4  mov     [rsp+48h+pcbStructInfo], rcx; pcbStructInfo
0x1800189f9  lea     rcx, [rsp+48h+hMem]
0x1800189fe  mov     [rsp+48h+pvStructInfo], rcx; pvStructInfo
0x180018a03  lea     rcx, PkiDecodePara
0x180018a0a  mov     [rsp+48h+pDecodePara], rcx; pDecodePara
0x180018a0f  mov     ecx, 10001h; dwCertEncodingType
0x180018a14  mov     [rsp+48h+dwFlags], 8005h; dwFlags
0x180018a1c  call    cs:__imp_CryptDecodeObjectEx
0x180018a22  test    eax, eax
0x180018a24  jz      short loc_180018A4A
0x180018a26  mov     rcx, [rsp+48h+hMem]; hMem
0x180018a2b  cmp     [rcx], ebx
0x180018a2d  jz      short loc_180018A58
0x180018a2f  mov     rax, [rcx+8]
0x180018a33  test    byte ptr [rax], 2
0x180018a36  jz      short loc_180018A58
0x180018a38  mov     ebx, 1
0x180018a3d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018a42  mov     eax, ebx
0x180018a44  add     rsp, 40h
0x180018a48  pop     rbx
0x180018a49  retn
0x180018a4a  mov     rcx, [rsp+48h+hMem]
0x180018a4f  jmp     short loc_180018A3D
0x180018a51  mov     rcx, [rsp+48h+hMem]
0x180018a56  jmp     short loc_180018A38
0x180018a58  mov     ecx, 800B0106h; dwErrCode
0x180018a5d  call    cs:__imp_SetLastError
0x180018a63  jmp     short loc_180018A4A
```
