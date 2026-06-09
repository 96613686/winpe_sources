# TREE_HASH_TABLE::CalcHash(ushort const *,ulong *)

- ea: `0x180003b80`
- end: `0x180003fa0`
- name: `?CalcHash@TREE_HASH_TABLE@@QEAAJPEBGPEAK@Z`
- size: `1056`
- prototype: `int(TREE_HASH_TABLE *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004d50`

## callees

- `0x180003b80`
- `0x180003fb0`
- `0x18002e516`
- `0x18002e52e`
- `0x18002e560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003e04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003e04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f51`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f51`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f85`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003d6f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003d6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f71`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180003e6d`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180003e6d`
- `bcrypt!BCryptCreateHash` at `0x180003e9d`
- `bcrypt!BCryptCreateHash` at `0x180003e9d`
- `bcrypt!BCryptFinishHash` at `0x180003ee3`
- `bcrypt!BCryptFinishHash` at `0x180003ee3`
- `bcrypt!BCryptHashData` at `0x180003ebe`
- `bcrypt!BCryptHashData` at `0x180003ebe`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180003efe`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180003efe`
- `bcrypt!BCryptDestroyHash` at `0x180003f14`
- `bcrypt!BCryptDestroyHash` at `0x180003f14`

## pseudocode

```c
__int64 __fastcall TREE_HASH_TABLE::CalcHash(TREE_HASH_TABLE *this, const unsigned __int16 *a2, unsigned int *a3)
{
  const unsigned __int16 *v3; // rdi
  int v4; // r14d
  unsigned __int16 v5; // ax
  int v6; // ebx
  char v8; // r13
  UCHAR *v9; // rsi
  __int64 v10; // rax
  __int64 v12; // r12
  UCHAR *v13; // rbx
  __int64 v14; // r12
  unsigned __int16 v15; // cx
  HANDLE ProcessHeap; // rax
  UCHAR *v17; // rax
  UCHAR *v18; // rcx
  __int64 v19; // rdx
  UCHAR *v20; // rax
  __int128 v21; // xmm0
  signed int v22; // ebx
  signed int LastError; // eax
  ULONG v24; // ebx
  unsigned __int64 v25; // rdx
  unsigned int v26; // r8d
  NTSTATUS v27; // r14d
  HANDLE v28; // rax
  HANDLE v29; // rax
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-C0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int *v32; // [rsp+58h] [rbp-B0h]
  int v33; // [rsp+88h] [rbp-80h]
  __int16 v34; // [rsp+8Ch] [rbp-7Ch]
  UCHAR pbOutput[16]; // [rsp+98h] [rbp-70h] BYREF
  __int128 v36; // [rsp+A8h] [rbp-60h]
  UCHAR pbInput[2]; // [rsp+B8h] [rbp-50h] BYREF
  char v38[526]; // [rsp+BAh] [rbp-4Eh] BYREF

  v3 = a2;
  v32 = a3;
  if ( !a2 || !a3 )
    return 2147942487LL;
  v4 = 0;
  if ( !*((_DWORD *)this + 6) )
  {
    v15 = *a2;
    v6 = 0;
    if ( *a2 )
    {
      do
      {
        ++v3;
        v6 = (v15 & 0xFFDF) + 101 * v6;
        v15 = *v3;
      }
      while ( *v3 );
    }
    goto LABEL_7;
  }
  if ( !*((_DWORD *)this + 7) )
  {
    v5 = *a2;
    v6 = 0;
    if ( *a2 )
    {
      do
      {
        ++v3;
        v6 = v5 + 101 * v6;
        v5 = *v3;
      }
      while ( *v3 );
    }
LABEL_7:
    *v32 = (69069 * v6 + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * v6 + 12345) >> 16);
    return (unsigned int)v4;
  }
  memset_0(v38, 0, 0x206u);
  v8 = 0;
  v33 = 520;
  v34 = 256;
  *(_WORD *)pbInput = 0;
  v9 = pbInput;
  v10 = -1;
  while ( v3[++v10] != 0 )
    ;
  v12 = (unsigned int)(2 * v10);
  if ( (unsigned __int64)(v12 + 2) <= 0x208 )
    goto LABEL_12;
  if ( (unsigned __int64)(v12 + 128) > 0xFFFFFFFF )
  {
    return (unsigned int)-2147024362;
  }
  else
  {
    if ( (unsigned int)(v12 + 128) <= 0x208 )
    {
LABEL_12:
      v13 = pbInput;
LABEL_13:
      memcpy_0(v13, v3, (unsigned int)v12);
      v14 = (unsigned int)v12 >> 1;
      v4 = v14;
      *(_WORD *)&v13[2 * v14] = 0;
      goto LABEL_28;
    }
    ProcessHeap = GetProcessHeap();
    v17 = (UCHAR *)HeapAlloc(ProcessHeap, 0, (unsigned int)(v12 + 128));
    v13 = v17;
    if ( v17 )
    {
      v18 = v17;
      v19 = 4;
      v20 = pbInput;
      do
      {
        v18 += 128;
        v21 = *(_OWORD *)v20;
        v20 += 128;
        *((_OWORD *)v18 - 8) = v21;
        *((_OWORD *)v18 - 7) = *((_OWORD *)v20 - 7);
        *((_OWORD *)v18 - 6) = *((_OWORD *)v20 - 6);
        *((_OWORD *)v18 - 5) = *((_OWORD *)v20 - 5);
        *((_OWORD *)v18 - 4) = *((_OWORD *)v20 - 4);
        *((_OWORD *)v18 - 3) = *((_OWORD *)v20 - 3);
        *((_OWORD *)v18 - 2) = *((_OWORD *)v20 - 2);
        *((_OWORD *)v18 - 1) = *((_OWORD *)v20 - 1);
        --v19;
      }
      while ( v19 );
      v8 = 1;
      *(_QWORD *)v18 = *(_QWORD *)v20;
      v9 = v13;
      goto LABEL_13;
    }
    SetLastError(8u);
    LastError = GetLastError();
    v22 = LastError;
    if ( LastError > 0 )
      v22 = (unsigned __int16)LastError | 0x80070000;
    if ( v22 >= 0 )
    {
LABEL_28:
      phAlgorithm = 0;
      phHash = 0;
      *(_OWORD *)pbOutput = 0;
      v36 = 0;
      if ( v9 && (v24 = 2 * v4) != 0 )
      {
        v27 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
        if ( v27 >= 0 )
        {
          v27 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
          if ( v27 >= 0 )
          {
            v27 = BCryptHashData(phHash, v9, v24, 0);
            if ( v27 >= 0 )
              v27 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
          }
        }
        if ( phAlgorithm )
          BCryptCloseAlgorithmProvider(phAlgorithm, 0);
        if ( phHash )
          BCryptDestroyHash(phHash);
        v4 = v27 | 0x10000000;
        if ( v4 >= 0 )
        {
          v6 = HashBlob(pbOutput, v25, v26);
          if ( v8 )
          {
            v28 = GetProcessHeap();
            HeapFree(v28, 0, v9);
          }
          goto LABEL_7;
        }
      }
      else
      {
        v4 = -805306355;
      }
      if ( v8 )
      {
        v29 = GetProcessHeap();
        HeapFree(v29, 0, v9);
      }
      return (unsigned int)v4;
    }
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180003b80  mov     r11, rsp
0x180003b83  push    rbp
0x180003b84  push    rdi
0x180003b85  lea     rbp, [r11-208h]
0x180003b8c  sub     rsp, 2F8h
0x180003b93  mov     rax, cs:__security_cookie
0x180003b9a  xor     rax, rsp
0x180003b9d  mov     [rbp+200h+var_40], rax
0x180003ba4  mov     rax, r8
0x180003ba7  mov     rdi, rdx
0x180003baa  mov     [rsp+300h+var_2B0], rax
0x180003baf  test    rdx, rdx
0x180003bb2  jz      loc_180003F96
0x180003bb8  test    rax, rax
0x180003bbb  jz      loc_180003F96
0x180003bc1  mov     [r11-30h], r14
0x180003bc5  xor     r14d, r14d
0x180003bc8  mov     [r11+8], rbx
0x180003bcc  mov     [r11-18h], rsi
0x180003bd0  mov     [r11-20h], r12
0x180003bd4  mov     [r11-28h], r13
0x180003bd8  mov     [r11-38h], r15
0x180003bdc  cmp     [rcx+18h], r14d
0x180003be0  jz      loc_180003D04
0x180003be6  cmp     [rcx+1Ch], r14d
0x180003bea  jnz     loc_180003C86
0x180003bf0  movzx   eax, word ptr [rdx]
0x180003bf3  xor     ebx, ebx
0x180003bf5  test    ax, ax
0x180003bf8  jz      short loc_180003C14
0x180003bfa  nop     word ptr [rax+rax+00h]
0x180003c00  imul    ebx, 65h ; 'e'
0x180003c03  lea     rdi, [rdi+2]
0x180003c07  movzx   eax, ax
0x180003c0a  add     ebx, eax
0x180003c0c  movzx   eax, word ptr [rdi]
0x180003c0f  test    ax, ax
0x180003c12  jnz     short loc_180003C00
0x180003c14  imul    eax, ebx, 10DCDh
0x180003c1a  imul    ecx, ebx, 41C64E6Dh
0x180003c20  inc     eax
0x180003c22  add     ecx, 3039h
0x180003c28  and     eax, 0FFFF0000h
0x180003c2d  shr     ecx, 10h
0x180003c30  or      ecx, eax
0x180003c32  mov     rax, [rsp+300h+var_2B0]
0x180003c37  mov     [rax], ecx
0x180003c39  mov     eax, r14d
0x180003c3c  mov     rbx, [rsp+300h+arg_0]
0x180003c44  mov     r13, [rsp+300h+var_20]
0x180003c4c  mov     r12, [rsp+300h+var_18]
0x180003c54  mov     rsi, [rsp+2F0h]
0x180003c5c  mov     r15, [rsp+300h+var_30]
0x180003c64  mov     r14, [rsp+300h+var_28]
0x180003c6c  mov     rcx, [rbp+200h+var_40]
0x180003c73  xor     rcx, rsp; StackCookie
0x180003c76  call    __security_check_cookie
0x180003c7b  add     rsp, 2F8h
0x180003c82  pop     rdi
0x180003c83  pop     rbp
0x180003c84  retn
0x180003c86  xor     edx, edx; Val
0x180003c88  lea     rcx, [rbp+200h+var_24E]; void *
0x180003c8c  mov     r8d, 206h; Size
0x180003c92  call    memset_0
0x180003c97  xor     r13b, r13b
0x180003c9a  mov     [rbp+200h+var_280], 208h
0x180003ca1  xor     eax, eax
0x180003ca3  mov     [rbp+200h+var_27C], 100h
0x180003ca9  mov     word ptr [rbp+200h+pbInput], ax
0x180003cad  lea     rsi, [rbp+200h+pbInput]
0x180003cb1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003cb8  nop     dword ptr [rax+rax+00000000h]
0x180003cc0  cmp     [rdi+rax*2+2], r14w
0x180003cc6  lea     rax, [rax+1]
0x180003cca  jnz     short loc_180003CC0
0x180003ccc  lea     r12d, [rax+rax]
0x180003cd0  lea     rax, [r12+2]
0x180003cd5  mov     r15d, r12d
0x180003cd8  cmp     rax, 208h
0x180003cde  ja      short loc_180003D3C
0x180003ce0  lea     rbx, [rbp+200h+pbInput]
0x180003ce4  mov     r8, r15; Size
0x180003ce7  mov     rdx, rdi; Src
0x180003cea  mov     rcx, rbx; void *
0x180003ced  call    memcpy_0
0x180003cf2  shr     r12d, 1
0x180003cf5  xor     edi, edi
0x180003cf7  mov     r14d, r12d
0x180003cfa  mov     [rbx+r12*2], di
0x180003cff  jmp     loc_180003E31
0x180003d04  movzx   ecx, word ptr [rdx]
0x180003d07  xor     ebx, ebx
0x180003d09  test    cx, cx
0x180003d0c  jz      loc_180003C14
0x180003d12  nop     dword ptr [rax+00h]
0x180003d16  nop     word ptr [rax+rax+00000000h]
0x180003d20  and     ecx, 0FFDFh
0x180003d26  imul    ebx, 65h ; 'e'
0x180003d29  lea     rdi, [rdi+2]
0x180003d2d  add     ebx, ecx
0x180003d2f  movzx   ecx, word ptr [rdi]
0x180003d32  test    cx, cx
0x180003d35  jnz     short loc_180003D20
0x180003d37  jmp     loc_180003C14
0x180003d3c  lea     rax, [r12+80h]
0x180003d44  mov     ecx, 0FFFFFFFFh
0x180003d49  cmp     rax, rcx
0x180003d4c  ja      loc_180003DF3
0x180003d52  cmp     eax, 208h
0x180003d57  jbe     short loc_180003CE0
0x180003d59  mov     ebx, eax
0x180003d5b  call    cs:__imp_GetProcessHeap
0x180003d62  nop     dword ptr [rax+rax+00h]
0x180003d67  mov     r8d, ebx; dwBytes
0x180003d6a  xor     edx, edx; dwFlags
0x180003d6c  mov     rcx, rax; hHeap
0x180003d6f  call    cs:__imp_HeapAlloc
0x180003d76  nop     dword ptr [rax+rax+00h]
0x180003d7b  mov     rbx, rax
0x180003d7e  test    rax, rax
0x180003d81  jz      short loc_180003DFF
0x180003d83  mov     rcx, rax
0x180003d86  mov     edx, 4
0x180003d8b  lea     rax, [rbp+200h+pbInput]
0x180003d8f  lea     rcx, [rcx+80h]
0x180003d96  movups  xmm0, xmmword ptr [rax]
0x180003d99  lea     rax, [rax+80h]
0x180003da0  movups  xmmword ptr [rcx-80h], xmm0
0x180003da4  movups  xmm1, xmmword ptr [rax-70h]
0x180003da8  movups  xmmword ptr [rcx-70h], xmm1
0x180003dac  movups  xmm0, xmmword ptr [rax-60h]
0x180003db0  movups  xmmword ptr [rcx-60h], xmm0
0x180003db4  movups  xmm1, xmmword ptr [rax-50h]
0x180003db8  movups  xmmword ptr [rcx-50h], xmm1
0x180003dbc  movups  xmm0, xmmword ptr [rax-40h]
0x180003dc0  movups  xmmword ptr [rcx-40h], xmm0
0x180003dc4  movups  xmm1, xmmword ptr [rax-30h]
0x180003dc8  movups  xmmword ptr [rcx-30h], xmm1
0x180003dcc  movups  xmm0, xmmword ptr [rax-20h]
0x180003dd0  movups  xmmword ptr [rcx-20h], xmm0
0x180003dd4  movups  xmm1, xmmword ptr [rax-10h]
0x180003dd8  movups  xmmword ptr [rcx-10h], xmm1
0x180003ddc  sub     rdx, 1
0x180003de0  jnz     short loc_180003D8F
0x180003de2  mov     rax, [rax]
0x180003de5  mov     r13b, 1
0x180003de8  mov     [rcx], rax
0x180003deb  mov     rsi, rbx
0x180003dee  jmp     loc_180003CE4
0x180003df3  mov     ebx, 80070216h
0x180003df8  mov     eax, ebx
0x180003dfa  jmp     loc_180003C3C
0x180003dff  mov     ecx, 8; dwErrCode
0x180003e04  call    cs:__imp_SetLastError
0x180003e0b  nop     dword ptr [rax+rax+00h]
0x180003e10  call    cs:__imp_GetLastError
0x180003e17  nop     dword ptr [rax+rax+00h]
0x180003e1c  mov     ebx, eax
0x180003e1e  test    eax, eax
0x180003e20  jle     short loc_180003E2B
0x180003e22  movzx   ebx, ax
0x180003e25  or      ebx, 80070000h
0x180003e2b  test    ebx, ebx
0x180003e2d  js      short loc_180003DF8
0x180003e2f  xor     edi, edi
0x180003e31  mov     [rsp+300h+phAlgorithm], rdi
0x180003e36  xorps   xmm0, xmm0
0x180003e39  mov     [rsp+300h+phHash], rdi
0x180003e3e  movups  xmmword ptr [rbp+200h+pbOutput], xmm0
0x180003e42  movups  [rbp+200h+var_260], xmm0
0x180003e46  test    rsi, rsi
0x180003e49  jz      loc_180003F62
0x180003e4f  lea     ebx, [r14+r14]
0x180003e53  test    ebx, ebx
0x180003e55  jz      loc_180003F62
0x180003e5b  xor     r9d, r9d; dwFlags
0x180003e5e  lea     rdx, pszAlgId; "SHA256"
0x180003e65  xor     r8d, r8d; pszImplementation
0x180003e68  lea     rcx, [rsp+300h+phAlgorithm]; phAlgorithm
0x180003e6d  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180003e74  nop     dword ptr [rax+rax+00h]
0x180003e79  mov     r14d, eax
0x180003e7c  test    eax, eax
0x180003e7e  js      short loc_180003EF2
0x180003e80  mov     rcx, [rsp+300h+phAlgorithm]; hAlgorithm
0x180003e85  lea     rdx, [rsp+300h+phHash]; phHash
0x180003e8a  mov     [rsp+30h], edi; dwFlags
0x180003e8e  xor     r9d, r9d; cbHashObject
0x180003e91  mov     [rsp+300h+cbSecret], edi; cbSecret
0x180003e95  xor     r8d, r8d; pbHashObject
0x180003e98  mov     [rsp+300h+pbSecret], rdi; pbSecret
0x180003e9d  call    cs:__imp_BCryptCreateHash
0x180003ea4  nop     dword ptr [rax+rax+00h]
0x180003ea9  mov     r14d, eax
0x180003eac  test    eax, eax
0x180003eae  js      short loc_180003EF2
0x180003eb0  mov     rcx, [rsp+300h+phHash]; hHash
0x180003eb5  xor     r9d, r9d; dwFlags
0x180003eb8  mov     r8d, ebx; cbInput
0x180003ebb  mov     rdx, rsi; pbInput
0x180003ebe  call    cs:__imp_BCryptHashData
0x180003ec5  nop     dword ptr [rax+rax+00h]
0x180003eca  mov     r14d, eax
0x180003ecd  test    eax, eax
0x180003ecf  js      short loc_180003EF2
0x180003ed1  mov     rcx, [rsp+300h+phHash]; hHash
0x180003ed6  lea     rdx, [rbp+200h+pbOutput]; pbOutput
0x180003eda  xor     r9d, r9d; dwFlags
0x180003edd  mov     r8d, 20h ; ' '; cbOutput
0x180003ee3  call    cs:__imp_BCryptFinishHash
0x180003eea  nop     dword ptr [rax+rax+00h]
0x180003eef  mov     r14d, eax
0x180003ef2  mov     rcx, [rsp+300h+phAlgorithm]; hAlgorithm
0x180003ef7  test    rcx, rcx
0x180003efa  jz      short loc_180003F0A
0x180003efc  xor     edx, edx; dwFlags
0x180003efe  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180003f05  nop     dword ptr [rax+rax+00h]
0x180003f0a  mov     rcx, [rsp+300h+phHash]; hHash
0x180003f0f  test    rcx, rcx
0x180003f12  jz      short loc_180003F20
0x180003f14  call    cs:__imp_BCryptDestroyHash
0x180003f1b  nop     dword ptr [rax+rax+00h]
0x180003f20  or      r14d, 10000000h
0x180003f27  jl      short loc_180003F68
0x180003f29  lea     rcx, [rbp+200h+pbOutput]; void *
0x180003f2d  call    ?HashBlob@@YAKPEBX_KK@Z; HashBlob(void const *,unsigned __int64,ulong)
0x180003f32  mov     ebx, eax
0x180003f34  test    r13b, r13b
0x180003f37  jz      loc_180003C14
0x180003f3d  call    cs:__imp_GetProcessHeap
0x180003f44  nop     dword ptr [rax+rax+00h]
0x180003f49  mov     r8, rsi; lpMem
0x180003f4c  xor     edx, edx; dwFlags
0x180003f4e  mov     rcx, rax; hHeap
0x180003f51  call    cs:__imp_HeapFree
0x180003f58  nop     dword ptr [rax+rax+00h]
0x180003f5d  jmp     loc_180003C14
0x180003f62  mov     r14d, 0D000000Dh
0x180003f68  test    r13b, r13b
0x180003f6b  jz      loc_180003C39
0x180003f71  call    cs:__imp_GetProcessHeap
0x180003f78  nop     dword ptr [rax+rax+00h]
0x180003f7d  mov     r8, rsi; lpMem
0x180003f80  xor     edx, edx; dwFlags
0x180003f82  mov     rcx, rax; hHeap
0x180003f85  call    cs:__imp_HeapFree
0x180003f8c  nop     dword ptr [rax+rax+00h]
0x180003f91  jmp     loc_180003C39
0x180003f96  mov     eax, 80070057h
0x180003f9b  jmp     loc_180003C6C
```
