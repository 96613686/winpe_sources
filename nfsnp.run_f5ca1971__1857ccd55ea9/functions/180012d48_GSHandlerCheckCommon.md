# __GSHandlerCheckCommon

- ea: `0x180012d48`
- end: `0x180012dab`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012d24`
- `0x180012db4`

## callees

- `0x180012d48`
- `0x180012e70`

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
0x180012d48  mov     r10, rcx
0x180012d4b  mov     r11, rdx
0x180012d4e  mov     ecx, [r8]
0x180012d51  and     ecx, 0FFFFFFF8h
0x180012d54  test    byte ptr [r8], 4
0x180012d58  jz      short loc_180012D6F
0x180012d5a  mov     eax, [r8+8]
0x180012d5e  movsxd  r9, dword ptr [r8+4]
0x180012d62  neg     eax
0x180012d64  movsxd  rdx, eax
0x180012d67  add     r9, r10
0x180012d6a  and     r9, rdx
0x180012d6d  jmp     short loc_180012D72
0x180012d6f  mov     r9, r10
0x180012d72  movsxd  rax, ecx
0x180012d75  mov     rdx, [rax+r9]
0x180012d79  mov     rax, [r11+10h]
0x180012d7d  mov     ecx, [rax+8]
0x180012d80  mov     rax, [r11+8]
0x180012d84  test    byte ptr [rcx+rax+3], 0Fh
0x180012d89  jz      short loc_180012D9D
0x180012d8b  movzx   eax, byte ptr [rcx+rax+3]
0x180012d90  mov     ecx, 0FFFFFFF0h
0x180012d95  and     rax, rcx
0x180012d98  add     rax, r10
0x180012d9b  jmp     short loc_180012DA0
0x180012d9d  mov     rax, r10
0x180012da0  xor     rdx, rax
0x180012da3  mov     rcx, rdx; StackCookie
0x180012da6  jmp     __security_check_cookie
```
