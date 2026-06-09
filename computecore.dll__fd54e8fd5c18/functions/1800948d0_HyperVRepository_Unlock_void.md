# HyperVRepository::Unlock(void)

- ea: `0x1800948d0`
- end: `0x18009499e`
- name: `?Unlock@HyperVRepository@@UEAAJXZ`
- size: `206`
- prototype: `__int64 __fastcall(HyperVRepository *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18001587c`
- `0x1800948d0`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180094958`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180094958`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800948ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800948ec`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18009496a`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18009496a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800948f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800948f2`

## string_xrefs

- `0x18009498b`: `onecore\vm\common\repository\core\hypervrepository.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HyperVRepository::Unlock(HyperVRepository *this)
{
  char v2; // si
  char *v3; // rdi
  DWORD CurrentThreadId; // eax
  char v5; // al
  int v6; // eax
  int v7; // eax
  int v8; // eax
  const char *v9; // r9
  __int64 result; // rax
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = 0;
  v3 = (char *)this + 112;
  AcquireSRWLockExclusive((PSRWLOCK)this + 14);
  CurrentThreadId = GetCurrentThreadId();
  *((_DWORD *)v3 + 2) = CurrentThreadId;
  v5 = 1;
  try
  {
    while ( v5 )
    {
      v6 = *((_DWORD *)this + 34);
      if ( v6 )
      {
        v7 = v6 - 1;
        *((_DWORD *)this + 34) = v7;
        if ( !v7 )
        {
          v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 40LL))(*((_QWORD *)this + 13));
          if ( v8 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x227,
              (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
              (const char *)(unsigned int)v8,
              v11);
          *(_QWORD *)((char *)this + 140) = 0;
          v2 = 1;
        }
      }
      v5 = 0;
    }
    *((_DWORD *)v3 + 2) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v3);
    if ( v2 )
      WakeAllConditionVariable((PCONDITION_VARIABLE)this + 16);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x235,
                           (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800948d0  mov     [rsp+arg_8], rbx
0x1800948d5  mov     [rsp+arg_10], rsi
0x1800948da  push    rdi
0x1800948db  sub     rsp, 40h
0x1800948df  mov     rbx, rcx
0x1800948e2  xor     sil, sil
0x1800948e5  lea     rdi, [rcx+70h]
0x1800948e9  mov     rcx, rdi; SRWLock
0x1800948ec  call    cs:__imp_AcquireSRWLockExclusive
0x1800948f2  call    cs:__imp_GetCurrentThreadId
0x1800948f8  mov     [rdi+8], eax
0x1800948fb  mov     [rsp+48h+var_20], rdi
0x180094900  mov     al, 1
0x180094902  mov     [rsp+48h+var_18], al
0x180094906  test    al, al
0x180094908  jz      short loc_18009494E
0x18009490a  mov     eax, [rbx+88h]
0x180094910  test    eax, eax
0x180094912  jz      short loc_180094946
0x180094914  sub     eax, 1
0x180094917  mov     [rbx+88h], eax
0x18009491d  jnz     short loc_180094946
0x18009491f  mov     rcx, [rbx+68h]
0x180094923  mov     rax, [rcx]
0x180094926  mov     rax, [rax+28h]
0x18009492a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009492f  mov     rcx, [rsp+48h]; this
0x180094934  test    eax, eax
0x180094936  js      short loc_180094988
0x180094938  mov     qword ptr [rbx+8Ch], 0
0x180094943  mov     sil, 1
0x180094946  xor     al, al
0x180094948  mov     [rsp+48h+var_18], al
0x18009494c  jmp     short loc_180094906
0x18009494e  mov     dword ptr [rdi+8], 0
0x180094955  mov     rcx, rdi; SRWLock
0x180094958  call    cs:__imp_ReleaseSRWLockExclusive
0x18009495e  test    sil, sil
0x180094961  jz      short loc_180094970
0x180094963  lea     rcx, [rbx+80h]; ConditionVariable
0x18009496a  call    cs:__imp_WakeAllConditionVariable
0x180094970  xor     eax, eax
0x180094972  jmp     short loc_180094978
0x180094974  mov     eax, [rsp+48h+var_28]
0x180094978  mov     rbx, [rsp+48h+arg_8]
0x18009497d  mov     rsi, [rsp+48h+arg_10]
0x180094982  add     rsp, 40h
0x180094986  pop     rdi
0x180094987  retn
0x180094988  mov     r9d, eax; char *
0x18009498b  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\repository\\core\\"...
0x180094992  mov     edx, 227h; void *
0x180094997  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
