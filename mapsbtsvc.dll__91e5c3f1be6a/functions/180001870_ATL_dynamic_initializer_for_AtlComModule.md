# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001870`
- end: `0x18000189e`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001870`
- `0x18000222c`
- `0x18000303c`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)qword_18001D0A0) >= 0 )
    ATL::_AtlComModule = 72;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180001870  sub     rsp, 28h
0x180001874  lea     rcx, qword_18001D0A0; this
0x18000187b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001880  test    eax, eax
0x180001882  js      short loc_18000188E
0x180001884  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x18000188e  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x180001895  add     rsp, 28h
0x180001899  jmp     atexit
```
