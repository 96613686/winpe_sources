# CComStdCallThunkHelper

- ea: `0x180001170`
- end: `0x18000118a`
- name: `CComStdCallThunkHelper`
- size: `26`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003cd0`

## pseudocode

```c
__int64 __fastcall CComStdCallThunkHelper(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(_QWORD, __int64))(a1 + 16))(*(_QWORD *)(a1 + 8), a2);
}

```

## disassembly

```asm
0x180001170  mov     rax, rcx
0x180001173  mov     rcx, [rcx+8]
0x180001177  push    rdx
0x180001178  push    rax
0x180001179  push    rcx
0x18000117a  mov     rcx, [rax+10h]
0x18000117e  call    cs:__guard_check_icall_fptr
0x180001184  pop     rcx
0x180001185  pop     rax
0x180001186  pop     rdx
0x180001187  jmp     qword ptr [rax+10h]
```
