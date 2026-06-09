# __GSHandlerCheckCommon

- ea: `0x14002c44c`
- end: `0x14002c4bc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002c428`

## callees

- `0x14002c44c`
- `0x14002c6d0`

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
0x14002c44c  sub     rsp, 28h
0x14002c450  mov     eax, [r8]
0x14002c453  mov     r10, rcx
0x14002c456  mov     ecx, eax
0x14002c458  mov     r11, rdx
0x14002c45b  and     ecx, 0FFFFFFF8h
0x14002c45e  test    al, 4
0x14002c460  jz      short loc_14002C477
0x14002c462  mov     eax, [r8+8]
0x14002c466  movsxd  r9, dword ptr [r8+4]
0x14002c46a  neg     eax
0x14002c46c  movsxd  rdx, eax
0x14002c46f  add     r9, r10
0x14002c472  and     r9, rdx
0x14002c475  jmp     short loc_14002C47A
0x14002c477  mov     r9, r10
0x14002c47a  movsxd  rax, ecx
0x14002c47d  mov     rdx, [rax+r9]
0x14002c481  mov     rax, [r11+10h]
0x14002c485  mov     ecx, [rax+8]
0x14002c488  mov     rax, [r11+8]
0x14002c48c  movzx   r8d, byte ptr [rcx+rax+3]
0x14002c492  test    r8b, 0Fh
0x14002c496  jz      short loc_14002C4A8
0x14002c498  mov     eax, r8d
0x14002c49b  mov     ecx, 0FFFFFFF0h
0x14002c4a0  and     rax, rcx
0x14002c4a3  add     rax, r10
0x14002c4a6  jmp     short loc_14002C4AB
0x14002c4a8  mov     rax, r10
0x14002c4ab  xor     rdx, rax
0x14002c4ae  mov     rcx, rdx; StackCookie
0x14002c4b1  call    __security_check_cookie
0x14002c4b6  add     rsp, 28h
0x14002c4ba  retn
```
