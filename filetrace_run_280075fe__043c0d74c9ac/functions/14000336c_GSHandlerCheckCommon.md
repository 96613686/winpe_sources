# __GSHandlerCheckCommon

- ea: `0x14000336c`
- end: `0x1400033dc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003348`
- `0x1400033e4`

## callees

- `0x14000336c`
- `0x140003510`

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
0x14000336c  sub     rsp, 28h
0x140003370  mov     eax, [r8]
0x140003373  mov     r10, rcx
0x140003376  mov     ecx, eax
0x140003378  mov     r11, rdx
0x14000337b  and     ecx, 0FFFFFFF8h
0x14000337e  test    al, 4
0x140003380  jz      short loc_140003397
0x140003382  mov     eax, [r8+8]
0x140003386  movsxd  r9, dword ptr [r8+4]
0x14000338a  neg     eax
0x14000338c  movsxd  rdx, eax
0x14000338f  add     r9, r10
0x140003392  and     r9, rdx
0x140003395  jmp     short loc_14000339A
0x140003397  mov     r9, r10
0x14000339a  movsxd  rax, ecx
0x14000339d  mov     rdx, [rax+r9]
0x1400033a1  mov     rax, [r11+10h]
0x1400033a5  mov     ecx, [rax+8]
0x1400033a8  mov     rax, [r11+8]
0x1400033ac  movzx   r8d, byte ptr [rcx+rax+3]
0x1400033b2  test    r8b, 0Fh
0x1400033b6  jz      short loc_1400033C8
0x1400033b8  mov     eax, r8d
0x1400033bb  mov     ecx, 0FFFFFFF0h
0x1400033c0  and     rax, rcx
0x1400033c3  add     rax, r10
0x1400033c6  jmp     short loc_1400033CB
0x1400033c8  mov     rax, r10
0x1400033cb  xor     rdx, rax
0x1400033ce  mov     rcx, rdx; StackCookie
0x1400033d1  call    __security_check_cookie
0x1400033d6  add     rsp, 28h
0x1400033da  retn
```
