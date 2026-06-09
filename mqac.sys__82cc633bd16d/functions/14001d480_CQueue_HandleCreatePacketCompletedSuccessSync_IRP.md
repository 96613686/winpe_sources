# CQueue::HandleCreatePacketCompletedSuccessSync(_IRP *)

- ea: `0x14001d480`
- end: `0x14001d499`
- name: `?HandleCreatePacketCompletedSuccessSync@CQueue@@EEAAJPEAU_IRP@@@Z`
- size: `25`
- prototype: `__int64 __fastcall(CQueue *__hidden this, struct _IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140024bf0`

## pseudocode

```c
__int64 __fastcall CQueue::HandleCreatePacketCompletedSuccessSync(CQueue *this, struct _IRP *a2)
{
  return (*(__int64 (__fastcall **)(CQueue *, struct _IRP *))(*(_QWORD *)this + 152LL))(this, a2);
}

```

## disassembly

```asm
0x14001d480  sub     rsp, 28h
0x14001d484  mov     rax, [rcx]
0x14001d487  mov     rax, [rax+98h]
0x14001d48e  call    _guard_dispatch_icall
0x14001d493  add     rsp, 28h
0x14001d497  retn
```
