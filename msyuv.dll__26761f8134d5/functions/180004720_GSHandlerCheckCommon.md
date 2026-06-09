# __GSHandlerCheckCommon

- ea: `0x180004720`
- end: `0x180004783`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800046fc`

## callees

- `0x180001400`
- `0x180004720`

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
0x180004720  mov     r10, rcx
0x180004723  mov     r11, rdx
0x180004726  mov     ecx, [r8]
0x180004729  and     ecx, 0FFFFFFF8h
0x18000472c  test    byte ptr [r8], 4
0x180004730  jz      short loc_180004747
0x180004732  mov     eax, [r8+8]
0x180004736  movsxd  r9, dword ptr [r8+4]
0x18000473a  neg     eax
0x18000473c  movsxd  rdx, eax
0x18000473f  add     r9, r10
0x180004742  and     r9, rdx
0x180004745  jmp     short loc_18000474A
0x180004747  mov     r9, r10
0x18000474a  movsxd  rax, ecx
0x18000474d  mov     rdx, [rax+r9]
0x180004751  mov     rax, [r11+10h]
0x180004755  mov     ecx, [rax+8]
0x180004758  mov     rax, [r11+8]
0x18000475c  test    byte ptr [rcx+rax+3], 0Fh
0x180004761  jz      short loc_180004775
0x180004763  movzx   eax, byte ptr [rcx+rax+3]
0x180004768  mov     ecx, 0FFFFFFF0h
0x18000476d  and     rax, rcx
0x180004770  add     rax, r10
0x180004773  jmp     short loc_180004778
0x180004775  mov     rax, r10
0x180004778  xor     rdx, rax
0x18000477b  mov     rcx, rdx; StackCookie
0x18000477e  jmp     __security_check_cookie
```
