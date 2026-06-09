# __GSHandlerCheckCommon

- ea: `0x1800095a4`
- end: `0x180009607`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009580`
- `0x180009610`

## callees

- `0x1800095a4`
- `0x1800096b0`

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
0x1800095a4  mov     r10, rcx
0x1800095a7  mov     r11, rdx
0x1800095aa  mov     ecx, [r8]
0x1800095ad  and     ecx, 0FFFFFFF8h
0x1800095b0  test    byte ptr [r8], 4
0x1800095b4  jz      short loc_1800095CB
0x1800095b6  mov     eax, [r8+8]
0x1800095ba  movsxd  r9, dword ptr [r8+4]
0x1800095be  neg     eax
0x1800095c0  movsxd  rdx, eax
0x1800095c3  add     r9, r10
0x1800095c6  and     r9, rdx
0x1800095c9  jmp     short loc_1800095CE
0x1800095cb  mov     r9, r10
0x1800095ce  movsxd  rax, ecx
0x1800095d1  mov     rdx, [rax+r9]
0x1800095d5  mov     rax, [r11+10h]
0x1800095d9  mov     ecx, [rax+8]
0x1800095dc  mov     rax, [r11+8]
0x1800095e0  test    byte ptr [rcx+rax+3], 0Fh
0x1800095e5  jz      short loc_1800095F9
0x1800095e7  movzx   eax, byte ptr [rcx+rax+3]
0x1800095ec  mov     ecx, 0FFFFFFF0h
0x1800095f1  and     rax, rcx
0x1800095f4  add     rax, r10
0x1800095f7  jmp     short loc_1800095FC
0x1800095f9  mov     rax, r10
0x1800095fc  xor     rdx, rax
0x1800095ff  mov     rcx, rdx; StackCookie
0x180009602  jmp     __security_check_cookie
```
