# __GSHandlerCheckCommon

- ea: `0x1800129a0`
- end: `0x180012a03`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001297c`

## callees

- `0x180002620`
- `0x1800129a0`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax

  v3 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  v4 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v3 + v4 + 3) & 0xF) != 0 )
    return a1 + (*(_BYTE *)(v3 + v4 + 3) & 0xF0);
  else
    return a1;
}

```

## disassembly

```asm
0x1800129a0  mov     r10, rcx
0x1800129a3  mov     r11, rdx
0x1800129a6  mov     ecx, [r8]
0x1800129a9  and     ecx, 0FFFFFFF8h
0x1800129ac  test    byte ptr [r8], 4
0x1800129b0  jz      short loc_1800129C7
0x1800129b2  mov     eax, [r8+8]
0x1800129b6  movsxd  r9, dword ptr [r8+4]
0x1800129ba  neg     eax
0x1800129bc  movsxd  rdx, eax
0x1800129bf  add     r9, r10
0x1800129c2  and     r9, rdx
0x1800129c5  jmp     short loc_1800129CA
0x1800129c7  mov     r9, r10
0x1800129ca  movsxd  rax, ecx
0x1800129cd  mov     rdx, [rax+r9]
0x1800129d1  mov     rax, [r11+10h]
0x1800129d5  mov     ecx, [rax+8]
0x1800129d8  mov     rax, [r11+8]
0x1800129dc  test    byte ptr [rcx+rax+3], 0Fh
0x1800129e1  jz      short loc_1800129F5
0x1800129e3  movzx   eax, byte ptr [rcx+rax+3]
0x1800129e8  mov     ecx, 0FFFFFFF0h
0x1800129ed  and     rax, rcx
0x1800129f0  add     rax, r10
0x1800129f3  jmp     short loc_1800129F8
0x1800129f5  mov     rax, r10
0x1800129f8  xor     rdx, rax
0x1800129fb  mov     rcx, rdx; StackCookie
0x1800129fe  jmp     __security_check_cookie
```
