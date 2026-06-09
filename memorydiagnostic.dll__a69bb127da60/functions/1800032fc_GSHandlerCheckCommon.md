# __GSHandlerCheckCommon

- ea: `0x1800032fc`
- end: `0x18000335f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800032d8`
- `0x1800207bc`

## callees

- `0x180002e50`
- `0x1800032fc`

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
0x1800032fc  mov     r10, rcx
0x1800032ff  mov     r11, rdx
0x180003302  mov     ecx, [r8]
0x180003305  and     ecx, 0FFFFFFF8h
0x180003308  test    byte ptr [r8], 4
0x18000330c  jz      short loc_180003323
0x18000330e  mov     eax, [r8+8]
0x180003312  movsxd  r9, dword ptr [r8+4]
0x180003316  neg     eax
0x180003318  movsxd  rdx, eax
0x18000331b  add     r9, r10
0x18000331e  and     r9, rdx
0x180003321  jmp     short loc_180003326
0x180003323  mov     r9, r10
0x180003326  movsxd  rax, ecx
0x180003329  mov     rdx, [rax+r9]
0x18000332d  mov     rax, [r11+10h]
0x180003331  mov     ecx, [rax+8]
0x180003334  mov     rax, [r11+8]
0x180003338  test    byte ptr [rcx+rax+3], 0Fh
0x18000333d  jz      short loc_180003351
0x18000333f  movzx   eax, byte ptr [rcx+rax+3]
0x180003344  mov     ecx, 0FFFFFFF0h
0x180003349  and     rax, rcx
0x18000334c  add     rax, r10
0x18000334f  jmp     short loc_180003354
0x180003351  mov     rax, r10
0x180003354  xor     rdx, rax
0x180003357  mov     rcx, rdx; StackCookie
0x18000335a  jmp     __security_check_cookie
```
