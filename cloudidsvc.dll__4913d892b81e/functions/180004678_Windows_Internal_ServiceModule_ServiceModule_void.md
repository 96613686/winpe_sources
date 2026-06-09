# Windows::Internal::ServiceModule::~ServiceModule(void)

- ea: `0x180004678`
- end: `0x180004697`
- name: `??1ServiceModule@Internal@Windows@@UEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Windows::Internal::ServiceModule *this, __int64, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004c5c`

## callees

- `0x180004194`
- `0x1800046a0`

## pseudocode

```c
void __fastcall Windows::Internal::ServiceModule::~ServiceModule(
        Windows::Internal::ServiceModule *this,
        __int64 a2,
        const unsigned __int16 *a3,
        bool a4)
{
  Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::~OutOfProcModuleBase<Windows::Internal::ServiceModule>(
    (Windows::Internal::ServiceModule *)((char *)this + 40),
    a2,
    a3,
    a4);
  Windows::Internal::ServiceModuleBase::~ServiceModuleBase(this);
}

```

## disassembly

```asm
0x180004678  push    rbx
0x18000467a  sub     rsp, 20h
0x18000467e  mov     rbx, rcx
0x180004681  add     rcx, 28h ; '('
0x180004685  call    ??1?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::~OutOfProcModuleBase<Windows::Internal::ServiceModule>(void)
0x18000468a  mov     rcx, rbx; this
0x18000468d  add     rsp, 20h
0x180004691  pop     rbx
0x180004692  jmp     ??1ServiceModuleBase@Internal@Windows@@QEAA@XZ; Windows::Internal::ServiceModuleBase::~ServiceModuleBase(void)
```
