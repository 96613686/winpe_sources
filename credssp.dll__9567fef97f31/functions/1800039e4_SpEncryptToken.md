# SpEncryptToken

- ea: `0x1800039e4`
- end: `0x180003d00`
- name: `SpEncryptToken`
- size: `796`
- prototype: `__int64 __fastcall(PCtxtHandle phContext, __int64, unsigned int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180001b50`
- `0x180002560`

## callees

- `0x1800039e4`
- `0x180003dd9`
- `0x180003de5`
- `0x180003e20`

## import_xrefs

- `SspiCli!EncryptMessage` at `0x180003b62`
- `SspiCli!EncryptMessage` at `0x180003c3c`
- `SspiCli!EncryptMessage` at `0x180003b62`
- `SspiCli!EncryptMessage` at `0x180003c3c`
- `SspiCli!FreeContextBuffer` at `0x180003c8e`
- `SspiCli!FreeContextBuffer` at `0x180003c8e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003aac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003bc8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003aac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003bc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003cbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003cbc`

## pseudocode

```c
__int64 __fastcall SpEncryptToken(PCtxtHandle phContext, __int64 a2, unsigned int a3, int a4)
{
  bool v4; // cf
  __int64 v8; // rax
  unsigned int v9; // r12d
  unsigned int v10; // r8d
  int dwLower_high; // ecx
  unsigned int v12; // r9d
  unsigned __int64 v13; // rcx
  _QWORD *v14; // rdi
  unsigned int v15; // ebx
  __int64 v16; // r9
  unsigned int v17; // r15d
  char *v18; // rbx
  unsigned int dwLower; // eax
  unsigned int v20; // ecx
  unsigned int v21; // eax
  unsigned int v22; // ecx
  _QWORD *v23; // rax
  char *v24; // rbx
  struct _SecBufferDesc pMessage; // [rsp+20h] [rbp-60h] BYREF
  unsigned int dwUpper; // [rsp+30h] [rbp-50h] BYREF
  int v28; // [rsp+34h] [rbp-4Ch]
  _QWORD *v29; // [rsp+38h] [rbp-48h]
  unsigned int Size; // [rsp+40h] [rbp-40h]
  int Size_4; // [rsp+44h] [rbp-3Ch]
  void *Src; // [rsp+48h] [rbp-38h]
  int dwUpper_high; // [rsp+50h] [rbp-30h]
  int v34; // [rsp+54h] [rbp-2Ch]
  char *v35; // [rsp+58h] [rbp-28h]
  int v36; // [rsp+64h] [rbp-1Ch]

  v4 = *(_DWORD *)(a2 + 4) == 0;
  pMessage = 0;
  if ( !v4 )
  {
    v8 = *(_QWORD *)(a2 + 8);
    v9 = 0;
    if ( v8 )
    {
      v10 = *(_DWORD *)v8;
      if ( *(_DWORD *)v8 )
      {
        if ( *(_QWORD *)(v8 + 8) )
        {
          dwLower_high = HIDWORD(phContext[2].dwLower);
          if ( ((a4 != 0 ? 0x8000 : 0x10000) & dwLower_high) != 0 )
          {
            v12 = LODWORD(phContext[2].dwUpper) + HIDWORD(phContext[2].dwUpper);
            if ( v12 >= LODWORD(phContext[2].dwUpper) )
            {
              v13 = v12 * (unsigned __int64)(v10 / LODWORD(phContext[3].dwLower) + 1);
              if ( v13 <= 0xFFFFFFFF && (unsigned int)v13 + v10 >= v10 )
              {
                v14 = LocalAlloc(0x40u, (unsigned int)v13 + v10);
                if ( !v14 )
                  return (unsigned int)-2146893056;
                v16 = *(_QWORD *)(a2 + 8);
                v17 = 0;
                if ( *(_DWORD *)v16 )
                {
                  while ( 1 )
                  {
                    dwUpper = phContext[2].dwUpper;
                    v28 = 7;
                    v29 = (_QWORD *)((char *)v14 + v17);
                    v18 = (char *)v29 + dwUpper;
                    dwLower = phContext[3].dwLower;
                    Src = v18;
                    v20 = *(_DWORD *)v16 - v9;
                    Size_4 = 1;
                    if ( dwLower >= v20 )
                      dwLower = v20;
                    Size = dwLower;
                    memcpy_0((char *)v29 + dwUpper, (const void *)(*(_QWORD *)(v16 + 8) + v9), dwLower);
                    v9 += Size;
                    v34 = 6;
                    v36 = 0;
                    pMessage.cBuffers = 4;
                    pMessage.ulVersion = 0;
                    v35 = &v18[Size];
                    dwUpper_high = HIDWORD(phContext[2].dwUpper);
                    pMessage.pBuffers = (PSecBuffer)&dwUpper;
                    v15 = EncryptMessage(phContext, 0, &pMessage, 0);
                    if ( v15 )
                      goto LABEL_24;
                    v16 = *(_QWORD *)(a2 + 8);
                    v17 += dwUpper + Size + dwUpper_high;
                    if ( v9 >= *(_DWORD *)v16 )
                      goto LABEL_26;
                  }
                }
                v15 = 0;
                goto LABEL_26;
              }
            }
          }
          else
          {
            if ( (dwLower_high & 0x800) == 0 )
              return (unsigned int)-2146893048;
            v21 = HIDWORD(phContext[3].dwLower);
            v22 = v21 + v10;
            if ( v21 + v10 >= v21 && v22 + 8 >= v22 )
            {
              v23 = LocalAlloc(0x40u, v22 + 8);
              v14 = v23;
              if ( !v23 )
                return (unsigned int)-2146893056;
              v24 = (char *)v23 + HIDWORD(phContext[3].dwLower) + 8;
              memcpy_0(v24, *(const void **)(*(_QWORD *)(a2 + 8) + 8LL), **(unsigned int **)(a2 + 8));
              dwUpper = HIDWORD(phContext[3].dwLower);
              v28 = 2;
              v29 = v14 + 1;
              Size = **(_DWORD **)(a2 + 8);
              pMessage.cBuffers = 2;
              pMessage.pBuffers = (PSecBuffer)&dwUpper;
              Size_4 = 1;
              Src = v24;
              pMessage.ulVersion = 0;
              v15 = EncryptMessage(phContext, 0, &pMessage, 0);
              if ( v15 )
              {
LABEL_24:
                v15 = -2146893052;
                LocalFree(v14);
                return v15;
              }
              memmove_0((char *)v14 + dwUpper + 8, Src, Size);
              v17 = Size + dwUpper + 8;
              *v14 = dwUpper;
              v16 = *(_QWORD *)(a2 + 8);
LABEL_26:
              if ( (phContext[2].dwLower & 0x10000000000LL) != 0 )
              {
                FreeContextBuffer(*(PVOID *)(v16 + 8));
                *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL) = v14;
              }
              else
              {
                if ( v17 <= a3 )
                  memcpy_0(*(void **)(v16 + 8), v14, v17);
                else
                  v15 = -2146893023;
                LocalFree(v14);
              }
              **(_DWORD **)(a2 + 8) = v17;
              return v15;
            }
          }
          return (unsigned int)-1073741675;
        }
      }
    }
  }
  return 2148074333LL;
}

```

