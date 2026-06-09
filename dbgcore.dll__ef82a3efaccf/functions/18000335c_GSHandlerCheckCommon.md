# __GSHandlerCheckCommon

- ea: `0x18000335c`
- end: `0x1800033bf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003338`
- `0x18002aee8`
- `0x18002af50`

## callees

- `0x180001710`
- `0x18000335c`

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
0x18000335c  mov     r10, rcx
0x18000335f  mov     r11, rdx
0x180003362  mov     ecx, [r8]
0x180003365  and     ecx, 0FFFFFFF8h
0x180003368  test    byte ptr [r8], 4
0x18000336c  jz      short loc_180003383
0x18000336e  mov     eax, [r8+8]
0x180003372  movsxd  r9, dword ptr [r8+4]
0x180003376  neg     eax
0x180003378  movsxd  rdx, eax
0x18000337b  add     r9, r10
0x18000337e  and     r9, rdx
0x180003381  jmp     short loc_180003386
0x180003383  mov     r9, r10
0x180003386  movsxd  rax, ecx
0x180003389  mov     rdx, [rax+r9]
0x18000338d  mov     rax, [r11+10h]
0x180003391  mov     ecx, [rax+8]
0x180003394  mov     rax, [r11+8]
0x180003398  test    byte ptr [rcx+rax+3], 0Fh
0x18000339d  jz      short loc_1800033B1
0x18000339f  movzx   eax, byte ptr [rcx+rax+3]
0x1800033a4  mov     ecx, 0FFFFFFF0h
0x1800033a9  and     rax, rcx
0x1800033ac  add     rax, r10
0x1800033af  jmp     short loc_1800033B4
0x1800033b1  mov     rax, r10
0x1800033b4  xor     rdx, rax
0x1800033b7  mov     rcx, rdx; StackCookie
0x1800033ba  jmp     __security_check_cookie
```
