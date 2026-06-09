# DAS::ProviderManagement::ProviderManager::GetProviderByName(ushort const *,std::shared_ptr<ProviderContext> &)

- ea: `0x140011ea4`
- end: `0x140012113`
- name: `?GetProviderByName@ProviderManager@ProviderManagement@DAS@@QEAAJPEBGAEAV?$shared_ptr@VProviderContext@@@std@@@Z`
- size: `623`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x140009850`
- `0x14000aae0`
- `0x14000afa4`
- `0x14000fea4`

## callees

- `0x140001570`
- `0x140006ce4`
- `0x1400106b4`
- `0x140011650`
- `0x14001176c`
- `0x140011c18`
- `0x140011ea4`
- `0x140014a38`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140011f10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400120b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400120c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400120d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400120e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140011f10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400120b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400120c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400120d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400120e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140011edc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140011f24`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140011edc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140011f24`

## pseudocode

```c
__int64 __fastcall DAS::ProviderManagement::ProviderManager::GetProviderByName(__int64 a1, __int64 a2, _QWORD *a3)
{
  RTL_SRWLOCK *v5; // rsi
  bool v6; // r15
  RTL_SRWLOCK *v8; // r14
  __int64 *v9; // rbx
  __int64 v10; // rax
  volatile signed __int32 *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rdx
  const wchar_t *v14; // rcx
  __int64 **v15; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  wchar_t *S1[2]; // [rsp+20h] [rbp-60h] BYREF
  size_t N; // [rsp+30h] [rbp-50h]
  unsigned __int64 v20; // [rsp+38h] [rbp-48h]
  __int64 v21; // [rsp+40h] [rbp-40h] BYREF
  volatile signed __int32 *v22; // [rsp+48h] [rbp-38h]
  char *v23[4]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v5 = (RTL_SRWLOCK *)(a1 + 8);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 8));
  v6 = 0;
  if ( *(_BYTE *)(a1 + 16) )
  {
    v8 = (RTL_SRWLOCK *)(a1 + 24);
    AcquireSRWLockShared((PSRWLOCK)(a1 + 24));
    v9 = **(__int64 ***)(a1 + 32);
    while ( !*((_BYTE *)v9 + 25) )
    {
      std::wstring::wstring((__int64)S1, (__int64)(v9 + 4));
      v10 = v9[9];
      if ( v10 )
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
      v21 = v9[8];
      v11 = (volatile signed __int32 *)v9[9];
      v22 = v11;
      v12 = std::wstring::wstring(v23);
      v13 = *(_QWORD *)(v12 + 16);
      if ( *(_QWORD *)(v12 + 24) > 7u )
        v12 = *(_QWORD *)v12;
      v14 = (const wchar_t *)S1;
      if ( v20 > 7 )
        v14 = S1[0];
      if ( N == v13 )
      {
        if ( N )
        {
          v6 = wmemcmp(v14, (const wchar_t *)v12, N) == 0;
          v11 = v22;
        }
        else
        {
          v6 = 1;
        }
      }
      std::wstring::~wstring(v23);
      if ( v6 )
      {
        std::shared_ptr<ProviderContext>::operator=(a3, &v21);
        if ( v11 )
        {
          if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
            if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
          }
        }
        std::wstring::~wstring((char **)S1);
        if ( v8 )
          ReleaseSRWLockShared(v8);
        if ( v5 )
          ReleaseSRWLockShared(v5);
        return 0;
      }
      v6 = 0;
      if ( v11 )
      {
        if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
          if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
        }
      }
      std::wstring::~wstring((char **)S1);
      v15 = (__int64 **)v9[2];
      if ( *((_BYTE *)v15 + 25) )
      {
        for ( i = (__int64 *)v9[1]; !*((_BYTE *)i + 25) && v9 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v9 = i;
        v9 = i;
      }
      else
      {
        v9 = (__int64 *)v9[2];
        for ( j = *v15; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v9 = j;
      }
    }
    if ( v8 )
      ReleaseSRWLockShared(v8);
    if ( v5 )
      ReleaseSRWLockShared(v5);
    return 2154037260LL;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x278,
      (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
      (const char *)0x80640013LL,
      (int)S1[0]);
    if ( v5 )
      ReleaseSRWLockShared(v5);
    return 2154037267LL;
  }
}

