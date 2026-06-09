# __GSHandlerCheckCommon

- ea: `0x14000be6c`
- end: `0x14000bedc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000be48`

## callees

- `0x14000be6c`
- `0x14000bfa0`

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
0x14000be6c  sub     rsp, 28h
0x14000be70  mov     eax, [r8]
0x14000be73  mov     r10, rcx
0x14000be76  mov     ecx, eax
0x14000be78  mov     r11, rdx
0x14000be7b  and     ecx, 0FFFFFFF8h
0x14000be7e  test    al, 4
0x14000be80  jz      short loc_14000BE97
0x14000be82  mov     eax, [r8+8]
0x14000be86  movsxd  r9, dword ptr [r8+4]
0x14000be8a  neg     eax
0x14000be8c  movsxd  rdx, eax
0x14000be8f  add     r9, r10
0x14000be92  and     r9, rdx
0x14000be95  jmp     short loc_14000BE9A
0x14000be97  mov     r9, r10
0x14000be9a  movsxd  rax, ecx
0x14000be9d  mov     rdx, [rax+r9]
0x14000bea1  mov     rax, [r11+10h]
0x14000bea5  mov     ecx, [rax+8]
0x14000bea8  mov     rax, [r11+8]
0x14000beac  movzx   r8d, byte ptr [rcx+rax+3]
0x14000beb2  test    r8b, 0Fh
0x14000beb6  jz      short loc_14000BEC8
0x14000beb8  mov     eax, r8d
0x14000bebb  mov     ecx, 0FFFFFFF0h
0x14000bec0  and     rax, rcx
0x14000bec3  add     rax, r10
0x14000bec6  jmp     short loc_14000BECB
0x14000bec8  mov     rax, r10
0x14000becb  xor     rdx, rax
0x14000bece  mov     rcx, rdx; StackCookie
0x14000bed1  call    __security_check_cookie
0x14000bed6  add     rsp, 28h
0x14000beda  retn
```
