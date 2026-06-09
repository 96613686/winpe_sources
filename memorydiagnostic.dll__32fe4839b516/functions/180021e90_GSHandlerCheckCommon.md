# __GSHandlerCheckCommon

- ea: `0x180021e90`
- end: `0x180021eeb`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021e6c`
- `0x180021ef4`

## callees

- `0x1800026b0`
- `0x180021e90`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  result = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v2 + result + 3) & 0xF) != 0 )
    return *(_BYTE *)(v2 + result + 3) & 0xF0;
  return result;
}

```

## disassembly

```asm
0x180021e90  push    rbx
0x180021e92  mov     r11d, [r8]
0x180021e95  mov     rbx, rdx
0x180021e98  and     r11d, 0FFFFFFF8h
0x180021e9c  mov     r9, rcx
0x180021e9f  test    byte ptr [r8], 4
0x180021ea3  mov     r10, rcx
0x180021ea6  jz      short loc_180021EBB
0x180021ea8  mov     eax, [r8+8]
0x180021eac  movsxd  r10, dword ptr [r8+4]
0x180021eb0  neg     eax
0x180021eb2  add     r10, rcx
0x180021eb5  movsxd  rcx, eax
0x180021eb8  and     r10, rcx
0x180021ebb  movsxd  rax, r11d
0x180021ebe  mov     rdx, [rax+r10]
0x180021ec2  mov     rax, [rbx+10h]
0x180021ec6  mov     ecx, [rax+8]
0x180021ec9  mov     rax, [rbx+8]
0x180021ecd  test    byte ptr [rcx+rax+3], 0Fh
0x180021ed2  jz      short loc_180021EDF
0x180021ed4  movzx   eax, byte ptr [rcx+rax+3]
0x180021ed9  and     eax, 0FFFFFFF0h
0x180021edc  add     r9, rax
0x180021edf  xor     r9, rdx
0x180021ee2  mov     rcx, r9; StackCookie
0x180021ee5  pop     rbx
0x180021ee6  jmp     __security_check_cookie
```
