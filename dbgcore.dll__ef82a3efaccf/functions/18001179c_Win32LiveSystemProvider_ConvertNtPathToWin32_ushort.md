# Win32LiveSystemProvider::ConvertNtPathToWin32(ushort *)

- ea: `0x18001179c`
- end: `0x18001198b`
- name: `?ConvertNtPathToWin32@Win32LiveSystemProvider@@AEAAJPEAG@Z`
- size: `495`
- prototype: `int(Win32LiveSystemProvider *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x180011ae4`

## callees

- `0x18000217c`
- `0x180003430`
- `0x18001179c`

## pseudocode

```c
__int64 __fastcall Win32LiveSystemProvider::ConvertNtPathToWin32(Win32LiveSystemProvider *this, unsigned __int16 *a2)
{
  __int64 v3; // rbx
  char *v4; // rsi
  Win32LiveSystemProvider *v5; // rdi
  Win32LiveSystemProvider *v6; // r12
  const wchar_t *v7; // rcx
  __int64 v8; // rbp
  __int64 v9; // r15
  __int64 v11; // r8
  int v12; // r10d
  __int64 v13; // r11
  unsigned int v14; // edx
  __int64 v15; // rax
  unsigned __int16 *v16; // rcx
  __int64 v17; // r9
  unsigned __int16 *v18; // r10
  unsigned __int16 *v19; // rcx
  unsigned __int16 *v20; // r9
  unsigned __int16 *v21; // rdi
  unsigned __int16 *v22; // rcx
  __int64 v23; // [rsp+20h] [rbp-48h] BYREF
  wchar_t v24; // [rsp+28h] [rbp-40h]

  v24 = asc_180030A68[4];
  v3 = -1;
  v23 = *(_QWORD *)L"\\\\?\\";
  do
    ++v3;
  while ( a2[v3] );
  v4 = (char *)this + 800;
  v5 = (Win32LiveSystemProvider *)*((_QWORD *)this + 100);
  if ( v5 == (Win32LiveSystemProvider *)((char *)this + 800) )
    return 2147500037LL;
  while ( 1 )
  {
    v6 = *(Win32LiveSystemProvider **)v5;
    v7 = (const wchar_t *)((char *)v5 + 16);
    v8 = -1;
    do
      ++v8;
    while ( v7[v8] );
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)v5 + v9 + 268) );
    if ( !wcsnicmp(v7, a2, (unsigned int)v8) )
      break;
    v5 = v6;
    if ( v6 == (Win32LiveSystemProvider *)v4 )
      return 2147500037LL;
  }
  v11 = (unsigned int)v3;
  v12 = 0;
  v13 = 2147483646;
  if ( (unsigned int)(v3 + v9 - v8) >= 0x104 )
  {
    if ( !(_DWORD)v3 )
      return (unsigned int)-2147024809;
    if ( (unsigned int)v3 > 0x7FFFFFFFuLL )
    {
      v14 = -2147024809;
      *a2 = 0;
      return v14;
    }
    v15 = 2147483646;
    v16 = (unsigned __int16 *)&v23;
    v17 = (unsigned int)v3;
    v18 = a2;
    do
    {
      if ( !v15 )
        break;
      if ( !*v16 )
        break;
      *v18++ = *v16++;
      --v15;
      --v17;
    }
    while ( v17 );
    v19 = v18 - 1;
    v14 = v17 == 0 ? 0x8007007A : 0;
    if ( v17 )
      v19 = v18;
    *v19 = 0;
    if ( !v17 )
      return v14;
    v12 = 4;
  }
  v20 = &a2[v12];
  if ( !(_DWORD)v3 )
    return (unsigned int)-2147024809;
  if ( (unsigned int)v3 > 0x7FFFFFFFuLL )
  {
    v14 = -2147024809;
    *v20 = 0;
    return v14;
  }
  v21 = (unsigned __int16 *)((char *)v5 + 536);
  do
  {
    if ( !v13 )
      break;
    if ( !*v21 )
      break;
    *v20++ = *v21++;
    --v13;
    --v11;
  }
  while ( v11 );
  v22 = v20 - 1;
  v14 = v11 == 0 ? 0x8007007A : 0;
  if ( v11 )
    v22 = v20;
  *v22 = 0;
  if ( !v11 )
    return v14;
  memmove_0(&a2[(unsigned int)(v9 + v12)], &a2[(unsigned int)v8 + 1], 2LL * (unsigned int)(v3 - v8));
  return 0;
}

```

## disassembly

