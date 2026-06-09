# __GSHandlerCheckCommon

- ea: `0x18000ecbc`
- end: `0x18000ed1f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ec98`
- `0x18000ed28`

## callees

- `0x180001550`
- `0x18000ecbc`

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
0x18000ecbc  mov     r10, rcx
0x18000ecbf  mov     r11, rdx
0x18000ecc2  mov     ecx, [r8]
0x18000ecc5  and     ecx, 0FFFFFFF8h
0x18000ecc8  test    byte ptr [r8], 4
0x18000eccc  jz      short loc_18000ECE3
0x18000ecce  mov     eax, [r8+8]
0x18000ecd2  movsxd  r9, dword ptr [r8+4]
0x18000ecd6  neg     eax
0x18000ecd8  movsxd  rdx, eax
0x18000ecdb  add     r9, r10
0x18000ecde  and     r9, rdx
0x18000ece1  jmp     short loc_18000ECE6
0x18000ece3  mov     r9, r10
0x18000ece6  movsxd  rax, ecx
0x18000ece9  mov     rdx, [rax+r9]
0x18000eced  mov     rax, [r11+10h]
0x18000ecf1  mov     ecx, [rax+8]
0x18000ecf4  mov     rax, [r11+8]
0x18000ecf8  test    byte ptr [rcx+rax+3], 0Fh
0x18000ecfd  jz      short loc_18000ED11
0x18000ecff  movzx   eax, byte ptr [rcx+rax+3]
0x18000ed04  mov     ecx, 0FFFFFFF0h
0x18000ed09  and     rax, rcx
0x18000ed0c  add     rax, r10
0x18000ed0f  jmp     short loc_18000ED14
0x18000ed11  mov     rax, r10
0x18000ed14  xor     rdx, rax
0x18000ed17  mov     rcx, rdx; StackCookie
0x18000ed1a  jmp     __security_check_cookie
```
