# __GSHandlerCheckCommon

- ea: `0x180003aa8`
- end: `0x180003b0b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003a84`

## callees

- `0x180003aa8`
- `0x180003b50`

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
0x180003aa8  mov     r10, rcx
0x180003aab  mov     r11, rdx
0x180003aae  mov     ecx, [r8]
0x180003ab1  and     ecx, 0FFFFFFF8h
0x180003ab4  test    byte ptr [r8], 4
0x180003ab8  jz      short loc_180003ACF
0x180003aba  mov     eax, [r8+8]
0x180003abe  movsxd  r9, dword ptr [r8+4]
0x180003ac2  neg     eax
0x180003ac4  movsxd  rdx, eax
0x180003ac7  add     r9, r10
0x180003aca  and     r9, rdx
0x180003acd  jmp     short loc_180003AD2
0x180003acf  mov     r9, r10
0x180003ad2  movsxd  rax, ecx
0x180003ad5  mov     rdx, [rax+r9]
0x180003ad9  mov     rax, [r11+10h]
0x180003add  mov     ecx, [rax+8]
0x180003ae0  mov     rax, [r11+8]
0x180003ae4  test    byte ptr [rcx+rax+3], 0Fh
0x180003ae9  jz      short loc_180003AFD
0x180003aeb  movzx   eax, byte ptr [rcx+rax+3]
0x180003af0  mov     ecx, 0FFFFFFF0h
0x180003af5  and     rax, rcx
0x180003af8  add     rax, r10
0x180003afb  jmp     short loc_180003B00
0x180003afd  mov     rax, r10
0x180003b00  xor     rdx, rax
0x180003b03  mov     rcx, rdx; StackCookie
0x180003b06  jmp     __security_check_cookie
```
