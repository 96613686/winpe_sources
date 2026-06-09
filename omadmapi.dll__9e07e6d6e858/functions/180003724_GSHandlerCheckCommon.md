# __GSHandlerCheckCommon

- ea: `0x180003724`
- end: `0x180003787`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003700`
- `0x180022928`

## callees

- `0x1800031b0`
- `0x180003724`

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
0x180003724  mov     r10, rcx
0x180003727  mov     r11, rdx
0x18000372a  mov     ecx, [r8]
0x18000372d  and     ecx, 0FFFFFFF8h
0x180003730  test    byte ptr [r8], 4
0x180003734  jz      short loc_18000374B
0x180003736  mov     eax, [r8+8]
0x18000373a  movsxd  r9, dword ptr [r8+4]
0x18000373e  neg     eax
0x180003740  movsxd  rdx, eax
0x180003743  add     r9, r10
0x180003746  and     r9, rdx
0x180003749  jmp     short loc_18000374E
0x18000374b  mov     r9, r10
0x18000374e  movsxd  rax, ecx
0x180003751  mov     rdx, [rax+r9]
0x180003755  mov     rax, [r11+10h]
0x180003759  mov     ecx, [rax+8]
0x18000375c  mov     rax, [r11+8]
0x180003760  test    byte ptr [rcx+rax+3], 0Fh
0x180003765  jz      short loc_180003779
0x180003767  movzx   eax, byte ptr [rcx+rax+3]
0x18000376c  mov     ecx, 0FFFFFFF0h
0x180003771  and     rax, rcx
0x180003774  add     rax, r10
0x180003777  jmp     short loc_18000377C
0x180003779  mov     rax, r10
0x18000377c  xor     rdx, rax
0x18000377f  mov     rcx, rdx; StackCookie
0x180003782  jmp     __security_check_cookie
```
