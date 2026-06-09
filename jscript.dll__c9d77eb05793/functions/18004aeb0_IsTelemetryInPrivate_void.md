# IsTelemetryInPrivate(void)

- ea: `0x18004aeb0`
- end: `0x18004af54`
- name: `?IsTelemetryInPrivate@@YA_NXZ`
- size: `164`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004adb0`

## callees

- `0x18004aeb0`
- `0x18005902c`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18004af25`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18004af25`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x18004af1b`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x18004af1b`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x18004aef5`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x18004aef5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18004aed7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18004aeeb`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18004aed7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18004aeeb`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18004aeca`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18004aeca`

## string_xrefs

- `0x18004af04`: `onecoreuap\inetcore\lib\tracelogging\legacydll.cpp`

## pseudocode

```c
char IsTelemetryInPrivate(void)
{
  int DWORD; // edi
  const char *v1; // r9
  char v2; // bl
  bool v3; // al
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( dword_1800B64D8 != 2 )
    return dword_1800B64D8 == 1;
  DWORD = IEConfiguration_GetDWORD(268435501);
  if ( (unsigned __int8)IEConfiguration_GetBool(536870914) || DWORD != 2 )
  {
    v2 = 1;
    if ( LCIEIsCurrentProcessInPrivateOverrideSet() )
    {
      v3 = LCIEIsCurrentProcessInPrivate();
      v2 = v3;
      if ( DWORD != 3 )
        dword_1800B64D8 = v3;
    }
  }
  else
  {
    if ( !(unsigned __int8)IEConfiguration_GetBool(268435512) )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecoreuap\\inetcore\\lib\\tracelogging\\legacydll.cpp",
        v1);
    return LCIEIsCurrentProcessUsingInPrivateComponents();
  }
  return v2;
}

```

## disassembly

```asm
0x18004aeb0  mov     [rsp+arg_0], rbx
0x18004aeb5  push    rdi
0x18004aeb6  sub     rsp, 20h
0x18004aeba  mov     eax, cs:dword_1800B64D8
0x18004aec0  cmp     eax, 2
0x18004aec3  jnz     short loc_18004AF3D
0x18004aec5  mov     ecx, 1000002Dh
0x18004aeca  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18004aed0  mov     ecx, 20000002h
0x18004aed5  mov     edi, eax
0x18004aed7  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18004aedd  test    al, al
0x18004aedf  jnz     short loc_18004AF16
0x18004aee1  cmp     edi, 2
0x18004aee4  jnz     short loc_18004AF16
0x18004aee6  mov     ecx, 10000038h
0x18004aeeb  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18004aef1  test    al, al
0x18004aef3  jz      short loc_18004AEFF
0x18004aef5  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x18004aefb  mov     bl, al
0x18004aefd  jmp     short loc_18004AF47
0x18004aeff  mov     rcx, [rsp+28h]; this
0x18004af04  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\lib\\tracelogging"...
0x18004af0b  mov     edx, 10h; void *
0x18004af10  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18004af16  mov     ebx, 1
0x18004af1b  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x18004af21  test    al, al
0x18004af23  jz      short loc_18004AF47
0x18004af25  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x18004af2b  mov     bl, al
0x18004af2d  cmp     edi, 3
0x18004af30  jz      short loc_18004AF47
0x18004af32  movzx   eax, al
0x18004af35  mov     cs:dword_1800B64D8, eax
0x18004af3b  jmp     short loc_18004AF47
0x18004af3d  mov     ebx, 1
0x18004af42  cmp     eax, ebx
0x18004af44  setz    bl
0x18004af47  mov     al, bl
0x18004af49  mov     rbx, [rsp+28h+arg_0]
0x18004af4e  add     rsp, 20h
0x18004af52  pop     rdi
0x18004af53  retn
```
