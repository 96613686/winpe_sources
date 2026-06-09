# __GSHandlerCheckCommon

- ea: `0x18000d7fc`
- end: `0x18000d85f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d7d8`

## callees

- `0x18000d0a0`
- `0x18000d7fc`

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
0x18000d7fc  mov     r10, rcx
0x18000d7ff  mov     r11, rdx
0x18000d802  mov     ecx, [r8]
0x18000d805  and     ecx, 0FFFFFFF8h
0x18000d808  test    byte ptr [r8], 4
0x18000d80c  jz      short loc_18000D823
0x18000d80e  mov     eax, [r8+8]
0x18000d812  movsxd  r9, dword ptr [r8+4]
0x18000d816  neg     eax
0x18000d818  movsxd  rdx, eax
0x18000d81b  add     r9, r10
0x18000d81e  and     r9, rdx
0x18000d821  jmp     short loc_18000D826
0x18000d823  mov     r9, r10
0x18000d826  movsxd  rax, ecx
0x18000d829  mov     rdx, [rax+r9]
0x18000d82d  mov     rax, [r11+10h]
0x18000d831  mov     ecx, [rax+8]
0x18000d834  mov     rax, [r11+8]
0x18000d838  test    byte ptr [rcx+rax+3], 0Fh
0x18000d83d  jz      short loc_18000D851
0x18000d83f  movzx   eax, byte ptr [rcx+rax+3]
0x18000d844  mov     ecx, 0FFFFFFF0h
0x18000d849  and     rax, rcx
0x18000d84c  add     rax, r10
0x18000d84f  jmp     short loc_18000D854
0x18000d851  mov     rax, r10
0x18000d854  xor     rdx, rax
0x18000d857  mov     rcx, rdx; StackCookie
0x18000d85a  jmp     __security_check_cookie
```
