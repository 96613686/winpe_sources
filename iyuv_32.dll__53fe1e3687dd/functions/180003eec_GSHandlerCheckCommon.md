# __GSHandlerCheckCommon

- ea: `0x180003eec`
- end: `0x180003f4f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003ec8`

## callees

- `0x180001400`
- `0x180003eec`

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
0x180003eec  mov     r10, rcx
0x180003eef  mov     r11, rdx
0x180003ef2  mov     ecx, [r8]
0x180003ef5  and     ecx, 0FFFFFFF8h
0x180003ef8  test    byte ptr [r8], 4
0x180003efc  jz      short loc_180003F13
0x180003efe  mov     eax, [r8+8]
0x180003f02  movsxd  r9, dword ptr [r8+4]
0x180003f06  neg     eax
0x180003f08  movsxd  rdx, eax
0x180003f0b  add     r9, r10
0x180003f0e  and     r9, rdx
0x180003f11  jmp     short loc_180003F16
0x180003f13  mov     r9, r10
0x180003f16  movsxd  rax, ecx
0x180003f19  mov     rdx, [rax+r9]
0x180003f1d  mov     rax, [r11+10h]
0x180003f21  mov     ecx, [rax+8]
0x180003f24  mov     rax, [r11+8]
0x180003f28  test    byte ptr [rcx+rax+3], 0Fh
0x180003f2d  jz      short loc_180003F41
0x180003f2f  movzx   eax, byte ptr [rcx+rax+3]
0x180003f34  mov     ecx, 0FFFFFFF0h
0x180003f39  and     rax, rcx
0x180003f3c  add     rax, r10
0x180003f3f  jmp     short loc_180003F44
0x180003f41  mov     rax, r10
0x180003f44  xor     rdx, rax
0x180003f47  mov     rcx, rdx; StackCookie
0x180003f4a  jmp     __security_check_cookie
```
