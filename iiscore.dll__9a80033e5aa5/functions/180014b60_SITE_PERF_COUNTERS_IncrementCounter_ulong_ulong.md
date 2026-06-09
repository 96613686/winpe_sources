# SITE_PERF_COUNTERS::IncrementCounter(ulong,ulong)

- ea: `0x180014b60`
- end: `0x180014bf6`
- name: `?IncrementCounter@SITE_PERF_COUNTERS@@UEAAXKK@Z`
- size: `150`
- prototype: `void __fastcall(SITE_PERF_COUNTERS *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014b60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014b82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014b82`

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
                                                      + (unsigned int)dword_18004ACE4[3 * a2]
                                                      + v3[1] * ((unsigned __int64)GetCurrentThreadId() % v3[2])));
      if ( a2 == 26 )
      {
        v5 = (unsigned int)qword_18004AE34;
      }
      else
      {
        if ( a2 != 29 )
          return;
        v5 = (unsigned int)qword_18004AE58;
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
0x180014b60  cmp     edx, 22h ; '"'
0x180014b63  jnb     short locret_180014BC9
0x180014b65  mov     [rsp+arg_8], rbx
0x180014b6a  push    rsi
0x180014b6b  sub     rsp, 20h
0x180014b6f  mov     [rsp+28h+arg_0], rdi
0x180014b74  mov     rsi, rcx
0x180014b77  mov     rdi, [rcx+8]
0x180014b7b  mov     ebx, edx
0x180014b7d  test    rdi, rdi
0x180014b80  jz      short loc_180014BBA
0x180014b82  call    cs:__imp_GetCurrentThreadId
0x180014b88  mov     eax, eax
0x180014b8a  xor     edx, edx
0x180014b8c  lea     rcx, [rbx+rbx*2]
0x180014b90  div     qword ptr [rdi+10h]
0x180014b94  lea     rax, dword_18004ACE4
0x180014b9b  mov     eax, [rax+rcx*4]
0x180014b9e  mov     r8d, edx
0x180014ba1  imul    r8, [rdi+8]
0x180014ba6  add     r8, rax
0x180014ba9  add     r8, [rdi]
0x180014bac  lock inc dword ptr [r8]
0x180014bb0  cmp     ebx, 1Ah
0x180014bb3  jz      short loc_180014BCA
0x180014bb5  cmp     ebx, 1Dh
0x180014bb8  jz      short loc_180014BEE
0x180014bba  mov     rdi, [rsp+28h+arg_0]
0x180014bbf  mov     rbx, [rsp+28h+arg_8]
0x180014bc4  add     rsp, 20h
0x180014bc8  pop     rsi
0x180014bc9  retn
0x180014bca  mov     ecx, dword ptr cs:qword_18004AE34
0x180014bd0  mov     rax, [rsi+8]
0x180014bd4  add     rcx, [rax]
0x180014bd7  test    rcx, rcx
0x180014bda  jz      short loc_180014BBA
0x180014bdc  cmp     dword ptr [rcx], 0
0x180014bdf  jnz     short loc_180014BBA
0x180014be1  mov     edx, 1
0x180014be6  xor     eax, eax
0x180014be8  lock cmpxchg [rcx], edx
0x180014bec  jmp     short loc_180014BBA
0x180014bee  mov     ecx, dword ptr cs:qword_18004AE58
0x180014bf4  jmp     short loc_180014BD0
```
