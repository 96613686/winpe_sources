# __GSHandlerCheckCommon

- ea: `0x140009700`
- end: `0x140009763`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400096dc`
- `0x14000976c`

## callees

- `0x140009700`
- `0x140009820`

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
0x140009700  mov     r10, rcx
0x140009703  mov     r11, rdx
0x140009706  mov     ecx, [r8]
0x140009709  and     ecx, 0FFFFFFF8h
0x14000970c  test    byte ptr [r8], 4
0x140009710  jz      short loc_140009727
0x140009712  mov     eax, [r8+8]
0x140009716  movsxd  r9, dword ptr [r8+4]
0x14000971a  neg     eax
0x14000971c  movsxd  rdx, eax
0x14000971f  add     r9, r10
0x140009722  and     r9, rdx
0x140009725  jmp     short loc_14000972A
0x140009727  mov     r9, r10
0x14000972a  movsxd  rax, ecx
0x14000972d  mov     rdx, [rax+r9]
0x140009731  mov     rax, [r11+10h]
0x140009735  mov     ecx, [rax+8]
0x140009738  mov     rax, [r11+8]
0x14000973c  test    byte ptr [rcx+rax+3], 0Fh
0x140009741  jz      short loc_140009755
0x140009743  movzx   eax, byte ptr [rcx+rax+3]
0x140009748  mov     ecx, 0FFFFFFF0h
0x14000974d  and     rax, rcx
0x140009750  add     rax, r10
0x140009753  jmp     short loc_140009758
0x140009755  mov     rax, r10
0x140009758  xor     rdx, rax
0x14000975b  mov     rcx, rdx; StackCookie
0x14000975e  jmp     __security_check_cookie
```
