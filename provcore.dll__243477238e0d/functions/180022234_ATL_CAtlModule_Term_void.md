# ATL::CAtlModule::Term(void)

- ea: `0x180022234`
- end: `0x1800222eb`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlModule *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180021b74`

## callees

- `0x180002b60`
- `0x180022234`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800222d2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800222d2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022274`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022274`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  ATL::_ATL_MODULE70 *v2; // r14
  __int64 v3; // rsi
  _QWORD *v4; // r15
  _QWORD *v5; // rbx
  IGlobalInterfaceTable *m_pGIT; // rcx

  v2 = &this->ATL::_ATL_MODULE70;
  if ( this->cbSize )
  {
    if ( this->m_pTermFuncs )
    {
      v3 = (unsigned __int64)v2 & -(__int64)(this != 0);
      if ( !v3 )
      {
        RaiseException(0xC0000005, 1u, 0, 0);
        __debugbreak();
      }
      v4 = *(_QWORD **)(((unsigned __int64)v2 & -(__int64)(this != 0)) + 8);
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
      this->m_pTermFuncs = 0;
    }
    m_pGIT = this->m_pGIT;
    if ( m_pGIT )
      m_pGIT->Release(m_pGIT);
    DeleteCriticalSection(&this->m_csStaticDataInitAndTypeInfo.m_sec);
    v2->cbSize = 0;
  }
}

```

## disassembly

```asm
0x180022234  push    rbx
0x180022236  push    rsi
0x180022237  push    rdi
0x180022238  push    r14
0x18002223a  push    r15
0x18002223c  sub     rsp, 20h
0x180022240  mov     rdi, this
0x180022243  lea     r14, [this+8]
0x180022247  cmp     dword ptr [r14], 0
0x18002224b  jz      loc_1800222DF
0x180022251  cmp     qword ptr [this+10h], 0
0x180022256  jz      short loc_1800222B9
0x180022258  mov     rax, this
0x18002225b  neg     rax
0x18002225e  sbb     rsi, rsi
0x180022261  and     rsi, r14
0x180022264  jnz     short loc_18002227B
0x180022266  xor     r9d, r9d; lpArguments
0x180022269  xor     r8d, r8d; nNumberOfArguments
0x18002226c  lea     edx, [rsi+1]; dwExceptionFlags
0x18002226f  mov     ecx, 0C0000005h; dwExceptionCode
0x180022274  call    cs:__imp_RaiseException
0x18002227a  int     3; Trap to Debugger
0x18002227b  mov     r15, [rsi+8]
0x18002227f  test    r15, r15
0x180022282  jz      short loc_1800222A9
0x180022284  mov     this, [r15+8]
0x180022288  mov     rax, [r15]
0x18002228b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022290  mov     rbx, [r15+10h]
0x180022294  mov     edx, 18h
0x180022299  mov     this, r15; block
0x18002229c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800222a1  mov     r15, rbx
0x1800222a4  test    rbx, rbx
0x1800222a7  jnz     short loc_180022284
0x1800222a9  mov     qword ptr [rsi+8], 0
0x1800222b1  mov     qword ptr [rdi+10h], 0
0x1800222b9  mov     this, [rdi+40h]
0x1800222bd  test    this, this
0x1800222c0  jz      short loc_1800222CE
0x1800222c2  mov     rax, [this]
0x1800222c5  mov     rax, [rax+10h]
0x1800222c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222ce  lea     this, [rdi+18h]; lpCriticalSection
0x1800222d2  call    cs:__imp_DeleteCriticalSection
0x1800222d8  mov     dword ptr [r14], 0
0x1800222df  add     rsp, 20h
0x1800222e3  pop     r15
0x1800222e5  pop     r14
0x1800222e7  pop     rdi
0x1800222e8  pop     rsi
0x1800222e9  pop     rbx
0x1800222ea  retn
```
