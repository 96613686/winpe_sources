# __GSHandlerCheckCommon

- ea: `0x18000aa5c`
- end: `0x18000aabf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000aa38`

## callees

- `0x180009310`
- `0x18000aa5c`

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
0x18000aa5c  mov     r10, rcx
0x18000aa5f  mov     r11, rdx
0x18000aa62  mov     ecx, [r8]
0x18000aa65  and     ecx, 0FFFFFFF8h
0x18000aa68  test    byte ptr [r8], 4
0x18000aa6c  jz      short loc_18000AA83
0x18000aa6e  mov     eax, [r8+8]
0x18000aa72  movsxd  r9, dword ptr [r8+4]
0x18000aa76  neg     eax
0x18000aa78  movsxd  rdx, eax
0x18000aa7b  add     r9, r10
0x18000aa7e  and     r9, rdx
0x18000aa81  jmp     short loc_18000AA86
0x18000aa83  mov     r9, r10
0x18000aa86  movsxd  rax, ecx
0x18000aa89  mov     rdx, [rax+r9]
0x18000aa8d  mov     rax, [r11+10h]
0x18000aa91  mov     ecx, [rax+8]
0x18000aa94  mov     rax, [r11+8]
0x18000aa98  test    byte ptr [rcx+rax+3], 0Fh
0x18000aa9d  jz      short loc_18000AAB1
0x18000aa9f  movzx   eax, byte ptr [rcx+rax+3]
0x18000aaa4  mov     ecx, 0FFFFFFF0h
0x18000aaa9  and     rax, rcx
0x18000aaac  add     rax, r10
0x18000aaaf  jmp     short loc_18000AAB4
0x18000aab1  mov     rax, r10
0x18000aab4  xor     rdx, rax
0x18000aab7  mov     rcx, rdx; StackCookie
0x18000aaba  jmp     __security_check_cookie
```
