# __GSHandlerCheckCommon

- ea: `0x180005bb4`
- end: `0x180005c17`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005b90`

## callees

- `0x180005bb4`
- `0x180005c60`

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
0x180005bb4  mov     r10, rcx
0x180005bb7  mov     r11, rdx
0x180005bba  mov     ecx, [r8]
0x180005bbd  and     ecx, 0FFFFFFF8h
0x180005bc0  test    byte ptr [r8], 4
0x180005bc4  jz      short loc_180005BDB
0x180005bc6  mov     eax, [r8+8]
0x180005bca  movsxd  r9, dword ptr [r8+4]
0x180005bce  neg     eax
0x180005bd0  movsxd  rdx, eax
0x180005bd3  add     r9, r10
0x180005bd6  and     r9, rdx
0x180005bd9  jmp     short loc_180005BDE
0x180005bdb  mov     r9, r10
0x180005bde  movsxd  rax, ecx
0x180005be1  mov     rdx, [rax+r9]
0x180005be5  mov     rax, [r11+10h]
0x180005be9  mov     ecx, [rax+8]
0x180005bec  mov     rax, [r11+8]
0x180005bf0  test    byte ptr [rcx+rax+3], 0Fh
0x180005bf5  jz      short loc_180005C09
0x180005bf7  movzx   eax, byte ptr [rcx+rax+3]
0x180005bfc  mov     ecx, 0FFFFFFF0h
0x180005c01  and     rax, rcx
0x180005c04  add     rax, r10
0x180005c07  jmp     short loc_180005C0C
0x180005c09  mov     rax, r10
0x180005c0c  xor     rdx, rax
0x180005c0f  mov     rcx, rdx; StackCookie
0x180005c12  jmp     __security_check_cookie
```
