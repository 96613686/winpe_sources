# __GSHandlerCheckCommon

- ea: `0x1800064f4`
- end: `0x180006557`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800064d0`

## callees

- `0x180001460`
- `0x1800064f4`

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
0x1800064f4  mov     r10, rcx
0x1800064f7  mov     r11, rdx
0x1800064fa  mov     ecx, [r8]
0x1800064fd  and     ecx, 0FFFFFFF8h
0x180006500  test    byte ptr [r8], 4
0x180006504  jz      short loc_18000651B
0x180006506  mov     eax, [r8+8]
0x18000650a  movsxd  r9, dword ptr [r8+4]
0x18000650e  neg     eax
0x180006510  movsxd  rdx, eax
0x180006513  add     r9, r10
0x180006516  and     r9, rdx
0x180006519  jmp     short loc_18000651E
0x18000651b  mov     r9, r10
0x18000651e  movsxd  rax, ecx
0x180006521  mov     rdx, [rax+r9]
0x180006525  mov     rax, [r11+10h]
0x180006529  mov     ecx, [rax+8]
0x18000652c  mov     rax, [r11+8]
0x180006530  test    byte ptr [rcx+rax+3], 0Fh
0x180006535  jz      short loc_180006549
0x180006537  movzx   eax, byte ptr [rcx+rax+3]
0x18000653c  mov     ecx, 0FFFFFFF0h
0x180006541  and     rax, rcx
0x180006544  add     rax, r10
0x180006547  jmp     short loc_18000654C
0x180006549  mov     rax, r10
0x18000654c  xor     rdx, rax
0x18000654f  mov     rcx, rdx; StackCookie
0x180006552  jmp     __security_check_cookie
```
