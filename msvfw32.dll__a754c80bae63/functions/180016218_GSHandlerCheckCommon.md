# __GSHandlerCheckCommon

- ea: `0x180016218`
- end: `0x18001627b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800161f4`
- `0x180016284`

## callees

- `0x1800014b0`
- `0x180016218`

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
0x180016218  mov     r10, rcx
0x18001621b  mov     r11, rdx
0x18001621e  mov     ecx, [r8]
0x180016221  and     ecx, 0FFFFFFF8h
0x180016224  test    byte ptr [r8], 4
0x180016228  jz      short loc_18001623F
0x18001622a  mov     eax, [r8+8]
0x18001622e  movsxd  r9, dword ptr [r8+4]
0x180016232  neg     eax
0x180016234  movsxd  rdx, eax
0x180016237  add     r9, r10
0x18001623a  and     r9, rdx
0x18001623d  jmp     short loc_180016242
0x18001623f  mov     r9, r10
0x180016242  movsxd  rax, ecx
0x180016245  mov     rdx, [rax+r9]
0x180016249  mov     rax, [r11+10h]
0x18001624d  mov     ecx, [rax+8]
0x180016250  mov     rax, [r11+8]
0x180016254  test    byte ptr [rcx+rax+3], 0Fh
0x180016259  jz      short loc_18001626D
0x18001625b  movzx   eax, byte ptr [rcx+rax+3]
0x180016260  mov     ecx, 0FFFFFFF0h
0x180016265  and     rax, rcx
0x180016268  add     rax, r10
0x18001626b  jmp     short loc_180016270
0x18001626d  mov     rax, r10
0x180016270  xor     rdx, rax
0x180016273  mov     rcx, rdx; StackCookie
0x180016276  jmp     __security_check_cookie
```
