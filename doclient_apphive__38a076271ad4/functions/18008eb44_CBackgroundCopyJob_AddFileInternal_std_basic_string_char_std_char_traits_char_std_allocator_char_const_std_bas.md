# CBackgroundCopyJob::_AddFileInternal(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,uint,DownloadRange const *,unsigned __int64,std::shared_ptr<CBackgroundCopyFile> &)

- ea: `0x18008eb44`
- end: `0x18008f0b6`
- name: `?_AddFileInternal@CBackgroundCopyJob@@AEAAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@00IPEBUDownloadRange@@_KAEAV?$shared_ptr@VCBackgroundCopyFile@@@3@@Z`
- size: `1394`
- prototype: `__int64 __usercall@<rax>(CBackgroundCopyJob *this@<rcx>, int, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18008ca0c`
- `0x180090510`

## callees

- `0x18000933c`
- `0x180014ac4`
- `0x1800199b4`
- `0x180019c5c`
- `0x18001dfc4`
- `0x1800604f8`
- `0x18008024c`
- `0x180080534`
- `0x180082d0c`
- `0x1800848b0`
- `0x180087f0c`
- `0x18008eb44`
- `0x18008f0bc`
- `0x18008f9d8`
- `0x1800928e4`
- `0x180094720`
- `0x1800955f4`
- `0x18009a2d4`
- `0x1800e8988`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ee84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008eee7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ef78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ee84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008eee7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ef78`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008ef04`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008ef04`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18008efbe`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18008efbe`

## string_xrefs

- `0x18008eb98`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008ebf8`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008ed27`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008edae`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008ee5d`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CBackgroundCopyJob::_AddFileInternal(
        CBackgroundCopyJob *this,
        _QWORD *a2,
        __int64 a3,
        const char *a4,
        int a5,
        __int64 a6,
        int a7,
        __int64 a8)
{
  _QWORD *v11; // rcx
  int v12; // eax
  unsigned int v13; // ebx
  __int64 result; // rax
  int File; // eax
  unsigned int v16; // r14d
  const char *v17; // r9
  char v18; // cl
  char v19; // r14
  volatile signed __int32 *v20; // rdi
  const char *v21; // rdx
  CBackgroundCopyFile *v22; // r12
  int v23; // eax
  unsigned int v24; // r14d
  volatile signed __int32 *v25; // rdi
  int v26; // eax
  unsigned int v27; // r14d
  volatile signed __int32 *v28; // rdi
  int v29; // eax
  unsigned int v30; // r14d
  bool v31; // zf
  volatile signed __int32 *v32; // rdi
  CBackgroundCopyFile **v33; // rdx
  volatile signed __int32 *v34; // rdi
  __int64 v35; // r14
  struct IPersistedEntity *v36; // rdx
  unsigned int Config; // r14d
  bool IsForeground; // al
  int v39; // [rsp+20h] [rbp-78h]
  __int128 v40; // [rsp+30h] [rbp-68h] BYREF
  CBackgroundCopyFile *v41[2]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v42; // [rsp+50h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v42 = a8;
  v11 = a2;
  if ( a2[3] > 0xFu )
    v11 = (_QWORD *)*a2;
  v12 = ValidateFileId(v11);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x616,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
      (const char *)(unsigned int)v12,
      v39);
    return v13;
  }
  *(_OWORD *)v41 = 0;
  try
  {
    File = CBackgroundCopyJob::_CreateFile();
    v16 = File;
    if ( File >= 0 )
    {
      if ( *((_QWORD *)a4 + 2) )
      {
        v18 = *(_BYTE *)(*((_QWORD *)this + 31) + 396LL);
        v19 = v18 == 0;
        if ( !v18 )
        {
          v40 = 0;
          if ( (int)CConfigStore::Find((char *)this + 16, 25, &v40) >= 0 )
          {
            if ( *(_BYTE *)(v40 + 32) != 1 )
              std::_Throw_bad_variant_access();
            v19 = *(_BYTE *)v40;
          }
          v20 = (volatile signed __int32 *)*((_QWORD *)&v40 + 1);
          if ( *((_QWORD *)&v40 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v40 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
              if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
            }
          }
        }
        if ( *((_QWORD *)a4 + 3) > 0xFu )
          a4 = *(const char **)a4;
        v21 = a4;
        v22 = v41[0];
        v23 = CBackgroundCopyFile::SetLocalPathAndCreateFile(v41[0], v21, v19);
        v24 = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x628,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
            (const char *)(unsigned int)v23,
            a7);
          v25 = (volatile signed __int32 *)v41[1];
          if ( v41[1] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41[1] + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
              if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
            }
          }
          return v24;
        }
      }
      else
      {
        v22 = v41[0];
      }
      if ( *(_QWORD *)(a3 + 16) && (v26 = CBackgroundCopyFile::SetRemoteName(v22), v27 = v26, v26 < 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x62C,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
          (const char *)(unsigned int)v26,
          a7);
        v28 = (volatile signed __int32 *)v41[1];
        if ( v41[1] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41[1] + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
            if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
          }
        }
        return v27;
      }
      else
      {
        v40 = (unsigned __int64)this + 136;
        if ( (unsigned int)mtx_do_lock((char *)this + 136) )
          std::_Throw_Cpp_error(5);
        if ( *((_DWORD *)this + 53) == 0x7FFFFFFF )
        {
          *((_DWORD *)this + 53) = 2147483646;
          std::_Throw_Cpp_error(6);
        }
        BYTE8(v40) = 1;
        v29 = CBackgroundCopyJob::_IsJobActiveForIncomingCall(this);
        v30 = v29;
        if ( v29 >= 0 )
        {
          CBackgroundCopyJob::_SetState(this, 0);
          v31 = (*((_DWORD *)this + 53))-- == 1;
          if ( v31 )
          {
            *((_DWORD *)this + 52) = -1;
            ReleaseSRWLockExclusive((PSRWLOCK)this + 19);
          }
          v40 = (unsigned __int64)this + 224;
          AcquireSRWLockExclusive((PSRWLOCK)this + 28);
          BYTE8(v40) = 1;
          v33 = (CBackgroundCopyFile **)*((_QWORD *)this + 9);
          if ( v33 == *((CBackgroundCopyFile ***)this + 10) )
          {
            std::vector<std::shared_ptr<CBackgroundCopyFile>>::_Emplace_reallocate<std::shared_ptr<CBackgroundCopyFile> const &>(
              (char *)this + 64,
              v33,
              v41);
            v34 = (volatile signed __int32 *)v41[1];
            v22 = v41[0];
          }
          else
          {
            *v33 = 0;
            v33[1] = 0;
            v34 = (volatile signed __int32 *)v41[1];
            if ( v41[1] )
              _InterlockedAdd((volatile signed __int32 *)v41[1] + 2, 1u);
            *v33 = v22;
            v33[1] = (CBackgroundCopyFile *)v34;
            *((_QWORD *)this + 9) += 16LL;
          }
          v35 = ((__int64)(*((_QWORD *)this + 9) - *((_QWORD *)this + 8)) >> 4) - 1;
          ReleaseSRWLockExclusive((PSRWLOCK)this + 28);
          v36 = (struct IPersistedEntity *)*((_QWORD *)this + 40);
          if ( v36 )
            CBackgroundCopyFile::SaveFileInfo(v22, v36, v35);
          if ( !v35 )
          {
            Config = CGlobalConfigManager::GetConfigValue<unsigned int>(*((_QWORD *)this + 47), 89);
            *(_QWORD *)&v40 = 0;
            GetSystemTimePreciseAsFileTime(&v40);
            *((_QWORD *)this + 36) = (unsigned int)v40
                                   + ((unsigned __int64)DWORD1(v40) << 32)
                                   + 10000000 * (Config - 0x2B6109100LL);
            CExpirator::AddContentToExpire(*((CExpirator **)this + 48));
          }
          IsForeground = CJobSharedData::IsForeground(*((CJobSharedData **)this + 31));
          CBackgroundCopyFile::SetBackground(v22, !IsForeground);
          std::shared_ptr<std::vector<Microsoft::WRL::ComPtr<IUnknown>>>::operator=(v42, v41);
          if ( v34 )
          {
            if ( _InterlockedExchangeAdd(v34 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
              if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
            }
          }
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x632,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
            (const char *)(unsigned int)v29,
            a7);
          v31 = (*((_DWORD *)this + 53))-- == 1;
          if ( v31 )
          {
            *((_DWORD *)this + 52) = -1;
            ReleaseSRWLockExclusive((PSRWLOCK)this + 19);
          }
          v32 = (volatile signed __int32 *)v41[1];
          if ( v41[1] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41[1] + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
              if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
            }
          }
          return v30;
        }
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x619,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
      (const char *)(unsigned int)File,
      a7);
    if ( v41[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(CBackgroundCopyFile *))v41[1])(v41[1]);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41[1] + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(CBackgroundCopyFile *))(*(_QWORD *)v41[1] + 8LL))(v41[1]);
      }
    }
    result = v16;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x652,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
                           v17);
  }
  return result;
}

```

