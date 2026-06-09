# __GSHandlerCheckCommon

- ea: `0x180002d20`
- end: `0x180002d83`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002cfc`

## callees

- `0x180002d20`
- `0x180002de0`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax

  v3 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  v4 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v3 + v4 + 3) & 0xF) != 0 )
    return a1 + (*(_BYTE *)(v3 + v4 + 3) & 0xF0);
  else
    return a1;
}

```

## disassembly

```asm
0x180002d20  mov     r10, rcx
0x180002d23  mov     r11, rdx
0x180002d26  mov     ecx, [r8]
0x180002d29  and     ecx, 0FFFFFFF8h
0x180002d2c  test    byte ptr [r8], 4
0x180002d30  jz      short loc_180002D47
0x180002d32  mov     eax, [r8+8]
0x180002d36  movsxd  r9, dword ptr [r8+4]
0x180002d3a  neg     eax
0x180002d3c  movsxd  rdx, eax
0x180002d3f  add     r9, r10
0x180002d42  and     r9, rdx
0x180002d45  jmp     short loc_180002D4A
0x180002d47  mov     r9, r10
0x180002d4a  movsxd  rax, ecx
0x180002d4d  mov     rdx, [rax+r9]
0x180002d51  mov     rax, [r11+10h]
0x180002d55  mov     ecx, [rax+8]
0x180002d58  mov     rax, [r11+8]
0x180002d5c  test    byte ptr [rcx+rax+3], 0Fh
0x180002d61  jz      short loc_180002D75
0x180002d63  movzx   eax, byte ptr [rcx+rax+3]
0x180002d68  mov     ecx, 0FFFFFFF0h
0x180002d6d  and     rax, rcx
0x180002d70  add     rax, r10
0x180002d73  jmp     short loc_180002D78
0x180002d75  mov     rax, r10
0x180002d78  xor     rdx, rax
0x180002d7b  mov     rcx, rdx; StackCookie
0x180002d7e  jmp     __security_check_cookie
```
