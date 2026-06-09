# __GSHandlerCheckCommon

- ea: `0x14000292c`
- end: `0x14000299c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002908`
- `0x1400029a4`

## callees

- `0x14000292c`
- `0x140002ae0`

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
0x14000292c  sub     rsp, 28h
0x140002930  mov     eax, [r8]
0x140002933  mov     r10, rcx
0x140002936  mov     ecx, eax
0x140002938  mov     r11, rdx
0x14000293b  and     ecx, 0FFFFFFF8h
0x14000293e  test    al, 4
0x140002940  jz      short loc_140002957
0x140002942  mov     eax, [r8+8]
0x140002946  movsxd  r9, dword ptr [r8+4]
0x14000294a  neg     eax
0x14000294c  movsxd  rdx, eax
0x14000294f  add     r9, r10
0x140002952  and     r9, rdx
0x140002955  jmp     short loc_14000295A
0x140002957  mov     r9, r10
0x14000295a  movsxd  rax, ecx
0x14000295d  mov     rdx, [rax+r9]
0x140002961  mov     rax, [r11+10h]
0x140002965  mov     ecx, [rax+8]
0x140002968  mov     rax, [r11+8]
0x14000296c  movzx   r8d, byte ptr [rcx+rax+3]
0x140002972  test    r8b, 0Fh
0x140002976  jz      short loc_140002988
0x140002978  mov     eax, r8d
0x14000297b  mov     ecx, 0FFFFFFF0h
0x140002980  and     rax, rcx
0x140002983  add     rax, r10
0x140002986  jmp     short loc_14000298B
0x140002988  mov     rax, r10
0x14000298b  xor     rdx, rax
0x14000298e  mov     rcx, rdx; StackCookie
0x140002991  call    __security_check_cookie
0x140002996  add     rsp, 28h
0x14000299a  retn
```
