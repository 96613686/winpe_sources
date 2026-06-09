# __GSHandlerCheckCommon

- ea: `0x18000a428`
- end: `0x18000a48b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a404`
- `0x18000a494`
- `0x18000a4fc`

## callees

- `0x18000a428`
- `0x18000a5b0`

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
0x18000a428  mov     r10, rcx
0x18000a42b  mov     r11, rdx
0x18000a42e  mov     ecx, [r8]
0x18000a431  and     ecx, 0FFFFFFF8h
0x18000a434  test    byte ptr [r8], 4
0x18000a438  jz      short loc_18000A44F
0x18000a43a  mov     eax, [r8+8]
0x18000a43e  movsxd  r9, dword ptr [r8+4]
0x18000a442  neg     eax
0x18000a444  movsxd  rdx, eax
0x18000a447  add     r9, r10
0x18000a44a  and     r9, rdx
0x18000a44d  jmp     short loc_18000A452
0x18000a44f  mov     r9, r10
0x18000a452  movsxd  rax, ecx
0x18000a455  mov     rdx, [rax+r9]
0x18000a459  mov     rax, [r11+10h]
0x18000a45d  mov     ecx, [rax+8]
0x18000a460  mov     rax, [r11+8]
0x18000a464  test    byte ptr [rcx+rax+3], 0Fh
0x18000a469  jz      short loc_18000A47D
0x18000a46b  movzx   eax, byte ptr [rcx+rax+3]
0x18000a470  mov     ecx, 0FFFFFFF0h
0x18000a475  and     rax, rcx
0x18000a478  add     rax, r10
0x18000a47b  jmp     short loc_18000A480
0x18000a47d  mov     rax, r10
0x18000a480  xor     rdx, rax
0x18000a483  mov     rcx, rdx; StackCookie
0x18000a486  jmp     __security_check_cookie
```
