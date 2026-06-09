# __GSHandlerCheckCommon

- ea: `0x140005220`
- end: `0x140005283`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400051fc`

## callees

- `0x1400020c0`
- `0x140005220`

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
0x140005220  mov     r10, rcx
0x140005223  mov     r11, rdx
0x140005226  mov     ecx, [r8]
0x140005229  and     ecx, 0FFFFFFF8h
0x14000522c  test    byte ptr [r8], 4
0x140005230  jz      short loc_140005247
0x140005232  mov     eax, [r8+8]
0x140005236  movsxd  r9, dword ptr [r8+4]
0x14000523a  neg     eax
0x14000523c  movsxd  rdx, eax
0x14000523f  add     r9, r10
0x140005242  and     r9, rdx
0x140005245  jmp     short loc_14000524A
0x140005247  mov     r9, r10
0x14000524a  movsxd  rax, ecx
0x14000524d  mov     rdx, [rax+r9]
0x140005251  mov     rax, [r11+10h]
0x140005255  mov     ecx, [rax+8]
0x140005258  mov     rax, [r11+8]
0x14000525c  test    byte ptr [rcx+rax+3], 0Fh
0x140005261  jz      short loc_140005275
0x140005263  movzx   eax, byte ptr [rcx+rax+3]
0x140005268  mov     ecx, 0FFFFFFF0h
0x14000526d  and     rax, rcx
0x140005270  add     rax, r10
0x140005273  jmp     short loc_140005278
0x140005275  mov     rax, r10
0x140005278  xor     rdx, rax
0x14000527b  mov     rcx, rdx; StackCookie
0x14000527e  jmp     __security_check_cookie
```
