# CGlobalConfigManager::_UpdateWorkingDirIfNeeded(_ConfigProviderType *)

- ea: `0x1800dae88`
- end: `0x1800db3f1`
- name: `?_UpdateWorkingDirIfNeeded@CGlobalConfigManager@@AEAAJPEAW4_ConfigProviderType@@@Z`
- size: `1385`
- prototype: `__int64 __fastcall(CGlobalConfigManager *__hidden this, enum _ConfigProviderType *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800d86e4`

## callees

- `0x18000933c`
- `0x1800095a0`
- `0x18000f014`
- `0x180071330`
- `0x1800714b0`
- `0x18009b368`
- `0x1800a1ea4`
- `0x1800a66f4`
- `0x1800dae88`
- `0x1800db484`
- `0x1800ed4ec`
- `0x1800ed774`
- `0x1800f82f0`
- `0x1800f8320`
- `0x1800f874c`
- `0x180107cbc`
- `0x180107d24`
- `0x180108e50`
- `0x1801099b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800daf06`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800daf06`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800daf24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800daf24`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800daf6c`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800daf6c`

## string_xrefs

- `0x1800db07f`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\GlobalConfigManager.cpp`
- `0x1800db11a`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\GlobalConfigManager.cpp`
- `0x1800db267`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\GlobalConfigManager.cpp`
- `0x1800db1a9`: `Ignoring new cache path on smaller drive: %s`
- `0x1800db1b6`: `CGlobalConfigManager::_UpdateWorkingDirIfNeeded`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CGlobalConfigManager::_UpdateWorkingDirIfNeeded(const void ***this, enum _ConfigProviderType *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rbx
  RTL_SRWLOCK *v5; // rsi
  __int64 v6; // rax
  volatile signed __int32 *v7; // rbx
  const void **v8; // rsi
  const void *v9; // rdx
  void **v10; // rcx
  void **v11; // r14
  size_t v12; // r12
  void **v13; // rdx
  void **v14; // rcx
  int DiskSpace; // eax
  unsigned int v16; // esi
  void **v17; // rdx
  int v18; // eax
  void **v19; // rax
  const char *v20; // r9
  __int64 result; // rax
  void **v22; // rcx
  int v23; // eax
  _DWORD *v24; // rax
  int v25; // [rsp+20h] [rbp-B8h]
  unsigned __int64 v26; // [rsp+30h] [rbp-A8h] BYREF
  unsigned __int64 v27[2]; // [rsp+38h] [rbp-A0h] BYREF
  __int128 v28; // [rsp+48h] [rbp-90h]
  void *Buf1[2]; // [rsp+58h] [rbp-80h] BYREF
  size_t Size[2]; // [rsp+68h] [rbp-70h]
  int v31; // [rsp+78h] [rbp-60h]
  void *Buf2[2]; // [rsp+80h] [rbp-58h] BYREF
  __int64 v33; // [rsp+90h] [rbp-48h]
  unsigned __int64 v34; // [rsp+98h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  try
  {
    v3 = 4;
    if ( dword_180195E30 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_180195E30);
      if ( dword_180195E30 == -1 )
      {
        CDOCachePath::CDOCachePath(v3, this, 30000);
        atexit(CGlobalConfigManager::_UpdateWorkingDirIfNeeded_::_3_::_dynamic_atexit_destructor_for__cachePath__);
        Init_thread_footer(&dword_180195E30);
      }
    }
    CDOCachePath::_TryRefresh((CDOCachePath *)v3);
    v4 = xmmword_180195E40;
    v27[1] = 1;
    v5 = (RTL_SRWLOCK *)(xmmword_180195E40 + 40);
    v27[0] = xmmword_180195E40 + 40;
    AcquireSRWLockShared((PSRWLOCK)(xmmword_180195E40 + 40));
    std::string::string(Buf1, v4);
    v31 = *(_DWORD *)(v4 + 32);
    ReleaseSRWLockShared(v5);
    v28 = 0;
    v6 = std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load(this + 23);
    v7 = (volatile signed __int32 *)v6;
    v8 = this[22];
    *(_QWORD *)&v28 = v8;
    *((_QWORD *)&v28 + 1) = v6;
    if ( v6 )
      _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
    if ( (_InterlockedExchange64((volatile __int64 *)this + 23, v6) & 3) == 2 )
      WakeByAddressAll(this + 23);
    v9 = v8;
    if ( (unsigned __int64)v8[3] > 0xF )
      v9 = *v8;
    v10 = Buf1;
    v11 = (void **)Buf1[0];
    v12 = Size[1];
    if ( Size[1] > 0xF )
      v10 = (void **)Buf1[0];
    if ( (const void *)Size[0] != v8[2] || Size[0] && memcmp(v10, v9, Size[0]) )
    {
      if ( v31 == 99 )
      {
        *(_OWORD *)Buf2 = 0;
        v33 = 0;
        v34 = 15;
        LOBYTE(Buf2[0]) = 0;
        CPersistenceLocation::GetDefaultCachePath(Buf2);
        v13 = Buf2;
        if ( v34 > 0xF )
          v13 = (void **)Buf2[0];
        v14 = Buf1;
        if ( Size[1] > 0xF )
          v14 = (void **)Buf1[0];
        if ( Size[0] != v33 || Size[0] && memcmp(v14, v13, Size[0]) )
        {
          v26 = 0;
          v27[0] = 0;
          if ( (unsigned __int64)v8[3] > 0xF )
            v8 = (const void **)*v8;
          DiskSpace = CGlobalConfigManager::_GetDiskSpace((CGlobalConfigManager *)this, (const char *)v8, 0, &v26);
          v16 = DiskSpace;
          if ( DiskSpace < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xADE,
              (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\GlobalConfigManager.cpp",
              (const char *)(unsigned int)DiskSpace,
              v25);
            std::string::~string(Buf2);
            if ( v7 )
            {
              if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
                if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
              }
            }
LABEL_55:
            std::string::~string(Buf1);
            return v16;
          }
          v17 = Buf1;
          if ( Size[1] > 0xF )
            v17 = (void **)Buf1[0];
          v18 = CGlobalConfigManager::_GetDiskSpace((CGlobalConfigManager *)this, (const char *)v17, 0, v27);
          v16 = v18;
          if ( v18 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xADF,
              (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\GlobalConfigManager.cpp",
              (const char *)(unsigned int)v18,
              v25);
            std::string::~string(Buf2);
            if ( v7 )
            {
              if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
                if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
              }
            }
            goto LABEL_55;
          }
          if ( v27[0] < v26 )
          {
            v19 = Buf1;
            if ( Size[1] > 0xF )
              v19 = (void **)Buf1[0];
            LogMessage(
              3u,
              "CGlobalConfigManager::_UpdateWorkingDirIfNeeded",
              0xAE2u,
              "Ignoring new cache path on smaller drive: %s",
              (const char *)v19);
            std::string::~string(Buf2);
            if ( v7 )
            {
              if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
                if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
              }
            }
            std::string::~string(Buf1);
            return 1;
          }
        }
        std::string::~string(Buf2);
        v12 = Size[1];
        v11 = (void **)Buf1[0];
      }
      if ( !*((_BYTE *)this + 686) )
      {
        v22 = Buf1;
        if ( v12 > 0xF )
          v22 = v11;
        v23 = CPath::VerifyAccess((const char *)v22);
        v16 = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAEC,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\GlobalConfigManager.cpp",
            (const char *)(unsigned int)v23,
            v25);
          if ( v7 )
          {
            if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
              if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
            }
          }
          goto LABEL_55;
        }
      }
      v24 = operator new(0x30u);
      v24[2] = 1;
      v24[3] = 1;
      *(_QWORD *)v24 = &std::_Ref_count_obj2<std::string>::`vftable';
      *((_OWORD *)v24 + 1) = *(_OWORD *)Buf1;
      *((_OWORD *)v24 + 2) = *(_OWORD *)Size;
      Size[0] = 0;
      Size[1] = 15;
      LOBYTE(Buf1[0]) = 0;
      v27[0] = (unsigned __int64)(v24 + 4);
      v27[1] = (unsigned __int64)v24;
      std::atomic<std::shared_ptr<HttpResponseInfo>>::operator=(this + 22, v27);
    }
    if ( v7 )
    {
      if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *, const void *))v7)(v7, v9);
        if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
    std::string::~string(Buf1);
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xAF3,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\GlobalConfigManager.cpp",
                           v20);
  }
  return result;
}

