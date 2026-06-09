# __GSHandlerCheckCommon

- ea: `0x18000431c`
- end: `0x18000437f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800042f8`
- `0x180004388`

## callees

- `0x18000431c`
- `0x180004420`

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
0x18000431c  mov     r10, rcx
0x18000431f  mov     r11, rdx
0x180004322  mov     ecx, [r8]
0x180004325  and     ecx, 0FFFFFFF8h
0x180004328  test    byte ptr [r8], 4
0x18000432c  jz      short loc_180004343
0x18000432e  mov     eax, [r8+8]
0x180004332  movsxd  r9, dword ptr [r8+4]
0x180004336  neg     eax
0x180004338  movsxd  rdx, eax
0x18000433b  add     r9, r10
0x18000433e  and     r9, rdx
0x180004341  jmp     short loc_180004346
0x180004343  mov     r9, r10
0x180004346  movsxd  rax, ecx
0x180004349  mov     rdx, [rax+r9]
0x18000434d  mov     rax, [r11+10h]
0x180004351  mov     ecx, [rax+8]
0x180004354  mov     rax, [r11+8]
0x180004358  test    byte ptr [rcx+rax+3], 0Fh
0x18000435d  jz      short loc_180004371
0x18000435f  movzx   eax, byte ptr [rcx+rax+3]
0x180004364  mov     ecx, 0FFFFFFF0h
0x180004369  and     rax, rcx
0x18000436c  add     rax, r10
0x18000436f  jmp     short loc_180004374
0x180004371  mov     rax, r10
0x180004374  xor     rdx, rax
0x180004377  mov     rcx, rdx; StackCookie
0x18000437a  jmp     __security_check_cookie
```
