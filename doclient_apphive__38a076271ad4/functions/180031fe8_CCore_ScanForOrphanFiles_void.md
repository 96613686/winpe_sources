# CCore::_ScanForOrphanFiles(void)

- ea: `0x180031fe8`
- end: `0x1800323aa`
- name: `?_ScanForOrphanFiles@CCore@@AEAAXXZ`
- size: `962`
- prototype: `void __fastcall(CCore *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task`

## callers

- `0x1800373f0`

## callees

- `0x1800095a0`
- `0x1800199b4`
- `0x180019c5c`
- `0x18001e260`
- `0x180031fe8`
- `0x1800323b0`
- `0x18009b290`
- `0x18009b368`
- `0x1800a4fe0`
- `0x1800d7d4c`
- `0x1800d86e4`
- `0x1800f82f0`
- `0x1800f8320`
- `0x180108e50`
- `0x1801099b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032313`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032313`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800322fd`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800322fd`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueA` at `0x18003218e`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueA` at `0x1800321c9`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueA` at `0x1800321fe`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueA` at `0x180032233`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueA` at `0x18003218e`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueA` at `0x1800321c9`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueA` at `0x1800321fe`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueA` at `0x180032233`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CCore::_ScanForOrphanFiles(CGlobalConfigManager **this)
{
  const char *v2; // rdx
  const void *v3; // rdx
  void **v4; // rcx
  void **v5; // rdx
  __int64 v6; // rdx
  struct CPersistenceLocation *v7; // rax
  const CHAR *v8; // rbx
  bool *i; // rdi
  const CHAR *v10; // r14
  struct CPersistenceLocation *v11; // rax
  struct CPersistenceLocation *v12; // rax
  const CHAR *v13; // rbx
  struct CPersistenceLocation *v14; // rax
  struct CPersistenceLocation *v15; // rax
  const CHAR *v16; // rbx
  struct CPersistenceLocation *v17; // rax
  struct CPersistenceLocation *v18; // rax
  const CHAR *v19; // rbx
  struct CPersistenceLocation *v20; // rax
  enum _ConfigProviderType *v21; // r8
  CGlobalConfigManager *v22; // r14
  unsigned int v23; // eax
  __int64 v24; // rbx
  _QWORD *v25; // rax
  const char *v27; // r9
  volatile signed __int32 *v28; // rbx
  unsigned int v29[2]; // [rsp+20h] [rbp-B8h] BYREF
  __int128 v30; // [rsp+28h] [rbp-B0h]
  __int64 v31; // [rsp+38h] [rbp-A0h] BYREF
  __int128 v32; // [rsp+40h] [rbp-98h]
  _QWORD v33[7]; // [rsp+50h] [rbp-88h] BYREF
  _QWORD *v34; // [rsp+88h] [rbp-50h]
  void *Buf1[2]; // [rsp+90h] [rbp-48h] BYREF
  size_t Size; // [rsp+A0h] [rbp-38h]
  unsigned __int64 v37; // [rsp+A8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  try
  {
    v30 = 0;
    CGlobalConfigManager::GetDOWorkingDir(this[108]);
    v2 = 0;
    if ( MEMORY[0x18] > 0xFu )
      v2 = *(const char **)v30;
    CCore::_DoScanForOrphanFiles((CCore *)this, v2);
    *(_OWORD *)Buf1 = 0;
    Size = 0;
    v37 = 15;
    LOBYTE(Buf1[0]) = 0;
    if ( (int)CPersistenceLocation::GetDefaultCachePath(Buf1) >= 0 )
    {
      v3 = (const void *)v30;
      if ( *(_QWORD *)(v30 + 24) > 0xFu )
        v3 = *(const void **)v30;
      v4 = Buf1;
      if ( v37 > 0xF )
        v4 = (void **)Buf1[0];
      if ( Size != *(_QWORD *)(v30 + 16) || Size && memcmp(v4, v3, Size) )
      {
        v5 = Buf1;
        if ( v37 > 0xF )
          v5 = (void **)Buf1[0];
        CCore::_DoScanForOrphanFiles((CCore *)this, (const char *)v5);
      }
    }
    v33[0] = std::JPEBD::Z::_Func_impl_no_alloc<`CCorePersistence::CleanupUnusedState'::`2'::_lambda_1_,void near * const volatile,CCore &>::`vftable';
    v33[1] = this;
    v34 = v33;
    RegEnumerateSubKeys(CAppRegistryHive::_shDOSubKey, "Swarms");
    if ( v34 )
    {
      LOBYTE(v6) = v34 != v33;
      (*(void (__fastcall **)(_QWORD *, __int64))(*v34 + 32LL))(v34, v6);
    }
    v7 = CPersistenceLocation::Instance();
    v8 = (char *)v7 + 32;
    if ( *((_QWORD *)v7 + 7) > 0xFu )
      v8 = *(const CHAR **)v8;
    for ( i = (bool *)off_18017E110; i != &CAppRegistryHive::_fUsingPrivateHive; i += 8 )
    {
      v10 = *(const CHAR **)i;
      v11 = CPersistenceLocation::Instance();
      RegDeleteKeyValueA((HKEY)(-2147483645LL - (*((_BYTE *)v11 + 160) != 0)), v8, v10);
    }
    v12 = CPersistenceLocation::Instance();
    v13 = (const CHAR *)v12;
    if ( *((_QWORD *)v12 + 3) > 0xFu )
      v13 = *(const CHAR **)v12;
    v14 = CPersistenceLocation::Instance();
    RegDeleteKeyValueA((HKEY)(-2147483645LL - (*((_BYTE *)v14 + 160) != 0)), v13, "UploadLimitMonthID");
    v15 = CPersistenceLocation::Instance();
    v16 = (const CHAR *)v15;
    if ( *((_QWORD *)v15 + 3) > 0xFu )
      v16 = *(const CHAR **)v15;
    v17 = CPersistenceLocation::Instance();
    RegDeleteKeyValueA((HKEY)(-2147483645LL - (*((_BYTE *)v17 + 160) != 0)), v16, "UploadLimitState");
    v18 = CPersistenceLocation::Instance();
    v19 = (const CHAR *)v18;
    if ( *((_QWORD *)v18 + 3) > 0xFu )
      v19 = *(const CHAR **)v18;
    v20 = CPersistenceLocation::Instance();
    RegDeleteKeyValueA((HKEY)(-2147483645LL - (*((_BYTE *)v20 + 160) != 0)), v19, "PeerId");
    v29[0] = 0;
    CGlobalConfigManager::GetMaxCacheAgeSecs(this[108], v29, v21);
    v22 = this[1];
    v23 = v29[0];
    if ( v29[0] > 0x93A80 )
      v23 = 604800;
    v24 = v23;
    v32 = (unsigned __int64)v22 + 16;
    if ( (unsigned int)mtx_do_lock((char *)v22 + 16) )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)v22 + 23) == 0x7FFFFFFF )
    {
      *((_DWORD *)v22 + 23) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    BYTE8(v32) = 1;
    v31 = 1000 * v24;
    v25 = operator new(0x18u);
    v25[1] = this;
    *v25 = ___7__CTaskImpl_V_lambda_1___2___ScanForOrphanFiles_CCore__AEAAXXZ__CTaskQueue__6B_;
    v25[2] = this;
    *(_QWORD *)v29 = v25;
    CTaskQueue::_Add(v22, v29, &v31);
    if ( *(_QWORD *)v29 )
      (***(void (__fastcall ****)(_QWORD, __int64))v29)(*(_QWORD *)v29, 1);
    WakeAllConditionVariable((PCONDITION_VARIABLE)v22 + 13);
    if ( (*((_DWORD *)v22 + 23))-- == 1 )
    {
      *((_DWORD *)v22 + 22) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)v22 + 4);
    }
    std::string::~string(Buf1);
    v28 = (volatile signed __int32 *)*((_QWORD *)&v30 + 1);
    if ( *((_QWORD *)&v30 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v30 + 1) + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
        if ( !_InterlockedDecrement(v28 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
      }
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xAEC,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\core\\Core.cpp",
      v27);
  }
}

```

