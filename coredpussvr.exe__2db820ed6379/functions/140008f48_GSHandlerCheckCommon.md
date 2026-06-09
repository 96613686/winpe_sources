# __GSHandlerCheckCommon

- ea: `0x140008f48`
- end: `0x140008fab`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008f24`
- `0x140008fb4`

## callees

- `0x140001500`
- `0x140008f48`

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
0x140008f48  mov     r10, rcx
0x140008f4b  mov     r11, rdx
0x140008f4e  mov     ecx, [r8]
0x140008f51  and     ecx, 0FFFFFFF8h
0x140008f54  test    byte ptr [r8], 4
0x140008f58  jz      short loc_140008F6F
0x140008f5a  mov     eax, [r8+8]
0x140008f5e  movsxd  r9, dword ptr [r8+4]
0x140008f62  neg     eax
0x140008f64  movsxd  rdx, eax
0x140008f67  add     r9, r10
0x140008f6a  and     r9, rdx
0x140008f6d  jmp     short loc_140008F72
0x140008f6f  mov     r9, r10
0x140008f72  movsxd  rax, ecx
0x140008f75  mov     rdx, [rax+r9]
0x140008f79  mov     rax, [r11+10h]
0x140008f7d  mov     ecx, [rax+8]
0x140008f80  mov     rax, [r11+8]
0x140008f84  test    byte ptr [rcx+rax+3], 0Fh
0x140008f89  jz      short loc_140008F9D
0x140008f8b  movzx   eax, byte ptr [rcx+rax+3]
0x140008f90  mov     ecx, 0FFFFFFF0h
0x140008f95  and     rax, rcx
0x140008f98  add     rax, r10
0x140008f9b  jmp     short loc_140008FA0
0x140008f9d  mov     rax, r10
0x140008fa0  xor     rdx, rax
0x140008fa3  mov     rcx, rdx; StackCookie
0x140008fa6  jmp     __security_check_cookie
```
