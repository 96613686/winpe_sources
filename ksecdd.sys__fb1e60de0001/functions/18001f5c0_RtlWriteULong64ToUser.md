# RtlWriteULong64ToUser

- ea: `0x18001f5c0`
- end: `0x18001f600`
- name: `RtlWriteULong64ToUser`
- size: `64`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180005160`
- `0x18000c93c`
- `0x18000cbb4`
- `0x180012040`

## callees

- `0x180007a4f`
- `0x18001f5c0`

## pseudocode

```c
void __fastcall RtlWriteULong64ToUser(_QWORD *a1, __int64 a2)
{
  ProbeForRead_0(a1, 8u, 1u);
  *a1 = a2;
}

```

## disassembly

```asm
0x18001f5c0  mov     [rsp+arg_0], rbx
0x18001f5c5  push    rdi
0x18001f5c6  sub     rsp, 20h
0x18001f5ca  mov     rax, cs:qword_18001C500
0x18001f5d1  mov     rdi, rdx
0x18001f5d4  mov     rbx, rcx
0x18001f5d7  test    rax, rax
0x18001f5da  jz      short loc_18001F5E3
0x18001f5dc  call    rax ; qword_18001C500
0x18001f5de  nop     dword ptr [rax]
0x18001f5e1  jmp     short loc_18001F5F4
0x18001f5e3  mov     edx, 8; Length
0x18001f5e8  lea     r8d, [rdx-7]; Alignment
0x18001f5ec  call    ProbeForRead_0
0x18001f5f1  mov     [rbx], rdi
0x18001f5f4  mov     rbx, [rsp+28h+arg_0]
0x18001f5f9  add     rsp, 20h
0x18001f5fd  pop     rdi
0x18001f5fe  retn
```
