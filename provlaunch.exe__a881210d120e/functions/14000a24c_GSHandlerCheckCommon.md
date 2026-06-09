# __GSHandlerCheckCommon

- ea: `0x14000a24c`
- end: `0x14000a2af`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000a228`
- `0x14000a2b8`

## callees

- `0x14000a24c`
- `0x14000a370`

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
0x14000a24c  mov     r10, rcx
0x14000a24f  mov     r11, rdx
0x14000a252  mov     ecx, [r8]
0x14000a255  and     ecx, 0FFFFFFF8h
0x14000a258  test    byte ptr [r8], 4
0x14000a25c  jz      short loc_14000A273
0x14000a25e  mov     eax, [r8+8]
0x14000a262  movsxd  r9, dword ptr [r8+4]
0x14000a266  neg     eax
0x14000a268  movsxd  rdx, eax
0x14000a26b  add     r9, r10
0x14000a26e  and     r9, rdx
0x14000a271  jmp     short loc_14000A276
0x14000a273  mov     r9, r10
0x14000a276  movsxd  rax, ecx
0x14000a279  mov     rdx, [rax+r9]
0x14000a27d  mov     rax, [r11+10h]
0x14000a281  mov     ecx, [rax+8]
0x14000a284  mov     rax, [r11+8]
0x14000a288  test    byte ptr [rcx+rax+3], 0Fh
0x14000a28d  jz      short loc_14000A2A1
0x14000a28f  movzx   eax, byte ptr [rcx+rax+3]
0x14000a294  mov     ecx, 0FFFFFFF0h
0x14000a299  and     rax, rcx
0x14000a29c  add     rax, r10
0x14000a29f  jmp     short loc_14000A2A4
0x14000a2a1  mov     rax, r10
0x14000a2a4  xor     rdx, rax
0x14000a2a7  mov     rcx, rdx; StackCookie
0x14000a2aa  jmp     __security_check_cookie
```
