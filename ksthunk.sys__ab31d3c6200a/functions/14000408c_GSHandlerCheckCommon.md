# __GSHandlerCheckCommon

- ea: `0x14000408c`
- end: `0x1400040fc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004068`

## callees

- `0x14000408c`
- `0x140004110`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  int v2; // r8d

  v2 = *(unsigned __int8 *)(*(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL) + *(_QWORD *)(a2 + 8) + 3LL);
  if ( (v2 & 0xF) != 0 )
    return a1 + (v2 & 0xFFFFFFF0);
  else
    return a1;
}

```

## disassembly

```asm
0x14000408c  sub     rsp, 28h
0x140004090  mov     eax, [r8]
0x140004093  mov     r10, rcx
0x140004096  mov     ecx, eax
0x140004098  mov     r11, rdx
0x14000409b  and     ecx, 0FFFFFFF8h
0x14000409e  test    al, 4
0x1400040a0  jz      short loc_1400040B7
0x1400040a2  mov     eax, [r8+8]
0x1400040a6  movsxd  r9, dword ptr [r8+4]
0x1400040aa  neg     eax
0x1400040ac  movsxd  rdx, eax
0x1400040af  add     r9, r10
0x1400040b2  and     r9, rdx
0x1400040b5  jmp     short loc_1400040BA
0x1400040b7  mov     r9, r10
0x1400040ba  movsxd  rax, ecx
0x1400040bd  mov     rdx, [rax+r9]
0x1400040c1  mov     rax, [r11+10h]
0x1400040c5  mov     ecx, [rax+8]
0x1400040c8  mov     rax, [r11+8]
0x1400040cc  movzx   r8d, byte ptr [rcx+rax+3]
0x1400040d2  test    r8b, 0Fh
0x1400040d6  jz      short loc_1400040E8
0x1400040d8  mov     eax, r8d
0x1400040db  mov     ecx, 0FFFFFFF0h
0x1400040e0  and     rax, rcx
0x1400040e3  add     rax, r10
0x1400040e6  jmp     short loc_1400040EB
0x1400040e8  mov     rax, r10
0x1400040eb  xor     rdx, rax
0x1400040ee  mov     rcx, rdx; StackCookie
0x1400040f1  call    __security_check_cookie
0x1400040f6  add     rsp, 28h
0x1400040fa  retn
```
