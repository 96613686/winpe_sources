# __GSHandlerCheckCommon

- ea: `0x140003c0c`
- end: `0x140003c7c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003be8`
- `0x140003c84`

## callees

- `0x140003c0c`
- `0x140003dc0`

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
0x140003c0c  sub     rsp, 28h
0x140003c10  mov     eax, [r8]
0x140003c13  mov     r10, rcx
0x140003c16  mov     ecx, eax
0x140003c18  mov     r11, rdx
0x140003c1b  and     ecx, 0FFFFFFF8h
0x140003c1e  test    al, 4
0x140003c20  jz      short loc_140003C37
0x140003c22  mov     eax, [r8+8]
0x140003c26  movsxd  r9, dword ptr [r8+4]
0x140003c2a  neg     eax
0x140003c2c  movsxd  rdx, eax
0x140003c2f  add     r9, r10
0x140003c32  and     r9, rdx
0x140003c35  jmp     short loc_140003C3A
0x140003c37  mov     r9, r10
0x140003c3a  movsxd  rax, ecx
0x140003c3d  mov     rdx, [rax+r9]
0x140003c41  mov     rax, [r11+10h]
0x140003c45  mov     ecx, [rax+8]
0x140003c48  mov     rax, [r11+8]
0x140003c4c  movzx   r8d, byte ptr [rcx+rax+3]
0x140003c52  test    r8b, 0Fh
0x140003c56  jz      short loc_140003C68
0x140003c58  mov     eax, r8d
0x140003c5b  mov     ecx, 0FFFFFFF0h
0x140003c60  and     rax, rcx
0x140003c63  add     rax, r10
0x140003c66  jmp     short loc_140003C6B
0x140003c68  mov     rax, r10
0x140003c6b  xor     rdx, rax
0x140003c6e  mov     rcx, rdx; StackCookie
0x140003c71  call    __security_check_cookie
0x140003c76  add     rsp, 28h
0x140003c7a  retn
```
