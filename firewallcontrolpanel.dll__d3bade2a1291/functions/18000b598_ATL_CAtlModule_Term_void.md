# ATL::CAtlModule::Term(void)

- ea: `0x18000b598`
- end: `0x18000b64a`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `178`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800099e0`

## callees

- `0x180009b5c`
- `0x18000b598`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b631`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b631`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b5d8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b5d8`

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
0x18000b598  push    rbx
0x18000b59a  push    rsi
0x18000b59b  push    rdi
0x18000b59c  push    r14
0x18000b59e  push    r15
0x18000b5a0  sub     rsp, 20h
0x18000b5a4  mov     rdi, rcx
0x18000b5a7  lea     r14, [rcx+8]
0x18000b5ab  cmp     dword ptr [r14], 0
0x18000b5af  jz      loc_18000B63E
0x18000b5b5  cmp     qword ptr [rcx+10h], 0
0x18000b5ba  jz      short loc_18000B618
0x18000b5bc  mov     rax, rcx
0x18000b5bf  neg     rax
0x18000b5c2  sbb     rsi, rsi
0x18000b5c5  and     rsi, r14
0x18000b5c8  jnz     short loc_18000B5DF
0x18000b5ca  xor     r9d, r9d; lpArguments
0x18000b5cd  xor     r8d, r8d; nNumberOfArguments
0x18000b5d0  lea     edx, [rsi+1]; dwExceptionFlags
0x18000b5d3  mov     ecx, 0C0000005h; dwExceptionCode
0x18000b5d8  call    cs:__imp_RaiseException
0x18000b5de  int     3; Trap to Debugger
0x18000b5df  mov     r15, [rsi+8]
0x18000b5e3  test    r15, r15
0x18000b5e6  jz      short loc_18000B608
0x18000b5e8  mov     rcx, [r15+8]
0x18000b5ec  mov     rax, [r15]
0x18000b5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5f4  mov     rbx, [r15+10h]
0x18000b5f8  mov     rcx, r15; lpMem
0x18000b5fb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b600  mov     r15, rbx
0x18000b603  test    rbx, rbx
0x18000b606  jnz     short loc_18000B5E8
0x18000b608  mov     qword ptr [rsi+8], 0
0x18000b610  mov     qword ptr [rdi+10h], 0
0x18000b618  mov     rcx, [rdi+40h]
0x18000b61c  test    rcx, rcx
0x18000b61f  jz      short loc_18000B62D
0x18000b621  mov     rax, [rcx]
0x18000b624  mov     rax, [rax+10h]
0x18000b628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b62d  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000b631  call    cs:__imp_DeleteCriticalSection
0x18000b637  mov     dword ptr [r14], 0
0x18000b63e  add     rsp, 20h
0x18000b642  pop     r15
0x18000b644  pop     r14
0x18000b646  pop     rdi
0x18000b647  pop     rsi
0x18000b648  pop     rbx
0x18000b649  retn
```
