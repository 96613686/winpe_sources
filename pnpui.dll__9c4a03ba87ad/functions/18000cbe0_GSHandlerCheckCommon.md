# __GSHandlerCheckCommon

- ea: `0x18000cbe0`
- end: `0x18000cc43`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cbbc`
- `0x18000cc4c`

## callees

- `0x18000cbe0`
- `0x18000cd10`

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
0x18000cbe0  mov     r10, rcx
0x18000cbe3  mov     r11, rdx
0x18000cbe6  mov     ecx, [r8]
0x18000cbe9  and     ecx, 0FFFFFFF8h
0x18000cbec  test    byte ptr [r8], 4
0x18000cbf0  jz      short loc_18000CC07
0x18000cbf2  mov     eax, [r8+8]
0x18000cbf6  movsxd  r9, dword ptr [r8+4]
0x18000cbfa  neg     eax
0x18000cbfc  movsxd  rdx, eax
0x18000cbff  add     r9, r10
0x18000cc02  and     r9, rdx
0x18000cc05  jmp     short loc_18000CC0A
0x18000cc07  mov     r9, r10
0x18000cc0a  movsxd  rax, ecx
0x18000cc0d  mov     rdx, [rax+r9]
0x18000cc11  mov     rax, [r11+10h]
0x18000cc15  mov     ecx, [rax+8]
0x18000cc18  mov     rax, [r11+8]
0x18000cc1c  test    byte ptr [rcx+rax+3], 0Fh
0x18000cc21  jz      short loc_18000CC35
0x18000cc23  movzx   eax, byte ptr [rcx+rax+3]
0x18000cc28  mov     ecx, 0FFFFFFF0h
0x18000cc2d  and     rax, rcx
0x18000cc30  add     rax, r10
0x18000cc33  jmp     short loc_18000CC38
0x18000cc35  mov     rax, r10
0x18000cc38  xor     rdx, rax
0x18000cc3b  mov     rcx, rdx; StackCookie
0x18000cc3e  jmp     __security_check_cookie
```
