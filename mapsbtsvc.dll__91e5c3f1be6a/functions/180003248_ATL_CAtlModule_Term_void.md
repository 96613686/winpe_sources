# ATL::CAtlModule::Term(void)

- ea: `0x180003248`
- end: `0x1800032fa`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `178`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002a3c`

## callees

- `0x180001e54`
- `0x180003248`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800032e1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800032e1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003288`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003288`

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
0x180003248  push    rbx
0x18000324a  push    rsi
0x18000324b  push    rdi
0x18000324c  push    r14
0x18000324e  push    r15
0x180003250  sub     rsp, 20h
0x180003254  mov     rdi, rcx
0x180003257  lea     r14, [rcx+8]
0x18000325b  cmp     dword ptr [r14], 0
0x18000325f  jz      loc_1800032EE
0x180003265  cmp     qword ptr [rcx+10h], 0
0x18000326a  jz      short loc_1800032C8
0x18000326c  mov     rax, rcx
0x18000326f  neg     rax
0x180003272  sbb     rsi, rsi
0x180003275  and     rsi, r14
0x180003278  jnz     short loc_18000328F
0x18000327a  xor     r9d, r9d; lpArguments
0x18000327d  xor     r8d, r8d; nNumberOfArguments
0x180003280  lea     edx, [rsi+1]; dwExceptionFlags
0x180003283  mov     ecx, 0C0000005h; dwExceptionCode
0x180003288  call    cs:__imp_RaiseException
0x18000328e  int     3; Trap to Debugger
0x18000328f  mov     r15, [rsi+8]
0x180003293  test    r15, r15
0x180003296  jz      short loc_1800032B8
0x180003298  mov     rcx, [r15+8]
0x18000329c  mov     rax, [r15]
0x18000329f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032a4  mov     rbx, [r15+10h]
0x1800032a8  mov     rcx, r15; Block
0x1800032ab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800032b0  mov     r15, rbx
0x1800032b3  test    rbx, rbx
0x1800032b6  jnz     short loc_180003298
0x1800032b8  mov     qword ptr [rsi+8], 0
0x1800032c0  mov     qword ptr [rdi+10h], 0
0x1800032c8  mov     rcx, [rdi+40h]
0x1800032cc  test    rcx, rcx
0x1800032cf  jz      short loc_1800032DD
0x1800032d1  mov     rax, [rcx]
0x1800032d4  mov     rax, [rax+10h]
0x1800032d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032dd  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800032e1  call    cs:__imp_DeleteCriticalSection
0x1800032e7  mov     dword ptr [r14], 0
0x1800032ee  add     rsp, 20h
0x1800032f2  pop     r15
0x1800032f4  pop     r14
0x1800032f6  pop     rdi
0x1800032f7  pop     rsi
0x1800032f8  pop     rbx
0x1800032f9  retn
```
