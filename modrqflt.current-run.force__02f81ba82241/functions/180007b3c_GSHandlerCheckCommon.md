# __GSHandlerCheckCommon

- ea: `0x180007b3c`
- end: `0x180007b9f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007b18`

## callees

- `0x180007b3c`
- `0x180007bc0`

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
0x180007b3c  mov     r10, rcx
0x180007b3f  mov     r11, rdx
0x180007b42  mov     ecx, [r8]
0x180007b45  and     ecx, 0FFFFFFF8h
0x180007b48  test    byte ptr [r8], 4
0x180007b4c  jz      short loc_180007B63
0x180007b4e  mov     eax, [r8+8]
0x180007b52  movsxd  r9, dword ptr [r8+4]
0x180007b56  neg     eax
0x180007b58  movsxd  rdx, eax
0x180007b5b  add     r9, r10
0x180007b5e  and     r9, rdx
0x180007b61  jmp     short loc_180007B66
0x180007b63  mov     r9, r10
0x180007b66  movsxd  rax, ecx
0x180007b69  mov     rdx, [rax+r9]
0x180007b6d  mov     rax, [r11+10h]
0x180007b71  mov     ecx, [rax+8]
0x180007b74  mov     rax, [r11+8]
0x180007b78  test    byte ptr [rcx+rax+3], 0Fh
0x180007b7d  jz      short loc_180007B91
0x180007b7f  movzx   eax, byte ptr [rcx+rax+3]
0x180007b84  mov     ecx, 0FFFFFFF0h
0x180007b89  and     rax, rcx
0x180007b8c  add     rax, r10
0x180007b8f  jmp     short loc_180007B94
0x180007b91  mov     rax, r10
0x180007b94  xor     rdx, rax
0x180007b97  mov     rcx, rdx; StackCookie
0x180007b9a  jmp     __security_check_cookie
```
