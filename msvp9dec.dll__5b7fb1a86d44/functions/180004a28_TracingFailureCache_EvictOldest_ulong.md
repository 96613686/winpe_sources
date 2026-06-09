# TracingFailureCache::EvictOldest(ulong)

- ea: `0x180004a28`
- end: `0x180004b36`
- name: `?EvictOldest@TracingFailureCache@@IEAAXK@Z`
- size: `270`
- prototype: `void __fastcall(TracingFailureCache *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800026d8`

## callees

- `0x18000386c`
- `0x180004a28`
- `0x180004e90`
- `0x180005039`

## pseudocode

```c
void __fastcall TracingFailureCache::EvictOldest(TracingFailureCache *this)
{
  unsigned int v2; // ebp
  char v3; // si
  int v4; // r14d
  unsigned int v5; // ebx
  TracingFailureDetails *v6; // rcx
  unsigned int i; // esi
  __int64 v8; // r8
  __int64 v9; // rbx

  if ( *((_DWORD *)this + 10) )
  {
    ++*((_DWORD *)this + 13);
    v2 = 0;
    v3 = 0;
    v4 = 7;
    qsort(*((void **)this + 11), *((unsigned int *)this + 10), 0x918u, TracingFailureDetails::CompareByTimeNewestFirst);
    v5 = *((_DWORD *)this + 10) - 1;
    do
    {
      v6 = (TracingFailureDetails *)(*((_QWORD *)this + 11) + 2328LL * v5);
      if ( *((_DWORD *)v6 + 505) )
      {
        if ( !v3 )
        {
          v3 = 1;
          v2 = v5;
        }
      }
      else
      {
        TracingFailureDetails::Reset(v6);
        --*((_DWORD *)this + 10);
        --v4;
      }
      if ( !v5 )
        break;
      --v5;
    }
    while ( v4 );
    if ( v3 )
    {
      for ( i = 0; i < *((_DWORD *)this + 10); ++i )
      {
        v8 = *((_QWORD *)this + 11);
        if ( !*(_DWORD *)(v8 + 2328LL * i + 2304) )
        {
          for ( ; !*(_DWORD *)(2328LL * v2 + v8 + 2020); --v2 )
            ;
          v9 = 2328LL * v2;
          memcpy_0((void *)(v8 + 2328LL * i), (const void *)(v9 + v8), 0x918u);
          TracingFailureDetails::Reset((TracingFailureDetails *)(v9 + *((_QWORD *)this + 11)));
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180004a28  push    rbx
0x180004a2a  push    rbp
0x180004a2b  push    rsi
0x180004a2c  push    rdi
0x180004a2d  push    r12
0x180004a2f  push    r14
0x180004a31  sub     rsp, 28h
0x180004a35  cmp     dword ptr [rcx+28h], 0
0x180004a39  mov     rdi, rcx
0x180004a3c  jz      loc_180004B29
0x180004a42  inc     dword ptr [rcx+34h]
0x180004a45  lea     r9, ?CompareByTimeNewestFirst@TracingFailureDetails@@SAHPEBX0@Z; CompareFunction
0x180004a4c  mov     edx, [rcx+28h]; NumOfElements
0x180004a4f  xor     ebp, ebp
0x180004a51  mov     rcx, [rcx+58h]; Base
0x180004a55  mov     r8d, 918h; SizeOfElements
0x180004a5b  xor     sil, sil
0x180004a5e  lea     r14d, [rbp+7]
0x180004a62  call    qsort
0x180004a67  mov     ebx, [rdi+28h]
0x180004a6a  dec     ebx
0x180004a6c  or      r12d, 0FFFFFFFFh
0x180004a70  mov     eax, ebx
0x180004a72  imul    rcx, rax, 918h
0x180004a79  add     rcx, [rdi+58h]; this
0x180004a7d  cmp     dword ptr [rcx+7E4h], 0
0x180004a84  jnz     short loc_180004A94
0x180004a86  call    ?Reset@TracingFailureDetails@@QEAAXXZ; TracingFailureDetails::Reset(void)
0x180004a8b  add     [rdi+28h], r12d
0x180004a8f  add     r14d, r12d
0x180004a92  jmp     short loc_180004A9E
0x180004a94  test    sil, sil
0x180004a97  jnz     short loc_180004A9E
0x180004a99  mov     sil, 1
0x180004a9c  mov     ebp, ebx
0x180004a9e  test    ebx, ebx
0x180004aa0  jz      short loc_180004AAA
0x180004aa2  add     ebx, r12d
0x180004aa5  test    r14d, r14d
0x180004aa8  jnz     short loc_180004A70
0x180004aaa  test    sil, sil
0x180004aad  jz      short loc_180004B29
0x180004aaf  xor     esi, esi
0x180004ab1  cmp     [rdi+28h], esi
0x180004ab4  jbe     short loc_180004B29
0x180004ab6  mov     r8, [rdi+58h]
0x180004aba  mov     eax, esi
0x180004abc  imul    r9, rax, 918h
0x180004ac3  add     r9, r8
0x180004ac6  cmp     dword ptr [r9+900h], 0
0x180004ace  jnz     short loc_180004B22
0x180004ad0  mov     eax, ebp
0x180004ad2  imul    rcx, rax, 918h
0x180004ad9  cmp     dword ptr [rcx+r8+7E4h], 0
0x180004ae2  jnz     short loc_180004AFB
0x180004ae4  add     ebp, r12d
0x180004ae7  mov     eax, ebp
0x180004ae9  imul    rdx, rax, 918h
0x180004af0  cmp     dword ptr [rdx+r8+7E4h], 0
0x180004af9  jz      short loc_180004AE4
0x180004afb  mov     eax, ebp
0x180004afd  mov     rcx, r9; void *
0x180004b00  imul    rbx, rax, 918h
0x180004b07  lea     rdx, [rbx+r8]; Src
0x180004b0b  mov     r8d, 918h; Size
0x180004b11  call    memcpy_0
0x180004b16  mov     rcx, [rdi+58h]
0x180004b1a  add     rcx, rbx; this
0x180004b1d  call    ?Reset@TracingFailureDetails@@QEAAXXZ; TracingFailureDetails::Reset(void)
0x180004b22  inc     esi
0x180004b24  cmp     esi, [rdi+28h]
0x180004b27  jb      short loc_180004AB6
0x180004b29  add     rsp, 28h
0x180004b2d  pop     r14
0x180004b2f  pop     r12
0x180004b31  pop     rdi
0x180004b32  pop     rsi
0x180004b33  pop     rbp
0x180004b34  pop     rbx
0x180004b35  retn
```
