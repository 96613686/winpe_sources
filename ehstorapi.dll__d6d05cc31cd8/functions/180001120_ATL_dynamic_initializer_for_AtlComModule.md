# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180001120`
- end: `0x18000114e`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001120`
- `0x180001c20`
- `0x180002d1c`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  if ( (int)ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)qword_1800121C0) >= 0 )
    ATL::_AtlComModule = 72;
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180001120  sub     rsp, 28h
0x180001124  lea     rcx, qword_1800121C0; this
0x18000112b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001130  test    eax, eax
0x180001132  js      short loc_18000113E
0x180001134  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x18000113e  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x180001145  add     rsp, 28h
0x180001149  jmp     atexit
```
