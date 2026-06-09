# __GSHandlerCheckCommon

- ea: `0x180003d70`
- end: `0x180003dd3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003d4c`

## callees

- `0x180003d70`
- `0x180003e20`

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
0x180003d70  mov     r10, rcx
0x180003d73  mov     r11, rdx
0x180003d76  mov     ecx, [r8]
0x180003d79  and     ecx, 0FFFFFFF8h
0x180003d7c  test    byte ptr [r8], 4
0x180003d80  jz      short loc_180003D97
0x180003d82  mov     eax, [r8+8]
0x180003d86  movsxd  r9, dword ptr [r8+4]
0x180003d8a  neg     eax
0x180003d8c  movsxd  rdx, eax
0x180003d8f  add     r9, r10
0x180003d92  and     r9, rdx
0x180003d95  jmp     short loc_180003D9A
0x180003d97  mov     r9, r10
0x180003d9a  movsxd  rax, ecx
0x180003d9d  mov     rdx, [rax+r9]
0x180003da1  mov     rax, [r11+10h]
0x180003da5  mov     ecx, [rax+8]
0x180003da8  mov     rax, [r11+8]
0x180003dac  test    byte ptr [rcx+rax+3], 0Fh
0x180003db1  jz      short loc_180003DC5
0x180003db3  movzx   eax, byte ptr [rcx+rax+3]
0x180003db8  mov     ecx, 0FFFFFFF0h
0x180003dbd  and     rax, rcx
0x180003dc0  add     rax, r10
0x180003dc3  jmp     short loc_180003DC8
0x180003dc5  mov     rax, r10
0x180003dc8  xor     rdx, rax
0x180003dcb  mov     rcx, rdx; StackCookie
0x180003dce  jmp     __security_check_cookie
```
