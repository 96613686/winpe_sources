# AdminInstallPackage(ushort const *,ushort const *)

- ea: `0x140003e10`
- end: `0x140003e60`
- name: `?AdminInstallPackage@@YAHPEBG0@Z`
- size: `80`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400011e4`

## callees

- `0x140004ca8`
- `0x140009820`

## pseudocode

```c
__int64 __fastcall AdminInstallPackage(const unsigned __int16 *a1, WCHAR *a2)
{
  unsigned __int16 v3[16]; // [rsp+20h] [rbp-38h] BYREF

  *(_OWORD *)v3 = *(_OWORD *)L"ACTION=ADMIN";
  *(_OWORD *)&v3[5] = *(_OWORD *)L"N=ADMIN";
  return DoInstallPackage(a2, v3, INSTALLUILEVEL_FULL);
}

```

## disassembly

```asm
0x140003e10  sub     rsp, 58h
0x140003e14  mov     rax, cs:__security_cookie
0x140003e1b  xor     rax, rsp
0x140003e1e  mov     [rsp+58h+var_18], rax
0x140003e23  movups  xmm0, xmmword ptr cs:aActionAdmin; "ACTION=ADMIN"
0x140003e2a  mov     rcx, rdx; unsigned __int16 *
0x140003e2d  mov     r8d, 5; enum tagINSTALLUILEVEL
0x140003e33  movups  xmm1, xmmword ptr cs:aActionAdmin+0Ah; "N=ADMIN"
0x140003e3a  lea     rdx, [rsp+58h+var_38]; unsigned __int16 *
0x140003e3f  movups  xmmword ptr [rsp+58h+var_38], xmm0
0x140003e44  movups  xmmword ptr [rsp+58h+var_38+0Ah], xmm1
0x140003e49  call    ?DoInstallPackage@@YAHPEBG0W4tagINSTALLUILEVEL@@@Z; DoInstallPackage(ushort const *,ushort const *,tagINSTALLUILEVEL)
0x140003e4e  mov     rcx, [rsp+58h+var_18]
0x140003e53  xor     rcx, rsp; StackCookie
0x140003e56  call    __security_check_cookie
0x140003e5b  add     rsp, 58h
0x140003e5f  retn
```
