# CTxtEdit::TxUpdateWindow(void)

- ea: `0x180048e54`
- end: `0x180048e73`
- name: `?TxUpdateWindow@CTxtEdit@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(CTxtEdit *__hidden this)`
- caller_count: `14`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180006610`
- `0x1800322bc`
- `0x1800379a0`
- `0x1800385d0`
- `0x18003a3b4`
- `0x18003ba00`
- `0x180043514`
- `0x180055270`
- `0x1800579f0`
- `0x180058e50`
- `0x18005d798`
- `0x18006f360`
- `0x180071654`
- `0x180084530`

## callees

- `0x180092010`

## pseudocode

```c
void __fastcall CTxtEdit::TxUpdateWindow(CTxtEdit *this)
{
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6) + 80LL))(
    *((_QWORD *)this + 6),
    (*((_DWORD *)this + 45) >> 3) & 1);
}

```

## disassembly

```asm
0x180048e54  mov     r8, [rcx+30h]
0x180048e58  mov     edx, [rcx+0B4h]
0x180048e5e  mov     rcx, r8
0x180048e61  shr     edx, 3
0x180048e64  and     edx, 1
0x180048e67  mov     rax, [r8]
0x180048e6a  mov     rax, [rax+50h]
0x180048e6e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
