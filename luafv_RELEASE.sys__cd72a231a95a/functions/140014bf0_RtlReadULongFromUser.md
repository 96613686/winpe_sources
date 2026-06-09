# RtlReadULongFromUser

- ea: `0x140014bf0`
- end: `0x140014c23`
- name: `RtlReadULongFromUser`
- size: `51`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140007020`
- `0x140024050`

## callees

- `0x140002546`
- `0x140014bf0`

## pseudocode

```c
__int64 __fastcall RtlReadULongFromUser(unsigned int *a1)
{
  ProbeForRead_0(a1, 4u, 1u);
  return *a1;
}

```

## disassembly

```asm
0x140014bf0  push    rbx
0x140014bf2  sub     rsp, 20h
0x140014bf6  mov     rax, cs:qword_140012618
0x140014bfd  mov     rbx, rcx
0x140014c00  test    rax, rax
0x140014c03  jz      short loc_140014C0C
0x140014c05  call    rax ; qword_140012618
0x140014c07  nop     dword ptr [rax]
0x140014c0a  jmp     short loc_140014C1C
0x140014c0c  mov     edx, 4; Length
0x140014c11  lea     r8d, [rdx-3]; Alignment
0x140014c15  call    ProbeForRead_0
0x140014c1a  mov     eax, [rbx]
0x140014c1c  add     rsp, 20h
0x140014c20  pop     rbx
0x140014c21  retn
```
