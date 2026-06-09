# __GSHandlerCheckCommon

- ea: `0x14000f998`
- end: `0x14000f9fb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000f974`
- `0x14000fa04`

## callees

- `0x140001340`
- `0x14000f998`

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
0x14000f998  mov     r10, rcx
0x14000f99b  mov     r11, rdx
0x14000f99e  mov     ecx, [r8]
0x14000f9a1  and     ecx, 0FFFFFFF8h
0x14000f9a4  test    byte ptr [r8], 4
0x14000f9a8  jz      short loc_14000F9BF
0x14000f9aa  mov     eax, [r8+8]
0x14000f9ae  movsxd  r9, dword ptr [r8+4]
0x14000f9b2  neg     eax
0x14000f9b4  movsxd  rdx, eax
0x14000f9b7  add     r9, r10
0x14000f9ba  and     r9, rdx
0x14000f9bd  jmp     short loc_14000F9C2
0x14000f9bf  mov     r9, r10
0x14000f9c2  movsxd  rax, ecx
0x14000f9c5  mov     rdx, [rax+r9]
0x14000f9c9  mov     rax, [r11+10h]
0x14000f9cd  mov     ecx, [rax+8]
0x14000f9d0  mov     rax, [r11+8]
0x14000f9d4  test    byte ptr [rcx+rax+3], 0Fh
0x14000f9d9  jz      short loc_14000F9ED
0x14000f9db  movzx   eax, byte ptr [rcx+rax+3]
0x14000f9e0  mov     ecx, 0FFFFFFF0h
0x14000f9e5  and     rax, rcx
0x14000f9e8  add     rax, r10
0x14000f9eb  jmp     short loc_14000F9F0
0x14000f9ed  mov     rax, r10
0x14000f9f0  xor     rdx, rax
0x14000f9f3  mov     rcx, rdx; StackCookie
0x14000f9f6  jmp     __security_check_cookie
```
