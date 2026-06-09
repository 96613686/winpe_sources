# CInputProfileMasterAssembly::Initialize(void)

- ea: `0x18002053c`
- end: `0x18002087e`
- name: `?Initialize@CInputProfileMasterAssembly@@AEAAJXZ`
- size: `834`
- prototype: `__int64 __fastcall(CInputProfileMasterAssembly *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180020940`

## callees

- `0x18000f900`
- `0x180011000`
- `0x18001e9f0`
- `0x18002053c`
- `0x180020884`
- `0x180020e60`
- `0x180021050`
- `0x1800214c8`
- `0x18008426c`
- `0x180087b5c`
- `0x18009363c`
- `0x18009eaea`
- `0x1800b8020`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800207da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800207da`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020769`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020769`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x18002059e`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800205dc`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x180020605`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x180020660`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800206c7`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800206fd`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x18002073c`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x18002083a`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x18002059e`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800205dc`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x180020605`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x180020660`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800206c7`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800206fd`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x18002073c`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x18002083a`
- `CoreMessaging!CoreUICreate` at `0x180020589`
- `CoreMessaging!CoreUICreate` at `0x180020589`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x1800205c7`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x1800205c7`

## pseudocode

```c
__int64 __fastcall CInputProfileMasterAssembly::Initialize(CInputProfileMasterAssembly *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  unsigned __int64 v4; // r8
  _QWORD *v5; // rsi
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // eax
  UserSessionInputProfiles *v13; // rax
  UserSessionInputProfiles *v14; // rbx
  tagSYSTHREAD *v15; // rcx
  int v16; // eax
  char v18[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v19; // [rsp+44h] [rbp-BCh] BYREF
  CInputProfileMasterAssembly *v20; // [rsp+48h] [rbp-B8h] BYREF
  CInputProfileMasterAssembly *v21; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v22[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 retaddr; // [rsp+298h] [rbp+198h]

  v19 = 0;
  if ( IsInputServiceEnabled() )
  {
    v2 = CoreUICreate((char *)this + 232);
    v3 = v2;
    if ( v2 >= 0 )
    {
      v5 = (_QWORD *)((char *)this + 240);
      v6 = CoreUIFactoryCreate((char *)this + 240);
      v3 = v6;
      if ( v6 >= 0 )
      {
        v7 = SharedMessagePortRefPtr::Initialize((char *)this + 168);
        v3 = v7;
        if ( v7 >= 0 )
        {
          memset_0(v22, 0, 0x208u);
          GetDesktopUniqueName(L"System\\RemoteInputProfiles", v22);
          v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, unsigned int *))(*(_QWORD *)*v5 + 24LL))(
                 *v5,
                 &GUID_dc12c303_ce65_436c_87b3_6614b2ca0d7e,
                 &v19);
          v3 = v8;
          if ( v8 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, char *))(*(_QWORD *)*v5 + 32LL))(
                   *v5,
                   ((unsigned __int64)this + 40) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64),
                   0,
                   v19,
                   0,
                   *((_QWORD *)this + 22),
                   (char *)this + 248);
            v3 = v9;
            if ( v9 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 31) + 64LL))(
                      *((_QWORD *)this + 31),
                      (char *)this + 184);
              v3 = v10;
              if ( v10 >= 0 )
              {
                v20 = this;
                v12 = Microsoft::WRL::Details::MakeAndInitialize<MessageProxyReconnectAdapter,MessageProxyReconnectAdapter,_GUID const &,unsigned short (&)[260],CInputProfileMasterAssembly *>(
                        (char *)this + 256,
                        v11,
                        v22,
                        &v20);
                v3 = v12;
                if ( v12 >= 0 )
                  return v3;
                if ( v12 == -2147024882 )
                  TerminateProcessOnMemoryExhaustion(0);
                v4 = 3105;
              }
              else
              {
                if ( v10 == -2147024882 )
                  TerminateProcessOnMemoryExhaustion(0);
                v4 = 3098;
              }
            }
            else
            {
              if ( v9 == -2147024882 )
                TerminateProcessOnMemoryExhaustion(0);
              v4 = 3096;
            }
          }
          else
          {
            if ( v8 == -2147024882 )
              TerminateProcessOnMemoryExhaustion(0);
            v4 = 3088;
          }
        }
        else
        {
          if ( v7 == -2147024882 )
            TerminateProcessOnMemoryExhaustion(0);
          v4 = 3081;
        }
      }
      else
      {
        if ( v6 == -2147024882 )
          TerminateProcessOnMemoryExhaustion(0);
        v4 = 3080;
      }
    }
    else
    {
      if ( v2 == -2147024882 )
        TerminateProcessOnMemoryExhaustion(0);
      v4 = 3079;
    }
  }
  else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl'::`2'::impl) )
  {
    v13 = (UserSessionInputProfiles *)LocalAlloc(0x40u, 0x50u);
    v14 = v13;
    if ( v13 )
    {
      *(_QWORD *)v13 = 0;
      *((_DWORD *)v13 + 2) = 0;
      *((_DWORD *)v13 + 3) = -1;
      *((_QWORD *)v13 + 2) = 0;
      *((_QWORD *)v13 + 3) = 0;
      *((_QWORD *)v13 + 4) = -2147483647;
      *((_WORD *)v13 + 20) = 0;
      *((_BYTE *)v13 + 42) = 1;
      *((_QWORD *)v13 + 6) = 0;
      *((_QWORD *)v13 + 7) = 0;
      *((_QWORD *)v13 + 8) = 0;
      *((_QWORD *)v13 + 9) = 0;
    }
    else
    {
      v14 = 0;
    }
    *((_QWORD *)this + 34) = v14;
    if ( v14 )
    {
      *(_DWORD *)v14 = tagSYSTHREAD::GetSystemFlags(*((tagSYSTHREAD **)this + 6));
      *((_QWORD *)v14 + 9) = GetProcessHeap();
      UserSessionInputProfiles::_UpdateUserSettings(v14);
      v3 = 0;
      CInputProfileMasterAssembly::_RefreshSessionProfiles(this);
      return v3;
    }
    v3 = -2147024882;
    v4 = 3110;
  }
  else
  {
    v15 = (tagSYSTHREAD *)*((_QWORD *)this + 6);
    v21 = this;
    v18[0] = 1;
    LODWORD(v20) = tagSYSTHREAD::GetSystemFlags(v15);
    v16 = Microsoft::WRL::Details::MakeAndInitialize<CInputProfilesMasterList,CInputProfilesMasterList,unsigned long,bool,CInputProfileMasterAssembly *>(
            (char *)this + 264,
            &v20,
            v18,
            &v21);
    v3 = v16;
    if ( v16 >= 0 )
      return (unsigned int)CInputProfileMasterAssembly::Load(this);
    if ( v16 == -2147024882 )
      TerminateProcessOnMemoryExhaustion(0);
    v4 = 3120;
  }
  FailFastWithHR(v3, retaddr, v4);
  return v3;
}

