# SITE_PERF_COUNTERS::DecrementCounter(ulong,unsigned __int64 *,ulong)

- ea: `0x180015960`
- end: `0x1800159d8`
- name: `?DecrementCounter@SITE_PERF_COUNTERS@@QEAAXKPEA_KK@Z`
- size: `120`
- prototype: `void __fastcall(SITE_PERF_COUNTERS *__hidden this, unsigned int, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000df90`

## callees

- `0x180015960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800159bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800159bb`

## pseudocode

```c
void __fastcall SITE_PERF_COUNTERS::DecrementCounter(SITE_PERF_COUNTERS *this, unsigned int a2, unsigned __int64 *a3)
{
  _QWORD *v3; // rdi
  unsigned __int64 *v4; // rbx
  __int64 v5; // rsi

  v3 = (_QWORD *)*((_QWORD *)this + 1);
  v4 = a3;
  v5 = a2;
  if ( v3 )
  {
    if ( a3 )
    {
      if ( *a3 == 0xFFFFFFFF )
      {
        LODWORD(a3) = (unsigned __int64)GetCurrentThreadId() % v3[2];
        *v4 = (unsigned int)a3;
      }
      else
      {
        LODWORD(a3) = *(_DWORD *)a3;
      }
    }
    _InterlockedDecrement((volatile signed __int32 *)(*v3
                                                    + v3[1] * (unsigned int)a3
                                                    + (unsigned int)dword_18004ACE4[3 * v5]));
  }
}

```

## disassembly

```asm
0x180015960  mov     [rsp+arg_0], rbx
0x180015965  mov     [rsp+arg_8], rsi
0x18001596a  push    rdi
0x18001596b  sub     rsp, 20h
0x18001596f  mov     rdi, [rcx+8]
0x180015973  mov     rbx, r8
0x180015976  mov     esi, edx
0x180015978  test    rdi, rdi
0x18001597b  jz      short loc_1800159A1
0x18001597d  test    rbx, rbx
0x180015980  jnz     short loc_1800159B1
0x180015982  lea     rax, dword_18004ACE4
0x180015989  lea     rcx, [rsi+rsi*2]
0x18001598d  mov     edx, [rax+rcx*4]
0x180015990  mov     eax, r8d
0x180015993  imul    rax, [rdi+8]
0x180015998  add     rdx, rax
0x18001599b  add     rdx, [rdi]
0x18001599e  lock dec dword ptr [rdx]
0x1800159a1  mov     rbx, [rsp+28h+arg_0]
0x1800159a6  mov     rsi, [rsp+28h+arg_8]
0x1800159ab  add     rsp, 20h
0x1800159af  pop     rdi
0x1800159b0  retn
0x1800159b1  mov     eax, 0FFFFFFFFh
0x1800159b6  cmp     [r8], rax
0x1800159b9  jnz     short loc_1800159D3
0x1800159bb  call    cs:__imp_GetCurrentThreadId
0x1800159c1  mov     eax, eax
0x1800159c3  xor     edx, edx
0x1800159c5  div     qword ptr [rdi+10h]
0x1800159c9  mov     eax, edx
0x1800159cb  mov     r8, rdx
0x1800159ce  mov     [rbx], rax
0x1800159d1  jmp     short loc_180015982
0x1800159d3  mov     r8d, [r8]
0x1800159d6  jmp     short loc_180015982
```
