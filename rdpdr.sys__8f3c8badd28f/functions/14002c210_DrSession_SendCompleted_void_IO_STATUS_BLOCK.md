# DrSession::SendCompleted(void *,_IO_STATUS_BLOCK *)

- ea: `0x14002c210`
- end: `0x14002c214`
- name: `?SendCompleted@DrSession@@EEAAJPEAXPEAU_IO_STATUS_BLOCK@@@Z`
- size: `4`
- prototype: `__int64 __fastcall(DrSession *__hidden this, void *, struct _IO_STATUS_BLOCK *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall DrSession::SendCompleted(DrSession *this, void *a2, struct _IO_STATUS_BLOCK *a3)
{
  return (unsigned int)a3->Status;
}

```

## disassembly

```asm
0x14002c210  mov     eax, [r8]
0x14002c213  retn
```
