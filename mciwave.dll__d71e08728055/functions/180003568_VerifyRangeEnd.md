# VerifyRangeEnd

- ea: `0x180003568`
- end: `0x1800035ca`
- name: `VerifyRangeEnd`
- size: `98`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180003614`
- `0x180003d64`
- `0x18000492c`

## callees

- `0x180003410`
- `0x180003568`
- `0x1800035d0`

## pseudocode

```c
__int64 __fastcall VerifyRangeEnd(__int64 a1, unsigned int a2, int a3)
{
  unsigned int v6; // eax
  bool v7; // zf
  __int64 result; // rax

  v6 = bytes2time(a1, *(_DWORD *)(a1 + 76), *(_DWORD *)(a1 + 8));
  if ( a3 )
  {
    v7 = a2 == v6;
    if ( a2 > v6 )
      return 0xFFFFFFFFLL;
  }
  else
  {
    v7 = a2 == v6;
  }
  if ( v7 )
    return *(unsigned int *)(a1 + 76);
  result = RoundedBytePosition(a1, a2, *(_DWORD *)(a1 + 8));
  if ( a3 )
  {
    if ( (unsigned int)result > *(_DWORD *)(a1 + 76) )
      return *(unsigned int *)(a1 + 76);
  }
  return result;
}

```

## disassembly

```asm
0x180003568  mov     [rsp+arg_0], rbx
0x18000356d  mov     [rsp+arg_8], rsi
0x180003572  push    rdi
0x180003573  sub     rsp, 20h
0x180003577  mov     esi, r8d
0x18000357a  mov     edi, edx
0x18000357c  mov     r8d, [rcx+8]
0x180003580  mov     rbx, rcx
0x180003583  mov     edx, [rcx+4Ch]
0x180003586  call    bytes2time
0x18000358b  test    esi, esi
0x18000358d  jz      short loc_180003598
0x18000358f  cmp     edi, eax
0x180003591  jbe     short loc_18000359A
0x180003593  or      eax, 0FFFFFFFFh
0x180003596  jmp     short loc_1800035BA
0x180003598  cmp     edi, eax
0x18000359a  jnz     short loc_1800035A1
0x18000359c  mov     eax, [rbx+4Ch]
0x18000359f  jmp     short loc_1800035BA
0x1800035a1  mov     r8d, [rbx+8]
0x1800035a5  mov     edx, edi
0x1800035a7  mov     rcx, rbx
0x1800035aa  call    RoundedBytePosition
0x1800035af  test    esi, esi
0x1800035b1  jz      short loc_1800035BA
0x1800035b3  cmp     eax, [rbx+4Ch]
0x1800035b6  cmova   eax, [rbx+4Ch]
0x1800035ba  mov     rbx, [rsp+28h+arg_0]
0x1800035bf  mov     rsi, [rsp+28h+arg_8]
0x1800035c4  add     rsp, 20h
0x1800035c8  pop     rdi
0x1800035c9  retn
```
