# __GSHandlerCheckCommon

- ea: `0x180014d40`
- end: `0x180014da3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014d1c`
- `0x180014dac`

## callees

- `0x180001f60`
- `0x180014d40`

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
0x180014d40  mov     r10, rcx
0x180014d43  mov     r11, rdx
0x180014d46  mov     ecx, [r8]
0x180014d49  and     ecx, 0FFFFFFF8h
0x180014d4c  test    byte ptr [r8], 4
0x180014d50  jz      short loc_180014D67
0x180014d52  mov     eax, [r8+8]
0x180014d56  movsxd  r9, dword ptr [r8+4]
0x180014d5a  neg     eax
0x180014d5c  movsxd  rdx, eax
0x180014d5f  add     r9, r10
0x180014d62  and     r9, rdx
0x180014d65  jmp     short loc_180014D6A
0x180014d67  mov     r9, r10
0x180014d6a  movsxd  rax, ecx
0x180014d6d  mov     rdx, [rax+r9]
0x180014d71  mov     rax, [r11+10h]
0x180014d75  mov     ecx, [rax+8]
0x180014d78  mov     rax, [r11+8]
0x180014d7c  test    byte ptr [rcx+rax+3], 0Fh
0x180014d81  jz      short loc_180014D95
0x180014d83  movzx   eax, byte ptr [rcx+rax+3]
0x180014d88  mov     ecx, 0FFFFFFF0h
0x180014d8d  and     rax, rcx
0x180014d90  add     rax, r10
0x180014d93  jmp     short loc_180014D98
0x180014d95  mov     rax, r10
0x180014d98  xor     rdx, rax
0x180014d9b  mov     rcx, rdx; StackCookie
0x180014d9e  jmp     __security_check_cookie
```
