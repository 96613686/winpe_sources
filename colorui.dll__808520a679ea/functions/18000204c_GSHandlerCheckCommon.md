# __GSHandlerCheckCommon

- ea: `0x18000204c`
- end: `0x1800020af`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002028`

## callees

- `0x18000204c`
- `0x180018500`

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
0x18000204c  mov     r10, rcx
0x18000204f  mov     r11, rdx
0x180002052  mov     ecx, [r8]
0x180002055  and     ecx, 0FFFFFFF8h
0x180002058  test    byte ptr [r8], 4
0x18000205c  jz      short loc_180002073
0x18000205e  mov     eax, [r8+8]
0x180002062  movsxd  r9, dword ptr [r8+4]
0x180002066  neg     eax
0x180002068  movsxd  rdx, eax
0x18000206b  add     r9, r10
0x18000206e  and     r9, rdx
0x180002071  jmp     short loc_180002076
0x180002073  mov     r9, r10
0x180002076  movsxd  rax, ecx
0x180002079  mov     rdx, [rax+r9]
0x18000207d  mov     rax, [r11+10h]
0x180002081  mov     ecx, [rax+8]
0x180002084  mov     rax, [r11+8]
0x180002088  test    byte ptr [rcx+rax+3], 0Fh
0x18000208d  jz      short loc_1800020A1
0x18000208f  movzx   eax, byte ptr [rcx+rax+3]
0x180002094  mov     ecx, 0FFFFFFF0h
0x180002099  and     rax, rcx
0x18000209c  add     rax, r10
0x18000209f  jmp     short loc_1800020A4
0x1800020a1  mov     rax, r10
0x1800020a4  xor     rdx, rax
0x1800020a7  mov     rcx, rdx; StackCookie
0x1800020aa  jmp     __security_check_cookie
```
