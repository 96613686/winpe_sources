# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001130`
- end: `0x180001167`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `55`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001130`
- `0x180001ca4`
- `0x1800039cc`

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
0x180001130  sub     rsp, 28h
0x180001134  lea     rcx, CriticalSection; this
0x18000113b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001140  test    eax, eax
0x180001142  jns     short loc_18000114D
0x180001144  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x18000114b  jmp     short loc_180001157
0x18000114d  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x180001157  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x18000115e  add     rsp, 28h
0x180001162  jmp     atexit
```
