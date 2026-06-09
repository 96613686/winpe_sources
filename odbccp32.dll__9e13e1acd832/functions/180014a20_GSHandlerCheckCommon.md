# __GSHandlerCheckCommon

- ea: `0x180014a20`
- end: `0x180014a83`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800149fc`

## callees

- `0x180014a20`
- `0x180014ae0`

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
0x180014a20  mov     r10, rcx
0x180014a23  mov     r11, rdx
0x180014a26  mov     ecx, [r8]
0x180014a29  and     ecx, 0FFFFFFF8h
0x180014a2c  test    byte ptr [r8], 4
0x180014a30  jz      short loc_180014A47
0x180014a32  mov     eax, [r8+8]
0x180014a36  movsxd  r9, dword ptr [r8+4]
0x180014a3a  neg     eax
0x180014a3c  movsxd  rdx, eax
0x180014a3f  add     r9, r10
0x180014a42  and     r9, rdx
0x180014a45  jmp     short loc_180014A4A
0x180014a47  mov     r9, r10
0x180014a4a  movsxd  rax, ecx
0x180014a4d  mov     rdx, [rax+r9]
0x180014a51  mov     rax, [r11+10h]
0x180014a55  mov     ecx, [rax+8]
0x180014a58  mov     rax, [r11+8]
0x180014a5c  test    byte ptr [rcx+rax+3], 0Fh
0x180014a61  jz      short loc_180014A75
0x180014a63  movzx   eax, byte ptr [rcx+rax+3]
0x180014a68  mov     ecx, 0FFFFFFF0h
0x180014a6d  and     rax, rcx
0x180014a70  add     rax, r10
0x180014a73  jmp     short loc_180014A78
0x180014a75  mov     rax, r10
0x180014a78  xor     rdx, rax
0x180014a7b  mov     rcx, rdx; StackCookie
0x180014a7e  jmp     __security_check_cookie
```
