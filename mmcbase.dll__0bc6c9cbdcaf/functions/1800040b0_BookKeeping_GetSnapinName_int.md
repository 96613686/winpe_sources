# BookKeeping::GetSnapinName(int)

- ea: `0x1800040b0`
- end: `0x18000412e`
- name: `?GetSnapinName@BookKeeping@@SAPEBGH@Z`
- size: `126`
- prototype: `const unsigned __int16 *__fastcall(int)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d720`
- `0x18000d930`
- `0x18000d9f0`
- `0x18000dc30`

## callees

- `0x1800040b0`
- `0x18001984c`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800040c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800040c9`

## pseudocode

```c
const unsigned __int16 *__fastcall BookKeeping::GetSnapinName(int a1)
{
  __int64 *v1; // rdi
  __int64 v2; // rbx
  __int64 *v3; // rcx

  v1 = 0;
  v2 = a1;
  if ( dword_18002F688
    || _InterlockedCompareExchange((volatile signed __int32 *)&dword_18002F688, GetCurrentThreadId(), 0) )
  {
    CSmallSpinLock::_LockSpin((CSmallSpinLock *)&dword_18002F688);
  }
  if ( (int)v2 >= 0 && (int)v2 < SHIDWORD(qword_18002F680) )
  {
    _mm_lfence();
    v1 = (__int64 *)*((_QWORD *)Src + v2);
  }
  v3 = &BookKeeping::s_unknownSnapin;
  _InterlockedExchange((volatile __int32 *)&dword_18002F688, 0);
  if ( v1 )
    v3 = v1;
  return (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64 *))*v3)(v3);
}

```

## disassembly

```asm
0x1800040b0  mov     [rsp+arg_8], rbx
0x1800040b5  push    rdi
0x1800040b6  sub     rsp, 20h
0x1800040ba  mov     eax, cs:dword_18002F688
0x1800040c0  xor     edi, edi
0x1800040c2  movsxd  rbx, ecx
0x1800040c5  test    eax, eax
0x1800040c7  jnz     short loc_1800040DD
0x1800040c9  call    cs:__imp_GetCurrentThreadId
0x1800040cf  mov     ecx, eax
0x1800040d1  xor     eax, eax
0x1800040d3  lock cmpxchg cs:dword_18002F688, ecx
0x1800040db  jz      short loc_1800040E9
0x1800040dd  lea     rcx, dword_18002F688; this
0x1800040e4  call    ?_LockSpin@CSmallSpinLock@@AEAAXXZ; CSmallSpinLock::_LockSpin(void)
0x1800040e9  test    ebx, ebx
0x1800040eb  js      short loc_180004103
0x1800040ed  cmp     ebx, dword ptr cs:qword_18002F680+4
0x1800040f3  jge     short loc_180004103
0x1800040f5  lfence
0x1800040f8  mov     rax, cs:Src
0x1800040ff  mov     rdi, [rax+rbx*8]
0x180004103  xor     eax, eax
0x180004105  lea     rcx, ?s_unknownSnapin@BookKeeping@@0VSnapinRecord@@A; SnapinRecord BookKeeping::s_unknownSnapin
0x18000410c  xchg    eax, cs:dword_18002F688
0x180004112  test    rdi, rdi
0x180004115  cmovnz  rcx, rdi
0x180004119  mov     rax, [rcx]
0x18000411c  mov     rax, [rax]
0x18000411f  mov     rbx, [rsp+28h+arg_8]
0x180004124  add     rsp, 20h
0x180004128  pop     rdi
0x180004129  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
