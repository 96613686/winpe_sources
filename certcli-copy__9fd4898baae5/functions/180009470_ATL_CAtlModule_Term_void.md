# ATL::CAtlModule::Term(void)

- ea: `0x180009470`
- end: `0x180009523`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `179`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180004e74`
- `0x180005180`
- `0x1800051e8`
- `0x18000952c`

## callees

- `0x180009470`
- `0x18003f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800094d3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800094d3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000950a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000950a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800094b0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800094b0`

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
0x180009470  push    rbx
0x180009472  push    rsi
0x180009473  push    rdi
0x180009474  push    r14
0x180009476  push    r15
0x180009478  sub     rsp, 20h
0x18000947c  mov     rdi, rcx
0x18000947f  lea     r14, [rcx+8]
0x180009483  cmp     dword ptr [r14], 0
0x180009487  jz      loc_180009517
0x18000948d  cmp     qword ptr [rcx+10h], 0
0x180009492  jz      short loc_1800094F1
0x180009494  mov     rax, rcx
0x180009497  neg     rax
0x18000949a  sbb     rsi, rsi
0x18000949d  and     rsi, r14
0x1800094a0  jnz     short loc_1800094B7
0x1800094a2  xor     r9d, r9d; lpArguments
0x1800094a5  xor     r8d, r8d; nNumberOfArguments
0x1800094a8  lea     edx, [rsi+1]; dwExceptionFlags
0x1800094ab  mov     ecx, 0C0000005h; dwExceptionCode
0x1800094b0  call    cs:__imp_RaiseException
0x1800094b6  int     3; Trap to Debugger
0x1800094b7  mov     r15, [rsi+8]
0x1800094bb  test    r15, r15
0x1800094be  jz      short loc_1800094E1
0x1800094c0  mov     rcx, [r15+8]
0x1800094c4  mov     rax, [r15]
0x1800094c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094cc  mov     rbx, [r15+10h]
0x1800094d0  mov     rcx, r15
0x1800094d3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800094d9  mov     r15, rbx
0x1800094dc  test    rbx, rbx
0x1800094df  jnz     short loc_1800094C0
0x1800094e1  mov     qword ptr [rsi+8], 0
0x1800094e9  mov     qword ptr [rdi+10h], 0
0x1800094f1  mov     rcx, [rdi+40h]
0x1800094f5  test    rcx, rcx
0x1800094f8  jz      short loc_180009506
0x1800094fa  mov     rax, [rcx]
0x1800094fd  mov     rax, [rax+10h]
0x180009501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009506  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000950a  call    cs:__imp_DeleteCriticalSection
0x180009510  mov     dword ptr [r14], 0
0x180009517  add     rsp, 20h
0x18000951b  pop     r15
0x18000951d  pop     r14
0x18000951f  pop     rdi
0x180009520  pop     rsi
0x180009521  pop     rbx
0x180009522  retn
```
