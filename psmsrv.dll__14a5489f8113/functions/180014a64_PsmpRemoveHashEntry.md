# PsmpRemoveHashEntry

- ea: `0x180014a64`
- end: `0x180014aec`
- name: `PsmpRemoveHashEntry`
- size: `136`
- prototype: `__int64 __fastcall(volatile signed __int32 *, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002740`
- `0x180009b40`
- `0x18000c5b8`
- `0x18001d688`

## callees

- `0x180014a64`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180014a89`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180014a89`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180014ab7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180014ab7`

## pseudocode

```c
__int64 __fastcall PsmpRemoveHashEntry(volatile signed __int32 *a1, __int64 a2)
{
  char v3; // si
  volatile signed __int32 *v5; // rbp
  __int64 v6; // rax
  __int64 v7; // r8
  _QWORD *v8; // rdx
  __int64 result; // rax

  v3 = 1;
  v5 = &a1[6 * *(unsigned int *)(a2 + 4) + 6];
  RtlAcquireSRWLockExclusive(v5);
  v6 = a2 + 24;
  v7 = *(_QWORD *)(a2 + 24);
  if ( v7 != a2 + 24 )
  {
    if ( *(_QWORD *)(v7 + 8) != v6 || (v8 = *(_QWORD **)(a2 + 32), *v8 != v6) )
      __fastfail(3u);
    *v8 = v7;
    v3 = 0;
    *(_QWORD *)(v7 + 8) = v8;
  }
  result = RtlReleaseSRWLockExclusive(v5);
  if ( !v3 )
  {
    _m_prefetchw((const void *)a2);
    result = (unsigned int)_InterlockedOr((volatile signed __int32 *)a2, 0x80000000);
    if ( (int)result >= 0 )
      _InterlockedDecrement(a1);
  }
  return result;
}

```

## disassembly

```asm
0x180014a64  push    rbx
0x180014a66  push    rbp
0x180014a67  push    rsi
0x180014a68  push    rdi
0x180014a69  sub     rsp, 28h
0x180014a6d  mov     eax, [rdx+4]
0x180014a70  mov     rdi, rcx
0x180014a73  mov     esi, 1
0x180014a78  mov     rbx, rdx
0x180014a7b  add     rax, rsi
0x180014a7e  lea     rax, [rax+rax*2]
0x180014a82  lea     rbp, [rcx+rax*8]
0x180014a86  mov     rcx, rbp
0x180014a89  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180014a8f  lea     rax, [rbx+18h]
0x180014a93  mov     r8, [rax]
0x180014a96  cmp     r8, rax
0x180014a99  jz      short loc_180014AB4
0x180014a9b  cmp     [r8+8], rax
0x180014a9f  jnz     short loc_180014AE5
0x180014aa1  mov     rdx, [rax+8]
0x180014aa5  cmp     [rdx], rax
0x180014aa8  jnz     short loc_180014AE5
0x180014aaa  mov     [rdx], r8
0x180014aad  xor     sil, sil
0x180014ab0  mov     [r8+8], rdx
0x180014ab4  mov     rcx, rbp
0x180014ab7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180014abd  test    sil, sil
0x180014ac0  jnz     short loc_180014ADC
0x180014ac2  prefetchw byte ptr [rbx]
0x180014ac5  mov     eax, [rbx]
0x180014ac7  mov     ecx, eax
0x180014ac9  or      ecx, 80000000h
0x180014acf  lock cmpxchg [rbx], ecx
0x180014ad3  jnz     short loc_180014AC7
0x180014ad5  test    eax, eax
0x180014ad7  js      short loc_180014ADC
0x180014ad9  lock dec dword ptr [rdi]
0x180014adc  add     rsp, 28h
0x180014ae0  pop     rdi
0x180014ae1  pop     rsi
0x180014ae2  pop     rbp
0x180014ae3  pop     rbx
0x180014ae4  retn
0x180014ae5  mov     ecx, 3
0x180014aea  int     29h; Win8: RtlFailFast(ecx)
```
