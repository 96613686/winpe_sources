# __GSHandlerCheckCommon

- ea: `0x140015588`
- end: `0x1400155eb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140015564`
- `0x1400155f4`

## callees

- `0x140015588`
- `0x140015690`

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
0x140015588  mov     r10, rcx
0x14001558b  mov     r11, rdx
0x14001558e  mov     ecx, [r8]
0x140015591  and     ecx, 0FFFFFFF8h
0x140015594  test    byte ptr [r8], 4
0x140015598  jz      short loc_1400155AF
0x14001559a  mov     eax, [r8+8]
0x14001559e  movsxd  r9, dword ptr [r8+4]
0x1400155a2  neg     eax
0x1400155a4  movsxd  rdx, eax
0x1400155a7  add     r9, r10
0x1400155aa  and     r9, rdx
0x1400155ad  jmp     short loc_1400155B2
0x1400155af  mov     r9, r10
0x1400155b2  movsxd  rax, ecx
0x1400155b5  mov     rdx, [rax+r9]
0x1400155b9  mov     rax, [r11+10h]
0x1400155bd  mov     ecx, [rax+8]
0x1400155c0  mov     rax, [r11+8]
0x1400155c4  test    byte ptr [rcx+rax+3], 0Fh
0x1400155c9  jz      short loc_1400155DD
0x1400155cb  movzx   eax, byte ptr [rcx+rax+3]
0x1400155d0  mov     ecx, 0FFFFFFF0h
0x1400155d5  and     rax, rcx
0x1400155d8  add     rax, r10
0x1400155db  jmp     short loc_1400155E0
0x1400155dd  mov     rax, r10
0x1400155e0  xor     rdx, rax
0x1400155e3  mov     rcx, rdx; StackCookie
0x1400155e6  jmp     __security_check_cookie
```
