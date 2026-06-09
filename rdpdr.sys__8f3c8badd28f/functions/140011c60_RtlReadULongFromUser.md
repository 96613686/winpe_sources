# RtlReadULongFromUser

- ea: `0x140011c60`
- end: `0x140011c93`
- name: `RtlReadULongFromUser`
- size: `51`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140007030`
- `0x140019220`
- `0x140019720`
- `0x140019aa4`
- `0x14001a59c`

## callees

- `0x140003051`
- `0x140011c60`

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
0x140011c60  push    rbx
0x140011c62  sub     rsp, 20h
0x140011c66  mov     rax, cs:qword_14000F5B8
0x140011c6d  mov     rbx, rcx
0x140011c70  test    rax, rax
0x140011c73  jz      short loc_140011C7C
0x140011c75  call    rax ; qword_14000F5B8
0x140011c77  nop     dword ptr [rax]
0x140011c7a  jmp     short loc_140011C8C
0x140011c7c  mov     edx, 4; Length
0x140011c81  lea     r8d, [rdx-3]; Alignment
0x140011c85  call    ProbeForRead_0
0x140011c8a  mov     eax, [rbx]
0x140011c8c  add     rsp, 20h
0x140011c90  pop     rbx
0x140011c91  retn
```