```

## disassembly

```asm
0x140011ea4  mov     [rsp-38h+arg_18], rbx
0x140011ea9  push    rbp
0x140011eaa  push    rsi
0x140011eab  push    rdi
0x140011eac  push    r12
0x140011eae  push    r13
0x140011eb0  push    r14
0x140011eb2  push    r15
0x140011eb4  mov     rbp, rsp
0x140011eb7  sub     rsp, 80h
0x140011ebe  mov     rax, cs:__security_cookie
0x140011ec5  xor     rax, rsp
0x140011ec8  mov     [rbp+var_10], rax
0x140011ecc  mov     r12, r8
0x140011ecf  mov     r13, rdx
0x140011ed2  mov     rbx, rcx
0x140011ed5  lea     rsi, [rcx+8]
0x140011ed9  mov     rcx, rsi; SRWLock
0x140011edc  call    cs:__imp_AcquireSRWLockShared
0x140011ee2  xor     r15d, r15d
0x140011ee5  cmp     [rbx+10h], r15b
0x140011ee9  jnz     short loc_140011F1D
0x140011eeb  mov     rcx, [rbp+38h]; this
0x140011eef  mov     ebx, 80640013h
0x140011ef4  mov     r9d, ebx; char *
0x140011ef7  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x140011efe  mov     edx, 278h; void *
0x140011f03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011f08  test    rsi, rsi
0x140011f0b  jz      short loc_140011F16
0x140011f0d  mov     rcx, rsi; SRWLock
0x140011f10  call    cs:__imp_ReleaseSRWLockShared
0x140011f16  mov     eax, ebx
0x140011f18  jmp     loc_1400120EC
0x140011f1d  lea     r14, [rbx+18h]
0x140011f21  mov     rcx, r14; SRWLock
0x140011f24  call    cs:__imp_AcquireSRWLockShared
0x140011f2a  mov     rbx, [rbx+20h]
0x140011f2e  mov     rbx, [rbx]
0x140011f31  cmp     [rbx+19h], r15b
0x140011f35  jnz     loc_1400120CB
0x140011f3b  lea     rdx, [rbx+20h]
0x140011f3f  lea     rcx, [rbp+S1]
0x140011f43  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140011f48  mov     rax, [rbx+48h]
0x140011f4c  test    rax, rax
0x140011f4f  jz      short loc_140011F55
0x140011f51  lock inc dword ptr [rax+8]
0x140011f55  mov     rax, [rbx+40h]
0x140011f59  mov     [rbp+var_40], rax
0x140011f5d  mov     rdi, [rbx+48h]
0x140011f61  mov     [rbp+var_38], rdi
0x140011f65  mov     rdx, r13
0x140011f68  lea     rcx, [rbp+var_30]
0x140011f6c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140011f71  mov     rdx, [rax+10h]
0x140011f75  cmp     qword ptr [rax+18h], 7
0x140011f7a  jbe     short loc_140011F7F
0x140011f7c  mov     rax, [rax]
0x140011f7f  mov     r8, [rbp+N]; N
0x140011f83  lea     rcx, [rbp+S1]
0x140011f87  cmp     [rbp+var_48], 7
0x140011f8c  cmova   rcx, [rbp+S1]; S1
0x140011f91  cmp     r8, rdx
0x140011f94  jnz     short loc_140011FB2
0x140011f96  test    r8, r8
0x140011f99  jnz     short loc_140011FA0
0x140011f9b  mov     r15b, 1
0x140011f9e  jmp     short loc_140011FB2
0x140011fa0  mov     rdx, rax; S2
0x140011fa3  call    wmemcmp
0x140011fa8  test    eax, eax
0x140011faa  setz    r15b
0x140011fae  mov     rdi, [rbp+var_38]
0x140011fb2  lea     rcx, [rbp+var_30]
0x140011fb6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140011fbb  test    r15b, r15b
0x140011fbe  jnz     loc_14001205B
0x140011fc4  xor     r15d, r15d
0x140011fc7  test    rdi, rdi
0x140011fca  jz      short loc_140012003
0x140011fcc  or      eax, 0FFFFFFFFh
0x140011fcf  lock xadd [rdi+8], eax
0x140011fd4  cmp     eax, 1
0x140011fd7  jnz     short loc_140012003
0x140011fd9  mov     rax, [rdi]
0x140011fdc  mov     rcx, rdi
0x140011fdf  mov     rax, [rax]
0x140011fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011fe7  or      eax, 0FFFFFFFFh
0x140011fea  lock xadd [rdi+0Ch], eax
0x140011fef  cmp     eax, 1
0x140011ff2  jnz     short loc_140012003
0x140011ff4  mov     rax, [rdi]
0x140011ff7  mov     rcx, rdi
0x140011ffa  mov     rax, [rax+8]
0x140011ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012003  lea     rcx, [rbp+S1]
0x140012007  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001200c  mov     rcx, [rbx+10h]
0x140012010  cmp     [rcx+19h], r15b
0x140012014  jz      short loc_140012037
0x140012016  mov     rax, [rbx+8]
0x14001201a  jmp     short loc_140012029
0x14001201c  cmp     rbx, [rax+10h]
0x140012020  jnz     short loc_14001202F
0x140012022  mov     rbx, rax
0x140012025  mov     rax, [rax+8]
0x140012029  cmp     [rax+19h], r15b
0x14001202d  jz      short loc_14001201C
0x14001202f  mov     rbx, rax
0x140012032  jmp     loc_140011F31
0x140012037  mov     rbx, rcx
0x14001203a  mov     rcx, [rcx]
0x14001203d  cmp     [rcx+19h], r15b
0x140012041  jnz     loc_140011F31
0x140012047  mov     rbx, rcx
0x14001204a  mov     rax, [rcx]
0x14001204d  mov     rcx, rax
0x140012050  cmp     [rax+19h], r15b
0x140012054  jz      short loc_140012047
0x140012056  jmp     loc_140011F31
0x14001205b  lea     rdx, [rbp+var_40]
0x14001205f  mov     rcx, r12
0x140012062  call    ??4?$shared_ptr@VProviderContext@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ProviderContext>::operator=(std::shared_ptr<ProviderContext> const &)
0x140012067  test    rdi, rdi
0x14001206a  jz      short loc_1400120A2
0x14001206c  or      ebx, 0FFFFFFFFh
0x14001206f  mov     eax, ebx
0x140012071  lock xadd [rdi+8], eax
0x140012076  add     eax, ebx
0x140012078  jnz     short loc_1400120A2
0x14001207a  mov     rax, [rdi]
0x14001207d  mov     rcx, rdi
0x140012080  mov     rax, [rax]
0x140012083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012088  mov     eax, ebx
0x14001208a  lock xadd [rdi+0Ch], eax
0x14001208f  add     eax, ebx
0x140012091  jnz     short loc_1400120A2
0x140012093  mov     rax, [rdi]
0x140012096  mov     rcx, rdi
0x140012099  mov     rax, [rax+8]
0x14001209d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400120a2  lea     rcx, [rbp+S1]
0x1400120a6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400120ab  test    r14, r14
0x1400120ae  jz      short loc_1400120B9
0x1400120b0  mov     rcx, r14; SRWLock
0x1400120b3  call    cs:__imp_ReleaseSRWLockShared
0x1400120b9  test    rsi, rsi
0x1400120bc  jz      short loc_1400120C7
0x1400120be  mov     rcx, rsi; SRWLock
0x1400120c1  call    cs:__imp_ReleaseSRWLockShared
0x1400120c7  xor     eax, eax
0x1400120c9  jmp     short loc_1400120EC
0x1400120cb  test    r14, r14
0x1400120ce  jz      short loc_1400120D9
0x1400120d0  mov     rcx, r14; SRWLock
0x1400120d3  call    cs:__imp_ReleaseSRWLockShared
0x1400120d9  test    rsi, rsi
0x1400120dc  jz      short loc_1400120E7
0x1400120de  mov     rcx, rsi; SRWLock
0x1400120e1  call    cs:__imp_ReleaseSRWLockShared
0x1400120e7  mov     eax, 8064000Ch
0x1400120ec  mov     rcx, [rbp+var_10]
0x1400120f0  xor     rcx, rsp; StackCookie
0x1400120f3  call    __security_check_cookie
0x1400120f8  mov     rbx, [rsp+80h+arg_18]
0x140012100  add     rsp, 80h
0x140012107  pop     r15
0x140012109  pop     r14
0x14001210b  pop     r13
0x14001210d  pop     r12
0x14001210f  pop     rdi
0x140012110  pop     rsi
0x140012111  pop     rbp
0x140012112  retn
```
