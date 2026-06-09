# __GSHandlerCheckCommon

- ea: `0x1800156c0`
- end: `0x180015723`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001569c`
- `0x18001572c`

## callees

- `0x180001560`
- `0x1800156c0`

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
0x1800156c0  mov     r10, rcx
0x1800156c3  mov     r11, rdx
0x1800156c6  mov     ecx, [r8]
0x1800156c9  and     ecx, 0FFFFFFF8h
0x1800156cc  test    byte ptr [r8], 4
0x1800156d0  jz      short loc_1800156E7
0x1800156d2  mov     eax, [r8+8]
0x1800156d6  movsxd  r9, dword ptr [r8+4]
0x1800156da  neg     eax
0x1800156dc  movsxd  rdx, eax
0x1800156df  add     r9, r10
0x1800156e2  and     r9, rdx
0x1800156e5  jmp     short loc_1800156EA
0x1800156e7  mov     r9, r10
0x1800156ea  movsxd  rax, ecx
0x1800156ed  mov     rdx, [rax+r9]
0x1800156f1  mov     rax, [r11+10h]
0x1800156f5  mov     ecx, [rax+8]
0x1800156f8  mov     rax, [r11+8]
0x1800156fc  test    byte ptr [rcx+rax+3], 0Fh
0x180015701  jz      short loc_180015715
0x180015703  movzx   eax, byte ptr [rcx+rax+3]
0x180015708  mov     ecx, 0FFFFFFF0h
0x18001570d  and     rax, rcx
0x180015710  add     rax, r10
0x180015713  jmp     short loc_180015718
0x180015715  mov     rax, r10
0x180015718  xor     rdx, rax
0x18001571b  mov     rcx, rdx; StackCookie
0x18001571e  jmp     __security_check_cookie
```
