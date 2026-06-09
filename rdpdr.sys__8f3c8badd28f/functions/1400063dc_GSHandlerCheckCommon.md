# __GSHandlerCheckCommon

- ea: `0x1400063dc`
- end: `0x14000644c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400063b8`

## callees

- `0x1400063dc`
- `0x140006480`

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
0x1400063dc  sub     rsp, 28h
0x1400063e0  mov     eax, [r8]
0x1400063e3  mov     r10, rcx
0x1400063e6  mov     ecx, eax
0x1400063e8  mov     r11, rdx
0x1400063eb  and     ecx, 0FFFFFFF8h
0x1400063ee  test    al, 4
0x1400063f0  jz      short loc_140006407
0x1400063f2  mov     eax, [r8+8]
0x1400063f6  movsxd  r9, dword ptr [r8+4]
0x1400063fa  neg     eax
0x1400063fc  movsxd  rdx, eax
0x1400063ff  add     r9, r10
0x140006402  and     r9, rdx
0x140006405  jmp     short loc_14000640A
0x140006407  mov     r9, r10
0x14000640a  movsxd  rax, ecx
0x14000640d  mov     rdx, [rax+r9]
0x140006411  mov     rax, [r11+10h]
0x140006415  mov     ecx, [rax+8]
0x140006418  mov     rax, [r11+8]
0x14000641c  movzx   r8d, byte ptr [rcx+rax+3]
0x140006422  test    r8b, 0Fh
0x140006426  jz      short loc_140006438
0x140006428  mov     eax, r8d
0x14000642b  mov     ecx, 0FFFFFFF0h
0x140006430  and     rax, rcx
0x140006433  add     rax, r10
0x140006436  jmp     short loc_14000643B
0x140006438  mov     rax, r10
0x14000643b  xor     rdx, rax
0x14000643e  mov     rcx, rdx; StackCookie
0x140006441  call    __security_check_cookie
0x140006446  add     rsp, 28h
0x14000644a  retn
```
