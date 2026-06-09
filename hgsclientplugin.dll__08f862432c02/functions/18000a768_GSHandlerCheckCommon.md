# __GSHandlerCheckCommon

- ea: `0x18000a768`
- end: `0x18000a7cb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a744`
- `0x18000a7d4`

## callees

- `0x180001520`
- `0x18000a768`

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
0x18000a768  mov     r10, rcx
0x18000a76b  mov     r11, rdx
0x18000a76e  mov     ecx, [r8]
0x18000a771  and     ecx, 0FFFFFFF8h
0x18000a774  test    byte ptr [r8], 4
0x18000a778  jz      short loc_18000A78F
0x18000a77a  mov     eax, [r8+8]
0x18000a77e  movsxd  r9, dword ptr [r8+4]
0x18000a782  neg     eax
0x18000a784  movsxd  rdx, eax
0x18000a787  add     r9, r10
0x18000a78a  and     r9, rdx
0x18000a78d  jmp     short loc_18000A792
0x18000a78f  mov     r9, r10
0x18000a792  movsxd  rax, ecx
0x18000a795  mov     rdx, [rax+r9]
0x18000a799  mov     rax, [r11+10h]
0x18000a79d  mov     ecx, [rax+8]
0x18000a7a0  mov     rax, [r11+8]
0x18000a7a4  test    byte ptr [rcx+rax+3], 0Fh
0x18000a7a9  jz      short loc_18000A7BD
0x18000a7ab  movzx   eax, byte ptr [rcx+rax+3]
0x18000a7b0  mov     ecx, 0FFFFFFF0h
0x18000a7b5  and     rax, rcx
0x18000a7b8  add     rax, r10
0x18000a7bb  jmp     short loc_18000A7C0
0x18000a7bd  mov     rax, r10
0x18000a7c0  xor     rdx, rax
0x18000a7c3  mov     rcx, rdx; StackCookie
0x18000a7c6  jmp     __security_check_cookie
```
