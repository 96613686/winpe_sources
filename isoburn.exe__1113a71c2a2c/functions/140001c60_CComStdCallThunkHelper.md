# CComStdCallThunkHelper

- ea: `0x140001c60`
- end: `0x140001c7a`
- name: `CComStdCallThunkHelper`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140006270`

## pseudocode

```c
__int64 __fastcall CComStdCallThunkHelper(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(_QWORD, __int64))(a1 + 16))(*(_QWORD *)(a1 + 8), a2);
}

```

## disassembly

```asm
0x140001c60  mov     rax, rcx
0x140001c63  mov     rcx, [rcx+8]
0x140001c67  push    rdx
0x140001c68  push    rax
0x140001c69  push    rcx
0x140001c6a  mov     rcx, [rax+10h]
0x140001c6e  call    cs:__guard_check_icall_fptr
0x140001c74  pop     rcx
0x140001c75  pop     rax
0x140001c76  pop     rdx
0x140001c77  jmp     qword ptr [rax+10h]
```
