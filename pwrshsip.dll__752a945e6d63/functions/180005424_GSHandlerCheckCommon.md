# __GSHandlerCheckCommon

- ea: `0x180005424`
- end: `0x180005487`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005400`

## callees

- `0x180005424`
- `0x1800054f0`

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
0x180005424  mov     r10, rcx
0x180005427  mov     r11, rdx
0x18000542a  mov     ecx, [r8]
0x18000542d  and     ecx, 0FFFFFFF8h
0x180005430  test    byte ptr [r8], 4
0x180005434  jz      short loc_18000544B
0x180005436  mov     eax, [r8+8]
0x18000543a  movsxd  r9, dword ptr [r8+4]
0x18000543e  neg     eax
0x180005440  movsxd  rdx, eax
0x180005443  add     r9, r10
0x180005446  and     r9, rdx
0x180005449  jmp     short loc_18000544E
0x18000544b  mov     r9, r10
0x18000544e  movsxd  rax, ecx
0x180005451  mov     rdx, [rax+r9]
0x180005455  mov     rax, [r11+10h]
0x180005459  mov     ecx, [rax+8]
0x18000545c  mov     rax, [r11+8]
0x180005460  test    byte ptr [rcx+rax+3], 0Fh
0x180005465  jz      short loc_180005479
0x180005467  movzx   eax, byte ptr [rcx+rax+3]
0x18000546c  mov     ecx, 0FFFFFFF0h
0x180005471  and     rax, rcx
0x180005474  add     rax, r10
0x180005477  jmp     short loc_18000547C
0x180005479  mov     rax, r10
0x18000547c  xor     rdx, rax
0x18000547f  mov     rcx, rdx; StackCookie
0x180005482  jmp     __security_check_cookie
```
