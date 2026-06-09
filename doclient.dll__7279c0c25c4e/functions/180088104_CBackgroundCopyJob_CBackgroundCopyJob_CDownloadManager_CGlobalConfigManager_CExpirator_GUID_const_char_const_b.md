# CBackgroundCopyJob::CBackgroundCopyJob(CDownloadManager &,CGlobalConfigManager &,CExpirator &,_GUID const &,char const *,bool)

- ea: `0x180088104`
- end: `0x1800886d0`
- name: `??0CBackgroundCopyJob@@QEAA@AEAVCDownloadManager@@AEAVCGlobalConfigManager@@AEAVCExpirator@@AEBU_GUID@@PEBD_N@Z`
- size: `1484`
- prototype: `CBackgroundCopyJob *__fastcall(CBackgroundCopyJob *this, struct CDownloadManager *, struct CGlobalConfigManager *, struct CExpirator *, const struct _GUID *, char *, bool)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x180097200`

## callees

- `0x180009528`
- `0x18000cea4`
- `0x18007f17c`
- `0x180087ddc`
- `0x180088104`
- `0x180089e64`
- `0x18008e068`
- `0x18008e31c`
- `0x18008f628`
- `0x18008f908`
- `0x180094020`
- `0x18009a2d4`
- `0x18009f91c`
- `0x18009fa14`
- `0x1800f82f0`
- `0x1800f8320`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800882a7`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180088469`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800882a7`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180088469`

## string_xrefs

