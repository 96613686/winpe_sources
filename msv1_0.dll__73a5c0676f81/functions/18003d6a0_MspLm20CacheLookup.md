# MspLm20CacheLookup

- ea: `0x18003d6a0`
- end: `0x18003da7e`
- name: `MspLm20CacheLookup`
- size: `990`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, __int64, _DWORD *, int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180011090`
- `0x180012d10`

## callees

- `0x18000dab4`
- `0x18000db30`
- `0x18000dc18`
- `0x18002e9fc`
- `0x18002f014`
- `0x18002fb50`
- `0x180030844`
- `0x18003d6a0`
- `0x1800448cc`
- `0x180044db0`
- `0x18006bd74`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d826`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d899`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003da19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003da27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d826`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d899`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003da19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003da27`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d869`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d869`
- `NtlmShared!MsvpComputeSaltedHashedPassword` at `0x18003d95b`
- `NtlmShared!MsvpComputeSaltedHashedPassword` at `0x18003d95b`
- `CRYPTSP!SystemFunction007` at `0x18003d90f`
- `CRYPTSP!SystemFunction007` at `0x18003d90f`

## pseudocode

```c
__int64 __fastcall MspLm20CacheLookup(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        _DWORD *a6,
        int *a7)
{
  int *v8; // r12
  __int64 result; // rax
  char *v12; // rsi
  HLOCAL v13; // r14
  __int64 v14; // r13
  int ClientBuffer; // ebx
  bool v16; // cf
  __int128 v17; // xmm1
  int CacheEntry; // eax
  unsigned int v19; // r12d
  _DWORD *v20; // rsi
  int v21; // eax
  __int64 i; // rcx
  __int64 v23; // r15
  HLOCAL v24; // rax
  int v25; // eax
  bool v26; // cc
  __int16 v27; // ax
  __int128 *v28; // r15
  __int128 *v29; // rcx
  char v30; // r8
  __int64 j; // rdx
  char v32; // cl
  char v33; // al
  _DWORD *v34; // rcx
  _QWORD *v35; // rdx
  __int128 *v36; // rax
  __int64 v37; // rcx
  __int64 *v38; // rax
  size_t Size; // [rsp+50h] [rbp-B0h] BYREF
  int *v40; // [rsp+58h] [rbp-A8h]
  __int64 v41; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  __int64 v43[2]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD *v44; // [rsp+80h] [rbp-80h]
  __int64 v45; // [rsp+88h] [rbp-78h]
  __int128 v46; // [rsp+90h] [rbp-70h] BYREF
  _DWORD *v47; // [rsp+A0h] [rbp-60h]
  __int64 v48; // [rsp+A8h] [rbp-58h]
  struct _UNICODE_STRING v49; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v50; // [rsp+D0h] [rbp-30h]
  __int128 v51; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v52[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v53[19]; // [rsp+110h] [rbp+10h] BYREF

  v8 = a7;
  v45 = a5;
  v44 = a6;
  v40 = a7;
  memset_0(&v49, 0, 0x40u);
  result = 0;
  v43[0] = 0;
  hMem = 0;
  v12 = 0;
  LODWORD(Size) = 0;
  v13 = 0;
  LODWORD(v41) = 0;
  memset(v53, 0, sizeof(v53));
  *(_OWORD *)v52 = 0;
  v51 = 0;
  if ( a1 )
  {
    *a7 = -1073741790;
    return result;
  }
  v47 = 0;
  v14 = 16;
  v48 = 0;
  *a7 = 0;
  v46 = 0;
  if ( a4 < 0x38
    || (v16 = *(_DWORD *)(a2 + 40) < 3u,
        v17 = *(_OWORD *)(a2 + 8),
        v49 = *(struct _UNICODE_STRING *)(a2 + 24),
        v50 = v17,
        !v16) )
  {
    ClientBuffer = -1073741811;
LABEL_48:
    NlpFreeClientBuffer(&v46);
    if ( v12 )
      LocalFree(v12);
    if ( v13 )
      LocalFree(v13);
    if ( *v8 >= 0 )
      *v8 = ClientBuffer;
    goto LABEL_54;
  }
  CacheEntry = NlpGetCacheEntry(
                 &v49,
                 0x10000000u,
                 (__int64)v43,
                 (__int64)v52,
                 (__int64)&v41,
                 (__int64)&hMem,
                 (__int64)&Size);
  *a7 = CacheEntry;
  if ( CacheEntry < 0 )
    goto LABEL_54;
  v13 = hMem;
  v19 = Size;
  if ( hMem && (_DWORD)Size )
  {
    v20 = hMem;
    v21 = NlpValidateSupplementalData((unsigned int)Size, hMem);
    ClientBuffer = v21;
    if ( v21 == -1073741275 )
    {
      if ( *(_DWORD *)a2 != 17 )
        goto LABEL_24;
      ClientBuffer = NlpMakeExSuppData(v19, v13);
      LocalFree(v13);
      v13 = hMem;
      v19 = Size;
      goto LABEL_22;
    }
    if ( v21 < 0 )
    {
LABEL_23:
      v12 = (char *)v43[0];
LABEL_47:
      v8 = v40;
      goto LABEL_48;
    }
    if ( *(_DWORD *)a2 == 11 )
    {
      ClientBuffer = 0;
      v19 = 0;
      v13 = 0;
      for ( i = 0; (unsigned int)i < v20[2]; i = (unsigned int)(i + 1) )
      {
        v23 = 3 * i;
        if ( !v20[3 * i + 3] )
        {
          v24 = LocalAlloc(0x40u, (unsigned int)v20[3 * i + 5]);
          v13 = v24;
          if ( v24 )
          {
            v19 = v20[v23 + 5];
            memcpy_0(v24, (char *)v20 + (unsigned int)v20[v23 + 4], v19);
          }
          else
          {
            ClientBuffer = -1073741801;
          }
          break;
        }
      }
      LocalFree(v20);
LABEL_22:
      if ( ClientBuffer < 0 )
        goto LABEL_23;
    }
  }
LABEL_24:
  v25 = *(_DWORD *)(a2 + 40);
  if ( !v25 && *(_DWORD *)(a2 + 44) )
  {
    ClientBuffer = -1073741811;
    goto LABEL_23;
  }
  v12 = (char *)v43[0];
  if ( v53[16] )
  {
    if ( v25 == 1 )
    {
      v26 = *(_DWORD *)(a2 + 44) <= 0xFFFFu;
      *(_OWORD *)v43 = 0;
      if ( !v26 )
      {
LABEL_30:
        ClientBuffer = -1073741811;
        goto LABEL_47;
      }
      v27 = *(_WORD *)(a2 + 44);
      v28 = (__int128 *)(a2 + 48);
      v43[1] = a2 + 48;
      LOWORD(v43[0]) = v27;
      WORD1(v43[0]) = v27;
      ClientBuffer = SystemFunction007(v43, &v51);
      if ( ClientBuffer < 0 )
        goto LABEL_47;
      v29 = &v51;
      *(_DWORD *)(a2 + 40) = 2;
      *(_DWORD *)(a2 + 44) = 16;
      goto LABEL_34;
    }
    v29 = 0;
    v28 = (__int128 *)(a2 + 48);
    if ( v25 == 2 )
    {
LABEL_34:
      if ( *(_DWORD *)(a2 + 44) != 16 )
        goto LABEL_30;
      if ( v29 )
        v28 = v29;
      ClientBuffer = MsvpComputeSaltedHashedPassword(v28, v28, v12 + 48, (unsigned int)v41);
      if ( ClientBuffer < 0 )
        goto LABEL_47;
      v30 = 0;
      for ( j = 0; j != 16; ++j )
      {
        v32 = *((_BYTE *)v28 + j);
        v33 = *((_BYTE *)v52 + j);
        v30 |= v33 ^ v32;
      }
      if ( v30 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids);
        ClientBuffer = -1073741715;
        goto LABEL_47;
      }
    }
  }
  *v44 = 32;
  ClientBuffer = NlpAllocateClientBuffer((__int64)&v46, 32, 0x20u);
  if ( ClientBuffer < 0 )
    goto LABEL_47;
  v34 = v47;
  v35 = (_QWORD *)v45;
  *v47 = *(_DWORD *)a2;
  *((_QWORD *)v34 + 1) = v12;
  *((_QWORD *)v34 + 2) = v13;
  v34[6] = v19;
  ClientBuffer = NlpFlushClientBuffer((__int64)&v46, v35);
  if ( ClientBuffer < 0 )
    goto LABEL_47;
LABEL_54:
  v36 = &v51;
  do
  {
    *(_BYTE *)v36 = 0;
    v36 = (__int128 *)((char *)v36 + 1);
    --v14;
  }
  while ( v14 );
  v37 = 35;
  v38 = v52;
  do
  {
    *(_BYTE *)v38 = 0;
    v38 = (__int64 *)((char *)v38 + 1);
    --v37;
  }
  while ( v37 );
  return 0;
}

```

