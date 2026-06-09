# __GSHandlerCheckCommon

- ea: `0x180002fcc`
- end: `0x18000302f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002fa8`

## callees

- `0x180002fcc`
- `0x180003060`

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
0x180002fcc  mov     r10, rcx
0x180002fcf  mov     r11, rdx
0x180002fd2  mov     ecx, [r8]
0x180002fd5  and     ecx, 0FFFFFFF8h
0x180002fd8  test    byte ptr [r8], 4
0x180002fdc  jz      short loc_180002FF3
0x180002fde  mov     eax, [r8+8]
0x180002fe2  movsxd  r9, dword ptr [r8+4]
0x180002fe6  neg     eax
0x180002fe8  movsxd  rdx, eax
0x180002feb  add     r9, r10
0x180002fee  and     r9, rdx
0x180002ff1  jmp     short loc_180002FF6
0x180002ff3  mov     r9, r10
0x180002ff6  movsxd  rax, ecx
0x180002ff9  mov     rdx, [rax+r9]
0x180002ffd  mov     rax, [r11+10h]
0x180003001  mov     ecx, [rax+8]
0x180003004  mov     rax, [r11+8]
0x180003008  test    byte ptr [rcx+rax+3], 0Fh
0x18000300d  jz      short loc_180003021
0x18000300f  movzx   eax, byte ptr [rcx+rax+3]
0x180003014  mov     ecx, 0FFFFFFF0h
0x180003019  and     rax, rcx
0x18000301c  add     rax, r10
0x18000301f  jmp     short loc_180003024
0x180003021  mov     rax, r10
0x180003024  xor     rdx, rax
0x180003027  mov     rcx, rdx; StackCookie
0x18000302a  jmp     __security_check_cookie
```
