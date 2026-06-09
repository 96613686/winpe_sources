# __GSHandlerCheckCommon

- ea: `0x180004b5c`
- end: `0x180004bbf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004b38`

## callees

- `0x180004b5c`
- `0x180004c10`

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
0x180004b5c  mov     r10, rcx
0x180004b5f  mov     r11, rdx
0x180004b62  mov     ecx, [r8]
0x180004b65  and     ecx, 0FFFFFFF8h
0x180004b68  test    byte ptr [r8], 4
0x180004b6c  jz      short loc_180004B83
0x180004b6e  mov     eax, [r8+8]
0x180004b72  movsxd  r9, dword ptr [r8+4]
0x180004b76  neg     eax
0x180004b78  movsxd  rdx, eax
0x180004b7b  add     r9, r10
0x180004b7e  and     r9, rdx
0x180004b81  jmp     short loc_180004B86
0x180004b83  mov     r9, r10
0x180004b86  movsxd  rax, ecx
0x180004b89  mov     rdx, [rax+r9]
0x180004b8d  mov     rax, [r11+10h]
0x180004b91  mov     ecx, [rax+8]
0x180004b94  mov     rax, [r11+8]
0x180004b98  test    byte ptr [rcx+rax+3], 0Fh
0x180004b9d  jz      short loc_180004BB1
0x180004b9f  movzx   eax, byte ptr [rcx+rax+3]
0x180004ba4  mov     ecx, 0FFFFFFF0h
0x180004ba9  and     rax, rcx
0x180004bac  add     rax, r10
0x180004baf  jmp     short loc_180004BB4
0x180004bb1  mov     rax, r10
0x180004bb4  xor     rdx, rax
0x180004bb7  mov     rcx, rdx; StackCookie
0x180004bba  jmp     __security_check_cookie
```
