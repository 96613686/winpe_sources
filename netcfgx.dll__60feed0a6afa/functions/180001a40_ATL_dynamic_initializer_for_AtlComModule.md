# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001a40`
- end: `0x180001a6e`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001a40`
- `0x1800023ac`
- `0x18000465c`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&stru_18001A200) >= 0 )
    ATL::_AtlComModule = 72;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180001a40  sub     rsp, 28h
0x180001a44  lea     rcx, stru_18001A200; this
0x180001a4b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001a50  test    eax, eax
0x180001a52  js      short loc_180001A5E
0x180001a54  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x180001a5e  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x180001a65  add     rsp, 28h
0x180001a69  jmp     atexit
```
