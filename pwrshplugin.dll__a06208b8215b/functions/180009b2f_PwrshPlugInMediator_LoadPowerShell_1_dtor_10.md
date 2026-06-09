# _PwrshPlugInMediator::LoadPowerShell_::_1_::dtor$10

- ea: `0x180009b2f`
- end: `0x180009b3f`
- name: `_PwrshPlugInMediator::LoadPowerShell_::_1_::dtor$10`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800051a4`

## pseudocode

```c
__int64 __fastcall PwrshPlugInMediator::LoadPowerShell_::_1_::dtor_10(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<mscorlib::_AppDomain>::~CComPtr<mscorlib::_AppDomain>((__int64 *)(*(_QWORD *)(a2 + 64) + 8LL));
}

```

## disassembly

```asm
0x180009b2f  mov     rcx, [rdx+40h]
0x180009b36  add     rcx, 8
0x180009b3a  jmp     ??1?$CComPtr@U_AppDomain@mscorlib@@@ATL@@QEAA@XZ; ATL::CComPtr<mscorlib::_AppDomain>::~CComPtr<mscorlib::_AppDomain>(void)
```