## disassembly

```asm
0x18003d6a0  push    rbp
0x18003d6a2  push    rbx
0x18003d6a3  push    rsi
0x18003d6a4  push    rdi
0x18003d6a5  push    r12
0x18003d6a7  push    r13
0x18003d6a9  push    r14
0x18003d6ab  push    r15
0x18003d6ad  lea     rbp, [rsp-38h]
0x18003d6b2  sub     rsp, 138h
0x18003d6b9  mov     rax, cs:__security_cookie
0x18003d6c0  xor     rax, rsp
0x18003d6c3  mov     [rbp+70h+var_48], rax
0x18003d6c7  mov     rax, [rbp+70h+arg_20]
0x18003d6ce  mov     rdi, rdx
0x18003d6d1  mov     r12, [rbp+70h+arg_30]
0x18003d6d8  xor     edx, edx; Val
0x18003d6da  mov     [rbp+70h+var_E8], rax
0x18003d6de  mov     rbx, rcx
0x18003d6e1  mov     rax, [rbp+70h+arg_28]
0x18003d6e8  lea     rcx, [rbp+70h+var_C0]; void *
0x18003d6ec  mov     r15d, r9d
0x18003d6ef  mov     [rbp+70h+var_F0], rax
0x18003d6f3  lea     r8d, [rdx+40h]; Size
0x18003d6f7  mov     [rsp+170h+var_118], r12
0x18003d6fc  call    memset_0
0x18003d701  xor     ecx, ecx
0x18003d703  xorps   xmm0, xmm0
0x18003d706  xor     eax, eax
0x18003d708  mov     [rsp+170h+var_100], rcx
0x18003d70d  mov     [rsp+170h+hMem], rcx
0x18003d712  mov     esi, ecx
0x18003d714  mov     dword ptr [rsp+170h+Size], ecx
0x18003d718  mov     r14d, ecx
0x18003d71b  mov     dword ptr [rsp+170h+var_110], ecx
0x18003d71f  movups  [rbp+70h+var_60], xmm0
0x18003d723  mov     dword ptr [rbp+70h+var_60+0Fh], eax
0x18003d726  movups  xmmword ptr [rbp+70h+var_70], xmm0
0x18003d72a  movups  [rbp+70h+var_80], xmm0
0x18003d72e  test    rbx, rbx
0x18003d731  jz      short loc_18003D740
0x18003d733  mov     dword ptr [r12], 0C0000022h
0x18003d73b  jmp     loc_18003DA5E
0x18003d740  mov     [rbp+70h+var_D0], rcx
0x18003d744  mov     r13d, 10h
0x18003d74a  mov     [rbp+70h+var_C8], rcx
0x18003d74e  mov     [r12], ecx
0x18003d752  movdqu  [rbp+70h+var_E0], xmm0
0x18003d757  cmp     r15d, 38h ; '8'
0x18003d75b  jnb     short loc_18003D767
0x18003d75d  mov     ebx, 0C000000Dh
0x18003d762  jmp     loc_18003DA08
0x18003d767  cmp     dword ptr [rdi+28h], 3
0x18003d76b  movups  xmm0, xmmword ptr [rdi+18h]
0x18003d76f  movups  xmm1, xmmword ptr [rdi+8]
0x18003d773  movdqu  xmmword ptr [rbp+70h+var_C0.Length], xmm0
0x18003d778  movdqu  [rbp+70h+var_A0], xmm1
0x18003d77d  jnb     short loc_18003D75D
0x18003d77f  lea     rax, [rsp+170h+Size]
0x18003d784  xor     r9d, r9d
0x18003d787  mov     [rsp+170h+var_130], rax; __int64
0x18003d78c  lea     rcx, [rbp+70h+var_C0]; struct _UNICODE_STRING *
0x18003d790  lea     rax, [rsp+170h+hMem]
0x18003d795  xor     r8d, r8d
0x18003d798  mov     [rsp+170h+var_138], rax; __int64
0x18003d79d  mov     edx, 10000000h; unsigned int
0x18003d7a2  lea     rax, [rsp+170h+var_110]
0x18003d7a7  mov     [rsp+170h+var_140], rax; __int64
0x18003d7ac  lea     rax, [rbp+70h+var_70]
0x18003d7b0  mov     [rsp+170h+var_148], rax; __int64
0x18003d7b5  lea     rax, [rsp+170h+var_100]
0x18003d7ba  mov     [rsp+170h+var_150], rax; __int64
0x18003d7bf  call    NlpGetCacheEntry
0x18003d7c4  mov     [r12], eax
0x18003d7c8  test    eax, eax
0x18003d7ca  js      loc_18003DA38
0x18003d7d0  mov     r14, [rsp+170h+hMem]
0x18003d7d5  mov     r12d, dword ptr [rsp+170h+Size]
0x18003d7da  test    r14, r14
0x18003d7dd  jz      loc_18003D8AD
0x18003d7e3  test    r12d, r12d
0x18003d7e6  jz      loc_18003D8AD
0x18003d7ec  mov     rdx, r14
0x18003d7ef  mov     ecx, r12d
0x18003d7f2  mov     rsi, r14
0x18003d7f5  call    NlpValidateSupplementalData
0x18003d7fa  mov     ebx, eax
0x18003d7fc  cmp     eax, 0C0000225h
0x18003d801  jnz     short loc_18003D838
0x18003d803  cmp     dword ptr [rdi], 11h
0x18003d806  jnz     loc_18003D8AD
0x18003d80c  lea     r9, [rsp+170h+hMem]
0x18003d811  mov     rdx, r14; Src
0x18003d814  lea     r8, [rsp+170h+Size]
0x18003d819  mov     ecx, r12d; Size
0x18003d81c  call    NlpMakeExSuppData
0x18003d821  mov     rcx, r14; hMem
0x18003d824  mov     ebx, eax
0x18003d826  call    cs:__imp_LocalFree
0x18003d82c  mov     r14, [rsp+170h+hMem]
0x18003d831  mov     r12d, dword ptr [rsp+170h+Size]
0x18003d836  jmp     short loc_18003D89F
0x18003d838  test    eax, eax
0x18003d83a  js      short loc_18003D8A3
0x18003d83c  cmp     dword ptr [rdi], 0Bh
0x18003d83f  jnz     short loc_18003D8AD
0x18003d841  xor     ebx, ebx
0x18003d843  xor     r12d, r12d
0x18003d846  xor     r14d, r14d
0x18003d849  xor     ecx, ecx
0x18003d84b  cmp     ecx, [rsi+8]
0x18003d84e  jnb     short loc_18003D896
0x18003d850  lea     r15, [rcx+rcx*2]
0x18003d854  cmp     [rsi+r15*4+0Ch], ebx
0x18003d859  jz      short loc_18003D85F
0x18003d85b  inc     ecx
0x18003d85d  jmp     short loc_18003D84B
0x18003d85f  mov     edx, [rsi+r15*4+14h]; uBytes
0x18003d864  mov     ecx, 40h ; '@'; uFlags
0x18003d869  call    cs:__imp_LocalAlloc
0x18003d86f  mov     r14, rax
0x18003d872  test    rax, rax
0x18003d875  jz      short loc_18003D891
0x18003d877  mov     r12d, [rsi+r15*4+14h]
0x18003d87c  mov     rcx, rax; void *
0x18003d87f  mov     edx, [rsi+r15*4+10h]
0x18003d884  mov     r8d, r12d; Size
0x18003d887  add     rdx, rsi; Src
0x18003d88a  call    memcpy_0
0x18003d88f  jmp     short loc_18003D896
0x18003d891  mov     ebx, 0C0000017h
0x18003d896  mov     rcx, rsi; hMem
0x18003d899  call    cs:__imp_LocalFree
0x18003d89f  test    ebx, ebx
0x18003d8a1  jns     short loc_18003D8AD
0x18003d8a3  mov     rsi, [rsp+170h+var_100]
0x18003d8a8  jmp     loc_18003DA03
0x18003d8ad  mov     eax, [rdi+28h]
0x18003d8b0  test    eax, eax
0x18003d8b2  jnz     short loc_18003D8C0
0x18003d8b4  cmp     [rdi+2Ch], eax
0x18003d8b7  jz      short loc_18003D8C0
0x18003d8b9  mov     ebx, 0C000000Dh
0x18003d8be  jmp     short loc_18003D8A3
0x18003d8c0  cmp     [rbp+70h+var_50], 0
0x18003d8c4  mov     rsi, [rsp+170h+var_100]
0x18003d8c9  jz      loc_18003D9BF
0x18003d8cf  cmp     eax, 1
0x18003d8d2  jnz     short loc_18003D930
0x18003d8d4  cmp     dword ptr [rdi+2Ch], 0FFFFh
0x18003d8db  xorps   xmm0, xmm0
0x18003d8de  movups  xmmword ptr [rsp+170h+var_100], xmm0
0x18003d8e3  jbe     short loc_18003D8EF
0x18003d8e5  mov     ebx, 0C000000Dh
0x18003d8ea  jmp     loc_18003DA03
0x18003d8ef  movzx   eax, word ptr [rdi+2Ch]
0x18003d8f3  lea     r15, [rdi+30h]
0x18003d8f7  lea     rdx, [rbp+70h+var_80]
0x18003d8fb  mov     [rsp+170h+var_100+8], r15
0x18003d900  lea     rcx, [rsp+170h+var_100]
0x18003d905  mov     word ptr [rsp+170h+var_100], ax
0x18003d90a  mov     word ptr [rsp+170h+var_100+2], ax
0x18003d90f  call    cs:__imp_SystemFunction007
0x18003d915  mov     ebx, eax
0x18003d917  test    eax, eax
0x18003d919  js      loc_18003DA03
0x18003d91f  lea     rcx, [rbp+70h+var_80]
0x18003d923  mov     dword ptr [rdi+28h], 2
0x18003d92a  mov     [rdi+2Ch], r13d
0x18003d92e  jmp     short loc_18003D93F
0x18003d930  xor     ecx, ecx
0x18003d932  lea     r15, [rdi+30h]
0x18003d936  cmp     eax, 2
0x18003d939  jnz     loc_18003D9BF
0x18003d93f  cmp     [rdi+2Ch], r13d
0x18003d943  jnz     short loc_18003D8E5
0x18003d945  mov     r9d, dword ptr [rsp+170h+var_110]
0x18003d94a  lea     r8, [rsi+30h]
0x18003d94e  test    rcx, rcx
0x18003d951  cmovnz  r15, rcx
0x18003d955  mov     rdx, r15
0x18003d958  mov     rcx, r15
0x18003d95b  call    cs:__imp_MsvpComputeSaltedHashedPassword
0x18003d961  mov     ebx, eax
0x18003d963  test    eax, eax
0x18003d965  js      loc_18003DA03
0x18003d96b  xor     r8b, r8b
0x18003d96e  xor     edx, edx
0x18003d970  mov     cl, [r15+rdx]
0x18003d974  mov     al, byte ptr [rbp+rdx+70h+var_70]
0x18003d978  inc     rdx
0x18003d97b  xor     cl, al
0x18003d97d  or      r8b, cl
0x18003d980  cmp     rdx, r13
0x18003d983  jnz     short loc_18003D970
0x18003d985  test    r8b, r8b
0x18003d988  jz      short loc_18003D9BF
0x18003d98a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d991  lea     rax, WPP_GLOBAL_Control
0x18003d998  cmp     rcx, rax
0x18003d99b  jz      short loc_18003D9B8
0x18003d99d  test    byte ptr [rcx+1Ch], 1
0x18003d9a1  jz      short loc_18003D9B8
0x18003d9a3  mov     rcx, [rcx+10h]
0x18003d9a7  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x18003d9ae  mov     edx, 38h ; '8'
0x18003d9b3  call    WPP_SF_
0x18003d9b8  mov     ebx, 0C000006Dh
0x18003d9bd  jmp     short loc_18003DA03
0x18003d9bf  mov     rax, [rbp+70h+var_F0]
0x18003d9c3  lea     rcx, [rbp+70h+var_E0]
0x18003d9c7  mov     edx, 20h ; ' '
0x18003d9cc  mov     r8d, edx
0x18003d9cf  mov     [rax], edx
0x18003d9d1  call    NlpAllocateClientBuffer
0x18003d9d6  mov     ebx, eax
0x18003d9d8  test    eax, eax
0x18003d9da  js      short loc_18003DA03
0x18003d9dc  mov     rcx, [rbp+70h+var_D0]
0x18003d9e0  mov     eax, [rdi]
0x18003d9e2  mov     rdx, [rbp+70h+var_E8]
0x18003d9e6  mov     [rcx], eax
0x18003d9e8  mov     [rcx+8], rsi
0x18003d9ec  mov     [rcx+10h], r14
0x18003d9f0  mov     [rcx+18h], r12d
0x18003d9f4  lea     rcx, [rbp+70h+var_E0]
0x18003d9f8  call    NlpFlushClientBuffer
0x18003d9fd  mov     ebx, eax
0x18003d9ff  test    eax, eax
0x18003da01  jns     short loc_18003DA38
0x18003da03  mov     r12, [rsp+170h+var_118]
0x18003da08  lea     rcx, [rbp+70h+var_E0]
0x18003da0c  call    NlpFreeClientBuffer
0x18003da11  test    rsi, rsi
0x18003da14  jz      short loc_18003DA1F
0x18003da16  mov     rcx, rsi; hMem
0x18003da19  call    cs:__imp_LocalFree
0x18003da1f  test    r14, r14
0x18003da22  jz      short loc_18003DA2D
0x18003da24  mov     rcx, r14; hMem
0x18003da27  call    cs:__imp_LocalFree
0x18003da2d  cmp     dword ptr [r12], 0
0x18003da32  jl      short loc_18003DA38
0x18003da34  mov     [r12], ebx
0x18003da38  lea     rax, [rbp+70h+var_80]
0x18003da3c  mov     byte ptr [rax], 0
0x18003da3f  inc     rax
0x18003da42  sub     r13, 1
0x18003da46  jnz     short loc_18003DA3C
0x18003da48  lea     ecx, [r13+23h]
0x18003da4c  lea     rax, [rbp+70h+var_70]
0x18003da50  mov     byte ptr [rax], 0
0x18003da53  inc     rax
0x18003da56  sub     rcx, 1
0x18003da5a  jnz     short loc_18003DA50
0x18003da5c  xor     eax, eax
0x18003da5e  mov     rcx, [rbp+70h+var_48]
0x18003da62  xor     rcx, rsp; StackCookie
0x18003da65  call    __security_check_cookie
0x18003da6a  add     rsp, 138h
0x18003da71  pop     r15
0x18003da73  pop     r14
0x18003da75  pop     r13
0x18003da77  pop     r12
0x18003da79  pop     rdi
0x18003da7a  pop     rsi
0x18003da7b  pop     rbx
0x18003da7c  pop     rbp
0x18003da7d  retn
```
