# DAS::ProviderManagement::ProviderManager::GetProviderFromProtocolId(_GUID const *,std::shared_ptr<ProviderContext> &)

- ea: `0x1400124d0`
- end: `0x1400126fc`
- name: `?GetProviderFromProtocolId@ProviderManager@ProviderManagement@DAS@@QEAAJPEBU_GUID@@AEAV?$shared_ptr@VProviderContext@@@std@@@Z`
- size: `556`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000afa4`

## callees

- `0x140001570`
- `0x140006ce4`
- `0x1400106b4`
- `0x140011650`
- `0x140011c18`
- `0x1400124d0`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001253a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001269d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400126ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400126bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400126cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001253a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001269d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400126ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400126bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400126cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140012505`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001254e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140012505`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001254e`

## pseudocode

```c
__int64 __fastcall DAS::ProviderManagement::ProviderManager::GetProviderFromProtocolId(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  RTL_SRWLOCK *v6; // rsi
  RTL_SRWLOCK *v8; // rbp
  __int64 *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rdi
  __int64 **v13; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  char *v16[4]; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v17[2]; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v6 = (RTL_SRWLOCK *)(a1 + 8);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 8));
  if ( *(_BYTE *)(a1 + 16) )
  {
    v8 = (RTL_SRWLOCK *)(a1 + 24);
    AcquireSRWLockShared((PSRWLOCK)(a1 + 24));
    v9 = **(__int64 ***)(a1 + 32);
    while ( !*((_BYTE *)v9 + 25) )
    {
      std::wstring::wstring((__int64)v16, (__int64)(v9 + 4));
      v10 = v9[9];
      if ( v10 )
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
      v11 = v9[8];
      v17[0] = v11;
      v12 = (volatile signed __int32 *)v9[9];
      v17[1] = v12;
      if ( *a2 == *(_QWORD *)(v11 + 8) && a2[1] == *(_QWORD *)(v11 + 16) )
      {
        std::shared_ptr<ProviderContext>::operator=(a3, v17);
        if ( v12 )
        {
          if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
            if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
          }
        }
        std::wstring::~wstring(v16);
        if ( v8 )
          ReleaseSRWLockShared(v8);
        if ( v6 )
          ReleaseSRWLockShared(v6);
        return 0;
      }
      if ( v12 )
      {
        if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
      std::wstring::~wstring(v16);
      v13 = (__int64 **)v9[2];
      if ( *((_BYTE *)v13 + 25) )
      {
        for ( i = (__int64 *)v9[1]; !*((_BYTE *)i + 25) && v9 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v9 = i;
        v9 = i;
      }
      else
      {
        v9 = (__int64 *)v9[2];
        for ( j = *v13; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v9 = j;
      }
    }
    if ( v8 )
      ReleaseSRWLockShared(v8);
    if ( v6 )
      ReleaseSRWLockShared(v6);
    return 2154037260LL;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2AD,
      (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
      (const char *)0x80640013LL,
      (int)v16[0]);
    if ( v6 )
      ReleaseSRWLockShared(v6);
    return 2154037267LL;
  }
}

```

## disassembly

