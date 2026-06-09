# __GSHandlerCheckCommon

- ea: `0x14000b92c`
- end: `0x14000b99c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000b908`
- `0x14000b9a4`

## callees

- `0x14000b92c`
- `0x14000ba20`

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
0x14000b92c  sub     rsp, 28h
0x14000b930  mov     eax, [r8]
0x14000b933  mov     r10, rcx
0x14000b936  mov     ecx, eax
0x14000b938  mov     r11, rdx
0x14000b93b  and     ecx, 0FFFFFFF8h
0x14000b93e  test    al, 4
0x14000b940  jz      short loc_14000B957
0x14000b942  mov     eax, [r8+8]
0x14000b946  movsxd  r9, dword ptr [r8+4]
0x14000b94a  neg     eax
0x14000b94c  movsxd  rdx, eax
0x14000b94f  add     r9, r10
0x14000b952  and     r9, rdx
0x14000b955  jmp     short loc_14000B95A
0x14000b957  mov     r9, r10
0x14000b95a  movsxd  rax, ecx
0x14000b95d  mov     rdx, [rax+r9]
0x14000b961  mov     rax, [r11+10h]
0x14000b965  mov     ecx, [rax+8]
0x14000b968  mov     rax, [r11+8]
0x14000b96c  movzx   r8d, byte ptr [rcx+rax+3]
0x14000b972  test    r8b, 0Fh
0x14000b976  jz      short loc_14000B988
0x14000b978  mov     eax, r8d
0x14000b97b  mov     ecx, 0FFFFFFF0h
0x14000b980  and     rax, rcx
0x14000b983  add     rax, r10
0x14000b986  jmp     short loc_14000B98B
0x14000b988  mov     rax, r10
0x14000b98b  xor     rdx, rax
0x14000b98e  mov     rcx, rdx; StackCookie
0x14000b991  call    __security_check_cookie
0x14000b996  add     rsp, 28h
0x14000b99a  retn
```
