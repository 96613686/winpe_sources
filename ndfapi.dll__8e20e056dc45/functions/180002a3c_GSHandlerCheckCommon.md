# __GSHandlerCheckCommon

- ea: `0x180002a3c`
- end: `0x180002a9f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002a18`
- `0x18001f5d4`

## callees

- `0x180002a3c`
- `0x18001f690`

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
0x180002a3c  mov     r10, rcx
0x180002a3f  mov     r11, rdx
0x180002a42  mov     ecx, [r8]
0x180002a45  and     ecx, 0FFFFFFF8h
0x180002a48  test    byte ptr [r8], 4
0x180002a4c  jz      short loc_180002A63
0x180002a4e  mov     eax, [r8+8]
0x180002a52  movsxd  r9, dword ptr [r8+4]
0x180002a56  neg     eax
0x180002a58  movsxd  rdx, eax
0x180002a5b  add     r9, r10
0x180002a5e  and     r9, rdx
0x180002a61  jmp     short loc_180002A66
0x180002a63  mov     r9, r10
0x180002a66  movsxd  rax, ecx
0x180002a69  mov     rdx, [rax+r9]
0x180002a6d  mov     rax, [r11+10h]
0x180002a71  mov     ecx, [rax+8]
0x180002a74  mov     rax, [r11+8]
0x180002a78  test    byte ptr [rcx+rax+3], 0Fh
0x180002a7d  jz      short loc_180002A91
0x180002a7f  movzx   eax, byte ptr [rcx+rax+3]
0x180002a84  mov     ecx, 0FFFFFFF0h
0x180002a89  and     rax, rcx
0x180002a8c  add     rax, r10
0x180002a8f  jmp     short loc_180002A94
0x180002a91  mov     rax, r10
0x180002a94  xor     rdx, rax
0x180002a97  mov     rcx, rdx; StackCookie
0x180002a9a  jmp     __security_check_cookie
```
