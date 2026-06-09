# __GSHandlerCheckCommon

- ea: `0x1800023f8`
- end: `0x18000245b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800023d4`
- `0x180002464`
- `0x180027290`
- `0x1800272f8`

## callees

- `0x1800023f8`
- `0x1800273b0`

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
0x1800023f8  mov     r10, rcx
0x1800023fb  mov     r11, rdx
0x1800023fe  mov     ecx, [r8]
0x180002401  and     ecx, 0FFFFFFF8h
0x180002404  test    byte ptr [r8], 4
0x180002408  jz      short loc_18000241F
0x18000240a  mov     eax, [r8+8]
0x18000240e  movsxd  r9, dword ptr [r8+4]
0x180002412  neg     eax
0x180002414  movsxd  rdx, eax
0x180002417  add     r9, r10
0x18000241a  and     r9, rdx
0x18000241d  jmp     short loc_180002422
0x18000241f  mov     r9, r10
0x180002422  movsxd  rax, ecx
0x180002425  mov     rdx, [rax+r9]
0x180002429  mov     rax, [r11+10h]
0x18000242d  mov     ecx, [rax+8]
0x180002430  mov     rax, [r11+8]
0x180002434  test    byte ptr [rcx+rax+3], 0Fh
0x180002439  jz      short loc_18000244D
0x18000243b  movzx   eax, byte ptr [rcx+rax+3]
0x180002440  mov     ecx, 0FFFFFFF0h
0x180002445  and     rax, rcx
0x180002448  add     rax, r10
0x18000244b  jmp     short loc_180002450
0x18000244d  mov     rax, r10
0x180002450  xor     rdx, rax
0x180002453  mov     rcx, rdx; StackCookie
0x180002456  jmp     __security_check_cookie
```
