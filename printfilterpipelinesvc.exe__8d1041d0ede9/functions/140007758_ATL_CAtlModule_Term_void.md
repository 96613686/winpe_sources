# ATL::CAtlModule::Term(void)

- ea: `0x140007758`
- end: `0x14000780f`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1400044e4`

## callees

- `0x140007758`
- `0x140046340`
- `0x140063010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400077f6`
- `KERNEL32!DeleteCriticalSection` at `0x1400077f6`
- `KERNEL32!RaiseException` at `0x140007798`
- `KERNEL32!RaiseException` at `0x140007798`

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
0x140007758  push    rbx
0x14000775a  push    rsi
0x14000775b  push    rdi
0x14000775c  push    r14
0x14000775e  push    r15
0x140007760  sub     rsp, 20h
0x140007764  mov     rdi, rcx
0x140007767  lea     r14, [rcx+8]
0x14000776b  cmp     dword ptr [r14], 0
0x14000776f  jz      loc_140007803
0x140007775  cmp     qword ptr [rcx+10h], 0
0x14000777a  jz      short loc_1400077DD
0x14000777c  mov     rax, rcx
0x14000777f  neg     rax
0x140007782  sbb     rsi, rsi
0x140007785  and     rsi, r14
0x140007788  jnz     short loc_14000779F
0x14000778a  xor     r9d, r9d; lpArguments
0x14000778d  xor     r8d, r8d; nNumberOfArguments
0x140007790  lea     edx, [rsi+1]; dwExceptionFlags
0x140007793  mov     ecx, 0C0000005h; dwExceptionCode
0x140007798  call    cs:__imp_RaiseException
0x14000779e  int     3; Trap to Debugger
0x14000779f  mov     r15, [rsi+8]
0x1400077a3  test    r15, r15
0x1400077a6  jz      short loc_1400077CD
0x1400077a8  mov     rcx, [r15+8]
0x1400077ac  mov     rax, [r15]
0x1400077af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400077b4  mov     rbx, [r15+10h]
0x1400077b8  mov     edx, 18h
0x1400077bd  mov     rcx, r15; Block
0x1400077c0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400077c5  mov     r15, rbx
0x1400077c8  test    rbx, rbx
0x1400077cb  jnz     short loc_1400077A8
0x1400077cd  mov     qword ptr [rsi+8], 0
0x1400077d5  mov     qword ptr [rdi+10h], 0
0x1400077dd  mov     rcx, [rdi+40h]
0x1400077e1  test    rcx, rcx
0x1400077e4  jz      short loc_1400077F2
0x1400077e6  mov     rax, [rcx]
0x1400077e9  mov     rax, [rax+10h]
0x1400077ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400077f2  lea     rcx, [rdi+18h]; lpCriticalSection
0x1400077f6  call    cs:__imp_DeleteCriticalSection
0x1400077fc  mov     dword ptr [r14], 0
0x140007803  add     rsp, 20h
0x140007807  pop     r15
0x140007809  pop     r14
0x14000780b  pop     rdi
0x14000780c  pop     rsi
0x14000780d  pop     rbx
0x14000780e  retn
```
