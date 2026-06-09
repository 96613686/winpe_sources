# RtlReadULongFromUser

- ea: `0x14000e06c`
- end: `0x14000e09f`
- name: `RtlReadULongFromUser`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140007030`
- `0x140012290`

## callees

- `0x140002b06`
- `0x14000e06c`

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
0x14000e06c  push    rbx
0x14000e06e  sub     rsp, 20h
0x14000e072  mov     rax, cs:qword_14000C468
0x14000e079  mov     rbx, rcx
0x14000e07c  test    rax, rax
0x14000e07f  jz      short loc_14000E088
0x14000e081  call    rax ; qword_14000C468
0x14000e083  nop     dword ptr [rax]
0x14000e086  jmp     short loc_14000E098
0x14000e088  mov     edx, 4; Length
0x14000e08d  lea     r8d, [rdx-3]; Alignment
0x14000e091  call    ProbeForRead_0
0x14000e096  mov     eax, [rbx]
0x14000e098  add     rsp, 20h
0x14000e09c  pop     rbx
0x14000e09d  retn
```
