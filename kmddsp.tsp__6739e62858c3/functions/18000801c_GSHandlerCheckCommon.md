# __GSHandlerCheckCommon

- ea: `0x18000801c`
- end: `0x18000807f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007ff8`

## callees

- `0x180001400`
- `0x18000801c`

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
0x18000801c  mov     r10, rcx
0x18000801f  mov     r11, rdx
0x180008022  mov     ecx, [r8]
0x180008025  and     ecx, 0FFFFFFF8h
0x180008028  test    byte ptr [r8], 4
0x18000802c  jz      short loc_180008043
0x18000802e  mov     eax, [r8+8]
0x180008032  movsxd  r9, dword ptr [r8+4]
0x180008036  neg     eax
0x180008038  movsxd  rdx, eax
0x18000803b  add     r9, r10
0x18000803e  and     r9, rdx
0x180008041  jmp     short loc_180008046
0x180008043  mov     r9, r10
0x180008046  movsxd  rax, ecx
0x180008049  mov     rdx, [rax+r9]
0x18000804d  mov     rax, [r11+10h]
0x180008051  mov     ecx, [rax+8]
0x180008054  mov     rax, [r11+8]
0x180008058  test    byte ptr [rcx+rax+3], 0Fh
0x18000805d  jz      short loc_180008071
0x18000805f  movzx   eax, byte ptr [rcx+rax+3]
0x180008064  mov     ecx, 0FFFFFFF0h
0x180008069  and     rax, rcx
0x18000806c  add     rax, r10
0x18000806f  jmp     short loc_180008074
0x180008071  mov     rax, r10
0x180008074  xor     rdx, rax
0x180008077  mov     rcx, rdx; StackCookie
0x18000807a  jmp     __security_check_cookie
```
