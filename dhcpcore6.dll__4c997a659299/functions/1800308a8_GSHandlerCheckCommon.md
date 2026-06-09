# __GSHandlerCheckCommon

- ea: `0x1800308a8`
- end: `0x18003090b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180030884`

## callees

- `0x180019ad0`
- `0x1800308a8`

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
0x1800308a8  mov     r10, rcx
0x1800308ab  mov     r11, rdx
0x1800308ae  mov     ecx, [r8]
0x1800308b1  and     ecx, 0FFFFFFF8h
0x1800308b4  test    byte ptr [r8], 4
0x1800308b8  jz      short loc_1800308CF
0x1800308ba  mov     eax, [r8+8]
0x1800308be  movsxd  r9, dword ptr [r8+4]
0x1800308c2  neg     eax
0x1800308c4  movsxd  rdx, eax
0x1800308c7  add     r9, r10
0x1800308ca  and     r9, rdx
0x1800308cd  jmp     short loc_1800308D2
0x1800308cf  mov     r9, r10
0x1800308d2  movsxd  rax, ecx
0x1800308d5  mov     rdx, [rax+r9]
0x1800308d9  mov     rax, [r11+10h]
0x1800308dd  mov     ecx, [rax+8]
0x1800308e0  mov     rax, [r11+8]
0x1800308e4  test    byte ptr [rcx+rax+3], 0Fh
0x1800308e9  jz      short loc_1800308FD
0x1800308eb  movzx   eax, byte ptr [rcx+rax+3]
0x1800308f0  mov     ecx, 0FFFFFFF0h
0x1800308f5  and     rax, rcx
0x1800308f8  add     rax, r10
0x1800308fb  jmp     short loc_180030900
0x1800308fd  mov     rax, r10
0x180030900  xor     rdx, rax
0x180030903  mov     rcx, rdx; StackCookie
0x180030906  jmp     __security_check_cookie
```
