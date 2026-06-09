# __GSHandlerCheckCommon

- ea: `0x1800084d0`
- end: `0x180008533`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800084ac`

## callees

- `0x1800084d0`
- `0x180008580`

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
0x1800084d0  mov     r10, rcx
0x1800084d3  mov     r11, rdx
0x1800084d6  mov     ecx, [r8]
0x1800084d9  and     ecx, 0FFFFFFF8h
0x1800084dc  test    byte ptr [r8], 4
0x1800084e0  jz      short loc_1800084F7
0x1800084e2  mov     eax, [r8+8]
0x1800084e6  movsxd  r9, dword ptr [r8+4]
0x1800084ea  neg     eax
0x1800084ec  movsxd  rdx, eax
0x1800084ef  add     r9, r10
0x1800084f2  and     r9, rdx
0x1800084f5  jmp     short loc_1800084FA
0x1800084f7  mov     r9, r10
0x1800084fa  movsxd  rax, ecx
0x1800084fd  mov     rdx, [rax+r9]
0x180008501  mov     rax, [r11+10h]
0x180008505  mov     ecx, [rax+8]
0x180008508  mov     rax, [r11+8]
0x18000850c  test    byte ptr [rcx+rax+3], 0Fh
0x180008511  jz      short loc_180008525
0x180008513  movzx   eax, byte ptr [rcx+rax+3]
0x180008518  mov     ecx, 0FFFFFFF0h
0x18000851d  and     rax, rcx
0x180008520  add     rax, r10
0x180008523  jmp     short loc_180008528
0x180008525  mov     rax, r10
0x180008528  xor     rdx, rax
0x18000852b  mov     rcx, rdx; StackCookie
0x18000852e  jmp     __security_check_cookie
```
