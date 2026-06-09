# __GSHandlerCheckCommon

- ea: `0x1400031d0`
- end: `0x140003233`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400031ac`

## callees

- `0x140001380`
- `0x1400031d0`

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
0x1400031d0  mov     r10, rcx
0x1400031d3  mov     r11, rdx
0x1400031d6  mov     ecx, [r8]
0x1400031d9  and     ecx, 0FFFFFFF8h
0x1400031dc  test    byte ptr [r8], 4
0x1400031e0  jz      short loc_1400031F7
0x1400031e2  mov     eax, [r8+8]
0x1400031e6  movsxd  r9, dword ptr [r8+4]
0x1400031ea  neg     eax
0x1400031ec  movsxd  rdx, eax
0x1400031ef  add     r9, r10
0x1400031f2  and     r9, rdx
0x1400031f5  jmp     short loc_1400031FA
0x1400031f7  mov     r9, r10
0x1400031fa  movsxd  rax, ecx
0x1400031fd  mov     rdx, [rax+r9]
0x140003201  mov     rax, [r11+10h]
0x140003205  mov     ecx, [rax+8]
0x140003208  mov     rax, [r11+8]
0x14000320c  test    byte ptr [rcx+rax+3], 0Fh
0x140003211  jz      short loc_140003225
0x140003213  movzx   eax, byte ptr [rcx+rax+3]
0x140003218  mov     ecx, 0FFFFFFF0h
0x14000321d  and     rax, rcx
0x140003220  add     rax, r10
0x140003223  jmp     short loc_140003228
0x140003225  mov     rax, r10
0x140003228  xor     rdx, rax
0x14000322b  mov     rcx, rdx; StackCookie
0x14000322e  jmp     __security_check_cookie
```
