# SITE_PERF_COUNTERS::IncrementCounter(ulong,ulong)

- ea: `0x180015c90`
- end: `0x180015d2d`
- name: `?IncrementCounter@SITE_PERF_COUNTERS@@UEAAXKK@Z`
- size: `157`
- prototype: `void __fastcall(SITE_PERF_COUNTERS *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015c90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015cb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015cb2`

## pseudocode

```c
void __fastcall SITE_PERF_COUNTERS::IncrementCounter(SITE_PERF_COUNTERS *this, unsigned int a2)
{
  _QWORD *v3; // rdi
  __int64 v5; // rcx
  volatile signed __int32 *v6; // rcx

  if ( a2 < 0x22 )
  {
    v3 = (_QWORD *)*((_QWORD *)this + 1);
    if ( v3 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(*v3
                                                      + (unsigned int)dword_18004DCE4[3 * a2]
                                                      + v3[1] * ((unsigned __int64)GetCurrentThreadId() % v3[2])));
      if ( a2 == 26 )
      {
        v5 = (unsigned int)qword_18004DE34;
      }
      else
      {
        if ( a2 != 29 )
          return;
        v5 = (unsigned int)qword_18004DE58;
      }
      v6 = (volatile signed __int32 *)(**((_QWORD **)this + 1) + v5);
      if ( v6 )
      {
        if ( !*v6 )
          _InterlockedCompareExchange(v6, 1, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x180015c90  cmp     edx, 22h ; '"'
0x180015c93  jnb     short locret_180015CFF
0x180015c95  mov     [rsp+arg_8], rbx
0x180015c9a  push    rsi
0x180015c9b  sub     rsp, 20h
0x180015c9f  mov     [rsp+28h+arg_0], rdi
0x180015ca4  mov     rsi, rcx
0x180015ca7  mov     rdi, [rcx+8]
0x180015cab  mov     ebx, edx
0x180015cad  test    rdi, rdi
0x180015cb0  jz      short loc_180015CF0
0x180015cb2  call    cs:__imp_GetCurrentThreadId
0x180015cb9  nop     dword ptr [rax+rax+00h]
0x180015cbe  mov     eax, eax
0x180015cc0  xor     edx, edx
0x180015cc2  lea     rcx, [rbx+rbx*2]
0x180015cc6  div     qword ptr [rdi+10h]
0x180015cca  lea     rax, dword_18004DCE4
0x180015cd1  mov     eax, [rax+rcx*4]
0x180015cd4  mov     r8d, edx
0x180015cd7  imul    r8, [rdi+8]
0x180015cdc  add     r8, rax
0x180015cdf  add     r8, [rdi]
0x180015ce2  lock inc dword ptr [r8]
0x180015ce6  cmp     ebx, 1Ah
0x180015ce9  jz      short loc_180015D01
0x180015ceb  cmp     ebx, 1Dh
0x180015cee  jz      short loc_180015D25
0x180015cf0  mov     rdi, [rsp+28h+arg_0]
0x180015cf5  mov     rbx, [rsp+28h+arg_8]
0x180015cfa  add     rsp, 20h
0x180015cfe  pop     rsi
0x180015cff  retn
0x180015d01  mov     ecx, dword ptr cs:qword_18004DE34
0x180015d07  mov     rax, [rsi+8]
0x180015d0b  add     rcx, [rax]
0x180015d0e  test    rcx, rcx
0x180015d11  jz      short loc_180015CF0
0x180015d13  cmp     dword ptr [rcx], 0
0x180015d16  jnz     short loc_180015CF0
0x180015d18  mov     edx, 1
0x180015d1d  xor     eax, eax
0x180015d1f  lock cmpxchg [rcx], edx
0x180015d23  jmp     short loc_180015CF0
0x180015d25  mov     ecx, dword ptr cs:qword_18004DE58
0x180015d2b  jmp     short loc_180015D07
```
