# _CTriggerMonitorPool::CreateNotificationTrigger_::_1_::dtor$5

- ea: `0x14001de18`
- end: `0x14001de41`
- name: `_CTriggerMonitorPool::CreateNotificationTrigger_::_1_::dtor$5`
- size: `41`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003194`
- `0x14001de18`

## pseudocode

```c
void __fastcall CTriggerMonitorPool::CreateNotificationTrigger_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 80) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 80) &= ~1u;
    _bstr_t::~_bstr_t((_bstr_t *)(a2 + 168));
  }
}

```

## disassembly

```asm
0x14001de18  push    rbp
0x14001de1a  sub     rsp, 20h
0x14001de1e  mov     rbp, rdx
0x14001de21  mov     eax, [rbp+50h]
0x14001de24  and     eax, 1
0x14001de27  test    eax, eax
0x14001de29  jz      short loc_14001DE3B
0x14001de2b  and     dword ptr [rbp+50h], 0FFFFFFFEh
0x14001de2f  lea     rcx, [rbp+0A8h]; this
0x14001de36  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14001de3b  add     rsp, 20h
0x14001de3f  pop     rbp
0x14001de40  retn
```
