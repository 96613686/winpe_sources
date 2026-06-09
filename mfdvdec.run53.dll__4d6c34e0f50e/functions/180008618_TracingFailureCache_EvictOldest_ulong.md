# TracingFailureCache::EvictOldest(ulong)

- ea: `0x180008618`
- end: `0x180008726`
- name: `?EvictOldest@TracingFailureCache@@IEAAXK@Z`
- size: `270`
- prototype: `void __fastcall(TracingFailureCache *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008ce8`

## callees

- `0x180001e8c`
- `0x180008618`
- `0x180008ca0`
- `0x18001d369`

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
0x180008618  push    rbx
0x18000861a  push    rbp
0x18000861b  push    rsi
0x18000861c  push    rdi
0x18000861d  push    r12
0x18000861f  push    r14
0x180008621  sub     rsp, 28h
0x180008625  cmp     dword ptr [rcx+28h], 0
0x180008629  mov     rdi, rcx
0x18000862c  jz      loc_180008719
0x180008632  inc     dword ptr [rcx+34h]
0x180008635  lea     r9, ?CompareByTimeNewestFirst@TracingFailureDetails@@SAHPEBX0@Z; CompareFunction
0x18000863c  mov     edx, [rcx+28h]; NumOfElements
0x18000863f  xor     ebp, ebp
0x180008641  mov     rcx, [rcx+58h]; Base
0x180008645  mov     r8d, 918h; SizeOfElements
0x18000864b  xor     sil, sil
0x18000864e  lea     r14d, [rbp+7]
0x180008652  call    qsort
0x180008657  mov     ebx, [rdi+28h]
0x18000865a  dec     ebx
0x18000865c  or      r12d, 0FFFFFFFFh
0x180008660  mov     eax, ebx
0x180008662  imul    rcx, rax, 918h
0x180008669  add     rcx, [rdi+58h]; this
0x18000866d  cmp     dword ptr [rcx+7E4h], 0
0x180008674  jnz     short loc_180008684
0x180008676  call    ?Reset@TracingFailureDetails@@QEAAXXZ; TracingFailureDetails::Reset(void)
0x18000867b  add     [rdi+28h], r12d
0x18000867f  add     r14d, r12d
0x180008682  jmp     short loc_18000868E
0x180008684  test    sil, sil
0x180008687  jnz     short loc_18000868E
0x180008689  mov     sil, 1
0x18000868c  mov     ebp, ebx
0x18000868e  test    ebx, ebx
0x180008690  jz      short loc_18000869A
0x180008692  add     ebx, r12d
0x180008695  test    r14d, r14d
0x180008698  jnz     short loc_180008660
0x18000869a  test    sil, sil
0x18000869d  jz      short loc_180008719
0x18000869f  xor     esi, esi
0x1800086a1  cmp     [rdi+28h], esi
0x1800086a4  jbe     short loc_180008719
0x1800086a6  mov     r8, [rdi+58h]
0x1800086aa  mov     eax, esi
0x1800086ac  imul    r9, rax, 918h
0x1800086b3  add     r9, r8
0x1800086b6  cmp     dword ptr [r9+900h], 0
0x1800086be  jnz     short loc_180008712
0x1800086c0  mov     eax, ebp
0x1800086c2  imul    rcx, rax, 918h
0x1800086c9  cmp     dword ptr [rcx+r8+7E4h], 0
0x1800086d2  jnz     short loc_1800086EB
0x1800086d4  add     ebp, r12d
0x1800086d7  mov     eax, ebp
0x1800086d9  imul    rdx, rax, 918h
0x1800086e0  cmp     dword ptr [rdx+r8+7E4h], 0
0x1800086e9  jz      short loc_1800086D4
0x1800086eb  mov     eax, ebp
0x1800086ed  mov     rcx, r9; void *
0x1800086f0  imul    rbx, rax, 918h
0x1800086f7  lea     rdx, [rbx+r8]; Src
0x1800086fb  mov     r8d, 918h; Size
0x180008701  call    memcpy_0
0x180008706  mov     rcx, [rdi+58h]
0x18000870a  add     rcx, rbx; this
0x18000870d  call    ?Reset@TracingFailureDetails@@QEAAXXZ; TracingFailureDetails::Reset(void)
0x180008712  inc     esi
0x180008714  cmp     esi, [rdi+28h]
0x180008717  jb      short loc_1800086A6
0x180008719  add     rsp, 28h
0x18000871d  pop     r14
0x18000871f  pop     r12
0x180008721  pop     rdi
0x180008722  pop     rsi
0x180008723  pop     rbp
0x180008724  pop     rbx
0x180008725  retn
```
