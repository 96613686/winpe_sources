# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001290`
- end: `0x1800012be`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `46`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001290`
- `0x180001c88`
- `0x180006664`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init(&stru_1800212B0) >= 0 )
    ATL::_AtlComModule = 72;
  return atexit(ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180001290  sub     rsp, 28h
0x180001294  lea     rcx, stru_1800212B0; this
0x18000129b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800012a0  test    eax, eax
0x1800012a2  js      short loc_1800012AE
0x1800012a4  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x1800012ae  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x1800012b5  add     rsp, 28h
0x1800012b9  jmp     atexit
```
