# __GSHandlerCheckCommon

- ea: `0x14000759c`
- end: `0x14000760c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007578`

## callees

- `0x14000759c`
- `0x1400076d0`

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
0x14000759c  sub     rsp, 28h
0x1400075a0  mov     eax, [r8]
0x1400075a3  mov     r10, rcx
0x1400075a6  mov     ecx, eax
0x1400075a8  mov     r11, rdx
0x1400075ab  and     ecx, 0FFFFFFF8h
0x1400075ae  test    al, 4
0x1400075b0  jz      short loc_1400075C7
0x1400075b2  mov     eax, [r8+8]
0x1400075b6  movsxd  r9, dword ptr [r8+4]
0x1400075ba  neg     eax
0x1400075bc  movsxd  rdx, eax
0x1400075bf  add     r9, r10
0x1400075c2  and     r9, rdx
0x1400075c5  jmp     short loc_1400075CA
0x1400075c7  mov     r9, r10
0x1400075ca  movsxd  rax, ecx
0x1400075cd  mov     rdx, [rax+r9]
0x1400075d1  mov     rax, [r11+10h]
0x1400075d5  mov     ecx, [rax+8]
0x1400075d8  mov     rax, [r11+8]
0x1400075dc  movzx   r8d, byte ptr [rcx+rax+3]
0x1400075e2  test    r8b, 0Fh
0x1400075e6  jz      short loc_1400075F8
0x1400075e8  mov     eax, r8d
0x1400075eb  mov     ecx, 0FFFFFFF0h
0x1400075f0  and     rax, rcx
0x1400075f3  add     rax, r10
0x1400075f6  jmp     short loc_1400075FB
0x1400075f8  mov     rax, r10
0x1400075fb  xor     rdx, rax
0x1400075fe  mov     rcx, rdx; StackCookie
0x140007601  call    __security_check_cookie
0x140007606  add     rsp, 28h
0x14000760a  retn
```
