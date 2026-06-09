# ATL::CAtlModule::Term(void)

- ea: `0x180008ca8`
- end: `0x180008d6c`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `196`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180007e74`

## callees

- `0x180001824`
- `0x180008ca8`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008d4c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008d4c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008ce8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008ce8`

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
      v4 = *(_QWORD **)(v3 + 8);
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
0x180008ca8  push    rbx
0x180008caa  push    rsi
0x180008cab  push    rdi
0x180008cac  push    r14
0x180008cae  push    r15
0x180008cb0  sub     rsp, 20h
0x180008cb4  mov     rdi, rcx
0x180008cb7  lea     r14, [rcx+8]
0x180008cbb  cmp     dword ptr [r14], 0
0x180008cbf  jz      loc_180008D5F
0x180008cc5  cmp     qword ptr [rcx+10h], 0
0x180008cca  jz      short loc_180008D33
0x180008ccc  mov     rax, rcx
0x180008ccf  neg     rax
0x180008cd2  sbb     rsi, rsi
0x180008cd5  and     rsi, r14
0x180008cd8  jnz     short loc_180008CF5
0x180008cda  xor     r9d, r9d; lpArguments
0x180008cdd  xor     r8d, r8d; nNumberOfArguments
0x180008ce0  lea     edx, [rsi+1]; dwExceptionFlags
0x180008ce3  mov     ecx, 0C0000005h; dwExceptionCode
0x180008ce8  call    cs:__imp_RaiseException
0x180008cef  nop     dword ptr [rax+rax+00h]
0x180008cf4  int     3; Trap to Debugger
0x180008cf5  mov     r15, [rsi+8]
0x180008cf9  test    r15, r15
0x180008cfc  jz      short loc_180008D23
0x180008cfe  mov     rcx, [r15+8]
0x180008d02  mov     rax, [r15]
0x180008d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d0a  mov     rbx, [r15+10h]
0x180008d0e  mov     edx, 18h; unsigned __int64
0x180008d13  mov     rcx, r15; void *
0x180008d16  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008d1b  mov     r15, rbx
0x180008d1e  test    rbx, rbx
0x180008d21  jnz     short loc_180008CFE
0x180008d23  mov     qword ptr [rsi+8], 0
0x180008d2b  mov     qword ptr [rdi+10h], 0
0x180008d33  mov     rcx, [rdi+40h]
0x180008d37  test    rcx, rcx
0x180008d3a  jz      short loc_180008D48
0x180008d3c  mov     rax, [rcx]
0x180008d3f  mov     rax, [rax+10h]
0x180008d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d48  lea     rcx, [rdi+18h]; lpCriticalSection
0x180008d4c  call    cs:__imp_DeleteCriticalSection
0x180008d53  nop     dword ptr [rax+rax+00h]
0x180008d58  mov     dword ptr [r14], 0
0x180008d5f  add     rsp, 20h
0x180008d63  pop     r15
0x180008d65  pop     r14
0x180008d67  pop     rdi
0x180008d68  pop     rsi
0x180008d69  pop     rbx
0x180008d6a  retn
```
