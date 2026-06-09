# ValidateItemAndGetBookmark

- ea: `0x180022328`
- end: `0x18002258c`
- name: `ValidateItemAndGetBookmark`
- size: `612`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180021110`
- `0x1800213c0`
- `0x180021c40`

## callees

- `0x180022328`
- `0x180044836`
- `0x18004484e`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!malloc` at `0x18002253a`
- `msvcrt!malloc` at `0x18002253a`

## string_xrefs

- `0x1800223ad`: `MSFT_DSCConfigurationOutput`
- `0x1800223ce`: `MSFT_DSCConfigurationOutputResult`

## pseudocode

```c
__int64 __fastcall ValidateItemAndGetBookmark(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _BYTE *a5)
{
  _QWORD *v8; // rdi
  __int64 v9; // r14
  __int64 v10; // rcx
  __int64 result; // rax
  _QWORD *v12; // rcx
  _QWORD *v13; // rcx
  const void *v14; // rdi
  size_t v15; // rsi
  void *v16; // rax
  void *v17; // rbx
  int v18; // [rsp+40h] [rbp-61h] BYREF
  int v19; // [rsp+44h] [rbp-5Dh] BYREF
  int v20; // [rsp+48h] [rbp-59h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-51h] BYREF
  wchar_t *v22; // [rsp+58h] [rbp-49h] BYREF
  wchar_t *v23[2]; // [rsp+60h] [rbp-41h] BYREF
  __int128 v24; // [rsp+70h] [rbp-31h]
  __int64 v25; // [rsp+80h] [rbp-21h]
  size_t Size[2]; // [rsp+88h] [rbp-19h] BYREF
  __int128 v27; // [rsp+98h] [rbp-9h]
  __int64 v28; // [rsp+A8h] [rbp+7h]

  v28 = 0;
  v20 = 0;
  v22 = 0;
  *(_OWORD *)Size = 0;
  v27 = 0;
  if ( a5 )
    *a5 = 0;
  if ( !a2 )
    return 4;
  if ( *(_DWORD *)(a2 + 40) != 15 )
    return 4;
  v8 = *(_QWORD **)a2;
  if ( !*(_QWORD *)a2 )
    return 4;
  v9 = v8[1];
  v10 = *(_QWORD *)(v9 + 56);
  if ( !v10 || wcscmp_0(*(const wchar_t **)(v10 + 8), L"MSFT_DSCConfigurationOutput") )
    return 4;
  if ( a5 && !wcscmp_0(*(const wchar_t **)(v9 + 8), L"MSFT_DSCConfigurationOutputResult") )
  {
    String1 = 0;
    v25 = 0;
    *(_OWORD *)v23 = 0;
    v18 = 0;
    v24 = 0;
    v19 = 0;
    if ( !*v8 )
      return 4;
    result = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, wchar_t **, wchar_t **, int *, int *))(*v8 + 96LL))(
               v8,
               0,
               &String1,
               v23,
               &v18,
               &v19);
    if ( (_DWORD)result )
      return result;
    if ( wcscmp_0(String1, L"JobId") || v18 != 13 || (v19 & 0x20000000) != 0 )
      return 4;
    if ( !wcscmp_0(v23[0], L"{ffffffff-ffff-ffff-ffff-ffffffffffff}") )
    {
      v12 = *(_QWORD **)a2;
      v23[0] = *(wchar_t **)(a1 + 64);
      if ( v12 && *v12 )
      {
        result = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, wchar_t **, __int64, _DWORD))(*v12 + 80LL))(
                   v12,
                   0,
                   v23,
                   13,
                   0);
        if ( (_DWORD)result )
          return result;
        *a5 = 1;
        goto LABEL_20;
      }
      return 4;
    }
  }
LABEL_20:
  v13 = *(_QWORD **)a2;
  if ( !*(_QWORD *)a2 || !*v13 )
    return 4;
  result = (*(__int64 (__fastcall **)(_QWORD *, __int64, wchar_t **, size_t *, int *, _QWORD))(*v13 + 96LL))(
             v13,
             1,
             &v22,
             Size,
             &v20,
             0);
  if ( (_DWORD)result )
    return result;
  if ( wcscmp_0(v22, L"Bookmark") )
    return 4;
  if ( v20 != 17 )
    return 4;
  if ( !LODWORD(Size[1]) )
    return 4;
  v14 = (const void *)Size[0];
  if ( !Size[0] )
    return 4;
  v15 = LODWORD(Size[1]);
  v16 = malloc(LODWORD(Size[1]));
  v17 = v16;
  if ( !v16 )
    return 27;
  memcpy_0(v16, v14, v15);
  *(_DWORD *)(a3 + 8) = Size[1];
  result = 0;
  *(_QWORD *)a3 = v17;
  return result;
}

```

