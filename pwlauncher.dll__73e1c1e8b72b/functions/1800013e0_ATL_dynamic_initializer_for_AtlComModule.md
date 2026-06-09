# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x1800013e0`
- end: `0x180001417`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `55`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800013e0`
- `0x180002088`
- `0x180003adc`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&CriticalSection) >= 0 )
    ATL::_AtlComModule = 72;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  return atexit(ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x1800013e0  sub     rsp, 28h
0x1800013e4  lea     rcx, CriticalSection; this
0x1800013eb  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800013f0  test    eax, eax
0x1800013f2  jns     short loc_1800013FD
0x1800013f4  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x1800013fb  jmp     short loc_180001407
0x1800013fd  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x180001407  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x18000140e  add     rsp, 28h
0x180001412  jmp     atexit
```
