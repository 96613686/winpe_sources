# __GSHandlerCheckCommon

- ea: `0x180014cd8`
- end: `0x180014d3b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014cb4`
- `0x180014d44`

## callees

- `0x180014cd8`
- `0x180014e00`

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
0x180014cd8  mov     r10, rcx
0x180014cdb  mov     r11, rdx
0x180014cde  mov     ecx, [r8]
0x180014ce1  and     ecx, 0FFFFFFF8h
0x180014ce4  test    byte ptr [r8], 4
0x180014ce8  jz      short loc_180014CFF
0x180014cea  mov     eax, [r8+8]
0x180014cee  movsxd  r9, dword ptr [r8+4]
0x180014cf2  neg     eax
0x180014cf4  movsxd  rdx, eax
0x180014cf7  add     r9, r10
0x180014cfa  and     r9, rdx
0x180014cfd  jmp     short loc_180014D02
0x180014cff  mov     r9, r10
0x180014d02  movsxd  rax, ecx
0x180014d05  mov     rdx, [rax+r9]
0x180014d09  mov     rax, [r11+10h]
0x180014d0d  mov     ecx, [rax+8]
0x180014d10  mov     rax, [r11+8]
0x180014d14  test    byte ptr [rcx+rax+3], 0Fh
0x180014d19  jz      short loc_180014D2D
0x180014d1b  movzx   eax, byte ptr [rcx+rax+3]
0x180014d20  mov     ecx, 0FFFFFFF0h
0x180014d25  and     rax, rcx
0x180014d28  add     rax, r10
0x180014d2b  jmp     short loc_180014D30
0x180014d2d  mov     rax, r10
0x180014d30  xor     rdx, rax
0x180014d33  mov     rcx, rdx; StackCookie
0x180014d36  jmp     __security_check_cookie
```