```asm
0x1400124d0  mov     [rsp+arg_8], rbx
0x1400124d5  mov     [rsp+arg_18], rbp
0x1400124da  push    rsi
0x1400124db  push    rdi
0x1400124dc  push    r13
0x1400124de  push    r14
0x1400124e0  push    r15
0x1400124e2  sub     rsp, 60h
0x1400124e6  mov     rax, cs:__security_cookie
0x1400124ed  xor     rax, rsp
0x1400124f0  mov     [rsp+88h+var_38], rax
0x1400124f5  mov     r15, r8
0x1400124f8  mov     r14, rdx
0x1400124fb  mov     rbx, rcx
0x1400124fe  lea     rsi, [rcx+8]
0x140012502  mov     rcx, rsi; SRWLock
0x140012505  call    cs:__imp_AcquireSRWLockShared
0x14001250b  cmp     byte ptr [rbx+10h], 0
0x14001250f  jnz     short loc_140012547
0x140012511  mov     rcx, [rsp+88h]; this
0x140012519  mov     ebx, 80640013h
0x14001251e  mov     r9d, ebx; char *
0x140012521  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x140012528  mov     edx, 2ADh; void *
0x14001252d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012532  test    rsi, rsi
0x140012535  jz      short loc_140012540
0x140012537  mov     rcx, rsi; SRWLock
0x14001253a  call    cs:__imp_ReleaseSRWLockShared
0x140012540  mov     eax, ebx
0x140012542  jmp     loc_1400126D6
0x140012547  lea     rbp, [rbx+18h]
0x14001254b  mov     rcx, rbp; SRWLock
0x14001254e  call    cs:__imp_AcquireSRWLockShared
0x140012554  mov     rbx, [rbx+20h]
0x140012558  mov     rbx, [rbx]
0x14001255b  or      r13d, 0FFFFFFFFh
0x14001255f  cmp     byte ptr [rbx+19h], 0
0x140012563  jnz     loc_1400126B5
0x140012569  lea     rdx, [rbx+20h]
0x14001256d  lea     rcx, [rsp+88h+var_68]
0x140012572  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140012577  mov     rax, [rbx+48h]
0x14001257b  test    rax, rax
0x14001257e  jz      short loc_140012584
0x140012580  lock inc dword ptr [rax+8]
0x140012584  mov     rcx, [rbx+40h]
0x140012588  mov     [rsp+88h+var_48], rcx
0x14001258d  mov     rdi, [rbx+48h]
0x140012591  mov     [rsp+88h+var_40], rdi
0x140012596  mov     rax, [r14]
0x140012599  cmp     rax, [rcx+8]
0x14001259d  jnz     short loc_1400125AD
0x14001259f  mov     rax, [r14+8]
0x1400125a3  cmp     rax, [rcx+10h]
0x1400125a7  jz      loc_140012642
0x1400125ad  test    rdi, rdi
0x1400125b0  jz      short loc_1400125E9
0x1400125b2  mov     eax, r13d
0x1400125b5  lock xadd [rdi+8], eax
0x1400125ba  add     eax, r13d
0x1400125bd  jnz     short loc_1400125E9
0x1400125bf  mov     rax, [rdi]
0x1400125c2  mov     rcx, rdi
0x1400125c5  mov     rax, [rax]
0x1400125c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400125cd  mov     eax, r13d
0x1400125d0  lock xadd [rdi+0Ch], eax
0x1400125d5  add     eax, r13d
0x1400125d8  jnz     short loc_1400125E9
0x1400125da  mov     rax, [rdi]
0x1400125dd  mov     rcx, rdi
0x1400125e0  mov     rax, [rax+8]
0x1400125e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400125e9  lea     rcx, [rsp+88h+var_68]
0x1400125ee  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400125f3  mov     rcx, [rbx+10h]
0x1400125f7  cmp     byte ptr [rcx+19h], 0
0x1400125fb  jz      short loc_14001261E
0x1400125fd  mov     rax, [rbx+8]
0x140012601  jmp     short loc_140012610
0x140012603  cmp     rbx, [rax+10h]
0x140012607  jnz     short loc_140012616
0x140012609  mov     rbx, rax
0x14001260c  mov     rax, [rax+8]
0x140012610  cmp     byte ptr [rax+19h], 0
0x140012614  jz      short loc_140012603
0x140012616  mov     rbx, rax
0x140012619  jmp     loc_14001255F
0x14001261e  mov     rbx, rcx
0x140012621  mov     rcx, [rcx]
0x140012624  cmp     byte ptr [rcx+19h], 0
0x140012628  jnz     loc_14001255F
0x14001262e  mov     rbx, rcx
0x140012631  mov     rax, [rcx]
0x140012634  mov     rcx, rax
0x140012637  cmp     byte ptr [rax+19h], 0
0x14001263b  jz      short loc_14001262E
0x14001263d  jmp     loc_14001255F
0x140012642  lea     rdx, [rsp+88h+var_48]
0x140012647  mov     rcx, r15
0x14001264a  call    ??4?$shared_ptr@VProviderContext@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ProviderContext>::operator=(std::shared_ptr<ProviderContext> const &)
0x14001264f  test    rdi, rdi
0x140012652  jz      short loc_14001268B
0x140012654  mov     eax, r13d
0x140012657  lock xadd [rdi+8], eax
0x14001265c  add     eax, r13d
0x14001265f  jnz     short loc_14001268B
0x140012661  mov     rax, [rdi]
0x140012664  mov     rcx, rdi
0x140012667  mov     rax, [rax]
0x14001266a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001266f  mov     eax, r13d
0x140012672  lock xadd [rdi+0Ch], eax
0x140012677  add     eax, r13d
0x14001267a  jnz     short loc_14001268B
0x14001267c  mov     rax, [rdi]
0x14001267f  mov     rcx, rdi
0x140012682  mov     rax, [rax+8]
0x140012686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001268b  lea     rcx, [rsp+88h+var_68]
0x140012690  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140012695  test    rbp, rbp
0x140012698  jz      short loc_1400126A3
0x14001269a  mov     rcx, rbp; SRWLock
0x14001269d  call    cs:__imp_ReleaseSRWLockShared
0x1400126a3  test    rsi, rsi
0x1400126a6  jz      short loc_1400126B1
0x1400126a8  mov     rcx, rsi; SRWLock
0x1400126ab  call    cs:__imp_ReleaseSRWLockShared
0x1400126b1  xor     eax, eax
0x1400126b3  jmp     short loc_1400126D6
0x1400126b5  test    rbp, rbp
0x1400126b8  jz      short loc_1400126C3
0x1400126ba  mov     rcx, rbp; SRWLock
0x1400126bd  call    cs:__imp_ReleaseSRWLockShared
0x1400126c3  test    rsi, rsi
0x1400126c6  jz      short loc_1400126D1
0x1400126c8  mov     rcx, rsi; SRWLock
0x1400126cb  call    cs:__imp_ReleaseSRWLockShared
0x1400126d1  mov     eax, 8064000Ch
0x1400126d6  mov     rcx, [rsp+88h+var_38]
0x1400126db  xor     rcx, rsp; StackCookie
0x1400126de  call    __security_check_cookie
0x1400126e3  lea     r11, [rsp+88h+var_28]
0x1400126e8  mov     rbx, [r11+38h]
0x1400126ec  mov     rbp, [r11+48h]
0x1400126f0  mov     rsp, r11
0x1400126f3  pop     r15
0x1400126f5  pop     r14
0x1400126f7  pop     r13
0x1400126f9  pop     rdi
0x1400126fa  pop     rsi
0x1400126fb  retn
```
