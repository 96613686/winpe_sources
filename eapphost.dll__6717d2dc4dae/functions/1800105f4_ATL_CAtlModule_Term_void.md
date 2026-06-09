# ATL::CAtlModule::Term(void)

- ea: `0x1800105f4`
- end: `0x1800106ab`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000e418`
- `0x180023140`
- `0x1800374a0`

## callees

- `0x180002ab4`
- `0x1800105f4`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010634`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010634`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010692`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010692`

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
0x1800105f4  push    rbx
0x1800105f6  push    rsi
0x1800105f7  push    rdi
0x1800105f8  push    r14
0x1800105fa  push    r15
0x1800105fc  sub     rsp, 20h
0x180010600  mov     rdi, rcx
0x180010603  lea     r14, [rcx+8]
0x180010607  cmp     dword ptr [r14], 0
0x18001060b  jz      loc_18001069F
0x180010611  cmp     qword ptr [rcx+10h], 0
0x180010616  jz      short loc_180010679
0x180010618  mov     rax, rcx
0x18001061b  neg     rax
0x18001061e  sbb     rsi, rsi
0x180010621  and     rsi, r14
0x180010624  jnz     short loc_18001063B
0x180010626  xor     r9d, r9d; lpArguments
0x180010629  xor     r8d, r8d; nNumberOfArguments
0x18001062c  lea     edx, [rsi+1]; dwExceptionFlags
0x18001062f  mov     ecx, 0C0000005h; dwExceptionCode
0x180010634  call    cs:__imp_RaiseException
0x18001063a  int     3; Trap to Debugger
0x18001063b  mov     r15, [rsi+8]
0x18001063f  test    r15, r15
0x180010642  jz      short loc_180010669
0x180010644  mov     rcx, [r15+8]
0x180010648  mov     rax, [r15]
0x18001064b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010650  mov     rbx, [r15+10h]
0x180010654  mov     edx, 18h; unsigned __int64
0x180010659  mov     rcx, r15; void *
0x18001065c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010661  mov     r15, rbx
0x180010664  test    rbx, rbx
0x180010667  jnz     short loc_180010644
0x180010669  mov     qword ptr [rsi+8], 0
0x180010671  mov     qword ptr [rdi+10h], 0
0x180010679  mov     rcx, [rdi+40h]
0x18001067d  test    rcx, rcx
0x180010680  jz      short loc_18001068E
0x180010682  mov     rax, [rcx]
0x180010685  mov     rax, [rax+10h]
0x180010689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001068e  lea     rcx, [rdi+18h]; lpCriticalSection
0x180010692  call    cs:__imp_DeleteCriticalSection
0x180010698  mov     dword ptr [r14], 0
0x18001069f  add     rsp, 20h
0x1800106a3  pop     r15
0x1800106a5  pop     r14
0x1800106a7  pop     rdi
0x1800106a8  pop     rsi
0x1800106a9  pop     rbx
0x1800106aa  retn
```
