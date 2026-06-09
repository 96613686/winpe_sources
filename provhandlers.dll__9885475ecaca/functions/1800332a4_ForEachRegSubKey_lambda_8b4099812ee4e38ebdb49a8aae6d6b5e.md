# ForEachRegSubKey__lambda_8b4099812ee4e38ebdb49a8aae6d6b5e_

- ea: `0x1800332a4`
- end: `0x18003340f`
- name: `ForEachRegSubKey__lambda_8b4099812ee4e38ebdb49a8aae6d6b5e___`
- size: `363`
- prototype: `__int64 __fastcall(HKEY hKey, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180034f2c`

## callees

- `0x180012390`
- `0x180012d80`
- `0x180032f9c`
- `0x1800332a4`
- `0x180034b9c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800333b7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800333b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800332fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800332fb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180033384`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180033384`

## string_xrefs

- `0x1800333d3`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`
- `0x1800333e8`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`
- `0x1800333fd`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`

## pseudocode

```c
__int64 __fastcall ForEachRegSubKey__lambda_8b4099812ee4e38ebdb49a8aae6d6b5e_(HKEY hKey, __int64 a2)
{
  unsigned int v3; // eax
  DWORD v4; // edx
  DWORD v5; // eax
  DWORD v6; // r8d
  const char *v7; // r9
  DWORD i; // ebx
  unsigned int v9; // eax
  unsigned int lpReserved; // [rsp+20h] [rbp-60h]
  unsigned int lpReserveda; // [rsp+20h] [rbp-60h]
  DWORD cchName; // [rsp+60h] [rbp-20h] BYREF
  LPWSTR lpName[2]; // [rsp+68h] [rbp-18h] BYREF
  __int64 v15; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  __int64 v17; // [rsp+A8h] [rbp+28h] BYREF
  DWORD v18; // [rsp+B0h] [rbp+30h] BYREF
  DWORD v19; // [rsp+B8h] [rbp+38h] BYREF

  v17 = a2;
  v19 = 0;
  v18 = 0;
  v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, &v19, &v18, 0, 0, 0, 0, 0, 0);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
      (const char *)v3,
      lpReserved);
  v4 = v18;
  v5 = v18 + 1;
  v6 = -1;
  if ( v18 + 1 >= v18 )
    v6 = v18 + 1;
  v7 = v5 < v18 ? (const char *)0x80070216LL : 0LL;
  v18 = v6;
  if ( v5 < v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
      v7,
      lpReserved);
  *(_OWORD *)lpName = 0;
  v15 = 0;
  if ( v6 )
    std::vector<unsigned short>::_Reallocate((__int64)lpName, v6);
  for ( i = 0; i < v19; ++i )
  {
    cchName = v18;
    v9 = RegEnumKeyExW(hKey, i, lpName[0], &cchName, 0, 0, 0, 0);
    if ( v9 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
        (const char *)v9,
        lpReserveda);
    if ( !(unsigned __int8)lambda_8b4099812ee4e38ebdb49a8aae6d6b5e_::operator()(&v17, hKey, lpName[0]) )
      break;
  }
  if ( lpName[0] )
    operator delete(lpName[0]);
  return i;
}

```

## disassembly

