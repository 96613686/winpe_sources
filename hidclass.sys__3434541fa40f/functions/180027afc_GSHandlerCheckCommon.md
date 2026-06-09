# __GSHandlerCheckCommon

- ea: `0x180027afc`
- end: `0x180027b6c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027ad8`

## callees

- `0x180027afc`
- `0x180027ba0`

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
0x180027afc  sub     rsp, 28h
0x180027b00  mov     eax, [r8]
0x180027b03  mov     r10, rcx
0x180027b06  mov     ecx, eax
0x180027b08  mov     r11, rdx
0x180027b0b  and     ecx, 0FFFFFFF8h
0x180027b0e  test    al, 4
0x180027b10  jz      short loc_180027B27
0x180027b12  mov     eax, [r8+8]
0x180027b16  movsxd  r9, dword ptr [r8+4]
0x180027b1a  neg     eax
0x180027b1c  movsxd  rdx, eax
0x180027b1f  add     r9, r10
0x180027b22  and     r9, rdx
0x180027b25  jmp     short loc_180027B2A
0x180027b27  mov     r9, r10
0x180027b2a  movsxd  rax, ecx
0x180027b2d  mov     rdx, [rax+r9]
0x180027b31  mov     rax, [r11+10h]
0x180027b35  mov     ecx, [rax+8]
0x180027b38  mov     rax, [r11+8]
0x180027b3c  movzx   r8d, byte ptr [rcx+rax+3]
0x180027b42  test    r8b, 0Fh
0x180027b46  jz      short loc_180027B58
0x180027b48  mov     eax, r8d
0x180027b4b  mov     ecx, 0FFFFFFF0h
0x180027b50  and     rax, rcx
0x180027b53  add     rax, r10
0x180027b56  jmp     short loc_180027B5B
0x180027b58  mov     rax, r10
0x180027b5b  xor     rdx, rax
0x180027b5e  mov     rcx, rdx; StackCookie
0x180027b61  call    __security_check_cookie
0x180027b66  add     rsp, 28h
0x180027b6a  retn
```
