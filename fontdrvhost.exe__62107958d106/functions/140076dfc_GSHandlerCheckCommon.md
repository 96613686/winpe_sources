# __GSHandlerCheckCommon

- ea: `0x140076dfc`
- end: `0x140076e5f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140076dd8`
- `0x140096088`
- `0x1400960f0`

## callees

- `0x140075de0`
- `0x140076dfc`

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
0x140076dfc  mov     r10, rcx
0x140076dff  mov     r11, rdx
0x140076e02  mov     ecx, [r8]
0x140076e05  and     ecx, 0FFFFFFF8h
0x140076e08  test    byte ptr [r8], 4
0x140076e0c  jz      short loc_140076E23
0x140076e0e  mov     eax, [r8+8]
0x140076e12  movsxd  r9, dword ptr [r8+4]
0x140076e16  neg     eax
0x140076e18  movsxd  rdx, eax
0x140076e1b  add     r9, r10
0x140076e1e  and     r9, rdx
0x140076e21  jmp     short loc_140076E26
0x140076e23  mov     r9, r10
0x140076e26  movsxd  rax, ecx
0x140076e29  mov     rdx, [rax+r9]
0x140076e2d  mov     rax, [r11+10h]
0x140076e31  mov     ecx, [rax+8]
0x140076e34  mov     rax, [r11+8]
0x140076e38  test    byte ptr [rcx+rax+3], 0Fh
0x140076e3d  jz      short loc_140076E51
0x140076e3f  movzx   eax, byte ptr [rcx+rax+3]
0x140076e44  mov     ecx, 0FFFFFFF0h
0x140076e49  and     rax, rcx
0x140076e4c  add     rax, r10
0x140076e4f  jmp     short loc_140076E54
0x140076e51  mov     rax, r10
0x140076e54  xor     rdx, rax
0x140076e57  mov     rcx, rdx; StackCookie
0x140076e5a  jmp     __security_check_cookie
```
