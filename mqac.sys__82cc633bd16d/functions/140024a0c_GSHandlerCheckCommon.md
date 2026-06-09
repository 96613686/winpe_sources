# __GSHandlerCheckCommon

- ea: `0x140024a0c`
- end: `0x140024a7c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400249e8`
- `0x140024a84`

## callees

- `0x140024a0c`
- `0x140024bb0`

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
0x140024a0c  sub     rsp, 28h
0x140024a10  mov     eax, [r8]
0x140024a13  mov     r10, rcx
0x140024a16  mov     ecx, eax
0x140024a18  mov     r11, rdx
0x140024a1b  and     ecx, 0FFFFFFF8h
0x140024a1e  test    al, 4
0x140024a20  jz      short loc_140024A37
0x140024a22  mov     eax, [r8+8]
0x140024a26  movsxd  r9, dword ptr [r8+4]
0x140024a2a  neg     eax
0x140024a2c  movsxd  rdx, eax
0x140024a2f  add     r9, r10
0x140024a32  and     r9, rdx
0x140024a35  jmp     short loc_140024A3A
0x140024a37  mov     r9, r10
0x140024a3a  movsxd  rax, ecx
0x140024a3d  mov     rdx, [rax+r9]
0x140024a41  mov     rax, [r11+10h]
0x140024a45  mov     ecx, [rax+8]
0x140024a48  mov     rax, [r11+8]
0x140024a4c  movzx   r8d, byte ptr [rcx+rax+3]
0x140024a52  test    r8b, 0Fh
0x140024a56  jz      short loc_140024A68
0x140024a58  mov     eax, r8d
0x140024a5b  mov     ecx, 0FFFFFFF0h
0x140024a60  and     rax, rcx
0x140024a63  add     rax, r10
0x140024a66  jmp     short loc_140024A6B
0x140024a68  mov     rax, r10
0x140024a6b  xor     rdx, rax
0x140024a6e  mov     rcx, rdx; StackCookie
0x140024a71  call    __security_check_cookie
0x140024a76  add     rsp, 28h
0x140024a7a  retn
```
