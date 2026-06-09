# __GSHandlerCheckCommon

- ea: `0x180003458`
- end: `0x1800034bb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003434`
- `0x1800034c4`
- `0x18002f028`

## callees

- `0x180003458`
- `0x18002f0e0`

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
0x180003458  mov     r10, rcx
0x18000345b  mov     r11, rdx
0x18000345e  mov     ecx, [r8]
0x180003461  and     ecx, 0FFFFFFF8h
0x180003464  test    byte ptr [r8], 4
0x180003468  jz      short loc_18000347F
0x18000346a  mov     eax, [r8+8]
0x18000346e  movsxd  r9, dword ptr [r8+4]
0x180003472  neg     eax
0x180003474  movsxd  rdx, eax
0x180003477  add     r9, r10
0x18000347a  and     r9, rdx
0x18000347d  jmp     short loc_180003482
0x18000347f  mov     r9, r10
0x180003482  movsxd  rax, ecx
0x180003485  mov     rdx, [rax+r9]
0x180003489  mov     rax, [r11+10h]
0x18000348d  mov     ecx, [rax+8]
0x180003490  mov     rax, [r11+8]
0x180003494  test    byte ptr [rcx+rax+3], 0Fh
0x180003499  jz      short loc_1800034AD
0x18000349b  movzx   eax, byte ptr [rcx+rax+3]
0x1800034a0  mov     ecx, 0FFFFFFF0h
0x1800034a5  and     rax, rcx
0x1800034a8  add     rax, r10
0x1800034ab  jmp     short loc_1800034B0
0x1800034ad  mov     rax, r10
0x1800034b0  xor     rdx, rax
0x1800034b3  mov     rcx, rdx; StackCookie
0x1800034b6  jmp     __security_check_cookie
```
