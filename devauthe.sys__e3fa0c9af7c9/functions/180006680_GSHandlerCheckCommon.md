# __GSHandlerCheckCommon

- ea: `0x180006680`
- end: `0x1800066f0`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000665c`

## callees

- `0x180006680`
- `0x1800067e0`

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
0x180006680  sub     rsp, 28h
0x180006684  mov     eax, [r8]
0x180006687  mov     r10, rcx
0x18000668a  mov     ecx, eax
0x18000668c  mov     r11, rdx
0x18000668f  and     ecx, 0FFFFFFF8h
0x180006692  test    al, 4
0x180006694  jz      short loc_1800066AB
0x180006696  mov     eax, [r8+8]
0x18000669a  movsxd  r9, dword ptr [r8+4]
0x18000669e  neg     eax
0x1800066a0  movsxd  rdx, eax
0x1800066a3  add     r9, r10
0x1800066a6  and     r9, rdx
0x1800066a9  jmp     short loc_1800066AE
0x1800066ab  mov     r9, r10
0x1800066ae  movsxd  rax, ecx
0x1800066b1  mov     rdx, [rax+r9]
0x1800066b5  mov     rax, [r11+10h]
0x1800066b9  mov     ecx, [rax+8]
0x1800066bc  mov     rax, [r11+8]
0x1800066c0  movzx   r8d, byte ptr [rcx+rax+3]
0x1800066c6  test    r8b, 0Fh
0x1800066ca  jz      short loc_1800066DC
0x1800066cc  mov     eax, r8d
0x1800066cf  mov     ecx, 0FFFFFFF0h
0x1800066d4  and     rax, rcx
0x1800066d7  add     rax, r10
0x1800066da  jmp     short loc_1800066DF
0x1800066dc  mov     rax, r10
0x1800066df  xor     rdx, rax
0x1800066e2  mov     rcx, rdx; StackCookie
0x1800066e5  call    __security_check_cookie
0x1800066ea  add     rsp, 28h
0x1800066ee  retn
```
