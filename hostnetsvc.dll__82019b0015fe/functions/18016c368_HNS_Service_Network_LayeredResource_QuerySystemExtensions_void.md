# HNS::Service::Network::LayeredResource::QuerySystemExtensions(void)

- ea: `0x18016c368`
- end: `0x18016c76e`
- name: `?QuerySystemExtensions@LayeredResource@Network@Service@HNS@@AEAAXXZ`
- size: `1030`
- prototype: `void __fastcall(HNS::Service::Network::LayeredResource *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180168210`

## callees

- `0x18005f0c0`
- `0x1800666b4`
- `0x1800677fc`
- `0x180067c00`
- `0x18006c530`
- `0x18007cbc8`
- `0x18007f21c`
- `0x1800b672c`
- `0x1800d2414`
- `0x1800d4834`
- `0x1800fbd60`
- `0x1800fbeb4`
- `0x18016c368`
- `0x18019a860`
- `0x18019aca0`
- `0x18019ad20`
- `0x18019ad7c`
- `0x18019dbb4`
- `0x18019dcb8`
- `0x18019dcfc`
- `0x18019de74`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18016c4f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18016c4f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016c4db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016c4db`
- `NetMgmtIF!NetMgmtSwitchExtensionEnumerate` at `0x18016c4b3`
- `NetMgmtIF!NetMgmtSwitchExtensionEnumerate` at `0x18016c4b3`
- `NetMgmtIF!NetMgmtSwitchExtensionFree` at `0x18016c4e6`
- `NetMgmtIF!NetMgmtSwitchExtensionFree` at `0x18016c707`

## string_xrefs

- `0x18016c744`: `onecore\vm\dv\net\hns\service\entity\layer\layeredresource.cpp`
- `0x18016c75c`: `onecore\vm\dv\net\hns\service\entity\layer\layeredresource.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall HNS::Service::Network::LayeredResource::QuerySystemExtensions(
        HNS::Service::Network::LayeredResource *this)
{
  char *v2; // rdi
  RTL_SRWLOCK *i; // rbx
  HNSObjectList *v4; // rcx
  __int64 v5; // rax
  _QWORD *v6; // rcx
  unsigned int v7; // eax
  __int64 v8; // r15
  _QWORD *v9; // rsi
  __int64 v10; // r14
  DWORD LastError; // ebx
  __int64 v12; // r15
  unsigned int j; // esi
  __int64 v14; // rbx
  unsigned __int64 v15; // r8
  bool v16; // bl
  HNSObject *v17; // r14
  RTL_SRWLOCK *v18; // rcx
  unsigned int v19; // [rsp+28h] [rbp-E0h]
  int v20; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+40h] [rbp-C8h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v23[3]; // [rsp+50h] [rbp-B8h] BYREF
  HNSObject *v24; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v25[3]; // [rsp+70h] [rbp-98h] BYREF
  GUID v26; // [rsp+88h] [rbp-80h] BYREF
  char v27; // [rsp+98h] [rbp-70h]
  __int128 v28; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v29; // [rsp+B8h] [rbp-50h]
  _OWORD v30[2]; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v31[4]; // [rsp+E8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]

  if ( !*((_QWORD *)this + 154) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x286,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\layer\\layeredresource.cpp",
      (const char *)0x803B0004LL,
      v19);
  v2 = (char *)this + 1456;
  if ( (unsigned int)HNSObject::PropertyExists(*((_QWORD *)this + 189), (char *)this + 1456) )
  {
    v5 = HNSObjectList::Create(&SRWLock);
    *(_OWORD *)&v23[1] = *((_OWORD *)this + 93);
    HNSObject::Set<wil::com_ptr_t<HNSObjectList,wil::err_exception_policy>>(
      *((_QWORD *)this + 189),
      (char *)this + 1456,
      v5,
      *((unsigned int *)this + 376),
      &v23[1]);
    v4 = (HNSObjectList *)SRWLock;
    if ( !SRWLock )
      goto LABEL_10;
    goto LABEL_9;
  }
  Property<wil::com_ptr_t<HNSObjectList,wil::err_exception_policy>>::get((char *)this + 1456, &SRWLock);
  for ( i = SRWLock; HNSObjectList::Count(i); HNSObjectList::RemoveObjectIndex(i, 0, (struct _GUID *)&v23[1]) )
    *(GUID *)&v23[1] = GUID_NULL;
  if ( i )
  {
    v4 = (HNSObjectList *)i;
LABEL_9:
    HNSObjectList::Release(v4);
  }
LABEL_10:
  v23[0] = 0;
  LODWORD(v21) = 0;
  HNSObject::Get<_GUID>(*(_QWORD *)(*((_QWORD *)this + 154) + 1304LL), &v23[1], *((_QWORD *)this + 154) + 1248LL);
  GuidToString(v31, &v23[1], 0);
  *(_QWORD *)&v26.Data1 = v23;
  *(_QWORD *)v26.Data4 = 0;
  v27 = 1;
  v6 = v31;
  if ( v31[3] > 7u )
    v6 = (_QWORD *)v31[0];
  v7 = NetMgmtSwitchExtensionEnumerate(v6, &v21, v26.Data4);
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2AA,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\layer\\layeredresource.cpp",
      (const char *)v7,
      v19);
  if ( v27 )
  {
    v8 = *(_QWORD *)v26.Data4;
    v9 = *(_QWORD **)&v26.Data1;
    v10 = **(_QWORD **)&v26.Data1;
    if ( **(_QWORD **)&v26.Data1 )
    {
      LastError = GetLastError();
      ((void (__fastcall *)(__int64))NetMgmtSwitchExtensionFree)(v10);
      SetLastError(LastError);
    }
    *v9 = v8;
  }
  v12 = v23[0];
  for ( j = 0; j < (unsigned int)v21; ++j )
  {
    v14 = v12 + 3180LL * j;
    v26 = *(GUID *)(v14 + 2816);
    memset(v30, 0, sizeof(v30));
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)(v14 + 2 * v15) );
    std::wstring::_Construct<1,unsigned short const *>((char **)v30, (const void *)(v12 + 3180LL * j), v15);
    v16 = *(_BYTE *)(v14 + 2853) != 0;
    HNSObject::Create(&v24);
    v17 = v24;
    v28 = 0;
    v29 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&v28, L"Id", 2u);
    *(GUID *)&v25[1] = GUID_NULL;
    HNSObject::Set<_GUID>(v17, &v28, &v26, 18, &v25[1]);
    std::wstring::~wstring(&v28);
    v28 = 0;
    v29 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&v28, L"Name", 4u);
    v26 = GUID_NULL;
    HNSObject::Set<std::wstring>(v17, &v28, v30, 18, &v26);
    std::wstring::~wstring(&v28);
    v28 = 0;
    v29 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&v28, L"IsEnabled", 9u);
    LOBYTE(v20) = v16;
    v26 = GUID_NULL;
    HNSObject::Set<unsigned char>(v17, &v28, &v20, 18, &v26);
    std::wstring::~wstring(&v28);
    v18 = *(RTL_SRWLOCK **)Property<wil::com_ptr_t<HNSObjectList,wil::err_exception_policy>>::get(v2, &v23[1]);
    SRWLock = (PSRWLOCK)v17;
    if ( v17 )
      _InterlockedIncrement((volatile signed __int32 *)v17 + 4);
    v26 = GUID_NULL;
    HNSObjectList::AddObject(v18);
    if ( v23[1] )
      HNSObjectList::Release((HNSObjectList *)v23[1]);
    if ( v17 )
      HNSObject::Release(v17);
    std::wstring::~wstring(v30);
  }
  std::wstring::~wstring(v31);
  if ( v23[0] )
    ((void (*)(void))NetMgmtSwitchExtensionFree)();
}

