# UpdateInternalStatsOnFlush

- ea: `0x18003d0dc`
- end: `0x18003d11e`
- name: `UpdateInternalStatsOnFlush`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18003cb80`
- `0x18003cef8`

## callees

- `0x18003d0dc`

## pseudocode

```c
void __fastcall UpdateInternalStatsOnFlush(__int64 a1, unsigned int a2)
{
  __int64 *v2; // r8
  __int64 v3; // rax

  if ( a2 )
  {
    v2 = (__int64 *)(a1 + 296);
    if ( *(_DWORD *)(a1 + 312) > a2 || (v3 = *v2) == 0 )
    {
      v3 = *v2;
      *(_DWORD *)(a1 + 312) = a2;
    }
    if ( *(_DWORD *)(a1 + 308) < a2 )
      *(_DWORD *)(a1 + 308) = a2;
    *v2 = v3 + 1;
    *(_QWORD *)(a1 + 288) += a2;
  }
}

```

## disassembly

```asm
0x18003d0dc  test    edx, edx
0x18003d0de  jz      short locret_18003D11D
0x18003d0e0  lea     r8, [rcx+128h]
0x18003d0e7  cmp     [rcx+138h], edx
0x18003d0ed  ja      short loc_18003D0F7
0x18003d0ef  mov     rax, [r8]
0x18003d0f2  test    rax, rax
0x18003d0f5  jnz     short loc_18003D100
0x18003d0f7  mov     rax, [r8]
0x18003d0fa  mov     [rcx+138h], edx
0x18003d100  cmp     [rcx+134h], edx
0x18003d106  jnb     short loc_18003D10E
0x18003d108  mov     [rcx+134h], edx
0x18003d10e  inc     rax
0x18003d111  mov     [r8], rax
0x18003d114  mov     eax, edx
0x18003d116  add     [rcx+120h], rax
0x18003d11d  retn
```
