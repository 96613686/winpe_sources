# TracingFailureCache::EvictOldest(ulong)

- ea: `0x18006df50`
- end: `0x18006e05e`
- name: `?EvictOldest@TracingFailureCache@@IEAAXK@Z`
- size: `270`
- prototype: `void __fastcall(TracingFailureCache *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800224f0`

## callees

- `0x180024bac`
- `0x18003a794`
- `0x18006df50`
- `0x18006e358`

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
0x18006df50  push    rbx
0x18006df52  push    rbp
0x18006df53  push    rsi
0x18006df54  push    rdi
0x18006df55  push    r12
0x18006df57  push    r14
0x18006df59  sub     rsp, 28h
0x18006df5d  cmp     dword ptr [rcx+28h], 0
0x18006df61  mov     rdi, rcx
0x18006df64  jz      loc_18006E051
0x18006df6a  inc     dword ptr [rcx+34h]
0x18006df6d  lea     r9, ?CompareByTimeNewestFirst@TracingFailureDetails@@SAHPEBX0@Z; CompareFunction
0x18006df74  mov     edx, [rcx+28h]; NumOfElements
0x18006df77  xor     ebp, ebp
0x18006df79  mov     rcx, [rcx+58h]; Base
0x18006df7d  mov     r8d, 918h; SizeOfElements
0x18006df83  xor     sil, sil
0x18006df86  lea     r14d, [rbp+7]
0x18006df8a  call    qsort
0x18006df8f  mov     ebx, [rdi+28h]
0x18006df92  dec     ebx
0x18006df94  or      r12d, 0FFFFFFFFh
0x18006df98  mov     eax, ebx
0x18006df9a  imul    rcx, rax, 918h
0x18006dfa1  add     rcx, [rdi+58h]; this
0x18006dfa5  cmp     dword ptr [rcx+7E4h], 0
0x18006dfac  jnz     short loc_18006DFBC
0x18006dfae  call    ?Reset@TracingFailureDetails@@QEAAXXZ; TracingFailureDetails::Reset(void)
0x18006dfb3  add     [rdi+28h], r12d
0x18006dfb7  add     r14d, r12d
0x18006dfba  jmp     short loc_18006DFC6
0x18006dfbc  test    sil, sil
0x18006dfbf  jnz     short loc_18006DFC6
0x18006dfc1  mov     sil, 1
0x18006dfc4  mov     ebp, ebx
0x18006dfc6  test    ebx, ebx
0x18006dfc8  jz      short loc_18006DFD2
0x18006dfca  add     ebx, r12d
0x18006dfcd  test    r14d, r14d
0x18006dfd0  jnz     short loc_18006DF98
0x18006dfd2  test    sil, sil
0x18006dfd5  jz      short loc_18006E051
0x18006dfd7  xor     esi, esi
0x18006dfd9  cmp     [rdi+28h], esi
0x18006dfdc  jbe     short loc_18006E051
0x18006dfde  mov     r8, [rdi+58h]
0x18006dfe2  mov     eax, esi
0x18006dfe4  imul    r9, rax, 918h
0x18006dfeb  add     r9, r8
0x18006dfee  cmp     dword ptr [r9+900h], 0
0x18006dff6  jnz     short loc_18006E04A
0x18006dff8  mov     eax, ebp
0x18006dffa  imul    rcx, rax, 918h
0x18006e001  cmp     dword ptr [rcx+r8+7E4h], 0
0x18006e00a  jnz     short loc_18006E023
0x18006e00c  add     ebp, r12d
0x18006e00f  mov     eax, ebp
0x18006e011  imul    rdx, rax, 918h
0x18006e018  cmp     dword ptr [rdx+r8+7E4h], 0
0x18006e021  jz      short loc_18006E00C
0x18006e023  mov     eax, ebp
0x18006e025  mov     rcx, r9; void *
0x18006e028  imul    rbx, rax, 918h
0x18006e02f  lea     rdx, [rbx+r8]; Src
0x18006e033  mov     r8d, 918h; Size
0x18006e039  call    memcpy_0
0x18006e03e  mov     rcx, [rdi+58h]
0x18006e042  add     rcx, rbx; this
0x18006e045  call    ?Reset@TracingFailureDetails@@QEAAXXZ; TracingFailureDetails::Reset(void)
0x18006e04a  inc     esi
0x18006e04c  cmp     esi, [rdi+28h]
0x18006e04f  jb      short loc_18006DFDE
0x18006e051  add     rsp, 28h
0x18006e055  pop     r14
0x18006e057  pop     r12
0x18006e059  pop     rdi
0x18006e05a  pop     rsi
0x18006e05b  pop     rbp
0x18006e05c  pop     rbx
0x18006e05d  retn
```