## disassembly

```asm
0x1800039e4  mov     [rsp-38h+arg_10], rbx
0x1800039e9  push    rbp
0x1800039ea  push    rsi
0x1800039eb  push    rdi
0x1800039ec  push    r12
0x1800039ee  push    r13
0x1800039f0  push    r14
0x1800039f2  push    r15
0x1800039f4  mov     rbp, rsp
0x1800039f7  sub     rsp, 80h
0x1800039fe  mov     rax, cs:__security_cookie
0x180003a05  xor     rax, rsp
0x180003a08  mov     [rbp+var_10], rax
0x180003a0c  cmp     dword ptr [rdx+4], 1
0x180003a10  xorps   xmm0, xmm0
0x180003a13  movups  xmmword ptr [rbp+pMessage.ulVersion], xmm0
0x180003a17  mov     r13d, r8d
0x180003a1a  mov     r14, rdx
0x180003a1d  mov     rsi, rcx
0x180003a20  jb      loc_180003CD4
0x180003a26  mov     rax, [rdx+8]
0x180003a2a  xor     r12d, r12d
0x180003a2d  test    rax, rax
0x180003a30  jz      loc_180003CD4
0x180003a36  mov     r8d, [rax]
0x180003a39  test    r8d, r8d
0x180003a3c  jz      loc_180003CD4
0x180003a42  cmp     [rax+8], r12
0x180003a46  jz      loc_180003CD4
0x180003a4c  mov     ecx, [rcx+24h]
0x180003a4f  neg     r9d
0x180003a52  sbb     eax, eax
0x180003a54  and     eax, 0FFFF8000h
0x180003a59  add     eax, 10000h
0x180003a5e  test    ecx, eax
0x180003a60  jz      loc_180003BA5
0x180003a66  mov     r9d, [rsi+2Ch]
0x180003a6a  add     r9d, [rsi+28h]
0x180003a6e  cmp     r9d, [rsi+28h]
0x180003a72  jb      loc_180003B9B
0x180003a78  mov     eax, r8d
0x180003a7b  xor     edx, edx
0x180003a7d  div     dword ptr [rsi+30h]
0x180003a80  lea     ecx, [rax+1]
0x180003a83  mov     eax, r9d
0x180003a86  imul    rcx, rax
0x180003a8a  mov     eax, 0FFFFFFFFh
0x180003a8f  cmp     rcx, rax
0x180003a92  ja      loc_180003B9B
0x180003a98  lea     eax, [rcx+r8]
0x180003a9c  cmp     eax, r8d
0x180003a9f  jb      loc_180003B9B
0x180003aa5  mov     edx, eax; uBytes
0x180003aa7  lea     ecx, [r12+40h]; uFlags
0x180003aac  call    cs:__imp_LocalAlloc
0x180003ab2  mov     rdi, rax
0x180003ab5  test    rax, rax
0x180003ab8  jnz     short loc_180003AC4
0x180003aba  mov     ebx, 80090300h
0x180003abf  jmp     loc_180003CC9
0x180003ac4  mov     r9, [r14+8]
0x180003ac8  mov     r15d, r12d
0x180003acb  cmp     [r9], r12d
0x180003ace  jbe     loc_180003B93
0x180003ad4  mov     eax, [rsi+28h]
0x180003ad7  mov     [rbp+var_50], eax
0x180003ada  mov     [rbp+var_4C], 7
0x180003ae1  mov     ecx, r15d
0x180003ae4  add     rcx, rdi
0x180003ae7  mov     edx, r12d
0x180003aea  mov     [rbp+var_48], rcx
0x180003aee  lea     rbx, [rax+rcx]
0x180003af2  mov     eax, [rsi+30h]
0x180003af5  mov     [rbp+Src], rbx
0x180003af9  mov     ecx, [r9]
0x180003afc  sub     ecx, r12d
0x180003aff  mov     dword ptr [rbp+Size+4], 1
0x180003b06  cmp     eax, ecx
0x180003b08  cmovnb  eax, ecx
0x180003b0b  mov     rcx, rbx; void *
0x180003b0e  mov     r8d, eax; Size
0x180003b11  mov     dword ptr [rbp+Size], r8d
0x180003b15  add     rdx, [r9+8]; Src
0x180003b19  call    memcpy_0
0x180003b1e  mov     ecx, dword ptr [rbp+Size]
0x180003b21  lea     r8, [rbp+pMessage]; pMessage
0x180003b25  add     r12d, ecx
0x180003b28  mov     [rbp+var_2C], 6
0x180003b2f  xor     r9d, r9d; MessageSeqNo
0x180003b32  mov     [rbp+var_1C], 0
0x180003b39  xor     edx, edx; fQOP
0x180003b3b  mov     [rbp+pMessage.cBuffers], 4
0x180003b42  lea     rax, [rbx+rcx]
0x180003b46  mov     [rbp+pMessage.ulVersion], 0
0x180003b4d  mov     [rbp+var_28], rax
0x180003b51  mov     rcx, rsi; phContext
0x180003b54  mov     eax, [rsi+2Ch]
0x180003b57  mov     [rbp+var_30], eax
0x180003b5a  lea     rax, [rbp+var_50]
0x180003b5e  mov     [rbp+pMessage.pBuffers], rax
0x180003b62  call    cs:__imp_EncryptMessage
0x180003b68  mov     ebx, eax
0x180003b6a  test    eax, eax
0x180003b6c  jnz     loc_180003C48
0x180003b72  mov     r8d, [rbp+var_30]
0x180003b76  add     r8d, dword ptr [rbp+Size]
0x180003b7a  add     r8d, [rbp+var_50]
0x180003b7e  mov     r9, [r14+8]
0x180003b82  add     r15d, r8d
0x180003b85  cmp     r12d, [r9]
0x180003b88  jb      loc_180003AD4
0x180003b8e  jmp     loc_180003C81
0x180003b93  mov     ebx, r12d
0x180003b96  jmp     loc_180003C81
0x180003b9b  mov     ebx, 0C0000095h
0x180003ba0  jmp     loc_180003CC9
0x180003ba5  bt      ecx, 0Bh
0x180003ba9  jnb     loc_180003CCD
0x180003baf  mov     eax, [rsi+34h]
0x180003bb2  lea     ecx, [rax+r8]
0x180003bb6  cmp     ecx, eax
0x180003bb8  jb      short loc_180003B9B
0x180003bba  lea     eax, [rcx+8]
0x180003bbd  cmp     eax, ecx
0x180003bbf  jb      short loc_180003B9B
0x180003bc1  mov     edx, eax; uBytes
0x180003bc3  mov     ecx, 40h ; '@'; uFlags
0x180003bc8  call    cs:__imp_LocalAlloc
0x180003bce  mov     rdi, rax
0x180003bd1  test    rax, rax
0x180003bd4  jz      loc_180003ABA
0x180003bda  mov     rdx, [r14+8]
0x180003bde  mov     ebx, [rsi+34h]
0x180003be1  add     rbx, 8
0x180003be5  add     rbx, rax
0x180003be8  mov     r8d, [rdx]; Size
0x180003beb  mov     rcx, rbx; void *
0x180003bee  mov     rdx, [rdx+8]; Src
0x180003bf2  call    memcpy_0
0x180003bf7  mov     eax, [rsi+34h]
0x180003bfa  lea     r8, [rbp+pMessage]; pMessage
0x180003bfe  mov     [rbp+var_50], eax
0x180003c01  mov     edx, 2
0x180003c06  mov     [rbp+var_4C], edx
0x180003c09  lea     rax, [rdi+8]
0x180003c0d  mov     [rbp+var_48], rax
0x180003c11  xor     r9d, r9d; MessageSeqNo
0x180003c14  mov     rax, [r14+8]
0x180003c18  mov     ecx, [rax]
0x180003c1a  lea     rax, [rbp+var_50]
0x180003c1e  mov     dword ptr [rbp+Size], ecx
0x180003c21  mov     rcx, rsi; phContext
0x180003c24  mov     [rbp+pMessage.cBuffers], edx
0x180003c27  xor     edx, edx; fQOP
0x180003c29  mov     [rbp+pMessage.pBuffers], rax
0x180003c2d  mov     dword ptr [rbp+Size+4], 1
0x180003c34  mov     [rbp+Src], rbx
0x180003c38  mov     [rbp+pMessage.ulVersion], r12d
0x180003c3c  call    cs:__imp_EncryptMessage
0x180003c42  mov     ebx, eax
0x180003c44  test    eax, eax
0x180003c46  jz      short loc_180003C58
0x180003c48  mov     rcx, rdi; hMem
0x180003c4b  mov     ebx, 80090304h
0x180003c50  call    cs:__imp_LocalFree
0x180003c56  jmp     short loc_180003CC9
0x180003c58  mov     ecx, [rbp+var_50]
0x180003c5b  mov     r8d, dword ptr [rbp+Size]; Size
0x180003c5f  add     rcx, 8
0x180003c63  mov     rdx, [rbp+Src]; Src
0x180003c67  add     rcx, rdi; void *
0x180003c6a  call    memmove_0
0x180003c6f  mov     ecx, [rbp+var_50]
0x180003c72  lea     r15d, [rcx+8]
0x180003c76  add     r15d, dword ptr [rbp+Size]
0x180003c7a  mov     [rdi], rcx
0x180003c7d  mov     r9, [r14+8]
0x180003c81  test    dword ptr [rsi+24h], 100h
0x180003c88  jz      short loc_180003C9E
0x180003c8a  mov     rcx, [r9+8]; pvContextBuffer
0x180003c8e  call    cs:__imp_FreeContextBuffer
0x180003c94  mov     rax, [r14+8]
0x180003c98  mov     [rax+8], rdi
0x180003c9c  jmp     short loc_180003CC2
0x180003c9e  cmp     r15d, r13d
0x180003ca1  jbe     short loc_180003CAA
0x180003ca3  mov     ebx, 80090321h
0x180003ca8  jmp     short loc_180003CB9
0x180003caa  mov     rcx, [r9+8]; void *
0x180003cae  mov     rdx, rdi; Src
0x180003cb1  mov     r8d, r15d; Size
0x180003cb4  call    memcpy_0
0x180003cb9  mov     rcx, rdi; hMem
0x180003cbc  call    cs:__imp_LocalFree
0x180003cc2  mov     rax, [r14+8]
0x180003cc6  mov     [rax], r15d
0x180003cc9  mov     eax, ebx
0x180003ccb  jmp     short loc_180003CD9
0x180003ccd  mov     ebx, 80090308h
0x180003cd2  jmp     short loc_180003CC9
0x180003cd4  mov     eax, 8009035Dh
0x180003cd9  mov     rcx, [rbp+var_10]
0x180003cdd  xor     rcx, rsp; StackCookie
0x180003ce0  call    __security_check_cookie
0x180003ce5  mov     rbx, [rsp+80h+arg_10]
0x180003ced  add     rsp, 80h
0x180003cf4  pop     r15
0x180003cf6  pop     r14
0x180003cf8  pop     r13
0x180003cfa  pop     r12
0x180003cfc  pop     rdi
0x180003cfd  pop     rsi
0x180003cfe  pop     rbp
0x180003cff  retn
```
