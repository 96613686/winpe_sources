# __GSHandlerCheckCommon

- ea: `0x1400370fc`
- end: `0x14003716c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400370d8`
- `0x140037174`

## callees

- `0x1400370fc`
- `0x1400371f0`

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
0x1400370fc  sub     rsp, 28h
0x140037100  mov     eax, [r8]
0x140037103  mov     r10, rcx
0x140037106  mov     ecx, eax
0x140037108  mov     r11, rdx
0x14003710b  and     ecx, 0FFFFFFF8h
0x14003710e  test    al, 4
0x140037110  jz      short loc_140037127
0x140037112  mov     eax, [r8+8]
0x140037116  movsxd  r9, dword ptr [r8+4]
0x14003711a  neg     eax
0x14003711c  movsxd  rdx, eax
0x14003711f  add     r9, r10
0x140037122  and     r9, rdx
0x140037125  jmp     short loc_14003712A
0x140037127  mov     r9, r10
0x14003712a  movsxd  rax, ecx
0x14003712d  mov     rdx, [rax+r9]
0x140037131  mov     rax, [r11+10h]
0x140037135  mov     ecx, [rax+8]
0x140037138  mov     rax, [r11+8]
0x14003713c  movzx   r8d, byte ptr [rcx+rax+3]
0x140037142  test    r8b, 0Fh
0x140037146  jz      short loc_140037158
0x140037148  mov     eax, r8d
0x14003714b  mov     ecx, 0FFFFFFF0h
0x140037150  and     rax, rcx
0x140037153  add     rax, r10
0x140037156  jmp     short loc_14003715B
0x140037158  mov     rax, r10
0x14003715b  xor     rdx, rax
0x14003715e  mov     rcx, rdx; StackCookie
0x140037161  call    __security_check_cookie
0x140037166  add     rsp, 28h
0x14003716a  retn
```
