# __GSHandlerCheckCommon

- ea: `0x18001a998`
- end: `0x18001a9fb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a974`
- `0x18001aa04`

## callees

- `0x18001a998`
- `0x18001aac0`

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
0x18001a998  mov     r10, rcx
0x18001a99b  mov     r11, rdx
0x18001a99e  mov     ecx, [r8]
0x18001a9a1  and     ecx, 0FFFFFFF8h
0x18001a9a4  test    byte ptr [r8], 4
0x18001a9a8  jz      short loc_18001A9BF
0x18001a9aa  mov     eax, [r8+8]
0x18001a9ae  movsxd  r9, dword ptr [r8+4]
0x18001a9b2  neg     eax
0x18001a9b4  movsxd  rdx, eax
0x18001a9b7  add     r9, r10
0x18001a9ba  and     r9, rdx
0x18001a9bd  jmp     short loc_18001A9C2
0x18001a9bf  mov     r9, r10
0x18001a9c2  movsxd  rax, ecx
0x18001a9c5  mov     rdx, [rax+r9]
0x18001a9c9  mov     rax, [r11+10h]
0x18001a9cd  mov     ecx, [rax+8]
0x18001a9d0  mov     rax, [r11+8]
0x18001a9d4  test    byte ptr [rcx+rax+3], 0Fh
0x18001a9d9  jz      short loc_18001A9ED
0x18001a9db  movzx   eax, byte ptr [rcx+rax+3]
0x18001a9e0  mov     ecx, 0FFFFFFF0h
0x18001a9e5  and     rax, rcx
0x18001a9e8  add     rax, r10
0x18001a9eb  jmp     short loc_18001A9F0
0x18001a9ed  mov     rax, r10
0x18001a9f0  xor     rdx, rax
0x18001a9f3  mov     rcx, rdx; StackCookie
0x18001a9f6  jmp     __security_check_cookie
```