```asm
0x18001179c  mov     [rsp+arg_10], rbx
0x1800117a1  push    rbp
0x1800117a2  push    rsi
0x1800117a3  push    rdi
0x1800117a4  push    r12
0x1800117a6  push    r13
0x1800117a8  push    r14
0x1800117aa  push    r15
0x1800117ac  sub     rsp, 30h
0x1800117b0  movzx   eax, word ptr cs:asc_180030A68+8; ""
0x1800117b7  mov     r14, rdx
0x1800117ba  movsd   xmm0, qword ptr cs:asc_180030A68; "\\\\?\\"
0x1800117c2  mov     [rsp+68h+var_40], ax
0x1800117c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800117cb  mov     rbx, rax
0x1800117ce  movsd   [rsp+68h+var_48], xmm0
0x1800117d4  xor     r13d, r13d
0x1800117d7  inc     rbx
0x1800117da  cmp     [rdx+rbx*2], r13w
0x1800117df  jnz     short loc_1800117D7
0x1800117e1  lea     rsi, [rcx+320h]
0x1800117e8  mov     rdi, [rsi]
0x1800117eb  cmp     rdi, rsi
0x1800117ee  jz      short loc_180011833
0x1800117f0  mov     r12, [rdi]
0x1800117f3  lea     rcx, [rdi+10h]; String1
0x1800117f7  mov     rbp, rax
0x1800117fa  inc     rbp
0x1800117fd  cmp     [rcx+rbp*2], r13w
0x180011802  jnz     short loc_1800117FA
0x180011804  mov     r15, rax
0x180011807  inc     r15
0x18001180a  cmp     [rdi+r15*2+218h], r13w
0x180011813  jnz     short loc_180011807
0x180011815  mov     r8d, ebp; MaxCount
0x180011818  mov     rdx, r14; String2
0x18001181b  call    _wcsnicmp
0x180011820  test    eax, eax
0x180011822  jz      short loc_180011850
0x180011824  mov     rdi, r12
0x180011827  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001182e  cmp     r12, rsi
0x180011831  jnz     short loc_1800117F0
0x180011833  mov     eax, 80004005h
0x180011838  mov     rbx, [rsp+68h+arg_10]
0x180011840  add     rsp, 30h
0x180011844  pop     r15
0x180011846  pop     r14
0x180011848  pop     r13
0x18001184a  pop     r12
0x18001184c  pop     rdi
0x18001184d  pop     rsi
0x18001184e  pop     rbp
0x18001184f  retn
0x180011850  mov     eax, r15d
0x180011853  mov     r8d, ebx
0x180011856  sub     eax, ebp
0x180011858  mov     esi, 7FFFFFFFh
0x18001185d  add     eax, ebx
0x18001185f  mov     r10d, r13d
0x180011862  mov     r12d, 8007007Ah
0x180011868  lea     r11d, [rsi-1]
0x18001186c  cmp     eax, 104h
0x180011871  jb      short loc_1800118D7
0x180011873  test    ebx, ebx
0x180011875  jz      short loc_1800118F5
0x180011877  cmp     r8, rsi
0x18001187a  jbe     short loc_180011883
0x18001187c  lea     edx, [r12-23h]
0x180011881  jmp     short loc_1800118FE
0x180011883  mov     rax, r11
0x180011886  lea     rcx, [rsp+68h+var_48]
0x18001188b  mov     r9, r8
0x18001188e  mov     r10, r14
0x180011891  test    rax, rax
0x180011894  jz      short loc_1800118B3
0x180011896  movzx   edx, word ptr [rcx]
0x180011899  test    dx, dx
0x18001189c  jz      short loc_1800118B3
0x18001189e  mov     [r10], dx
0x1800118a2  add     rcx, 2
0x1800118a6  add     r10, 2
0x1800118aa  dec     rax
0x1800118ad  sub     r9, 1
0x1800118b1  jnz     short loc_180011891
0x1800118b3  mov     rax, r9
0x1800118b6  lea     rcx, [r10-2]
0x1800118ba  neg     rax
0x1800118bd  sbb     edx, edx
0x1800118bf  not     edx
0x1800118c1  and     edx, r12d
0x1800118c4  test    r9, r9
0x1800118c7  cmovnz  rcx, r10
0x1800118cb  mov     [rcx], r13w
0x1800118cf  jz      short loc_180011902
0x1800118d1  mov     r10d, 4
0x1800118d7  mov     eax, r10d
0x1800118da  lea     r9, [r14+rax*2]
0x1800118de  test    ebx, ebx
0x1800118e0  jz      loc_180011979
0x1800118e6  cmp     r8, rsi
0x1800118e9  jbe     short loc_180011909
0x1800118eb  mov     edx, 80070057h
0x1800118f0  jmp     loc_180011982
0x1800118f5  mov     edx, 80070057h
0x1800118fa  test    ebx, ebx
0x1800118fc  jz      short loc_180011902
0x1800118fe  mov     [r14], r13w
0x180011902  mov     eax, edx
0x180011904  jmp     loc_180011838
0x180011909  add     rdi, 218h
0x180011910  test    ebx, ebx
0x180011912  jz      short loc_180011936
0x180011914  test    r11, r11
0x180011917  jz      short loc_180011936
0x180011919  movzx   eax, word ptr [rdi]
0x18001191c  test    ax, ax
0x18001191f  jz      short loc_180011936
0x180011921  mov     [r9], ax
0x180011925  add     rdi, 2
0x180011929  add     r9, 2
0x18001192d  dec     r11
0x180011930  sub     r8, 1
0x180011934  jnz     short loc_180011914
0x180011936  mov     rax, r8
0x180011939  lea     rcx, [r9-2]
0x18001193d  neg     rax
0x180011940  sbb     edx, edx
0x180011942  not     edx
0x180011944  and     edx, r12d
0x180011947  test    r8, r8
0x18001194a  cmovnz  rcx, r9
0x18001194e  mov     [rcx], r13w
0x180011952  jz      short loc_180011902
0x180011954  lea     eax, [r15+r10]
0x180011958  mov     edx, ebp
0x18001195a  inc     rdx
0x18001195d  lea     rcx, [r14+rax*2]; void *
0x180011961  sub     ebx, ebp
0x180011963  mov     r8d, ebx
0x180011966  add     r8, r8; Size
0x180011969  lea     rdx, [r14+rdx*2]; Src
0x18001196d  call    memmove_0
0x180011972  xor     eax, eax
0x180011974  jmp     loc_180011838
0x180011979  mov     edx, 80070057h
0x18001197e  test    ebx, ebx
0x180011980  jz      short loc_180011902
0x180011982  mov     [r9], r13w
0x180011986  jmp     loc_180011902
```
