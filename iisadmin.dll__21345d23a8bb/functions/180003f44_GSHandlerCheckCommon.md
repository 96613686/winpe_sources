# __GSHandlerCheckCommon

- ea: `0x180003f44`
- end: `0x180003fa7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003f20`

## callees

- `0x180003f44`
- `0x180003fd0`

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
0x180003f44  mov     r10, rcx
0x180003f47  mov     r11, rdx
0x180003f4a  mov     ecx, [r8]
0x180003f4d  and     ecx, 0FFFFFFF8h
0x180003f50  test    byte ptr [r8], 4
0x180003f54  jz      short loc_180003F6B
0x180003f56  mov     eax, [r8+8]
0x180003f5a  movsxd  r9, dword ptr [r8+4]
0x180003f5e  neg     eax
0x180003f60  movsxd  rdx, eax
0x180003f63  add     r9, r10
0x180003f66  and     r9, rdx
0x180003f69  jmp     short loc_180003F6E
0x180003f6b  mov     r9, r10
0x180003f6e  movsxd  rax, ecx
0x180003f71  mov     rdx, [rax+r9]
0x180003f75  mov     rax, [r11+10h]
0x180003f79  mov     ecx, [rax+8]
0x180003f7c  mov     rax, [r11+8]
0x180003f80  test    byte ptr [rcx+rax+3], 0Fh
0x180003f85  jz      short loc_180003F99
0x180003f87  movzx   eax, byte ptr [rcx+rax+3]
0x180003f8c  mov     ecx, 0FFFFFFF0h
0x180003f91  and     rax, rcx
0x180003f94  add     rax, r10
0x180003f97  jmp     short loc_180003F9C
0x180003f99  mov     rax, r10
0x180003f9c  xor     rdx, rax
0x180003f9f  mov     rcx, rdx; StackCookie
0x180003fa2  jmp     __security_check_cookie
```
