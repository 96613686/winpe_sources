# __GSHandlerCheckCommon

- ea: `0x1800093ec`
- end: `0x18000944f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800093c8`

## callees

- `0x1800093ec`
- `0x180009490`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax

  v3 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  v4 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v3 + v4 + 3) & 0xF) != 0 )
    return a1 + (*(_BYTE *)(v3 + v4 + 3) & 0xF0);
  else
    return a1;
}

```

## disassembly

```asm
0x1800093ec  mov     r10, rcx
0x1800093ef  mov     r11, rdx
0x1800093f2  mov     ecx, [r8]
0x1800093f5  and     ecx, 0FFFFFFF8h
0x1800093f8  test    byte ptr [r8], 4
0x1800093fc  jz      short loc_180009413
0x1800093fe  mov     eax, [r8+8]
0x180009402  movsxd  r9, dword ptr [r8+4]
0x180009406  neg     eax
0x180009408  movsxd  rdx, eax
0x18000940b  add     r9, r10
0x18000940e  and     r9, rdx
0x180009411  jmp     short loc_180009416
0x180009413  mov     r9, r10
0x180009416  movsxd  rax, ecx
0x180009419  mov     rdx, [rax+r9]
0x18000941d  mov     rax, [r11+10h]
0x180009421  mov     ecx, [rax+8]
0x180009424  mov     rax, [r11+8]
0x180009428  test    byte ptr [rcx+rax+3], 0Fh
0x18000942d  jz      short loc_180009441
0x18000942f  movzx   eax, byte ptr [rcx+rax+3]
0x180009434  mov     ecx, 0FFFFFFF0h
0x180009439  and     rax, rcx
0x18000943c  add     rax, r10
0x18000943f  jmp     short loc_180009444
0x180009441  mov     rax, r10
0x180009444  xor     rdx, rax
0x180009447  mov     rcx, rdx; StackCookie
0x18000944a  jmp     __security_check_cookie
```
