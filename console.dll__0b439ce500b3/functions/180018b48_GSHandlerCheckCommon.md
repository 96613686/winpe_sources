# __GSHandlerCheckCommon

- ea: `0x180018b48`
- end: `0x180018bab`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018b24`
- `0x180018bb4`
- `0x180018c1c`

## callees

- `0x1800015b0`
- `0x180018b48`

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
0x180018b48  mov     r10, rcx
0x180018b4b  mov     r11, rdx
0x180018b4e  mov     ecx, [r8]
0x180018b51  and     ecx, 0FFFFFFF8h
0x180018b54  test    byte ptr [r8], 4
0x180018b58  jz      short loc_180018B6F
0x180018b5a  mov     eax, [r8+8]
0x180018b5e  movsxd  r9, dword ptr [r8+4]
0x180018b62  neg     eax
0x180018b64  movsxd  rdx, eax
0x180018b67  add     r9, r10
0x180018b6a  and     r9, rdx
0x180018b6d  jmp     short loc_180018B72
0x180018b6f  mov     r9, r10
0x180018b72  movsxd  rax, ecx
0x180018b75  mov     rdx, [rax+r9]
0x180018b79  mov     rax, [r11+10h]
0x180018b7d  mov     ecx, [rax+8]
0x180018b80  mov     rax, [r11+8]
0x180018b84  test    byte ptr [rcx+rax+3], 0Fh
0x180018b89  jz      short loc_180018B9D
0x180018b8b  movzx   eax, byte ptr [rcx+rax+3]
0x180018b90  mov     ecx, 0FFFFFFF0h
0x180018b95  and     rax, rcx
0x180018b98  add     rax, r10
0x180018b9b  jmp     short loc_180018BA0
0x180018b9d  mov     rax, r10
0x180018ba0  xor     rdx, rax
0x180018ba3  mov     rcx, rdx; StackCookie
0x180018ba6  jmp     __security_check_cookie
```
