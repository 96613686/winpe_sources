# __GSHandlerCheckCommon

- ea: `0x18000a740`
- end: `0x18000a7a3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a71c`

## callees

- `0x18000a740`
- `0x18000a800`

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
0x18000a740  mov     r10, rcx
0x18000a743  mov     r11, rdx
0x18000a746  mov     ecx, [r8]
0x18000a749  and     ecx, 0FFFFFFF8h
0x18000a74c  test    byte ptr [r8], 4
0x18000a750  jz      short loc_18000A767
0x18000a752  mov     eax, [r8+8]
0x18000a756  movsxd  r9, dword ptr [r8+4]
0x18000a75a  neg     eax
0x18000a75c  movsxd  rdx, eax
0x18000a75f  add     r9, r10
0x18000a762  and     r9, rdx
0x18000a765  jmp     short loc_18000A76A
0x18000a767  mov     r9, r10
0x18000a76a  movsxd  rax, ecx
0x18000a76d  mov     rdx, [rax+r9]
0x18000a771  mov     rax, [r11+10h]
0x18000a775  mov     ecx, [rax+8]
0x18000a778  mov     rax, [r11+8]
0x18000a77c  test    byte ptr [rcx+rax+3], 0Fh
0x18000a781  jz      short loc_18000A795
0x18000a783  movzx   eax, byte ptr [rcx+rax+3]
0x18000a788  mov     ecx, 0FFFFFFF0h
0x18000a78d  and     rax, rcx
0x18000a790  add     rax, r10
0x18000a793  jmp     short loc_18000A798
0x18000a795  mov     rax, r10
0x18000a798  xor     rdx, rax
0x18000a79b  mov     rcx, rdx; StackCookie
0x18000a79e  jmp     __security_check_cookie
```
