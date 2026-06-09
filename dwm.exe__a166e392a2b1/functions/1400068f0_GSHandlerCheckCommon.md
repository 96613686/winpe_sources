# __GSHandlerCheckCommon

- ea: `0x1400068f0`
- end: `0x140006953`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400068cc`

## callees

- `0x140005530`
- `0x1400068f0`

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
0x1400068f0  mov     r10, rcx
0x1400068f3  mov     r11, rdx
0x1400068f6  mov     ecx, [r8]
0x1400068f9  and     ecx, 0FFFFFFF8h
0x1400068fc  test    byte ptr [r8], 4
0x140006900  jz      short loc_140006917
0x140006902  mov     eax, [r8+8]
0x140006906  movsxd  r9, dword ptr [r8+4]
0x14000690a  neg     eax
0x14000690c  movsxd  rdx, eax
0x14000690f  add     r9, r10
0x140006912  and     r9, rdx
0x140006915  jmp     short loc_14000691A
0x140006917  mov     r9, r10
0x14000691a  movsxd  rax, ecx
0x14000691d  mov     rdx, [rax+r9]
0x140006921  mov     rax, [r11+10h]
0x140006925  mov     ecx, [rax+8]
0x140006928  mov     rax, [r11+8]
0x14000692c  test    byte ptr [rcx+rax+3], 0Fh
0x140006931  jz      short loc_140006945
0x140006933  movzx   eax, byte ptr [rcx+rax+3]
0x140006938  mov     ecx, 0FFFFFFF0h
0x14000693d  and     rax, rcx
0x140006940  add     rax, r10
0x140006943  jmp     short loc_140006948
0x140006945  mov     rax, r10
0x140006948  xor     rdx, rax
0x14000694b  mov     rcx, rdx; StackCookie
0x14000694e  jmp     __security_check_cookie
```
