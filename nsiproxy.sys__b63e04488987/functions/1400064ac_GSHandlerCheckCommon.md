# __GSHandlerCheckCommon

- ea: `0x1400064ac`
- end: `0x14000651c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006488`

## callees

- `0x1400064ac`
- `0x140006530`

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
0x1400064ac  sub     rsp, 28h
0x1400064b0  mov     eax, [r8]
0x1400064b3  mov     r10, rcx
0x1400064b6  mov     ecx, eax
0x1400064b8  mov     r11, rdx
0x1400064bb  and     ecx, 0FFFFFFF8h
0x1400064be  test    al, 4
0x1400064c0  jz      short loc_1400064D7
0x1400064c2  mov     eax, [r8+8]
0x1400064c6  movsxd  r9, dword ptr [r8+4]
0x1400064ca  neg     eax
0x1400064cc  movsxd  rdx, eax
0x1400064cf  add     r9, r10
0x1400064d2  and     r9, rdx
0x1400064d5  jmp     short loc_1400064DA
0x1400064d7  mov     r9, r10
0x1400064da  movsxd  rax, ecx
0x1400064dd  mov     rdx, [rax+r9]
0x1400064e1  mov     rax, [r11+10h]
0x1400064e5  mov     ecx, [rax+8]
0x1400064e8  mov     rax, [r11+8]
0x1400064ec  movzx   r8d, byte ptr [rcx+rax+3]
0x1400064f2  test    r8b, 0Fh
0x1400064f6  jz      short loc_140006508
0x1400064f8  mov     eax, r8d
0x1400064fb  mov     ecx, 0FFFFFFF0h
0x140006500  and     rax, rcx
0x140006503  add     rax, r10
0x140006506  jmp     short loc_14000650B
0x140006508  mov     rax, r10
0x14000650b  xor     rdx, rax
0x14000650e  mov     rcx, rdx; StackCookie
0x140006511  call    __security_check_cookie
0x140006516  add     rsp, 28h
0x14000651a  retn
```
