# __GSHandlerCheckCommon

- ea: `0x180005ed0`
- end: `0x180005f33`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005eac`

## callees

- `0x180005ed0`
- `0x180005f90`

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
0x180005ed0  mov     r10, rcx
0x180005ed3  mov     r11, rdx
0x180005ed6  mov     ecx, [r8]
0x180005ed9  and     ecx, 0FFFFFFF8h
0x180005edc  test    byte ptr [r8], 4
0x180005ee0  jz      short loc_180005EF7
0x180005ee2  mov     eax, [r8+8]
0x180005ee6  movsxd  r9, dword ptr [r8+4]
0x180005eea  neg     eax
0x180005eec  movsxd  rdx, eax
0x180005eef  add     r9, r10
0x180005ef2  and     r9, rdx
0x180005ef5  jmp     short loc_180005EFA
0x180005ef7  mov     r9, r10
0x180005efa  movsxd  rax, ecx
0x180005efd  mov     rdx, [rax+r9]
0x180005f01  mov     rax, [r11+10h]
0x180005f05  mov     ecx, [rax+8]
0x180005f08  mov     rax, [r11+8]
0x180005f0c  test    byte ptr [rcx+rax+3], 0Fh
0x180005f11  jz      short loc_180005F25
0x180005f13  movzx   eax, byte ptr [rcx+rax+3]
0x180005f18  mov     ecx, 0FFFFFFF0h
0x180005f1d  and     rax, rcx
0x180005f20  add     rax, r10
0x180005f23  jmp     short loc_180005F28
0x180005f25  mov     rax, r10
0x180005f28  xor     rdx, rax
0x180005f2b  mov     rcx, rdx; StackCookie
0x180005f2e  jmp     __security_check_cookie
```
