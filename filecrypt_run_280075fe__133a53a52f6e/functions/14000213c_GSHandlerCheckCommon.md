# __GSHandlerCheckCommon

- ea: `0x14000213c`
- end: `0x1400021ac`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002118`
- `0x1400034c8`

## callees

- `0x14000213c`
- `0x140003540`

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
0x14000213c  sub     rsp, 28h
0x140002140  mov     eax, [r8]
0x140002143  mov     r10, rcx
0x140002146  mov     ecx, eax
0x140002148  mov     r11, rdx
0x14000214b  and     ecx, 0FFFFFFF8h
0x14000214e  test    al, 4
0x140002150  jz      short loc_140002167
0x140002152  mov     eax, [r8+8]
0x140002156  movsxd  r9, dword ptr [r8+4]
0x14000215a  neg     eax
0x14000215c  movsxd  rdx, eax
0x14000215f  add     r9, r10
0x140002162  and     r9, rdx
0x140002165  jmp     short loc_14000216A
0x140002167  mov     r9, r10
0x14000216a  movsxd  rax, ecx
0x14000216d  mov     rdx, [rax+r9]
0x140002171  mov     rax, [r11+10h]
0x140002175  mov     ecx, [rax+8]
0x140002178  mov     rax, [r11+8]
0x14000217c  movzx   r8d, byte ptr [rcx+rax+3]
0x140002182  test    r8b, 0Fh
0x140002186  jz      short loc_140002198
0x140002188  mov     eax, r8d
0x14000218b  mov     ecx, 0FFFFFFF0h
0x140002190  and     rax, rcx
0x140002193  add     rax, r10
0x140002196  jmp     short loc_14000219B
0x140002198  mov     rax, r10
0x14000219b  xor     rdx, rax
0x14000219e  mov     rcx, rdx; StackCookie
0x1400021a1  call    __security_check_cookie
0x1400021a6  add     rsp, 28h
0x1400021aa  retn
```
