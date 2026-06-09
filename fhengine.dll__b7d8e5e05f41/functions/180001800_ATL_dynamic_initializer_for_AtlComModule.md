# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001800`
- end: `0x180001837`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001800`
- `0x180002504`
- `0x180004f0c`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)qword_1800401D0) >= 0 )
    ATL::_AtlComModule = 72;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180001800  sub     rsp, 28h
0x180001804  lea     rcx, qword_1800401D0; this
0x18000180b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001810  test    eax, eax
0x180001812  jns     short loc_18000181D
0x180001814  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x18000181b  jmp     short loc_180001827
0x18000181d  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x180001827  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x18000182e  add     rsp, 28h
0x180001832  jmp     atexit
```
