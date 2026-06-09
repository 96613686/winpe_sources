# ATL::CAtlModule::Term(void)

- ea: `0x18000f16c`
- end: `0x18000f21f`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `179`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006160`
- `0x18000f228`
- `0x18002f9d0`

## callees

- `0x18000f16c`
- `0x180030010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f1cf`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f1cf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f206`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f206`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f1ac`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f1ac`

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
0x18000f16c  push    rbx
0x18000f16e  push    rsi
0x18000f16f  push    rdi
0x18000f170  push    r14
0x18000f172  push    r15
0x18000f174  sub     rsp, 20h
0x18000f178  mov     rdi, rcx
0x18000f17b  lea     r14, [rcx+8]
0x18000f17f  cmp     dword ptr [r14], 0
0x18000f183  jz      loc_18000F213
0x18000f189  cmp     qword ptr [rcx+10h], 0
0x18000f18e  jz      short loc_18000F1ED
0x18000f190  mov     rax, rcx
0x18000f193  neg     rax
0x18000f196  sbb     rsi, rsi
0x18000f199  and     rsi, r14
0x18000f19c  jnz     short loc_18000F1B3
0x18000f19e  xor     r9d, r9d; lpArguments
0x18000f1a1  xor     r8d, r8d; nNumberOfArguments
0x18000f1a4  lea     edx, [rsi+1]; dwExceptionFlags
0x18000f1a7  mov     ecx, 0C0000005h; dwExceptionCode
0x18000f1ac  call    cs:__imp_RaiseException
0x18000f1b2  int     3; Trap to Debugger
0x18000f1b3  mov     r15, [rsi+8]
0x18000f1b7  test    r15, r15
0x18000f1ba  jz      short loc_18000F1DD
0x18000f1bc  mov     rcx, [r15+8]
0x18000f1c0  mov     rax, [r15]
0x18000f1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1c8  mov     rbx, [r15+10h]
0x18000f1cc  mov     rcx, r15
0x18000f1cf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f1d5  mov     r15, rbx
0x18000f1d8  test    rbx, rbx
0x18000f1db  jnz     short loc_18000F1BC
0x18000f1dd  mov     qword ptr [rsi+8], 0
0x18000f1e5  mov     qword ptr [rdi+10h], 0
0x18000f1ed  mov     rcx, [rdi+40h]
0x18000f1f1  test    rcx, rcx
0x18000f1f4  jz      short loc_18000F202
0x18000f1f6  mov     rax, [rcx]
0x18000f1f9  mov     rax, [rax+10h]
0x18000f1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f202  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000f206  call    cs:__imp_DeleteCriticalSection
0x18000f20c  mov     dword ptr [r14], 0
0x18000f213  add     rsp, 20h
0x18000f217  pop     r15
0x18000f219  pop     r14
0x18000f21b  pop     rdi
0x18000f21c  pop     rsi
0x18000f21d  pop     rbx
0x18000f21e  retn
```
