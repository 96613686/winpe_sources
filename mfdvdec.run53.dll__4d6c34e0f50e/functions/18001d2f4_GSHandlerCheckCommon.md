# __GSHandlerCheckCommon

- ea: `0x18001d2f4`
- end: `0x18001d357`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d2d0`

## callees

- `0x180001580`
- `0x18001d2f4`

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
0x18001d2f4  mov     r10, rcx
0x18001d2f7  mov     r11, rdx
0x18001d2fa  mov     ecx, [r8]
0x18001d2fd  and     ecx, 0FFFFFFF8h
0x18001d300  test    byte ptr [r8], 4
0x18001d304  jz      short loc_18001D31B
0x18001d306  mov     eax, [r8+8]
0x18001d30a  movsxd  r9, dword ptr [r8+4]
0x18001d30e  neg     eax
0x18001d310  movsxd  rdx, eax
0x18001d313  add     r9, r10
0x18001d316  and     r9, rdx
0x18001d319  jmp     short loc_18001D31E
0x18001d31b  mov     r9, r10
0x18001d31e  movsxd  rax, ecx
0x18001d321  mov     rdx, [rax+r9]
0x18001d325  mov     rax, [r11+10h]
0x18001d329  mov     ecx, [rax+8]
0x18001d32c  mov     rax, [r11+8]
0x18001d330  test    byte ptr [rcx+rax+3], 0Fh
0x18001d335  jz      short loc_18001D349
0x18001d337  movzx   eax, byte ptr [rcx+rax+3]
0x18001d33c  mov     ecx, 0FFFFFFF0h
0x18001d341  and     rax, rcx
0x18001d344  add     rax, r10
0x18001d347  jmp     short loc_18001D34C
0x18001d349  mov     rax, r10
0x18001d34c  xor     rdx, rax
0x18001d34f  mov     rcx, rdx; StackCookie
0x18001d352  jmp     __security_check_cookie
```