```

## disassembly

```asm
0x18002053c  mov     [rsp-8+arg_8], rbx
0x180020541  mov     [rsp-8+arg_10], rsi
0x180020546  push    rbp
0x180020547  push    rdi
0x180020548  push    r14
0x18002054a  lea     rbp, [rsp-180h]
0x180020552  sub     rsp, 280h
0x180020559  mov     rax, cs:__security_cookie
0x180020560  xor     rax, rsp
0x180020563  mov     [rbp+190h+var_20], rax
0x18002056a  xor     r14d, r14d
0x18002056d  mov     rdi, rcx
0x180020570  mov     [rsp+290h+var_24C], r14d
0x180020575  call    ?IsInputServiceEnabled@@YA_NXZ; IsInputServiceEnabled(void)
0x18002057a  test    al, al
0x18002057c  jz      loc_18002074D
0x180020582  lea     rcx, [rdi+0E8h]
0x180020589  call    cs:__imp_CoreUICreate
0x18002058f  mov     ebx, eax
0x180020591  test    eax, eax
0x180020593  jns     short loc_1800205BD
0x180020595  cmp     eax, 8007000Eh
0x18002059a  jnz     short loc_1800205A4
0x18002059c  xor     ecx, ecx; FailedAllocationSize
0x18002059e  call    cs:__imp_TerminateProcessOnMemoryExhaustion
0x1800205a4  mov     r8d, 0C07h; unsigned __int64
0x1800205aa  mov     rdx, [rbp+198h]; unsigned __int64
0x1800205b1  mov     ecx, ebx; int
0x1800205b3  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x1800205b8  jmp     loc_180020855
0x1800205bd  lea     rsi, [rdi+0F0h]
0x1800205c4  mov     rcx, rsi
0x1800205c7  call    cs:__imp_CoreUIFactoryCreate
0x1800205cd  mov     ebx, eax
0x1800205cf  test    eax, eax
0x1800205d1  jns     short loc_1800205EA
0x1800205d3  cmp     eax, 8007000Eh
0x1800205d8  jnz     short loc_1800205E2
0x1800205da  xor     ecx, ecx; FailedAllocationSize
0x1800205dc  call    cs:__imp_TerminateProcessOnMemoryExhaustion
0x1800205e2  mov     r8d, 0C08h
0x1800205e8  jmp     short loc_1800205AA
0x1800205ea  lea     rcx, [rdi+0A8h]
0x1800205f1  call    ?Initialize@SharedMessagePortRefPtr@@QEAAJW4InputCapability@@@Z; SharedMessagePortRefPtr::Initialize(InputCapability)
0x1800205f6  mov     ebx, eax
0x1800205f8  test    eax, eax
0x1800205fa  jns     short loc_180020613
0x1800205fc  cmp     eax, 8007000Eh
0x180020601  jnz     short loc_18002060B
0x180020603  xor     ecx, ecx; FailedAllocationSize
0x180020605  call    cs:__imp_TerminateProcessOnMemoryExhaustion
0x18002060b  mov     r8d, 0C09h
0x180020611  jmp     short loc_1800205AA
0x180020613  xor     edx, edx; Val
0x180020615  lea     rcx, [rsp+290h+var_230]; void *
0x18002061a  mov     r8d, 208h; Size
0x180020620  call    memset_0
0x180020625  lea     rdx, [rsp+290h+var_230]; unsigned __int16 *
0x18002062a  lea     rcx, aSystemRemotein; "System\\RemoteInputProfiles"
0x180020631  call    ?GetDesktopUniqueName@@YAXPEBGPEAGK@Z; GetDesktopUniqueName(ushort const *,ushort *,ulong)
0x180020636  mov     rcx, [rsi]
0x180020639  lea     r8, [rsp+290h+var_24C]
0x18002063e  lea     rdx, _GUID_dc12c303_ce65_436c_87b3_6614b2ca0d7e
0x180020645  mov     rax, [rcx]
0x180020648  mov     rax, [rax+18h]
0x18002064c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020651  mov     ebx, eax
0x180020653  test    eax, eax
0x180020655  jns     short loc_180020671
0x180020657  cmp     eax, 8007000Eh
0x18002065c  jnz     short loc_180020666
0x18002065e  xor     ecx, ecx; FailedAllocationSize
0x180020660  call    cs:__imp_TerminateProcessOnMemoryExhaustion
0x180020666  mov     r8d, 0C10h
0x18002066c  jmp     loc_1800205AA
0x180020671  mov     r10, [rsi]
0x180020674  lea     rcx, [rdi+28h]
0x180020678  mov     r9d, [rsp+290h+var_24C]
0x18002067d  lea     rsi, [rdi+0F8h]
0x180020684  mov     [rsp+290h+var_260], rsi
0x180020689  mov     rax, rdi
0x18002068c  neg     rax
0x18002068f  mov     r8, [r10]
0x180020692  sbb     rdx, rdx
0x180020695  and     rdx, rcx
0x180020698  mov     rcx, [rdi+0B0h]
0x18002069f  mov     [rsp+290h+var_268], rcx
0x1800206a4  mov     rcx, r10
0x1800206a7  mov     rax, [r8+20h]
0x1800206ab  xor     r8d, r8d
0x1800206ae  mov     [rsp+290h+var_270], r14
0x1800206b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206b8  mov     ebx, eax
0x1800206ba  test    eax, eax
0x1800206bc  jns     short loc_1800206D8
0x1800206be  cmp     eax, 8007000Eh
0x1800206c3  jnz     short loc_1800206CD
0x1800206c5  xor     ecx, ecx; FailedAllocationSize
0x1800206c7  call    cs:__imp_TerminateProcessOnMemoryExhaustion
0x1800206cd  mov     r8d, 0C18h
0x1800206d3  jmp     loc_1800205AA
0x1800206d8  mov     rcx, [rsi]
0x1800206db  lea     rdx, [rdi+0B8h]
0x1800206e2  mov     rax, [rcx]
0x1800206e5  mov     rax, [rax+40h]
0x1800206e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206ee  mov     ebx, eax
0x1800206f0  test    eax, eax
0x1800206f2  jns     short loc_18002070E
0x1800206f4  cmp     eax, 8007000Eh
0x1800206f9  jnz     short loc_180020703
0x1800206fb  xor     ecx, ecx; FailedAllocationSize
0x1800206fd  call    cs:__imp_TerminateProcessOnMemoryExhaustion
0x180020703  mov     r8d, 0C1Ah
0x180020709  jmp     loc_1800205AA
0x18002070e  lea     rcx, [rdi+100h]
0x180020715  mov     [rsp+290h+var_248], rdi
0x18002071a  lea     r9, [rsp+290h+var_248]
0x18002071f  lea     r8, [rsp+290h+var_230]
0x180020724  call    ??$MakeAndInitialize@VMessageProxyReconnectAdapter@@V1@AEBU_GUID@@AEAY0BAE@GPEAVCInputProfileMasterAssembly@@@Details@WRL@Microsoft@@YAJPEAPEAVMessageProxyReconnectAdapter@@AEBU_GUID@@AEAY0BAE@G$$QEAPEAVCInputProfileMasterAssembly@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MessageProxyReconnectAdapter,MessageProxyReconnectAdapter,_GUID const &,ushort (&)[260],CInputProfileMasterAssembly *>(MessageProxyReconnectAdapter * *,_GUID const &,ushort (&)[260],CInputProfileMasterAssembly * &&)
0x180020729  mov     ebx, eax
0x18002072b  test    eax, eax
0x18002072d  jns     loc_180020855
0x180020733  cmp     eax, 8007000Eh
0x180020738  jnz     short loc_180020742
0x18002073a  xor     ecx, ecx; FailedAllocationSize
0x18002073c  call    cs:__imp_TerminateProcessOnMemoryExhaustion
0x180020742  mov     r8d, 0C21h
0x180020748  jmp     loc_1800205AA
0x18002074d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47> `wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl(void)'::`2'::impl
0x180020754  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(void)
0x180020759  test    al, al
0x18002075b  jz      loc_1800207F9
0x180020761  mov     edx, 50h ; 'P'; uBytes
0x180020766  lea     ecx, [rdx-10h]; uFlags
0x180020769  call    cs:__imp_LocalAlloc
0x18002076f  mov     rbx, rax
0x180020772  test    rax, rax
0x180020775  jz      short loc_1800207B0
0x180020777  mov     [rax], r14
0x18002077a  mov     [rax+8], r14d
0x18002077e  mov     dword ptr [rax+0Ch], 0FFFFFFFFh
0x180020785  mov     [rax+10h], r14
0x180020789  mov     [rax+18h], r14
0x18002078d  mov     qword ptr [rax+20h], 0FFFFFFFF80000001h
0x180020795  mov     [rax+28h], r14w
0x18002079a  mov     byte ptr [rax+2Ah], 1
0x18002079e  mov     [rax+30h], r14
0x1800207a2  mov     [rax+38h], r14
0x1800207a6  mov     [rax+40h], r14
0x1800207aa  mov     [rax+48h], r14
0x1800207ae  jmp     short loc_1800207B3
0x1800207b0  mov     rbx, r14
0x1800207b3  mov     [rdi+110h], rbx
0x1800207ba  test    rbx, rbx
0x1800207bd  jnz     short loc_1800207CF
0x1800207bf  mov     ebx, 8007000Eh
0x1800207c4  mov     r8d, 0C26h
0x1800207ca  jmp     loc_1800205AA
0x1800207cf  mov     rcx, [rdi+30h]; this
0x1800207d3  call    ?GetSystemFlags@tagSYSTHREAD@@QEAAKXZ; tagSYSTHREAD::GetSystemFlags(void)
0x1800207d8  mov     [rbx], eax
0x1800207da  call    cs:__imp_GetProcessHeap
0x1800207e0  mov     rcx, rbx; this
0x1800207e3  mov     [rbx+48h], rax
0x1800207e7  call    ?_UpdateUserSettings@UserSessionInputProfiles@@AEAA_NXZ; UserSessionInputProfiles::_UpdateUserSettings(void)
0x1800207ec  mov     rcx, rdi; this
0x1800207ef  mov     ebx, r14d
0x1800207f2  call    ?_RefreshSessionProfiles@CInputProfileMasterAssembly@@AEAAXXZ; CInputProfileMasterAssembly::_RefreshSessionProfiles(void)
0x1800207f7  jmp     short loc_180020855
0x1800207f9  mov     rcx, [rdi+30h]; this
0x1800207fd  mov     [rsp+290h+var_240], rdi
0x180020802  mov     [rsp+290h+var_250], 1
0x180020807  call    ?GetSystemFlags@tagSYSTHREAD@@QEAAKXZ; tagSYSTHREAD::GetSystemFlags(void)
0x18002080c  lea     rcx, [rdi+108h]
0x180020813  mov     dword ptr [rsp+290h+var_248], eax
0x180020817  lea     r9, [rsp+290h+var_240]
0x18002081c  lea     r8, [rsp+290h+var_250]
0x180020821  lea     rdx, [rsp+290h+var_248]
0x180020826  call    ??$MakeAndInitialize@VCInputProfilesMasterList@@V1@K_NPEAVCInputProfileMasterAssembly@@@Details@WRL@Microsoft@@YAJPEAPEAVCInputProfilesMasterList@@$$QEAK$$QEA_N$$QEAPEAVCInputProfileMasterAssembly@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CInputProfilesMasterList,CInputProfilesMasterList,ulong,bool,CInputProfileMasterAssembly *>(CInputProfilesMasterList * *,ulong &&,bool &&,CInputProfileMasterAssembly * &&)
0x18002082b  mov     ebx, eax
0x18002082d  test    eax, eax
0x18002082f  jns     short loc_18002084B
0x180020831  cmp     eax, 8007000Eh
0x180020836  jnz     short loc_180020840
0x180020838  xor     ecx, ecx; FailedAllocationSize
0x18002083a  call    cs:__imp_TerminateProcessOnMemoryExhaustion
0x180020840  mov     r8d, 0C30h
0x180020846  jmp     loc_1800205AA
0x18002084b  mov     rcx, rdi; this
0x18002084e  call    ?Load@CInputProfileMasterAssembly@@AEAAJ_N@Z; CInputProfileMasterAssembly::Load(bool)
0x180020853  mov     ebx, eax
0x180020855  mov     eax, ebx
0x180020857  mov     rcx, [rbp+190h+var_20]
0x18002085e  xor     rcx, rsp; StackCookie
0x180020861  call    __security_check_cookie
0x180020866  lea     r11, [rsp+290h+var_10]
0x18002086e  mov     rbx, [r11+28h]
0x180020872  mov     rsi, [r11+30h]
0x180020876  mov     rsp, r11
0x180020879  pop     r14
0x18002087b  pop     rdi
0x18002087c  pop     rbp
0x18002087d  retn
```
