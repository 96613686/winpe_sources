# __GSHandlerCheckCommon

- ea: `0x18000206c`
- end: `0x1800020cf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002048`
- `0x18000aaa0`

## callees

- `0x18000206c`
- `0x18000ab60`

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
0x18000206c  mov     r10, rcx
0x18000206f  mov     r11, rdx
0x180002072  mov     ecx, [r8]
0x180002075  and     ecx, 0FFFFFFF8h
0x180002078  test    byte ptr [r8], 4
0x18000207c  jz      short loc_180002093
0x18000207e  mov     eax, [r8+8]
0x180002082  movsxd  r9, dword ptr [r8+4]
0x180002086  neg     eax
0x180002088  movsxd  rdx, eax
0x18000208b  add     r9, r10
0x18000208e  and     r9, rdx
0x180002091  jmp     short loc_180002096
0x180002093  mov     r9, r10
0x180002096  movsxd  rax, ecx
0x180002099  mov     rdx, [rax+r9]
0x18000209d  mov     rax, [r11+10h]
0x1800020a1  mov     ecx, [rax+8]
0x1800020a4  mov     rax, [r11+8]
0x1800020a8  test    byte ptr [rcx+rax+3], 0Fh
0x1800020ad  jz      short loc_1800020C1
0x1800020af  movzx   eax, byte ptr [rcx+rax+3]
0x1800020b4  mov     ecx, 0FFFFFFF0h
0x1800020b9  and     rax, rcx
0x1800020bc  add     rax, r10
0x1800020bf  jmp     short loc_1800020C4
0x1800020c1  mov     rax, r10
0x1800020c4  xor     rdx, rax
0x1800020c7  mov     rcx, rdx; StackCookie
0x1800020ca  jmp     __security_check_cookie
```
