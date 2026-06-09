# DirectXDatabaseUpdaterLogging::`scalar deleting destructor'(uint)

- ea: `0x1400065d0`
- end: `0x140006604`
- name: `??_GDirectXDatabaseUpdaterLogging@@UEAAPEAXI@Z`
- size: `52`
- prototype: `DirectXDatabaseUpdaterLogging *__fastcall(DirectXDatabaseUpdaterLogging *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callees

- `0x140003218`
- `0x1400061ac`
- `0x1400065d0`

## pseudocode

```c
DirectXDatabaseUpdaterLogging *__fastcall DirectXDatabaseUpdaterLogging::`scalar deleting destructor'(
        DirectXDatabaseUpdaterLogging *this,
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
0x1400065d0  mov     [rsp+arg_0], rbx
0x1400065d5  push    rdi
0x1400065d6  sub     rsp, 20h
0x1400065da  mov     ebx, edx
0x1400065dc  mov     rdi, rcx
0x1400065df  call    ??1TraceLoggingProvider@wil@@MEAA@XZ; wil::TraceLoggingProvider::~TraceLoggingProvider(void)
0x1400065e4  test    bl, 1
0x1400065e7  jz      short loc_1400065F6
0x1400065e9  mov     edx, 20h ; ' '; unsigned __int64
0x1400065ee  mov     rcx, rdi; void *
0x1400065f1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400065f6  mov     rbx, [rsp+28h+arg_0]
0x1400065fb  mov     rax, rdi
0x1400065fe  add     rsp, 20h
0x140006602  pop     rdi
0x140006603  retn
```
