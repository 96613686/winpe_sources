# __GSHandlerCheckCommon

- ea: `0x1800026cc`
- end: `0x18000272f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800026a8`

## callees

- `0x1800026cc`
- `0x180002760`

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
0x1800026cc  mov     r10, rcx
0x1800026cf  mov     r11, rdx
0x1800026d2  mov     ecx, [r8]
0x1800026d5  and     ecx, 0FFFFFFF8h
0x1800026d8  test    byte ptr [r8], 4
0x1800026dc  jz      short loc_1800026F3
0x1800026de  mov     eax, [r8+8]
0x1800026e2  movsxd  r9, dword ptr [r8+4]
0x1800026e6  neg     eax
0x1800026e8  movsxd  rdx, eax
0x1800026eb  add     r9, r10
0x1800026ee  and     r9, rdx
0x1800026f1  jmp     short loc_1800026F6
0x1800026f3  mov     r9, r10
0x1800026f6  movsxd  rax, ecx
0x1800026f9  mov     rdx, [rax+r9]
0x1800026fd  mov     rax, [r11+10h]
0x180002701  mov     ecx, [rax+8]
0x180002704  mov     rax, [r11+8]
0x180002708  test    byte ptr [rcx+rax+3], 0Fh
0x18000270d  jz      short loc_180002721
0x18000270f  movzx   eax, byte ptr [rcx+rax+3]
0x180002714  mov     ecx, 0FFFFFFF0h
0x180002719  and     rax, rcx
0x18000271c  add     rax, r10
0x18000271f  jmp     short loc_180002724
0x180002721  mov     rax, r10
0x180002724  xor     rdx, rax
0x180002727  mov     rcx, rdx; StackCookie
0x18000272a  jmp     __security_check_cookie
```
