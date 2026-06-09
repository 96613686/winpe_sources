# __GSHandlerCheckCommon

- ea: `0x140006a0c`
- end: `0x140006a7c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400069e8`

## callees

- `0x140006a0c`
- `0x140006b40`

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
0x140006a0c  sub     rsp, 28h
0x140006a10  mov     eax, [r8]
0x140006a13  mov     r10, rcx
0x140006a16  mov     ecx, eax
0x140006a18  mov     r11, rdx
0x140006a1b  and     ecx, 0FFFFFFF8h
0x140006a1e  test    al, 4
0x140006a20  jz      short loc_140006A37
0x140006a22  mov     eax, [r8+8]
0x140006a26  movsxd  r9, dword ptr [r8+4]
0x140006a2a  neg     eax
0x140006a2c  movsxd  rdx, eax
0x140006a2f  add     r9, r10
0x140006a32  and     r9, rdx
0x140006a35  jmp     short loc_140006A3A
0x140006a37  mov     r9, r10
0x140006a3a  movsxd  rax, ecx
0x140006a3d  mov     rdx, [rax+r9]
0x140006a41  mov     rax, [r11+10h]
0x140006a45  mov     ecx, [rax+8]
0x140006a48  mov     rax, [r11+8]
0x140006a4c  movzx   r8d, byte ptr [rcx+rax+3]
0x140006a52  test    r8b, 0Fh
0x140006a56  jz      short loc_140006A68
0x140006a58  mov     eax, r8d
0x140006a5b  mov     ecx, 0FFFFFFF0h
0x140006a60  and     rax, rcx
0x140006a63  add     rax, r10
0x140006a66  jmp     short loc_140006A6B
0x140006a68  mov     rax, r10
0x140006a6b  xor     rdx, rax
0x140006a6e  mov     rcx, rdx; StackCookie
0x140006a71  call    __security_check_cookie
0x140006a76  add     rsp, 28h
0x140006a7a  retn
```
