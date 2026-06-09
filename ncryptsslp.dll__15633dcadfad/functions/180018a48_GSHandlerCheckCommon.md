# __GSHandlerCheckCommon

- ea: `0x180018a48`
- end: `0x180018aab`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018a24`
- `0x18001d5e0`

## callees

- `0x180018a48`
- `0x180024ef0`

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
0x180018a48  mov     r10, rcx
0x180018a4b  mov     r11, rdx
0x180018a4e  mov     ecx, [r8]
0x180018a51  and     ecx, 0FFFFFFF8h
0x180018a54  test    byte ptr [r8], 4
0x180018a58  jz      short loc_180018A6F
0x180018a5a  mov     eax, [r8+8]
0x180018a5e  movsxd  r9, dword ptr [r8+4]
0x180018a62  neg     eax
0x180018a64  movsxd  rdx, eax
0x180018a67  add     r9, r10
0x180018a6a  and     r9, rdx
0x180018a6d  jmp     short loc_180018A72
0x180018a6f  mov     r9, r10
0x180018a72  movsxd  rax, ecx
0x180018a75  mov     rdx, [rax+r9]
0x180018a79  mov     rax, [r11+10h]
0x180018a7d  mov     ecx, [rax+8]
0x180018a80  mov     rax, [r11+8]
0x180018a84  test    byte ptr [rcx+rax+3], 0Fh
0x180018a89  jz      short loc_180018A9D
0x180018a8b  movzx   eax, byte ptr [rcx+rax+3]
0x180018a90  mov     ecx, 0FFFFFFF0h
0x180018a95  and     rax, rcx
0x180018a98  add     rax, r10
0x180018a9b  jmp     short loc_180018AA0
0x180018a9d  mov     rax, r10
0x180018aa0  xor     rdx, rax
0x180018aa3  mov     rcx, rdx; StackCookie
0x180018aa6  jmp     __security_check_cookie
```
