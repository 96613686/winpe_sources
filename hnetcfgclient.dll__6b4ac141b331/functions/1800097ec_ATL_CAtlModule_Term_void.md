# ATL::CAtlModule::Term(void)

- ea: `0x1800097ec`
- end: `0x18000989f`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `179`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006980`
- `0x18000a0b4`
- `0x18002e180`

## callees

- `0x1800097ec`
- `0x18002f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000984f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000984f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009886`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009886`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000982c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000982c`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  unsigned __int64 v2; // r14
  __int64 v3; // rsi
  _QWORD *v4; // r15
  _QWORD *v5; // rbx
  __int64 v6; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v3 = v2 & -(__int64)(this != 0);
      if ( !v3 )
      {
        RaiseException(0xC0000005, 1u, 0, 0);
        __debugbreak();
      }
      v4 = *(_QWORD **)((v2 & -(__int64)(this != 0)) + 8);
      if ( v4 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v4)(v4[1]);
          v5 = (_QWORD *)v4[2];
          operator delete(v4);
          v4 = v5;
        }
        while ( v5 );
      }
      *(_QWORD *)(v3 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v6 = *((_QWORD *)this + 8);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x1800097ec  push    rbx
0x1800097ee  push    rsi
0x1800097ef  push    rdi
0x1800097f0  push    r14
0x1800097f2  push    r15
0x1800097f4  sub     rsp, 20h
0x1800097f8  mov     rdi, rcx
0x1800097fb  lea     r14, [rcx+8]
0x1800097ff  cmp     dword ptr [r14], 0
0x180009803  jz      loc_180009893
0x180009809  cmp     qword ptr [rcx+10h], 0
0x18000980e  jz      short loc_18000986D
0x180009810  mov     rax, rcx
0x180009813  neg     rax
0x180009816  sbb     rsi, rsi
0x180009819  and     rsi, r14
0x18000981c  jnz     short loc_180009833
0x18000981e  xor     r9d, r9d; lpArguments
0x180009821  xor     r8d, r8d; nNumberOfArguments
0x180009824  lea     edx, [rsi+1]; dwExceptionFlags
0x180009827  mov     ecx, 0C0000005h; dwExceptionCode
0x18000982c  call    cs:__imp_RaiseException
0x180009832  int     3; Trap to Debugger
0x180009833  mov     r15, [rsi+8]
0x180009837  test    r15, r15
0x18000983a  jz      short loc_18000985D
0x18000983c  mov     rcx, [r15+8]
0x180009840  mov     rax, [r15]
0x180009843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009848  mov     rbx, [r15+10h]
0x18000984c  mov     rcx, r15
0x18000984f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009855  mov     r15, rbx
0x180009858  test    rbx, rbx
0x18000985b  jnz     short loc_18000983C
0x18000985d  mov     qword ptr [rsi+8], 0
0x180009865  mov     qword ptr [rdi+10h], 0
0x18000986d  mov     rcx, [rdi+40h]
0x180009871  test    rcx, rcx
0x180009874  jz      short loc_180009882
0x180009876  mov     rax, [rcx]
0x180009879  mov     rax, [rax+10h]
0x18000987d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009882  lea     rcx, [rdi+18h]; lpCriticalSection
0x180009886  call    cs:__imp_DeleteCriticalSection
0x18000988c  mov     dword ptr [r14], 0
0x180009893  add     rsp, 20h
0x180009897  pop     r15
0x180009899  pop     r14
0x18000989b  pop     rdi
0x18000989c  pop     rsi
0x18000989d  pop     rbx
0x18000989e  retn
```
