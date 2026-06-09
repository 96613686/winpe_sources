# VerifyAdditionalProtocolList(uchar *,ulong,ulong)

- ea: `0x1400351f0`
- end: `0x14003524f`
- name: `?VerifyAdditionalProtocolList@@YAJPEAEKK@Z`
- size: `95`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400351f0`
- `0x1400352d4`
- `0x1400354c0`

## pseudocode

```c
__int64 __fastcall VerifyAdditionalProtocolList(unsigned __int8 *a1, unsigned int a2, int a3)
{
  __int64 result; // rax
  int v7; // eax
  unsigned int v8; // ecx

  if ( (*a1 & 0xF8) != 0x30 )
    return 3221225485LL;
  result = VerifyMultipleProtocolLists(a1, a2, a3);
  if ( (int)result >= 0 )
    return 0;
  if ( (a3 & 2) == 0 )
  {
    v7 = VerifySingleProtocolList(a1, a2, a3);
    v8 = 0;
    if ( v7 < 0 )
      return (unsigned int)v7;
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x1400351f0  mov     [rsp+arg_0], rbx
0x1400351f5  mov     [rsp+arg_8], rsi
0x1400351fa  push    rdi
0x1400351fb  sub     rsp, 20h
0x1400351ff  mov     al, [rcx]
0x140035201  mov     ebx, r8d
0x140035204  and     al, 0F8h
0x140035206  mov     esi, edx
0x140035208  mov     rdi, rcx
0x14003520b  cmp     al, 30h ; '0'
0x14003520d  jz      short loc_140035216
0x14003520f  mov     eax, 0C000000Dh
0x140035214  jmp     short loc_14003523E
0x140035216  call    ?VerifyMultipleProtocolLists@@YAJPEAEKK@Z; VerifyMultipleProtocolLists(uchar *,ulong,ulong)
0x14003521b  test    eax, eax
0x14003521d  jns     short loc_14003523C
0x14003521f  test    bl, 2
0x140035222  jnz     short loc_14003523E
0x140035224  mov     r8d, ebx; unsigned int
0x140035227  mov     edx, esi; unsigned int
0x140035229  mov     rcx, rdi; unsigned __int8 *
0x14003522c  call    ?VerifySingleProtocolList@@YAJPEAEKK@Z; VerifySingleProtocolList(uchar *,ulong,ulong)
0x140035231  xor     ecx, ecx
0x140035233  test    eax, eax
0x140035235  cmovs   ecx, eax
0x140035238  mov     eax, ecx
0x14003523a  jmp     short loc_14003523E
0x14003523c  xor     eax, eax
0x14003523e  mov     rbx, [rsp+28h+arg_0]
0x140035243  mov     rsi, [rsp+28h+arg_8]
0x140035248  add     rsp, 20h
0x14003524c  pop     rdi
0x14003524d  retn
```
