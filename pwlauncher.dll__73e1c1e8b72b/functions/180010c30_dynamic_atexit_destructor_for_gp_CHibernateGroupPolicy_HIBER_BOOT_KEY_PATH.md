# _dynamic_atexit_destructor_for__gp::CHibernateGroupPolicy::HIBER_BOOT_KEY_PATH__

- ea: `0x180010c30`
- end: `0x180010c60`
- name: `_dynamic_atexit_destructor_for__gp::CHibernateGroupPolicy::HIBER_BOOT_KEY_PATH__`
- size: `48`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180010c30`
- `0x180011010`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__gp::CHibernateGroupPolicy::HIBER_BOOT_KEY_PATH__()
{
  LPCWSTR v0; // rdx
  signed __int32 v1; // eax
  bool v2; // cc
  __int64 result; // rax

  v0 = gp::CHibernateGroupPolicy::HIBER_BOOT_KEY_PATH - 12;
  v1 = _InterlockedExchangeAdd(
         (volatile signed __int32 *)gp::CHibernateGroupPolicy::HIBER_BOOT_KEY_PATH - 2,
         0xFFFFFFFF);
  v2 = v1 <= 1;
  result = (unsigned int)(v1 - 1);
  if ( v2 )
    return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v0 + 8LL))(*(_QWORD *)v0);
  return result;
}

```

## disassembly

```asm
0x180010c30  sub     rsp, 28h
0x180010c34  mov     rdx, cs:?HIBER_BOOT_KEY_PATH@CHibernateGroupPolicy@gp@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const gp::CHibernateGroupPolicy::HIBER_BOOT_KEY_PATH
0x180010c3b  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180010c3f  or      eax, 0FFFFFFFFh
0x180010c42  lock xadd [rdx+10h], eax
0x180010c47  sub     eax, 1
0x180010c4a  jg      short loc_180010C5B
0x180010c4c  mov     rcx, [rdx]
0x180010c4f  mov     rax, [rcx]
0x180010c52  mov     rax, [rax+8]
0x180010c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c5b  add     rsp, 28h
0x180010c5f  retn
```