```

## disassembly

```asm
0x1800dae88  mov     [rsp+arg_8], rbx
0x1800dae8d  mov     [rsp+arg_10], rsi
0x1800dae92  push    rdi
0x1800dae93  push    r12
0x1800dae95  push    r13
0x1800dae97  push    r14
0x1800dae99  push    r15
0x1800dae9b  sub     rsp, 0B0h
0x1800daea2  mov     rax, cs:__security_cookie
0x1800daea9  xor     rax, rsp
0x1800daeac  mov     [rsp+0D8h+var_38], rax
0x1800daeb4  mov     r15, rcx
0x1800daeb7  mov     edx, cs:_tls_index
0x1800daebd  mov     rax, gs:58h
0x1800daec6  mov     ecx, 4; this
0x1800daecb  mov     rax, [rax+rdx*8]
0x1800daecf  mov     edx, [rcx+rax]
0x1800daed2  cmp     cs:dword_180195E30, edx
0x1800daed8  jg      loc_1800DB3A8
0x1800daede  or      edi, 0FFFFFFFFh
0x1800daee1  call    ?_TryRefresh@CDOCachePath@@AEAAXXZ; CDOCachePath::_TryRefresh(void)
0x1800daee6  mov     rbx, qword ptr cs:xmmword_180195E40
0x1800daeed  xorps   xmm0, xmm0
0x1800daef0  movups  xmmword ptr [rsp+0D8h+var_A0], xmm0
0x1800daef5  lea     rsi, [rbx+28h]
0x1800daef9  mov     [rsp+0D8h+var_A0], rsi
0x1800daefe  mov     byte ptr [rsp+0D8h+var_A0+8], 1
0x1800daf03  mov     rcx, rsi; SRWLock
0x1800daf06  call    cs:__imp_AcquireSRWLockShared
0x1800daf0c  nop
0x1800daf0d  mov     rdx, rbx
0x1800daf10  lea     rcx, [rsp+0D8h+Buf1]
0x1800daf15  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1800daf1a  mov     eax, [rbx+20h]
0x1800daf1d  mov     [rsp+0D8h+var_60], eax
0x1800daf21  mov     rcx, rsi; SRWLock
0x1800daf24  call    cs:__imp_ReleaseSRWLockShared
0x1800daf2a  nop
0x1800daf2b  lea     r13, [r15+0B0h]
0x1800daf32  xorps   xmm0, xmm0
0x1800daf35  movups  [rsp+0D8h+var_90], xmm0
0x1800daf3a  lea     r14, [r13+8]
0x1800daf3e  mov     rcx, r14; Address
0x1800daf41  call    ?_Lock_and_load@?$_Locked_pointer@V_Ref_count_base@std@@@std@@QEAAPEAV_Ref_count_base@2@XZ; std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load(void)
0x1800daf46  mov     rbx, rax
0x1800daf49  mov     rsi, [r13+0]
0x1800daf4d  mov     qword ptr [rsp+0D8h+var_90], rsi
0x1800daf52  mov     qword ptr [rsp+0D8h+var_90+8], rax
0x1800daf57  test    rax, rax
0x1800daf5a  jz      short loc_1800DAF60
0x1800daf5c  lock inc dword ptr [rax+8]
0x1800daf60  xchg    rax, [r14]
0x1800daf63  and     al, 3
0x1800daf65  cmp     al, 2
0x1800daf67  jnz     short loc_1800DAF73
0x1800daf69  mov     rcx, r14; Address
0x1800daf6c  call    cs:__imp_WakeByAddressAll
0x1800daf72  nop
0x1800daf73  mov     rdx, rsi
0x1800daf76  cmp     qword ptr [rsi+18h], 0Fh
0x1800daf7b  jbe     short loc_1800DAF80
0x1800daf7d  mov     rdx, [rsi]; Buf2
0x1800daf80  lea     rcx, [rsp+0D8h+Buf1]
0x1800daf85  mov     r14, [rsp+0D8h+Buf1]
0x1800daf8a  mov     r12, [rsp+0D8h+Size+8]
0x1800daf8f  cmp     r12, 0Fh
0x1800daf93  cmova   rcx, r14; Buf1
0x1800daf97  mov     r8, [rsp+0D8h+Size]; Size
0x1800daf9c  cmp     r8, [rsi+10h]
0x1800dafa0  jnz     short loc_1800DAFB8
0x1800dafa2  test    r8, r8
0x1800dafa5  jz      loc_1800DB329
0x1800dafab  call    memcmp
0x1800dafb0  test    eax, eax
0x1800dafb2  jz      loc_1800DB329
0x1800dafb8  cmp     [rsp+0D8h+var_60], 63h ; 'c'
0x1800dafbd  jnz     loc_1800DB23A
0x1800dafc3  xorps   xmm0, xmm0
0x1800dafc6  movups  xmmword ptr [rsp+0D8h+Buf2], xmm0
0x1800dafce  xor     r14d, r14d
0x1800dafd1  mov     [rsp+0D8h+var_48], r14
0x1800dafd9  lea     r12d, [r14+0Fh]
0x1800dafdd  mov     [rsp+0D8h+var_40], r12
0x1800dafe5  mov     byte ptr [rsp+0D8h+Buf2], r14b
0x1800dafed  lea     rcx, [rsp+0D8h+Buf2]; void *
0x1800daff5  call    ?GetDefaultCachePath@CPersistenceLocation@@SAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CPersistenceLocation::GetDefaultCachePath(std::string &)
0x1800daffa  lea     rdx, [rsp+0D8h+Buf2]
0x1800db002  cmp     [rsp+0D8h+var_40], r12
0x1800db00a  cmova   rdx, [rsp+0D8h+Buf2]; Buf2
0x1800db013  lea     rcx, [rsp+0D8h+Buf1]
0x1800db018  cmp     [rsp+0D8h+Size+8], r12
0x1800db01d  cmova   rcx, [rsp+0D8h+Buf1]; Buf1
0x1800db023  mov     r8, [rsp+0D8h+Size]; Size
0x1800db028  cmp     r8, [rsp+0D8h+var_48]
0x1800db030  jnz     short loc_1800DB048
0x1800db032  test    r8, r8
0x1800db035  jz      loc_1800DB223
0x1800db03b  call    memcmp
0x1800db040  test    eax, eax
0x1800db042  jz      loc_1800DB223
0x1800db048  mov     [rsp+0D8h+var_A8], r14
0x1800db04d  mov     [rsp+0D8h+var_A0], r14
0x1800db052  cmp     [rsi+18h], r12
0x1800db056  jbe     short loc_1800DB05B
0x1800db058  mov     rsi, [rsi]
0x1800db05b  lea     r9, [rsp+0D8h+var_A8]; unsigned __int64 *
0x1800db060  xor     r8d, r8d; __int64 *
0x1800db063  mov     rdx, rsi; char *
0x1800db066  mov     rcx, r15; this
0x1800db069  call    ?_GetDiskSpace@CGlobalConfigManager@@AEBAJPEBDPEA_JPEA_K@Z; CGlobalConfigManager::_GetDiskSpace(char const *,__int64 *,unsigned __int64 *)
0x1800db06e  mov     esi, eax
0x1800db070  test    eax, eax
0x1800db072  jns     short loc_1800DB0E9
0x1800db074  mov     rcx, [rsp+0D8h]; this
0x1800db07c  mov     r9d, eax; char *
0x1800db07f  lea     r8, aCW1SSrcDeliver_112; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800db086  mov     edx, 0ADEh; void *
0x1800db08b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800db090  nop
0x1800db091  lea     rcx, [rsp+0D8h+Buf2]; void *
0x1800db099  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800db09e  nop
0x1800db09f  test    rbx, rbx
0x1800db0a2  jz      short loc_1800DB0D8
0x1800db0a4  mov     eax, edi
0x1800db0a6  lock xadd [rbx+8], eax
0x1800db0ab  add     eax, edi
0x1800db0ad  jnz     short loc_1800DB0D8
0x1800db0af  mov     rax, [rbx]
0x1800db0b2  mov     rcx, rbx
0x1800db0b5  mov     rax, [rax]
0x1800db0b8  call    _guard_dispatch_icall
0x1800db0bd  mov     eax, edi
0x1800db0bf  lock xadd [rbx+0Ch], eax
0x1800db0c4  add     eax, edi
0x1800db0c6  jnz     short loc_1800DB0D8
0x1800db0c8  mov     rax, [rbx]
0x1800db0cb  mov     rcx, rbx
0x1800db0ce  mov     rax, [rax+8]
0x1800db0d2  call    _guard_dispatch_icall
0x1800db0d7  nop
0x1800db0d8  lea     rcx, [rsp+0D8h+Buf1]; void *
0x1800db0dd  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800db0e2  mov     eax, esi
0x1800db0e4  jmp     loc_1800DB37B
0x1800db0e9  lea     rdx, [rsp+0D8h+Buf1]
0x1800db0ee  cmp     [rsp+0D8h+Size+8], r12
0x1800db0f3  cmova   rdx, [rsp+0D8h+Buf1]; char *
0x1800db0f9  lea     r9, [rsp+0D8h+var_A0]; unsigned __int64 *
0x1800db0fe  xor     r8d, r8d; __int64 *
0x1800db101  mov     rcx, r15; this
0x1800db104  call    ?_GetDiskSpace@CGlobalConfigManager@@AEBAJPEBDPEA_JPEA_K@Z; CGlobalConfigManager::_GetDiskSpace(char const *,__int64 *,unsigned __int64 *)
0x1800db109  mov     esi, eax
0x1800db10b  test    eax, eax
0x1800db10d  jns     short loc_1800DB184
0x1800db10f  mov     rcx, [rsp+0D8h]; this
0x1800db117  mov     r9d, eax; char *
0x1800db11a  lea     r8, aCW1SSrcDeliver_112; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800db121  mov     edx, 0ADFh; void *
0x1800db126  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800db12b  nop
0x1800db12c  lea     rcx, [rsp+0D8h+Buf2]; void *
0x1800db134  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800db139  nop
0x1800db13a  test    rbx, rbx
0x1800db13d  jz      short loc_1800DB173
0x1800db13f  mov     eax, edi
0x1800db141  lock xadd [rbx+8], eax
0x1800db146  add     eax, edi
0x1800db148  jnz     short loc_1800DB173
0x1800db14a  mov     rax, [rbx]
0x1800db14d  mov     rcx, rbx
0x1800db150  mov     rax, [rax]
0x1800db153  call    _guard_dispatch_icall
0x1800db158  mov     eax, edi
0x1800db15a  lock xadd [rbx+0Ch], eax
0x1800db15f  add     eax, edi
0x1800db161  jnz     short loc_1800DB173
0x1800db163  mov     rax, [rbx]
0x1800db166  mov     rcx, rbx
0x1800db169  mov     rax, [rax+8]
0x1800db16d  call    _guard_dispatch_icall
0x1800db172  nop
0x1800db173  lea     rcx, [rsp+0D8h+Buf1]; void *
0x1800db178  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800db17d  mov     eax, esi
0x1800db17f  jmp     loc_1800DB37B
0x1800db184  mov     rax, [rsp+0D8h+var_A8]
0x1800db189  cmp     [rsp+0D8h+var_A0], rax
0x1800db18e  jnb     loc_1800DB223
0x1800db194  lea     rax, [rsp+0D8h+Buf1]
0x1800db199  cmp     [rsp+0D8h+Size+8], r12
0x1800db19e  cmova   rax, [rsp+0D8h+Buf1]
0x1800db1a4  mov     qword ptr [rsp+0D8h+var_B8], rax
0x1800db1a9  lea     r9, aIgnoringNewCac; "Ignoring new cache path on smaller driv"...
0x1800db1b0  mov     r8d, 0AE2h; unsigned int
0x1800db1b6  lea     rdx, aCglobalconfigm_9; "CGlobalConfigManager::_UpdateWorkingDir"...
0x1800db1bd  mov     ecx, 3; unsigned __int8
0x1800db1c2  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800db1c7  nop
0x1800db1c8  lea     rcx, [rsp+0D8h+Buf2]; void *
0x1800db1d0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800db1d5  nop
0x1800db1d6  test    rbx, rbx
0x1800db1d9  jz      short loc_1800DB20F
0x1800db1db  mov     eax, edi
0x1800db1dd  lock xadd [rbx+8], eax
0x1800db1e2  add     eax, edi
0x1800db1e4  jnz     short loc_1800DB20F
0x1800db1e6  mov     rax, [rbx]
0x1800db1e9  mov     rcx, rbx
0x1800db1ec  mov     rax, [rax]
0x1800db1ef  call    _guard_dispatch_icall
0x1800db1f4  mov     ecx, edi
0x1800db1f6  lock xadd [rbx+0Ch], ecx
0x1800db1fb  add     ecx, edi
0x1800db1fd  jnz     short loc_1800DB20F
0x1800db1ff  mov     rcx, [rbx]
0x1800db202  mov     rax, [rcx+8]
0x1800db206  mov     rcx, rbx
0x1800db209  call    _guard_dispatch_icall
0x1800db20e  nop
0x1800db20f  lea     rcx, [rsp+0D8h+Buf1]; void *
0x1800db214  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800db219  mov     eax, 1
0x1800db21e  jmp     loc_1800DB37B
0x1800db223  lea     rcx, [rsp+0D8h+Buf2]; void *
0x1800db22b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800db230  mov     r12, [rsp+0D8h+Size+8]
0x1800db235  mov     r14, [rsp+0D8h+Buf1]
0x1800db23a  cmp     byte ptr [r15+2AEh], 0
0x1800db242  jnz     short loc_1800DB2C3
0x1800db244  lea     rcx, [rsp+0D8h+Buf1]
0x1800db249  cmp     r12, 0Fh
0x1800db24d  cmova   rcx, r14; char *
0x1800db251  call    ?VerifyAccess@CPath@@SAJPEBD@Z; CPath::VerifyAccess(char const *)
0x1800db256  mov     esi, eax
0x1800db258  test    eax, eax
0x1800db25a  jns     short loc_1800DB2C3
0x1800db25c  mov     rcx, [rsp+0D8h]; this
0x1800db264  mov     r9d, eax; char *
0x1800db267  lea     r8, aCW1SSrcDeliver_112; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800db26e  mov     edx, 0AECh; void *
0x1800db273  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800db278  nop
0x1800db279  test    rbx, rbx
0x1800db27c  jz      short loc_1800DB2B2
0x1800db27e  mov     eax, edi
0x1800db280  lock xadd [rbx+8], eax
0x1800db285  add     eax, edi
0x1800db287  jnz     short loc_1800DB2B2
0x1800db289  mov     rax, [rbx]
0x1800db28c  mov     rcx, rbx
0x1800db28f  mov     rax, [rax]
0x1800db292  call    _guard_dispatch_icall
0x1800db297  mov     eax, edi
0x1800db299  lock xadd [rbx+0Ch], eax
0x1800db29e  add     eax, edi
0x1800db2a0  jnz     short loc_1800DB2B2
0x1800db2a2  mov     rax, [rbx]
0x1800db2a5  mov     rcx, rbx
0x1800db2a8  mov     rax, [rax+8]
0x1800db2ac  call    _guard_dispatch_icall
0x1800db2b1  nop
0x1800db2b2  lea     rcx, [rsp+0D8h+Buf1]; void *
0x1800db2b7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800db2bc  mov     eax, esi
0x1800db2be  jmp     loc_1800DB37B
0x1800db2c3  mov     ecx, 30h ; '0'; Size
0x1800db2c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800db2cd  mov     dword ptr [rax+8], 1
0x1800db2d4  mov     dword ptr [rax+0Ch], 1
0x1800db2db  lea     rcx, ??_7?$_Ref_count_obj2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::string>::`vftable'
0x1800db2e2  mov     [rax], rcx
0x1800db2e5  lea     rdx, [rax+10h]
0x1800db2e9  movups  xmm0, xmmword ptr [rsp+0D8h+Buf1]
0x1800db2ee  movups  xmmword ptr [rdx], xmm0
0x1800db2f1  movups  xmm1, xmmword ptr [rsp+0D8h+Size]
0x1800db2f6  movups  xmmword ptr [rdx+10h], xmm1
0x1800db2fa  mov     [rsp+0D8h+Size], 0
0x1800db303  mov     [rsp+0D8h+Size+8], 0Fh
0x1800db30c  mov     byte ptr [rsp+0D8h+Buf1], 0
0x1800db311  mov     [rsp+0D8h+var_A0], rdx
0x1800db316  mov     [rsp+0D8h+var_A0+8], rax
0x1800db31b  lea     rdx, [rsp+0D8h+var_A0]
0x1800db320  mov     rcx, r13
0x1800db323  call    ??4?$atomic@V?$shared_ptr@UHttpResponseInfo@@@std@@@std@@QEAAXV?$shared_ptr@UHttpResponseInfo@@@1@@Z; std::atomic<std::shared_ptr<HttpResponseInfo>>::operator=(std::shared_ptr<HttpResponseInfo>)
0x1800db328  nop
0x1800db329  test    rbx, rbx
0x1800db32c  jz      short loc_1800DB362
0x1800db32e  mov     eax, edi
0x1800db330  lock xadd [rbx+8], eax
0x1800db335  add     eax, edi
0x1800db337  jnz     short loc_1800DB362
0x1800db339  mov     rax, [rbx]
0x1800db33c  mov     rcx, rbx
0x1800db33f  mov     rax, [rax]
0x1800db342  call    _guard_dispatch_icall
0x1800db347  mov     eax, edi
0x1800db349  lock xadd [rbx+0Ch], eax
  ... truncated ...
```
