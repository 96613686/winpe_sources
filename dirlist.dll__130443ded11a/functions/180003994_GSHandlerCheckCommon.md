# __GSHandlerCheckCommon

- ea: `0x180003994`
- end: `0x1800039f7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003970`

## callees

- `0x180003994`
- `0x180003a40`

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
0x180003994  mov     r10, rcx
0x180003997  mov     r11, rdx
0x18000399a  mov     ecx, [r8]
0x18000399d  and     ecx, 0FFFFFFF8h
0x1800039a0  test    byte ptr [r8], 4
0x1800039a4  jz      short loc_1800039BB
0x1800039a6  mov     eax, [r8+8]
0x1800039aa  movsxd  r9, dword ptr [r8+4]
0x1800039ae  neg     eax
0x1800039b0  movsxd  rdx, eax
0x1800039b3  add     r9, r10
0x1800039b6  and     r9, rdx
0x1800039b9  jmp     short loc_1800039BE
0x1800039bb  mov     r9, r10
0x1800039be  movsxd  rax, ecx
0x1800039c1  mov     rdx, [rax+r9]
0x1800039c5  mov     rax, [r11+10h]
0x1800039c9  mov     ecx, [rax+8]
0x1800039cc  mov     rax, [r11+8]
0x1800039d0  test    byte ptr [rcx+rax+3], 0Fh
0x1800039d5  jz      short loc_1800039E9
0x1800039d7  movzx   eax, byte ptr [rcx+rax+3]
0x1800039dc  mov     ecx, 0FFFFFFF0h
0x1800039e1  and     rax, rcx
0x1800039e4  add     rax, r10
0x1800039e7  jmp     short loc_1800039EC
0x1800039e9  mov     rax, r10
0x1800039ec  xor     rdx, rax
0x1800039ef  mov     rcx, rdx; StackCookie
0x1800039f2  jmp     __security_check_cookie
```
