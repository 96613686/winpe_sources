# __GSHandlerCheckCommon

- ea: `0x180002a4c`
- end: `0x180002aaf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002a28`
- `0x180011288`

## callees

- `0x180002a4c`
- `0x180011340`

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
0x180002a4c  mov     r10, rcx
0x180002a4f  mov     r11, rdx
0x180002a52  mov     ecx, [r8]
0x180002a55  and     ecx, 0FFFFFFF8h
0x180002a58  test    byte ptr [r8], 4
0x180002a5c  jz      short loc_180002A73
0x180002a5e  mov     eax, [r8+8]
0x180002a62  movsxd  r9, dword ptr [r8+4]
0x180002a66  neg     eax
0x180002a68  movsxd  rdx, eax
0x180002a6b  add     r9, r10
0x180002a6e  and     r9, rdx
0x180002a71  jmp     short loc_180002A76
0x180002a73  mov     r9, r10
0x180002a76  movsxd  rax, ecx
0x180002a79  mov     rdx, [rax+r9]
0x180002a7d  mov     rax, [r11+10h]
0x180002a81  mov     ecx, [rax+8]
0x180002a84  mov     rax, [r11+8]
0x180002a88  test    byte ptr [rcx+rax+3], 0Fh
0x180002a8d  jz      short loc_180002AA1
0x180002a8f  movzx   eax, byte ptr [rcx+rax+3]
0x180002a94  mov     ecx, 0FFFFFFF0h
0x180002a99  and     rax, rcx
0x180002a9c  add     rax, r10
0x180002a9f  jmp     short loc_180002AA4
0x180002aa1  mov     rax, r10
0x180002aa4  xor     rdx, rax
0x180002aa7  mov     rcx, rdx; StackCookie
0x180002aaa  jmp     __security_check_cookie
```
