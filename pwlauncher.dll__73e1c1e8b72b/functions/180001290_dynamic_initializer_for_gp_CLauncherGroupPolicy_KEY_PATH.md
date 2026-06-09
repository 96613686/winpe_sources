# _dynamic_initializer_for__gp::CLauncherGroupPolicy::KEY_PATH__

- ea: `0x180001290`
- end: `0x1800012b7`
- name: `_dynamic_initializer_for__gp::CLauncherGroupPolicy::KEY_PATH__`
- size: `39`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002088`
- `0x1800092dc`

## pseudocode

```c
int dynamic_initializer_for__gp::CLauncherGroupPolicy::KEY_PATH__()
{
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &gp::CLauncherGroupPolicy::KEY_PATH,
    (unsigned __int64)L"Software\\Policies\\Microsoft\\PortableOperatingSystem");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__gp::CLauncherGroupPolicy::KEY_PATH__);
}

```

## disassembly

```asm
0x180001290  sub     rsp, 28h
0x180001294  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Portable"...
0x18000129b  lea     rcx, ?KEY_PATH@CLauncherGroupPolicy@gp@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const gp::CLauncherGroupPolicy::KEY_PATH
0x1800012a2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800012a7  lea     rcx, _dynamic_atexit_destructor_for__gp__CLauncherGroupPolicy__KEY_PATH__
0x1800012ae  add     rsp, 28h
0x1800012b2  jmp     atexit
```
