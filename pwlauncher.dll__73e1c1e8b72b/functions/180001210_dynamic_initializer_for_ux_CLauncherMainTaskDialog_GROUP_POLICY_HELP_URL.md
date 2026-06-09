# _dynamic_initializer_for__ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL__

- ea: `0x180001210`
- end: `0x180001248`
- name: `_dynamic_initializer_for__ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL__`
- size: `56`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001210`
- `0x180002088`
- `0x18000374c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000121b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000121b`

## pseudocode

```c
int dynamic_initializer_for__ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL__()
{
  ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL = SysAllocString(L"mshelp://windows/?id=ca607790-adf6-41a7-abd8-0a1f2feb70b1");
  if ( !ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL )
    ATL::AtlThrowImpl(-2147024882);
  return atexit(dynamic_atexit_destructor_for__ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL__);
}

```

## disassembly

```asm
0x180001210  sub     rsp, 28h
0x180001214  lea     rcx, aMshelpWindowsI; "mshelp://windows/?id=ca607790-adf6-41a7"...
0x18000121b  call    cs:__imp_SysAllocString
0x180001221  mov     cs:?GROUP_POLICY_HELP_URL@CLauncherMainTaskDialog@ux@@0VCComBSTR@ATL@@B, rax; ATL::CComBSTR const ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL
0x180001228  test    rax, rax
0x18000122b  jz      short loc_18000123D
0x18000122d  lea     rcx, _dynamic_atexit_destructor_for__ux__CLauncherMainTaskDialog__GROUP_POLICY_HELP_URL__
0x180001234  add     rsp, 28h
0x180001238  jmp     atexit
0x18000123d  mov     ecx, 8007000Eh; int
0x180001242  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
