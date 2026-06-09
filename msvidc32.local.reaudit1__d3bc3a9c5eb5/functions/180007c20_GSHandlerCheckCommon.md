# __GSHandlerCheckCommon

- ea: `0x180007c20`
- end: `0x180007c83`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007bfc`

## callees

- `0x180001400`
- `0x180007c20`

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
0x180007c20  mov     r10, rcx
0x180007c23  mov     r11, rdx
0x180007c26  mov     ecx, [r8]
0x180007c29  and     ecx, 0FFFFFFF8h
0x180007c2c  test    byte ptr [r8], 4
0x180007c30  jz      short loc_180007C47
0x180007c32  mov     eax, [r8+8]
0x180007c36  movsxd  r9, dword ptr [r8+4]
0x180007c3a  neg     eax
0x180007c3c  movsxd  rdx, eax
0x180007c3f  add     r9, r10
0x180007c42  and     r9, rdx
0x180007c45  jmp     short loc_180007C4A
0x180007c47  mov     r9, r10
0x180007c4a  movsxd  rax, ecx
0x180007c4d  mov     rdx, [rax+r9]
0x180007c51  mov     rax, [r11+10h]
0x180007c55  mov     ecx, [rax+8]
0x180007c58  mov     rax, [r11+8]
0x180007c5c  test    byte ptr [rcx+rax+3], 0Fh
0x180007c61  jz      short loc_180007C75
0x180007c63  movzx   eax, byte ptr [rcx+rax+3]
0x180007c68  mov     ecx, 0FFFFFFF0h
0x180007c6d  and     rax, rcx
0x180007c70  add     rax, r10
0x180007c73  jmp     short loc_180007C78
0x180007c75  mov     rax, r10
0x180007c78  xor     rdx, rax
0x180007c7b  mov     rcx, rdx; StackCookie
0x180007c7e  jmp     __security_check_cookie
```
