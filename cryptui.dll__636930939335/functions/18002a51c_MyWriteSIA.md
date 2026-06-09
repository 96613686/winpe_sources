# _MyWriteSIA

- ea: `0x18002a51c`
- end: `0x18002a645`
- name: `_MyWriteSIA`
- size: `297`
- prototype: `__int64 __fastcall(int, int, int, int, PCCERT_CONTEXT pCertContext)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002a500`

## callees

- `0x18002a51c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a56f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a56f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a62a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a634`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a62a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a5f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a5f5`
- `CRYPT32!CryptEncodeObjectEx` at `0x18002a5eb`
- `CRYPT32!CryptEncodeObjectEx` at `0x18002a5eb`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18002a620`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18002a620`

## pseudocode

```c
__int64 __fastcall MyWriteSIA(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, PCCERT_CONTEXT pCertContext)
{
  unsigned int v5; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rax
  signed int LastError; // eax
  DWORD *v13; // r9
  DWORD pvEncoded[4]; // [rsp+40h] [rbp-28h] BYREF
  __int128 pvStructInfo; // [rsp+50h] [rbp-18h] BYREF

  v5 = 0;
  *(_OWORD *)pvEncoded = 0;
  pvStructInfo = 0;
  if ( !a1 || !a2 )
  {
    v13 = 0;
    goto LABEL_14;
  }
  if ( a2 >= 0x7FFFFFF
    || (LODWORD(pvStructInfo) = a2,
        *((_QWORD *)&pvStructInfo + 1) = LocalAlloc(0x40u, 32LL * a2),
        (v8 = *((_QWORD *)&pvStructInfo + 1)) == 0) )
  {
    v5 = -2147024882;
    goto LABEL_15;
  }
  v9 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      v10 = 32LL * (unsigned int)v9;
      *(_QWORD *)(v10 + v8) = "1.3.6.1.5.5.7.48.1";
      *(_DWORD *)(v10 + v8 + 8) = 7;
      v11 = *(_QWORD *)(a1 + 8 * v9);
      v9 = (unsigned int)(v9 + 1);
      *(_QWORD *)(v10 + v8 + 16) = v11;
      if ( (unsigned int)v9 >= a2 )
        break;
      v8 = *((_QWORD *)&pvStructInfo + 1);
    }
  }
  pvEncoded[0] = 0;
  *(_QWORD *)&pvEncoded[2] = 0;
  if ( CryptEncodeObjectEx(0x10001u, (LPCSTR)0x20, &pvStructInfo, 0x8000u, 0, &pvEncoded[2], pvEncoded) )
  {
    v13 = pvEncoded;
LABEL_14:
    CertSetCertificateContextProperty(pCertContext, 0x51u, 0, v13);
    goto LABEL_15;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_15:
  LocalFree(*(HLOCAL *)&pvEncoded[2]);
  LocalFree(*((HLOCAL *)&pvStructInfo + 1));
  return v5;
}

