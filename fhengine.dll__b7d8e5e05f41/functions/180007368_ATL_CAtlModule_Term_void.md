# ATL::CAtlModule::Term(void)

- ea: `0x180007368`
- end: `0x18000741b`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `179`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000696c`

## callees

- `0x180007368`
- `0x180034010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800073cb`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800073cb`
- `KERNEL32!RaiseException` at `0x1800073a8`
- `KERNEL32!RaiseException` at `0x1800073a8`
- `KERNEL32!DeleteCriticalSection` at `0x180007402`
- `KERNEL32!DeleteCriticalSection` at `0x180007402`

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
0x180007368  push    rbx
0x18000736a  push    rsi
0x18000736b  push    rdi
0x18000736c  push    r14
0x18000736e  push    r15
0x180007370  sub     rsp, 20h
0x180007374  mov     rdi, rcx
0x180007377  lea     r14, [rcx+8]
0x18000737b  cmp     dword ptr [r14], 0
0x18000737f  jz      loc_18000740F
0x180007385  cmp     qword ptr [rcx+10h], 0
0x18000738a  jz      short loc_1800073E9
0x18000738c  mov     rax, rcx
0x18000738f  neg     rax
0x180007392  sbb     rsi, rsi
0x180007395  and     rsi, r14
0x180007398  jnz     short loc_1800073AF
0x18000739a  xor     r9d, r9d; lpArguments
0x18000739d  xor     r8d, r8d; nNumberOfArguments
0x1800073a0  lea     edx, [rsi+1]; dwExceptionFlags
0x1800073a3  mov     ecx, 0C0000005h; dwExceptionCode
0x1800073a8  call    cs:__imp_RaiseException
0x1800073ae  int     3; Trap to Debugger
0x1800073af  mov     r15, [rsi+8]
0x1800073b3  test    r15, r15
0x1800073b6  jz      short loc_1800073D9
0x1800073b8  mov     rcx, [r15+8]
0x1800073bc  mov     rax, [r15]
0x1800073bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073c4  mov     rbx, [r15+10h]
0x1800073c8  mov     rcx, r15
0x1800073cb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800073d1  mov     r15, rbx
0x1800073d4  test    rbx, rbx
0x1800073d7  jnz     short loc_1800073B8
0x1800073d9  mov     qword ptr [rsi+8], 0
0x1800073e1  mov     qword ptr [rdi+10h], 0
0x1800073e9  mov     rcx, [rdi+40h]
0x1800073ed  test    rcx, rcx
0x1800073f0  jz      short loc_1800073FE
0x1800073f2  mov     rax, [rcx]
0x1800073f5  mov     rax, [rax+10h]
0x1800073f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073fe  lea     rcx, [rdi+18h]; lpCriticalSection
0x180007402  call    cs:__imp_DeleteCriticalSection
0x180007408  mov     dword ptr [r14], 0
0x18000740f  add     rsp, 20h
0x180007413  pop     r15
0x180007415  pop     r14
0x180007417  pop     rdi
0x180007418  pop     rsi
0x180007419  pop     rbx
0x18000741a  retn
```
