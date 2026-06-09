# __GSHandlerCheckCommon

- ea: `0x18001b3d0`
- end: `0x18001b433`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b3ac`
- `0x18001b43c`
- `0x18001b4a4`

## callees

- `0x18001b3d0`
- `0x18001b550`

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
0x18001b3d0  mov     r10, rcx
0x18001b3d3  mov     r11, rdx
0x18001b3d6  mov     ecx, [r8]
0x18001b3d9  and     ecx, 0FFFFFFF8h
0x18001b3dc  test    byte ptr [r8], 4
0x18001b3e0  jz      short loc_18001B3F7
0x18001b3e2  mov     eax, [r8+8]
0x18001b3e6  movsxd  r9, dword ptr [r8+4]
0x18001b3ea  neg     eax
0x18001b3ec  movsxd  rdx, eax
0x18001b3ef  add     r9, r10
0x18001b3f2  and     r9, rdx
0x18001b3f5  jmp     short loc_18001B3FA
0x18001b3f7  mov     r9, r10
0x18001b3fa  movsxd  rax, ecx
0x18001b3fd  mov     rdx, [rax+r9]
0x18001b401  mov     rax, [r11+10h]
0x18001b405  mov     ecx, [rax+8]
0x18001b408  mov     rax, [r11+8]
0x18001b40c  test    byte ptr [rcx+rax+3], 0Fh
0x18001b411  jz      short loc_18001B425
0x18001b413  movzx   eax, byte ptr [rcx+rax+3]
0x18001b418  mov     ecx, 0FFFFFFF0h
0x18001b41d  and     rax, rcx
0x18001b420  add     rax, r10
0x18001b423  jmp     short loc_18001B428
0x18001b425  mov     rax, r10
0x18001b428  xor     rdx, rax
0x18001b42b  mov     rcx, rdx; StackCookie
0x18001b42e  jmp     __security_check_cookie
```
