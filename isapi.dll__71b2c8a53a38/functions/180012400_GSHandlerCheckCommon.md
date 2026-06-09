# __GSHandlerCheckCommon

- ea: `0x180012400`
- end: `0x180012463`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800123dc`

## callees

- `0x180012400`
- `0x1800124c0`

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
0x180012400  mov     r10, rcx
0x180012403  mov     r11, rdx
0x180012406  mov     ecx, [r8]
0x180012409  and     ecx, 0FFFFFFF8h
0x18001240c  test    byte ptr [r8], 4
0x180012410  jz      short loc_180012427
0x180012412  mov     eax, [r8+8]
0x180012416  movsxd  r9, dword ptr [r8+4]
0x18001241a  neg     eax
0x18001241c  movsxd  rdx, eax
0x18001241f  add     r9, r10
0x180012422  and     r9, rdx
0x180012425  jmp     short loc_18001242A
0x180012427  mov     r9, r10
0x18001242a  movsxd  rax, ecx
0x18001242d  mov     rdx, [rax+r9]
0x180012431  mov     rax, [r11+10h]
0x180012435  mov     ecx, [rax+8]
0x180012438  mov     rax, [r11+8]
0x18001243c  test    byte ptr [rcx+rax+3], 0Fh
0x180012441  jz      short loc_180012455
0x180012443  movzx   eax, byte ptr [rcx+rax+3]
0x180012448  mov     ecx, 0FFFFFFF0h
0x18001244d  and     rax, rcx
0x180012450  add     rax, r10
0x180012453  jmp     short loc_180012458
0x180012455  mov     rax, r10
0x180012458  xor     rdx, rax
0x18001245b  mov     rcx, rdx; StackCookie
0x18001245e  jmp     __security_check_cookie
```
