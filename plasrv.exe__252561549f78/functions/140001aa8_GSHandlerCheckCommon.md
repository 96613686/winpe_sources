# __GSHandlerCheckCommon

- ea: `0x140001aa8`
- end: `0x140001b0b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001a84`

## callees

- `0x140001aa8`
- `0x140001b30`

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
0x140001aa8  mov     r10, rcx
0x140001aab  mov     r11, rdx
0x140001aae  mov     ecx, [r8]
0x140001ab1  and     ecx, 0FFFFFFF8h
0x140001ab4  test    byte ptr [r8], 4
0x140001ab8  jz      short loc_140001ACF
0x140001aba  mov     eax, [r8+8]
0x140001abe  movsxd  r9, dword ptr [r8+4]
0x140001ac2  neg     eax
0x140001ac4  movsxd  rdx, eax
0x140001ac7  add     r9, r10
0x140001aca  and     r9, rdx
0x140001acd  jmp     short loc_140001AD2
0x140001acf  mov     r9, r10
0x140001ad2  movsxd  rax, ecx
0x140001ad5  mov     rdx, [rax+r9]
0x140001ad9  mov     rax, [r11+10h]
0x140001add  mov     ecx, [rax+8]
0x140001ae0  mov     rax, [r11+8]
0x140001ae4  test    byte ptr [rcx+rax+3], 0Fh
0x140001ae9  jz      short loc_140001AFD
0x140001aeb  movzx   eax, byte ptr [rcx+rax+3]
0x140001af0  mov     ecx, 0FFFFFFF0h
0x140001af5  and     rax, rcx
0x140001af8  add     rax, r10
0x140001afb  jmp     short loc_140001B00
0x140001afd  mov     rax, r10
0x140001b00  xor     rdx, rax
0x140001b03  mov     rcx, rdx; StackCookie
0x140001b06  jmp     __security_check_cookie
```
