# helium::Container::DestroyJob(void *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,helium::ReasonDestroyed,std::optional<long>,DesktopAppXProvider::TryGetViableRunningHeliumContainer *)

- ea: `0x18006eff8`
- end: `0x18006f3b7`
- name: `?DestroyJob@Container@helium@@SAXPEAXPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4ReasonDestroyed@2@V?$optional@J@4@PEAVTryGetViableRunningHeliumContainer@DesktopAppXProvider@@@Z`
- size: `959`
- prototype: `__int64 __usercall@<rax>(struct _GUID *retstr@<rcx>, __int64, __int64)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180054f80`
- `0x180059b7c`
- `0x18006ec7c`

## callees

- `0x1800053a0`
- `0x180010a84`
- `0x1800202bc`
- `0x180048f18`
- `0x180048f40`
- `0x180052af8`
- `0x18006c420`
- `0x18006c484`
- `0x18006c67c`
- `0x18006eff8`
- `0x1800718c0`
- `0x180096668`
- `0x1800969dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006f29b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006f29b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006f361`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006f361`
- `ntdll!RtlNtStatusToDosError` at `0x18006f232`
- `ntdll!RtlNtStatusToDosError` at `0x18006f232`
- `ntdll!NtMakeTemporaryObject` at `0x18006f152`
- `ntdll!NtMakeTemporaryObject` at `0x18006f152`
- `ntdll!EtwEventUnregister` at `0x18006f202`
- `ntdll!EtwEventUnregister` at `0x18006f202`
- `ntdll!EtwEventWrite` at `0x18006f1f1`
- `ntdll!EtwEventWrite` at `0x18006f1f1`
- `ntdll!EtwEventRegister` at `0x18006f1c5`
- `ntdll!EtwEventRegister` at `0x18006f1c5`
- `container!WcCleanupContainer` at `0x18006f119`
- `container!WcCleanupContainer` at `0x18006f119`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006f096`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006f096`

## string_xrefs

- `0x18006f21d`: `onecore\base\appmodel\execmodel\desktopappx\lib\ManifestedETWHelpers.h`
- `0x18006f38c`: `onecore\internal\com\inc\combase\ComGuid.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall helium::Container::DestroyJob(
        struct _GUID *retstr,
        __int64 a2,
        void *a3,
        int a4,
        __int64 a5,
        __int64 a6)
{
  int v6; // r14d
  struct _GUID *v7; // rdi
  const char *v8; // r9
  const char *v9; // r9
  int v10; // eax
  const char *v11; // r9
  NTSTATUS TemporaryObject; // eax
  NTSTATUS v13; // edi
  unsigned int v14; // eax
  signed int v15; // eax
  int v16; // ecx
  __int64 v17; // rcx
  __int64 *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 i; // rcx
  __int64 j; // rdx
  unsigned int v23; // [rsp+20h] [rbp-128h]
  __int64 v24; // [rsp+38h] [rbp-110h] BYREF
  __int128 v25; // [rsp+40h] [rbp-108h] BYREF
  NTSTATUS v26; // [rsp+50h] [rbp-F8h] BYREF
  OLECHAR *v27; // [rsp+58h] [rbp-F0h] BYREF
  struct _GUID *v28; // [rsp+60h] [rbp-E8h]
  __int64 v29; // [rsp+68h] [rbp-E0h] BYREF
  __int64 *v30; // [rsp+70h] [rbp-D8h] BYREF
  __int64 *v31; // [rsp+78h] [rbp-D0h]
  void *v32; // [rsp+80h] [rbp-C8h]
  GUID rguid; // [rsp+88h] [rbp-C0h] BYREF
  OLECHAR sz[40]; // [rsp+A0h] [rbp-A8h] BYREF
  _BYTE v35[32]; // [rsp+F0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  try
  {
    v6 = a4;
    v7 = retstr;
    v28 = retstr;
    v29 = a2;
    v32 = a3;
    LODWORD(v24) = a4;
    rguid = 0;
    rguid = *helium::GetContainerIdentifier((helium *)v35, retstr, a3);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\heliumcontainer.cpp",
      v8);
    v7 = v28;
    v6 = v24;
  }
  if ( StringFromGUID2(&rguid, sz, 39) != 39 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecore\\internal\\com\\inc\\combase\\ComGuid.hpp",
      v9);
  try
  {
    v27 = sz;
    LODWORD(v25) = v6;
    *(_QWORD *)((char *)&v25 + 4) = a5;
    HIDWORD(v25) = 0;
    v24 = 0x1100000012LL;
    v30 = &v24;
    v31 = (__int64 *)&v25;
    ScopedPrivileges::Take(v35, &v30);
    v10 = WcCleanupContainer(v7, 0);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xEB,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\heliumcontainer.cpp",
        (const char *)(unsigned int)v10,
        v23);
    ImpersonationReverter::~ImpersonationReverter((ImpersonationReverter *)v35);
  }
  catch ( ... )
  {
    HIDWORD(v25) = wil::details::in1diag3::Log_CaughtException(
                     retaddr,
                     (void *)0xF1,
                     (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\heliumcontainer.cpp",
                     v11);
    v7 = v28;
  }
  TemporaryObject = NtMakeTemporaryObject(v7);
  v13 = TemporaryObject;
  if ( TemporaryObject < 0 )
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0xF4,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\heliumcontainer.cpp",
      (const char *)(unsigned int)TemporaryObject,
      v23);
  v26 = v13;
  if ( v25 < 0 || v13 < 0 )
  {
    v15 = RtlNtStatusToDosError(v13);
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    LODWORD(v24) = v15;
    LogAppModelRuntimeEvent<long &,long &,unsigned short const * &,unsigned short const * &>(
      v16,
      (unsigned int)&v25 + 12,
      (unsigned int)&v24,
      (unsigned int)&v29,
      (__int64)&v27);
  }
  else
  {
    EtwLogging::details::CreateEventDataDescriptors<unsigned short const * &,unsigned short const * &>(v35, &v29, &v27);
    v24 = 0;
    if ( !(unsigned int)EtwEventRegister(&AppModelRuntimeProviderId, 0, 0, &v24) )
    {
      EtwEventWrite(v24, &AppModelDesktopAppXContainerDestroySuccess, 2, v35);
      v14 = EtwEventUnregister(v24);
      if ( v14 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x64,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\ManifestedETWHelpers.h",
          (const char *)v14,
          v23);
    }
  }
  if ( a6 )
    DesktopAppXProvider::TryGetViableRunningHeliumContainer::ExistingContainerShutdownDetails<unsigned short const * &,long &,long &>(
      &v27,
      (char *)&v25 + 12,
      &v26);
  AcquireSRWLockShared(&helium::Container::s_lockInstanceAndDiagnosticMaps);
  std::_Tree<std::_Tmap_traits<std::wstring,helium::Container *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,helium::Container *>>,1>>::equal_range(
    v17,
    &v30,
    v32);
  v18 = v30;
  while ( v18 != v31 )
  {
    v19 = v18[8];
    if ( *(_QWORD *)(v19 + 160) == *(_QWORD *)&rguid.Data1 && *(_QWORD *)(v19 + 168) == *(_QWORD *)rguid.Data4 )
    {
      if ( !*(_BYTE *)(v19 + 208) )
      {
        *(_OWORD *)(v19 + 188) = v25;
        *(_DWORD *)(v19 + 204) = v26;
        *(_BYTE *)(v19 + 208) = 1;
      }
      break;
    }
    v20 = v18[2];
    if ( *(_BYTE *)(v20 + 25) )
    {
      for ( i = v18[1]; !*(_BYTE *)(i + 25) && v18 == *(__int64 **)(i + 16); i = *(_QWORD *)(i + 8) )
        v18 = (__int64 *)i;
      v18 = (__int64 *)i;
    }
    else
    {
      v18 = (__int64 *)v18[2];
      for ( j = *(_QWORD *)v20; !*(_BYTE *)(j + 25); j = *(_QWORD *)j )
        v18 = (__int64 *)j;
    }
  }
  ReleaseSRWLockShared(&helium::Container::s_lockInstanceAndDiagnosticMaps);
}

