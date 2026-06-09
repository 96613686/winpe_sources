# IsTelemetryInPrivate(void)

- ea: `0x18004bbd0`
- end: `0x18004bc9d`
- name: `?IsTelemetryInPrivate@@YA_NXZ`
- size: `205`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004bac4`

## callees

- `0x18004bbd0`
- `0x18005a008`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18004bc67`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18004bc67`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x18004bc57`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x18004bc57`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x18004bc2b`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x18004bc2b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18004bc01`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18004bc1b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18004bc01`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18004bc1b`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18004bbee`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18004bbee`

## string_xrefs

- `0x18004bc40`: `onecoreuap\inetcore\lib\tracelogging\legacydll.cpp`

## pseudocode

```c
char IsTelemetryInPrivate(void)
{
  int DWORD; // edi
  const char *v1; // r9
  char v2; // bl
  bool v3; // al
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( dword_1800B84DC != 2 )
    return dword_1800B84DC == 1;
  DWORD = IEConfiguration_GetDWORD(268435501);
  if ( (unsigned __int8)IEConfiguration_GetBool(536870914) || DWORD != 2 )
  {
    v2 = 1;
    if ( LCIEIsCurrentProcessInPrivateOverrideSet() )
    {
      v3 = LCIEIsCurrentProcessInPrivate();
      v2 = v3;
      if ( DWORD != 3 )
        dword_1800B84DC = v3;
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
0x18004bbd0  mov     [rsp+arg_0], rbx
0x18004bbd5  push    rdi
0x18004bbd6  sub     rsp, 20h
0x18004bbda  mov     eax, cs:dword_1800B84DC
0x18004bbe0  cmp     eax, 2
0x18004bbe3  jnz     loc_18004BC85
0x18004bbe9  mov     ecx, 1000002Dh
0x18004bbee  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18004bbf5  nop     dword ptr [rax+rax+00h]
0x18004bbfa  mov     ecx, 20000002h
0x18004bbff  mov     edi, eax
0x18004bc01  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18004bc08  nop     dword ptr [rax+rax+00h]
0x18004bc0d  test    al, al
0x18004bc0f  jnz     short loc_18004BC52
0x18004bc11  cmp     edi, 2
0x18004bc14  jnz     short loc_18004BC52
0x18004bc16  mov     ecx, 10000038h
0x18004bc1b  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18004bc22  nop     dword ptr [rax+rax+00h]
0x18004bc27  test    al, al
0x18004bc29  jz      short loc_18004BC3B
0x18004bc2b  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x18004bc32  nop     dword ptr [rax+rax+00h]
0x18004bc37  mov     bl, al
0x18004bc39  jmp     short loc_18004BC8F
0x18004bc3b  mov     rcx, [rsp+28h]; this
0x18004bc40  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\lib\\tracelogging"...
0x18004bc47  mov     edx, 10h; void *
0x18004bc4c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18004bc52  mov     ebx, 1
0x18004bc57  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x18004bc5e  nop     dword ptr [rax+rax+00h]
0x18004bc63  test    al, al
0x18004bc65  jz      short loc_18004BC8F
0x18004bc67  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x18004bc6e  nop     dword ptr [rax+rax+00h]
0x18004bc73  mov     bl, al
0x18004bc75  cmp     edi, 3
0x18004bc78  jz      short loc_18004BC8F
0x18004bc7a  movzx   eax, al
0x18004bc7d  mov     cs:dword_1800B84DC, eax
0x18004bc83  jmp     short loc_18004BC8F
0x18004bc85  mov     ebx, 1
0x18004bc8a  cmp     eax, ebx
0x18004bc8c  setz    bl
0x18004bc8f  mov     al, bl
0x18004bc91  mov     rbx, [rsp+28h+arg_0]
0x18004bc96  add     rsp, 20h
0x18004bc9a  pop     rdi
0x18004bc9b  retn
```
