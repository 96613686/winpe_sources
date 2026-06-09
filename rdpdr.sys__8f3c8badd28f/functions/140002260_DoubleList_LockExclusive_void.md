# DoubleList::LockExclusive(void)

- ea: `0x140002260`
- end: `0x14000227b`
- name: `?LockExclusive@DoubleList@@QEAAXXZ`
- size: `27`
- prototype: `void __fastcall(DoubleList *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140017eb0`
- `0x14001d504`
- `0x14001d938`
- `0x14001dafc`
- `0x14001dcb4`
- `0x14001fbd8`
- `0x14001fd20`
- `0x140026a48`
- `0x14002c940`

## callees

- `0x140006560`

## pseudocode

```c
void __fastcall DoubleList::LockExclusive(DoubleList *this)
{
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 4) + 24LL))((char *)this + 32);
}

```

## disassembly

```asm
0x140002260  sub     rsp, 28h
0x140002264  mov     rax, [rcx+20h]
0x140002268  add     rcx, 20h ; ' '
0x14000226c  mov     rax, [rax+18h]
0x140002270  call    _guard_dispatch_icall
0x140002275  add     rsp, 28h
0x140002279  retn
```
