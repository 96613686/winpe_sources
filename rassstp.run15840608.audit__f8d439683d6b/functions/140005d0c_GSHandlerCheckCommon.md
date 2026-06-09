# __GSHandlerCheckCommon

- ea: `0x140005d0c`
- end: `0x140005d7c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005ce8`
- `0x140005d84`

## callees

- `0x140005d0c`
- `0x140005e10`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  int v2; // r8d

  v2 = *(unsigned __int8 *)(*(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL) + *(_QWORD *)(a2 + 8) + 3LL);
  if ( (v2 & 0xF) != 0 )
    return a1 + (v2 & 0xFFFFFFF0);
  else
    return a1;
}

```

## disassembly

```asm
0x140005d0c  sub     rsp, 28h
0x140005d10  mov     eax, [r8]
0x140005d13  mov     r10, rcx
0x140005d16  mov     ecx, eax
0x140005d18  mov     r11, rdx
0x140005d1b  and     ecx, 0FFFFFFF8h
0x140005d1e  test    al, 4
0x140005d20  jz      short loc_140005D37
0x140005d22  mov     eax, [r8+8]
0x140005d26  movsxd  r9, dword ptr [r8+4]
0x140005d2a  neg     eax
0x140005d2c  movsxd  rdx, eax
0x140005d2f  add     r9, r10
0x140005d32  and     r9, rdx
0x140005d35  jmp     short loc_140005D3A
0x140005d37  mov     r9, r10
0x140005d3a  movsxd  rax, ecx
0x140005d3d  mov     rdx, [rax+r9]
0x140005d41  mov     rax, [r11+10h]
0x140005d45  mov     ecx, [rax+8]
0x140005d48  mov     rax, [r11+8]
0x140005d4c  movzx   r8d, byte ptr [rcx+rax+3]
0x140005d52  test    r8b, 0Fh
0x140005d56  jz      short loc_140005D68
0x140005d58  mov     eax, r8d
0x140005d5b  mov     ecx, 0FFFFFFF0h
0x140005d60  and     rax, rcx
0x140005d63  add     rax, r10
0x140005d66  jmp     short loc_140005D6B
0x140005d68  mov     rax, r10
0x140005d6b  xor     rdx, rax
0x140005d6e  mov     rcx, rdx; StackCookie
0x140005d71  call    __security_check_cookie
0x140005d76  add     rsp, 28h
0x140005d7a  retn
```
