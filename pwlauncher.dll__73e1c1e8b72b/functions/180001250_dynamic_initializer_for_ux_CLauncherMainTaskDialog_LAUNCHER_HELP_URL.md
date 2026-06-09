# _dynamic_initializer_for__ux::CLauncherMainTaskDialog::LAUNCHER_HELP_URL__

- ea: `0x180001250`
- end: `0x180001288`
- name: `_dynamic_initializer_for__ux::CLauncherMainTaskDialog::LAUNCHER_HELP_URL__`
- size: `56`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001250`
- `0x180002088`
- `0x18000374c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000125b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000125b`

## pseudocode

```c
int dynamic_initializer_for__ux::CLauncherMainTaskDialog::LAUNCHER_HELP_URL__()
{
  ux::CLauncherMainTaskDialog::LAUNCHER_HELP_URL = SysAllocString(L"mshelp://windows/?id=2eb8104c-2b9d-48f0-98e9-2ea70d47f115");
  if ( !ux::CLauncherMainTaskDialog::LAUNCHER_HELP_URL )
    ATL::AtlThrowImpl(-2147024882);
  return atexit(dynamic_atexit_destructor_for__ux::CLauncherMainTaskDialog::LAUNCHER_HELP_URL__);
}

```

## disassembly

```asm
0x180001250  sub     rsp, 28h
0x180001254  lea     rcx, aMshelpWindowsI_1; "mshelp://windows/?id=2eb8104c-2b9d-48f0"...
0x18000125b  call    cs:__imp_SysAllocString
0x180001261  mov     cs:?LAUNCHER_HELP_URL@CLauncherMainTaskDialog@ux@@0VCComBSTR@ATL@@B, rax; ATL::CComBSTR const ux::CLauncherMainTaskDialog::LAUNCHER_HELP_URL
0x180001268  test    rax, rax
0x18000126b  jz      short loc_18000127D
0x18000126d  lea     rcx, _dynamic_atexit_destructor_for__ux__CLauncherMainTaskDialog__LAUNCHER_HELP_URL__
0x180001274  add     rsp, 28h
0x180001278  jmp     atexit
0x18000127d  mov     ecx, 8007000Eh; int
0x180001282  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
