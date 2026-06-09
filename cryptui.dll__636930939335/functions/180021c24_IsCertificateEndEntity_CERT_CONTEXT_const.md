# IsCertificateEndEntity(_CERT_CONTEXT const *)

- ea: `0x180021c24`
- end: `0x180021e02`
- name: `?IsCertificateEndEntity@@YAHPEBU_CERT_CONTEXT@@@Z`
- size: `478`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180022ad0`

## callees

- `0x180021c24`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021cca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021d83`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021cca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021d83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021dd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021de1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021dd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021de1`
- `CRYPT32!CertFindExtension` at `0x180021c72`
- `CRYPT32!CertFindExtension` at `0x180021d2f`
- `CRYPT32!CertFindExtension` at `0x180021c72`
- `CRYPT32!CertFindExtension` at `0x180021d2f`
- `CRYPT32!CryptDecodeObject` at `0x180021cb5`
- `CRYPT32!CryptDecodeObject` at `0x180021cfd`
- `CRYPT32!CryptDecodeObject` at `0x180021d72`
- `CRYPT32!CryptDecodeObject` at `0x180021db2`
- `CRYPT32!CryptDecodeObject` at `0x180021cb5`
- `CRYPT32!CryptDecodeObject` at `0x180021cfd`
- `CRYPT32!CryptDecodeObject` at `0x180021d72`
- `CRYPT32!CryptDecodeObject` at `0x180021db2`

## pseudocode

```c
__int64 __fastcall IsCertificateEndEntity(const struct _CERT_CONTEXT *a1)
{
  unsigned int v3; // ebx
  _QWORD *v4; // rdi
  _DWORD *pvStructInfo; // rbp
  PCERT_EXTENSION Extension; // r14
  PCERT_EXTENSION v7; // r14
  char *v8; // rax
  DWORD pcbStructInfo; // [rsp+70h] [rbp+8h] BYREF

  pcbStructInfo = 0;
  if ( !a1 )
    return 0;
  v3 = 0;
  v4 = 0;
  pvStructInfo = 0;
  Extension = CertFindExtension("2.5.29.19", a1->pCertInfo->cExtension, a1->pCertInfo->rgExtension);
  if ( Extension )
  {
    pcbStructInfo = 0;
    if ( CryptDecodeObject(1u, (LPCSTR)0xF, Extension->Value.pbData, Extension->Value.cbData, 0, 0, &pcbStructInfo) )
    {
      pvStructInfo = LocalAlloc(0x40u, pcbStructInfo);
      if ( pvStructInfo )
      {
        if ( CryptDecodeObject(
               1u,
               (LPCSTR)0xF,
               Extension->Value.pbData,
               Extension->Value.cbData,
               0,
               pvStructInfo,
               &pcbStructInfo) )
        {
          LOBYTE(v3) = *pvStructInfo == 0;
        }
      }
    }
  }
  else
  {
    v7 = CertFindExtension("2.5.29.10", a1->pCertInfo->cExtension, a1->pCertInfo->rgExtension);
    if ( v7 )
    {
      pcbStructInfo = 0;
      if ( CryptDecodeObject(1u, (LPCSTR)0xD, v7->Value.pbData, v7->Value.cbData, 0, 0, &pcbStructInfo) )
      {
        v4 = LocalAlloc(0x40u, pcbStructInfo);
        if ( v4 )
        {
          if ( CryptDecodeObject(1u, (LPCSTR)0xD, v7->Value.pbData, v7->Value.cbData, 0, v4, &pcbStructInfo)
            && *(_DWORD *)v4 )
          {
            v8 = (char *)v4[1];
            if ( (*v8 & 0x40) != 0 )
            {
              v3 = 1;
            }
            else if ( *v8 < 0 )
            {
              v3 = 0;
            }
          }
        }
      }
    }
  }
  LocalFree(v4);
  LocalFree(pvStructInfo);
  return v3;
}

