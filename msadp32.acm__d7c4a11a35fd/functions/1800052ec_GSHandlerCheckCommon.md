# __GSHandlerCheckCommon

- ea: `0x1800052ec`
- end: `0x18000534f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800052c8`

## callees

- `0x180001400`
- `0x1800052ec`

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
0x1800052ec  mov     r10, rcx
0x1800052ef  mov     r11, rdx
0x1800052f2  mov     ecx, [r8]
0x1800052f5  and     ecx, 0FFFFFFF8h
0x1800052f8  test    byte ptr [r8], 4
0x1800052fc  jz      short loc_180005313
0x1800052fe  mov     eax, [r8+8]
0x180005302  movsxd  r9, dword ptr [r8+4]
0x180005306  neg     eax
0x180005308  movsxd  rdx, eax
0x18000530b  add     r9, r10
0x18000530e  and     r9, rdx
0x180005311  jmp     short loc_180005316
0x180005313  mov     r9, r10
0x180005316  movsxd  rax, ecx
0x180005319  mov     rdx, [rax+r9]
0x18000531d  mov     rax, [r11+10h]
0x180005321  mov     ecx, [rax+8]
0x180005324  mov     rax, [r11+8]
0x180005328  test    byte ptr [rcx+rax+3], 0Fh
0x18000532d  jz      short loc_180005341
0x18000532f  movzx   eax, byte ptr [rcx+rax+3]
0x180005334  mov     ecx, 0FFFFFFF0h
0x180005339  and     rax, rcx
0x18000533c  add     rax, r10
0x18000533f  jmp     short loc_180005344
0x180005341  mov     rax, r10
0x180005344  xor     rdx, rax
0x180005347  mov     rcx, rdx; StackCookie
0x18000534a  jmp     __security_check_cookie
```
