# ATL::CAtlModule::Term(void)

- ea: `0x180006090`
- end: `0x180006147`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180004070`
- `0x1800067c0`
- `0x180022d70`

## callees

- `0x180002294`
- `0x180006090`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000612e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000612e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800060d0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800060d0`

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
          operator delete(v4, 0x18u);
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
0x180006090  push    rbx
0x180006092  push    rsi
0x180006093  push    rdi
0x180006094  push    r14
0x180006096  push    r15
0x180006098  sub     rsp, 20h
0x18000609c  mov     rdi, rcx
0x18000609f  lea     r14, [rcx+8]
0x1800060a3  cmp     dword ptr [r14], 0
0x1800060a7  jz      loc_18000613B
0x1800060ad  cmp     qword ptr [rcx+10h], 0
0x1800060b2  jz      short loc_180006115
0x1800060b4  mov     rax, rcx
0x1800060b7  neg     rax
0x1800060ba  sbb     rsi, rsi
0x1800060bd  and     rsi, r14
0x1800060c0  jnz     short loc_1800060D7
0x1800060c2  xor     r9d, r9d; lpArguments
0x1800060c5  xor     r8d, r8d; nNumberOfArguments
0x1800060c8  lea     edx, [rsi+1]; dwExceptionFlags
0x1800060cb  mov     ecx, 0C0000005h; dwExceptionCode
0x1800060d0  call    cs:__imp_RaiseException
0x1800060d6  int     3; Trap to Debugger
0x1800060d7  mov     r15, [rsi+8]
0x1800060db  test    r15, r15
0x1800060de  jz      short loc_180006105
0x1800060e0  mov     rcx, [r15+8]
0x1800060e4  mov     rax, [r15]
0x1800060e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060ec  mov     rbx, [r15+10h]
0x1800060f0  mov     edx, 18h; unsigned __int64
0x1800060f5  mov     rcx, r15; void *
0x1800060f8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800060fd  mov     r15, rbx
0x180006100  test    rbx, rbx
0x180006103  jnz     short loc_1800060E0
0x180006105  mov     qword ptr [rsi+8], 0
0x18000610d  mov     qword ptr [rdi+10h], 0
0x180006115  mov     rcx, [rdi+40h]
0x180006119  test    rcx, rcx
0x18000611c  jz      short loc_18000612A
0x18000611e  mov     rax, [rcx]
0x180006121  mov     rax, [rax+10h]
0x180006125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000612a  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000612e  call    cs:__imp_DeleteCriticalSection
0x180006134  mov     dword ptr [r14], 0
0x18000613b  add     rsp, 20h
0x18000613f  pop     r15
0x180006141  pop     r14
0x180006143  pop     rdi
0x180006144  pop     rsi
0x180006145  pop     rbx
0x180006146  retn
```
