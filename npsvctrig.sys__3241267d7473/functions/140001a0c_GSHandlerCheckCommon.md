# __GSHandlerCheckCommon

- ea: `0x140001a0c`
- end: `0x140001a7c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400019e8`

## callees

- `0x140001a0c`
- `0x140001b40`

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
0x140001a0c  sub     rsp, 28h
0x140001a10  mov     eax, [r8]
0x140001a13  mov     r10, rcx
0x140001a16  mov     ecx, eax
0x140001a18  mov     r11, rdx
0x140001a1b  and     ecx, 0FFFFFFF8h
0x140001a1e  test    al, 4
0x140001a20  jz      short loc_140001A37
0x140001a22  mov     eax, [r8+8]
0x140001a26  movsxd  r9, dword ptr [r8+4]
0x140001a2a  neg     eax
0x140001a2c  movsxd  rdx, eax
0x140001a2f  add     r9, r10
0x140001a32  and     r9, rdx
0x140001a35  jmp     short loc_140001A3A
0x140001a37  mov     r9, r10
0x140001a3a  movsxd  rax, ecx
0x140001a3d  mov     rdx, [rax+r9]
0x140001a41  mov     rax, [r11+10h]
0x140001a45  mov     ecx, [rax+8]
0x140001a48  mov     rax, [r11+8]
0x140001a4c  movzx   r8d, byte ptr [rcx+rax+3]
0x140001a52  test    r8b, 0Fh
0x140001a56  jz      short loc_140001A68
0x140001a58  mov     eax, r8d
0x140001a5b  mov     ecx, 0FFFFFFF0h
0x140001a60  and     rax, rcx
0x140001a63  add     rax, r10
0x140001a66  jmp     short loc_140001A6B
0x140001a68  mov     rax, r10
0x140001a6b  xor     rdx, rax
0x140001a6e  mov     rcx, rdx; StackCookie
0x140001a71  call    __security_check_cookie
0x140001a76  add     rsp, 28h
0x140001a7a  retn
```
