# __GSHandlerCheckCommon

- ea: `0x1800053b0`
- end: `0x180005413`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000538c`
- `0x18000541c`

## callees

- `0x1800053b0`
- `0x1800054b0`

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
0x1800053b0  mov     r10, rcx
0x1800053b3  mov     r11, rdx
0x1800053b6  mov     ecx, [r8]
0x1800053b9  and     ecx, 0FFFFFFF8h
0x1800053bc  test    byte ptr [r8], 4
0x1800053c0  jz      short loc_1800053D7
0x1800053c2  mov     eax, [r8+8]
0x1800053c6  movsxd  r9, dword ptr [r8+4]
0x1800053ca  neg     eax
0x1800053cc  movsxd  rdx, eax
0x1800053cf  add     r9, r10
0x1800053d2  and     r9, rdx
0x1800053d5  jmp     short loc_1800053DA
0x1800053d7  mov     r9, r10
0x1800053da  movsxd  rax, ecx
0x1800053dd  mov     rdx, [rax+r9]
0x1800053e1  mov     rax, [r11+10h]
0x1800053e5  mov     ecx, [rax+8]
0x1800053e8  mov     rax, [r11+8]
0x1800053ec  test    byte ptr [rcx+rax+3], 0Fh
0x1800053f1  jz      short loc_180005405
0x1800053f3  movzx   eax, byte ptr [rcx+rax+3]
0x1800053f8  mov     ecx, 0FFFFFFF0h
0x1800053fd  and     rax, rcx
0x180005400  add     rax, r10
0x180005403  jmp     short loc_180005408
0x180005405  mov     rax, r10
0x180005408  xor     rdx, rax
0x18000540b  mov     rcx, rdx; StackCookie
0x18000540e  jmp     __security_check_cookie
```
