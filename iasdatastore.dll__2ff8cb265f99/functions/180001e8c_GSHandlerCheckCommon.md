# __GSHandlerCheckCommon

- ea: `0x180001e8c`
- end: `0x180001eef`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001e68`
- `0x18000dc78`

## callees

- `0x180001e8c`
- `0x18000dd10`

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
0x180001e8c  mov     r10, rcx
0x180001e8f  mov     r11, rdx
0x180001e92  mov     ecx, [r8]
0x180001e95  and     ecx, 0FFFFFFF8h
0x180001e98  test    byte ptr [r8], 4
0x180001e9c  jz      short loc_180001EB3
0x180001e9e  mov     eax, [r8+8]
0x180001ea2  movsxd  r9, dword ptr [r8+4]
0x180001ea6  neg     eax
0x180001ea8  movsxd  rdx, eax
0x180001eab  add     r9, r10
0x180001eae  and     r9, rdx
0x180001eb1  jmp     short loc_180001EB6
0x180001eb3  mov     r9, r10
0x180001eb6  movsxd  rax, ecx
0x180001eb9  mov     rdx, [rax+r9]
0x180001ebd  mov     rax, [r11+10h]
0x180001ec1  mov     ecx, [rax+8]
0x180001ec4  mov     rax, [r11+8]
0x180001ec8  test    byte ptr [rcx+rax+3], 0Fh
0x180001ecd  jz      short loc_180001EE1
0x180001ecf  movzx   eax, byte ptr [rcx+rax+3]
0x180001ed4  mov     ecx, 0FFFFFFF0h
0x180001ed9  and     rax, rcx
0x180001edc  add     rax, r10
0x180001edf  jmp     short loc_180001EE4
0x180001ee1  mov     rax, r10
0x180001ee4  xor     rdx, rax
0x180001ee7  mov     rcx, rdx; StackCookie
0x180001eea  jmp     __security_check_cookie
```
