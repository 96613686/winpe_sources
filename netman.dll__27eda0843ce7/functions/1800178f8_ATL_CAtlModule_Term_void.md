# ATL::CAtlModule::Term(void)

- ea: `0x1800178f8`
- end: `0x1800179af`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180004d98`
- `0x1800096b0`
- `0x180009740`
- `0x180035890`

## callees

- `0x180001734`
- `0x1800178f8`
- `0x180036010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180017938`
- `KERNEL32!RaiseException` at `0x180017938`
- `KERNEL32!DeleteCriticalSection` at `0x180017996`
- `KERNEL32!DeleteCriticalSection` at `0x180017996`

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
0x1800178f8  push    rbx
0x1800178fa  push    rsi
0x1800178fb  push    rdi
0x1800178fc  push    r14
0x1800178fe  push    r15
0x180017900  sub     rsp, 20h
0x180017904  mov     rdi, rcx
0x180017907  lea     r14, [rcx+8]
0x18001790b  cmp     dword ptr [r14], 0
0x18001790f  jz      loc_1800179A3
0x180017915  cmp     qword ptr [rcx+10h], 0
0x18001791a  jz      short loc_18001797D
0x18001791c  mov     rax, rcx
0x18001791f  neg     rax
0x180017922  sbb     rsi, rsi
0x180017925  and     rsi, r14
0x180017928  jnz     short loc_18001793F
0x18001792a  xor     r9d, r9d; lpArguments
0x18001792d  xor     r8d, r8d; nNumberOfArguments
0x180017930  lea     edx, [rsi+1]; dwExceptionFlags
0x180017933  mov     ecx, 0C0000005h; dwExceptionCode
0x180017938  call    cs:__imp_RaiseException
0x18001793e  int     3; Trap to Debugger
0x18001793f  mov     r15, [rsi+8]
0x180017943  test    r15, r15
0x180017946  jz      short loc_18001796D
0x180017948  mov     rcx, [r15+8]
0x18001794c  mov     rax, [r15]
0x18001794f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017954  mov     rbx, [r15+10h]
0x180017958  mov     edx, 18h; unsigned __int64
0x18001795d  mov     rcx, r15; void *
0x180017960  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017965  mov     r15, rbx
0x180017968  test    rbx, rbx
0x18001796b  jnz     short loc_180017948
0x18001796d  mov     qword ptr [rsi+8], 0
0x180017975  mov     qword ptr [rdi+10h], 0
0x18001797d  mov     rcx, [rdi+40h]
0x180017981  test    rcx, rcx
0x180017984  jz      short loc_180017992
0x180017986  mov     rax, [rcx]
0x180017989  mov     rax, [rax+10h]
0x18001798d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017992  lea     rcx, [rdi+18h]; lpCriticalSection
0x180017996  call    cs:__imp_DeleteCriticalSection
0x18001799c  mov     dword ptr [r14], 0
0x1800179a3  add     rsp, 20h
0x1800179a7  pop     r15
0x1800179a9  pop     r14
0x1800179ab  pop     rdi
0x1800179ac  pop     rsi
0x1800179ad  pop     rbx
0x1800179ae  retn
```
