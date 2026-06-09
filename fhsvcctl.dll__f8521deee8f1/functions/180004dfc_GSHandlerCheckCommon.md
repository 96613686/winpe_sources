# __GSHandlerCheckCommon

- ea: `0x180004dfc`
- end: `0x180004e5f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004dd8`
- `0x180004e68`

## callees

- `0x180004dfc`
- `0x180004f20`

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
0x180004dfc  mov     r10, rcx
0x180004dff  mov     r11, rdx
0x180004e02  mov     ecx, [r8]
0x180004e05  and     ecx, 0FFFFFFF8h
0x180004e08  test    byte ptr [r8], 4
0x180004e0c  jz      short loc_180004E23
0x180004e0e  mov     eax, [r8+8]
0x180004e12  movsxd  r9, dword ptr [r8+4]
0x180004e16  neg     eax
0x180004e18  movsxd  rdx, eax
0x180004e1b  add     r9, r10
0x180004e1e  and     r9, rdx
0x180004e21  jmp     short loc_180004E26
0x180004e23  mov     r9, r10
0x180004e26  movsxd  rax, ecx
0x180004e29  mov     rdx, [rax+r9]
0x180004e2d  mov     rax, [r11+10h]
0x180004e31  mov     ecx, [rax+8]
0x180004e34  mov     rax, [r11+8]
0x180004e38  test    byte ptr [rcx+rax+3], 0Fh
0x180004e3d  jz      short loc_180004E51
0x180004e3f  movzx   eax, byte ptr [rcx+rax+3]
0x180004e44  mov     ecx, 0FFFFFFF0h
0x180004e49  and     rax, rcx
0x180004e4c  add     rax, r10
0x180004e4f  jmp     short loc_180004E54
0x180004e51  mov     rax, r10
0x180004e54  xor     rdx, rax
0x180004e57  mov     rcx, rdx; StackCookie
0x180004e5a  jmp     __security_check_cookie
```
