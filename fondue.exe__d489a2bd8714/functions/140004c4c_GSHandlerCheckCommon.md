# __GSHandlerCheckCommon

- ea: `0x140004c4c`
- end: `0x140004caf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004c28`

## callees

- `0x140004c4c`
- `0x140004cd0`

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
0x140004c4c  mov     r10, rcx
0x140004c4f  mov     r11, rdx
0x140004c52  mov     ecx, [r8]
0x140004c55  and     ecx, 0FFFFFFF8h
0x140004c58  test    byte ptr [r8], 4
0x140004c5c  jz      short loc_140004C73
0x140004c5e  mov     eax, [r8+8]
0x140004c62  movsxd  r9, dword ptr [r8+4]
0x140004c66  neg     eax
0x140004c68  movsxd  rdx, eax
0x140004c6b  add     r9, r10
0x140004c6e  and     r9, rdx
0x140004c71  jmp     short loc_140004C76
0x140004c73  mov     r9, r10
0x140004c76  movsxd  rax, ecx
0x140004c79  mov     rdx, [rax+r9]
0x140004c7d  mov     rax, [r11+10h]
0x140004c81  mov     ecx, [rax+8]
0x140004c84  mov     rax, [r11+8]
0x140004c88  test    byte ptr [rcx+rax+3], 0Fh
0x140004c8d  jz      short loc_140004CA1
0x140004c8f  movzx   eax, byte ptr [rcx+rax+3]
0x140004c94  mov     ecx, 0FFFFFFF0h
0x140004c99  and     rax, rcx
0x140004c9c  add     rax, r10
0x140004c9f  jmp     short loc_140004CA4
0x140004ca1  mov     rax, r10
0x140004ca4  xor     rdx, rax
0x140004ca7  mov     rcx, rdx; StackCookie
0x140004caa  jmp     __security_check_cookie
```
