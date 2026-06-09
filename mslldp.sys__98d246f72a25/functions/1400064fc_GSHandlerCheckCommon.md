# __GSHandlerCheckCommon

- ea: `0x1400064fc`
- end: `0x14000656c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400064d8`

## callees

- `0x1400064fc`
- `0x140006630`

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
0x1400064fc  sub     rsp, 28h
0x140006500  mov     eax, [r8]
0x140006503  mov     r10, rcx
0x140006506  mov     ecx, eax
0x140006508  mov     r11, rdx
0x14000650b  and     ecx, 0FFFFFFF8h
0x14000650e  test    al, 4
0x140006510  jz      short loc_140006527
0x140006512  mov     eax, [r8+8]
0x140006516  movsxd  r9, dword ptr [r8+4]
0x14000651a  neg     eax
0x14000651c  movsxd  rdx, eax
0x14000651f  add     r9, r10
0x140006522  and     r9, rdx
0x140006525  jmp     short loc_14000652A
0x140006527  mov     r9, r10
0x14000652a  movsxd  rax, ecx
0x14000652d  mov     rdx, [rax+r9]
0x140006531  mov     rax, [r11+10h]
0x140006535  mov     ecx, [rax+8]
0x140006538  mov     rax, [r11+8]
0x14000653c  movzx   r8d, byte ptr [rcx+rax+3]
0x140006542  test    r8b, 0Fh
0x140006546  jz      short loc_140006558
0x140006548  mov     eax, r8d
0x14000654b  mov     ecx, 0FFFFFFF0h
0x140006550  and     rax, rcx
0x140006553  add     rax, r10
0x140006556  jmp     short loc_14000655B
0x140006558  mov     rax, r10
0x14000655b  xor     rdx, rax
0x14000655e  mov     rcx, rdx; StackCookie
0x140006561  call    __security_check_cookie
0x140006566  add     rsp, 28h
0x14000656a  retn
```
