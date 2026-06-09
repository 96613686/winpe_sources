# ATL::CAtlModule::Term(void)

- ea: `0x180010eb0`
- end: `0x180010f67`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000ee44`

## callees

- `0x1800017c4`
- `0x180010eb0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010f4e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010f4e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010ef0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010ef0`

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
0x180010eb0  push    rbx
0x180010eb2  push    rsi
0x180010eb3  push    rdi
0x180010eb4  push    r14
0x180010eb6  push    r15
0x180010eb8  sub     rsp, 20h
0x180010ebc  mov     rdi, rcx
0x180010ebf  lea     r14, [rcx+8]
0x180010ec3  cmp     dword ptr [r14], 0
0x180010ec7  jz      loc_180010F5B
0x180010ecd  cmp     qword ptr [rcx+10h], 0
0x180010ed2  jz      short loc_180010F35
0x180010ed4  mov     rax, rcx
0x180010ed7  neg     rax
0x180010eda  sbb     rsi, rsi
0x180010edd  and     rsi, r14
0x180010ee0  jnz     short loc_180010EF7
0x180010ee2  xor     r9d, r9d; lpArguments
0x180010ee5  xor     r8d, r8d; nNumberOfArguments
0x180010ee8  lea     edx, [rsi+1]; dwExceptionFlags
0x180010eeb  mov     ecx, 0C0000005h; dwExceptionCode
0x180010ef0  call    cs:__imp_RaiseException
0x180010ef6  int     3; Trap to Debugger
0x180010ef7  mov     r15, [rsi+8]
0x180010efb  test    r15, r15
0x180010efe  jz      short loc_180010F25
0x180010f00  mov     rcx, [r15+8]
0x180010f04  mov     rax, [r15]
0x180010f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f0c  mov     rbx, [r15+10h]
0x180010f10  mov     edx, 18h; unsigned __int64
0x180010f15  mov     rcx, r15; void *
0x180010f18  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010f1d  mov     r15, rbx
0x180010f20  test    rbx, rbx
0x180010f23  jnz     short loc_180010F00
0x180010f25  mov     qword ptr [rsi+8], 0
0x180010f2d  mov     qword ptr [rdi+10h], 0
0x180010f35  mov     rcx, [rdi+40h]
0x180010f39  test    rcx, rcx
0x180010f3c  jz      short loc_180010F4A
0x180010f3e  mov     rax, [rcx]
0x180010f41  mov     rax, [rax+10h]
0x180010f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f4a  lea     rcx, [rdi+18h]; lpCriticalSection
0x180010f4e  call    cs:__imp_DeleteCriticalSection
0x180010f54  mov     dword ptr [r14], 0
0x180010f5b  add     rsp, 20h
0x180010f5f  pop     r15
0x180010f61  pop     r14
0x180010f63  pop     rdi
0x180010f64  pop     rsi
0x180010f65  pop     rbx
0x180010f66  retn
```
