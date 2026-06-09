# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001890`
- end: `0x1800018be`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001890`
- `0x180001f84`
- `0x180006f6c`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&stru_18001A210) >= 0 )
    ATL::_AtlComModule = 72;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180001890  sub     rsp, 28h
0x180001894  lea     rcx, stru_18001A210; this
0x18000189b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800018a0  test    eax, eax
0x1800018a2  js      short loc_1800018AE
0x1800018a4  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x1800018ae  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x1800018b5  add     rsp, 28h
0x1800018b9  jmp     atexit
```
