# __GSHandlerCheckCommon

- ea: `0x140001f60`
- end: `0x140001fc3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001f3c`

## callees

- `0x140001f60`
- `0x140001ff0`

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
0x140001f60  mov     r10, rcx
0x140001f63  mov     r11, rdx
0x140001f66  mov     ecx, [r8]
0x140001f69  and     ecx, 0FFFFFFF8h
0x140001f6c  test    byte ptr [r8], 4
0x140001f70  jz      short loc_140001F87
0x140001f72  mov     eax, [r8+8]
0x140001f76  movsxd  r9, dword ptr [r8+4]
0x140001f7a  neg     eax
0x140001f7c  movsxd  rdx, eax
0x140001f7f  add     r9, r10
0x140001f82  and     r9, rdx
0x140001f85  jmp     short loc_140001F8A
0x140001f87  mov     r9, r10
0x140001f8a  movsxd  rax, ecx
0x140001f8d  mov     rdx, [rax+r9]
0x140001f91  mov     rax, [r11+10h]
0x140001f95  mov     ecx, [rax+8]
0x140001f98  mov     rax, [r11+8]
0x140001f9c  test    byte ptr [rcx+rax+3], 0Fh
0x140001fa1  jz      short loc_140001FB5
0x140001fa3  movzx   eax, byte ptr [rcx+rax+3]
0x140001fa8  mov     ecx, 0FFFFFFF0h
0x140001fad  and     rax, rcx
0x140001fb0  add     rax, r10
0x140001fb3  jmp     short loc_140001FB8
0x140001fb5  mov     rax, r10
0x140001fb8  xor     rdx, rax
0x140001fbb  mov     rcx, rdx; StackCookie
0x140001fbe  jmp     __security_check_cookie
```
