# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x1800012e0`
- end: `0x18000130e`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800012e0`
- `0x180001c88`
- `0x18000a948`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)qword_1800275A0) >= 0 )
    ATL::_AtlComModule = 72;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x1800012e0  sub     rsp, 28h
0x1800012e4  lea     rcx, qword_1800275A0; this
0x1800012eb  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800012f0  test    eax, eax
0x1800012f2  js      short loc_1800012FE
0x1800012f4  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x1800012fe  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x180001305  add     rsp, 28h
0x180001309  jmp     atexit
```
