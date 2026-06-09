# __GSHandlerCheckCommon

- ea: `0x180003720`
- end: `0x180003783`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800036fc`

## callees

- `0x180003720`
- `0x1800037d0`

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
0x180003720  mov     r10, rcx
0x180003723  mov     r11, rdx
0x180003726  mov     ecx, [r8]
0x180003729  and     ecx, 0FFFFFFF8h
0x18000372c  test    byte ptr [r8], 4
0x180003730  jz      short loc_180003747
0x180003732  mov     eax, [r8+8]
0x180003736  movsxd  r9, dword ptr [r8+4]
0x18000373a  neg     eax
0x18000373c  movsxd  rdx, eax
0x18000373f  add     r9, r10
0x180003742  and     r9, rdx
0x180003745  jmp     short loc_18000374A
0x180003747  mov     r9, r10
0x18000374a  movsxd  rax, ecx
0x18000374d  mov     rdx, [rax+r9]
0x180003751  mov     rax, [r11+10h]
0x180003755  mov     ecx, [rax+8]
0x180003758  mov     rax, [r11+8]
0x18000375c  test    byte ptr [rcx+rax+3], 0Fh
0x180003761  jz      short loc_180003775
0x180003763  movzx   eax, byte ptr [rcx+rax+3]
0x180003768  mov     ecx, 0FFFFFFF0h
0x18000376d  and     rax, rcx
0x180003770  add     rax, r10
0x180003773  jmp     short loc_180003778
0x180003775  mov     rax, r10
0x180003778  xor     rdx, rax
0x18000377b  mov     rcx, rdx; StackCookie
0x18000377e  jmp     __security_check_cookie
```
