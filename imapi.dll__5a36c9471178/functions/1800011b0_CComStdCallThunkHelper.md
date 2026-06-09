# CComStdCallThunkHelper

- ea: `0x1800011b0`
- end: `0x1800011ca`
- name: `CComStdCallThunkHelper`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003260`

## pseudocode

```c
__int64 __fastcall CComStdCallThunkHelper(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(_QWORD, __int64))(a1 + 16))(*(_QWORD *)(a1 + 8), a2);
}

```

## disassembly

```asm
0x1800011b0  mov     rax, rcx
0x1800011b3  mov     rcx, [rcx+8]
0x1800011b7  push    rdx
0x1800011b8  push    rax
0x1800011b9  push    rcx
0x1800011ba  mov     rcx, [rax+10h]
0x1800011be  call    cs:__guard_check_icall_fptr
0x1800011c4  pop     rcx
0x1800011c5  pop     rax
0x1800011c6  pop     rdx
0x1800011c7  jmp     qword ptr [rax+10h]
```