## disassembly

```asm
0x18008eb44  push    rbx
0x18008eb46  push    rsi
0x18008eb47  push    rdi
0x18008eb48  push    r12
0x18008eb4a  push    r13
0x18008eb4c  push    r14
0x18008eb4e  push    r15
0x18008eb50  sub     rsp, 60h
0x18008eb54  mov     r12, r9
0x18008eb57  mov     r13, r8
0x18008eb5a  mov     rdi, rdx
0x18008eb5d  mov     rsi, rcx
0x18008eb60  mov     r14, [rsp+98h+arg_28]
0x18008eb68  mov     rax, [rsp+98h+arg_38]
0x18008eb70  mov     [rsp+98h+var_48], rax
0x18008eb75  mov     rcx, rdx
0x18008eb78  cmp     qword ptr [rdx+18h], 0Fh
0x18008eb7d  jbe     short loc_18008EB82
0x18008eb7f  mov     rcx, [rdx]
0x18008eb82  call    _ValidateFileId
0x18008eb87  mov     ebx, eax
0x18008eb89  test    eax, eax
0x18008eb8b  jns     short loc_18008EBB0
0x18008eb8d  mov     rcx, [rsp+98h]; this
0x18008eb95  mov     r9d, eax; char *
0x18008eb98  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008eb9f  mov     edx, 616h; void *
0x18008eba4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008eba9  mov     eax, ebx
0x18008ebab  jmp     loc_18008F080
0x18008ebb0  xorps   xmm1, xmm1
0x18008ebb3  movdqu  xmmword ptr [rsp+98h+var_58], xmm1
0x18008ebb9  lea     rax, [rsp+98h+var_58]
0x18008ebbe  mov     [rsp+98h+var_70], rax
0x18008ebc3  mov     rax, qword ptr [rsp+98h+arg_30]
0x18008ebcb  mov     qword ptr [rsp+98h+var_78], rax; int
0x18008ebd0  mov     r9, r14
0x18008ebd3  mov     r8d, [rsp+98h+arg_20]
0x18008ebdb  mov     rdx, rdi
0x18008ebde  mov     rcx, rsi
0x18008ebe1  call    ?_CreateFile@CBackgroundCopyJob@@AEAAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@IPEBUDownloadRange@@_KAEAV?$shared_ptr@VCBackgroundCopyFile@@@3@@Z; CBackgroundCopyJob::_CreateFile(std::string const &,uint,DownloadRange const *,unsigned __int64,std::shared_ptr<CBackgroundCopyFile> &)
0x18008ebe6  mov     r14d, eax
0x18008ebe9  test    eax, eax
0x18008ebeb  jns     short loc_18008EC52
0x18008ebed  mov     rcx, [rsp+98h]; this
0x18008ebf5  mov     r9d, eax; char *
0x18008ebf8  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008ebff  mov     edx, 619h; void *
0x18008ec04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ec09  nop
0x18008ec0a  mov     rdi, [rsp+98h+var_58+8]
0x18008ec0f  test    rdi, rdi
0x18008ec12  jz      short loc_18008EC4A
0x18008ec14  or      ebx, 0FFFFFFFFh
0x18008ec17  mov     eax, ebx
0x18008ec19  lock xadd [rdi+8], eax
0x18008ec1e  add     eax, ebx
0x18008ec20  jnz     short loc_18008EC4A
0x18008ec22  mov     rax, [rdi]
0x18008ec25  mov     rcx, rdi
0x18008ec28  mov     rax, [rax]
0x18008ec2b  call    _guard_dispatch_icall
0x18008ec30  mov     eax, ebx
0x18008ec32  lock xadd [rdi+0Ch], eax
0x18008ec37  add     eax, ebx
0x18008ec39  jnz     short loc_18008EC4A
0x18008ec3b  mov     rax, [rdi]
0x18008ec3e  mov     rcx, rdi
0x18008ec41  mov     rax, [rax+8]
0x18008ec45  call    _guard_dispatch_icall
0x18008ec4a  mov     eax, r14d
0x18008ec4d  jmp     loc_18008F080
0x18008ec52  cmp     qword ptr [r12+10h], 0
0x18008ec58  jz      loc_18008ED7E
0x18008ec5e  mov     rax, [rsi+0F8h]
0x18008ec65  mov     cl, [rax+18Ch]
0x18008ec6b  test    cl, cl
0x18008ec6d  setz    r14b
0x18008ec71  test    cl, cl
0x18008ec73  jnz     short loc_18008ECEF
0x18008ec75  xorps   xmm1, xmm1
0x18008ec78  movdqu  [rsp+98h+var_68], xmm1
0x18008ec7e  lea     rcx, [rsi+10h]
0x18008ec82  lea     r8, [rsp+98h+var_68]
0x18008ec87  mov     edx, 19h
0x18008ec8c  call    ?Find@CConfigStore@@QEBAJHAEAV?$shared_ptr@VCConfigValue@@@std@@@Z; CConfigStore::Find(int,std::shared_ptr<CConfigValue> &)
0x18008ec91  mov     r15d, 1
0x18008ec97  test    eax, eax
0x18008ec99  js      short loc_18008ECAD
0x18008ec9b  mov     rax, qword ptr [rsp+98h+var_68]
0x18008eca0  cmp     [rax+20h], r15b
0x18008eca4  jnz     loc_18008F090
0x18008ecaa  mov     r14b, [rax]
0x18008ecad  mov     rdi, qword ptr [rsp+98h+var_68+8]
0x18008ecb2  or      ebx, 0FFFFFFFFh
0x18008ecb5  test    rdi, rdi
0x18008ecb8  jz      short loc_18008ECF6
0x18008ecba  mov     eax, ebx
0x18008ecbc  lock xadd [rdi+8], eax
0x18008ecc1  add     eax, ebx
0x18008ecc3  jnz     short loc_18008ECF6
0x18008ecc5  mov     rax, [rdi]
0x18008ecc8  mov     rcx, rdi
0x18008eccb  mov     rax, [rax]
0x18008ecce  call    _guard_dispatch_icall
0x18008ecd3  mov     eax, ebx
0x18008ecd5  lock xadd [rdi+0Ch], eax
0x18008ecda  add     eax, ebx
0x18008ecdc  jnz     short loc_18008ECF6
0x18008ecde  mov     rax, [rdi]
0x18008ece1  mov     rcx, rdi
0x18008ece4  mov     rax, [rax+8]
0x18008ece8  call    _guard_dispatch_icall
0x18008eced  jmp     short loc_18008ECF6
0x18008ecef  or      ebx, 0FFFFFFFFh
0x18008ecf2  lea     r15d, [rbx+2]
0x18008ecf6  cmp     qword ptr [r12+18h], 0Fh
0x18008ecfc  jbe     short loc_18008ED02
0x18008ecfe  mov     r12, [r12]
0x18008ed02  mov     r8b, r14b; bool
0x18008ed05  mov     rdx, r12; char *
0x18008ed08  mov     r12, [rsp+98h+var_58]
0x18008ed0d  mov     rcx, r12; this
0x18008ed10  call    ?SetLocalPathAndCreateFile@CBackgroundCopyFile@@QEAAJPEBD_N@Z; CBackgroundCopyFile::SetLocalPathAndCreateFile(char const *,bool)
0x18008ed15  mov     r14d, eax
0x18008ed18  test    eax, eax
0x18008ed1a  jns     short loc_18008ED8A
0x18008ed1c  mov     rcx, [rsp+98h]; this
0x18008ed24  mov     r9d, eax; char *
0x18008ed27  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008ed2e  mov     edx, 628h; void *
0x18008ed33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ed38  nop
0x18008ed39  mov     rdi, [rsp+98h+var_58+8]
0x18008ed3e  test    rdi, rdi
0x18008ed41  jz      short loc_18008ED76
0x18008ed43  mov     eax, ebx
0x18008ed45  lock xadd [rdi+8], eax
0x18008ed4a  add     eax, ebx
0x18008ed4c  jnz     short loc_18008ED76
0x18008ed4e  mov     rax, [rdi]
0x18008ed51  mov     rcx, rdi
0x18008ed54  mov     rax, [rax]
0x18008ed57  call    _guard_dispatch_icall
0x18008ed5c  mov     eax, ebx
0x18008ed5e  lock xadd [rdi+0Ch], eax
0x18008ed63  add     eax, ebx
0x18008ed65  jnz     short loc_18008ED76
0x18008ed67  mov     rax, [rdi]
0x18008ed6a  mov     rcx, rdi
0x18008ed6d  mov     rax, [rax+8]
0x18008ed71  call    _guard_dispatch_icall
0x18008ed76  mov     eax, r14d
0x18008ed79  jmp     loc_18008F080
0x18008ed7e  or      ebx, 0FFFFFFFFh
0x18008ed81  lea     r15d, [rbx+2]
0x18008ed85  mov     r12, [rsp+98h+var_58]
0x18008ed8a  cmp     qword ptr [r13+10h], 0
0x18008ed8f  jz      short loc_18008EE05
0x18008ed91  mov     rdx, r13
0x18008ed94  mov     rcx, r12
0x18008ed97  call    ?SetRemoteName@CBackgroundCopyFile@@QEAAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CBackgroundCopyFile::SetRemoteName(std::string const &)
0x18008ed9c  mov     r14d, eax
0x18008ed9f  test    eax, eax
0x18008eda1  jns     short loc_18008EE05
0x18008eda3  mov     rcx, [rsp+98h]; this
0x18008edab  mov     r9d, eax; char *
0x18008edae  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008edb5  mov     edx, 62Ch; void *
0x18008edba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008edbf  nop
0x18008edc0  mov     rdi, [rsp+98h+var_58+8]
0x18008edc5  test    rdi, rdi
0x18008edc8  jz      short loc_18008EDFD
0x18008edca  mov     eax, ebx
0x18008edcc  lock xadd [rdi+8], eax
0x18008edd1  add     eax, ebx
0x18008edd3  jnz     short loc_18008EDFD
0x18008edd5  mov     rax, [rdi]
0x18008edd8  mov     rcx, rdi
0x18008eddb  mov     rax, [rax]
0x18008edde  call    _guard_dispatch_icall
0x18008ede3  mov     eax, ebx
0x18008ede5  lock xadd [rdi+0Ch], eax
0x18008edea  add     eax, ebx
0x18008edec  jnz     short loc_18008EDFD
0x18008edee  mov     rax, [rdi]
0x18008edf1  mov     rcx, rdi
0x18008edf4  mov     rax, [rax+8]
0x18008edf8  call    _guard_dispatch_icall
0x18008edfd  mov     eax, r14d
0x18008ee00  jmp     loc_18008F080
0x18008ee05  xorps   xmm0, xmm0
0x18008ee08  movups  [rsp+98h+var_68], xmm0
0x18008ee0d  lea     rdi, [rsi+88h]
0x18008ee14  mov     qword ptr [rsp+98h+var_68], rdi
0x18008ee19  mov     byte ptr [rsp+98h+var_68+8], 0
0x18008ee1e  mov     rcx, rdi
0x18008ee21  call    mtx_do_lock
0x18008ee26  test    eax, eax
0x18008ee28  jnz     loc_18008F096
0x18008ee2e  cmp     dword ptr [rsi+0D4h], 7FFFFFFFh
0x18008ee38  jz      loc_18008F0A0
0x18008ee3e  mov     byte ptr [rsp+98h+var_68+8], r15b
0x18008ee43  mov     rcx, rsi; this
0x18008ee46  call    ?_IsJobActiveForIncomingCall@CBackgroundCopyJob@@AEBAJXZ; CBackgroundCopyJob::_IsJobActiveForIncomingCall(void)
0x18008ee4b  mov     r14d, eax
0x18008ee4e  test    eax, eax
0x18008ee50  jns     short loc_18008EED0
0x18008ee52  mov     rcx, [rsp+98h]; this
0x18008ee5a  mov     r9d, eax; char *
0x18008ee5d  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008ee64  mov     edx, 632h; void *
0x18008ee69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ee6e  nop
0x18008ee6f  add     [rsi+0D4h], ebx
0x18008ee75  jnz     short loc_18008EE8B
0x18008ee77  mov     [rsi+0D0h], ebx
0x18008ee7d  lea     rcx, [rsi+98h]; SRWLock
0x18008ee84  call    cs:__imp_ReleaseSRWLockExclusive
0x18008ee8a  nop
0x18008ee8b  mov     rdi, [rsp+98h+var_58+8]
0x18008ee90  test    rdi, rdi
0x18008ee93  jz      short loc_18008EEC8
0x18008ee95  mov     eax, ebx
0x18008ee97  lock xadd [rdi+8], eax
0x18008ee9c  add     eax, ebx
0x18008ee9e  jnz     short loc_18008EEC8
0x18008eea0  mov     rax, [rdi]
0x18008eea3  mov     rcx, rdi
0x18008eea6  mov     rax, [rax]
0x18008eea9  call    _guard_dispatch_icall
0x18008eeae  mov     eax, ebx
0x18008eeb0  lock xadd [rdi+0Ch], eax
0x18008eeb5  add     eax, ebx
0x18008eeb7  jnz     short loc_18008EEC8
0x18008eeb9  mov     rax, [rdi]
0x18008eebc  mov     rcx, rdi
0x18008eebf  mov     rax, [rax+8]
0x18008eec3  call    _guard_dispatch_icall
0x18008eec8  mov     eax, r14d
0x18008eecb  jmp     loc_18008F080
0x18008eed0  xor     edx, edx
0x18008eed2  mov     rcx, rsi
0x18008eed5  call    ?_SetState@CBackgroundCopyJob@@AEAAXW4DownloadJobState@@@Z; CBackgroundCopyJob::_SetState(DownloadJobState)
0x18008eeda  nop
0x18008eedb  add     [rdi+4Ch], ebx
0x18008eede  jnz     short loc_18008EEED
0x18008eee0  mov     [rdi+48h], ebx
0x18008eee3  lea     rcx, [rdi+10h]; SRWLock
0x18008eee7  call    cs:__imp_ReleaseSRWLockExclusive
0x18008eeed  xorps   xmm0, xmm0
0x18008eef0  movups  [rsp+98h+var_68], xmm0
0x18008eef5  lea     rax, [rsi+0E0h]
0x18008eefc  mov     qword ptr [rsp+98h+var_68], rax
0x18008ef01  mov     rcx, rax; SRWLock
0x18008ef04  call    cs:__imp_AcquireSRWLockExclusive
0x18008ef0a  mov     byte ptr [rsp+98h+var_68+8], r15b
0x18008ef0f  mov     rdx, [rsi+48h]
0x18008ef13  cmp     rdx, [rsi+50h]
0x18008ef17  jz      short loc_18008EF45
0x18008ef19  mov     qword ptr [rdx], 0
0x18008ef20  mov     qword ptr [rdx+8], 0
0x18008ef28  mov     rdi, [rsp+98h+var_58+8]
0x18008ef2d  test    rdi, rdi
0x18008ef30  jz      short loc_18008EF37
0x18008ef32  lock add [rdi+8], r15d
0x18008ef37  mov     [rdx], r12
0x18008ef3a  mov     [rdx+8], rdi
0x18008ef3e  add     qword ptr [rsi+48h], 10h
0x18008ef43  jmp     short loc_18008EF5D
0x18008ef45  lea     r8, [rsp+98h+var_58]
0x18008ef4a  lea     rcx, [rsi+40h]
0x18008ef4e  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VCBackgroundCopyFile@@@std@@@?$vector@V?$shared_ptr@VCBackgroundCopyFile@@@std@@V?$allocator@V?$shared_ptr@VCBackgroundCopyFile@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VCBackgroundCopyFile@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<CBackgroundCopyFile>>::_Emplace_reallocate<std::shared_ptr<CBackgroundCopyFile> const &>(std::shared_ptr<CBackgroundCopyFile> * const,std::shared_ptr<CBackgroundCopyFile> const &)
0x18008ef53  mov     rdi, [rsp+98h+var_58+8]
0x18008ef58  mov     r12, [rsp+98h+var_58]
0x18008ef5d  mov     r14, [rsi+48h]
0x18008ef61  sub     r14, [rsi+40h]
0x18008ef65  sar     r14, 4
0x18008ef69  sub     r14, r15
0x18008ef6c  test    r15b, r15b
0x18008ef6f  jz      short loc_18008EF7E
0x18008ef71  lea     rcx, [rsi+0E0h]; SRWLock
0x18008ef78  call    cs:__imp_ReleaseSRWLockExclusive
0x18008ef7e  mov     rdx, [rsi+140h]; struct IPersistedEntity *
0x18008ef85  test    rdx, rdx
0x18008ef88  jz      short loc_18008EF95
0x18008ef8a  mov     r8d, r14d; unsigned int
0x18008ef8d  mov     rcx, r12; this
0x18008ef90  call    ?SaveFileInfo@CBackgroundCopyFile@@QEAAJAEAVIPersistedEntity@@I@Z; CBackgroundCopyFile::SaveFileInfo(IPersistedEntity &,uint)
0x18008ef95  test    r14, r14
0x18008ef98  jnz     short loc_18008F010
0x18008ef9a  xor     r8d, r8d
0x18008ef9d  lea     edx, [r14+59h]
0x18008efa1  mov     rcx, [rsi+178h]
0x18008efa8  call    ??$GetConfigValue@I@CGlobalConfigManager@@QEBAIW4Index@DOConfig@@PEAW4_ConfigProviderType@@@Z; CGlobalConfigManager::GetConfigValue<uint>(DOConfig::Index,_ConfigProviderType *)
0x18008efad  mov     r14d, eax
0x18008efb0  mov     qword ptr [rsp+98h+var_68], 0
0x18008efb9  lea     rcx, [rsp+98h+var_68]
0x18008efbe  call    cs:__imp_GetSystemTimePreciseAsFileTime
  ... truncated ...
```
