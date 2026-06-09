# __GSHandlerCheckCommon

- ea: `0x18000c2c0`
- end: `0x18000c323`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c29c`
- `0x1800139d4`

## callees

- `0x18000b410`
- `0x18000c2c0`

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
0x18000c2c0  mov     r10, rcx
0x18000c2c3  mov     r11, rdx
0x18000c2c6  mov     ecx, [r8]
0x18000c2c9  and     ecx, 0FFFFFFF8h
0x18000c2cc  test    byte ptr [r8], 4
0x18000c2d0  jz      short loc_18000C2E7
0x18000c2d2  mov     eax, [r8+8]
0x18000c2d6  movsxd  r9, dword ptr [r8+4]
0x18000c2da  neg     eax
0x18000c2dc  movsxd  rdx, eax
0x18000c2df  add     r9, r10
0x18000c2e2  and     r9, rdx
0x18000c2e5  jmp     short loc_18000C2EA
0x18000c2e7  mov     r9, r10
0x18000c2ea  movsxd  rax, ecx
0x18000c2ed  mov     rdx, [rax+r9]
0x18000c2f1  mov     rax, [r11+10h]
0x18000c2f5  mov     ecx, [rax+8]
0x18000c2f8  mov     rax, [r11+8]
0x18000c2fc  test    byte ptr [rcx+rax+3], 0Fh
0x18000c301  jz      short loc_18000C315
0x18000c303  movzx   eax, byte ptr [rcx+rax+3]
0x18000c308  mov     ecx, 0FFFFFFF0h
0x18000c30d  and     rax, rcx
0x18000c310  add     rax, r10
0x18000c313  jmp     short loc_18000C318
0x18000c315  mov     rax, r10
0x18000c318  xor     rdx, rax
0x18000c31b  mov     rcx, rdx; StackCookie
0x18000c31e  jmp     __security_check_cookie
```
