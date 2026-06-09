# __GSHandlerCheckCommon

- ea: `0x180009da8`
- end: `0x180009e0b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009d84`

## callees

- `0x180009da8`
- `0x180009e40`

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
0x180009da8  mov     r10, rcx
0x180009dab  mov     r11, rdx
0x180009dae  mov     ecx, [r8]
0x180009db1  and     ecx, 0FFFFFFF8h
0x180009db4  test    byte ptr [r8], 4
0x180009db8  jz      short loc_180009DCF
0x180009dba  mov     eax, [r8+8]
0x180009dbe  movsxd  r9, dword ptr [r8+4]
0x180009dc2  neg     eax
0x180009dc4  movsxd  rdx, eax
0x180009dc7  add     r9, r10
0x180009dca  and     r9, rdx
0x180009dcd  jmp     short loc_180009DD2
0x180009dcf  mov     r9, r10
0x180009dd2  movsxd  rax, ecx
0x180009dd5  mov     rdx, [rax+r9]
0x180009dd9  mov     rax, [r11+10h]
0x180009ddd  mov     ecx, [rax+8]
0x180009de0  mov     rax, [r11+8]
0x180009de4  test    byte ptr [rcx+rax+3], 0Fh
0x180009de9  jz      short loc_180009DFD
0x180009deb  movzx   eax, byte ptr [rcx+rax+3]
0x180009df0  mov     ecx, 0FFFFFFF0h
0x180009df5  and     rax, rcx
0x180009df8  add     rax, r10
0x180009dfb  jmp     short loc_180009E00
0x180009dfd  mov     rax, r10
0x180009e00  xor     rdx, rax
0x180009e03  mov     rcx, rdx; StackCookie
0x180009e06  jmp     __security_check_cookie
```
