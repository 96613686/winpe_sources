# _dynamic_initializer_for__ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC__

- ea: `0x1800011d0`
- end: `0x180001208`
- name: `_dynamic_initializer_for__ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC__`
- size: `56`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800011d0`
- `0x180002088`
- `0x18000374c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800011db`
- `OLEAUT32!__imp_SysAllocString` at `0x1800011db`

## pseudocode

```c
int dynamic_initializer_for__ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC__()
{
  ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC = SysAllocString(L"mshelp://windows/?id=00000000-0000-0000-0000-000000000000");
  if ( !ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC )
    ATL::AtlThrowImpl(-2147024882);
  return atexit(dynamic_atexit_destructor_for__ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC__);
}

```

## disassembly

```asm
0x1800011d0  sub     rsp, 28h
0x1800011d4  lea     rcx, psz; "mshelp://windows/?id=00000000-0000-0000"...
0x1800011db  call    cs:__imp_SysAllocString
0x1800011e1  mov     cs:?FIRMWARE_HELP_TOPIC@CLauncherErrorTaskDialog@ux@@0VCComBSTR@ATL@@B, rax; ATL::CComBSTR const ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC
0x1800011e8  test    rax, rax
0x1800011eb  jz      short loc_1800011FD
0x1800011ed  lea     rcx, _dynamic_atexit_destructor_for__ux__CLauncherErrorTaskDialog__FIRMWARE_HELP_TOPIC__
0x1800011f4  add     rsp, 28h
0x1800011f8  jmp     atexit
0x1800011fd  mov     ecx, 8007000Eh; int
0x180001202  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
