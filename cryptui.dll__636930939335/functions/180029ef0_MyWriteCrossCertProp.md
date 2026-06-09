# _MyWriteCrossCertProp

- ea: `0x180029ef0`
- end: `0x18002a08c`
- name: `_MyWriteCrossCertProp`
- size: `412`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180029ef0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029f4d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029f6b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a00f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029f4d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029f6b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a00f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a062`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a06b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a075`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a062`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a06b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029ff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029ff0`
- `CRYPT32!CryptEncodeObject` at `0x180029fe6`
- `CRYPT32!CryptEncodeObject` at `0x18002a034`
- `CRYPT32!CryptEncodeObject` at `0x180029fe6`
- `CRYPT32!CryptEncodeObject` at `0x18002a034`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18002a058`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18002a058`

## pseudocode

```c
__int64 __fastcall MyWriteCrossCertProp(__int64 a1, unsigned int a2, const CERT_CONTEXT *a3)
{
  char *v3; // r14
  __int64 v4; // rdi
  unsigned int v5; // ebx
  unsigned int v8; // r9d
  __int64 v9; // r8
  __int64 v10; // rdx
  char *v11; // rcx
  __int64 v12; // rax
  signed int LastError; // eax
  DWORD *v14; // r9
  DWORD pcbEncoded[4]; // [rsp+30h] [rbp-20h] BYREF
  __int128 pvStructInfo; // [rsp+40h] [rbp-10h] BYREF

  v3 = 0;
  v4 = a2;
  v5 = 0;
  *(_OWORD *)pcbEncoded = 0;
  pvStructInfo = 0;
  if ( !a1 || !a2 )
  {
    v14 = 0;
    goto LABEL_17;
  }
  if ( a2 > 0xAAAAAA9 )
    goto LABEL_15;
  LODWORD(pvStructInfo) = 28800;
  DWORD1(pvStructInfo) = a2;
  *((_QWORD *)&pvStructInfo + 1) = LocalAlloc(0x40u, 16LL * a2);
  if ( !*((_QWORD *)&pvStructInfo + 1) )
    goto LABEL_15;
  v3 = (char *)LocalAlloc(0x40u, 24 * v4);
  if ( !v3 )
    goto LABEL_15;
  v8 = 0;
  if ( (_DWORD)v4 )
  {
    v9 = 0;
    do
    {
      v10 = 2 * v9;
      ++v8;
      *(_DWORD *)(*((_QWORD *)&pvStructInfo + 1) + 8 * v10) = 1;
      v11 = &v3[24 * v9];
      *(_QWORD *)(*((_QWORD *)&pvStructInfo + 1) + 8 * v10 + 8) = v11;
      *(_DWORD *)v11 = 7;
      v12 = *(_QWORD *)(a1 + 8 * v9++);
      *((_QWORD *)v11 + 1) = v12;
    }
    while ( v8 < (unsigned int)v4 );
  }
  pcbEncoded[0] = 0;
  *(_QWORD *)&pcbEncoded[2] = 0;
  if ( !CryptEncodeObject(0x10001u, (LPCSTR)0x3A, &pvStructInfo, 0, pcbEncoded) )
    goto LABEL_10;
  *(_QWORD *)&pcbEncoded[2] = LocalAlloc(0x40u, pcbEncoded[0]);
  if ( !*(_QWORD *)&pcbEncoded[2] )
  {
LABEL_15:
    v5 = -2147024882;
    goto LABEL_18;
  }
  if ( CryptEncodeObject(0x10001u, (LPCSTR)0x3A, &pvStructInfo, *(BYTE **)&pcbEncoded[2], pcbEncoded) )
  {
    v14 = pcbEncoded;
LABEL_17:
    CertSetCertificateContextProperty(a3, 0x17u, 0, v14);
    goto LABEL_18;
  }
LABEL_10:
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_18:
  LocalFree(*(HLOCAL *)&pcbEncoded[2]);
  LocalFree(v3);
  LocalFree(*((HLOCAL *)&pvStructInfo + 1));
  return v5;
}

```

## disassembly

