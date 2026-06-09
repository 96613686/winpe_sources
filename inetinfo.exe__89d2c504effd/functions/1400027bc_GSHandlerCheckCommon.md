# __GSHandlerCheckCommon

- ea: `0x1400027bc`
- end: `0x14000281f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002798`

## callees

- `0x1400027bc`
- `0x140002850`

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
0x1400027bc  mov     r10, rcx
0x1400027bf  mov     r11, rdx
0x1400027c2  mov     ecx, [r8]
0x1400027c5  and     ecx, 0FFFFFFF8h
0x1400027c8  test    byte ptr [r8], 4
0x1400027cc  jz      short loc_1400027E3
0x1400027ce  mov     eax, [r8+8]
0x1400027d2  movsxd  r9, dword ptr [r8+4]
0x1400027d6  neg     eax
0x1400027d8  movsxd  rdx, eax
0x1400027db  add     r9, r10
0x1400027de  and     r9, rdx
0x1400027e1  jmp     short loc_1400027E6
0x1400027e3  mov     r9, r10
0x1400027e6  movsxd  rax, ecx
0x1400027e9  mov     rdx, [rax+r9]
0x1400027ed  mov     rax, [r11+10h]
0x1400027f1  mov     ecx, [rax+8]
0x1400027f4  mov     rax, [r11+8]
0x1400027f8  test    byte ptr [rcx+rax+3], 0Fh
0x1400027fd  jz      short loc_140002811
0x1400027ff  movzx   eax, byte ptr [rcx+rax+3]
0x140002804  mov     ecx, 0FFFFFFF0h
0x140002809  and     rax, rcx
0x14000280c  add     rax, r10
0x14000280f  jmp     short loc_140002814
0x140002811  mov     rax, r10
0x140002814  xor     rdx, rax
0x140002817  mov     rcx, rdx; StackCookie
0x14000281a  jmp     __security_check_cookie
```
