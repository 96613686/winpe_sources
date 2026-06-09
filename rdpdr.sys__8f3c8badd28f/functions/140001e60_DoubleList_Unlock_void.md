# DoubleList::Unlock(void)

- ea: `0x140001e60`
- end: `0x140001e7b`
- name: `?Unlock@DoubleList@@QEAAXXZ`
- size: `27`
- prototype: `void __fastcall(DoubleList *__hidden this)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x140011b3c`
- `0x140017eb0`
- `0x140019aa4`
- `0x14001d504`
- `0x14001d938`
- `0x14001dafc`
- `0x14001dcb4`
- `0x14001fbd8`
- `0x14001fd20`
- `0x140024360`
- `0x140026a48`
- `0x140027fe0`
- `0x14002c940`

## callees

- `0x140006560`

## pseudocode

```c
void __fastcall DoubleList::Unlock(DoubleList *this)
{
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 4) + 32LL))((char *)this + 32);
}

```

## disassembly

```asm
0x140001e60  sub     rsp, 28h
0x140001e64  mov     rax, [rcx+20h]
0x140001e68  add     rcx, 20h ; ' '
0x140001e6c  mov     rax, [rax+20h]
0x140001e70  call    _guard_dispatch_icall
0x140001e75  add     rsp, 28h
0x140001e79  retn
```