```

## disassembly

```asm
0x180021c24  mov     [rsp+arg_8], rbx
0x180021c29  mov     [rsp+arg_10], rbp
0x180021c2e  push    rsi
0x180021c2f  push    rdi
0x180021c30  push    r12
0x180021c32  push    r14
0x180021c34  push    r15
0x180021c36  sub     rsp, 40h
0x180021c3a  xor     r15d, r15d
0x180021c3d  mov     rsi, rcx
0x180021c40  mov     [rsp+68h+arg_0], r15d
0x180021c45  test    rcx, rcx
0x180021c48  jnz     short loc_180021C51
0x180021c4a  xor     eax, eax
0x180021c4c  jmp     loc_180021DE9
0x180021c51  mov     rdx, [rcx+18h]
0x180021c55  mov     ebx, r15d
0x180021c58  lea     rcx, a252919; "2.5.29.19"
0x180021c5f  mov     rdi, r15
0x180021c62  mov     rbp, r15
0x180021c65  mov     r8, [rdx+0C8h]; rgExtensions
0x180021c6c  mov     edx, [rdx+0C0h]; cExtensions
0x180021c72  call    cs:__imp_CertFindExtension
0x180021c78  mov     r14, rax
0x180021c7b  test    rax, rax
0x180021c7e  jz      loc_180021D17
0x180021c84  mov     [rsp+68h+arg_0], r15d
0x180021c89  lea     rax, [rsp+68h+arg_0]
0x180021c8e  mov     r9d, [r14+10h]; cbEncoded
0x180021c92  mov     r12d, 0Fh
0x180021c98  mov     r8, [r14+18h]; pbEncoded
0x180021c9c  mov     edx, r12d; lpszStructType
0x180021c9f  mov     [rsp+68h+pcbStructInfo], rax; pcbStructInfo
0x180021ca4  mov     [rsp+68h+pvStructInfo], r15; pvStructInfo
0x180021ca9  lea     esi, [r12-0Eh]
0x180021cae  mov     [rsp+68h+dwFlags], r15d; dwFlags
0x180021cb3  mov     ecx, esi; dwCertEncodingType
0x180021cb5  call    cs:__imp_CryptDecodeObject
0x180021cbb  test    eax, eax
0x180021cbd  jz      loc_180021DD5
0x180021cc3  mov     edx, [rsp+68h+arg_0]; uBytes
0x180021cc7  lea     ecx, [rsi+3Fh]; uFlags
0x180021cca  call    cs:__imp_LocalAlloc
0x180021cd0  mov     rbp, rax
0x180021cd3  test    rax, rax
0x180021cd6  jz      loc_180021DD5
0x180021cdc  mov     r9d, [r14+10h]; cbEncoded
0x180021ce0  lea     rax, [rsp+68h+arg_0]
0x180021ce5  mov     r8, [r14+18h]; pbEncoded
0x180021ce9  mov     edx, r12d; lpszStructType
0x180021cec  mov     [rsp+68h+pcbStructInfo], rax; pcbStructInfo
0x180021cf1  mov     ecx, esi; dwCertEncodingType
0x180021cf3  mov     [rsp+68h+pvStructInfo], rbp; pvStructInfo
0x180021cf8  mov     [rsp+68h+dwFlags], r15d; dwFlags
0x180021cfd  call    cs:__imp_CryptDecodeObject
0x180021d03  test    eax, eax
0x180021d05  jz      loc_180021DD5
0x180021d0b  cmp     [rbp+0], r15d
0x180021d0f  setz    bl
0x180021d12  jmp     loc_180021DD5
0x180021d17  mov     rdx, [rsi+18h]
0x180021d1b  lea     rcx, a252910; "2.5.29.10"
0x180021d22  mov     r8, [rdx+0C8h]; rgExtensions
0x180021d29  mov     edx, [rdx+0C0h]; cExtensions
0x180021d2f  call    cs:__imp_CertFindExtension
0x180021d35  mov     r14, rax
0x180021d38  test    rax, rax
0x180021d3b  jz      loc_180021DD5
0x180021d41  mov     [rsp+68h+arg_0], r15d
0x180021d46  lea     rax, [rsp+68h+arg_0]
0x180021d4b  mov     r9d, [r14+10h]; cbEncoded
0x180021d4f  mov     r12d, 0Dh
0x180021d55  mov     r8, [r14+18h]; pbEncoded
0x180021d59  mov     edx, r12d; lpszStructType
0x180021d5c  mov     [rsp+68h+pcbStructInfo], rax; pcbStructInfo
0x180021d61  mov     [rsp+68h+pvStructInfo], r15; pvStructInfo
0x180021d66  lea     esi, [r12-0Ch]
0x180021d6b  mov     [rsp+68h+dwFlags], r15d; dwFlags
0x180021d70  mov     ecx, esi; dwCertEncodingType
0x180021d72  call    cs:__imp_CryptDecodeObject
0x180021d78  test    eax, eax
0x180021d7a  jz      short loc_180021DD5
0x180021d7c  mov     edx, [rsp+68h+arg_0]; uBytes
0x180021d80  lea     ecx, [rsi+3Fh]; uFlags
0x180021d83  call    cs:__imp_LocalAlloc
0x180021d89  mov     rdi, rax
0x180021d8c  test    rax, rax
0x180021d8f  jz      short loc_180021DD5
0x180021d91  mov     r9d, [r14+10h]; cbEncoded
0x180021d95  lea     rax, [rsp+68h+arg_0]
0x180021d9a  mov     r8, [r14+18h]; pbEncoded
0x180021d9e  mov     edx, r12d; lpszStructType
0x180021da1  mov     [rsp+68h+pcbStructInfo], rax; pcbStructInfo
0x180021da6  mov     ecx, esi; dwCertEncodingType
0x180021da8  mov     [rsp+68h+pvStructInfo], rdi; pvStructInfo
0x180021dad  mov     [rsp+68h+dwFlags], r15d; dwFlags
0x180021db2  call    cs:__imp_CryptDecodeObject
0x180021db8  test    eax, eax
0x180021dba  jz      short loc_180021DD5
0x180021dbc  cmp     [rdi], r15d
0x180021dbf  jz      short loc_180021DD5
0x180021dc1  mov     rax, [rdi+8]
0x180021dc5  test    byte ptr [rax], 40h
0x180021dc8  jz      short loc_180021DCE
0x180021dca  mov     ebx, esi
0x180021dcc  jmp     short loc_180021DD5
0x180021dce  cmp     [rax], r15b
0x180021dd1  cmovl   ebx, r15d
0x180021dd5  mov     rcx, rdi; hMem
0x180021dd8  call    cs:__imp_LocalFree
0x180021dde  mov     rcx, rbp; hMem
0x180021de1  call    cs:__imp_LocalFree
0x180021de7  mov     eax, ebx
0x180021de9  lea     r11, [rsp+68h+var_28]
0x180021dee  mov     rbx, [r11+38h]
0x180021df2  mov     rbp, [r11+40h]
0x180021df6  mov     rsp, r11
0x180021df9  pop     r15
0x180021dfb  pop     r14
0x180021dfd  pop     r12
0x180021dff  pop     rdi
0x180021e00  pop     rsi
0x180021e01  retn
```
