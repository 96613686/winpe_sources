# __GSHandlerCheckCommon

- ea: `0x1800190b8`
- end: `0x18001911b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019094`
- `0x180019124`

## callees

- `0x1800190b8`
- `0x1800191f0`

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
0x1800190b8  mov     r10, rcx
0x1800190bb  mov     r11, rdx
0x1800190be  mov     ecx, [r8]
0x1800190c1  and     ecx, 0FFFFFFF8h
0x1800190c4  test    byte ptr [r8], 4
0x1800190c8  jz      short loc_1800190DF
0x1800190ca  mov     eax, [r8+8]
0x1800190ce  movsxd  r9, dword ptr [r8+4]
0x1800190d2  neg     eax
0x1800190d4  movsxd  rdx, eax
0x1800190d7  add     r9, r10
0x1800190da  and     r9, rdx
0x1800190dd  jmp     short loc_1800190E2
0x1800190df  mov     r9, r10
0x1800190e2  movsxd  rax, ecx
0x1800190e5  mov     rdx, [rax+r9]
0x1800190e9  mov     rax, [r11+10h]
0x1800190ed  mov     ecx, [rax+8]
0x1800190f0  mov     rax, [r11+8]
0x1800190f4  test    byte ptr [rcx+rax+3], 0Fh
0x1800190f9  jz      short loc_18001910D
0x1800190fb  movzx   eax, byte ptr [rcx+rax+3]
0x180019100  mov     ecx, 0FFFFFFF0h
0x180019105  and     rax, rcx
0x180019108  add     rax, r10
0x18001910b  jmp     short loc_180019110
0x18001910d  mov     rax, r10
0x180019110  xor     rdx, rax
0x180019113  mov     rcx, rdx; StackCookie
0x180019116  jmp     __security_check_cookie
```