- `0x18008866a`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008867f`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x180088694`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x1800886a9`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x1800886be`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CBackgroundCopyJob *__fastcall CBackgroundCopyJob::CBackgroundCopyJob(
        CBackgroundCopyJob *this,
        struct CDownloadManager *a2,
        struct CGlobalConfigManager *a3,
        struct CExpirator *a4,
        const struct _GUID *a5,
        char *a6,
        bool a7)
{
  __int64 v11; // rax
  _DWORD *v12; // rdi
  struct _GUID *v13; // rbx
  struct IPersistedEntity **v14; // rax
  struct IPersistedEntity *v15; // rdi
  int v16; // eax
  struct IPersistedEntity **v17; // rax
  struct IPersistedEntity *v18; // rbx
  int v19; // eax
  struct _GUID *v20; // rdi
  int v21; // eax
  volatile signed __int32 *v22; // rbx
  int NewCv; // eax
  int v24; // eax
  struct _GUID *v25; // rcx
  volatile signed __int32 *v26; // rbx
  int v28; // [rsp+20h] [rbp-50h]
  struct _GUID *v29[2]; // [rsp+30h] [rbp-40h] BYREF
  CBackgroundCopyJob *v30; // [rsp+40h] [rbp-30h]
  bool v31; // [rsp+48h] [rbp-28h] BYREF
  struct IPersistedEntity *v32; // [rsp+50h] [rbp-20h] BYREF
  struct _GUID *v33; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v30 = this;
  v29[0] = (struct _GUID *)a5;
  *(_QWORD *)this = &CBackgroundCopyJob::`vftable'{for `IDeliveryOptimizationJobPrivCallback'};
  *((_QWORD *)this + 1) = &CBackgroundCopyJob::`vftable'{for `IExpirable'};
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  v11 = std::_Allocate<16,std::_Default_allocate_traits>(56);
  *(_QWORD *)v11 = v11;
  *(_QWORD *)(v11 + 8) = v11;
  *(_QWORD *)(v11 + 16) = v11;
  *(_WORD *)(v11 + 24) = 257;
  *((_QWORD *)this + 2) = v11;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 258;
  *((_OWORD *)this + 10) = 0;
  *((_OWORD *)this + 11) = 0;
  *((_OWORD *)this + 12) = 0;
  *((_OWORD *)this + 9) = 0;
  *((_DWORD *)this + 52) = -1;
  *((_DWORD *)this + 53) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 1;
  v12 = operator new(0x1A0u);
  *(_OWORD *)v12 = 0;
  v12[2] = 1;
  v12[3] = 1;
  *(_QWORD *)v12 = &std::_Ref_count_obj2<CJobSharedData>::`vftable';
  CJobSharedData::CJobSharedData((CJobSharedData *)(v12 + 4), this, a2, v29[0], a7);
  *((_QWORD *)this + 31) = v12 + 4;
  *((_QWORD *)this + 32) = v12;
  v32 = 0;
  GetSystemTimePreciseAsFileTime(&v32);
  *((_QWORD *)this + 33) = ((unsigned __int64)HIDWORD(v32) << 32) - 116444736000000000LL + (unsigned int)v32;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_BYTE *)this + 344) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 1;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = a3;
  *((_QWORD *)this + 48) = a4;
  *((_QWORD *)this + 49) = 0;
  *((_WORD *)this + 200) = 0;
  *((_BYTE *)this + 402) = 0;
  v31 = 0;
  v13 = v29[0];
  v14 = (struct IPersistedEntity **)std::make_unique<CPersistedEntityRegJob<CAppRegistryEntityLocation>,_GUID const &,0>(
                                      v29,
                                      v29[0]);
  v15 = *v14;
  *v14 = 0;
  v32 = v15;
  if ( v29[0] )
    (**(void (__fastcall ***)(struct _GUID *, __int64))v29[0])(v29[0], 1);
  if ( v15 )
  {
    v16 = CBackgroundCopyJob::_LoadJobInfo(this, v15, &v31);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBE,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
        (const char *)(unsigned int)v16,
        v28);
    if ( !v31 )
    {
      v17 = (struct IPersistedEntity **)std::make_unique<CPersistedEntityRegJob<CSysRegistryEntityLocation>,_GUID const &,0>(
                                          v29,
                                          v13);
      v18 = *v17;
      *v17 = 0;
      v33 = (struct _GUID *)v18;
      if ( v29[0] )
        (**(void (__fastcall ***)(struct _GUID *, __int64))v29[0])(v29[0], 1);
      v19 = CBackgroundCopyJob::_LoadJobInfo(this, v18, &v31);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC2,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
          (const char *)(unsigned int)v19,
          v28);
      if ( v31 )
        CBackgroundCopyJob::_SaveJobInfo(this);
      if ( v18 )
        (**(void (__fastcall ***)(struct IPersistedEntity *, __int64))v18)(v18, 1);
    }
  }
  if ( v15 )
    (**(void (__fastcall ***)(struct IPersistedEntity *, __int64))v15)(v15, 1);
  if ( !v31 )
  {
    v32 = 0;
    GetSystemTimePreciseAsFileTime(&v32);
    *((_QWORD *)this + 36) = ((unsigned __int64)HIDWORD(v32) << 32) - 116444700000000000LL + (unsigned int)v32;
    CJobSharedData::SetOwnerIdentity(*((RTL_SRWLOCK **)this + 31));
    if ( a6 )
    {
      v20 = (struct _GUID *)operator new(0x38u);
      v33 = v20;
      *v20 = 0;
      *(_DWORD *)v20->Data4 = 1;
      *(_DWORD *)&v20->Data4[4] = 1;
      *(_QWORD *)&v20->Data1 = &std::_Ref_count_obj2<CConfigValue>::`vftable';
      CConfigValue::CConfigValue((CConfigValue *)&v20[1], a6);
      v29[0] = v20 + 1;
      v29[1] = v20;
      v21 = CBackgroundCopyJob::SetDownloadProperty(this, (char *)3, (unsigned __int8 **)v29, 0);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD9,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
          (const char *)(unsigned int)v21,
          v28);
      v22 = (volatile signed __int32 *)v29[1];
      if ( v29[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v29[1]->Data4, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
          if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
        }
      }
    }
  }
  if ( !*((_QWORD *)this + 11) )
  {
    NewCv = CBackgroundCopyJob::_CreateNewCv(this);
    if ( NewCv < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDF,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
        (const char *)(unsigned int)NewCv,
        v28);
  }
  if ( v31 )
  {
    v24 = CBackgroundCopyJob::_InitFromSavedState(this);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE4,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
        (const char *)(unsigned int)v24,
        v28);
  }
  CExpirator::AddContentToExpire(*((CExpirator **)this + 48));
  if ( !v31 && a7 )
  {
    v25 = (struct _GUID *)operator new(0x38u);
    v33 = v25;
    *v25 = 0;
    *(_DWORD *)v25->Data4 = 1;
    *(_DWORD *)&v25->Data4[4] = 1;
    *(_QWORD *)&v25->Data1 = &std::_Ref_count_obj2<CConfigValue>::`vftable';
    LOBYTE(v25[1].Data1) = 1;
    LOBYTE(v25[3].Data1) = 1;
    v29[0] = v25 + 1;
    v29[1] = v25;
    CBackgroundCopyJob::SetDownloadProperty(this, (char *)0x1B, (unsigned __int8 **)v29, 0);
    v26 = (volatile signed __int32 *)v29[1];
    if ( v29[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v29[1]->Data4, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
        if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180088104  mov     [rsp-28h+arg_8], rbx
0x180088109  mov     [rsp-28h+arg_10], rsi
0x18008810e  mov     [rsp-28h+arg_18], rdi
0x180088113  push    rbp
0x180088114  push    r12
0x180088116  push    r13
0x180088118  push    r14
0x18008811a  push    r15
0x18008811c  mov     rbp, rsp
0x18008811f  sub     rsp, 70h
0x180088123  mov     rax, cs:__security_cookie
0x18008812a  xor     rax, rsp
0x18008812d  mov     [rbp+var_10], rax
0x180088131  mov     r15, r9
0x180088134  mov     r14, r8
0x180088137  mov     rsi, rdx
0x18008813a  mov     r12, rcx
0x18008813d  mov     [rbp+var_30], rcx
0x180088141  mov     rax, [rbp+arg_20]
0x180088145  mov     [rbp+var_40], rax
0x180088149  mov     r13, [rbp+arg_28]
0x18008814d  xor     edi, edi
0x18008814f  lea     rcx, ??_7CBackgroundCopyJob@@6BIDeliveryOptimizationJobPrivCallback@@@; const CBackgroundCopyJob::`vftable'{for `IDeliveryOptimizationJobPrivCallback'}
0x180088156  mov     [r12], rcx
0x18008815a  lea     rcx, ??_7CBackgroundCopyJob@@6BIExpirable@@@; const CBackgroundCopyJob::`vftable'{for `IExpirable'}
0x180088161  mov     [r12+8], rcx
0x180088166  mov     [r12+10h], rdi
0x18008816b  mov     [r12+18h], rdi
0x180088170  lea     ecx, [rdi+38h]
0x180088173  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180088178  mov     [rax], rax
0x18008817b  mov     [rax+8], rax
0x18008817f  mov     [rax+10h], rax
0x180088183  mov     word ptr [rax+18h], 101h
0x180088189  mov     [r12+10h], rax
0x18008818e  mov     [r12+20h], rdi
0x180088193  mov     [r12+28h], rdi
0x180088198  mov     [r12+30h], rdi
0x18008819d  mov     [r12+38h], rdi
0x1800881a2  mov     [r12+40h], rdi
0x1800881a7  mov     [r12+48h], rdi
0x1800881ac  mov     [r12+50h], rdi
0x1800881b1  mov     [r12+58h], rdi
0x1800881b6  mov     [r12+60h], rdi
0x1800881bb  mov     [r12+68h], rdi
0x1800881c0  mov     [r12+70h], rdi
0x1800881c5  mov     [r12+78h], rdi
0x1800881ca  mov     [r12+80h], rdi
0x1800881d2  mov     qword ptr [r12+88h], 102h
0x1800881de  xorps   xmm0, xmm0
0x1800881e1  movups  xmmword ptr [r12+0A0h], xmm0
0x1800881ea  movups  xmmword ptr [r12+0B0h], xmm0
0x1800881f3  movups  xmmword ptr [r12+0C0h], xmm0
0x1800881fc  xorps   xmm1, xmm1
0x1800881ff  movdqu  xmmword ptr [r12+90h], xmm1
0x180088209  mov     dword ptr [r12+0D0h], 0FFFFFFFFh
0x180088215  mov     [r12+0D4h], edi
0x18008821d  mov     [r12+0D8h], rdi
0x180088225  mov     [r12+0E0h], rdi
0x18008822d  mov     [r12+0E8h], rdi
0x180088235  mov     qword ptr [r12+0F0h], 1
0x180088241  mov     ecx, 1A0h; Size
0x180088246  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008824b  mov     rdi, rax
0x18008824e  mov     [rbp+var_20], rax
0x180088252  xorps   xmm0, xmm0
0x180088255  movups  xmmword ptr [rax], xmm0
0x180088258  mov     dword ptr [rax+8], 1
0x18008825f  mov     dword ptr [rax+0Ch], 1
0x180088266  lea     rax, ??_7?$_Ref_count_obj2@VCJobSharedData@@@std@@6B@; const std::_Ref_count_obj2<CJobSharedData>::`vftable'
0x18008826d  mov     [rdi], rax
0x180088270  lea     rbx, [rdi+10h]
0x180088274  mov     al, [rbp+arg_30]
0x180088277  mov     byte ptr [rsp+70h+var_50], al; int
0x18008827b  mov     r9, [rbp+var_40]; struct _GUID *
0x18008827f  mov     r8, rsi; struct CDownloadManager *
0x180088282  mov     rdx, r12; struct IDeliveryOptimizationJobPrivCallback *
0x180088285  mov     rcx, rbx; this
0x180088288  call    ??0CJobSharedData@@QEAA@AEAVIDeliveryOptimizationJobPrivCallback@@AEAVCDownloadManager@@AEBU_GUID@@_N@Z; CJobSharedData::CJobSharedData(IDeliveryOptimizationJobPrivCallback &,CDownloadManager &,_GUID const &,bool)
0x18008828d  nop
0x18008828e  lea     rsi, [r12+0F8h]
0x180088296  mov     [rsi], rbx
0x180088299  mov     [rsi+8], rdi
0x18008829d  xor     ebx, ebx
0x18008829f  mov     [rbp+var_20], rbx
0x1800882a3  lea     rcx, [rbp+var_20]
0x1800882a7  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800882ad  mov     eax, dword ptr [rbp+var_20+4]
0x1800882b0  shl     rax, 20h
0x1800882b4  mov     ecx, dword ptr [rbp+var_20]
0x1800882b7  mov     rdx, 0FE624E212AC18000h
0x1800882c1  add     rax, rdx
0x1800882c4  add     rcx, rax
0x1800882c7  mov     [r12+108h], rcx
0x1800882cf  mov     [r12+110h], rbx
0x1800882d7  mov     [r12+118h], rbx
0x1800882df  mov     [r12+120h], rbx
0x1800882e7  mov     [r12+128h], rbx
0x1800882ef  mov     [r12+130h], rbx
0x1800882f7  mov     [r12+138h], rbx
0x1800882ff  mov     [r12+140h], rbx
0x180088307  mov     [r12+148h], rbx
0x18008830f  mov     [r12+158h], bl
0x180088317  mov     [r12+150h], rbx
0x18008831f  mov     [r12+160h], rbx
0x180088327  mov     qword ptr [r12+168h], 1
0x180088333  mov     [r12+170h], rbx
0x18008833b  mov     [r12+178h], r14
0x180088343  mov     [r12+180h], r15
0x18008834b  xor     r14d, r14d
0x18008834e  mov     [r12+188h], r14
0x180088356  mov     [r12+190h], r14w
0x18008835f  mov     [r12+192h], r14b
0x180088367  mov     [rbp+var_28], r14b
0x18008836b  mov     rbx, [rbp+var_40]
0x18008836f  mov     rdx, rbx
0x180088372  lea     rcx, [rbp+var_40]
0x180088376  call    ??$make_unique@V?$CPersistedEntityRegJob@VCAppRegistryEntityLocation@@@@AEBU_GUID@@$0A@@std@@YA?AV?$unique_ptr@V?$CPersistedEntityRegJob@VCAppRegistryEntityLocation@@@@U?$default_delete@V?$CPersistedEntityRegJob@VCAppRegistryEntityLocation@@@@@std@@@0@AEBU_GUID@@@Z; std::make_unique<CPersistedEntityRegJob<CAppRegistryEntityLocation>,_GUID const &,0>(_GUID const &)
0x18008837b  mov     rdi, [rax]
0x18008837e  mov     [rax], r14
0x180088381  mov     [rbp+var_20], rdi
0x180088385  mov     rcx, [rbp+var_40]
0x180088389  lea     r15d, [r14+1]
0x18008838d  test    rcx, rcx
0x180088390  jz      short loc_1800883A1
0x180088392  mov     rax, [rcx]
0x180088395  mov     edx, r15d
0x180088398  mov     rax, [rax]
0x18008839b  call    _guard_dispatch_icall
0x1800883a0  nop
0x1800883a1  test    rdi, rdi
0x1800883a4  jz      loc_18008843A
0x1800883aa  lea     r8, [rbp+var_28]; bool *
0x1800883ae  mov     rdx, rdi; struct IPersistedEntity *
0x1800883b1  mov     rcx, r12; this
0x1800883b4  call    ?_LoadJobInfo@CBackgroundCopyJob@@AEAAJAEAVIPersistedEntity@@PEA_N@Z; CBackgroundCopyJob::_LoadJobInfo(IPersistedEntity &,bool *)
0x1800883b9  mov     rcx, [rbp+28h]; this
0x1800883bd  test    eax, eax
0x1800883bf  js      loc_18008867C
0x1800883c5  cmp     [rbp+var_28], r14b
0x1800883c9  jnz     short loc_18008843A
0x1800883cb  mov     rdx, rbx
0x1800883ce  lea     rcx, [rbp+var_40]
0x1800883d2  call    ??$make_unique@V?$CPersistedEntityRegJob@VCSysRegistryEntityLocation@@@@AEBU_GUID@@$0A@@std@@YA?AV?$unique_ptr@V?$CPersistedEntityRegJob@VCSysRegistryEntityLocation@@@@U?$default_delete@V?$CPersistedEntityRegJob@VCSysRegistryEntityLocation@@@@@std@@@0@AEBU_GUID@@@Z; std::make_unique<CPersistedEntityRegJob<CSysRegistryEntityLocation>,_GUID const &,0>(_GUID const &)
0x1800883d7  mov     rbx, [rax]
0x1800883da  mov     [rax], r14
0x1800883dd  mov     [rbp+var_18], rbx
0x1800883e1  mov     rcx, [rbp+var_40]
0x1800883e5  test    rcx, rcx
0x1800883e8  jz      short loc_1800883F9
0x1800883ea  mov     rax, [rcx]
0x1800883ed  mov     edx, r15d
0x1800883f0  mov     rax, [rax]
0x1800883f3  call    _guard_dispatch_icall
0x1800883f8  nop
0x1800883f9  lea     r8, [rbp+var_28]; bool *
0x1800883fd  mov     rdx, rbx; struct IPersistedEntity *
0x180088400  mov     rcx, r12; this
0x180088403  call    ?_LoadJobInfo@CBackgroundCopyJob@@AEAAJAEAVIPersistedEntity@@PEA_N@Z; CBackgroundCopyJob::_LoadJobInfo(IPersistedEntity &,bool *)
0x180088408  mov     rcx, [rbp+28h]; this
0x18008840c  test    eax, eax
0x18008840e  js      loc_180088691
0x180088414  cmp     [rbp+var_28], r14b
0x180088418  jz      short loc_180088423
0x18008841a  mov     rcx, r12; this
0x18008841d  call    ?_SaveJobInfo@CBackgroundCopyJob@@AEAAXXZ; CBackgroundCopyJob::_SaveJobInfo(void)
0x180088422  nop
0x180088423  test    rbx, rbx
0x180088426  jz      short loc_18008843A
0x180088428  mov     rax, [rbx]
0x18008842b  mov     edx, r15d
0x18008842e  mov     rcx, rbx
0x180088431  mov     rax, [rax]
0x180088434  call    _guard_dispatch_icall
0x180088439  nop
0x18008843a  test    rdi, rdi
0x18008843d  jz      short loc_180088450
0x18008843f  mov     rax, [rdi]
0x180088442  mov     edx, r15d
0x180088445  mov     rcx, rdi
0x180088448  mov     rax, [rax]
0x18008844b  call    _guard_dispatch_icall
0x180088450  lea     rbx, ??_7?$_Ref_count_obj2@VCConfigValue@@@std@@6B@; const std::_Ref_count_obj2<CConfigValue>::`vftable'
0x180088457  cmp     [rbp+var_28], r14b
0x18008845b  jnz     loc_180088549
0x180088461  mov     [rbp+var_20], r14
0x180088465  lea     rcx, [rbp+var_20]
0x180088469  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x18008846f  mov     eax, dword ptr [rbp+var_20+4]
0x180088472  shl     rax, 20h
0x180088476  mov     ecx, dword ptr [rbp+var_20]
0x180088479  mov     rdx, 0FE624E298C85E800h
0x180088483  add     rax, rdx
0x180088486  add     rcx, rax
0x180088489  mov     [r12+120h], rcx
0x180088491  mov     rcx, [rsi]; this
0x180088494  call    ?SetOwnerIdentity@CJobSharedData@@QEAAXXZ; CJobSharedData::SetOwnerIdentity(void)
0x180088499  test    r13, r13
0x18008849c  jz      loc_180088549
0x1800884a2  mov     ecx, 38h ; '8'; Size
0x1800884a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800884ac  mov     rdi, rax
0x1800884af  mov     [rbp+var_18], rax
0x1800884b3  xorps   xmm0, xmm0
0x1800884b6  movups  xmmword ptr [rax], xmm0
0x1800884b9  mov     [rax+8], r15d
0x1800884bd  mov     [rax+0Ch], r15d
0x1800884c1  mov     [rax], rbx
0x1800884c4  lea     rbx, [rax+10h]
0x1800884c8  mov     rdx, r13; char *
0x1800884cb  mov     rcx, rbx; this
0x1800884ce  call    ??0CConfigValue@@QEAA@PEBD@Z; CConfigValue::CConfigValue(char const *)
0x1800884d3  nop
0x1800884d4  xorps   xmm0, xmm0
0x1800884d7  movups  xmmword ptr [rbp+var_40], xmm0
0x1800884db  mov     [rbp+var_40], rbx
0x1800884df  mov     [rbp+var_40+8], rdi
0x1800884e3  xor     r9d, r9d
0x1800884e6  lea     r8, [rbp+var_40]
0x1800884ea  lea     edx, [r9+3]; char *
0x1800884ee  mov     rcx, r12; this
0x1800884f1  call    ?SetDownloadProperty@CBackgroundCopyJob@@QEAAJIAEBV?$shared_ptr@VCConfigValue@@@std@@_N@Z; CBackgroundCopyJob::SetDownloadProperty(uint,std::shared_ptr<CConfigValue> const &,bool)
0x1800884f6  mov     rcx, [rbp+28h]; this
0x1800884fa  test    eax, eax
0x1800884fc  js      loc_1800886A6
0x180088502  mov     rbx, [rbp+var_40+8]
0x180088506  test    rbx, rbx
0x180088509  jz      short loc_180088542
0x18008850b  or      eax, 0FFFFFFFFh
0x18008850e  lock xadd [rbx+8], eax
0x180088513  cmp     eax, 1
0x180088516  jnz     short loc_180088542
0x180088518  mov     rax, [rbx]
0x18008851b  mov     rcx, rbx
0x18008851e  mov     rax, [rax]
0x180088521  call    _guard_dispatch_icall
0x180088526  or      eax, 0FFFFFFFFh
0x180088529  lock xadd [rbx+0Ch], eax
0x18008852e  cmp     eax, 1
0x180088531  jnz     short loc_180088542
0x180088533  mov     rax, [rbx]
0x180088536  mov     rcx, rbx
0x180088539  mov     rax, [rax+8]
0x18008853d  call    _guard_dispatch_icall
0x180088542  lea     rbx, ??_7?$_Ref_count_obj2@VCConfigValue@@@std@@6B@; const std::_Ref_count_obj2<CConfigValue>::`vftable'
0x180088549  cmp     [r12+58h], r14
0x18008854e  jnz     short loc_180088564
0x180088550  mov     rcx, r12; this
0x180088553  call    ?_CreateNewCv@CBackgroundCopyJob@@AEAAJXZ; CBackgroundCopyJob::_CreateNewCv(void)
0x180088558  mov     rcx, [rbp+28h]; this
0x18008855c  test    eax, eax
0x18008855e  js      loc_1800886BB
0x180088564  cmp     [rbp+var_28], r14b
0x180088568  jz      short loc_18008857E
0x18008856a  mov     rcx, r12; this
0x18008856d  call    ?_InitFromSavedState@CBackgroundCopyJob@@AEAAJXZ; CBackgroundCopyJob::_InitFromSavedState(void)
0x180088572  mov     rcx, [rbp+28h]; this
0x180088576  test    eax, eax
0x180088578  js      loc_180088667
0x18008857e  mov     r8, [r12+120h]
0x180088586  lea     rdx, [r12+8]
0x18008858b  mov     rcx, [r12+180h]
0x180088593  call    ?AddContentToExpire@CExpirator@@QEAAXPEAVIExpirable@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; CExpirator::AddContentToExpire(IExpirable *,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>)
0x180088598  cmp     [rbp+var_28], r14b
0x18008859c  jnz     loc_18008863A
0x1800885a2  cmp     [rbp+arg_30], r14b
0x1800885a6  jz      loc_18008863A
0x1800885ac  mov     ecx, 38h ; '8'; Size
0x1800885b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800885b6  mov     rcx, rax
0x1800885b9  mov     [rbp+var_18], rax
0x1800885bd  xorps   xmm0, xmm0
0x1800885c0  movups  xmmword ptr [rax], xmm0
0x1800885c3  mov     [rax+8], r15d
0x1800885c7  mov     [rax+0Ch], r15d
0x1800885cb  mov     [rax], rbx
0x1800885ce  add     rax, 10h
0x1800885d2  mov     [rax], r15b
0x1800885d5  mov     [rax+20h], r15b
0x1800885d9  movups  xmmword ptr [rbp+var_40], xmm0
0x1800885dd  mov     [rbp+var_40], rax
0x1800885e1  mov     [rbp+var_40+8], rcx
0x1800885e5  xor     r9d, r9d
0x1800885e8  lea     r8, [rbp+var_40]
0x1800885ec  lea     edx, [r9+1Bh]; char *
0x1800885f0  mov     rcx, r12; this
0x1800885f3  call    ?SetDownloadProperty@CBackgroundCopyJob@@QEAAJIAEBV?$shared_ptr@VCConfigValue@@@std@@_N@Z; CBackgroundCopyJob::SetDownloadProperty(uint,std::shared_ptr<CConfigValue> const &,bool)
0x1800885f8  nop
0x1800885f9  mov     rbx, [rbp+var_40+8]
0x1800885fd  test    rbx, rbx
0x180088600  jz      short loc_18008863A
0x180088602  or      eax, 0FFFFFFFFh
0x180088605  lock xadd [rbx+8], eax
0x18008860a  cmp     eax, 1
0x18008860d  jnz     short loc_18008863A
0x18008860f  mov     rax, [rbx]
0x180088612  mov     rcx, rbx
0x180088615  mov     rax, [rax]
0x180088618  call    _guard_dispatch_icall
0x18008861d  or      edx, 0FFFFFFFFh
  ... truncated ...
```
