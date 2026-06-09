# __GSHandlerCheckCommon

- ea: `0x140006ecc`
- end: `0x140006f3c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006ea8`

## callees

- `0x140006ecc`
- `0x140010160`

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
0x140006ecc  sub     rsp, 28h
0x140006ed0  mov     eax, [r8]
0x140006ed3  mov     r10, rcx
0x140006ed6  mov     ecx, eax
0x140006ed8  mov     r11, rdx
0x140006edb  and     ecx, 0FFFFFFF8h
0x140006ede  test    al, 4
0x140006ee0  jz      short loc_140006EF7
0x140006ee2  mov     eax, [r8+8]
0x140006ee6  movsxd  r9, dword ptr [r8+4]
0x140006eea  neg     eax
0x140006eec  movsxd  rdx, eax
0x140006eef  add     r9, r10
0x140006ef2  and     r9, rdx
0x140006ef5  jmp     short loc_140006EFA
0x140006ef7  mov     r9, r10
0x140006efa  movsxd  rax, ecx
0x140006efd  mov     rdx, [rax+r9]
0x140006f01  mov     rax, [r11+10h]
0x140006f05  mov     ecx, [rax+8]
0x140006f08  mov     rax, [r11+8]
0x140006f0c  movzx   r8d, byte ptr [rcx+rax+3]
0x140006f12  test    r8b, 0Fh
0x140006f16  jz      short loc_140006F28
0x140006f18  mov     eax, r8d
0x140006f1b  mov     ecx, 0FFFFFFF0h
0x140006f20  and     rax, rcx
0x140006f23  add     rax, r10
0x140006f26  jmp     short loc_140006F2B
0x140006f28  mov     rax, r10
0x140006f2b  xor     rdx, rax
0x140006f2e  mov     rcx, rdx; StackCookie
0x140006f31  call    __security_check_cookie
0x140006f36  add     rsp, 28h
0x140006f3a  retn
```
