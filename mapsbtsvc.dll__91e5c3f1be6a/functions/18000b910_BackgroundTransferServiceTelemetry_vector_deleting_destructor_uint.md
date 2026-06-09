# BackgroundTransferServiceTelemetry::`vector deleting destructor'(uint)

- ea: `0x18000b910`
- end: `0x18000b93f`
- name: `??_EBackgroundTransferServiceTelemetry@@UEAAPEAXI@Z`
- size: `47`
- prototype: `BackgroundTransferServiceTelemetry *__fastcall(BackgroundTransferServiceTelemetry *this, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x180009700`

## callees

- `0x180001e54`
- `0x18000b67c`
- `0x18000b910`

## pseudocode

```c
BackgroundTransferServiceTelemetry *__fastcall BackgroundTransferServiceTelemetry::`vector deleting destructor'(
        BackgroundTransferServiceTelemetry *this,
        char a2)
{
  wil::TraceLoggingProvider::~TraceLoggingProvider(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000b910  mov     [rsp+arg_0], rbx
0x18000b915  push    rdi
0x18000b916  sub     rsp, 20h
0x18000b91a  mov     ebx, edx
0x18000b91c  mov     rdi, rcx
0x18000b91f  call    ??1TraceLoggingProvider@wil@@MEAA@XZ; wil::TraceLoggingProvider::~TraceLoggingProvider(void)
0x18000b924  test    bl, 1
0x18000b927  jz      short loc_18000B931
0x18000b929  mov     rcx, rdi; Block
0x18000b92c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b931  mov     rbx, [rsp+28h+arg_0]
0x18000b936  mov     rax, rdi
0x18000b939  add     rsp, 20h
0x18000b93d  pop     rdi
0x18000b93e  retn
```
