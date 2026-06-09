# __GSHandlerCheckCommon

- ea: `0x18001e340`
- end: `0x18001e3a3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e31c`
- `0x18001e3ac`

## callees

- `0x180007740`
- `0x18001e340`

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
0x18001e340  mov     r10, rcx
0x18001e343  mov     r11, rdx
0x18001e346  mov     ecx, [r8]
0x18001e349  and     ecx, 0FFFFFFF8h
0x18001e34c  test    byte ptr [r8], 4
0x18001e350  jz      short loc_18001E367
0x18001e352  mov     eax, [r8+8]
0x18001e356  movsxd  r9, dword ptr [r8+4]
0x18001e35a  neg     eax
0x18001e35c  movsxd  rdx, eax
0x18001e35f  add     r9, r10
0x18001e362  and     r9, rdx
0x18001e365  jmp     short loc_18001E36A
0x18001e367  mov     r9, r10
0x18001e36a  movsxd  rax, ecx
0x18001e36d  mov     rdx, [rax+r9]
0x18001e371  mov     rax, [r11+10h]
0x18001e375  mov     ecx, [rax+8]
0x18001e378  mov     rax, [r11+8]
0x18001e37c  test    byte ptr [rcx+rax+3], 0Fh
0x18001e381  jz      short loc_18001E395
0x18001e383  movzx   eax, byte ptr [rcx+rax+3]
0x18001e388  mov     ecx, 0FFFFFFF0h
0x18001e38d  and     rax, rcx
0x18001e390  add     rax, r10
0x18001e393  jmp     short loc_18001E398
0x18001e395  mov     rax, r10
0x18001e398  xor     rdx, rax
0x18001e39b  mov     rcx, rdx; StackCookie
0x18001e39e  jmp     __security_check_cookie
```
