# __GSHandlerCheckCommon

- ea: `0x180012b58`
- end: `0x180012bb3`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012b38`
- `0x180012c10`
- `0x18001edf0`

## callees

- `0x180012b58`
- `0x180012bd0`

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
0x180012b58  push    rbx
0x180012b5a  mov     r11d, [r8]
0x180012b5d  mov     rbx, rdx
0x180012b60  and     r11d, 0FFFFFFF8h
0x180012b64  mov     r9, rcx
0x180012b67  test    byte ptr [r8], 4
0x180012b6b  mov     r10, rcx
0x180012b6e  jz      short loc_180012B83
0x180012b70  mov     eax, [r8+8]
0x180012b74  movsxd  r10, dword ptr [r8+4]
0x180012b78  neg     eax
0x180012b7a  add     r10, rcx
0x180012b7d  movsxd  rcx, eax
0x180012b80  and     r10, rcx
0x180012b83  movsxd  rax, r11d
0x180012b86  mov     rdx, [rax+r10]
0x180012b8a  mov     rax, [rbx+10h]
0x180012b8e  mov     ecx, [rax+8]
0x180012b91  mov     rax, [rbx+8]
0x180012b95  test    byte ptr [rcx+rax+3], 0Fh
0x180012b9a  jz      short loc_180012BA7
0x180012b9c  movzx   eax, byte ptr [rcx+rax+3]
0x180012ba1  and     eax, 0FFFFFFF0h
0x180012ba4  add     r9, rax
0x180012ba7  xor     r9, rdx
0x180012baa  mov     rcx, r9; StackCookie
0x180012bad  pop     rbx
0x180012bae  jmp     __security_check_cookie
```
