# __GSHandlerCheckCommon

- ea: `0x1800056b8`
- end: `0x18000571b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005694`

## callees

- `0x1800056b8`
- `0x180005780`

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
0x1800056b8  mov     r10, rcx
0x1800056bb  mov     r11, rdx
0x1800056be  mov     ecx, [r8]
0x1800056c1  and     ecx, 0FFFFFFF8h
0x1800056c4  test    byte ptr [r8], 4
0x1800056c8  jz      short loc_1800056DF
0x1800056ca  mov     eax, [r8+8]
0x1800056ce  movsxd  r9, dword ptr [r8+4]
0x1800056d2  neg     eax
0x1800056d4  movsxd  rdx, eax
0x1800056d7  add     r9, r10
0x1800056da  and     r9, rdx
0x1800056dd  jmp     short loc_1800056E2
0x1800056df  mov     r9, r10
0x1800056e2  movsxd  rax, ecx
0x1800056e5  mov     rdx, [rax+r9]
0x1800056e9  mov     rax, [r11+10h]
0x1800056ed  mov     ecx, [rax+8]
0x1800056f0  mov     rax, [r11+8]
0x1800056f4  test    byte ptr [rcx+rax+3], 0Fh
0x1800056f9  jz      short loc_18000570D
0x1800056fb  movzx   eax, byte ptr [rcx+rax+3]
0x180005700  mov     ecx, 0FFFFFFF0h
0x180005705  and     rax, rcx
0x180005708  add     rax, r10
0x18000570b  jmp     short loc_180005710
0x18000570d  mov     rax, r10
0x180005710  xor     rdx, rax
0x180005713  mov     rcx, rdx; StackCookie
0x180005716  jmp     __security_check_cookie
```
