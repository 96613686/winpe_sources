# __GSHandlerCheckCommon

- ea: `0x18001072c`
- end: `0x18001079c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010708`
- `0x1800107a4`

## callees

- `0x18001072c`
- `0x180010840`

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
0x18001072c  sub     rsp, 28h
0x180010730  mov     eax, [r8]
0x180010733  mov     r10, rcx
0x180010736  mov     ecx, eax
0x180010738  mov     r11, rdx
0x18001073b  and     ecx, 0FFFFFFF8h
0x18001073e  test    al, 4
0x180010740  jz      short loc_180010757
0x180010742  mov     eax, [r8+8]
0x180010746  movsxd  r9, dword ptr [r8+4]
0x18001074a  neg     eax
0x18001074c  movsxd  rdx, eax
0x18001074f  add     r9, r10
0x180010752  and     r9, rdx
0x180010755  jmp     short loc_18001075A
0x180010757  mov     r9, r10
0x18001075a  movsxd  rax, ecx
0x18001075d  mov     rdx, [rax+r9]
0x180010761  mov     rax, [r11+10h]
0x180010765  mov     ecx, [rax+8]
0x180010768  mov     rax, [r11+8]
0x18001076c  movzx   r8d, byte ptr [rcx+rax+3]
0x180010772  test    r8b, 0Fh
0x180010776  jz      short loc_180010788
0x180010778  mov     eax, r8d
0x18001077b  mov     ecx, 0FFFFFFF0h
0x180010780  and     rax, rcx
0x180010783  add     rax, r10
0x180010786  jmp     short loc_18001078B
0x180010788  mov     rax, r10
0x18001078b  xor     rdx, rax
0x18001078e  mov     rcx, rdx; StackCookie
0x180010791  call    __security_check_cookie
0x180010796  add     rsp, 28h
0x18001079a  retn
```
