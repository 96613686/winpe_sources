# __GSHandlerCheckCommon

- ea: `0x1400112d0`
- end: `0x140011333`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400112ac`
- `0x14001133c`

## callees

- `0x1400022a0`
- `0x1400112d0`

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
0x1400112d0  mov     r10, rcx
0x1400112d3  mov     r11, rdx
0x1400112d6  mov     ecx, [r8]
0x1400112d9  and     ecx, 0FFFFFFF8h
0x1400112dc  test    byte ptr [r8], 4
0x1400112e0  jz      short loc_1400112F7
0x1400112e2  mov     eax, [r8+8]
0x1400112e6  movsxd  r9, dword ptr [r8+4]
0x1400112ea  neg     eax
0x1400112ec  movsxd  rdx, eax
0x1400112ef  add     r9, r10
0x1400112f2  and     r9, rdx
0x1400112f5  jmp     short loc_1400112FA
0x1400112f7  mov     r9, r10
0x1400112fa  movsxd  rax, ecx
0x1400112fd  mov     rdx, [rax+r9]
0x140011301  mov     rax, [r11+10h]
0x140011305  mov     ecx, [rax+8]
0x140011308  mov     rax, [r11+8]
0x14001130c  test    byte ptr [rcx+rax+3], 0Fh
0x140011311  jz      short loc_140011325
0x140011313  movzx   eax, byte ptr [rcx+rax+3]
0x140011318  mov     ecx, 0FFFFFFF0h
0x14001131d  and     rax, rcx
0x140011320  add     rax, r10
0x140011323  jmp     short loc_140011328
0x140011325  mov     rax, r10
0x140011328  xor     rdx, rax
0x14001132b  mov     rcx, rdx; StackCookie
0x14001132e  jmp     __security_check_cookie
```