```

## disassembly

```asm
0x18016c368  mov     rax, rsp
0x18016c36b  mov     [rax+10h], rbx
0x18016c36f  mov     [rax+18h], rsi
0x18016c373  push    rbp
0x18016c374  push    rdi
0x18016c375  push    r12
0x18016c377  push    r14
0x18016c379  push    r15
0x18016c37b  lea     rbp, [rax-48h]
0x18016c37f  sub     rsp, 120h
0x18016c386  movaps  xmmword ptr [rax-38h], xmm6
0x18016c38a  mov     rax, cs:__security_cookie
0x18016c391  xor     rax, rsp
0x18016c394  mov     [rbp+40h+var_40], rax
0x18016c398  mov     rsi, rcx
0x18016c39b  mov     rcx, [rbp+48h]; this
0x18016c39f  xor     r12d, r12d
0x18016c3a2  cmp     [rsi+4D0h], r12
0x18016c3a9  jz      loc_18016C756
0x18016c3af  lea     rdi, [rsi+5B0h]
0x18016c3b6  mov     rdx, rdi
0x18016c3b9  mov     rcx, [rdi+38h]
0x18016c3bd  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x18016c3c2  test    eax, eax
0x18016c3c4  jnz     short loc_18016C40D
0x18016c3c6  lea     rdx, [rsp+140h+SRWLock]
0x18016c3cb  mov     rcx, rdi
0x18016c3ce  call    ?get@?$Property@V?$com_ptr_t@VHNSObjectList@@Uerr_exception_policy@wil@@@wil@@@@QEBA?BV?$com_ptr_t@VHNSObjectList@@Uerr_exception_policy@wil@@@wil@@XZ; Property<wil::com_ptr_t<HNSObjectList,wil::err_exception_policy>>::get(void)
0x18016c3d3  nop
0x18016c3d4  mov     rbx, [rsp+140h+SRWLock]
0x18016c3d9  jmp     short loc_18016C3F7
0x18016c3db  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18016c3e2  movdqu  xmmword ptr [rsp+140h+var_F8+8], xmm0
0x18016c3e8  lea     r8, [rsp+140h+var_F8+8]; struct _GUID
0x18016c3ed  xor     edx, edx; unsigned int
0x18016c3ef  mov     rcx, rbx; SRWLock
0x18016c3f2  call    ?RemoveObjectIndex@HNSObjectList@@QEAAXKU_GUID@@@Z; HNSObjectList::RemoveObjectIndex(ulong,_GUID)
0x18016c3f7  mov     rcx, rbx; SRWLock
0x18016c3fa  call    ?Count@HNSObjectList@@QEBAKXZ; HNSObjectList::Count(void)
0x18016c3ff  test    eax, eax
0x18016c401  jnz     short loc_18016C3DB
0x18016c403  test    rbx, rbx
0x18016c406  jz      short loc_18016C44F
0x18016c408  mov     rcx, rbx
0x18016c40b  jmp     short loc_18016C44A
0x18016c40d  lea     rcx, [rsp+140h+SRWLock]
0x18016c412  call    ?Create@HNSObjectList@@SA?AV?$com_ptr_t@VHNSObjectList@@Uerr_exception_policy@wil@@@wil@@XZ; HNSObjectList::Create(void)
0x18016c417  nop
0x18016c418  movups  xmm0, xmmword ptr [rdi+20h]
0x18016c41c  movdqu  xmmword ptr [rsp+140h+var_F8+8], xmm0
0x18016c422  lea     rcx, [rsp+140h+var_F8+8]
0x18016c427  mov     qword ptr [rsp+140h+var_120], rcx; unsigned int
0x18016c42c  mov     r9d, [rdi+30h]
0x18016c430  mov     r8, rax
0x18016c433  mov     rdx, rdi
0x18016c436  mov     rcx, [rdi+38h]
0x18016c43a  call    ??$Set@V?$com_ptr_t@VHNSObjectList@@Uerr_exception_policy@wil@@@wil@@@HNSObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$com_ptr_t@VHNSObjectList@@Uerr_exception_policy@wil@@@wil@@KU_GUID@@@Z; HNSObject::Set<wil::com_ptr_t<HNSObjectList,wil::err_exception_policy>>(std::wstring const &,wil::com_ptr_t<HNSObjectList,wil::err_exception_policy> const &,ulong,_GUID)
0x18016c43f  nop
0x18016c440  mov     rcx, [rsp+140h+SRWLock]; this
0x18016c445  test    rcx, rcx
0x18016c448  jz      short loc_18016C44F
0x18016c44a  call    ?Release@HNSObjectList@@QEAAKXZ; HNSObjectList::Release(void)
0x18016c44f  mov     qword ptr [rsp+140h+var_F8], r12
0x18016c454  mov     dword ptr [rsp+140h+var_108], r12d
0x18016c459  mov     rcx, [rsi+4D0h]
0x18016c460  lea     r8, [rcx+4E0h]
0x18016c467  lea     rdx, [rsp+140h+var_F8+8]
0x18016c46c  mov     rcx, [rcx+518h]
0x18016c473  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x18016c478  nop
0x18016c479  xor     r8d, r8d
0x18016c47c  lea     rdx, [rsp+140h+var_F8+8]
0x18016c481  lea     rcx, [rbp+40h+var_60]
0x18016c485  call    ?GuidToString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; GuidToString(_GUID const &,bool)
0x18016c48a  nop
0x18016c48b  lea     rax, [rsp+140h+var_F8]
0x18016c490  mov     qword ptr [rbp+40h+var_C0], rax
0x18016c494  mov     qword ptr [rbp+40h+var_C0+8], r12
0x18016c498  mov     [rbp+40h+var_B0], 1
0x18016c49c  lea     rcx, [rbp+40h+var_60]
0x18016c4a0  cmp     [rbp+40h+var_48], 7
0x18016c4a5  cmova   rcx, [rbp+40h+var_60]
0x18016c4aa  lea     r8, [rbp+40h+var_C0+8]
0x18016c4ae  lea     rdx, [rsp+140h+var_108]
0x18016c4b3  call    cs:__imp_NetMgmtSwitchExtensionEnumerate
0x18016c4b9  mov     rcx, [rbp+48h]; this
0x18016c4bd  test    eax, eax
0x18016c4bf  jnz     loc_18016C741
0x18016c4c5  cmp     [rbp+40h+var_B0], r12b
0x18016c4c9  jz      short loc_18016C4FE
0x18016c4cb  mov     r15, qword ptr [rbp+40h+var_C0+8]
0x18016c4cf  mov     rsi, qword ptr [rbp+40h+var_C0]
0x18016c4d3  mov     r14, [rsi]
0x18016c4d6  test    r14, r14
0x18016c4d9  jz      short loc_18016C4FB
0x18016c4db  call    cs:__imp_GetLastError
0x18016c4e1  mov     ebx, eax
0x18016c4e3  mov     rcx, r14
0x18016c4e6  mov     rax, cs:__imp_NetMgmtSwitchExtensionFree
0x18016c4ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016c4f2  nop
0x18016c4f3  mov     ecx, ebx; dwErrCode
0x18016c4f5  call    cs:__imp_SetLastError
0x18016c4fb  mov     [rsi], r15
0x18016c4fe  mov     r15, qword ptr [rsp+140h+var_F8]
0x18016c503  mov     esi, r12d
0x18016c506  cmp     dword ptr [rsp+140h+var_108], r12d
0x18016c50b  jbe     loc_18016C6F3
0x18016c511  mov     eax, esi
0x18016c513  imul    rbx, rax, 0C6Ch
0x18016c51a  add     rbx, r15
0x18016c51d  movups  xmm0, xmmword ptr [rbx+0B00h]
0x18016c524  movdqu  [rbp+40h+var_C0], xmm0
0x18016c529  xorps   xmm1, xmm1
0x18016c52c  movups  [rbp+40h+var_80], xmm1
0x18016c530  xorps   xmm0, xmm0
0x18016c533  movdqu  [rbp+40h+var_70], xmm0
0x18016c538  or      r8, 0FFFFFFFFFFFFFFFFh
0x18016c53c  inc     r8
0x18016c53f  cmp     [rbx+r8*2], r12w
0x18016c544  jnz     short loc_18016C53C
0x18016c546  mov     rdx, rbx
0x18016c549  lea     rcx, [rbp+40h+var_80]
0x18016c54d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18016c552  nop
0x18016c553  cmp     [rbx+0B25h], r12b
0x18016c55a  setnz   bl
0x18016c55d  lea     rcx, [rsp+140h+var_E0]
0x18016c562  call    ?Create@HNSObject@@SA?AV?$com_ptr_t@VHNSObject@@Uerr_exception_policy@wil@@@wil@@XZ; HNSObject::Create(void)
0x18016c567  nop
0x18016c568  mov     r14, [rsp+140h+var_E0]
0x18016c56d  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18016c574  xorps   xmm0, xmm0
0x18016c577  movups  [rbp+40h+var_A0], xmm0
0x18016c57b  xorps   xmm1, xmm1
0x18016c57e  movdqu  [rbp+40h+var_90], xmm1
0x18016c583  mov     r8d, 2
0x18016c589  lea     rdx, aId; "Id"
0x18016c590  lea     rcx, [rbp+40h+var_A0]
0x18016c594  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18016c599  nop
0x18016c59a  movdqu  xmmword ptr [rsp+140h+var_D8+8], xmm6
0x18016c5a0  lea     rax, [rsp+140h+var_D8+8]
0x18016c5a5  mov     qword ptr [rsp+140h+var_120], rax
0x18016c5aa  mov     r9d, 12h
0x18016c5b0  lea     r8, [rbp+40h+var_C0]
0x18016c5b4  lea     rdx, [rbp+40h+var_A0]
0x18016c5b8  mov     rcx, r14
0x18016c5bb  call    ??$Set@U_GUID@@@HNSObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@KU3@@Z; HNSObject::Set<_GUID>(std::wstring const &,_GUID const &,ulong,_GUID)
0x18016c5c0  nop
0x18016c5c1  lea     rcx, [rbp+40h+var_A0]; void *
0x18016c5c5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18016c5ca  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18016c5d1  xorps   xmm0, xmm0
0x18016c5d4  movups  [rbp+40h+var_A0], xmm0
0x18016c5d8  xorps   xmm1, xmm1
0x18016c5db  movdqu  [rbp+40h+var_90], xmm1
0x18016c5e0  mov     r8d, 4
0x18016c5e6  lea     rdx, aName; "Name"
0x18016c5ed  lea     rcx, [rbp+40h+var_A0]
0x18016c5f1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18016c5f6  nop
0x18016c5f7  movdqu  [rbp+40h+var_C0], xmm6
0x18016c5fc  lea     rax, [rbp+40h+var_C0]
0x18016c600  mov     qword ptr [rsp+140h+var_120], rax
0x18016c605  mov     r9d, 12h
0x18016c60b  lea     r8, [rbp+40h+var_80]
0x18016c60f  lea     rdx, [rbp+40h+var_A0]
0x18016c613  mov     rcx, r14
0x18016c616  call    ??$Set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@HNSObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KU_GUID@@@Z; HNSObject::Set<std::wstring>(std::wstring const &,std::wstring const &,ulong,_GUID)
0x18016c61b  nop
0x18016c61c  lea     rcx, [rbp+40h+var_A0]; void *
0x18016c620  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18016c625  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18016c62c  xorps   xmm0, xmm0
0x18016c62f  movups  [rbp+40h+var_A0], xmm0
0x18016c633  xorps   xmm1, xmm1
0x18016c636  movdqu  [rbp+40h+var_90], xmm1
0x18016c63b  mov     r8d, 9
0x18016c641  lea     rdx, aIsenabled; "IsEnabled"
0x18016c648  lea     rcx, [rbp+40h+var_A0]
0x18016c64c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18016c651  nop
0x18016c652  mov     byte ptr [rsp+140h+var_110], bl
0x18016c656  movdqu  [rbp+40h+var_C0], xmm6
0x18016c65b  lea     rax, [rbp+40h+var_C0]
0x18016c65f  mov     qword ptr [rsp+140h+var_120], rax
0x18016c664  mov     r9d, 12h
0x18016c66a  lea     r8, [rsp+140h+var_110]
0x18016c66f  lea     rdx, [rbp+40h+var_A0]
0x18016c673  mov     rcx, r14
0x18016c676  call    ??$Set@E@HNSObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBEKU_GUID@@@Z; HNSObject::Set<uchar>(std::wstring const &,uchar const &,ulong,_GUID)
0x18016c67b  nop
0x18016c67c  lea     rcx, [rbp+40h+var_A0]; void *
0x18016c680  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18016c685  lea     rdx, [rsp+140h+var_F8+8]
0x18016c68a  mov     rcx, rdi
0x18016c68d  call    ?get@?$Property@V?$com_ptr_t@VHNSObjectList@@Uerr_exception_policy@wil@@@wil@@@@QEBA?BV?$com_ptr_t@VHNSObjectList@@Uerr_exception_policy@wil@@@wil@@XZ; Property<wil::com_ptr_t<HNSObjectList,wil::err_exception_policy>>::get(void)
0x18016c692  nop
0x18016c693  mov     rcx, [rax]; SRWLock
0x18016c696  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18016c69d  mov     [rsp+140h+SRWLock], r14
0x18016c6a2  test    r14, r14
0x18016c6a5  jz      short loc_18016C6AC
0x18016c6a7  lock inc dword ptr [r14+10h]
0x18016c6ac  movdqu  [rbp+40h+var_C0], xmm0
0x18016c6b1  lea     r8, [rbp+40h+var_C0]
0x18016c6b5  lea     rdx, [rsp+140h+SRWLock]
0x18016c6ba  call    ?AddObject@HNSObjectList@@QEAAXV?$com_ptr_t@VHNSObject@@Uerr_exception_policy@wil@@@wil@@U_GUID@@@Z; HNSObjectList::AddObject(wil::com_ptr_t<HNSObject,wil::err_exception_policy>,_GUID)
0x18016c6bf  nop
0x18016c6c0  mov     rcx, qword ptr [rsp+140h+var_F8+8]; this
0x18016c6c5  test    rcx, rcx
0x18016c6c8  jz      short loc_18016C6D0
0x18016c6ca  call    ?Release@HNSObjectList@@QEAAKXZ; HNSObjectList::Release(void)
0x18016c6cf  nop
0x18016c6d0  test    r14, r14
0x18016c6d3  jz      short loc_18016C6DE
0x18016c6d5  mov     rcx, r14; this
0x18016c6d8  call    ?Release@HNSObject@@QEAAKXZ; HNSObject::Release(void)
0x18016c6dd  nop
0x18016c6de  lea     rcx, [rbp+40h+var_80]; void *
0x18016c6e2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18016c6e7  inc     esi
0x18016c6e9  cmp     esi, dword ptr [rsp+140h+var_108]
0x18016c6ed  jb      loc_18016C511
0x18016c6f3  lea     rcx, [rbp+40h+var_60]; void *
0x18016c6f7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18016c6fc  nop
0x18016c6fd  mov     rcx, qword ptr [rsp+140h+var_F8]
0x18016c702  test    rcx, rcx
0x18016c705  jz      short loc_18016C714
0x18016c707  mov     rax, cs:__imp_NetMgmtSwitchExtensionFree
0x18016c70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016c713  nop
0x18016c714  mov     rcx, [rbp+40h+var_40]
0x18016c718  xor     rcx, rsp; StackCookie
0x18016c71b  call    __security_check_cookie
0x18016c720  lea     r11, [rsp+140h+var_20]
0x18016c728  mov     rbx, [r11+38h]
0x18016c72c  mov     rsi, [r11+40h]
0x18016c730  movaps  xmm6, xmmword ptr [r11-10h]
0x18016c735  mov     rsp, r11
0x18016c738  pop     r15
0x18016c73a  pop     r14
0x18016c73c  pop     r12
0x18016c73e  pop     rdi
0x18016c73f  pop     rbp
0x18016c740  retn
0x18016c741  mov     r9d, eax; char *
0x18016c744  lea     r8, aOnecoreVmDvNet_162; "onecore\\vm\\dv\\net\\hns\\service\\ent"...
0x18016c74b  mov     edx, 2AAh; void *
0x18016c750  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18016c756  mov     r9d, 803B0004h; char *
0x18016c75c  lea     r8, aOnecoreVmDvNet_162; "onecore\\vm\\dv\\net\\hns\\service\\ent"...
0x18016c763  mov     edx, 286h; void *
0x18016c768  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
