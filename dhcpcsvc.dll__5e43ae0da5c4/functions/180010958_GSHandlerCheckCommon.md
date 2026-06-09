# __GSHandlerCheckCommon

- ea: `0x180010958`
- end: `0x1800109bb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010934`
- `0x1800109c4`

## callees

- `0x1800048c0`
- `0x180010958`

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
0x180010958  mov     r10, rcx
0x18001095b  mov     r11, rdx
0x18001095e  mov     ecx, [r8]
0x180010961  and     ecx, 0FFFFFFF8h
0x180010964  test    byte ptr [r8], 4
0x180010968  jz      short loc_18001097F
0x18001096a  mov     eax, [r8+8]
0x18001096e  movsxd  r9, dword ptr [r8+4]
0x180010972  neg     eax
0x180010974  movsxd  rdx, eax
0x180010977  add     r9, r10
0x18001097a  and     r9, rdx
0x18001097d  jmp     short loc_180010982
0x18001097f  mov     r9, r10
0x180010982  movsxd  rax, ecx
0x180010985  mov     rdx, [rax+r9]
0x180010989  mov     rax, [r11+10h]
0x18001098d  mov     ecx, [rax+8]
0x180010990  mov     rax, [r11+8]
0x180010994  test    byte ptr [rcx+rax+3], 0Fh
0x180010999  jz      short loc_1800109AD
0x18001099b  movzx   eax, byte ptr [rcx+rax+3]
0x1800109a0  mov     ecx, 0FFFFFFF0h
0x1800109a5  and     rax, rcx
0x1800109a8  add     rax, r10
0x1800109ab  jmp     short loc_1800109B0
0x1800109ad  mov     rax, r10
0x1800109b0  xor     rdx, rax
0x1800109b3  mov     rcx, rdx; StackCookie
0x1800109b6  jmp     __security_check_cookie
```
