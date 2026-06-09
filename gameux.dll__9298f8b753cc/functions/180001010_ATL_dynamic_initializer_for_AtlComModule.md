# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001010`
- end: `0x180001055`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001010`
- `0x180001170`
- `0x180001838`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&stru_1800070C0) >= 0 )
    ATL::_AtlComModule = 72;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  return atexit(ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180001010  sub     rsp, 28h
0x180001014  lea     rcx, stru_1800070C0; this
0x18000101b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001020  test    eax, eax
0x180001022  jns     short loc_18000103B
0x180001024  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x18000102b  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x180001032  add     rsp, 28h
0x180001036  jmp     atexit
0x18000103b  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x180001042  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x18000104c  add     rsp, 28h
0x180001050  jmp     atexit
```
