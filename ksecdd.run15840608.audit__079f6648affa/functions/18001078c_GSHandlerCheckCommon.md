# __GSHandlerCheckCommon

- ea: `0x18001078c`
- end: `0x1800107fc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010768`
- `0x180010804`

## callees

- `0x18001078c`
- `0x1800108a0`

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
0x18001078c  sub     rsp, 28h
0x180010790  mov     eax, [r8]
0x180010793  mov     r10, rcx
0x180010796  mov     ecx, eax
0x180010798  mov     r11, rdx
0x18001079b  and     ecx, 0FFFFFFF8h
0x18001079e  test    al, 4
0x1800107a0  jz      short loc_1800107B7
0x1800107a2  mov     eax, [r8+8]
0x1800107a6  movsxd  r9, dword ptr [r8+4]
0x1800107aa  neg     eax
0x1800107ac  movsxd  rdx, eax
0x1800107af  add     r9, r10
0x1800107b2  and     r9, rdx
0x1800107b5  jmp     short loc_1800107BA
0x1800107b7  mov     r9, r10
0x1800107ba  movsxd  rax, ecx
0x1800107bd  mov     rdx, [rax+r9]
0x1800107c1  mov     rax, [r11+10h]
0x1800107c5  mov     ecx, [rax+8]
0x1800107c8  mov     rax, [r11+8]
0x1800107cc  movzx   r8d, byte ptr [rcx+rax+3]
0x1800107d2  test    r8b, 0Fh
0x1800107d6  jz      short loc_1800107E8
0x1800107d8  mov     eax, r8d
0x1800107db  mov     ecx, 0FFFFFFF0h
0x1800107e0  and     rax, rcx
0x1800107e3  add     rax, r10
0x1800107e6  jmp     short loc_1800107EB
0x1800107e8  mov     rax, r10
0x1800107eb  xor     rdx, rax
0x1800107ee  mov     rcx, rdx; StackCookie
0x1800107f1  call    __security_check_cookie
0x1800107f6  add     rsp, 28h
0x1800107fa  retn
```
