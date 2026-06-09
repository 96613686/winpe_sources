# __GSHandlerCheckCommon

- ea: `0x18000cda4`
- end: `0x18000ce07`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cd80`
- `0x18000ce10`

## callees

- `0x180001600`
- `0x18000cda4`

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
0x18000cda4  mov     r10, rcx
0x18000cda7  mov     r11, rdx
0x18000cdaa  mov     ecx, [r8]
0x18000cdad  and     ecx, 0FFFFFFF8h
0x18000cdb0  test    byte ptr [r8], 4
0x18000cdb4  jz      short loc_18000CDCB
0x18000cdb6  mov     eax, [r8+8]
0x18000cdba  movsxd  r9, dword ptr [r8+4]
0x18000cdbe  neg     eax
0x18000cdc0  movsxd  rdx, eax
0x18000cdc3  add     r9, r10
0x18000cdc6  and     r9, rdx
0x18000cdc9  jmp     short loc_18000CDCE
0x18000cdcb  mov     r9, r10
0x18000cdce  movsxd  rax, ecx
0x18000cdd1  mov     rdx, [rax+r9]
0x18000cdd5  mov     rax, [r11+10h]
0x18000cdd9  mov     ecx, [rax+8]
0x18000cddc  mov     rax, [r11+8]
0x18000cde0  test    byte ptr [rcx+rax+3], 0Fh
0x18000cde5  jz      short loc_18000CDF9
0x18000cde7  movzx   eax, byte ptr [rcx+rax+3]
0x18000cdec  mov     ecx, 0FFFFFFF0h
0x18000cdf1  and     rax, rcx
0x18000cdf4  add     rax, r10
0x18000cdf7  jmp     short loc_18000CDFC
0x18000cdf9  mov     rax, r10
0x18000cdfc  xor     rdx, rax
0x18000cdff  mov     rcx, rdx; StackCookie
0x18000ce02  jmp     __security_check_cookie
```
