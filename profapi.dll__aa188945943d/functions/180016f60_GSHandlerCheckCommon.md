# __GSHandlerCheckCommon

- ea: `0x180016f60`
- end: `0x180016fc3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016f3c`
- `0x180016fcc`

## callees

- `0x18000fa10`
- `0x180016f60`

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
0x180016f60  mov     r10, rcx
0x180016f63  mov     r11, rdx
0x180016f66  mov     ecx, [r8]
0x180016f69  and     ecx, 0FFFFFFF8h
0x180016f6c  test    byte ptr [r8], 4
0x180016f70  jz      short loc_180016F87
0x180016f72  mov     eax, [r8+8]
0x180016f76  movsxd  r9, dword ptr [r8+4]
0x180016f7a  neg     eax
0x180016f7c  movsxd  rdx, eax
0x180016f7f  add     r9, r10
0x180016f82  and     r9, rdx
0x180016f85  jmp     short loc_180016F8A
0x180016f87  mov     r9, r10
0x180016f8a  movsxd  rax, ecx
0x180016f8d  mov     rdx, [rax+r9]
0x180016f91  mov     rax, [r11+10h]
0x180016f95  mov     ecx, [rax+8]
0x180016f98  mov     rax, [r11+8]
0x180016f9c  test    byte ptr [rcx+rax+3], 0Fh
0x180016fa1  jz      short loc_180016FB5
0x180016fa3  movzx   eax, byte ptr [rcx+rax+3]
0x180016fa8  mov     ecx, 0FFFFFFF0h
0x180016fad  and     rax, rcx
0x180016fb0  add     rax, r10
0x180016fb3  jmp     short loc_180016FB8
0x180016fb5  mov     rax, r10
0x180016fb8  xor     rdx, rax
0x180016fbb  mov     rcx, rdx; StackCookie
0x180016fbe  jmp     __security_check_cookie
```
