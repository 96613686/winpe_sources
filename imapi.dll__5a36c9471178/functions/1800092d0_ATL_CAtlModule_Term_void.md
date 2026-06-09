# ATL::CAtlModule::Term(void)

- ea: `0x1800092d0`
- end: `0x180009374`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `164`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180008030`
- `0x180009bd0`
- `0x180018930`

## callees

- `0x180001144`
- `0x1800046fc`
- `0x1800092d0`
- `0x180019010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180009350`
- `KERNEL32!DeleteCriticalSection` at `0x180009350`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this, unsigned int a2)
{
  unsigned __int64 v2; // r14
  __int64 v4; // rsi
  _QWORD *v5; // r15
  _QWORD *v6; // rbx
  __int64 v7; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v4 = v2 & -(__int64)(this != 0);
      if ( !v4 )
      {
        ATL::_AtlRaiseException(0xC0000005, a2);
        JUMPOUT(0x180009373LL);
      }
      v5 = *(_QWORD **)((v2 & -(__int64)(this != 0)) + 8);
      if ( v5 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v5)(v5[1]);
          v6 = (_QWORD *)v5[2];
          operator delete(v5);
          v5 = v6;
        }
        while ( v6 );
      }
      *(_QWORD *)(v4 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v7 = *((_QWORD *)this + 8);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x1800092d0  push    rbx
0x1800092d2  push    rsi
0x1800092d3  push    rdi
0x1800092d4  push    r14
0x1800092d6  push    r15
0x1800092d8  sub     rsp, 20h
0x1800092dc  lea     r14, [rcx+8]
0x1800092e0  mov     rdi, rcx
0x1800092e3  cmp     dword ptr [r14], 0
0x1800092e7  jz      short loc_18000935D
0x1800092e9  cmp     qword ptr [rcx+10h], 0
0x1800092ee  jz      short loc_180009337
0x1800092f0  mov     rax, rcx
0x1800092f3  neg     rax
0x1800092f6  sbb     rsi, rsi
0x1800092f9  and     rsi, r14
0x1800092fc  jz      short loc_180009369
0x1800092fe  mov     r15, [rsi+8]
0x180009302  test    r15, r15
0x180009305  jz      short loc_180009327
0x180009307  mov     rcx, [r15+8]
0x18000930b  mov     rax, [r15]
0x18000930e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009313  mov     rbx, [r15+10h]
0x180009317  mov     rcx, r15; Block
0x18000931a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000931f  mov     r15, rbx
0x180009322  test    rbx, rbx
0x180009325  jnz     short loc_180009307
0x180009327  mov     qword ptr [rsi+8], 0
0x18000932f  mov     qword ptr [rdi+10h], 0
0x180009337  mov     rcx, [rdi+40h]
0x18000933b  test    rcx, rcx
0x18000933e  jz      short loc_18000934C
0x180009340  mov     rax, [rcx]
0x180009343  mov     rax, [rax+10h]
0x180009347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000934c  lea     rcx, [rdi+18h]; lpCriticalSection
0x180009350  call    cs:__imp_DeleteCriticalSection
0x180009356  mov     dword ptr [r14], 0
0x18000935d  add     rsp, 20h
0x180009361  pop     r15
0x180009363  pop     r14
0x180009365  pop     rdi
0x180009366  pop     rsi
0x180009367  pop     rbx
0x180009368  retn
0x180009369  mov     ecx, 0C0000005h; unsigned int
0x18000936e  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
