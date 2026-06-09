# __GSHandlerCheckCommon

- ea: `0x180009400`
- end: `0x180009463`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800093dc`
- `0x18000946c`

## callees

- `0x1800015b0`
- `0x180009400`

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
0x180009400  mov     r10, rcx
0x180009403  mov     r11, rdx
0x180009406  mov     ecx, [r8]
0x180009409  and     ecx, 0FFFFFFF8h
0x18000940c  test    byte ptr [r8], 4
0x180009410  jz      short loc_180009427
0x180009412  mov     eax, [r8+8]
0x180009416  movsxd  r9, dword ptr [r8+4]
0x18000941a  neg     eax
0x18000941c  movsxd  rdx, eax
0x18000941f  add     r9, r10
0x180009422  and     r9, rdx
0x180009425  jmp     short loc_18000942A
0x180009427  mov     r9, r10
0x18000942a  movsxd  rax, ecx
0x18000942d  mov     rdx, [rax+r9]
0x180009431  mov     rax, [r11+10h]
0x180009435  mov     ecx, [rax+8]
0x180009438  mov     rax, [r11+8]
0x18000943c  test    byte ptr [rcx+rax+3], 0Fh
0x180009441  jz      short loc_180009455
0x180009443  movzx   eax, byte ptr [rcx+rax+3]
0x180009448  mov     ecx, 0FFFFFFF0h
0x18000944d  and     rax, rcx
0x180009450  add     rax, r10
0x180009453  jmp     short loc_180009458
0x180009455  mov     rax, r10
0x180009458  xor     rdx, rax
0x18000945b  mov     rcx, rdx; StackCookie
0x18000945e  jmp     __security_check_cookie
```
