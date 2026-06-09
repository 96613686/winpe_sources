# LcmCmOpenAf

- ea: `0x140001a90`
- end: `0x140001adf`
- name: `LcmCmOpenAf`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001a90`

## pseudocode

```c
__int64 __fastcall LcmCmOpenAf(__int64 a1, _DWORD *a2, signed __int64 a3, _QWORD *a4)
{
  if ( *(_DWORD *)a1 != 827601484 )
    return 3221291029LL;
  if ( *a2 != 2049 || a2[1] != 6 || a2[2] != 30 )
    return 3221291012LL;
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 352), a3, 0) )
    return 3221225473LL;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 376));
  *a4 = a1;
  return 0;
}

```

## disassembly

```asm
0x140001a90  cmp     dword ptr [rcx], 3154324Ch
0x140001a96  jnz     short loc_140001AC0
0x140001a98  cmp     dword ptr [rdx], 801h
0x140001a9e  jnz     short loc_140001AD9
0x140001aa0  cmp     dword ptr [rdx+4], 6
0x140001aa4  jnz     short loc_140001AD9
0x140001aa6  cmp     dword ptr [rdx+8], 1Eh
0x140001aaa  jnz     short loc_140001AD9
0x140001aac  xor     eax, eax
0x140001aae  lock cmpxchg [rcx+160h], r8
0x140001ab7  jz      short loc_140001AC7
0x140001ab9  mov     eax, 0C0000001h
0x140001abe  retn
0x140001ac0  mov     eax, 0C0010015h
0x140001ac5  retn
0x140001ac7  lock inc dword ptr [rcx+4]
0x140001acb  lock inc dword ptr [rcx+178h]
0x140001ad2  mov     [r9], rcx
0x140001ad5  xor     eax, eax
0x140001ad7  retn
0x140001ad9  mov     eax, 0C0010004h
0x140001ade  retn
```
