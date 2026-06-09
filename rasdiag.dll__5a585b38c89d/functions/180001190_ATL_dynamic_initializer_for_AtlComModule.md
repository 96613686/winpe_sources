# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001190`
- end: `0x1800011c7`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `55`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001190`
- `0x180002560`
- `0x18000447c`

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
0x180001190  sub     rsp, 28h
0x180001194  lea     rcx, CriticalSection; this
0x18000119b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800011a0  test    eax, eax
0x1800011a2  jns     short loc_1800011AD
0x1800011a4  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x1800011ab  jmp     short loc_1800011B7
0x1800011ad  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x1800011b7  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x1800011be  add     rsp, 28h
0x1800011c2  jmp     atexit
```
