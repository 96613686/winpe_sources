# ATL::CAtlModule::Term(void)

- ea: `0x180004778`
- end: `0x18000482b`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `179`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180004090`

## callees

- `0x180004778`
- `0x18002f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800047db`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800047db`
- `KERNEL32!DeleteCriticalSection` at `0x180004812`
- `KERNEL32!DeleteCriticalSection` at `0x180004812`
- `KERNEL32!RaiseException` at `0x1800047b8`
- `KERNEL32!RaiseException` at `0x1800047b8`

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
0x180004778  push    rbx
0x18000477a  push    rsi
0x18000477b  push    rdi
0x18000477c  push    r14
0x18000477e  push    r15
0x180004780  sub     rsp, 20h
0x180004784  mov     rdi, rcx
0x180004787  lea     r14, [rcx+8]
0x18000478b  cmp     dword ptr [r14], 0
0x18000478f  jz      loc_18000481F
0x180004795  cmp     qword ptr [rcx+10h], 0
0x18000479a  jz      short loc_1800047F9
0x18000479c  mov     rax, rcx
0x18000479f  neg     rax
0x1800047a2  sbb     rsi, rsi
0x1800047a5  and     rsi, r14
0x1800047a8  jnz     short loc_1800047BF
0x1800047aa  xor     r9d, r9d; lpArguments
0x1800047ad  xor     r8d, r8d; nNumberOfArguments
0x1800047b0  lea     edx, [rsi+1]; dwExceptionFlags
0x1800047b3  mov     ecx, 0C0000005h; dwExceptionCode
0x1800047b8  call    cs:__imp_RaiseException
0x1800047be  int     3; Trap to Debugger
0x1800047bf  mov     r15, [rsi+8]
0x1800047c3  test    r15, r15
0x1800047c6  jz      short loc_1800047E9
0x1800047c8  mov     rcx, [r15+8]
0x1800047cc  mov     rax, [r15]
0x1800047cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047d4  mov     rbx, [r15+10h]
0x1800047d8  mov     rcx, r15
0x1800047db  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800047e1  mov     r15, rbx
0x1800047e4  test    rbx, rbx
0x1800047e7  jnz     short loc_1800047C8
0x1800047e9  mov     qword ptr [rsi+8], 0
0x1800047f1  mov     qword ptr [rdi+10h], 0
0x1800047f9  mov     rcx, [rdi+40h]
0x1800047fd  test    rcx, rcx
0x180004800  jz      short loc_18000480E
0x180004802  mov     rax, [rcx]
0x180004805  mov     rax, [rax+10h]
0x180004809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000480e  lea     rcx, [rdi+18h]; lpCriticalSection
0x180004812  call    cs:__imp_DeleteCriticalSection
0x180004818  mov     dword ptr [r14], 0
0x18000481f  add     rsp, 20h
0x180004823  pop     r15
0x180004825  pop     r14
0x180004827  pop     rdi
0x180004828  pop     rsi
0x180004829  pop     rbx
0x18000482a  retn
```
