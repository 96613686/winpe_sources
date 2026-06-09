# IsTelemetryInPrivate(void)

- ea: `0x1400057f8`
- end: `0x14000589c`
- name: `?IsTelemetryInPrivate@@YA_NXZ`
- size: `164`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140001310`

## callees

- `0x1400032b4`
- `0x1400057f8`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x14000586d`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x14000586d`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x140005863`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x140005863`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x14000583d`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x14000583d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x14000581f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x140005833`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x14000581f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x140005833`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x140005812`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x140005812`

## string_xrefs

- `0x14000584c`: `onecoreuap\inetcore\lib\tracelogging\legacydll.cpp`

## pseudocode

```c
char IsTelemetryInPrivate(void)
{
  int DWORD; // edi
  const char *v1; // r9
  char v2; // bl
  bool v3; // al
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( dword_14000A154 != 2 )
    return dword_14000A154 == 1;
  DWORD = IEConfiguration_GetDWORD(268435501);
  if ( (unsigned __int8)IEConfiguration_GetBool(536870914) || DWORD != 2 )
  {
    v2 = 1;
    if ( LCIEIsCurrentProcessInPrivateOverrideSet() )
    {
      v3 = LCIEIsCurrentProcessInPrivate();
      v2 = v3;
      if ( DWORD != 3 )
        dword_14000A154 = v3;
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
0x1400057f8  mov     [rsp+arg_0], rbx
0x1400057fd  push    rdi
0x1400057fe  sub     rsp, 20h
0x140005802  mov     eax, cs:dword_14000A154
0x140005808  cmp     eax, 2
0x14000580b  jnz     short loc_140005885
0x14000580d  mov     ecx, 1000002Dh
0x140005812  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x140005818  mov     ecx, 20000002h
0x14000581d  mov     edi, eax
0x14000581f  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x140005825  test    al, al
0x140005827  jnz     short loc_14000585E
0x140005829  cmp     edi, 2
0x14000582c  jnz     short loc_14000585E
0x14000582e  mov     ecx, 10000038h
0x140005833  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x140005839  test    al, al
0x14000583b  jz      short loc_140005847
0x14000583d  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x140005843  mov     bl, al
0x140005845  jmp     short loc_14000588F
0x140005847  mov     rcx, [rsp+28h]; this
0x14000584c  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\lib\\tracelogging"...
0x140005853  mov     edx, 10h; void *
0x140005858  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000585e  mov     ebx, 1
0x140005863  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x140005869  test    al, al
0x14000586b  jz      short loc_14000588F
0x14000586d  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x140005873  mov     bl, al
0x140005875  cmp     edi, 3
0x140005878  jz      short loc_14000588F
0x14000587a  movzx   eax, al
0x14000587d  mov     cs:dword_14000A154, eax
0x140005883  jmp     short loc_14000588F
0x140005885  mov     ebx, 1
0x14000588a  cmp     eax, ebx
0x14000588c  setz    bl
0x14000588f  mov     al, bl
0x140005891  mov     rbx, [rsp+28h+arg_0]
0x140005896  add     rsp, 20h
0x14000589a  pop     rdi
0x14000589b  retn
```
