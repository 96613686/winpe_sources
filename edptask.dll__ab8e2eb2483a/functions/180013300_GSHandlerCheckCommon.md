# __GSHandlerCheckCommon

- ea: `0x180013300`
- end: `0x180013363`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800132dc`
- `0x18001336c`

## callees

- `0x180013300`
- `0x180013410`

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
0x180013300  mov     r10, rcx
0x180013303  mov     r11, rdx
0x180013306  mov     ecx, [r8]
0x180013309  and     ecx, 0FFFFFFF8h
0x18001330c  test    byte ptr [r8], 4
0x180013310  jz      short loc_180013327
0x180013312  mov     eax, [r8+8]
0x180013316  movsxd  r9, dword ptr [r8+4]
0x18001331a  neg     eax
0x18001331c  movsxd  rdx, eax
0x18001331f  add     r9, r10
0x180013322  and     r9, rdx
0x180013325  jmp     short loc_18001332A
0x180013327  mov     r9, r10
0x18001332a  movsxd  rax, ecx
0x18001332d  mov     rdx, [rax+r9]
0x180013331  mov     rax, [r11+10h]
0x180013335  mov     ecx, [rax+8]
0x180013338  mov     rax, [r11+8]
0x18001333c  test    byte ptr [rcx+rax+3], 0Fh
0x180013341  jz      short loc_180013355
0x180013343  movzx   eax, byte ptr [rcx+rax+3]
0x180013348  mov     ecx, 0FFFFFFF0h
0x18001334d  and     rax, rcx
0x180013350  add     rax, r10
0x180013353  jmp     short loc_180013358
0x180013355  mov     rax, r10
0x180013358  xor     rdx, rax
0x18001335b  mov     rcx, rdx; StackCookie
0x18001335e  jmp     __security_check_cookie
```