## disassembly

```asm
0x180022328  push    rbp
0x18002232a  push    rbx
0x18002232b  push    rsi
0x18002232c  push    rdi
0x18002232d  push    r13
0x18002232f  push    r14
0x180022331  push    r15
0x180022333  lea     rbp, [rsp-1Fh]
0x180022338  sub     rsp, 0C0h
0x18002233f  mov     rax, cs:__security_cookie
0x180022346  xor     rax, rsp
0x180022349  mov     [rbp+4Fh+var_40], rax
0x18002234d  mov     rsi, [rbp+4Fh+arg_20]
0x180022351  xor     eax, eax
0x180022353  mov     [rbp+4Fh+var_48], rax
0x180022357  xorps   xmm0, xmm0
0x18002235a  mov     [rbp+4Fh+var_A8], eax
0x18002235d  mov     r15, r8
0x180022360  mov     [rbp+4Fh+var_98], rax
0x180022364  mov     rbx, rdx
0x180022367  mov     r13, rcx
0x18002236a  movups  xmmword ptr [rbp+4Fh+Size], xmm0
0x18002236e  movups  [rbp+4Fh+var_58], xmm0
0x180022372  test    rsi, rsi
0x180022375  jz      short loc_180022379
0x180022377  mov     [rsi], al
0x180022379  test    rbx, rbx
0x18002237c  jz      loc_180022569
0x180022382  cmp     dword ptr [rdx+28h], 0Fh
0x180022386  jnz     loc_180022569
0x18002238c  mov     rdi, [rdx]
0x18002238f  test    rdi, rdi
0x180022392  jz      loc_180022569
0x180022398  mov     r14, [rdi+8]
0x18002239c  mov     rcx, [r14+38h]
0x1800223a0  test    rcx, rcx
0x1800223a3  jz      loc_180022569
0x1800223a9  mov     rcx, [rcx+8]; String1
0x1800223ad  lea     rdx, aMsftDscconfigu_2; "MSFT_DSCConfigurationOutput"
0x1800223b4  call    wcscmp_0
0x1800223b9  test    eax, eax
0x1800223bb  jnz     loc_180022569
0x1800223c1  test    rsi, rsi
0x1800223c4  jz      loc_1800224C8
0x1800223ca  mov     rcx, [r14+8]; String1
0x1800223ce  lea     rdx, aMsftDscconfigu_3; "MSFT_DSCConfigurationOutputResult"
0x1800223d5  call    wcscmp_0
0x1800223da  test    eax, eax
0x1800223dc  jnz     loc_1800224C8
0x1800223e2  xor     eax, eax
0x1800223e4  mov     [rbp+4Fh+String1], 0
0x1800223ec  xorps   xmm0, xmm0
0x1800223ef  mov     [rbp+4Fh+var_70], rax
0x1800223f3  movups  xmmword ptr [rbp+4Fh+var_90], xmm0
0x1800223f7  mov     [rbp+4Fh+var_B0], eax
0x1800223fa  movups  [rbp+4Fh+var_80], xmm0
0x1800223fe  mov     [rbp+4Fh+var_AC], eax
0x180022401  mov     rax, [rdi]
0x180022404  test    rax, rax
0x180022407  jz      loc_180022569
0x18002240d  mov     rax, [rax+60h]
0x180022411  lea     rcx, [rbp+4Fh+var_AC]
0x180022415  mov     [rsp+0F0h+var_C8], rcx
0x18002241a  lea     r9, [rbp+4Fh+var_90]
0x18002241e  lea     rcx, [rbp+4Fh+var_B0]
0x180022422  xor     edx, edx
0x180022424  mov     [rsp+0F0h+var_D0], rcx
0x180022429  lea     r8, [rbp+4Fh+String1]
0x18002242d  mov     rcx, rdi
0x180022430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022435  test    eax, eax
0x180022437  jnz     loc_18002256E
0x18002243d  mov     rcx, [rbp+4Fh+String1]; String1
0x180022441  lea     rdx, aJobid_0; "JobId"
0x180022448  call    wcscmp_0
0x18002244d  test    eax, eax
0x18002244f  jnz     loc_180022569
0x180022455  cmp     [rbp+4Fh+var_B0], 0Dh
0x180022459  jnz     loc_180022569
0x18002245f  test    [rbp+4Fh+var_AC], 20000000h
0x180022466  jnz     loc_180022569
0x18002246c  mov     rcx, [rbp+4Fh+var_90]; String1
0x180022470  lea     rdx, aFfffffffFfffFf; "{ffffffff-ffff-ffff-ffff-ffffffffffff}"
0x180022477  call    wcscmp_0
0x18002247c  test    eax, eax
0x18002247e  jnz     short loc_1800224C8
0x180022480  mov     rcx, [rbx]
0x180022483  mov     rax, [r13+40h]
0x180022487  mov     [rbp+4Fh+var_90], rax
0x18002248b  test    rcx, rcx
0x18002248e  jz      loc_180022569
0x180022494  mov     rax, [rcx]
0x180022497  test    rax, rax
0x18002249a  jz      loc_180022569
0x1800224a0  mov     rax, [rax+50h]
0x1800224a4  lea     r8, [rbp+4Fh+var_90]
0x1800224a8  mov     r9d, 0Dh
0x1800224ae  mov     dword ptr [rsp+0F0h+var_D0], 0
0x1800224b6  xor     edx, edx
0x1800224b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224bd  test    eax, eax
0x1800224bf  jnz     loc_18002256E
0x1800224c5  mov     byte ptr [rsi], 1
0x1800224c8  mov     rcx, [rbx]
0x1800224cb  test    rcx, rcx
0x1800224ce  jz      loc_180022569
0x1800224d4  mov     rax, [rcx]
0x1800224d7  test    rax, rax
0x1800224da  jz      loc_180022569
0x1800224e0  mov     rax, [rax+60h]
0x1800224e4  lea     r8, [rbp+4Fh+var_A8]
0x1800224e8  mov     [rsp+0F0h+var_C8], 0
0x1800224f1  lea     r9, [rbp+4Fh+Size]
0x1800224f5  mov     [rsp+0F0h+var_D0], r8
0x1800224fa  mov     edx, 1
0x1800224ff  lea     r8, [rbp+4Fh+var_98]
0x180022503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022508  test    eax, eax
0x18002250a  jnz     short loc_18002256E
0x18002250c  mov     rcx, [rbp+4Fh+var_98]; String1
0x180022510  lea     rdx, aBookmark; "Bookmark"
0x180022517  call    wcscmp_0
0x18002251c  test    eax, eax
0x18002251e  jnz     short loc_180022569
0x180022520  cmp     [rbp+4Fh+var_A8], 11h
0x180022524  jnz     short loc_180022569
0x180022526  mov     eax, dword ptr [rbp+4Fh+Size+8]
0x180022529  test    eax, eax
0x18002252b  jz      short loc_180022569
0x18002252d  mov     rdi, [rbp+4Fh+Size]
0x180022531  test    rdi, rdi
0x180022534  jz      short loc_180022569
0x180022536  mov     ecx, eax; Size
0x180022538  mov     esi, eax
0x18002253a  call    cs:__imp_malloc
0x180022540  mov     rbx, rax
0x180022543  test    rax, rax
0x180022546  jnz     short loc_18002254D
0x180022548  lea     eax, [rbx+1Bh]
0x18002254b  jmp     short loc_18002256E
0x18002254d  mov     r8, rsi; Size
0x180022550  mov     rdx, rdi; Src
0x180022553  mov     rcx, rbx; void *
0x180022556  call    memcpy_0
0x18002255b  mov     eax, dword ptr [rbp+4Fh+Size+8]
0x18002255e  mov     [r15+8], eax
0x180022562  xor     eax, eax
0x180022564  mov     [r15], rbx
0x180022567  jmp     short loc_18002256E
0x180022569  mov     eax, 4
0x18002256e  mov     rcx, [rbp+4Fh+var_40]
0x180022572  xor     rcx, rsp; StackCookie
0x180022575  call    __security_check_cookie
0x18002257a  add     rsp, 0C0h
0x180022581  pop     r15
0x180022583  pop     r14
0x180022585  pop     r13
0x180022587  pop     rdi
0x180022588  pop     rsi
0x180022589  pop     rbx
0x18002258a  pop     rbp
0x18002258b  retn
```
