# COpenHandle::GetAcl(IMDCOM *,ushort const *,uchar * *,ulong *)

- ea: `0x18000b3bc`
- end: `0x18000b61d`
- name: `?GetAcl@COpenHandle@@QEAAHPEAUIMDCOM@@PEBGPEAPEAEPEAK@Z`
- size: `609`
- prototype: `int(COpenHandle *__hidden this, struct IMDCOM *, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b988`

## callees

- `0x18000b3bc`
- `0x18000fb06`
- `0x180010010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000b4f8`
- `msvcrt!_wcsnicmp` at `0x18000b4f8`
- `msvcrt!wcschr` at `0x18000b4c8`
- `msvcrt!wcschr` at `0x18000b4e0`
- `msvcrt!wcschr` at `0x18000b4c8`
- `msvcrt!wcschr` at `0x18000b4e0`
- `KERNEL32!LocalAlloc` at `0x18000b467`
- `KERNEL32!LocalAlloc` at `0x18000b467`
- `KERNEL32!LocalFree` at `0x18000b5e5`
- `KERNEL32!LocalFree` at `0x18000b5e5`

## pseudocode

```c
__int64 __fastcall COpenHandle::GetAcl(
        const void **this,
        struct IMDCOM *a2,
        const unsigned __int16 *a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  const unsigned __int16 *v5; // r14
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rcx
  SIZE_T v11; // r15
  wchar_t *v12; // rax
  wchar_t *v13; // rsi
  unsigned int v14; // ebx
  size_t v15; // rbx
  wchar_t *v16; // rbx
  wchar_t *i; // rax
  __int64 v18; // rax
  __int64 (__fastcall *v19)(struct IMDCOM *, _QWORD, wchar_t *, _OWORD *, int *); // rax
  int v20; // eax
  int v21; // edx
  wchar_t v22; // cx
  wchar_t *v23; // r9
  wchar_t *v24; // r8
  wchar_t *v25; // rax
  __int64 v26; // rax
  __int64 (__fastcall *v27)(struct IMDCOM *, _QWORD, wchar_t *, _OWORD *, int *); // rax
  unsigned int *v28; // rdx
  _OWORD v30[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v31; // [rsp+50h] [rbp-10h]
  int v32; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int8 **v33; // [rsp+B8h] [rbp+58h]

  v33 = a4;
  v5 = &byte_1800127D8;
  v31 = 0;
  v32 = 0;
  if ( a3 )
    v5 = a3;
  memset(v30, 0, sizeof(v30));
  if ( *v5 == 47 || *v5 == 92 )
    ++v5;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( *((_WORD *)*this + v9) );
  do
    ++v8;
  while ( v5[v8] );
  if ( (_DWORD)v8 )
  {
    v10 = (unsigned int)(v8 - 1);
    if ( v5[v10] == 47 || v5[v10] == 92 )
      LODWORD(v8) = v8 - 1;
  }
  v11 = 2 * ((unsigned int)v9 + (_DWORD)v8 + ((_DWORD)v8 != 0)) + 2;
  v12 = (wchar_t *)LocalAlloc(0, v11);
  v13 = v12;
  if ( v12 )
  {
    v15 = (unsigned int)v9;
    memcpy_0(v12, *this, v15 * 2);
    v16 = &v13[v15];
    if ( (_DWORD)v8 )
    {
      *v16 = 47;
      memcpy_0(v16 + 1, v5, 2LL * (unsigned int)v8);
    }
    v13[(v11 - 2) >> 1] = 0;
    for ( i = wcschr(v16, 0x5Cu); i; i = wcschr(i, 0x5Cu) )
      *i = 47;
    if ( !_wcsnicmp(v13, L"/Schema/", 8u) )
      v13[7] = 0;
    v18 = *(_QWORD *)a2;
    v14 = 1;
    *(_QWORD *)&v30[0] = 0xB0000178BLL;
    v19 = *(__int64 (__fastcall **)(struct IMDCOM *, _QWORD, wchar_t *, _OWORD *, int *))(v18 + 168);
    DWORD2(v30[0]) = 1;
    *(_QWORD *)((char *)v30 + 12) = 3;
    *((_QWORD *)&v30[1] + 1) = 0;
    LODWORD(v31) = 0;
    v20 = v19(a2, 0, v13, v30, &v32);
    v21 = v20;
    if ( (v20 & 0x1FFF0000) == 0x70000 )
      v20 = (unsigned __int16)v20;
    if ( v20 == 122 )
    {
      do
      {
        v22 = *v13;
        if ( !*v13 )
          break;
        v23 = v13;
        v24 = 0;
        do
        {
          v25 = v23;
          if ( v22 != 47 )
            v25 = v24;
          ++v23;
          v24 = v25;
          v22 = *v23;
        }
        while ( *v23 );
        if ( !v25 )
          break;
        *v25 = 0;
        v26 = *(_QWORD *)a2;
        LODWORD(v30[1]) = 0;
        *((_QWORD *)&v30[1] + 1) = 0;
        v27 = *(__int64 (__fastcall **)(struct IMDCOM *, _QWORD, wchar_t *, _OWORD *, int *))(v26 + 168);
        LODWORD(v31) = 0;
        v21 = v27(a2, 0, v13, v30, &v32);
      }
      while ( v21 < 0 );
    }
    if ( v21 < 0 || !(_DWORD)v31 )
      v14 = 0;
    LocalFree(v13);
    if ( v14 )
    {
      v28 = a5;
      *v33 = (unsigned __int8 *)*((_QWORD *)&v30[1] + 1);
      *v28 = v31;
    }
  }
  else
  {
    return 0;
  }
  return v14;
}

```

