# __GSHandlerCheckCommon

- ea: `0x140010ddc`
- end: `0x140010e4c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010db8`

## callees

- `0x140010ddc`
- `0x140010f20`

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
0x140010ddc  sub     rsp, 28h
0x140010de0  mov     eax, [r8]
0x140010de3  mov     r10, rcx
0x140010de6  mov     ecx, eax
0x140010de8  mov     r11, rdx
0x140010deb  and     ecx, 0FFFFFFF8h
0x140010dee  test    al, 4
0x140010df0  jz      short loc_140010E07
0x140010df2  mov     eax, [r8+8]
0x140010df6  movsxd  r9, dword ptr [r8+4]
0x140010dfa  neg     eax
0x140010dfc  movsxd  rdx, eax
0x140010dff  add     r9, r10
0x140010e02  and     r9, rdx
0x140010e05  jmp     short loc_140010E0A
0x140010e07  mov     r9, r10
0x140010e0a  movsxd  rax, ecx
0x140010e0d  mov     rdx, [rax+r9]
0x140010e11  mov     rax, [r11+10h]
0x140010e15  mov     ecx, [rax+8]
0x140010e18  mov     rax, [r11+8]
0x140010e1c  movzx   r8d, byte ptr [rcx+rax+3]
0x140010e22  test    r8b, 0Fh
0x140010e26  jz      short loc_140010E38
0x140010e28  mov     eax, r8d
0x140010e2b  mov     ecx, 0FFFFFFF0h
0x140010e30  and     rax, rcx
0x140010e33  add     rax, r10
0x140010e36  jmp     short loc_140010E3B
0x140010e38  mov     rax, r10
0x140010e3b  xor     rdx, rax
0x140010e3e  mov     rcx, rdx; StackCookie
0x140010e41  call    __security_check_cookie
0x140010e46  add     rsp, 28h
0x140010e4a  retn
```
