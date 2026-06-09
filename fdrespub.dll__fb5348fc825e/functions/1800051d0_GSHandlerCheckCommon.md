# __GSHandlerCheckCommon

- ea: `0x1800051d0`
- end: `0x180005233`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800051ac`

## callees

- `0x1800051d0`
- `0x180005270`

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
0x1800051d0  mov     r10, rcx
0x1800051d3  mov     r11, rdx
0x1800051d6  mov     ecx, [r8]
0x1800051d9  and     ecx, 0FFFFFFF8h
0x1800051dc  test    byte ptr [r8], 4
0x1800051e0  jz      short loc_1800051F7
0x1800051e2  mov     eax, [r8+8]
0x1800051e6  movsxd  r9, dword ptr [r8+4]
0x1800051ea  neg     eax
0x1800051ec  movsxd  rdx, eax
0x1800051ef  add     r9, r10
0x1800051f2  and     r9, rdx
0x1800051f5  jmp     short loc_1800051FA
0x1800051f7  mov     r9, r10
0x1800051fa  movsxd  rax, ecx
0x1800051fd  mov     rdx, [rax+r9]
0x180005201  mov     rax, [r11+10h]
0x180005205  mov     ecx, [rax+8]
0x180005208  mov     rax, [r11+8]
0x18000520c  test    byte ptr [rcx+rax+3], 0Fh
0x180005211  jz      short loc_180005225
0x180005213  movzx   eax, byte ptr [rcx+rax+3]
0x180005218  mov     ecx, 0FFFFFFF0h
0x18000521d  and     rax, rcx
0x180005220  add     rax, r10
0x180005223  jmp     short loc_180005228
0x180005225  mov     rax, r10
0x180005228  xor     rdx, rax
0x18000522b  mov     rcx, rdx; StackCookie
0x18000522e  jmp     __security_check_cookie
```
