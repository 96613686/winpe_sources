# _dynamic_initializer_for__g_groupPolicyMonitor__

- ea: `0x180008bd0`
- end: `0x180008c34`
- name: `_dynamic_initializer_for__g_groupPolicyMonitor__`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008bd0`
- `0x180010200`
- `0x1800477c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008bde`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008bde`

## pseudocode

```c
int dynamic_initializer_for__g_groupPolicyMonitor__()
{
  g_groupPolicyMonitor = CreateEventW(0, 0, 0, 0);
  if ( !g_groupPolicyMonitor
    && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_8c649a3b49c335dd6fdbca526a2b3512_Traceguids);
  }
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_groupPolicyMonitor__);
}

```

## disassembly

```asm
0x180008bd0  sub     rsp, 28h
0x180008bd4  xor     r9d, r9d; lpName
0x180008bd7  xor     r8d, r8d; bInitialState
0x180008bda  xor     edx, edx; bManualReset
0x180008bdc  xor     ecx, ecx; lpEventAttributes
0x180008bde  call    cs:__imp_CreateEventW
0x180008be4  mov     cs:?g_groupPolicyMonitor@@3VGroupPolicyMonitor@@A, rax; GroupPolicyMonitor g_groupPolicyMonitor
0x180008beb  test    rax, rax
0x180008bee  jnz     short loc_180008C24
0x180008bf0  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bf7  lea     rax, WPP_GLOBAL_Control
0x180008bfe  cmp     rcx, rax
0x180008c01  jz      short loc_180008C24
0x180008c03  test    byte ptr [rcx+1Ch], 10h
0x180008c07  jz      short loc_180008C24
0x180008c09  cmp     byte ptr [rcx+19h], 3
0x180008c0d  jb      short loc_180008C24
0x180008c0f  mov     rcx, [rcx+10h]
0x180008c13  lea     r8, WPP_8c649a3b49c335dd6fdbca526a2b3512_Traceguids
0x180008c1a  mov     edx, 0Ah
0x180008c1f  call    WPP_SF_
0x180008c24  lea     rcx, _dynamic_atexit_destructor_for__g_groupPolicyMonitor__
0x180008c2b  add     rsp, 28h
0x180008c2f  jmp     atexit
```
