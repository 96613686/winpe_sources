# __GSHandlerCheckCommon

- ea: `0x180003520`
- end: `0x180003583`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800034fc`
- `0x18001e928`
- `0x18001e990`

## callees

- `0x1800022e0`
- `0x180003520`

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
0x180003520  mov     r10, rcx
0x180003523  mov     r11, rdx
0x180003526  mov     ecx, [r8]
0x180003529  and     ecx, 0FFFFFFF8h
0x18000352c  test    byte ptr [r8], 4
0x180003530  jz      short loc_180003547
0x180003532  mov     eax, [r8+8]
0x180003536  movsxd  r9, dword ptr [r8+4]
0x18000353a  neg     eax
0x18000353c  movsxd  rdx, eax
0x18000353f  add     r9, r10
0x180003542  and     r9, rdx
0x180003545  jmp     short loc_18000354A
0x180003547  mov     r9, r10
0x18000354a  movsxd  rax, ecx
0x18000354d  mov     rdx, [rax+r9]
0x180003551  mov     rax, [r11+10h]
0x180003555  mov     ecx, [rax+8]
0x180003558  mov     rax, [r11+8]
0x18000355c  test    byte ptr [rcx+rax+3], 0Fh
0x180003561  jz      short loc_180003575
0x180003563  movzx   eax, byte ptr [rcx+rax+3]
0x180003568  mov     ecx, 0FFFFFFF0h
0x18000356d  and     rax, rcx
0x180003570  add     rax, r10
0x180003573  jmp     short loc_180003578
0x180003575  mov     rax, r10
0x180003578  xor     rdx, rax
0x18000357b  mov     rcx, rdx; StackCookie
0x18000357e  jmp     __security_check_cookie
```
