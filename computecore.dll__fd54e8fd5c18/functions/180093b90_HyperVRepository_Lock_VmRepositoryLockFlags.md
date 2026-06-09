# HyperVRepository::Lock(VmRepositoryLockFlags)

- ea: `0x180093b90`
- end: `0x180093e20`
- name: `?Lock@HyperVRepository@@UEAAJW4VmRepositoryLockFlags@@@Z`
- size: `656`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800067c0`
- `0x18000f1b4`
- `0x18001587c`
- `0x180027380`
- `0x180093b90`
- `0x180094860`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180093cb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180093d83`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180093cb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180093d83`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180093bdf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180093bdf`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180093c72`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180093c72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093be5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093c7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093d60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093be5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093c7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093d60`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180093bcf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180093c40`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180093bcf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180093c40`

## string_xrefs

- `0x180093c94`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x180093d9a`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x180093ddd`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x180093df9`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x180093e0d`: `onecore\vm\common\repository\core\hypervrepository.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HyperVRepository::Lock(__int64 a1, char a2)
{
  DWORD v4; // r15d
  DWORD TickCount; // r13d
  char i; // cl
  DWORD v7; // eax
  DWORD v8; // r8d
  BOOL v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  __int64 v12; // rdx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // [rsp+20h] [rbp-48h]
  unsigned int v17; // [rsp+20h] [rbp-48h]
  int v18; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    if ( *(_QWORD *)(a1 + 104) )
    {
      v4 = *(_DWORD *)(a1 + 148);
      TickCount = GetTickCount();
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 112));
      *(_DWORD *)(a1 + 120) = GetCurrentThreadId();
      v17 = a1 + 112;
      for ( i = 1; i; i = 0 )
      {
        while ( *(_DWORD *)(a1 + 140)
             && !HyperVRepository::ThreadHoldsExclusiveLock((HyperVRepository *)a1)
             && ((a2 & 1) != 0 || *(_DWORD *)(a1 + 140) != 1) )
        {
          if ( v4 == -1 )
          {
            v8 = -1;
          }
          else
          {
            v7 = GetTickCount() - TickCount;
            if ( v7 >= v4 )
              v8 = 0;
            else
              v8 = v4 - v7;
          }
          *(_DWORD *)(a1 + 120) = 0;
          v9 = SleepConditionVariableSRW((PCONDITION_VARIABLE)(a1 + 128), (PSRWLOCK)(a1 + 112), v8, 0);
          *(_DWORD *)(a1 + 120) = GetCurrentThreadId();
          if ( !v9 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1E1,
              (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
              (const char *)0x800705B4LL,
              v17);
            *(_DWORD *)(a1 + 120) = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 112));
            return 2147943860LL;
          }
        }
        if ( !*(_DWORD *)(a1 + 136) )
        {
          v18 = 0;
          if ( (*(int (__fastcall **)(_QWORD, int *))(**(_QWORD **)(a1 + 104) + 264LL))(*(_QWORD *)(a1 + 104), &v18) >= 0 )
          {
            v13 = v18;
          }
          else
          {
            v13 = 0;
            v18 = 0;
          }
          if ( !v13 )
          {
            if ( !*(_DWORD *)(a1 + 152) )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x1FA,
                (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
                (const char *)0x37,
                v17);
            v14 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 104) + 336LL))(*(_QWORD *)(a1 + 104));
            if ( v14 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1F6,
                (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
                (const char *)(unsigned int)v14,
                v17);
          }
          LOBYTE(v12) = a2 & 1;
          v15 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 104) + 32LL))(
                  *(_QWORD *)(a1 + 104),
                  v12);
          if ( v15 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1FE,
              (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
              (const char *)(unsigned int)v15,
              v17);
          if ( (a2 & 1) != 0 )
          {
            *(_DWORD *)(a1 + 140) = -1;
            *(_DWORD *)(a1 + 144) = GetCurrentThreadId();
          }
          else
          {
            *(_DWORD *)(a1 + 140) = 1;
          }
        }
        ++*(_DWORD *)(a1 + 136);
      }
      *(_DWORD *)(a1 + 120) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 112));
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
        (const char *)0x8000FFFFLL,
        v16);
      result = 2147549183LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x213,
                           (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180093b90  mov     [rsp+arg_8], rbx
0x180093b95  mov     [rsp+arg_10], rsi
0x180093b9a  push    rdi
0x180093b9b  push    r12
0x180093b9d  push    r13
0x180093b9f  push    r14
0x180093ba1  push    r15
0x180093ba3  sub     rsp, 40h
0x180093ba7  mov     rax, cs:__security_cookie
0x180093bae  xor     rax, rsp
0x180093bb1  mov     [rsp+68h+var_30], rax
0x180093bb6  mov     r12d, edx
0x180093bb9  mov     rdi, rcx
0x180093bbc  xor     ebx, ebx
0x180093bbe  cmp     [rcx+68h], rbx
0x180093bc2  jz      loc_180093D8D
0x180093bc8  mov     r15d, [rcx+94h]
0x180093bcf  call    cs:__imp_GetTickCount
0x180093bd5  mov     r13d, eax
0x180093bd8  lea     rsi, [rdi+70h]
0x180093bdc  mov     rcx, rsi; SRWLock
0x180093bdf  call    cs:__imp_AcquireSRWLockExclusive
0x180093be5  call    cs:__imp_GetCurrentThreadId
0x180093beb  mov     [rsi+8], eax
0x180093bee  mov     [rsp+68h+var_48], rsi
0x180093bf3  mov     cl, 1
0x180093bf5  mov     [rsp+68h+var_40], cl
0x180093bf9  test    cl, cl
0x180093bfb  jz      loc_180093D7D
0x180093c01  mov     r14d, r12d
0x180093c04  and     r14d, 1
0x180093c08  jmp     short loc_180093C0C
0x180093c0a  xor     ebx, ebx
0x180093c0c  cmp     [rdi+8Ch], ebx
0x180093c12  jz      loc_180093CBD
0x180093c18  mov     rcx, rdi; this
0x180093c1b  call    ?ThreadHoldsExclusiveLock@HyperVRepository@@UEBA_NXZ; HyperVRepository::ThreadHoldsExclusiveLock(void)
0x180093c20  test    al, al
0x180093c22  jnz     loc_180093CBD
0x180093c28  test    r14d, r14d
0x180093c2b  jnz     short loc_180093C3A
0x180093c2d  cmp     dword ptr [rdi+8Ch], 1
0x180093c34  jz      loc_180093CBD
0x180093c3a  cmp     r15d, 0FFFFFFFFh
0x180093c3e  jz      short loc_180093C5B
0x180093c40  call    cs:__imp_GetTickCount
0x180093c46  sub     eax, r13d
0x180093c49  cmp     eax, r15d
0x180093c4c  jnb     short loc_180093C56
0x180093c4e  mov     r8d, r15d
0x180093c51  sub     r8d, eax
0x180093c54  jmp     short loc_180093C5E
0x180093c56  xor     r8d, r8d
0x180093c59  jmp     short loc_180093C5E
0x180093c5b  mov     r8d, r15d; dwMilliseconds
0x180093c5e  mov     dword ptr [rsi+8], 0
0x180093c65  xor     r9d, r9d; Flags
0x180093c68  mov     rdx, rsi; SRWLock
0x180093c6b  lea     rcx, [rdi+80h]; ConditionVariable
0x180093c72  call    cs:__imp_SleepConditionVariableSRW
0x180093c78  mov     ebx, eax
0x180093c7a  call    cs:__imp_GetCurrentThreadId
0x180093c80  mov     [rsi+8], eax
0x180093c83  test    ebx, ebx
0x180093c85  jnz     short loc_180093C0A
0x180093c87  mov     rcx, [rsp+68h]; this
0x180093c8c  mov     ebx, 800705B4h
0x180093c91  mov     r9d, ebx; char *
0x180093c94  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\repository\\core\\"...
0x180093c9b  mov     edx, 1E1h; void *
0x180093ca0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093ca5  nop
0x180093ca6  mov     dword ptr [rsi+8], 0
0x180093cad  mov     rcx, rsi; SRWLock
0x180093cb0  call    cs:__imp_ReleaseSRWLockExclusive
0x180093cb6  mov     eax, ebx
0x180093cb8  jmp     loc_180093DB3
0x180093cbd  cmp     [rdi+88h], ebx
0x180093cc3  jnz     loc_180093D6C
0x180093cc9  mov     [rsp+68h+var_38], ebx
0x180093ccd  mov     rcx, [rdi+68h]
0x180093cd1  mov     rax, [rcx]
0x180093cd4  lea     rdx, [rsp+68h+var_38]
0x180093cd9  mov     rax, [rax+108h]
0x180093ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093ce5  test    eax, eax
0x180093ce7  jns     short loc_180093CF1
0x180093ce9  mov     eax, ebx
0x180093ceb  mov     [rsp+68h+var_38], ebx
0x180093cef  jmp     short loc_180093CF5
0x180093cf1  mov     eax, [rsp+68h+var_38]
0x180093cf5  test    eax, eax
0x180093cf7  jnz     short loc_180093D25
0x180093cf9  cmp     [rdi+98h], ebx
0x180093cff  jz      loc_180093DEE
0x180093d05  mov     rcx, [rdi+68h]
0x180093d09  mov     rax, [rcx]
0x180093d0c  mov     rax, [rax+150h]
0x180093d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093d18  mov     rcx, [rsp+68h]; this
0x180093d1d  test    eax, eax
0x180093d1f  js      loc_180093DDA
0x180093d25  mov     rcx, [rdi+68h]
0x180093d29  mov     rax, [rcx]
0x180093d2c  mov     dl, r14b
0x180093d2f  mov     rax, [rax+20h]
0x180093d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093d38  mov     rcx, [rsp+68h]; this
0x180093d3d  test    eax, eax
0x180093d3f  js      loc_180093E0A
0x180093d45  test    r14d, r14d
0x180093d48  jnz     short loc_180093D56
0x180093d4a  mov     dword ptr [rdi+8Ch], 1
0x180093d54  jmp     short loc_180093D6C
0x180093d56  mov     dword ptr [rdi+8Ch], 0FFFFFFFFh
0x180093d60  call    cs:__imp_GetCurrentThreadId
0x180093d66  mov     [rdi+90h], eax
0x180093d6c  inc     dword ptr [rdi+88h]
0x180093d72  mov     cl, bl
0x180093d74  mov     [rsp+68h+var_40], bl
0x180093d78  jmp     loc_180093BF9
0x180093d7d  mov     [rsi+8], ebx
0x180093d80  mov     rcx, rsi; SRWLock
0x180093d83  call    cs:__imp_ReleaseSRWLockExclusive
0x180093d89  xor     eax, eax
0x180093d8b  jmp     short loc_180093DB3
0x180093d8d  mov     rcx, [rsp+68h]; this
0x180093d92  mov     ebx, 8000FFFFh
0x180093d97  mov     r9d, ebx; char *
0x180093d9a  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\repository\\core\\"...
0x180093da1  mov     edx, 1C4h; void *
0x180093da6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093dab  mov     eax, ebx
0x180093dad  jmp     short loc_180093DB3
0x180093daf  mov     eax, [rsp+68h+var_38]
0x180093db3  mov     rcx, [rsp+68h+var_30]
0x180093db8  xor     rcx, rsp; StackCookie
0x180093dbb  call    __security_check_cookie
0x180093dc0  lea     r11, [rsp+68h+var_28]
0x180093dc5  mov     rbx, [r11+38h]
0x180093dc9  mov     rsi, [r11+40h]
0x180093dcd  mov     rsp, r11
0x180093dd0  pop     r15
0x180093dd2  pop     r14
0x180093dd4  pop     r13
0x180093dd6  pop     r12
0x180093dd8  pop     rdi
0x180093dd9  retn
0x180093dda  mov     r9d, eax; char *
0x180093ddd  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\repository\\core\\"...
0x180093de4  mov     edx, 1F6h; void *
0x180093de9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093dee  mov     rcx, [rsp+68h]; this
0x180093df3  mov     r9d, 37h ; '7'; char *
0x180093df9  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\repository\\core\\"...
0x180093e00  mov     edx, 1FAh; void *
0x180093e05  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180093e0a  mov     r9d, eax; char *
0x180093e0d  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\repository\\core\\"...
0x180093e14  mov     edx, 1FEh; void *
0x180093e19  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
