# ATL::CAtlModule::Term(void)

- ea: `0x18000dedc`
- end: `0x18000df8e`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `178`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000bdc0`
- `0x180018f80`

## callees

- `0x18000bd88`
- `0x18000dedc`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000df75`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000df75`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000df1c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000df1c`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  unsigned __int64 v1; // r14
  __int64 v3; // rsi
  _QWORD *v4; // r15
  _QWORD *v5; // rbx
  __int64 v6; // rcx

  v1 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v3 = v1 & -(__int64)(this != 0);
      if ( !v3 )
      {
        RaiseException(0xC0000005, 1u, 0, 0);
        __debugbreak();
      }
      v4 = *(_QWORD **)((v1 & -(__int64)(this != 0)) + 8);
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
    *(_DWORD *)v1 = 0;
  }
}

```

## disassembly

```asm
0x18000dedc  push    rbx
0x18000dede  push    rsi
0x18000dedf  push    rdi
0x18000dee0  push    r14
0x18000dee2  push    r15
0x18000dee4  sub     rsp, 20h
0x18000dee8  lea     r14, [rcx+8]
0x18000deec  mov     rdi, rcx
0x18000deef  cmp     dword ptr [r14], 0
0x18000def3  jz      loc_18000DF82
0x18000def9  cmp     qword ptr [rcx+10h], 0
0x18000defe  jz      short loc_18000DF5C
0x18000df00  mov     rax, rcx
0x18000df03  neg     rax
0x18000df06  sbb     rsi, rsi
0x18000df09  and     rsi, r14
0x18000df0c  jnz     short loc_18000DF23
0x18000df0e  xor     r9d, r9d; lpArguments
0x18000df11  lea     edx, [rsi+1]; dwExceptionFlags
0x18000df14  xor     r8d, r8d; nNumberOfArguments
0x18000df17  mov     ecx, 0C0000005h; dwExceptionCode
0x18000df1c  call    cs:__imp_RaiseException
0x18000df22  int     3; Trap to Debugger
0x18000df23  mov     r15, [rsi+8]
0x18000df27  test    r15, r15
0x18000df2a  jz      short loc_18000DF4C
0x18000df2c  mov     rcx, [r15+8]
0x18000df30  mov     rax, [r15]
0x18000df33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df38  mov     rbx, [r15+10h]
0x18000df3c  mov     rcx, r15; lpMem
0x18000df3f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000df44  mov     r15, rbx
0x18000df47  test    rbx, rbx
0x18000df4a  jnz     short loc_18000DF2C
0x18000df4c  mov     qword ptr [rsi+8], 0
0x18000df54  mov     qword ptr [rdi+10h], 0
0x18000df5c  mov     rcx, [rdi+40h]
0x18000df60  test    rcx, rcx
0x18000df63  jz      short loc_18000DF71
0x18000df65  mov     rax, [rcx]
0x18000df68  mov     rax, [rax+10h]
0x18000df6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df71  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000df75  call    cs:__imp_DeleteCriticalSection
0x18000df7b  mov     dword ptr [r14], 0
0x18000df82  add     rsp, 20h
0x18000df86  pop     r15
0x18000df88  pop     r14
0x18000df8a  pop     rdi
0x18000df8b  pop     rsi
0x18000df8c  pop     rbx
0x18000df8d  retn
```
