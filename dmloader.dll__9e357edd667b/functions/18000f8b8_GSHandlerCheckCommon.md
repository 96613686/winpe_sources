# __GSHandlerCheckCommon

- ea: `0x18000f8b8`
- end: `0x18000f91b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f894`

## callees

- `0x1800015d0`
- `0x18000f8b8`

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
0x18000f8b8  mov     r10, rcx
0x18000f8bb  mov     r11, rdx
0x18000f8be  mov     ecx, [r8]
0x18000f8c1  and     ecx, 0FFFFFFF8h
0x18000f8c4  test    byte ptr [r8], 4
0x18000f8c8  jz      short loc_18000F8DF
0x18000f8ca  mov     eax, [r8+8]
0x18000f8ce  movsxd  r9, dword ptr [r8+4]
0x18000f8d2  neg     eax
0x18000f8d4  movsxd  rdx, eax
0x18000f8d7  add     r9, r10
0x18000f8da  and     r9, rdx
0x18000f8dd  jmp     short loc_18000F8E2
0x18000f8df  mov     r9, r10
0x18000f8e2  movsxd  rax, ecx
0x18000f8e5  mov     rdx, [rax+r9]
0x18000f8e9  mov     rax, [r11+10h]
0x18000f8ed  mov     ecx, [rax+8]
0x18000f8f0  mov     rax, [r11+8]
0x18000f8f4  test    byte ptr [rcx+rax+3], 0Fh
0x18000f8f9  jz      short loc_18000F90D
0x18000f8fb  movzx   eax, byte ptr [rcx+rax+3]
0x18000f900  mov     ecx, 0FFFFFFF0h
0x18000f905  and     rax, rcx
0x18000f908  add     rax, r10
0x18000f90b  jmp     short loc_18000F910
0x18000f90d  mov     rax, r10
0x18000f910  xor     rdx, rax
0x18000f913  mov     rcx, rdx; StackCookie
0x18000f916  jmp     __security_check_cookie
```
