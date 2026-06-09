# _HotpatchMonitor::SetServiceToAutoStart_::_1_::dtor$0

- ea: `0x180014219`
- end: `0x180014225`
- name: `_HotpatchMonitor::SetServiceToAutoStart_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x18000402c`

## pseudocode

```c
void __fastcall HotpatchMonitor::SetServiceToAutoStart_::_1_::dtor_0(__int64 a1, unsigned __int64 a2)
{
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::~unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>(
    (void **)(a2 + 96),
    a2);
}

```

## disassembly

```asm
0x180014219  lea     rcx, [rdx+60h]
0x180014220  jmp     ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::~unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>(void)
```
