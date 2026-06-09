# ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)

- ea: `0x180009bf4`
- end: `0x180009c22`
- name: `??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z`
- size: `46`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000bf94`
- `0x18000d3ec`
- `0x18000db90`
- `0x18000e5d4`
- `0x18000fc34`
- `0x180016700`
- `0x180016a80`
- `0x180017720`
- `0x1800189b0`
- `0x18001b0d0`

## callees

- `0x180009bf4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c05`

## pseudocode

```c
HKEY *__fastcall ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(
        HKEY *a1)
{
  HKEY v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    RegCloseKey(v2);
    *a1 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180009bf4  push    rbx
0x180009bf6  sub     rsp, 20h
0x180009bfa  mov     rbx, rcx
0x180009bfd  mov     rcx, [rcx]; hKey
0x180009c00  test    rcx, rcx
0x180009c03  jz      short loc_180009C18
0x180009c05  call    cs:__imp_RegCloseKey
0x180009c0c  nop     dword ptr [rax+rax+00h]
0x180009c11  mov     qword ptr [rbx], 0
0x180009c18  mov     rax, rbx
0x180009c1b  add     rsp, 20h
0x180009c1f  pop     rbx
0x180009c20  retn
```
