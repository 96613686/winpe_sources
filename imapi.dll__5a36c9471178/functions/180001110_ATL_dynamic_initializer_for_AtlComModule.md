# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001110`
- end: `0x18000113e`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001110`
- `0x180001c24`
- `0x180002f5c`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&CriticalSection) >= 0 )
    ATL::_AtlComModule = 72;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180001110  sub     rsp, 28h
0x180001114  lea     rcx, CriticalSection; this
0x18000111b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001120  test    eax, eax
0x180001122  js      short loc_18000112E
0x180001124  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x18000112e  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x180001135  add     rsp, 28h
0x180001139  jmp     atexit
```
