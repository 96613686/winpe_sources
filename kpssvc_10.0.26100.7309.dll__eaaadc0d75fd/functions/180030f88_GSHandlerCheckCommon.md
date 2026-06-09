# __GSHandlerCheckCommon

- ea: `0x180030f88`
- end: `0x180030fe3`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180030f64`

## callees

- `0x180030f88`
- `0x180031040`

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
0x180030f88  push    rbx
0x180030f8a  mov     r11d, [r8]
0x180030f8d  mov     rbx, rdx
0x180030f90  and     r11d, 0FFFFFFF8h
0x180030f94  mov     r9, rcx
0x180030f97  test    byte ptr [r8], 4
0x180030f9b  mov     r10, rcx
0x180030f9e  jz      short loc_180030FB3
0x180030fa0  mov     eax, [r8+8]
0x180030fa4  movsxd  r10, dword ptr [r8+4]
0x180030fa8  neg     eax
0x180030faa  add     r10, rcx
0x180030fad  movsxd  rcx, eax
0x180030fb0  and     r10, rcx
0x180030fb3  movsxd  rax, r11d
0x180030fb6  mov     rdx, [rax+r10]
0x180030fba  mov     rax, [rbx+10h]
0x180030fbe  mov     ecx, [rax+8]
0x180030fc1  mov     rax, [rbx+8]
0x180030fc5  test    byte ptr [rcx+rax+3], 0Fh
0x180030fca  jz      short loc_180030FD7
0x180030fcc  movzx   eax, byte ptr [rcx+rax+3]
0x180030fd1  and     eax, 0FFFFFFF0h
0x180030fd4  add     r9, rax
0x180030fd7  xor     r9, rdx
0x180030fda  mov     rcx, r9; StackCookie
0x180030fdd  pop     rbx
0x180030fde  jmp     __security_check_cookie
```