```asm
0x1800332a4  mov     r11, rsp
0x1800332a7  mov     [r11+8], rbx
0x1800332ab  mov     [r11+10h], rdx
0x1800332af  push    rbp
0x1800332b0  push    rsi
0x1800332b1  push    r14
0x1800332b3  mov     rbp, rsp
0x1800332b6  sub     rsp, 80h
0x1800332bd  mov     rsi, rcx
0x1800332c0  xor     r14d, r14d
0x1800332c3  mov     [rbp+arg_18], r14d
0x1800332c7  mov     [rbp+arg_10], r14d
0x1800332cb  mov     [r11-40h], r14
0x1800332cf  mov     [r11-48h], r14
0x1800332d3  mov     [r11-50h], r14
0x1800332d7  mov     [r11-58h], r14
0x1800332db  mov     [r11-60h], r14
0x1800332df  mov     [r11-68h], r14
0x1800332e3  lea     rax, [rbp+arg_10]
0x1800332e7  mov     [r11-70h], rax
0x1800332eb  lea     rax, [rbp+arg_18]
0x1800332ef  mov     [r11-78h], rax
0x1800332f3  xor     r9d, r9d; lpReserved
0x1800332f6  xor     r8d, r8d; lpcchClass
0x1800332f9  xor     edx, edx; lpClass
0x1800332fb  call    cs:__imp_RegQueryInfoKeyW
0x180033301  mov     rcx, [rbp+18h]; this
0x180033305  test    eax, eax
0x180033307  jnz     loc_1800333FA
0x18003330d  mov     edx, [rbp+arg_10]
0x180033310  lea     eax, [rdx+1]
0x180033313  or      r8d, 0FFFFFFFFh
0x180033317  cmp     eax, edx
0x180033319  cmovnb  r8d, eax
0x18003331d  sbb     r9d, r9d
0x180033320  and     r9d, 80070216h; char *
0x180033327  mov     [rbp+arg_10], r8d
0x18003332b  mov     rcx, [rbp+18h]; this
0x18003332f  cmp     eax, edx
0x180033331  jb      loc_1800333D3
0x180033337  xorps   xmm0, xmm0
0x18003333a  movdqu  xmmword ptr [rbp+lpName], xmm0
0x18003333f  mov     [rbp+var_8], r14
0x180033343  mov     edx, r8d
0x180033346  test    r8d, r8d
0x180033349  jz      short loc_180033354
0x18003334b  lea     rcx, [rbp+lpName]
0x18003334f  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x180033354  mov     ebx, r14d
0x180033357  cmp     [rbp+arg_18], r14d
0x18003335b  jbe     short loc_1800333AD
0x18003335d  mov     eax, [rbp+arg_10]
0x180033360  mov     [rbp+cchName], eax
0x180033363  mov     [rsp+80h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180033368  mov     [rsp+80h+lpcchClass], r14; lpcchClass
0x18003336d  mov     [rsp+80h+lpClass], r14; lpClass
0x180033372  mov     [rsp+80h+lpReserved], r14; unsigned int
0x180033377  lea     r9, [rbp+cchName]; lpcchName
0x18003337b  mov     r8, [rbp+lpName]; lpName
0x18003337f  mov     edx, ebx; dwIndex
0x180033381  mov     rcx, rsi; hKey
0x180033384  call    cs:__imp_RegEnumKeyExW
0x18003338a  mov     rcx, [rbp+18h]; this
0x18003338e  test    eax, eax
0x180033390  jnz     short loc_1800333E5
0x180033392  mov     r8, [rbp+lpName]
0x180033396  mov     rdx, rsi
0x180033399  lea     rcx, [rbp+arg_8]
0x18003339d  call    _lambda_8b4099812ee4e38ebdb49a8aae6d6b5e___operator__
0x1800333a2  test    al, al
0x1800333a4  jz      short loc_1800333AD
0x1800333a6  inc     ebx
0x1800333a8  cmp     ebx, [rbp+arg_18]
0x1800333ab  jb      short loc_18003335D
0x1800333ad  cmp     [rbp+lpName], r14
0x1800333b1  jz      short loc_1800333BD
0x1800333b3  mov     rcx, [rbp+lpName]
0x1800333b7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800333bd  mov     eax, ebx
0x1800333bf  mov     rbx, [rsp+80h+arg_0]
0x1800333c7  add     rsp, 80h
0x1800333ce  pop     r14
0x1800333d0  pop     rsi
0x1800333d1  pop     rbp
0x1800333d2  retn
0x1800333d3  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x1800333da  mov     edx, 43h ; 'C'; void *
0x1800333df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800333e5  mov     r9d, eax; char *
0x1800333e8  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x1800333ef  mov     edx, 4Ch ; 'L'; void *
0x1800333f4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800333fa  mov     r9d, eax; char *
0x1800333fd  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x180033404  mov     edx, 40h ; '@'; void *
0x180033409  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
