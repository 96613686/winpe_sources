# ATL::CAtlModule::Term(void)

- ea: `0x18000b644`
- end: `0x18000b6f6`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `178`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180008de0`
- `0x18000b6fc`
- `0x18000cdb0`

## callees

- `0x180001240`
- `0x18000b644`
- `0x18000d010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000b6dd`
- `KERNEL32!DeleteCriticalSection` at `0x18000b6dd`
- `KERNEL32!RaiseException` at `0x18000b684`
- `KERNEL32!RaiseException` at `0x18000b684`

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
0x18000b644  push    rbx
0x18000b646  push    rsi
0x18000b647  push    rdi
0x18000b648  push    r14
0x18000b64a  push    r15
0x18000b64c  sub     rsp, 20h
0x18000b650  mov     rdi, rcx
0x18000b653  lea     r14, [rcx+8]
0x18000b657  cmp     dword ptr [r14], 0
0x18000b65b  jz      loc_18000B6EA
0x18000b661  cmp     qword ptr [rcx+10h], 0
0x18000b666  jz      short loc_18000B6C4
0x18000b668  mov     rax, rcx
0x18000b66b  neg     rax
0x18000b66e  sbb     rsi, rsi
0x18000b671  and     rsi, r14
0x18000b674  jnz     short loc_18000B68B
0x18000b676  xor     r9d, r9d; lpArguments
0x18000b679  xor     r8d, r8d; nNumberOfArguments
0x18000b67c  lea     edx, [rsi+1]; dwExceptionFlags
0x18000b67f  mov     ecx, 0C0000005h; dwExceptionCode
0x18000b684  call    cs:__imp_RaiseException
0x18000b68a  int     3; Trap to Debugger
0x18000b68b  mov     r15, [rsi+8]
0x18000b68f  test    r15, r15
0x18000b692  jz      short loc_18000B6B4
0x18000b694  mov     rcx, [r15+8]
0x18000b698  mov     rax, [r15]
0x18000b69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6a0  mov     rbx, [r15+10h]
0x18000b6a4  mov     rcx, r15; Block
0x18000b6a7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b6ac  mov     r15, rbx
0x18000b6af  test    rbx, rbx
0x18000b6b2  jnz     short loc_18000B694
0x18000b6b4  mov     qword ptr [rsi+8], 0
0x18000b6bc  mov     qword ptr [rdi+10h], 0
0x18000b6c4  mov     rcx, [rdi+40h]
0x18000b6c8  test    rcx, rcx
0x18000b6cb  jz      short loc_18000B6D9
0x18000b6cd  mov     rax, [rcx]
0x18000b6d0  mov     rax, [rax+10h]
0x18000b6d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6d9  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000b6dd  call    cs:__imp_DeleteCriticalSection
0x18000b6e3  mov     dword ptr [r14], 0
0x18000b6ea  add     rsp, 20h
0x18000b6ee  pop     r15
0x18000b6f0  pop     r14
0x18000b6f2  pop     rdi
0x18000b6f3  pop     rsi
0x18000b6f4  pop     rbx
0x18000b6f5  retn
```
