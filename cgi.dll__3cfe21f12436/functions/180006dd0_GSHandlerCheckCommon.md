# __GSHandlerCheckCommon

- ea: `0x180006dd0`
- end: `0x180006e33`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006dac`

## callees

- `0x180006dd0`
- `0x180006e90`

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
0x180006dd0  mov     r10, rcx
0x180006dd3  mov     r11, rdx
0x180006dd6  mov     ecx, [r8]
0x180006dd9  and     ecx, 0FFFFFFF8h
0x180006ddc  test    byte ptr [r8], 4
0x180006de0  jz      short loc_180006DF7
0x180006de2  mov     eax, [r8+8]
0x180006de6  movsxd  r9, dword ptr [r8+4]
0x180006dea  neg     eax
0x180006dec  movsxd  rdx, eax
0x180006def  add     r9, r10
0x180006df2  and     r9, rdx
0x180006df5  jmp     short loc_180006DFA
0x180006df7  mov     r9, r10
0x180006dfa  movsxd  rax, ecx
0x180006dfd  mov     rdx, [rax+r9]
0x180006e01  mov     rax, [r11+10h]
0x180006e05  mov     ecx, [rax+8]
0x180006e08  mov     rax, [r11+8]
0x180006e0c  test    byte ptr [rcx+rax+3], 0Fh
0x180006e11  jz      short loc_180006E25
0x180006e13  movzx   eax, byte ptr [rcx+rax+3]
0x180006e18  mov     ecx, 0FFFFFFF0h
0x180006e1d  and     rax, rcx
0x180006e20  add     rax, r10
0x180006e23  jmp     short loc_180006E28
0x180006e25  mov     rax, r10
0x180006e28  xor     rdx, rax
0x180006e2b  mov     rcx, rdx; StackCookie
0x180006e2e  jmp     __security_check_cookie
```
