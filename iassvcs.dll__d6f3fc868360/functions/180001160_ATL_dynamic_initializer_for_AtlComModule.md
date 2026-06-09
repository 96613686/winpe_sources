# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001160`
- end: `0x18000118e`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `46`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001160`
- `0x18000195c`
- `0x18001033c`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&CriticalSection) >= 0 )
    ATL::_AtlComModule = 72;
  return atexit(ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180001160  sub     rsp, 28h
0x180001164  lea     rcx, CriticalSection; this
0x18000116b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001170  test    eax, eax
0x180001172  js      short loc_18000117E
0x180001174  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x18000117e  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x180001185  add     rsp, 28h
0x180001189  jmp     atexit
```
