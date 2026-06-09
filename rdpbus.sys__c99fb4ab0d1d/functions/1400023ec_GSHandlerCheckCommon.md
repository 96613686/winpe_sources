# __GSHandlerCheckCommon

- ea: `0x1400023ec`
- end: `0x14000245c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400023c8`

## callees

- `0x1400023ec`
- `0x140002520`

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
0x1400023ec  sub     rsp, 28h
0x1400023f0  mov     eax, [r8]
0x1400023f3  mov     r10, rcx
0x1400023f6  mov     ecx, eax
0x1400023f8  mov     r11, rdx
0x1400023fb  and     ecx, 0FFFFFFF8h
0x1400023fe  test    al, 4
0x140002400  jz      short loc_140002417
0x140002402  mov     eax, [r8+8]
0x140002406  movsxd  r9, dword ptr [r8+4]
0x14000240a  neg     eax
0x14000240c  movsxd  rdx, eax
0x14000240f  add     r9, r10
0x140002412  and     r9, rdx
0x140002415  jmp     short loc_14000241A
0x140002417  mov     r9, r10
0x14000241a  movsxd  rax, ecx
0x14000241d  mov     rdx, [rax+r9]
0x140002421  mov     rax, [r11+10h]
0x140002425  mov     ecx, [rax+8]
0x140002428  mov     rax, [r11+8]
0x14000242c  movzx   r8d, byte ptr [rcx+rax+3]
0x140002432  test    r8b, 0Fh
0x140002436  jz      short loc_140002448
0x140002438  mov     eax, r8d
0x14000243b  mov     ecx, 0FFFFFFF0h
0x140002440  and     rax, rcx
0x140002443  add     rax, r10
0x140002446  jmp     short loc_14000244B
0x140002448  mov     rax, r10
0x14000244b  xor     rdx, rax
0x14000244e  mov     rcx, rdx; StackCookie
0x140002451  call    __security_check_cookie
0x140002456  add     rsp, 28h
0x14000245a  retn
```
