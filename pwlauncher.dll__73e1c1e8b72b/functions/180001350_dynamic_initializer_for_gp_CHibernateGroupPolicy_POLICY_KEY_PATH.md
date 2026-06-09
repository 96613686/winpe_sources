# _dynamic_initializer_for__gp::CHibernateGroupPolicy::POLICY_KEY_PATH__

- ea: `0x180001350`
- end: `0x180001377`
- name: `_dynamic_initializer_for__gp::CHibernateGroupPolicy::POLICY_KEY_PATH__`
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
int dynamic_initializer_for__gp::CHibernateGroupPolicy::POLICY_KEY_PATH__()
{
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &gp::CHibernateGroupPolicy::POLICY_KEY_PATH,
    (unsigned __int64)L"System\\CurrentControlSet\\Policies\\Microsoft\\PortableOperatingSystem");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__gp::CHibernateGroupPolicy::POLICY_KEY_PATH__);
}

```

## disassembly

```asm
0x180001350  sub     rsp, 28h
0x180001354  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Policies\\Mi"...
0x18000135b  lea     rcx, ?POLICY_KEY_PATH@CHibernateGroupPolicy@gp@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const gp::CHibernateGroupPolicy::POLICY_KEY_PATH
0x180001362  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180001367  lea     rcx, _dynamic_atexit_destructor_for__gp__CHibernateGroupPolicy__POLICY_KEY_PATH__
0x18000136e  add     rsp, 28h
0x180001372  jmp     atexit
```
