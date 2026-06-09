# IntfHlpDeinit(void)

- ea: `0x18002807c`
- end: `0x1800280d9`
- name: `?IntfHlpDeinit@@YAXXZ`
- size: `93`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b9fc`

## callees

- `0x18002821c`

## import_xrefs

- `MobileNetworking!AcquireWriteLock` at `0x18002809b`
- `MobileNetworking!AcquireWriteLock` at `0x18002809b`
- `MobileNetworking!ReleaseWriteLock` at `0x1800280c1`
- `MobileNetworking!ReleaseWriteLock` at `0x1800280c1`
- `MobileNetworking!DeleteReadWriteLock` at `0x1800280d2`

## pseudocode

```c
void IntfHlpDeinit(void)
{
  AcquireWriteLock(&Block, qword_180052DF0, "IntfHlpDeinit", 112);
  ResetAdapterAddressesInfo();
  ReleaseWriteLock(&Block, qword_180052DF0, "IntfHlpDeinit", 116);
  DeleteReadWriteLock(qword_180052DF0);
}

```

## disassembly

```asm
0x18002807c  sub     rsp, 28h
0x180028080  mov     r9d, 70h ; 'p'
0x180028086  lea     r8, aIntfhlpdeinit; "IntfHlpDeinit"
0x18002808d  lea     rdx, qword_180052DF0
0x180028094  lea     rcx, Block
0x18002809b  call    cs:__imp_AcquireWriteLock
0x1800280a1  call    ?ResetAdapterAddressesInfo@@YAXXZ; ResetAdapterAddressesInfo(void)
0x1800280a6  mov     r9d, 74h ; 't'
0x1800280ac  lea     r8, aIntfhlpdeinit; "IntfHlpDeinit"
0x1800280b3  lea     rdx, qword_180052DF0
0x1800280ba  lea     rcx, Block
0x1800280c1  call    cs:__imp_ReleaseWriteLock
0x1800280c7  lea     rcx, qword_180052DF0
0x1800280ce  add     rsp, 28h
0x1800280d2  jmp     cs:__imp_DeleteReadWriteLock
```
