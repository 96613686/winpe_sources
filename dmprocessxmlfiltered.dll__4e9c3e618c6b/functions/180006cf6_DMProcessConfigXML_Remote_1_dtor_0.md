# _DMProcessConfigXML_Remote_::_1_::dtor$0

- ea: `0x180006cf6`
- end: `0x180006d02`
- name: `_DMProcessConfigXML_Remote_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003270`

## pseudocode

```c
__int64 __fastcall DMProcessConfigXML_Remote_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFn__lambda_ad248e0ab71bdb01f4ac6bd623336000___::_ScopeExitFn__lambda_ad248e0ab71bdb01f4ac6bd623336000___(a2 + 48);
}

```

## disassembly

```asm
0x180006cf6  lea     rcx, [rdx+30h]
0x180006cfd  jmp     wil__details__ScopeExitFn__lambda_ad248e0ab71bdb01f4ac6bd623336000______ScopeExitFn__lambda_ad248e0ab71bdb01f4ac6bd623336000___
```
