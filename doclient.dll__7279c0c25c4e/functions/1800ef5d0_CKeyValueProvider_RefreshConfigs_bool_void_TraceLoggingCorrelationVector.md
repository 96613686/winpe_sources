# CKeyValueProvider::RefreshConfigs(bool,void *,TraceLoggingCorrelationVector *)

- ea: `0x1800ef5d0`
- end: `0x1800ef9f1`
- name: `?RefreshConfigs@CKeyValueProvider@@UEAAJ_NPEAXPEAVTraceLoggingCorrelationVector@@@Z`
- size: `1057`
- prototype: `__int64 __fastcall(RTL_SRWLOCK **this, char, void *, struct TraceLoggingCorrelationVector *)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000933c`
- `0x1800095a0`
- `0x18001d324`
- `0x18007d008`
- `0x18009b538`
- `0x1800a1ea4`
- `0x1800a5c88`
- `0x1800bfe3c`
- `0x1800d63dc`
- `0x1800e9994`
- `0x1800ea1d8`
- `0x1800ef5d0`
- `0x1800ef9f8`
- `0x1800efc10`
- `0x1800effa8`
- `0x1800f82f0`
- `0x1800f8314`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ef6f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ef6f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ef697`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ef697`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800ef878`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800ef878`

## string_xrefs

