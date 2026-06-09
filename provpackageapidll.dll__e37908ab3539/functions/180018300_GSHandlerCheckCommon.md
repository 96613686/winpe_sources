# __GSHandlerCheckCommon

- ea: `0x180018300`
- end: `0x180018363`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800182dc`
- `0x18001836c`

## callees

- `0x180001510`
- `0x180018300`

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
0x180018300  mov     r10, rcx
0x180018303  mov     r11, rdx
0x180018306  mov     ecx, [r8]
0x180018309  and     ecx, 0FFFFFFF8h
0x18001830c  test    byte ptr [r8], 4
0x180018310  jz      short loc_180018327
0x180018312  mov     eax, [r8+8]
0x180018316  movsxd  r9, dword ptr [r8+4]
0x18001831a  neg     eax
0x18001831c  movsxd  rdx, eax
0x18001831f  add     r9, r10
0x180018322  and     r9, rdx
0x180018325  jmp     short loc_18001832A
0x180018327  mov     r9, r10
0x18001832a  movsxd  rax, ecx
0x18001832d  mov     rdx, [rax+r9]
0x180018331  mov     rax, [r11+10h]
0x180018335  mov     ecx, [rax+8]
0x180018338  mov     rax, [r11+8]
0x18001833c  test    byte ptr [rcx+rax+3], 0Fh
0x180018341  jz      short loc_180018355
0x180018343  movzx   eax, byte ptr [rcx+rax+3]
0x180018348  mov     ecx, 0FFFFFFF0h
0x18001834d  and     rax, rcx
0x180018350  add     rax, r10
0x180018353  jmp     short loc_180018358
0x180018355  mov     rax, r10
0x180018358  xor     rdx, rax
0x18001835b  mov     rcx, rdx; StackCookie
0x18001835e  jmp     __security_check_cookie
```
