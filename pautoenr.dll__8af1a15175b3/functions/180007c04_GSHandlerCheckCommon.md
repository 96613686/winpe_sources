# __GSHandlerCheckCommon

- ea: `0x180007c04`
- end: `0x180007c67`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007be0`
- `0x180007c70`

## callees

- `0x180007c04`
- `0x180007d20`

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
0x180007c04  mov     r10, rcx
0x180007c07  mov     r11, rdx
0x180007c0a  mov     ecx, [r8]
0x180007c0d  and     ecx, 0FFFFFFF8h
0x180007c10  test    byte ptr [r8], 4
0x180007c14  jz      short loc_180007C2B
0x180007c16  mov     eax, [r8+8]
0x180007c1a  movsxd  r9, dword ptr [r8+4]
0x180007c1e  neg     eax
0x180007c20  movsxd  rdx, eax
0x180007c23  add     r9, r10
0x180007c26  and     r9, rdx
0x180007c29  jmp     short loc_180007C2E
0x180007c2b  mov     r9, r10
0x180007c2e  movsxd  rax, ecx
0x180007c31  mov     rdx, [rax+r9]
0x180007c35  mov     rax, [r11+10h]
0x180007c39  mov     ecx, [rax+8]
0x180007c3c  mov     rax, [r11+8]
0x180007c40  test    byte ptr [rcx+rax+3], 0Fh
0x180007c45  jz      short loc_180007C59
0x180007c47  movzx   eax, byte ptr [rcx+rax+3]
0x180007c4c  mov     ecx, 0FFFFFFF0h
0x180007c51  and     rax, rcx
0x180007c54  add     rax, r10
0x180007c57  jmp     short loc_180007C5C
0x180007c59  mov     rax, r10
0x180007c5c  xor     rdx, rax
0x180007c5f  mov     rcx, rdx; StackCookie
0x180007c62  jmp     __security_check_cookie
```
