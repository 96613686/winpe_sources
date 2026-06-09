# ATL::CAtlModule::Term(void)

- ea: `0x18001b74c`
- end: `0x18001b803`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180017190`
- `0x18001bf84`
- `0x180055ca0`

## callees

- `0x180001ea4`
- `0x18001b74c`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b7ea`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b7ea`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b78c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b78c`

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
0x18001b74c  push    rbx
0x18001b74e  push    rsi
0x18001b74f  push    rdi
0x18001b750  push    r14
0x18001b752  push    r15
0x18001b754  sub     rsp, 20h
0x18001b758  mov     rdi, rcx
0x18001b75b  lea     r14, [rcx+8]
0x18001b75f  cmp     dword ptr [r14], 0
0x18001b763  jz      loc_18001B7F7
0x18001b769  cmp     qword ptr [rcx+10h], 0
0x18001b76e  jz      short loc_18001B7D1
0x18001b770  mov     rax, rcx
0x18001b773  neg     rax
0x18001b776  sbb     rsi, rsi
0x18001b779  and     rsi, r14
0x18001b77c  jnz     short loc_18001B793
0x18001b77e  xor     r9d, r9d; lpArguments
0x18001b781  xor     r8d, r8d; nNumberOfArguments
0x18001b784  lea     edx, [rsi+1]; dwExceptionFlags
0x18001b787  mov     ecx, 0C0000005h; dwExceptionCode
0x18001b78c  call    cs:__imp_RaiseException
0x18001b792  int     3; Trap to Debugger
0x18001b793  mov     r15, [rsi+8]
0x18001b797  test    r15, r15
0x18001b79a  jz      short loc_18001B7C1
0x18001b79c  mov     rcx, [r15+8]
0x18001b7a0  mov     rax, [r15]
0x18001b7a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7a8  mov     rbx, [r15+10h]
0x18001b7ac  mov     edx, 18h
0x18001b7b1  mov     rcx, r15; Block
0x18001b7b4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b7b9  mov     r15, rbx
0x18001b7bc  test    rbx, rbx
0x18001b7bf  jnz     short loc_18001B79C
0x18001b7c1  mov     qword ptr [rsi+8], 0
0x18001b7c9  mov     qword ptr [rdi+10h], 0
0x18001b7d1  mov     rcx, [rdi+40h]
0x18001b7d5  test    rcx, rcx
0x18001b7d8  jz      short loc_18001B7E6
0x18001b7da  mov     rax, [rcx]
0x18001b7dd  mov     rax, [rax+10h]
0x18001b7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7e6  lea     rcx, [rdi+18h]; lpCriticalSection
0x18001b7ea  call    cs:__imp_DeleteCriticalSection
0x18001b7f0  mov     dword ptr [r14], 0
0x18001b7f7  add     rsp, 20h
0x18001b7fb  pop     r15
0x18001b7fd  pop     r14
0x18001b7ff  pop     rdi
0x18001b800  pop     rsi
0x18001b801  pop     rbx
0x18001b802  retn
```
