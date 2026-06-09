# __GSHandlerCheckCommon

- ea: `0x1400013dc`
- end: `0x14000144c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400013b8`
- `0x140001454`

## callees

- `0x1400013dc`
- `0x1400014d0`

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
0x1400013dc  sub     rsp, 28h
0x1400013e0  mov     eax, [r8]
0x1400013e3  mov     r10, rcx
0x1400013e6  mov     ecx, eax
0x1400013e8  mov     r11, rdx
0x1400013eb  and     ecx, 0FFFFFFF8h
0x1400013ee  test    al, 4
0x1400013f0  jz      short loc_140001407
0x1400013f2  mov     eax, [r8+8]
0x1400013f6  movsxd  r9, dword ptr [r8+4]
0x1400013fa  neg     eax
0x1400013fc  movsxd  rdx, eax
0x1400013ff  add     r9, r10
0x140001402  and     r9, rdx
0x140001405  jmp     short loc_14000140A
0x140001407  mov     r9, r10
0x14000140a  movsxd  rax, ecx
0x14000140d  mov     rdx, [rax+r9]
0x140001411  mov     rax, [r11+10h]
0x140001415  mov     ecx, [rax+8]
0x140001418  mov     rax, [r11+8]
0x14000141c  movzx   r8d, byte ptr [rcx+rax+3]
0x140001422  test    r8b, 0Fh
0x140001426  jz      short loc_140001438
0x140001428  mov     eax, r8d
0x14000142b  mov     ecx, 0FFFFFFF0h
0x140001430  and     rax, rcx
0x140001433  add     rax, r10
0x140001436  jmp     short loc_14000143B
0x140001438  mov     rax, r10
0x14000143b  xor     rdx, rax
0x14000143e  mov     rcx, rdx; StackCookie
0x140001441  call    __security_check_cookie
0x140001446  add     rsp, 28h
0x14000144a  retn
```