```asm
0x180029ef0  push    rbp
0x180029ef2  push    rbx
0x180029ef3  push    rsi
0x180029ef4  push    rdi
0x180029ef5  push    r12
0x180029ef7  push    r14
0x180029ef9  push    r15
0x180029efb  mov     rbp, rsp
0x180029efe  sub     rsp, 50h
0x180029f02  xor     r14d, r14d
0x180029f05  mov     edi, edx
0x180029f07  xor     ebx, ebx
0x180029f09  xorps   xmm0, xmm0
0x180029f0c  xorps   xmm1, xmm1
0x180029f0f  mov     r15, r8
0x180029f12  mov     r12, rcx
0x180029f15  movups  xmmword ptr [rbp+var_20], xmm0
0x180029f19  movups  [rbp+pvStructInfo], xmm1
0x180029f1d  test    rcx, rcx
0x180029f20  jz      loc_18002A04B
0x180029f26  test    edx, edx
0x180029f28  jz      loc_18002A04B
0x180029f2e  cmp     edi, 0AAAAAA9h
0x180029f34  ja      loc_18002A044
0x180029f3a  mov     edx, edi
0x180029f3c  mov     dword ptr [rbp+pvStructInfo], 7080h
0x180029f43  shl     rdx, 4; uBytes
0x180029f47  lea     ecx, [rbx+40h]; uFlags
0x180029f4a  mov     dword ptr [rbp+pvStructInfo+4], edi
0x180029f4d  call    cs:__imp_LocalAlloc
0x180029f53  mov     qword ptr [rbp+pvStructInfo+8], rax
0x180029f57  test    rax, rax
0x180029f5a  jz      loc_18002A044
0x180029f60  lea     rdx, [rdi+rdi*2]
0x180029f64  shl     rdx, 3; uBytes
0x180029f68  lea     ecx, [rbx+40h]; uFlags
0x180029f6b  call    cs:__imp_LocalAlloc
0x180029f71  mov     r14, rax
0x180029f74  test    rax, rax
0x180029f77  jz      loc_18002A044
0x180029f7d  xor     r9d, r9d
0x180029f80  test    edi, edi
0x180029f82  jz      short loc_180029FC2
0x180029f84  xor     r8d, r8d
0x180029f87  mov     rax, qword ptr [rbp+pvStructInfo+8]
0x180029f8b  mov     rdx, r8
0x180029f8e  add     rdx, rdx
0x180029f91  inc     r9d
0x180029f94  mov     dword ptr [rax+rdx*8], 1
0x180029f9b  lea     rax, [r8+r8*2]
0x180029f9f  lea     rcx, [r14+rax*8]
0x180029fa3  mov     rax, qword ptr [rbp+pvStructInfo+8]
0x180029fa7  mov     [rax+rdx*8+8], rcx
0x180029fac  mov     dword ptr [rcx], 7
0x180029fb2  mov     rax, [r12+r8*8]
0x180029fb6  inc     r8
0x180029fb9  mov     [rcx+8], rax
0x180029fbd  cmp     r9d, edi
0x180029fc0  jb      short loc_180029F87
0x180029fc2  xor     r9d, r9d; pbEncoded
0x180029fc5  mov     [rbp+var_20], ebx
0x180029fc8  lea     rax, [rbp+var_20]
0x180029fcc  mov     qword ptr [rbp+var_20+8], rbx
0x180029fd0  mov     esi, 10001h
0x180029fd5  mov     [rsp+50h+pcbEncoded], rax; pcbEncoded
0x180029fda  lea     r8, [rbp+pvStructInfo]; pvStructInfo
0x180029fde  mov     ecx, esi; dwCertEncodingType
0x180029fe0  lea     edi, [r9+3Ah]
0x180029fe4  mov     edx, edi; lpszStructType
0x180029fe6  call    cs:__imp_CryptEncodeObject
0x180029fec  test    eax, eax
0x180029fee  jnz     short loc_18002A007
0x180029ff0  call    cs:__imp_GetLastError
0x180029ff6  mov     ebx, eax
0x180029ff8  test    eax, eax
0x180029ffa  jle     short loc_18002A05E
0x180029ffc  movzx   ebx, ax
0x180029fff  or      ebx, 80070000h
0x18002a005  jmp     short loc_18002A05E
0x18002a007  mov     edx, [rbp+var_20]; uBytes
0x18002a00a  mov     ecx, 40h ; '@'; uFlags
0x18002a00f  call    cs:__imp_LocalAlloc
0x18002a015  mov     qword ptr [rbp+var_20+8], rax
0x18002a019  test    rax, rax
0x18002a01c  jz      short loc_18002A044
0x18002a01e  mov     r9, qword ptr [rbp+var_20+8]; pbEncoded
0x18002a022  lea     rax, [rbp+var_20]
0x18002a026  lea     r8, [rbp+pvStructInfo]; pvStructInfo
0x18002a02a  mov     [rsp+50h+pcbEncoded], rax; pcbEncoded
0x18002a02f  mov     rdx, rdi; lpszStructType
0x18002a032  mov     ecx, esi; dwCertEncodingType
0x18002a034  call    cs:__imp_CryptEncodeObject
0x18002a03a  test    eax, eax
0x18002a03c  jz      short loc_180029FF0
0x18002a03e  lea     r9, [rbp+var_20]
0x18002a042  jmp     short loc_18002A04E
0x18002a044  mov     ebx, 8007000Eh
0x18002a049  jmp     short loc_18002A05E
0x18002a04b  xor     r9d, r9d; pvData
0x18002a04e  xor     r8d, r8d; dwFlags
0x18002a051  mov     rcx, r15; pCertContext
0x18002a054  lea     edx, [r8+17h]; dwPropId
0x18002a058  call    cs:__imp_CertSetCertificateContextProperty
0x18002a05e  mov     rcx, qword ptr [rbp+var_20+8]; hMem
0x18002a062  call    cs:__imp_LocalFree
0x18002a068  mov     rcx, r14; hMem
0x18002a06b  call    cs:__imp_LocalFree
0x18002a071  mov     rcx, qword ptr [rbp+pvStructInfo+8]; hMem
0x18002a075  call    cs:__imp_LocalFree
0x18002a07b  mov     eax, ebx
0x18002a07d  add     rsp, 50h
0x18002a081  pop     r15
0x18002a083  pop     r14
0x18002a085  pop     r12
0x18002a087  pop     rdi
0x18002a088  pop     rsi
0x18002a089  pop     rbx
0x18002a08a  pop     rbp
0x18002a08b  retn
```
