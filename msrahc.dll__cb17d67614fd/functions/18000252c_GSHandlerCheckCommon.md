# __GSHandlerCheckCommon

- ea: `0x18000252c`
- end: `0x18000258f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002508`
- `0x18001a528`

## callees

- `0x18000252c`
- `0x18001a5e0`

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
0x18000252c  mov     r10, rcx
0x18000252f  mov     r11, rdx
0x180002532  mov     ecx, [r8]
0x180002535  and     ecx, 0FFFFFFF8h
0x180002538  test    byte ptr [r8], 4
0x18000253c  jz      short loc_180002553
0x18000253e  mov     eax, [r8+8]
0x180002542  movsxd  r9, dword ptr [r8+4]
0x180002546  neg     eax
0x180002548  movsxd  rdx, eax
0x18000254b  add     r9, r10
0x18000254e  and     r9, rdx
0x180002551  jmp     short loc_180002556
0x180002553  mov     r9, r10
0x180002556  movsxd  rax, ecx
0x180002559  mov     rdx, [rax+r9]
0x18000255d  mov     rax, [r11+10h]
0x180002561  mov     ecx, [rax+8]
0x180002564  mov     rax, [r11+8]
0x180002568  test    byte ptr [rcx+rax+3], 0Fh
0x18000256d  jz      short loc_180002581
0x18000256f  movzx   eax, byte ptr [rcx+rax+3]
0x180002574  mov     ecx, 0FFFFFFF0h
0x180002579  and     rax, rcx
0x18000257c  add     rax, r10
0x18000257f  jmp     short loc_180002584
0x180002581  mov     rax, r10
0x180002584  xor     rdx, rax
0x180002587  mov     rcx, rdx; StackCookie
0x18000258a  jmp     __security_check_cookie
```
