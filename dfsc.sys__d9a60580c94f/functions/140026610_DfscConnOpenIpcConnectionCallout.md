# DfscConnOpenIpcConnectionCallout

- ea: `0x140026610`
- end: `0x14002665a`
- name: `DfscConnOpenIpcConnectionCallout`
- size: `74`
- prototype: `void __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140026660`

## pseudocode

```c
void __fastcall DfscConnOpenIpcConnectionCallout(PVOID Parameter)
{
  *((_DWORD *)Parameter + 16) = DfscConnOpenIpcConnectionCallin(
                                  *(_QWORD *)Parameter,
                                  *((_QWORD *)Parameter + 1),
                                  *((_QWORD *)Parameter + 2),
                                  *((_DWORD *)Parameter + 6),
                                  *((_QWORD *)Parameter + 4),
                                  *((_BYTE *)Parameter + 48),
                                  *((_QWORD *)Parameter + 7),
                                  *((PHANDLE *)Parameter + 5));
}

```

## disassembly

```asm
0x140026610  push    rbx
0x140026612  sub     rsp, 40h
0x140026616  mov     rax, [rcx+28h]
0x14002661a  mov     rbx, rcx
0x14002661d  mov     r9d, [rcx+18h]; int
0x140026621  mov     r8, [rcx+10h]; int
0x140026625  mov     rdx, [rcx+8]; int
0x140026629  mov     [rsp+48h+FileHandle], rax; FileHandle
0x14002662e  mov     rax, [rcx+38h]
0x140026632  mov     [rsp+48h+var_18], rax; __int64
0x140026637  movzx   eax, byte ptr [rcx+30h]
0x14002663b  mov     [rsp+48h+var_20], al; char
0x14002663f  mov     rax, [rcx+20h]
0x140026643  mov     rcx, [rcx]; int
0x140026646  mov     [rsp+48h+var_28], rax; __int64
0x14002664b  call    DfscConnOpenIpcConnectionCallin
0x140026650  mov     [rbx+40h], eax
0x140026653  add     rsp, 40h
0x140026657  pop     rbx
0x140026658  retn
```
