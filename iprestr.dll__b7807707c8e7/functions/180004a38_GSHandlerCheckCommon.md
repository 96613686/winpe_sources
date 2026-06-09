# __GSHandlerCheckCommon

- ea: `0x180004a38`
- end: `0x180004a9b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004a14`

## callees

- `0x180004a38`
- `0x180004ad0`

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
0x180004a38  mov     r10, rcx
0x180004a3b  mov     r11, rdx
0x180004a3e  mov     ecx, [r8]
0x180004a41  and     ecx, 0FFFFFFF8h
0x180004a44  test    byte ptr [r8], 4
0x180004a48  jz      short loc_180004A5F
0x180004a4a  mov     eax, [r8+8]
0x180004a4e  movsxd  r9, dword ptr [r8+4]
0x180004a52  neg     eax
0x180004a54  movsxd  rdx, eax
0x180004a57  add     r9, r10
0x180004a5a  and     r9, rdx
0x180004a5d  jmp     short loc_180004A62
0x180004a5f  mov     r9, r10
0x180004a62  movsxd  rax, ecx
0x180004a65  mov     rdx, [rax+r9]
0x180004a69  mov     rax, [r11+10h]
0x180004a6d  mov     ecx, [rax+8]
0x180004a70  mov     rax, [r11+8]
0x180004a74  test    byte ptr [rcx+rax+3], 0Fh
0x180004a79  jz      short loc_180004A8D
0x180004a7b  movzx   eax, byte ptr [rcx+rax+3]
0x180004a80  mov     ecx, 0FFFFFFF0h
0x180004a85  and     rax, rcx
0x180004a88  add     rax, r10
0x180004a8b  jmp     short loc_180004A90
0x180004a8d  mov     rax, r10
0x180004a90  xor     rdx, rax
0x180004a93  mov     rcx, rdx; StackCookie
0x180004a96  jmp     __security_check_cookie
```
