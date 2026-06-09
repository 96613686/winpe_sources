# __GSHandlerCheckCommon

- ea: `0x18001143c`
- end: `0x18001149f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011418`

## callees

- `0x18000e3a0`
- `0x18001143c`

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
0x18001143c  mov     r10, rcx
0x18001143f  mov     r11, rdx
0x180011442  mov     ecx, [r8]
0x180011445  and     ecx, 0FFFFFFF8h
0x180011448  test    byte ptr [r8], 4
0x18001144c  jz      short loc_180011463
0x18001144e  mov     eax, [r8+8]
0x180011452  movsxd  r9, dword ptr [r8+4]
0x180011456  neg     eax
0x180011458  movsxd  rdx, eax
0x18001145b  add     r9, r10
0x18001145e  and     r9, rdx
0x180011461  jmp     short loc_180011466
0x180011463  mov     r9, r10
0x180011466  movsxd  rax, ecx
0x180011469  mov     rdx, [rax+r9]
0x18001146d  mov     rax, [r11+10h]
0x180011471  mov     ecx, [rax+8]
0x180011474  mov     rax, [r11+8]
0x180011478  test    byte ptr [rcx+rax+3], 0Fh
0x18001147d  jz      short loc_180011491
0x18001147f  movzx   eax, byte ptr [rcx+rax+3]
0x180011484  mov     ecx, 0FFFFFFF0h
0x180011489  and     rax, rcx
0x18001148c  add     rax, r10
0x18001148f  jmp     short loc_180011494
0x180011491  mov     rax, r10
0x180011494  xor     rdx, rax
0x180011497  mov     rcx, rdx; StackCookie
0x18001149a  jmp     __security_check_cookie
```
