# __GSHandlerCheckCommon

- ea: `0x140001cfc`
- end: `0x140001d6c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001cd8`
- `0x140001d74`

## callees

- `0x140001cfc`
- `0x140001e10`

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
0x140001cfc  sub     rsp, 28h
0x140001d00  mov     eax, [r8]
0x140001d03  mov     r10, rcx
0x140001d06  mov     ecx, eax
0x140001d08  mov     r11, rdx
0x140001d0b  and     ecx, 0FFFFFFF8h
0x140001d0e  test    al, 4
0x140001d10  jz      short loc_140001D27
0x140001d12  mov     eax, [r8+8]
0x140001d16  movsxd  r9, dword ptr [r8+4]
0x140001d1a  neg     eax
0x140001d1c  movsxd  rdx, eax
0x140001d1f  add     r9, r10
0x140001d22  and     r9, rdx
0x140001d25  jmp     short loc_140001D2A
0x140001d27  mov     r9, r10
0x140001d2a  movsxd  rax, ecx
0x140001d2d  mov     rdx, [rax+r9]
0x140001d31  mov     rax, [r11+10h]
0x140001d35  mov     ecx, [rax+8]
0x140001d38  mov     rax, [r11+8]
0x140001d3c  movzx   r8d, byte ptr [rcx+rax+3]
0x140001d42  test    r8b, 0Fh
0x140001d46  jz      short loc_140001D58
0x140001d48  mov     eax, r8d
0x140001d4b  mov     ecx, 0FFFFFFF0h
0x140001d50  and     rax, rcx
0x140001d53  add     rax, r10
0x140001d56  jmp     short loc_140001D5B
0x140001d58  mov     rax, r10
0x140001d5b  xor     rdx, rax
0x140001d5e  mov     rcx, rdx; StackCookie
0x140001d61  call    __security_check_cookie
0x140001d66  add     rsp, 28h
0x140001d6a  retn
```
