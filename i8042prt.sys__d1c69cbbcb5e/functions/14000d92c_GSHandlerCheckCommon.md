# __GSHandlerCheckCommon

- ea: `0x14000d92c`
- end: `0x14000d99c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d908`

## callees

- `0x14000d92c`
- `0x14000da60`

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
0x14000d92c  sub     rsp, 28h
0x14000d930  mov     eax, [r8]
0x14000d933  mov     r10, rcx
0x14000d936  mov     ecx, eax
0x14000d938  mov     r11, rdx
0x14000d93b  and     ecx, 0FFFFFFF8h
0x14000d93e  test    al, 4
0x14000d940  jz      short loc_14000D957
0x14000d942  mov     eax, [r8+8]
0x14000d946  movsxd  r9, dword ptr [r8+4]
0x14000d94a  neg     eax
0x14000d94c  movsxd  rdx, eax
0x14000d94f  add     r9, r10
0x14000d952  and     r9, rdx
0x14000d955  jmp     short loc_14000D95A
0x14000d957  mov     r9, r10
0x14000d95a  movsxd  rax, ecx
0x14000d95d  mov     rdx, [rax+r9]
0x14000d961  mov     rax, [r11+10h]
0x14000d965  mov     ecx, [rax+8]
0x14000d968  mov     rax, [r11+8]
0x14000d96c  movzx   r8d, byte ptr [rcx+rax+3]
0x14000d972  test    r8b, 0Fh
0x14000d976  jz      short loc_14000D988
0x14000d978  mov     eax, r8d
0x14000d97b  mov     ecx, 0FFFFFFF0h
0x14000d980  and     rax, rcx
0x14000d983  add     rax, r10
0x14000d986  jmp     short loc_14000D98B
0x14000d988  mov     rax, r10
0x14000d98b  xor     rdx, rax
0x14000d98e  mov     rcx, rdx; StackCookie
0x14000d991  call    __security_check_cookie
0x14000d996  add     rsp, 28h
0x14000d99a  retn
```
