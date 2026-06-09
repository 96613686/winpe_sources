# __GSHandlerCheckCommon

- ea: `0x14000536c`
- end: `0x1400053dc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005348`

## callees

- `0x14000536c`
- `0x1400054a0`

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
0x14000536c  sub     rsp, 28h
0x140005370  mov     eax, [r8]
0x140005373  mov     r10, rcx
0x140005376  mov     ecx, eax
0x140005378  mov     r11, rdx
0x14000537b  and     ecx, 0FFFFFFF8h
0x14000537e  test    al, 4
0x140005380  jz      short loc_140005397
0x140005382  mov     eax, [r8+8]
0x140005386  movsxd  r9, dword ptr [r8+4]
0x14000538a  neg     eax
0x14000538c  movsxd  rdx, eax
0x14000538f  add     r9, r10
0x140005392  and     r9, rdx
0x140005395  jmp     short loc_14000539A
0x140005397  mov     r9, r10
0x14000539a  movsxd  rax, ecx
0x14000539d  mov     rdx, [rax+r9]
0x1400053a1  mov     rax, [r11+10h]
0x1400053a5  mov     ecx, [rax+8]
0x1400053a8  mov     rax, [r11+8]
0x1400053ac  movzx   r8d, byte ptr [rcx+rax+3]
0x1400053b2  test    r8b, 0Fh
0x1400053b6  jz      short loc_1400053C8
0x1400053b8  mov     eax, r8d
0x1400053bb  mov     ecx, 0FFFFFFF0h
0x1400053c0  and     rax, rcx
0x1400053c3  add     rax, r10
0x1400053c6  jmp     short loc_1400053CB
0x1400053c8  mov     rax, r10
0x1400053cb  xor     rdx, rax
0x1400053ce  mov     rcx, rdx; StackCookie
0x1400053d1  call    __security_check_cookie
0x1400053d6  add     rsp, 28h
0x1400053da  retn
```
