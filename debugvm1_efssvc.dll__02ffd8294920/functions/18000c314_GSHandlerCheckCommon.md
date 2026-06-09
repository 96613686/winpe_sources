# __GSHandlerCheckCommon

- ea: `0x18000c314`
- end: `0x18000c377`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c2f0`

## callees

- `0x18000c314`
- `0x18000c3c0`

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
0x18000c314  mov     r10, rcx
0x18000c317  mov     r11, rdx
0x18000c31a  mov     ecx, [r8]
0x18000c31d  and     ecx, 0FFFFFFF8h
0x18000c320  test    byte ptr [r8], 4
0x18000c324  jz      short loc_18000C33B
0x18000c326  mov     eax, [r8+8]
0x18000c32a  movsxd  r9, dword ptr [r8+4]
0x18000c32e  neg     eax
0x18000c330  movsxd  rdx, eax
0x18000c333  add     r9, r10
0x18000c336  and     r9, rdx
0x18000c339  jmp     short loc_18000C33E
0x18000c33b  mov     r9, r10
0x18000c33e  movsxd  rax, ecx
0x18000c341  mov     rdx, [rax+r9]
0x18000c345  mov     rax, [r11+10h]
0x18000c349  mov     ecx, [rax+8]
0x18000c34c  mov     rax, [r11+8]
0x18000c350  test    byte ptr [rcx+rax+3], 0Fh
0x18000c355  jz      short loc_18000C369
0x18000c357  movzx   eax, byte ptr [rcx+rax+3]
0x18000c35c  mov     ecx, 0FFFFFFF0h
0x18000c361  and     rax, rcx
0x18000c364  add     rax, r10
0x18000c367  jmp     short loc_18000C36C
0x18000c369  mov     rax, r10
0x18000c36c  xor     rdx, rax
0x18000c36f  mov     rcx, rdx; StackCookie
0x18000c372  jmp     __security_check_cookie
```
