# __GSHandlerCheckCommon

- ea: `0x14000670c`
- end: `0x14000677c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400066e8`

## callees

- `0x14000670c`
- `0x1400067a0`

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
0x14000670c  sub     rsp, 28h
0x140006710  mov     eax, [r8]
0x140006713  mov     r10, rcx
0x140006716  mov     ecx, eax
0x140006718  mov     r11, rdx
0x14000671b  and     ecx, 0FFFFFFF8h
0x14000671e  test    al, 4
0x140006720  jz      short loc_140006737
0x140006722  mov     eax, [r8+8]
0x140006726  movsxd  r9, dword ptr [r8+4]
0x14000672a  neg     eax
0x14000672c  movsxd  rdx, eax
0x14000672f  add     r9, r10
0x140006732  and     r9, rdx
0x140006735  jmp     short loc_14000673A
0x140006737  mov     r9, r10
0x14000673a  movsxd  rax, ecx
0x14000673d  mov     rdx, [rax+r9]
0x140006741  mov     rax, [r11+10h]
0x140006745  mov     ecx, [rax+8]
0x140006748  mov     rax, [r11+8]
0x14000674c  movzx   r8d, byte ptr [rcx+rax+3]
0x140006752  test    r8b, 0Fh
0x140006756  jz      short loc_140006768
0x140006758  mov     eax, r8d
0x14000675b  mov     ecx, 0FFFFFFF0h
0x140006760  and     rax, rcx
0x140006763  add     rax, r10
0x140006766  jmp     short loc_14000676B
0x140006768  mov     rax, r10
0x14000676b  xor     rdx, rax
0x14000676e  mov     rcx, rdx; StackCookie
0x140006771  call    __security_check_cookie
0x140006776  add     rsp, 28h
0x14000677a  retn
```
