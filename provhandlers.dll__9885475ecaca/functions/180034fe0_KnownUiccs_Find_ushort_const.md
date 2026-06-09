# KnownUiccs::Find(ushort const *)

- ea: `0x180034fe0`
- end: `0x18003506c`
- name: `?Find@KnownUiccs@@SA?AUKnownUicc@@PEBG@Z`
- size: `140`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180028400`
- `0x180029e90`

## callees

- `0x180012390`
- `0x180034fe0`
- `0x180035074`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035043`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035043`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035019`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035019`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KnownUiccs::Find(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int v6; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  hKey = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, gc_wszRegUicc, 0, 9u, &hKey);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x15E,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
      (const char *)v4,
      v6);
  KnownUicc::FromRegKey(a1, hKey, a2);
  if ( hKey )
    RegCloseKey(hKey);
  return a1;
}

```

## disassembly

```asm
0x180034fe0  mov     r11, rsp
0x180034fe3  mov     [r11+8], rbx
0x180034fe7  push    rdi
0x180034fe8  sub     rsp, 40h
0x180034fec  mov     rdi, rdx
0x180034fef  mov     rbx, rcx
0x180034ff2  mov     qword ptr [r11+18h], 0
0x180034ffa  lea     rax, [r11+18h]
0x180034ffe  mov     [r11-28h], rax
0x180035002  mov     r9d, 9; samDesired
0x180035008  xor     r8d, r8d; ulOptions
0x18003500b  mov     rdx, cs:?gc_wszRegUicc@@3PEBGEB; lpSubKey
0x180035012  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035019  call    cs:__imp_RegOpenKeyExW
0x18003501f  mov     rcx, [rsp+48h]; this
0x180035024  test    eax, eax
0x180035026  jnz     short loc_180035057
0x180035028  mov     r8, rdi
0x18003502b  mov     rdx, [rsp+48h+hKey]
0x180035030  mov     rcx, rbx
0x180035033  call    ?FromRegKey@KnownUicc@@SA?AU1@PEAUHKEY__@@PEBG@Z; KnownUicc::FromRegKey(HKEY__ *,ushort const *)
0x180035038  nop
0x180035039  mov     rcx, [rsp+48h+hKey]; hKey
0x18003503e  test    rcx, rcx
0x180035041  jz      short loc_180035049
0x180035043  call    cs:__imp_RegCloseKey
0x180035049  mov     rax, rbx
0x18003504c  mov     rbx, [rsp+48h+arg_0]
0x180035051  add     rsp, 40h
0x180035055  pop     rdi
0x180035056  retn
0x180035057  mov     r9d, eax; char *
0x18003505a  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180035061  mov     edx, 15Eh; void *
0x180035066  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
