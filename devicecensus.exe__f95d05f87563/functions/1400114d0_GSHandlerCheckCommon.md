# __GSHandlerCheckCommon

- ea: `0x1400114d0`
- end: `0x140011533`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400114ac`
- `0x14001153c`

## callees

- `0x1400114d0`
- `0x1400115f0`

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
0x1400114d0  mov     r10, rcx
0x1400114d3  mov     r11, rdx
0x1400114d6  mov     ecx, [r8]
0x1400114d9  and     ecx, 0FFFFFFF8h
0x1400114dc  test    byte ptr [r8], 4
0x1400114e0  jz      short loc_1400114F7
0x1400114e2  mov     eax, [r8+8]
0x1400114e6  movsxd  r9, dword ptr [r8+4]
0x1400114ea  neg     eax
0x1400114ec  movsxd  rdx, eax
0x1400114ef  add     r9, r10
0x1400114f2  and     r9, rdx
0x1400114f5  jmp     short loc_1400114FA
0x1400114f7  mov     r9, r10
0x1400114fa  movsxd  rax, ecx
0x1400114fd  mov     rdx, [rax+r9]
0x140011501  mov     rax, [r11+10h]
0x140011505  mov     ecx, [rax+8]
0x140011508  mov     rax, [r11+8]
0x14001150c  test    byte ptr [rcx+rax+3], 0Fh
0x140011511  jz      short loc_140011525
0x140011513  movzx   eax, byte ptr [rcx+rax+3]
0x140011518  mov     ecx, 0FFFFFFF0h
0x14001151d  and     rax, rcx
0x140011520  add     rax, r10
0x140011523  jmp     short loc_140011528
0x140011525  mov     rax, r10
0x140011528  xor     rdx, rax
0x14001152b  mov     rcx, rdx; StackCookie
0x14001152e  jmp     __security_check_cookie
```