## disassembly

```asm
0x18000b3bc  mov     [rsp-38h+arg_8], rbx
0x18000b3c1  mov     [rsp-38h+arg_18], r9
0x18000b3c6  push    rbp
0x18000b3c7  push    rsi
0x18000b3c8  push    rdi
0x18000b3c9  push    r12
0x18000b3cb  push    r13
0x18000b3cd  push    r14
0x18000b3cf  push    r15
0x18000b3d1  mov     rbp, rsp
0x18000b3d4  sub     rsp, 60h
0x18000b3d8  xor     eax, eax
0x18000b3da  lea     r14, byte_1800127D8
0x18000b3e1  xorps   xmm0, xmm0
0x18000b3e4  mov     [rbp+var_10], rax
0x18000b3e8  mov     r13, rdx
0x18000b3eb  mov     r12, rcx
0x18000b3ee  xor     edx, edx
0x18000b3f0  test    r8, r8
0x18000b3f3  mov     [rbp+arg_0], edx
0x18000b3f6  lea     r9d, [rax+2Fh]
0x18000b3fa  cmovnz  r14, r8
0x18000b3fe  lea     r8d, [rax+5Ch]
0x18000b402  movups  [rbp+var_30], xmm0
0x18000b406  movups  [rbp+var_20], xmm0
0x18000b40a  cmp     [r14], r9w
0x18000b40e  jz      short loc_18000B416
0x18000b410  cmp     [r14], r8w
0x18000b414  jnz     short loc_18000B41A
0x18000b416  add     r14, 2
0x18000b41a  mov     rax, [rcx]
0x18000b41d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000b421  mov     rbx, rdi
0x18000b424  inc     rbx
0x18000b427  cmp     [rax+rbx*2], dx
0x18000b42b  jnz     short loc_18000B424
0x18000b42d  inc     rdi
0x18000b430  cmp     [r14+rdi*2], dx
0x18000b435  jnz     short loc_18000B42D
0x18000b437  test    edi, edi
0x18000b439  jz      short loc_18000B44E
0x18000b43b  lea     ecx, [rdi-1]
0x18000b43e  cmp     [r14+rcx*2], r9w
0x18000b443  jz      short loc_18000B44C
0x18000b445  cmp     [r14+rcx*2], r8w
0x18000b44a  jnz     short loc_18000B44E
0x18000b44c  mov     edi, ecx
0x18000b44e  mov     eax, edx
0x18000b450  test    edi, edi
0x18000b452  setnz   al
0x18000b455  xor     ecx, ecx; uFlags
0x18000b457  add     eax, edi
0x18000b459  add     eax, ebx
0x18000b45b  lea     eax, ds:2[rax*2]
0x18000b462  mov     edx, eax; uBytes
0x18000b464  mov     r15d, eax
0x18000b467  call    cs:__imp_LocalAlloc
0x18000b46d  mov     rsi, rax
0x18000b470  test    rax, rax
0x18000b473  jnz     short loc_18000B47C
0x18000b475  xor     ebx, ebx
0x18000b477  jmp     loc_18000B603
0x18000b47c  mov     rdx, [r12]; Src
0x18000b480  mov     rcx, rsi; void *
0x18000b483  mov     eax, ebx
0x18000b485  lea     rbx, [rax+rax]
0x18000b489  mov     r8, rbx; Size
0x18000b48c  call    memcpy_0
0x18000b491  add     rbx, rsi
0x18000b494  xor     r12d, r12d
0x18000b497  test    edi, edi
0x18000b499  jz      short loc_18000B4B2
0x18000b49b  mov     r8d, edi
0x18000b49e  lea     rcx, [rbx+2]; void *
0x18000b4a2  add     r8, r8; Size
0x18000b4a5  mov     word ptr [rbx], 2Fh ; '/'
0x18000b4aa  mov     rdx, r14; Src
0x18000b4ad  call    memcpy_0
0x18000b4b2  lea     rdx, [r15-2]
0x18000b4b6  mov     edi, 5Ch ; '\'
0x18000b4bb  shr     rdx, 1
0x18000b4be  mov     rcx, rbx; Str
0x18000b4c1  mov     [rsi+rdx*2], r12w
0x18000b4c6  mov     edx, edi; Ch
0x18000b4c8  call    cs:__imp_wcschr
0x18000b4ce  lea     r14d, [rdi-2Dh]
0x18000b4d2  test    rax, rax
0x18000b4d5  jz      short loc_18000B4E8
0x18000b4d7  mov     edx, edi; Ch
0x18000b4d9  mov     [rax], r14w
0x18000b4dd  mov     rcx, rax; Str
0x18000b4e0  call    cs:__imp_wcschr
0x18000b4e6  jmp     short loc_18000B4D2
0x18000b4e8  mov     r8d, 8; MaxCount
0x18000b4ee  lea     rdx, aSchema; "/Schema/"
0x18000b4f5  mov     rcx, rsi; String1
0x18000b4f8  call    cs:__imp__wcsnicmp
0x18000b4fe  test    eax, eax
0x18000b500  jnz     short loc_18000B507
0x18000b502  mov     [rsi+0Eh], r12w
0x18000b507  mov     rax, [r13+0]
0x18000b50b  lea     rcx, [rbp+arg_0]
0x18000b50f  mov     [rsp+60h+var_40], rcx
0x18000b514  lea     r9, [rbp+var_30]
0x18000b518  mov     ebx, 1
0x18000b51d  mov     dword ptr [rbp+var_30], 178Bh
0x18000b524  mov     r8, rsi
0x18000b527  mov     dword ptr [rbp+var_30+4], 0Bh
0x18000b52e  mov     rax, [rax+0A8h]
0x18000b535  xor     edx, edx
0x18000b537  mov     rcx, r13
0x18000b53a  mov     dword ptr [rbp+var_30+8], ebx
0x18000b53d  mov     qword ptr [rbp+var_30+0Ch], 3
0x18000b545  mov     qword ptr [rbp+var_20+8], r12
0x18000b549  mov     dword ptr [rbp+var_10], r12d
0x18000b54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b552  mov     ecx, eax
0x18000b554  mov     edx, eax
0x18000b556  and     ecx, 1FFF0000h
0x18000b55c  cmp     ecx, 70000h
0x18000b562  jnz     short loc_18000B567
0x18000b564  movzx   eax, ax
0x18000b567  cmp     eax, 7Ah ; 'z'
0x18000b56a  jnz     short loc_18000B5D5
0x18000b56c  movzx   ecx, word ptr [rsi]
0x18000b56f  test    cx, cx
0x18000b572  jz      short loc_18000B5D5
0x18000b574  mov     r9, rsi
0x18000b577  mov     r8, r12
0x18000b57a  cmp     cx, r14w
0x18000b57e  mov     rax, r9
0x18000b581  cmovnz  rax, r8
0x18000b585  add     r9, 2
0x18000b589  mov     r8, rax
0x18000b58c  movzx   ecx, word ptr [r9]
0x18000b590  test    cx, cx
0x18000b593  jnz     short loc_18000B57A
0x18000b595  test    rax, rax
0x18000b598  jz      short loc_18000B5D5
0x18000b59a  mov     [rax], r12w
0x18000b59e  lea     rcx, [rbp+arg_0]
0x18000b5a2  mov     rax, [r13+0]
0x18000b5a6  lea     r9, [rbp+var_30]
0x18000b5aa  mov     [rsp+60h+var_40], rcx
0x18000b5af  mov     r8, rsi
0x18000b5b2  xor     edx, edx
0x18000b5b4  mov     dword ptr [rbp+var_20], r12d
0x18000b5b8  mov     rcx, r13
0x18000b5bb  mov     qword ptr [rbp+var_20+8], r12
0x18000b5bf  mov     rax, [rax+0A8h]
0x18000b5c6  mov     dword ptr [rbp+var_10], r12d
0x18000b5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5cf  mov     edx, eax
0x18000b5d1  test    eax, eax
0x18000b5d3  js      short loc_18000B56C
0x18000b5d5  test    edx, edx
0x18000b5d7  js      short loc_18000B5DF
0x18000b5d9  cmp     dword ptr [rbp+var_10], r12d
0x18000b5dd  jnz     short loc_18000B5E2
0x18000b5df  mov     ebx, r12d
0x18000b5e2  mov     rcx, rsi; hMem
0x18000b5e5  call    cs:__imp_LocalFree
0x18000b5eb  test    ebx, ebx
0x18000b5ed  jz      short loc_18000B603
0x18000b5ef  mov     rcx, qword ptr [rbp+var_20+8]
0x18000b5f3  mov     rax, [rbp+arg_18]
0x18000b5f7  mov     rdx, [rbp+arg_20]
0x18000b5fb  mov     [rax], rcx
0x18000b5fe  mov     ecx, dword ptr [rbp+var_10]
0x18000b601  mov     [rdx], ecx
0x18000b603  mov     eax, ebx
0x18000b605  mov     rbx, [rsp+60h+arg_8]
0x18000b60d  add     rsp, 60h
0x18000b611  pop     r15
0x18000b613  pop     r14
0x18000b615  pop     r13
0x18000b617  pop     r12
0x18000b619  pop     rdi
0x18000b61a  pop     rsi
0x18000b61b  pop     rbp
0x18000b61c  retn
```