## disassembly

```asm
0x180031fe8  mov     [rsp+arg_8], rbx
0x180031fed  mov     [rsp+arg_10], rsi
0x180031ff2  push    rdi
0x180031ff3  push    r13
0x180031ff5  push    r14
0x180031ff7  sub     rsp, 0C0h
0x180031ffe  mov     rax, cs:__security_cookie
0x180032005  xor     rax, rsp
0x180032008  mov     [rsp+0D8h+var_28], rax
0x180032010  mov     rsi, rcx
0x180032013  xorps   xmm0, xmm0
0x180032016  movups  [rsp+0D8h+var_B0], xmm0
0x18003201b  lea     rdx, [rsp+0D8h+var_B0]
0x180032020  mov     rcx, [rcx+360h]
0x180032027  call    ?GetDOWorkingDir@CGlobalConfigManager@@QEAA?AV?$shared_ptr@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAW4_ConfigProviderType@@@Z; CGlobalConfigManager::GetDOWorkingDir(_ConfigProviderType *)
0x18003202c  nop
0x18003202d  mov     rdx, qword ptr [rsp+0D8h+var_B0]
0x180032032  cmp     qword ptr [rdx+18h], 0Fh
0x180032037  jbe     short loc_18003203C
0x180032039  mov     rdx, [rdx]; char *
0x18003203c  mov     rcx, rsi; this
0x18003203f  call    ?_DoScanForOrphanFiles@CCore@@AEAAXPEBD@Z; CCore::_DoScanForOrphanFiles(char const *)
0x180032044  xorps   xmm0, xmm0
0x180032047  movups  xmmword ptr [rsp+0D8h+Buf1], xmm0
0x18003204f  mov     [rsp+0D8h+Size], 0
0x18003205b  mov     [rsp+0D8h+var_30], 0Fh
0x180032067  mov     byte ptr [rsp+0D8h+Buf1], 0
0x18003206f  lea     rcx, [rsp+0D8h+Buf1]; void *
0x180032077  call    ?GetDefaultCachePath@CPersistenceLocation@@SAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CPersistenceLocation::GetDefaultCachePath(std::string &)
0x18003207c  test    eax, eax
0x18003207e  js      short loc_1800320EA
0x180032080  mov     rdx, qword ptr [rsp+0D8h+var_B0]
0x180032085  mov     rax, [rdx+10h]
0x180032089  cmp     qword ptr [rdx+18h], 0Fh
0x18003208e  jbe     short loc_180032093
0x180032090  mov     rdx, [rdx]; Buf2
0x180032093  lea     rcx, [rsp+0D8h+Buf1]
0x18003209b  cmp     [rsp+0D8h+var_30], 0Fh
0x1800320a4  cmova   rcx, [rsp+0D8h+Buf1]; Buf1
0x1800320ad  mov     r8, [rsp+0D8h+Size]; Size
0x1800320b5  cmp     r8, rax
0x1800320b8  jnz     short loc_1800320C8
0x1800320ba  test    r8, r8
0x1800320bd  jz      short loc_1800320EA
0x1800320bf  call    memcmp
0x1800320c4  test    eax, eax
0x1800320c6  jz      short loc_1800320EA
0x1800320c8  lea     rdx, [rsp+0D8h+Buf1]
0x1800320d0  cmp     [rsp+0D8h+var_30], 0Fh
0x1800320d9  cmova   rdx, [rsp+0D8h+Buf1]; char *
0x1800320e2  mov     rcx, rsi; this
0x1800320e5  call    ?_DoScanForOrphanFiles@CCore@@AEAAXPEBD@Z; CCore::_DoScanForOrphanFiles(char const *)
0x1800320ea  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1??CleanupUnusedState@CCorePersistence@@SAXAEAVCCore@@@Z@JPEBD@std@@6B@; const std::_Func_impl_no_alloc<`CCorePersistence::CleanupUnusedState(CCore &)'::`2'::_lambda_1_,long,char const *>::`vftable'
0x1800320f1  mov     [rsp+0D8h+var_88], rax
0x1800320f6  mov     [rsp+0D8h+var_80], rsi
0x1800320fb  lea     rax, [rsp+0D8h+var_88]
0x180032100  mov     [rsp+0D8h+var_50], rax
0x180032108  lea     r8, [rsp+0D8h+var_88]
0x18003210d  lea     rdx, aSwarms; "Swarms"
0x180032114  mov     rcx, cs:?_shDOSubKey@CAppRegistryHive@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hKey
0x18003211b  call    ?RegEnumerateSubKeys@@YAXPEAUHKEY__@@PEBDAEBV?$function@$$A6AJPEBD@Z@std@@@Z; RegEnumerateSubKeys(HKEY__ *,char const *,std::function<long (char const *)> const &)
0x180032120  nop
0x180032121  mov     rcx, [rsp+0D8h+var_50]
0x180032129  test    rcx, rcx
0x18003212c  jz      short loc_180032145
0x18003212e  lea     rax, [rsp+0D8h+var_88]
0x180032133  cmp     rcx, rax
0x180032136  setnz   dl
0x180032139  mov     rax, [rcx]
0x18003213c  mov     rax, [rax+20h]
0x180032140  call    _guard_dispatch_icall
0x180032145  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x18003214a  lea     rbx, [rax+20h]
0x18003214e  cmp     qword ptr [rbx+18h], 0Fh
0x180032153  jbe     short loc_180032158
0x180032155  mov     rbx, [rbx]
0x180032158  lea     rdi, off_18017E110; "CountryCode_saved"
0x18003215f  mov     r13, 0FFFFFFFF80000003h
0x180032166  lea     rax, ?_fUsingPrivateHive@CAppRegistryHive@@0_NA; bool CAppRegistryHive::_fUsingPrivateHive
0x18003216d  cmp     rdi, rax
0x180032170  jz      short loc_18003219A
0x180032172  mov     r14, [rdi]
0x180032175  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x18003217a  mov     al, [rax+0A0h]
0x180032180  neg     al
0x180032182  sbb     rcx, rcx
0x180032185  add     rcx, r13; hKey
0x180032188  mov     r8, r14; lpValueName
0x18003218b  mov     rdx, rbx; lpSubKey
0x18003218e  call    cs:__imp_RegDeleteKeyValueA
0x180032194  add     rdi, 8
0x180032198  jmp     short loc_180032166
0x18003219a  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x18003219f  mov     rbx, rax
0x1800321a2  cmp     qword ptr [rax+18h], 0Fh
0x1800321a7  jbe     short loc_1800321AC
0x1800321a9  mov     rbx, [rax]
0x1800321ac  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x1800321b1  mov     al, [rax+0A0h]
0x1800321b7  neg     al
0x1800321b9  sbb     rcx, rcx
0x1800321bc  add     rcx, r13; hKey
0x1800321bf  lea     r8, aUploadlimitmon; "UploadLimitMonthID"
0x1800321c6  mov     rdx, rbx; lpSubKey
0x1800321c9  call    cs:__imp_RegDeleteKeyValueA
0x1800321cf  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x1800321d4  mov     rbx, rax
0x1800321d7  cmp     qword ptr [rax+18h], 0Fh
0x1800321dc  jbe     short loc_1800321E1
0x1800321de  mov     rbx, [rax]
0x1800321e1  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x1800321e6  mov     al, [rax+0A0h]
0x1800321ec  neg     al
0x1800321ee  sbb     rcx, rcx
0x1800321f1  add     rcx, r13; hKey
0x1800321f4  lea     r8, aUploadlimitsta; "UploadLimitState"
0x1800321fb  mov     rdx, rbx; lpSubKey
0x1800321fe  call    cs:__imp_RegDeleteKeyValueA
0x180032204  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x180032209  mov     rbx, rax
0x18003220c  cmp     qword ptr [rax+18h], 0Fh
0x180032211  jbe     short loc_180032216
0x180032213  mov     rbx, [rax]
0x180032216  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x18003221b  mov     al, [rax+0A0h]
0x180032221  neg     al
0x180032223  sbb     rcx, rcx
0x180032226  add     rcx, r13; hKey
0x180032229  lea     r8, aPeerid; "PeerId"
0x180032230  mov     rdx, rbx; lpSubKey
0x180032233  call    cs:__imp_RegDeleteKeyValueA
0x180032239  mov     [rsp+0D8h+var_B8], 0
0x180032241  lea     rdx, [rsp+0D8h+var_B8]; unsigned int *
0x180032246  mov     rcx, [rsi+360h]; this
0x18003224d  call    ?GetMaxCacheAgeSecs@CGlobalConfigManager@@QEBA_NAEAIPEAW4_ConfigProviderType@@@Z; CGlobalConfigManager::GetMaxCacheAgeSecs(uint &,_ConfigProviderType *)
0x180032252  mov     r14, [rsi+8]
0x180032256  mov     eax, [rsp+0D8h+var_B8]
0x18003225a  mov     ecx, 93A80h
0x18003225f  cmp     eax, ecx
0x180032261  cmova   eax, ecx
0x180032264  mov     ebx, eax
0x180032266  xorps   xmm0, xmm0
0x180032269  movups  [rsp+0D8h+var_98], xmm0
0x18003226e  lea     rdi, [r14+10h]
0x180032272  mov     qword ptr [rsp+0D8h+var_98], rdi
0x180032277  mov     byte ptr [rsp+0D8h+var_98+8], 0
0x18003227c  mov     rcx, rdi
0x18003227f  call    mtx_do_lock
0x180032284  test    eax, eax
0x180032286  jnz     loc_18003238F
0x18003228c  mov     eax, [rdi+4Ch]
0x18003228f  cmp     eax, 7FFFFFFFh
0x180032294  jz      loc_180032399
0x18003229a  mov     byte ptr [rsp+0D8h+var_98+8], 1
0x18003229f  imul    rax, rbx, 3E8h
0x1800322a6  mov     [rsp+0D8h+var_A0], rax
0x1800322ab  mov     ecx, 18h; Size
0x1800322b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800322b5  mov     [rax+8], rsi
0x1800322b9  lea     rcx, ??_7?$CTaskImpl@V_lambda_1_@?2??_ScanForOrphanFiles@CCore@@AEAAXXZ@@CTaskQueue@@6B@; const CTaskQueue::CTaskImpl<`CCore::_ScanForOrphanFiles(void)'::`3'::_lambda_1_>::`vftable'
0x1800322c0  mov     [rax], rcx
0x1800322c3  mov     [rax+10h], rsi
0x1800322c7  mov     qword ptr [rsp+0D8h+var_B8], rax
0x1800322cc  lea     r8, [rsp+0D8h+var_A0]
0x1800322d1  lea     rdx, [rsp+0D8h+var_B8]
0x1800322d6  mov     rcx, r14
0x1800322d9  call    ?_Add@CTaskQueue@@AEAAX$$QEAV?$unique_ptr@VTask@CTaskQueue@@U?$default_delete@VTask@CTaskQueue@@@std@@@std@@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@3@@Z; CTaskQueue::_Add(std::unique_ptr<CTaskQueue::Task> &&,std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x1800322de  nop
0x1800322df  mov     rcx, qword ptr [rsp+0D8h+var_B8]
0x1800322e4  test    rcx, rcx
0x1800322e7  jz      short loc_1800322F9
0x1800322e9  mov     rax, [rcx]
0x1800322ec  mov     edx, 1
0x1800322f1  mov     rax, [rax]
0x1800322f4  call    _guard_dispatch_icall
0x1800322f9  lea     rcx, [r14+68h]; ConditionVariable
0x1800322fd  call    cs:__imp_WakeAllConditionVariable
0x180032303  nop
0x180032304  or      esi, 0FFFFFFFFh
0x180032307  add     [rdi+4Ch], esi
0x18003230a  jnz     short loc_18003231A
0x18003230c  mov     [rdi+48h], esi
0x18003230f  lea     rcx, [rdi+10h]; SRWLock
0x180032313  call    cs:__imp_ReleaseSRWLockExclusive
0x180032319  nop
0x18003231a  lea     rcx, [rsp+0D8h+Buf1]; void *
0x180032322  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180032327  nop
0x180032328  mov     rbx, qword ptr [rsp+0D8h+var_B0+8]
0x18003232d  test    rbx, rbx
0x180032330  jz      short loc_180032366
0x180032332  mov     eax, esi
0x180032334  lock xadd [rbx+8], eax
0x180032339  add     eax, esi
0x18003233b  jnz     short loc_180032366
0x18003233d  mov     rax, [rbx]
0x180032340  mov     rcx, rbx
0x180032343  mov     rax, [rax]
0x180032346  call    _guard_dispatch_icall
0x18003234b  mov     eax, esi
0x18003234d  lock xadd [rbx+0Ch], eax
0x180032352  add     eax, esi
0x180032354  jnz     short loc_180032366
0x180032356  mov     rax, [rbx]
0x180032359  mov     rcx, rbx
0x18003235c  mov     rax, [rax+8]
0x180032360  call    _guard_dispatch_icall
0x180032365  nop
0x180032366  mov     rcx, [rsp+0D8h+var_28]
0x18003236e  xor     rcx, rsp; StackCookie
0x180032371  call    __security_check_cookie
0x180032376  lea     r11, [rsp+0D8h+var_18]
0x18003237e  mov     rbx, [r11+28h]
0x180032382  mov     rsi, [r11+30h]
0x180032386  mov     rsp, r11
0x180032389  pop     r14
0x18003238b  pop     r13
0x18003238d  pop     rdi
0x18003238e  retn
0x18003238f  mov     ecx, 5; int
0x180032394  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180032399  dec     eax
0x18003239b  mov     [rdi+4Ch], eax
0x18003239e  mov     ecx, 6; int
0x1800323a3  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
