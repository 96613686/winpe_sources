# RegSetSzValue(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180033354`
- end: `0x1800333bf`
- name: `?RegSetSzValue@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `107`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009348`
- `0x180009924`
- `0x18000a4e4`

## callees

- `0x18002f9bc`
- `0x180033354`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003338a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003338a`

## string_xrefs

- `0x1800333a7`: `onecoreuap\admin\prov\multivariant\common\src\commonutils.cpp`

## pseudocode

```c
LSTATUS __fastcall RegSetSzValue(HKEY a1, const unsigned __int16 *a2, const BYTE *a3)
{
  __int64 v3; // rax
  unsigned __int64 cbData; // rax
  LSTATUS result; // eax
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&a3[2 * v3] );
  cbData = 2 * v3;
  if ( cbData > 0xFFFFFFFF )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x34,
      (int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\commonutils.cpp",
      (const char *)0x80070216LL,
      lpData);
  result = RegSetValueExW(a1, a2, 0, 1u, a3, cbData);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180033354  push    rbx
0x180033356  sub     rsp, 30h
0x18003335a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003335e  xor     ebx, ebx
0x180033360  inc     rax
0x180033363  cmp     [r8+rax*2], bx
0x180033368  jnz     short loc_180033360
0x18003336a  add     rax, rax
0x18003336d  mov     r9d, 0FFFFFFFFh
0x180033373  cmp     rax, r9
0x180033376  ja      short loc_1800333A2
0x180033378  mov     [rsp+38h+cbData], eax; cbData
0x18003337c  mov     r9d, 1; dwType
0x180033382  mov     [rsp+38h+lpData], r8; lpData
0x180033387  xor     r8d, r8d; Reserved
0x18003338a  call    cs:__imp_RegSetValueExW
0x180033390  test    eax, eax
0x180033392  jle     short loc_18003339C
0x180033394  movzx   eax, ax
0x180033397  or      eax, 80070000h
0x18003339c  add     rsp, 30h
0x1800333a0  pop     rbx
0x1800333a1  retn
0x1800333a2  mov     rcx, [rsp+38h]; this
0x1800333a7  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800333ae  mov     r9d, 80070216h; char *
0x1800333b4  mov     edx, 34h ; '4'; void *
0x1800333b9  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
