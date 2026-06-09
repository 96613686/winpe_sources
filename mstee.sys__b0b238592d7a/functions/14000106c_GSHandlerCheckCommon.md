# __GSHandlerCheckCommon

- ea: `0x14000106c`
- end: `0x1400010dc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001048`

## callees

- `0x14000106c`
- `0x1400011a0`

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
0x14000106c  sub     rsp, 28h
0x140001070  mov     eax, [r8]
0x140001073  mov     r10, rcx
0x140001076  mov     ecx, eax
0x140001078  mov     r11, rdx
0x14000107b  and     ecx, 0FFFFFFF8h
0x14000107e  test    al, 4
0x140001080  jz      short loc_140001097
0x140001082  mov     eax, [r8+8]
0x140001086  movsxd  r9, dword ptr [r8+4]
0x14000108a  neg     eax
0x14000108c  movsxd  rdx, eax
0x14000108f  add     r9, r10
0x140001092  and     r9, rdx
0x140001095  jmp     short loc_14000109A
0x140001097  mov     r9, r10
0x14000109a  movsxd  rax, ecx
0x14000109d  mov     rdx, [rax+r9]
0x1400010a1  mov     rax, [r11+10h]
0x1400010a5  mov     ecx, [rax+8]
0x1400010a8  mov     rax, [r11+8]
0x1400010ac  movzx   r8d, byte ptr [rcx+rax+3]
0x1400010b2  test    r8b, 0Fh
0x1400010b6  jz      short loc_1400010C8
0x1400010b8  mov     eax, r8d
0x1400010bb  mov     ecx, 0FFFFFFF0h
0x1400010c0  and     rax, rcx
0x1400010c3  add     rax, r10
0x1400010c6  jmp     short loc_1400010CB
0x1400010c8  mov     rax, r10
0x1400010cb  xor     rdx, rax
0x1400010ce  mov     rcx, rdx; StackCookie
0x1400010d1  call    __security_check_cookie
0x1400010d6  add     rsp, 28h
0x1400010da  retn
```
