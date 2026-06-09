# __GSHandlerCheckCommon

- ea: `0x18001b5b0`
- end: `0x18001b613`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b58c`

## callees

- `0x180014dc0`
- `0x18001b5b0`

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
0x18001b5b0  mov     r10, rcx
0x18001b5b3  mov     r11, rdx
0x18001b5b6  mov     ecx, [r8]
0x18001b5b9  and     ecx, 0FFFFFFF8h
0x18001b5bc  test    byte ptr [r8], 4
0x18001b5c0  jz      short loc_18001B5D7
0x18001b5c2  mov     eax, [r8+8]
0x18001b5c6  movsxd  r9, dword ptr [r8+4]
0x18001b5ca  neg     eax
0x18001b5cc  movsxd  rdx, eax
0x18001b5cf  add     r9, r10
0x18001b5d2  and     r9, rdx
0x18001b5d5  jmp     short loc_18001B5DA
0x18001b5d7  mov     r9, r10
0x18001b5da  movsxd  rax, ecx
0x18001b5dd  mov     rdx, [rax+r9]
0x18001b5e1  mov     rax, [r11+10h]
0x18001b5e5  mov     ecx, [rax+8]
0x18001b5e8  mov     rax, [r11+8]
0x18001b5ec  test    byte ptr [rcx+rax+3], 0Fh
0x18001b5f1  jz      short loc_18001B605
0x18001b5f3  movzx   eax, byte ptr [rcx+rax+3]
0x18001b5f8  mov     ecx, 0FFFFFFF0h
0x18001b5fd  and     rax, rcx
0x18001b600  add     rax, r10
0x18001b603  jmp     short loc_18001B608
0x18001b605  mov     rax, r10
0x18001b608  xor     rdx, rax
0x18001b60b  mov     rcx, rdx; StackCookie
0x18001b60e  jmp     __security_check_cookie
```
