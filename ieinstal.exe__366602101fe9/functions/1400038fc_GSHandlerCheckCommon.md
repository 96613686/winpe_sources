# __GSHandlerCheckCommon

- ea: `0x1400038fc`
- end: `0x14000395f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400038d8`

## callees

- `0x1400038fc`
- `0x1400109c0`

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
0x1400038fc  mov     r10, rcx
0x1400038ff  mov     r11, rdx
0x140003902  mov     ecx, [r8]
0x140003905  and     ecx, 0FFFFFFF8h
0x140003908  test    byte ptr [r8], 4
0x14000390c  jz      short loc_140003923
0x14000390e  mov     eax, [r8+8]
0x140003912  movsxd  r9, dword ptr [r8+4]
0x140003916  neg     eax
0x140003918  movsxd  rdx, eax
0x14000391b  add     r9, r10
0x14000391e  and     r9, rdx
0x140003921  jmp     short loc_140003926
0x140003923  mov     r9, r10
0x140003926  movsxd  rax, ecx
0x140003929  mov     rdx, [rax+r9]
0x14000392d  mov     rax, [r11+10h]
0x140003931  mov     ecx, [rax+8]
0x140003934  mov     rax, [r11+8]
0x140003938  test    byte ptr [rcx+rax+3], 0Fh
0x14000393d  jz      short loc_140003951
0x14000393f  movzx   eax, byte ptr [rcx+rax+3]
0x140003944  mov     ecx, 0FFFFFFF0h
0x140003949  and     rax, rcx
0x14000394c  add     rax, r10
0x14000394f  jmp     short loc_140003954
0x140003951  mov     rax, r10
0x140003954  xor     rdx, rax
0x140003957  mov     rcx, rdx; StackCookie
0x14000395a  jmp     __security_check_cookie
```