```

## disassembly

```asm
0x18002a51c  push    rbp
0x18002a51e  push    rbx
0x18002a51f  push    rsi
0x18002a520  push    rdi
0x18002a521  mov     rbp, rsp
0x18002a524  sub     rsp, 68h
0x18002a528  xor     ebx, ebx
0x18002a52a  mov     edi, edx
0x18002a52c  xorps   xmm0, xmm0
0x18002a52f  xorps   xmm1, xmm1
0x18002a532  mov     rsi, rcx
0x18002a535  movups  xmmword ptr [rbp+var_28], xmm0
0x18002a539  movups  [rbp+pvStructInfo], xmm1
0x18002a53d  test    rcx, rcx
0x18002a540  jz      loc_18002A612
0x18002a546  test    edx, edx
0x18002a548  jz      loc_18002A612
0x18002a54e  cmp     edi, 7FFFFFFh
0x18002a554  jb      short loc_18002A560
0x18002a556  mov     ebx, 8007000Eh
0x18002a55b  jmp     loc_18002A626
0x18002a560  mov     rdx, rdi
0x18002a563  mov     dword ptr [rbp+pvStructInfo], edi
0x18002a566  shl     rdx, 5; uBytes
0x18002a56a  mov     ecx, 40h ; '@'; uFlags
0x18002a56f  call    cs:__imp_LocalAlloc
0x18002a575  mov     qword ptr [rbp+pvStructInfo+8], rax
0x18002a579  mov     rdx, rax
0x18002a57c  test    rax, rax
0x18002a57f  jz      short loc_18002A556
0x18002a581  xor     r8d, r8d
0x18002a584  test    edi, edi
0x18002a586  jz      short loc_18002A5B9
0x18002a588  mov     ecx, r8d
0x18002a58b  lea     r9, a1361557481; "1.3.6.1.5.5.7.48.1"
0x18002a592  shl     rcx, 5
0x18002a596  mov     [rcx+rdx], r9
0x18002a59a  mov     dword ptr [rcx+rdx+8], 7
0x18002a5a2  mov     rax, [rsi+r8*8]
0x18002a5a6  inc     r8d
0x18002a5a9  mov     [rcx+rdx+10h], rax
0x18002a5ae  cmp     r8d, edi
0x18002a5b1  jnb     short loc_18002A5B9
0x18002a5b3  mov     rdx, qword ptr [rbp+pvStructInfo+8]
0x18002a5b7  jmp     short loc_18002A588
0x18002a5b9  lea     rax, [rbp+var_28]
0x18002a5bd  mov     [rbp+var_28], ebx
0x18002a5c0  mov     [rsp+68h+pcbEncoded], rax; pcbEncoded
0x18002a5c5  lea     r8, [rbp+pvStructInfo]; pvStructInfo
0x18002a5c9  lea     rax, [rbp+var_28+8]
0x18002a5cd  mov     qword ptr [rbp+var_28+8], rbx
0x18002a5d1  mov     [rsp+68h+pvEncoded], rax; pvEncoded
0x18002a5d6  mov     r9d, 8000h; dwFlags
0x18002a5dc  mov     edx, 20h ; ' '; lpszStructType
0x18002a5e1  mov     [rsp+68h+pEncodePara], rbx; pEncodePara
0x18002a5e6  mov     ecx, 10001h; dwCertEncodingType
0x18002a5eb  call    cs:__imp_CryptEncodeObjectEx
0x18002a5f1  test    eax, eax
0x18002a5f3  jnz     short loc_18002A60C
0x18002a5f5  call    cs:__imp_GetLastError
0x18002a5fb  mov     ebx, eax
0x18002a5fd  test    eax, eax
0x18002a5ff  jle     short loc_18002A626
0x18002a601  movzx   ebx, ax
0x18002a604  or      ebx, 80070000h
0x18002a60a  jmp     short loc_18002A626
0x18002a60c  lea     r9, [rbp+var_28]
0x18002a610  jmp     short loc_18002A615
0x18002a612  xor     r9d, r9d; pvData
0x18002a615  mov     rcx, [rbp+pCertContext]; pCertContext
0x18002a619  xor     r8d, r8d; dwFlags
0x18002a61c  lea     edx, [r8+51h]; dwPropId
0x18002a620  call    cs:__imp_CertSetCertificateContextProperty
0x18002a626  mov     rcx, qword ptr [rbp+var_28+8]; hMem
0x18002a62a  call    cs:__imp_LocalFree
0x18002a630  mov     rcx, qword ptr [rbp+pvStructInfo+8]; hMem
0x18002a634  call    cs:__imp_LocalFree
0x18002a63a  mov     eax, ebx
0x18002a63c  add     rsp, 68h
0x18002a640  pop     rdi
0x18002a641  pop     rsi
0x18002a642  pop     rbx
0x18002a643  pop     rbp
0x18002a644  retn
```
