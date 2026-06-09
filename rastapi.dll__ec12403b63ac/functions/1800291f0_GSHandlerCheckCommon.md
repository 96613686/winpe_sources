# __GSHandlerCheckCommon

- ea: `0x1800291f0`
- end: `0x180029253`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800291cc`

## callees

- `0x1800291f0`
- `0x1800292b0`

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
0x1800291f0  mov     r10, rcx
0x1800291f3  mov     r11, rdx
0x1800291f6  mov     ecx, [r8]
0x1800291f9  and     ecx, 0FFFFFFF8h
0x1800291fc  test    byte ptr [r8], 4
0x180029200  jz      short loc_180029217
0x180029202  mov     eax, [r8+8]
0x180029206  movsxd  r9, dword ptr [r8+4]
0x18002920a  neg     eax
0x18002920c  movsxd  rdx, eax
0x18002920f  add     r9, r10
0x180029212  and     r9, rdx
0x180029215  jmp     short loc_18002921A
0x180029217  mov     r9, r10
0x18002921a  movsxd  rax, ecx
0x18002921d  mov     rdx, [rax+r9]
0x180029221  mov     rax, [r11+10h]
0x180029225  mov     ecx, [rax+8]
0x180029228  mov     rax, [r11+8]
0x18002922c  test    byte ptr [rcx+rax+3], 0Fh
0x180029231  jz      short loc_180029245
0x180029233  movzx   eax, byte ptr [rcx+rax+3]
0x180029238  mov     ecx, 0FFFFFFF0h
0x18002923d  and     rax, rcx
0x180029240  add     rax, r10
0x180029243  jmp     short loc_180029248
0x180029245  mov     rax, r10
0x180029248  xor     rdx, rax
0x18002924b  mov     rcx, rdx; StackCookie
0x18002924e  jmp     __security_check_cookie
```
