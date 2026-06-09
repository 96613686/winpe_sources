# __GSHandlerCheckCommon

- ea: `0x18001419c`
- end: `0x1800141ff`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014178`
- `0x180025db0`
- `0x180025e18`

## callees

- `0x180013b20`
- `0x18001419c`

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
0x18001419c  mov     r10, rcx
0x18001419f  mov     r11, rdx
0x1800141a2  mov     ecx, [r8]
0x1800141a5  and     ecx, 0FFFFFFF8h
0x1800141a8  test    byte ptr [r8], 4
0x1800141ac  jz      short loc_1800141C3
0x1800141ae  mov     eax, [r8+8]
0x1800141b2  movsxd  r9, dword ptr [r8+4]
0x1800141b6  neg     eax
0x1800141b8  movsxd  rdx, eax
0x1800141bb  add     r9, r10
0x1800141be  and     r9, rdx
0x1800141c1  jmp     short loc_1800141C6
0x1800141c3  mov     r9, r10
0x1800141c6  movsxd  rax, ecx
0x1800141c9  mov     rdx, [rax+r9]
0x1800141cd  mov     rax, [r11+10h]
0x1800141d1  mov     ecx, [rax+8]
0x1800141d4  mov     rax, [r11+8]
0x1800141d8  test    byte ptr [rcx+rax+3], 0Fh
0x1800141dd  jz      short loc_1800141F1
0x1800141df  movzx   eax, byte ptr [rcx+rax+3]
0x1800141e4  mov     ecx, 0FFFFFFF0h
0x1800141e9  and     rax, rcx
0x1800141ec  add     rax, r10
0x1800141ef  jmp     short loc_1800141F4
0x1800141f1  mov     rax, r10
0x1800141f4  xor     rdx, rax
0x1800141f7  mov     rcx, rdx; StackCookie
0x1800141fa  jmp     __security_check_cookie
```