- `0x1800ef818`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\ConfigProvider.h`
- `0x1800ef70a`: `Provider %d down, scheduling task to refresh Geo+KV`
- `0x1800ef717`: `CGlobalConfigManager::NotifyProviderDown`
- `0x1800ef90c`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\KeyValueProvider.cpp`
- `0x1800ef99d`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\KeyValueProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
__int64 __fastcall CKeyValueProvider::RefreshConfigs(
        RTL_SRWLOCK **this,
        char a2,
        void *a3,
        struct TraceLoggingCorrelationVector *a4)
{
  unsigned int v6; // edi
  __int64 v8; // rcx
  int v9; // esi
  RTL_SRWLOCK *v10; // rbx
  RTL_SRWLOCK *v11; // r12
  RTL_SRWLOCK *v12; // r14
  _QWORD *Ptr; // rsi
  __int64 *v14; // r15
  __int64 *v15; // rbx
  CGlobalConfigManager *v16; // rbx
  RTL_SRWLOCK *v17; // rcx
  volatile signed __int32 *v18; // r14
  int v19; // eax
  volatile signed __int32 *v20; // rsi
  signed __int64 v21; // r8
  int StatePath; // eax
  unsigned int v23; // ebx
  const char *v24; // rcx
  int v25; // [rsp+20h] [rbp-B8h]
  __int64 v26; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+38h] [rbp-A0h] BYREF
  char *v28[2]; // [rsp+40h] [rbp-98h] BYREF
  __m128i si128; // [rsp+50h] [rbp-88h]
  _OWORD v30[2]; // [rsp+60h] [rbp-78h] BYREF
  _OWORD v31[2]; // [rsp+80h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  CServiceConfigProvider::_UpdateSvcCommTracker((CServiceConfigProvider *)this);
  v6 = 0;
  if ( !a2 && !CPeriodicOpTracker::TimeForNextCall((CPeriodicOpTracker *)(this + 12)) )
    return 1;
  LOBYTE(v26) = 0;
  v30[0] = 0;
  v30[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v30[0]) = 0;
  v9 = CKeyValueProvider::_ConstructRequestUrl(this, v30);
  if ( v9 >= 0 )
  {
    LODWORD(v28[0]) = 0;
    v9 = CServiceConfigProvider::_CallService((CServiceConfigProvider *)this, (__int64)v28, (__int64)&v26);
    if ( v9 >= 0 )
    {
      v10 = this[11];
      v11 = v10 + 71;
      AcquireSRWLockExclusive(v10 + 71);
      v12 = v10 + 69;
      Ptr = v10[69].Ptr;
      v14 = (__int64 *)Ptr[1];
      while ( !*((_BYTE *)v14 + 25) )
      {
        std::_Tree_val<std::_Tree_simple_types<std::string>>::_Erase_tree<std::allocator<std::_Tree_node<std::string,void *>>>(
          v12,
          v12,
          v14[2]);
        v15 = v14;
        v14 = (__int64 *)*v14;
        std::string::~string(v15 + 4);
        operator delete(v15);
      }
      Ptr[1] = Ptr;
      *Ptr = Ptr;
      Ptr[2] = Ptr;
      v12[1].Ptr = 0;
      ReleaseSRWLockExclusive(v11);
      goto LABEL_36;
    }
    if ( LODWORD(v28[0]) >= 2 )
    {
      v16 = (CGlobalConfigManager *)this[11];
      LogMessage(
        5u,
        "CGlobalConfigManager::NotifyProviderDown",
        0x156u,
        "Provider %d down, scheduling task to refresh Geo+KV",
        0);
      CGlobalConfigManager::RefreshRemoteProvidersAsync(v16, 0);
    }
  }
  if ( !*((_BYTE *)this + 216) )
  {
    v31[0] = 0;
    v31[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v31[0]) = 0;
    if ( (int)CKeyValueProvider::_LoadKV(v8, v31) < 0 )
      goto LABEL_35;
    v27 = 0;
    v17 = this[26];
    *(_OWORD *)v28 = 0;
    if ( (*((int (__fastcall **)(RTL_SRWLOCK *, __int64, char **))v17->Ptr + 1))(v17, 76, v28) >= 0 )
    {
      v19 = CConvert::FromVariantNoThrow<unsigned __int64,std::monostate,bool,int,unsigned int,__int64,unsigned __int64,double,std::string>(
              v28[0],
              &v27);
      if ( v19 >= 0 )
      {
        v20 = (volatile signed __int32 *)v28[1];
        if ( v28[1] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v28[1] + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
            if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
          }
        }
        v28[0] = 0;
        GetSystemTimePreciseAsFileTime(v28);
        v21 = LODWORD(v28[0]) + ((unsigned __int64)HIDWORD(v28[0]) << 32) - 116444736000000000LL;
        if ( v27 - 116444736000000000LL == v21 || v27 - 116444736000000000LL < v21 )
        {
          v9 = -2147020495;
        }
        else
        {
          v9 = CKeyValueProvider::_ProcessJsonResponseInternal(this, v31, &v26);
          if ( v9 >= 0 )
            goto LABEL_35;
        }
        *(_OWORD *)v28 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOBYTE(v28[0]) = 0;
        StatePath = CPersistenceLocation::GetStatePath("keyValueLKG.dat", v28);
        v23 = StatePath;
        if ( StatePath < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x40,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\KeyValueProvider.cpp",
            (const char *)(unsigned int)StatePath,
            v25);
          std::string::~string(v28);
          std::string::~string(v31);
          std::string::~string(v30);
          return v23;
        }
        v24 = (const char *)v28;
        if ( si128.m128i_i64[1] > 0xFuLL )
          v24 = v28[0];
        CFile::Delete(v24);
        std::string::~string(v28);
LABEL_35:
        std::string::~string(v31);
        if ( v9 >= 0 )
        {
LABEL_36:
          LOBYTE(v6) = (_BYTE)v26 == 0;
          std::string::~string(v30);
          return v6;
        }
        goto LABEL_37;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\ConfigProvider.h",
        (const char *)(unsigned int)v19,
        v25);
    }
    v18 = (volatile signed __int32 *)v28[1];
    if ( v28[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v28[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    goto LABEL_35;
  }
LABEL_37:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x46,
    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\KeyValueProvider.cpp",
    (const char *)(unsigned int)v9,
    v25);
  std::string::~string(v30);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800ef5d0  mov     [rsp+arg_8], rbx
0x1800ef5d5  push    rsi
0x1800ef5d6  push    rdi
0x1800ef5d7  push    r12
0x1800ef5d9  push    r14
0x1800ef5db  push    r15
0x1800ef5dd  sub     rsp, 0B0h
0x1800ef5e4  mov     rax, cs:__security_cookie
0x1800ef5eb  xor     rax, rsp
0x1800ef5ee  mov     [rsp+0D8h+var_38], rax
0x1800ef5f6  mov     r12, r9
0x1800ef5f9  mov     r15, r8
0x1800ef5fc  mov     bl, dl
0x1800ef5fe  mov     r14, rcx
0x1800ef601  call    ?_UpdateSvcCommTracker@CServiceConfigProvider@@IEAAXXZ; CServiceConfigProvider::_UpdateSvcCommTracker(void)
0x1800ef606  xor     edi, edi
0x1800ef608  test    bl, bl
0x1800ef60a  jnz     short loc_1800EF621
0x1800ef60c  lea     rcx, [r14+60h]; this
0x1800ef610  call    ?TimeForNextCall@CPeriodicOpTracker@@QEBA_NXZ; CPeriodicOpTracker::TimeForNextCall(void)
0x1800ef615  test    al, al
0x1800ef617  jnz     short loc_1800EF621
0x1800ef619  lea     eax, [rdi+1]
0x1800ef61c  jmp     loc_1800EF9C8
0x1800ef621  mov     byte ptr [rsp+0D8h+var_A8], dil
0x1800ef626  xorps   xmm0, xmm0
0x1800ef629  movups  [rsp+0D8h+var_78], xmm0
0x1800ef62e  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800ef636  movdqu  [rsp+0D8h+var_68], xmm1
0x1800ef63c  mov     byte ptr [rsp+0D8h+var_78], dil
0x1800ef641  lea     rdx, [rsp+0D8h+var_78]
0x1800ef646  mov     rcx, r14
0x1800ef649  call    ?_ConstructRequestUrl@CKeyValueProvider@@AEBAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CKeyValueProvider::_ConstructRequestUrl(std::string &)
0x1800ef64e  mov     esi, eax
0x1800ef650  test    eax, eax
0x1800ef652  js      loc_1800EF732
0x1800ef658  mov     dword ptr [rsp+0D8h+var_98], edi
0x1800ef65c  lea     rax, [rsp+0D8h+var_A8]
0x1800ef661  mov     [rsp+0D8h+var_B0], rax; __int64
0x1800ef666  lea     rax, [rsp+0D8h+var_98]
0x1800ef66b  mov     [rsp+0D8h+var_B8], rax; __int64
0x1800ef670  mov     r9, r12
0x1800ef673  mov     r8, r15
0x1800ef676  lea     rdx, [rsp+0D8h+var_78]
0x1800ef67b  mov     rcx, r14; this
0x1800ef67e  call    ?_CallService@CServiceConfigProvider@@IEAAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAXPEAVTraceLoggingCorrelationVector@@PEAIPEA_N@Z; CServiceConfigProvider::_CallService(std::string const &,void *,TraceLoggingCorrelationVector *,uint *,bool *)
0x1800ef683  mov     esi, eax
0x1800ef685  test    eax, eax
0x1800ef687  js      short loc_1800EF6FB
0x1800ef689  mov     rbx, [r14+58h]
0x1800ef68d  lea     r12, [rbx+238h]
0x1800ef694  mov     rcx, r12; SRWLock
0x1800ef697  call    cs:__imp_AcquireSRWLockExclusive
0x1800ef69d  lea     r14, [rbx+228h]
0x1800ef6a4  mov     rsi, [r14]
0x1800ef6a7  mov     r15, [rsi+8]
0x1800ef6ab  jmp     short loc_1800EF6D8
0x1800ef6ad  mov     r8, [r15+10h]
0x1800ef6b1  mov     rdx, r14
0x1800ef6b4  mov     rcx, r14
0x1800ef6b7  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::string>>::_Erase_tree<std::allocator<std::_Tree_node<std::string,void *>>>(std::allocator<std::_Tree_node<std::string,void *>> &,std::_Tree_node<std::string,void *> *)
0x1800ef6bc  mov     rbx, r15
0x1800ef6bf  mov     r15, [r15]
0x1800ef6c2  lea     rcx, [rbx+20h]; void *
0x1800ef6c6  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ef6cb  mov     edx, 40h ; '@'
0x1800ef6d0  mov     rcx, rbx; Block
0x1800ef6d3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ef6d8  cmp     [r15+19h], dil
0x1800ef6dc  jz      short loc_1800EF6AD
0x1800ef6de  mov     [rsi+8], rsi
0x1800ef6e2  mov     [rsi], rsi
0x1800ef6e5  mov     [rsi+10h], rsi
0x1800ef6e9  mov     [r14+8], rdi
0x1800ef6ed  mov     rcx, r12; SRWLock
0x1800ef6f0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ef6f6  jmp     loc_1800EF97B
0x1800ef6fb  cmp     dword ptr [rsp+0D8h+var_98], 2
0x1800ef700  jb      short loc_1800EF732
0x1800ef702  mov     rbx, [r14+58h]
0x1800ef706  mov     dword ptr [rsp+0D8h+var_B8], edi; int
0x1800ef70a  lea     r9, aProviderDDownS; "Provider %d down, scheduling task to re"...
0x1800ef711  mov     r8d, 156h; unsigned int
0x1800ef717  lea     rdx, aCglobalconfigm_12; "CGlobalConfigManager::NotifyProviderDow"...
0x1800ef71e  mov     ecx, 5; unsigned __int8
0x1800ef723  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800ef728  xor     edx, edx; void *
0x1800ef72a  mov     rcx, rbx; this
0x1800ef72d  call    ?RefreshRemoteProvidersAsync@CGlobalConfigManager@@QEAAXPEAX@Z; CGlobalConfigManager::RefreshRemoteProvidersAsync(void *)
0x1800ef732  cmp     [r14+0D8h], dil
0x1800ef739  jnz     loc_1800EF992
0x1800ef73f  xorps   xmm0, xmm0
0x1800ef742  movups  [rsp+0D8h+var_58], xmm0
0x1800ef74a  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800ef752  movdqu  [rsp+0D8h+var_48], xmm1
0x1800ef75b  mov     byte ptr [rsp+0D8h+var_58], dil
0x1800ef763  lea     rdx, [rsp+0D8h+var_58]
0x1800ef76b  call    ?_LoadKV@CKeyValueProvider@@AEAAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CKeyValueProvider::_LoadKV(std::string &)
0x1800ef770  test    eax, eax
0x1800ef772  js      loc_1800EF96A
0x1800ef778  mov     [rsp+0D8h+var_A0], rdi
0x1800ef77d  mov     rcx, [r14+0D0h]
0x1800ef784  xorps   xmm1, xmm1
0x1800ef787  movdqu  xmmword ptr [rsp+0D8h+var_98], xmm1
0x1800ef78d  mov     rax, [rcx]
0x1800ef790  lea     r8, [rsp+0D8h+var_98]
0x1800ef795  mov     edx, 4Ch ; 'L'
0x1800ef79a  mov     rax, [rax+8]
0x1800ef79e  call    _guard_dispatch_icall
0x1800ef7a3  test    eax, eax
0x1800ef7a5  jns     short loc_1800EF7FA
0x1800ef7a7  mov     r14, [rsp+0D8h+var_98+8]
0x1800ef7ac  test    r14, r14
0x1800ef7af  jz      loc_1800EF96A
0x1800ef7b5  or      ebx, 0FFFFFFFFh
0x1800ef7b8  mov     eax, ebx
0x1800ef7ba  lock xadd [r14+8], eax
0x1800ef7c0  add     eax, ebx
0x1800ef7c2  jnz     loc_1800EF96A
0x1800ef7c8  mov     rax, [r14]
0x1800ef7cb  mov     rcx, r14
0x1800ef7ce  mov     rax, [rax]
0x1800ef7d1  call    _guard_dispatch_icall
0x1800ef7d6  mov     eax, ebx
0x1800ef7d8  lock xadd [r14+0Ch], eax
0x1800ef7de  add     eax, ebx
0x1800ef7e0  jnz     loc_1800EF96A
0x1800ef7e6  mov     rax, [r14]
0x1800ef7e9  mov     rcx, r14
0x1800ef7ec  mov     rax, [rax+8]
0x1800ef7f0  call    _guard_dispatch_icall
0x1800ef7f5  jmp     loc_1800EF96A
0x1800ef7fa  lea     rdx, [rsp+0D8h+var_A0]
0x1800ef7ff  mov     rcx, [rsp+0D8h+var_98]
0x1800ef804  call    ??$FromVariantNoThrow@_KUmonostate@std@@_NHI_J_KNV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@CConvert@@SAJAEBV?$variant@Umonostate@std@@_NHI_J_KNV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@std@@AEA_K@Z; CConvert::FromVariantNoThrow<unsigned __int64,std::monostate,bool,int,uint,__int64,unsigned __int64,double,std::string>(std::variant<std::monostate,bool,int,uint,__int64,unsigned __int64,double,std::string> const &,unsigned __int64 &)
0x1800ef809  test    eax, eax
0x1800ef80b  jns     short loc_1800EF82E
0x1800ef80d  mov     rcx, [rsp+0D8h]; this
0x1800ef815  mov     r9d, eax; char *
0x1800ef818  lea     r8, aCW1SSrcDeliver_3; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ef81f  mov     edx, 47h ; 'G'; void *
0x1800ef824  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ef829  jmp     loc_1800EF7A7
0x1800ef82e  mov     rsi, [rsp+0D8h+var_98+8]
0x1800ef833  test    rsi, rsi
0x1800ef836  jz      short loc_1800EF86E
0x1800ef838  or      ebx, 0FFFFFFFFh
0x1800ef83b  mov     eax, ebx
0x1800ef83d  lock xadd [rsi+8], eax
0x1800ef842  add     eax, ebx
0x1800ef844  jnz     short loc_1800EF86E
0x1800ef846  mov     rax, [rsi]
0x1800ef849  mov     rcx, rsi
0x1800ef84c  mov     rax, [rax]
0x1800ef84f  call    _guard_dispatch_icall
0x1800ef854  mov     eax, ebx
0x1800ef856  lock xadd [rsi+0Ch], eax
0x1800ef85b  add     eax, ebx
0x1800ef85d  jnz     short loc_1800EF86E
0x1800ef85f  mov     rax, [rsi]
0x1800ef862  mov     rcx, rsi
0x1800ef865  mov     rax, [rax+8]
0x1800ef869  call    _guard_dispatch_icall
0x1800ef86e  mov     [rsp+0D8h+var_98], rdi
0x1800ef873  lea     rcx, [rsp+0D8h+var_98]
0x1800ef878  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800ef87e  mov     r8d, dword ptr [rsp+0D8h+var_98+4]
0x1800ef883  shl     r8, 20h
0x1800ef887  mov     edx, dword ptr [rsp+0D8h+var_98]
0x1800ef88b  mov     rcx, 0FE624E212AC18000h
0x1800ef895  add     r8, rcx
0x1800ef898  add     r8, rdx
0x1800ef89b  mov     rdx, [rsp+0D8h+var_A0]
0x1800ef8a0  add     rdx, rcx
0x1800ef8a3  cmp     rdx, r8
0x1800ef8a6  jz      short loc_1800EF8CA
0x1800ef8a8  jl      short loc_1800EF8CA
0x1800ef8aa  lea     r8, [rsp+0D8h+var_A8]
0x1800ef8af  lea     rdx, [rsp+0D8h+var_58]
0x1800ef8b7  mov     rcx, r14
0x1800ef8ba  call    ?_ProcessJsonResponseInternal@CKeyValueProvider@@AEAAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEA_N@Z; CKeyValueProvider::_ProcessJsonResponseInternal(std::string const &,bool *)
0x1800ef8bf  mov     esi, eax
0x1800ef8c1  test    eax, eax
0x1800ef8c3  js      short loc_1800EF8CF
0x1800ef8c5  jmp     loc_1800EF96A
0x1800ef8ca  mov     esi, 80071131h
0x1800ef8cf  xorps   xmm0, xmm0
0x1800ef8d2  movups  xmmword ptr [rsp+0D8h+var_98], xmm0
0x1800ef8d7  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800ef8df  movdqu  [rsp+0D8h+var_88], xmm1
0x1800ef8e5  mov     byte ptr [rsp+0D8h+var_98], dil
0x1800ef8ea  lea     rdx, [rsp+0D8h+var_98]
0x1800ef8ef  lea     rcx, aKeyvaluelkgDat; "keyValueLKG.dat"
0x1800ef8f6  call    ?GetStatePath@CPersistenceLocation@@SAJPEBDAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CPersistenceLocation::GetStatePath(char const *,std::string &)
0x1800ef8fb  mov     ebx, eax
0x1800ef8fd  test    eax, eax
0x1800ef8ff  jns     short loc_1800EF948
0x1800ef901  mov     rcx, [rsp+0D8h]; this
0x1800ef909  mov     r9d, eax; char *
0x1800ef90c  lea     r8, aCW1SSrcDeliver_86; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ef913  mov     edx, 40h ; '@'; void *
0x1800ef918  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ef91d  nop
0x1800ef91e  lea     rcx, [rsp+0D8h+var_98]; void *
0x1800ef923  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ef928  nop
0x1800ef929  lea     rcx, [rsp+0D8h+var_58]; void *
0x1800ef931  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ef936  nop
0x1800ef937  lea     rcx, [rsp+0D8h+var_78]; void *
0x1800ef93c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ef941  mov     eax, ebx
0x1800ef943  jmp     loc_1800EF9C8
0x1800ef948  lea     rcx, [rsp+0D8h+var_98]
0x1800ef94d  cmp     qword ptr [rsp+0D8h+var_88+8], 0Fh
0x1800ef953  cmova   rcx, [rsp+0D8h+var_98]; char *
0x1800ef959  call    ?Delete@CFile@@SAJPEBD@Z; CFile::Delete(char const *)
0x1800ef95e  nop
0x1800ef95f  lea     rcx, [rsp+0D8h+var_98]; void *
0x1800ef964  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ef969  nop
0x1800ef96a  lea     rcx, [rsp+0D8h+var_58]; void *
0x1800ef972  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ef977  test    esi, esi
0x1800ef979  js      short loc_1800EF992
0x1800ef97b  cmp     byte ptr [rsp+0D8h+var_A8], dil
0x1800ef980  setz    dil
0x1800ef984  lea     rcx, [rsp+0D8h+var_78]; void *
0x1800ef989  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ef98e  mov     eax, edi
0x1800ef990  jmp     short loc_1800EF9C8
0x1800ef992  mov     rcx, [rsp+0D8h]; this
0x1800ef99a  mov     r9d, esi; char *
0x1800ef99d  lea     r8, aCW1SSrcDeliver_86; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ef9a4  mov     edx, 46h ; 'F'; void *
0x1800ef9a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ef9ae  nop
0x1800ef9af  lea     rcx, [rsp+0D8h+var_78]; void *
0x1800ef9b4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ef9b9  mov     eax, esi
0x1800ef9bb  jmp     short loc_1800EF9C8
0x1800ef9bd  mov     eax, 8007000Eh
0x1800ef9c2  jmp     short loc_1800EF9C8
0x1800ef9c4  mov     eax, dword ptr [rsp+0D8h+var_98]
0x1800ef9c8  mov     rcx, [rsp+0D8h+var_38]
0x1800ef9d0  xor     rcx, rsp; StackCookie
0x1800ef9d3  call    __security_check_cookie
0x1800ef9d8  mov     rbx, [rsp+0D8h+arg_8]
0x1800ef9e0  add     rsp, 0B0h
0x1800ef9e7  pop     r15
0x1800ef9e9  pop     r14
0x1800ef9eb  pop     r12
0x1800ef9ed  pop     rdi
0x1800ef9ee  pop     rsi
0x1800ef9ef  retn
```
