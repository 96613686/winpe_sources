# __GSHandlerCheckCommon

- ea: `0x180006700`
- end: `0x180006763`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800066dc`

## callees

- `0x180006700`
- `0x1800067c0`

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
0x180006700  mov     r10, rcx
0x180006703  mov     r11, rdx
0x180006706  mov     ecx, [r8]
0x180006709  and     ecx, 0FFFFFFF8h
0x18000670c  test    byte ptr [r8], 4
0x180006710  jz      short loc_180006727
0x180006712  mov     eax, [r8+8]
0x180006716  movsxd  r9, dword ptr [r8+4]
0x18000671a  neg     eax
0x18000671c  movsxd  rdx, eax
0x18000671f  add     r9, r10
0x180006722  and     r9, rdx
0x180006725  jmp     short loc_18000672A
0x180006727  mov     r9, r10
0x18000672a  movsxd  rax, ecx
0x18000672d  mov     rdx, [rax+r9]
0x180006731  mov     rax, [r11+10h]
0x180006735  mov     ecx, [rax+8]
0x180006738  mov     rax, [r11+8]
0x18000673c  test    byte ptr [rcx+rax+3], 0Fh
0x180006741  jz      short loc_180006755
0x180006743  movzx   eax, byte ptr [rcx+rax+3]
0x180006748  mov     ecx, 0FFFFFFF0h
0x18000674d  and     rax, rcx
0x180006750  add     rax, r10
0x180006753  jmp     short loc_180006758
0x180006755  mov     rax, r10
0x180006758  xor     rdx, rax
0x18000675b  mov     rcx, rdx; StackCookie
0x18000675e  jmp     __security_check_cookie
```
