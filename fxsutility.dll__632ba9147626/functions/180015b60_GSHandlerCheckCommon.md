# __GSHandlerCheckCommon

- ea: `0x180015b60`
- end: `0x180015bc3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015b3c`
- `0x180015bcc`
- `0x180015c34`

## callees

- `0x180015b60`
- `0x180015cf0`

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
0x180015b60  mov     r10, rcx
0x180015b63  mov     r11, rdx
0x180015b66  mov     ecx, [r8]
0x180015b69  and     ecx, 0FFFFFFF8h
0x180015b6c  test    byte ptr [r8], 4
0x180015b70  jz      short loc_180015B87
0x180015b72  mov     eax, [r8+8]
0x180015b76  movsxd  r9, dword ptr [r8+4]
0x180015b7a  neg     eax
0x180015b7c  movsxd  rdx, eax
0x180015b7f  add     r9, r10
0x180015b82  and     r9, rdx
0x180015b85  jmp     short loc_180015B8A
0x180015b87  mov     r9, r10
0x180015b8a  movsxd  rax, ecx
0x180015b8d  mov     rdx, [rax+r9]
0x180015b91  mov     rax, [r11+10h]
0x180015b95  mov     ecx, [rax+8]
0x180015b98  mov     rax, [r11+8]
0x180015b9c  test    byte ptr [rcx+rax+3], 0Fh
0x180015ba1  jz      short loc_180015BB5
0x180015ba3  movzx   eax, byte ptr [rcx+rax+3]
0x180015ba8  mov     ecx, 0FFFFFFF0h
0x180015bad  and     rax, rcx
0x180015bb0  add     rax, r10
0x180015bb3  jmp     short loc_180015BB8
0x180015bb5  mov     rax, r10
0x180015bb8  xor     rdx, rax
0x180015bbb  mov     rcx, rdx; StackCookie
0x180015bbe  jmp     __security_check_cookie
```