```

## disassembly

```asm
0x18006eff8  mov     r11, rsp
0x18006effb  push    rsi
0x18006effc  push    rdi
0x18006effd  push    r14
0x18006efff  push    r15
0x18006f001  sub     rsp, 128h
0x18006f008  mov     rax, cs:__security_cookie
0x18006f00f  xor     rax, rsp
0x18006f012  mov     [rsp+148h+var_38], rax
0x18006f01a  mov     r14d, r9d
0x18006f01d  mov     rdi, rcx
0x18006f020  mov     [rsp+148h+var_E8], rcx
0x18006f025  mov     [rsp+148h+var_E0], rdx
0x18006f02a  mov     [rsp+148h+var_C8], r8
0x18006f032  mov     dword ptr [rsp+148h+var_110], r9d
0x18006f037  xorps   xmm0, xmm0
0x18006f03a  movups  xmmword ptr [rsp+148h+rguid.Data1], xmm0
0x18006f042  mov     [rsp+148h+var_118], 0
0x18006f047  mov     rdx, rcx; retstr
0x18006f04a  lea     rcx, [r11-58h]; this
0x18006f04e  call    ?GetContainerIdentifier@helium@@YA?AU_GUID@@PEAX@Z; helium::GetContainerIdentifier(void *)
0x18006f053  movups  xmm0, xmmword ptr [rax]
0x18006f056  movdqu  xmmword ptr [rsp+148h+rguid.Data1], xmm0
0x18006f05f  mov     sil, 1
0x18006f062  mov     [rsp+148h+var_118], sil
0x18006f067  jmp     short loc_18006F078
0x18006f069  mov     sil, [rsp+148h+var_118]
0x18006f06e  mov     rdi, [rsp+148h+var_E8]
0x18006f073  mov     r14d, dword ptr [rsp+148h+var_110]
0x18006f078  mov     r15, [rsp+148h]
0x18006f080  mov     r8d, 27h ; '''; cchMax
0x18006f086  lea     rdx, [rsp+148h+sz]; lpsz
0x18006f08e  lea     rcx, [rsp+148h+rguid]; rguid
0x18006f096  call    cs:__imp_StringFromGUID2
0x18006f09d  nop     dword ptr [rax+rax+00h]
0x18006f0a2  cmp     eax, 27h ; '''
0x18006f0a5  jnz     loc_18006F38C
0x18006f0ab  lea     rax, [rsp+148h+sz]
0x18006f0b3  lea     rcx, aNull; "<null>"
0x18006f0ba  test    sil, sil
0x18006f0bd  cmovz   rax, rcx
0x18006f0c1  mov     [rsp+148h+var_F0], rax
0x18006f0c6  mov     dword ptr [rsp+148h+var_108], r14d
0x18006f0cb  mov     rax, [rsp+148h+arg_20]
0x18006f0d3  mov     qword ptr [rsp+148h+var_108+4], rax
0x18006f0d8  and     dword ptr [rsp+148h+var_108+0Ch], 0
0x18006f0dd  mov     dword ptr [rsp+148h+var_110], 12h
0x18006f0e5  mov     dword ptr [rsp+148h+var_110+4], 11h
0x18006f0ed  lea     rax, [rsp+148h+var_110]
0x18006f0f2  mov     [rsp+148h+var_D8], rax
0x18006f0f7  lea     rax, [rsp+148h+var_108]
0x18006f0fc  mov     [rsp+148h+var_D0], rax
0x18006f101  lea     rdx, [rsp+148h+var_D8]
0x18006f106  lea     rcx, [rsp+148h+var_58]
0x18006f10e  call    ?Take@ScopedPrivileges@@SA?AU1@V?$initializer_list@K@std@@@Z; ScopedPrivileges::Take(std::initializer_list<ulong>)
0x18006f113  nop
0x18006f114  xor     edx, edx
0x18006f116  mov     rcx, rdi
0x18006f119  call    cs:__imp_WcCleanupContainer
0x18006f120  nop     dword ptr [rax+rax+00h]
0x18006f125  mov     rcx, [rsp+148h]; this
0x18006f12d  test    eax, eax
0x18006f12f  js      loc_18006F3A1
0x18006f135  lea     rcx, [rsp+148h+var_58]; this
0x18006f13d  call    ??1ImpersonationReverter@@QEAA@XZ; ImpersonationReverter::~ImpersonationReverter(void)
0x18006f142  nop
0x18006f143  jmp     short loc_18006F14F
0x18006f145  mov     sil, [rsp+148h+var_118]
0x18006f14a  mov     rdi, [rsp+148h+var_E8]
0x18006f14f  mov     rcx, rdi; Handle
0x18006f152  call    cs:__imp_NtMakeTemporaryObject
0x18006f159  nop     dword ptr [rax+rax+00h]
0x18006f15e  mov     edi, eax
0x18006f160  test    eax, eax
0x18006f162  jns     short loc_18006F180
0x18006f164  mov     rcx, [rsp+148h]; this
0x18006f16c  mov     r9d, eax; char *
0x18006f16f  lea     r8, aOnecoreBaseApp_52; "onecore\\base\\appmodel\\execmodel\\des"...
0x18006f176  mov     edx, 0F4h; void *
0x18006f17b  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18006f180  mov     [rsp+148h+var_F8], edi
0x18006f184  cmp     dword ptr [rsp+148h+var_108+0Ch], 0
0x18006f189  jl      loc_18006F230
0x18006f18f  test    edi, edi
0x18006f191  js      loc_18006F230
0x18006f197  lea     r8, [rsp+148h+var_F0]
0x18006f19c  lea     rdx, [rsp+148h+var_E0]
0x18006f1a1  lea     rcx, [rsp+148h+var_58]
0x18006f1a9  call    ??$CreateEventDataDescriptors@AEAPEBGAEAPEBG@details@EtwLogging@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@AEAPEBG1@Z; EtwLogging::details::CreateEventDataDescriptors<ushort const * &,ushort const * &>(_EVENT_DATA_DESCRIPTOR *,ushort const * &,ushort const * &)
0x18006f1ae  and     [rsp+148h+var_110], 0
0x18006f1b4  lea     r9, [rsp+148h+var_110]
0x18006f1b9  xor     r8d, r8d
0x18006f1bc  xor     edx, edx
0x18006f1be  lea     rcx, AppModelRuntimeProviderId
0x18006f1c5  call    cs:__imp_EtwEventRegister
0x18006f1cc  nop     dword ptr [rax+rax+00h]
0x18006f1d1  test    eax, eax
0x18006f1d3  jnz     loc_18006F26C
0x18006f1d9  lea     r9, [rsp+148h+var_58]
0x18006f1e1  lea     r8d, [rax+2]
0x18006f1e5  lea     rdx, AppModelDesktopAppXContainerDestroySuccess
0x18006f1ec  mov     rcx, [rsp+148h+var_110]
0x18006f1f1  call    cs:__imp_EtwEventWrite
0x18006f1f8  nop     dword ptr [rax+rax+00h]
0x18006f1fd  mov     rcx, [rsp+148h+var_110]
0x18006f202  call    cs:__imp_EtwEventUnregister
0x18006f209  nop     dword ptr [rax+rax+00h]
0x18006f20e  test    eax, eax
0x18006f210  jz      short loc_18006F26C
0x18006f212  mov     rcx, [rsp+148h]; this
0x18006f21a  mov     r9d, eax; char *
0x18006f21d  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\execmodel\\des"...
0x18006f224  mov     edx, 64h ; 'd'; void *
0x18006f229  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18006f22e  jmp     short loc_18006F26C
0x18006f230  mov     ecx, edi; Status
0x18006f232  call    cs:__imp_RtlNtStatusToDosError
0x18006f239  nop     dword ptr [rax+rax+00h]
0x18006f23e  test    eax, eax
0x18006f240  jle     short loc_18006F24A
0x18006f242  movzx   eax, ax
0x18006f245  or      eax, 80070000h
0x18006f24a  mov     dword ptr [rsp+148h+var_110], eax
0x18006f24e  lea     rax, [rsp+148h+var_F0]
0x18006f253  mov     qword ptr [rsp+148h+var_128], rax
0x18006f258  lea     r9, [rsp+148h+var_E0]
0x18006f25d  lea     r8, [rsp+148h+var_110]
0x18006f262  lea     rdx, [rsp+148h+var_108+0Ch]
0x18006f267  call    ??$LogAppModelRuntimeEvent@AEAJAEAJAEAPEBGAEAPEBG@@YAXAEBU_EVENT_DESCRIPTOR@@AEAJ1AEAPEBG2@Z; LogAppModelRuntimeEvent<long &,long &,ushort const * &,ushort const * &>(_EVENT_DESCRIPTOR const &,long &,long &,ushort const * &,ushort const * &)
0x18006f26c  cmp     [rsp+148h+arg_28], 0
0x18006f275  jz      short loc_18006F28B
0x18006f277  lea     r8, [rsp+148h+var_F8]
0x18006f27c  lea     rdx, [rsp+148h+var_108+0Ch]
0x18006f281  lea     rcx, [rsp+148h+var_F0]
0x18006f286  call    ??$ExistingContainerShutdownDetails@AEAPEBGAEAJAEAJ@TryGetViableRunningHeliumContainer@DesktopAppXProvider@@SAXAEAPEBGAEAJ1@Z; DesktopAppXProvider::TryGetViableRunningHeliumContainer::ExistingContainerShutdownDetails<ushort const * &,long &,long &>(ushort const * &,long &,long &)
0x18006f28b  test    sil, sil
0x18006f28e  jz      loc_18006F36D
0x18006f294  lea     rcx, ?s_lockInstanceAndDiagnosticMaps@Container@helium@@0Vsrwlock@wil@@A; SRWLock
0x18006f29b  call    cs:__imp_AcquireSRWLockShared
0x18006f2a2  nop     dword ptr [rax+rax+00h]
0x18006f2a7  mov     r8, [rsp+148h+var_C8]
0x18006f2af  lea     rdx, [rsp+148h+var_D8]
0x18006f2b4  call    ?equal_range@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@@std@@@std@@@std@@@std@@V12@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,helium::Container *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,helium::Container *>>,1>>::equal_range(std::wstring const &)
0x18006f2b9  mov     rax, [rsp+148h+var_D8]
0x18006f2be  mov     r8, qword ptr [rsp+148h+rguid.Data4]
0x18006f2c6  mov     r9, qword ptr [rsp+148h+rguid.Data1]
0x18006f2ce  cmp     rax, [rsp+148h+var_D0]
0x18006f2d3  jz      loc_18006F35A
0x18006f2d9  mov     rcx, [rax+40h]
0x18006f2dd  cmp     [rcx+0A0h], r9
0x18006f2e4  jnz     short loc_18006F2EF
0x18006f2e6  cmp     [rcx+0A8h], r8
0x18006f2ed  jz      short loc_18006F334
0x18006f2ef  mov     rcx, [rax+10h]
0x18006f2f3  cmp     byte ptr [rcx+19h], 0
0x18006f2f7  jz      short loc_18006F317
0x18006f2f9  mov     rcx, [rax+8]
0x18006f2fd  jmp     short loc_18006F30C
0x18006f2ff  cmp     rax, [rcx+10h]
0x18006f303  jnz     short loc_18006F312
0x18006f305  mov     rax, rcx
0x18006f308  mov     rcx, [rcx+8]
0x18006f30c  cmp     byte ptr [rcx+19h], 0
0x18006f310  jz      short loc_18006F2FF
0x18006f312  mov     rax, rcx
0x18006f315  jmp     short loc_18006F2CE
0x18006f317  mov     rax, rcx
0x18006f31a  mov     rdx, [rcx]
0x18006f31d  cmp     byte ptr [rdx+19h], 0
0x18006f321  jnz     short loc_18006F2CE
0x18006f323  mov     rax, rdx
0x18006f326  mov     rcx, [rdx]
0x18006f329  mov     rdx, rcx
0x18006f32c  cmp     byte ptr [rcx+19h], 0
0x18006f330  jz      short loc_18006F323
0x18006f332  jmp     short loc_18006F2CE
0x18006f334  cmp     byte ptr [rcx+0D0h], 0
0x18006f33b  jnz     short loc_18006F35A
0x18006f33d  movups  xmm0, [rsp+148h+var_108]
0x18006f342  movups  xmmword ptr [rcx+0BCh], xmm0
0x18006f349  mov     eax, [rsp+148h+var_F8]
0x18006f34d  mov     [rcx+0CCh], eax
0x18006f353  mov     byte ptr [rcx+0D0h], 1
0x18006f35a  lea     rcx, ?s_lockInstanceAndDiagnosticMaps@Container@helium@@0Vsrwlock@wil@@A; SRWLock
0x18006f361  call    cs:__imp_ReleaseSRWLockShared
0x18006f368  nop     dword ptr [rax+rax+00h]
0x18006f36d  mov     rcx, [rsp+148h+var_38]
0x18006f375  xor     rcx, rsp; StackCookie
0x18006f378  call    __security_check_cookie
0x18006f37d  add     rsp, 128h
0x18006f384  pop     r15
0x18006f386  pop     r14
0x18006f388  pop     rdi
0x18006f389  pop     rsi
0x18006f38a  retn
0x18006f38c  lea     r8, aOnecoreInterna_5; "onecore\\internal\\com\\inc\\combase\\C"...
0x18006f393  mov     edx, 19h; void *
0x18006f398  mov     rcx, r15; this
0x18006f39b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18006f3a1  mov     r9d, eax; char *
0x18006f3a4  lea     r8, aOnecoreBaseApp_52; "onecore\\base\\appmodel\\execmodel\\des"...
0x18006f3ab  mov     edx, 0EBh; void *
0x18006f3b0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
