# __GSHandlerCheckCommon

- ea: `0x14000360c`
- end: `0x14000367c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400035e8`

## callees

- `0x14000360c`
- `0x140003690`

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
0x14000360c  sub     rsp, 28h
0x140003610  mov     eax, [r8]
0x140003613  mov     r10, rcx
0x140003616  mov     ecx, eax
0x140003618  mov     r11, rdx
0x14000361b  and     ecx, 0FFFFFFF8h
0x14000361e  test    al, 4
0x140003620  jz      short loc_140003637
0x140003622  mov     eax, [r8+8]
0x140003626  movsxd  r9, dword ptr [r8+4]
0x14000362a  neg     eax
0x14000362c  movsxd  rdx, eax
0x14000362f  add     r9, r10
0x140003632  and     r9, rdx
0x140003635  jmp     short loc_14000363A
0x140003637  mov     r9, r10
0x14000363a  movsxd  rax, ecx
0x14000363d  mov     rdx, [rax+r9]
0x140003641  mov     rax, [r11+10h]
0x140003645  mov     ecx, [rax+8]
0x140003648  mov     rax, [r11+8]
0x14000364c  movzx   r8d, byte ptr [rcx+rax+3]
0x140003652  test    r8b, 0Fh
0x140003656  jz      short loc_140003668
0x140003658  mov     eax, r8d
0x14000365b  mov     ecx, 0FFFFFFF0h
0x140003660  and     rax, rcx
0x140003663  add     rax, r10
0x140003666  jmp     short loc_14000366B
0x140003668  mov     rax, r10
0x14000366b  xor     rdx, rax
0x14000366e  mov     rcx, rdx; StackCookie
0x140003671  call    __security_check_cookie
0x140003676  add     rsp, 28h
0x14000367a  retn
```
