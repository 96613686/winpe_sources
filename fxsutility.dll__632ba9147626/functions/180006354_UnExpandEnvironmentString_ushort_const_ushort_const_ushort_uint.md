# UnExpandEnvironmentString(ushort const *,ushort const *,ushort *,uint)

- ea: `0x180006354`
- end: `0x180006495`
- name: `?UnExpandEnvironmentString@@YAHPEBG0PEAGI@Z`
- size: `321`
- prototype: `__int64 __fastcall(PCNZWCH lpString2, LPCWSTR lpSrc, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000649c`

## callees

- `0x180005168`
- `0x180006354`
- `0x180015cf0`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000638b`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000638b`
- `KERNEL32!CompareStringW` at `0x1800063bb`
- `KERNEL32!CompareStringW` at `0x1800063bb`

## pseudocode

```c
_BOOL8 __fastcall UnExpandEnvironmentString(PCNZWCH lpString2, LPCWSTR lpSrc, unsigned __int16 *a3)
{
  DWORD v6; // eax
  __int64 v7; // rsi
  PCNZWCH v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  LPCWSTR v11; // rax
  WCHAR Dst[264]; // [rsp+30h] [rbp-248h] BYREF

  v6 = ExpandEnvironmentStringsW(lpSrc, Dst, 0x104u);
  v7 = v6 - 1;
  if ( (unsigned int)v7 > 0x103 || CompareStringW(0x400u, 1u, Dst, v7, lpString2, v6 - 1) != 2 || !lpString2 )
    return 0;
  v8 = lpString2;
  v9 = 0x7FFFFFFF;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v9;
  }
  while ( v9 );
  if ( !v9 || !lpSrc )
    return 0;
  v10 = 0x7FFFFFFF;
  v11 = lpSrc;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  return v10
      && ((0x7FFFFFFF - v9) & -(__int64)(v9 != 0))
       + ((0x7FFFFFFF - v10) & -(__int64)(v10 != 0))
       - (unsigned __int64)(unsigned int)v7 < 0x104
      && (int)StringCchPrintfW(a3, 0x104u, L"%s%s", lpSrc, &lpString2[v7]) >= 0;
}

```

## disassembly

```asm
0x180006354  push    rbx
0x180006356  push    rbp
0x180006357  push    rsi
0x180006358  push    rdi
0x180006359  push    r14
0x18000635b  sub     rsp, 250h
0x180006362  mov     rax, cs:__security_cookie
0x180006369  xor     rax, rsp
0x18000636c  mov     [rsp+278h+var_38], rax
0x180006374  mov     rdi, rdx
0x180006377  mov     rbp, r8
0x18000637a  mov     rbx, rcx
0x18000637d  lea     rdx, [rsp+278h+Dst]; lpDst
0x180006382  mov     rcx, rdi; lpSrc
0x180006385  mov     r8d, 104h; nSize
0x18000638b  call    cs:__imp_ExpandEnvironmentStringsW
0x180006391  lea     esi, [rax-1]
0x180006394  cmp     esi, 103h
0x18000639a  ja      loc_180006475
0x1800063a0  mov     [rsp+278h+cchCount2], esi; cchCount2
0x1800063a4  lea     r8, [rsp+278h+Dst]; lpString1
0x1800063a9  mov     r9d, esi; cchCount1
0x1800063ac  mov     [rsp+278h+lpString2], rbx; lpString2
0x1800063b1  mov     edx, 1; dwCmpFlags
0x1800063b6  mov     ecx, 400h; Locale
0x1800063bb  call    cs:__imp_CompareStringW
0x1800063c1  cmp     eax, 2
0x1800063c4  jnz     loc_180006475
0x1800063ca  xor     r14d, r14d
0x1800063cd  test    rbx, rbx
0x1800063d0  jz      loc_180006475
0x1800063d6  mov     r9d, 7FFFFFFFh
0x1800063dc  mov     rax, rbx
0x1800063df  mov     edx, r9d
0x1800063e2  cmp     [rax], r14w
0x1800063e6  jz      short loc_1800063F2
0x1800063e8  add     rax, 2
0x1800063ec  sub     rdx, 1
0x1800063f0  jnz     short loc_1800063E2
0x1800063f2  mov     rcx, r9
0x1800063f5  mov     rax, rdx
0x1800063f8  sub     rcx, rdx
0x1800063fb  neg     rax
0x1800063fe  sbb     r11, r11
0x180006401  and     r11, rcx
0x180006404  test    rdx, rdx
0x180006407  jz      short loc_180006475
0x180006409  test    rdi, rdi
0x18000640c  jz      short loc_180006475
0x18000640e  mov     rcx, r9
0x180006411  mov     rax, rdi
0x180006414  cmp     [rax], r14w
0x180006418  jz      short loc_180006424
0x18000641a  add     rax, 2
0x18000641e  sub     rcx, 1
0x180006422  jnz     short loc_180006414
0x180006424  sub     r9, rcx
0x180006427  mov     rax, rcx
0x18000642a  neg     rax
0x18000642d  sbb     r8, r8
0x180006430  and     r8, r9
0x180006433  test    rcx, rcx
0x180006436  jz      short loc_180006475
0x180006438  mov     r10d, esi
0x18000643b  sub     r8, r10
0x18000643e  add     r8, r11
0x180006441  cmp     r8, 104h
0x180006448  jnb     short loc_180006475
0x18000644a  lea     r8, [rbx+rsi*2]
0x18000644e  mov     r9, rdi
0x180006451  mov     [rsp+278h+lpString2], r8
0x180006456  mov     edx, 104h; unsigned __int64
0x18000645b  lea     r8, aSS_0; "%s%s"
0x180006462  mov     rcx, rbp; unsigned __int16 *
0x180006465  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000646a  test    eax, eax
0x18000646c  js      short loc_180006475
0x18000646e  mov     eax, 1
0x180006473  jmp     short loc_180006477
0x180006475  xor     eax, eax
0x180006477  mov     rcx, [rsp+278h+var_38]
0x18000647f  xor     rcx, rsp; StackCookie
0x180006482  call    __security_check_cookie
0x180006487  add     rsp, 250h
0x18000648e  pop     r14
0x180006490  pop     rdi
0x180006491  pop     rsi
0x180006492  pop     rbp
0x180006493  pop     rbx
0x180006494  retn
```
