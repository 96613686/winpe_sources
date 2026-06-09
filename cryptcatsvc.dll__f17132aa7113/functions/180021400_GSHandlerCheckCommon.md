# __GSHandlerCheckCommon

- ea: `0x180021400`
- end: `0x180021463`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800213dc`
- `0x18002146c`
- `0x1800214d4`

## callees

- `0x18000be40`
- `0x180021400`

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
0x180021400  mov     r10, rcx
0x180021403  mov     r11, rdx
0x180021406  mov     ecx, [r8]
0x180021409  and     ecx, 0FFFFFFF8h
0x18002140c  test    byte ptr [r8], 4
0x180021410  jz      short loc_180021427
0x180021412  mov     eax, [r8+8]
0x180021416  movsxd  r9, dword ptr [r8+4]
0x18002141a  neg     eax
0x18002141c  movsxd  rdx, eax
0x18002141f  add     r9, r10
0x180021422  and     r9, rdx
0x180021425  jmp     short loc_18002142A
0x180021427  mov     r9, r10
0x18002142a  movsxd  rax, ecx
0x18002142d  mov     rdx, [rax+r9]
0x180021431  mov     rax, [r11+10h]
0x180021435  mov     ecx, [rax+8]
0x180021438  mov     rax, [r11+8]
0x18002143c  test    byte ptr [rcx+rax+3], 0Fh
0x180021441  jz      short loc_180021455
0x180021443  movzx   eax, byte ptr [rcx+rax+3]
0x180021448  mov     ecx, 0FFFFFFF0h
0x18002144d  and     rax, rcx
0x180021450  add     rax, r10
0x180021453  jmp     short loc_180021458
0x180021455  mov     rax, r10
0x180021458  xor     rdx, rax
0x18002145b  mov     rcx, rdx; StackCookie
0x18002145e  jmp     __security_check_cookie
```
