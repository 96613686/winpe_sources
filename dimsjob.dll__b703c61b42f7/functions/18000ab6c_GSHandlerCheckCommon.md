# __GSHandlerCheckCommon

- ea: `0x18000ab6c`
- end: `0x18000abcf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ab48`
- `0x18000abd8`
- `0x18000ac9c`

## callees

- `0x18000ab6c`
- `0x18000ad30`

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
0x18000ab6c  mov     r10, rcx
0x18000ab6f  mov     r11, rdx
0x18000ab72  mov     ecx, [r8]
0x18000ab75  and     ecx, 0FFFFFFF8h
0x18000ab78  test    byte ptr [r8], 4
0x18000ab7c  jz      short loc_18000AB93
0x18000ab7e  mov     eax, [r8+8]
0x18000ab82  movsxd  r9, dword ptr [r8+4]
0x18000ab86  neg     eax
0x18000ab88  movsxd  rdx, eax
0x18000ab8b  add     r9, r10
0x18000ab8e  and     r9, rdx
0x18000ab91  jmp     short loc_18000AB96
0x18000ab93  mov     r9, r10
0x18000ab96  movsxd  rax, ecx
0x18000ab99  mov     rdx, [rax+r9]
0x18000ab9d  mov     rax, [r11+10h]
0x18000aba1  mov     ecx, [rax+8]
0x18000aba4  mov     rax, [r11+8]
0x18000aba8  test    byte ptr [rcx+rax+3], 0Fh
0x18000abad  jz      short loc_18000ABC1
0x18000abaf  movzx   eax, byte ptr [rcx+rax+3]
0x18000abb4  mov     ecx, 0FFFFFFF0h
0x18000abb9  and     rax, rcx
0x18000abbc  add     rax, r10
0x18000abbf  jmp     short loc_18000ABC4
0x18000abc1  mov     rax, r10
0x18000abc4  xor     rdx, rax
0x18000abc7  mov     rcx, rdx; StackCookie
0x18000abca  jmp     __security_check_cookie
```
