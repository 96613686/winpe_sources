# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001060`
- end: `0x18000108e`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001060`
- `0x1800019f8`
- `0x180003edc`

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
0x180001060  sub     rsp, 28h
0x180001064  lea     rcx, CriticalSection; this
0x18000106b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001070  test    eax, eax
0x180001072  js      short loc_18000107E
0x180001074  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x18000107e  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x180001085  add     rsp, 28h
0x180001089  jmp     atexit
```
