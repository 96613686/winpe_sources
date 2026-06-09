# __GSHandlerCheckCommon

- ea: `0x18000d114`
- end: `0x18000d177`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d0f0`

## callees

- `0x18000d114`
- `0x18000d1c0`

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
0x18000d114  mov     r10, rcx
0x18000d117  mov     r11, rdx
0x18000d11a  mov     ecx, [r8]
0x18000d11d  and     ecx, 0FFFFFFF8h
0x18000d120  test    byte ptr [r8], 4
0x18000d124  jz      short loc_18000D13B
0x18000d126  mov     eax, [r8+8]
0x18000d12a  movsxd  r9, dword ptr [r8+4]
0x18000d12e  neg     eax
0x18000d130  movsxd  rdx, eax
0x18000d133  add     r9, r10
0x18000d136  and     r9, rdx
0x18000d139  jmp     short loc_18000D13E
0x18000d13b  mov     r9, r10
0x18000d13e  movsxd  rax, ecx
0x18000d141  mov     rdx, [rax+r9]
0x18000d145  mov     rax, [r11+10h]
0x18000d149  mov     ecx, [rax+8]
0x18000d14c  mov     rax, [r11+8]
0x18000d150  test    byte ptr [rcx+rax+3], 0Fh
0x18000d155  jz      short loc_18000D169
0x18000d157  movzx   eax, byte ptr [rcx+rax+3]
0x18000d15c  mov     ecx, 0FFFFFFF0h
0x18000d161  and     rax, rcx
0x18000d164  add     rax, r10
0x18000d167  jmp     short loc_18000D16C
0x18000d169  mov     rax, r10
0x18000d16c  xor     rdx, rax
0x18000d16f  mov     rcx, rdx; StackCookie
0x18000d172  jmp     __security_check_cookie
```
