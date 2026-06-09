# __GSHandlerCheckCommon

- ea: `0x140006ffc`
- end: `0x14000706c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006fd8`

## callees

- `0x140006ffc`
- `0x140007130`

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
0x140006ffc  sub     rsp, 28h
0x140007000  mov     eax, [r8]
0x140007003  mov     r10, rcx
0x140007006  mov     ecx, eax
0x140007008  mov     r11, rdx
0x14000700b  and     ecx, 0FFFFFFF8h
0x14000700e  test    al, 4
0x140007010  jz      short loc_140007027
0x140007012  mov     eax, [r8+8]
0x140007016  movsxd  r9, dword ptr [r8+4]
0x14000701a  neg     eax
0x14000701c  movsxd  rdx, eax
0x14000701f  add     r9, r10
0x140007022  and     r9, rdx
0x140007025  jmp     short loc_14000702A
0x140007027  mov     r9, r10
0x14000702a  movsxd  rax, ecx
0x14000702d  mov     rdx, [rax+r9]
0x140007031  mov     rax, [r11+10h]
0x140007035  mov     ecx, [rax+8]
0x140007038  mov     rax, [r11+8]
0x14000703c  movzx   r8d, byte ptr [rcx+rax+3]
0x140007042  test    r8b, 0Fh
0x140007046  jz      short loc_140007058
0x140007048  mov     eax, r8d
0x14000704b  mov     ecx, 0FFFFFFF0h
0x140007050  and     rax, rcx
0x140007053  add     rax, r10
0x140007056  jmp     short loc_14000705B
0x140007058  mov     rax, r10
0x14000705b  xor     rdx, rax
0x14000705e  mov     rcx, rdx; StackCookie
0x140007061  call    __security_check_cookie
0x140007066  add     rsp, 28h
0x14000706a  retn
```
