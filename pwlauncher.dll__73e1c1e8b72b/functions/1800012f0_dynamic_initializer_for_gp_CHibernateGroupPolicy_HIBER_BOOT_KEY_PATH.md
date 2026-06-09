# _dynamic_initializer_for__gp::CHibernateGroupPolicy::HIBER_BOOT_KEY_PATH__

- ea: `0x1800012f0`
- end: `0x180001317`
- name: `_dynamic_initializer_for__gp::CHibernateGroupPolicy::HIBER_BOOT_KEY_PATH__`
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
int dynamic_initializer_for__gp::CHibernateGroupPolicy::HIBER_BOOT_KEY_PATH__()
{
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &gp::CHibernateGroupPolicy::HIBER_BOOT_KEY_PATH,
    (unsigned __int64)L"Software\\Policies\\Microsoft\\Windows\\System");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__gp::CHibernateGroupPolicy::HIBER_BOOT_KEY_PATH__);
}

```

## disassembly

```asm
0x1800012f0  sub     rsp, 28h
0x1800012f4  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x1800012fb  lea     rcx, ?HIBER_BOOT_KEY_PATH@CHibernateGroupPolicy@gp@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const gp::CHibernateGroupPolicy::HIBER_BOOT_KEY_PATH
0x180001302  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180001307  lea     rcx, _dynamic_atexit_destructor_for__gp__CHibernateGroupPolicy__HIBER_BOOT_KEY_PATH__
0x18000130e  add     rsp, 28h
0x180001312  jmp     atexit
```
