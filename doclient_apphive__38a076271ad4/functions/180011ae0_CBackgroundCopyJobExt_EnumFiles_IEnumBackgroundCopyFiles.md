# CBackgroundCopyJobExt::EnumFiles(IEnumBackgroundCopyFiles * *)

- ea: `0x180011ae0`
- end: `0x180012090`
- name: `?EnumFiles@CBackgroundCopyJobExt@@UEAAJPEAPEAUIEnumBackgroundCopyFiles@@@Z`
- size: `1456`
- prototype: `__int64 __fastcall(CBackgroundCopyJobExt *__hidden this, struct IEnumBackgroundCopyFiles **)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000933c`
- `0x180011ae0`
- `0x180013fb8`
- `0x180014ac4`
- `0x180014c80`
- `0x180015018`
- `0x180018228`
- `0x180084964`
- `0x180084a70`
- `0x18008b8b4`
- `0x1800a1f08`
- `0x1800f82f0`
- `0x1800f8320`
- `0x1800f876c`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011e6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011e6b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011b58`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011b92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011b58`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011b92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180011b6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180011bc5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180011b6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180011bc5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011e1d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011e1d`

## string_xrefs

- `0x180011b2f`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x180011ccd`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x180011f6e`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x180011d83`: `File: %s, SetFileExt failed`
- `0x180011d98`: `CBackgroundCopyJobExt::EnumFiles`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
__int64 __fastcall CBackgroundCopyJobExt::EnumFiles(RTL_SRWLOCK *this, struct IEnumBackgroundCopyFiles **a2)
{
  RTL_SRWLOCK *Ptr; // rbx
  __int64 v5; // rsi
  RTL_SRWLOCK *v6; // r13
  RTL_SRWLOCK *v7; // r12
  _QWORD *v8; // rcx
  char *v9; // rbx
  volatile signed __int32 *v10; // rsi
  unsigned __int128 v11; // kr10_16
  int v12; // eax
  unsigned int v13; // r15d
  struct IBackgroundCopyFile *v14; // rcx
  int v15; // eax
  int v16; // r15d
  __int64 v17; // rax
  struct IBackgroundCopyFile **v18; // rdx
  struct IBackgroundCopyFile *v19; // rcx
  struct IBackgroundCopyFile *v20; // rax
  struct IBackgroundCopyFile *v21; // rsi
  int v22; // r14d
  int v23; // [rsp+20h] [rbp-98h]
  __int128 v24; // [rsp+38h] [rbp-80h] BYREF
  struct IBackgroundCopyFile *i; // [rsp+48h] [rbp-70h]
  struct IBackgroundCopyFile *v26; // [rsp+50h] [rbp-68h] BYREF
  struct IEnumBackgroundCopyFiles **v27; // [rsp+58h] [rbp-60h]
  struct IBackgroundCopyFile *v28; // [rsp+60h] [rbp-58h] BYREF
  unsigned __int128 v29; // [rsp+68h] [rbp-50h] BYREF
  __int64 v30; // [rsp+78h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v27 = a2;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1ED,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
      (const char *)0x80004003LL,
      v23);
    return 2147500035LL;
  }
  *a2 = 0;
  Ptr = (RTL_SRWLOCK *)this[3].Ptr;
  AcquireSRWLockShared(Ptr + 28);
  v5 = ((char *)Ptr[9].Ptr - (char *)Ptr[8].Ptr) >> 4;
  ReleaseSRWLockShared(Ptr + 28);
  if ( !v5 )
    return 2161123332LL;
  v24 = 0;
  v6 = this + 7;
  AcquireSRWLockShared(this + 7);
  v7 = this + 5;
  v8 = this[5].Ptr;
  if ( v8 && (__int64)(v8[1] - *v8) >> 3 == v5 )
    std::shared_ptr<std::vector<Microsoft::WRL::ComPtr<IUnknown>>>::operator=(&v24, &this[5]);
  ReleaseSRWLockShared(this + 7);
  if ( !(_QWORD)v24 )
  {
    v9 = (char *)operator new(0x28u);
    *((_DWORD *)v9 + 2) = 1;
    *((_DWORD *)v9 + 3) = 1;
    *(_QWORD *)v9 = &std::_Ref_count_obj2<std::vector<Microsoft::WRL::ComPtr<IUnknown>>>::`vftable';
    *((_QWORD *)v9 + 2) = 0;
    *((_QWORD *)v9 + 3) = 0;
    *((_QWORD *)v9 + 4) = 0;
    *(_QWORD *)&v24 = v9 + 16;
    v10 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
    *((_QWORD *)&v24 + 1) = v9;
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    v29 = 0;
    v30 = 0;
    CBackgroundCopyJob::GetFiles(this[3].Ptr, &v29);
    v11 = v29;
    for ( i = (struct IBackgroundCopyFile *)*((_QWORD *)&v29 + 1);
          ;
          v11 = __PAIR128__((unsigned __int64)i, (__int64)v11 + 16) )
    {
      if ( (_QWORD)v11 == *((_QWORD *)&v11 + 1) )
      {
        AcquireSRWLockExclusive(v6);
        if ( v7->Ptr
          && (__int64)(*((_QWORD *)v7->Ptr + 1) - *(_QWORD *)v7->Ptr) >> 3 >= (unsigned __int64)((__int64)(*((_QWORD *)v9 + 3) - *((_QWORD *)v9 + 2)) >> 3) )
        {
          std::shared_ptr<std::vector<Microsoft::WRL::ComPtr<IUnknown>>>::operator=(&v24, v7);
          v9 = (char *)*((_QWORD *)&v24 + 1);
        }
        else
        {
          std::shared_ptr<std::vector<Microsoft::WRL::ComPtr<IUnknown>>>::operator=(v7, &v24);
        }
        ReleaseSRWLockExclusive(v6);
        std::vector<std::shared_ptr<CConfigValue>>::_Tidy(&v29);
        goto LABEL_43;
      }
      v28 = 0;
      if ( (int)CBackgroundCopyFile::GetFileExt(*(CBackgroundCopyFile **)v11, &v28) < 0 )
      {
        v12 = Microsoft::WRL::Details::MakeAndInitialize<CBackgroundCopyFileExt,IBackgroundCopyFile,std::shared_ptr<CBackgroundCopyFile> &>(
                &v28,
                v11);
        v13 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x20D,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
            (const char *)(unsigned int)v12,
            v23);
          v14 = v28;
          if ( v28 )
          {
            v28 = 0;
            ((void (__fastcall *)(struct IBackgroundCopyFile *))v14->lpVtbl->Release)(v14);
          }
          std::vector<std::shared_ptr<CConfigValue>>::_Tidy(&v29);
          if ( v9 && _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(void *))v9)(v9);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
          }
          return v13;
        }
        v15 = CBackgroundCopyFile::SetFileExt(*(CBackgroundCopyFile **)v11, v28);
        v16 = v15;
        if ( v15 < 0 && v15 != -2133843949 )
        {
          v17 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 16LL))(*(_QWORD *)v11);
          if ( *(_QWORD *)(v17 + 24) > 0xFu )
            v17 = *(_QWORD *)v17;
          LogResult(
            3u,
            "CBackgroundCopyJobExt::EnumFiles",
            0x213u,
            v16,
            "File: %s, SetFileExt failed",
            (const char *)v17);
        }
      }
      v26 = v28;
      v18 = (struct IBackgroundCopyFile **)*((_QWORD *)v9 + 3);
      if ( v18 == *((struct IBackgroundCopyFile ***)v9 + 4) )
      {
        std::vector<Microsoft::WRL::ComPtr<IUnknown>>::_Emplace_reallocate<IBackgroundCopyFile *>(v9 + 16, v18, &v26);
      }
      else
      {
        *v18 = v28;
        if ( v28 )
          ((void (__fastcall *)(struct IBackgroundCopyFile *))v28->lpVtbl->AddRef)(v28);
        *((_QWORD *)v9 + 3) += 8LL;
      }
      v19 = v28;
      if ( v28 )
      {
        v28 = 0;
        ((void (__fastcall *)(struct IBackgroundCopyFile *))v19->lpVtbl->Release)(v19);
      }
    }
  }
  v9 = (char *)*((_QWORD *)&v24 + 1);
LABEL_43:
  v20 = (struct IBackgroundCopyFile *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v21 = v20;
  i = v20;
  v26 = v20;
  if ( !v20 )
  {
    v22 = -2147024882;
    goto LABEL_49;
  }
  v28 = v20;
  CServiceLocker::_LockService(1);
  HIDWORD(v21[1].lpVtbl) = 1;
  v21->lpVtbl = (struct IBackgroundCopyFileVtbl *)&Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IEnumBackgroundCopyFiles>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  v21->lpVtbl = (struct IBackgroundCopyFileVtbl *)&CEnumObjectsImpl<IBackgroundCopyFile,IEnumBackgroundCopyFiles>::`vftable';
  v21[3].lpVtbl = 0;
  v21[4].lpVtbl = 0;
  v21[5].lpVtbl = 0;
  v21[6].lpVtbl = 0;
  v26 = v21;
  i = 0;
  std::shared_ptr<std::vector<Microsoft::WRL::ComPtr<IUnknown>>>::operator=(&v21[3], &v24);
  v22 = ((__int64 (__fastcall *)(struct IBackgroundCopyFile *))v21->lpVtbl->GetProgress)(v21);
  if ( v22 < 0 )
  {
    ((void (__fastcall *)(struct IBackgroundCopyFile *))v21->lpVtbl->Release)(v21);
LABEL_49:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22D,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
      (const char *)(unsigned int)v22,
      v23);
    if ( v9 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v9)(v9);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
      }
    }
    return (unsigned int)v22;
  }
  ((void (__fastcall *)(struct IBackgroundCopyFile *))v21->lpVtbl->AddRef)(v21);
  ((void (__fastcall *)(struct IBackgroundCopyFile *))v21->lpVtbl->Release)(v21);
  *v27 = (struct IEnumBackgroundCopyFiles *)v21;
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v9)(v9);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011ae0  mov     [rsp+arg_10], rbx
0x180011ae5  mov     [rsp+arg_18], rsi
0x180011aea  push    rdi
0x180011aeb  push    r12
0x180011aed  push    r13
0x180011aef  push    r14
0x180011af1  push    r15
0x180011af3  sub     rsp, 90h
0x180011afa  mov     rax, cs:__security_cookie
0x180011b01  xor     rax, rsp
0x180011b04  mov     [rsp+0B8h+var_38], rax
0x180011b0c  mov     rax, rdx
0x180011b0f  mov     [rsp+0B8h+var_60], rdx
0x180011b14  mov     r15, rcx
0x180011b17  xor     r14d, r14d
0x180011b1a  test    rax, rax
0x180011b1d  jnz     short loc_180011B47
0x180011b1f  mov     rcx, [rsp+0B8h]; this
0x180011b27  mov     ebx, 80004003h
0x180011b2c  mov     r9d, ebx; char *
0x180011b2f  lea     r8, aCW1SSrcDeliver_81; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180011b36  mov     edx, 1EDh; void *
0x180011b3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011b40  mov     eax, ebx
0x180011b42  jmp     loc_180012062
0x180011b47  mov     [rdx], r14
0x180011b4a  mov     rbx, [rcx+18h]
0x180011b4e  lea     rdi, [rbx+0E0h]
0x180011b55  mov     rcx, rdi; SRWLock
0x180011b58  call    cs:__imp_AcquireSRWLockShared
0x180011b5e  mov     rsi, [rbx+48h]
0x180011b62  sub     rsi, [rbx+40h]
0x180011b66  sar     rsi, 4
0x180011b6a  mov     rcx, rdi; SRWLock
0x180011b6d  call    cs:__imp_ReleaseSRWLockShared
0x180011b73  test    rsi, rsi
0x180011b76  jnz     short loc_180011B82
0x180011b78  mov     eax, 80D02004h
0x180011b7d  jmp     loc_180012062
0x180011b82  xorps   xmm1, xmm1
0x180011b85  movdqu  [rsp+0B8h+var_80], xmm1
0x180011b8b  lea     r13, [r15+38h]
0x180011b8f  mov     rcx, r13; SRWLock
0x180011b92  call    cs:__imp_AcquireSRWLockShared
0x180011b98  lea     r12, [r15+28h]
0x180011b9c  mov     rcx, [r12]
0x180011ba0  test    rcx, rcx
0x180011ba3  jz      short loc_180011BC2
0x180011ba5  mov     rax, [rcx+8]
0x180011ba9  sub     rax, [rcx]
0x180011bac  sar     rax, 3
0x180011bb0  cmp     rax, rsi
0x180011bb3  jnz     short loc_180011BC2
0x180011bb5  mov     rdx, r12
0x180011bb8  lea     rcx, [rsp+0B8h+var_80]
0x180011bbd  call    ??4?$shared_ptr@V?$vector@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<std::vector<Microsoft::WRL::ComPtr<IUnknown>>>::operator=(std::shared_ptr<std::vector<Microsoft::WRL::ComPtr<IUnknown>>> const &)
0x180011bc2  mov     rcx, r13; SRWLock
0x180011bc5  call    cs:__imp_ReleaseSRWLockShared
0x180011bcb  cmp     qword ptr [rsp+0B8h+var_80], r14
0x180011bd0  jnz     loc_180011E7E
0x180011bd6  mov     ecx, 28h ; '('; Size
0x180011bdb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011be0  mov     rbx, rax
0x180011be3  mov     dword ptr [rax+8], 1
0x180011bea  mov     dword ptr [rax+0Ch], 1
0x180011bf1  lea     rax, ??_7?$_Ref_count_obj2@V?$vector@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<Microsoft::WRL::ComPtr<IUnknown>>>::`vftable'
0x180011bf8  mov     [rbx], rax
0x180011bfb  lea     r14, [rbx+10h]
0x180011bff  xor     eax, eax
0x180011c01  mov     [r14], rax
0x180011c04  mov     [r14+8], rax
0x180011c08  mov     [r14+10h], rax
0x180011c0c  mov     qword ptr [rsp+0B8h+var_80], r14
0x180011c11  mov     rsi, qword ptr [rsp+0B8h+var_80+8]
0x180011c16  mov     qword ptr [rsp+0B8h+var_80+8], rbx
0x180011c1b  or      edi, 0FFFFFFFFh
0x180011c1e  test    rsi, rsi
0x180011c21  jz      short loc_180011C56
0x180011c23  mov     eax, edi
0x180011c25  lock xadd [rsi+8], eax
0x180011c2a  add     eax, edi
0x180011c2c  jnz     short loc_180011C56
0x180011c2e  mov     rax, [rsi]
0x180011c31  mov     rcx, rsi
0x180011c34  mov     rax, [rax]
0x180011c37  call    _guard_dispatch_icall
0x180011c3c  mov     eax, edi
0x180011c3e  lock xadd [rsi+0Ch], eax
0x180011c43  add     eax, edi
0x180011c45  jnz     short loc_180011C56
0x180011c47  mov     rax, [rsi]
0x180011c4a  mov     rcx, rsi
0x180011c4d  mov     rax, [rax+8]
0x180011c51  call    _guard_dispatch_icall
0x180011c56  xorps   xmm0, xmm0
0x180011c59  xor     eax, eax
0x180011c5b  movups  [rsp+0B8h+var_50], xmm0
0x180011c60  mov     [rsp+0B8h+var_40], rax
0x180011c65  lea     rdx, [rsp+0B8h+var_50]
0x180011c6a  mov     rcx, [r15+18h]
0x180011c6e  call    ?GetFiles@CBackgroundCopyJob@@QEBA?AV?$vector@V?$shared_ptr@VCBackgroundCopyFile@@@std@@V?$allocator@V?$shared_ptr@VCBackgroundCopyFile@@@std@@@2@@std@@XZ; CBackgroundCopyJob::GetFiles(void)
0x180011c73  nop
0x180011c74  mov     rsi, qword ptr [rsp+0B8h+var_50]
0x180011c79  mov     rax, qword ptr [rsp+0B8h+var_50+8]
0x180011c7e  mov     [rsp+0B8h+var_70], rax
0x180011c83  cmp     rsi, rax
0x180011c86  jz      loc_180011E1A
0x180011c8c  mov     [rsp+0B8h+var_58], 0
0x180011c95  lea     rdx, [rsp+0B8h+var_58]; struct IBackgroundCopyFile **
0x180011c9a  mov     rcx, [rsi]; this
0x180011c9d  call    ?GetFileExt@CBackgroundCopyFile@@QEBAJPEAPEAUIBackgroundCopyFile@@@Z; CBackgroundCopyFile::GetFileExt(IBackgroundCopyFile * *)
0x180011ca2  test    eax, eax
0x180011ca4  jns     loc_180011DA9
0x180011caa  mov     rdx, rsi
0x180011cad  lea     rcx, [rsp+0B8h+var_58]
0x180011cb2  call    ??$MakeAndInitialize@VCBackgroundCopyFileExt@@UIBackgroundCopyFile@@AEAV?$shared_ptr@VCBackgroundCopyFile@@@std@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIBackgroundCopyFile@@@WRL@Microsoft@@@012@AEAV?$shared_ptr@VCBackgroundCopyFile@@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CBackgroundCopyFileExt,IBackgroundCopyFile,std::shared_ptr<CBackgroundCopyFile> &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IBackgroundCopyFile>>,std::shared_ptr<CBackgroundCopyFile> &)
0x180011cb7  mov     r15d, eax
0x180011cba  test    eax, eax
0x180011cbc  jns     loc_180011D4A
0x180011cc2  mov     rcx, [rsp+0B8h]; this
0x180011cca  mov     r9d, eax; char *
0x180011ccd  lea     r8, aCW1SSrcDeliver_81; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180011cd4  mov     edx, 20Dh; void *
0x180011cd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011cde  nop
0x180011cdf  mov     rcx, [rsp+0B8h+var_58]
0x180011ce4  test    rcx, rcx
0x180011ce7  jz      short loc_180011CFF
0x180011ce9  mov     [rsp+0B8h+var_58], 0
0x180011cf2  mov     rax, [rcx]
0x180011cf5  mov     rax, [rax+10h]
0x180011cf9  call    _guard_dispatch_icall
0x180011cfe  nop
0x180011cff  lea     rcx, [rsp+0B8h+var_50]
0x180011d04  call    ?_Tidy@?$vector@V?$shared_ptr@VCConfigValue@@@std@@V?$allocator@V?$shared_ptr@VCConfigValue@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<CConfigValue>>::_Tidy(void)
0x180011d09  nop
0x180011d0a  test    rbx, rbx
0x180011d0d  jz      short loc_180011D42
0x180011d0f  mov     eax, edi
0x180011d11  lock xadd [rbx+8], eax
0x180011d16  add     eax, edi
0x180011d18  jnz     short loc_180011D42
0x180011d1a  mov     rax, [rbx]
0x180011d1d  mov     rcx, rbx
0x180011d20  mov     rax, [rax]
0x180011d23  call    _guard_dispatch_icall
0x180011d28  mov     edx, edi
0x180011d2a  lock xadd [rbx+0Ch], edx
0x180011d2f  add     edx, edi
0x180011d31  jnz     short loc_180011D42
0x180011d33  mov     rdx, [rbx]
0x180011d36  mov     rcx, rbx
0x180011d39  mov     rax, [rdx+8]
0x180011d3d  call    _guard_dispatch_icall
0x180011d42  mov     eax, r15d
0x180011d45  jmp     loc_180012062
0x180011d4a  mov     rdx, [rsp+0B8h+var_58]; struct IBackgroundCopyFile *
0x180011d4f  mov     rcx, [rsi]; this
0x180011d52  call    ?SetFileExt@CBackgroundCopyFile@@QEAAJPEAUIBackgroundCopyFile@@@Z; CBackgroundCopyFile::SetFileExt(IBackgroundCopyFile *)
0x180011d57  mov     r15d, eax
0x180011d5a  test    eax, eax
0x180011d5c  jns     short loc_180011DA9
0x180011d5e  cmp     eax, 80D02013h
0x180011d63  jz      short loc_180011DA9
0x180011d65  mov     rcx, [rsi]
0x180011d68  mov     rax, [rcx]
0x180011d6b  mov     rax, [rax+10h]
0x180011d6f  call    _guard_dispatch_icall
0x180011d74  cmp     qword ptr [rax+18h], 0Fh
0x180011d79  jbe     short loc_180011D7E
0x180011d7b  mov     rax, [rax]
0x180011d7e  mov     [rsp+0B8h+var_90], rax
0x180011d83  lea     rax, aFileSSetfileex; "File: %s, SetFileExt failed"
0x180011d8a  mov     [rsp+0B8h+var_98], rax; char *
0x180011d8f  mov     r9d, r15d; int
0x180011d92  mov     r8d, 213h; unsigned int
0x180011d98  lea     rdx, aCbackgroundcop_40; "CBackgroundCopyJobExt::EnumFiles"
0x180011d9f  mov     ecx, 3; unsigned __int8
0x180011da4  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x180011da9  mov     rax, [rsp+0B8h+var_58]
0x180011dae  mov     [rsp+0B8h+var_68], rax
0x180011db3  mov     rdx, [r14+8]
0x180011db7  cmp     rdx, [r14+10h]
0x180011dbb  jz      short loc_180011DDE
0x180011dbd  mov     [rdx], rax
0x180011dc0  mov     rcx, [rsp+0B8h+var_58]
0x180011dc5  test    rcx, rcx
0x180011dc8  jz      short loc_180011DD7
0x180011dca  mov     rax, [rcx]
0x180011dcd  mov     rax, [rax+8]
0x180011dd1  call    _guard_dispatch_icall
0x180011dd6  nop
0x180011dd7  add     qword ptr [r14+8], 8
0x180011ddc  jmp     short loc_180011DEC
0x180011dde  lea     r8, [rsp+0B8h+var_68]
0x180011de3  mov     rcx, r14
0x180011de6  call    ??$_Emplace_reallocate@PEAUIBackgroundCopyFile@@@?$vector@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAV234@$$QEAPEAUIBackgroundCopyFile@@@Z; std::vector<Microsoft::WRL::ComPtr<IUnknown>>::_Emplace_reallocate<IBackgroundCopyFile *>(Microsoft::WRL::ComPtr<IUnknown> * const,IBackgroundCopyFile * &&)
0x180011deb  nop
0x180011dec  mov     rcx, [rsp+0B8h+var_58]
0x180011df1  test    rcx, rcx
0x180011df4  jz      short loc_180011E0C
0x180011df6  mov     [rsp+0B8h+var_58], 0
0x180011dff  mov     rax, [rcx]
0x180011e02  mov     rax, [rax+10h]
0x180011e06  call    _guard_dispatch_icall
0x180011e0b  nop
0x180011e0c  add     rsi, 10h
0x180011e10  mov     rax, [rsp+0B8h+var_70]
0x180011e15  jmp     loc_180011C83
0x180011e1a  mov     rcx, r13; SRWLock
0x180011e1d  call    cs:__imp_AcquireSRWLockExclusive
0x180011e23  mov     r8, [r12]
0x180011e27  test    r8, r8
0x180011e2a  jz      short loc_180011E5B
0x180011e2c  mov     rcx, [r14+8]
0x180011e30  sub     rcx, [r14]
0x180011e33  sar     rcx, 3
0x180011e37  mov     rax, [r8+8]
0x180011e3b  sub     rax, [r8]
0x180011e3e  sar     rax, 3
0x180011e42  cmp     rax, rcx
0x180011e45  jb      short loc_180011E5B
0x180011e47  mov     rdx, r12
0x180011e4a  lea     rcx, [rsp+0B8h+var_80]
0x180011e4f  call    ??4?$shared_ptr@V?$vector@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<std::vector<Microsoft::WRL::ComPtr<IUnknown>>>::operator=(std::shared_ptr<std::vector<Microsoft::WRL::ComPtr<IUnknown>>> const &)
0x180011e54  mov     rbx, qword ptr [rsp+0B8h+var_80+8]
0x180011e59  jmp     short loc_180011E68
0x180011e5b  lea     rdx, [rsp+0B8h+var_80]
0x180011e60  mov     rcx, r12
0x180011e63  call    ??4?$shared_ptr@V?$vector@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<std::vector<Microsoft::WRL::ComPtr<IUnknown>>>::operator=(std::shared_ptr<std::vector<Microsoft::WRL::ComPtr<IUnknown>>> const &)
0x180011e68  mov     rcx, r13; SRWLock
0x180011e6b  call    cs:__imp_ReleaseSRWLockExclusive
0x180011e71  nop
0x180011e72  lea     rcx, [rsp+0B8h+var_50]
0x180011e77  call    ?_Tidy@?$vector@V?$shared_ptr@VCConfigValue@@@std@@V?$allocator@V?$shared_ptr@VCConfigValue@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<CConfigValue>>::_Tidy(void)
0x180011e7c  jmp     short loc_180011E86
0x180011e7e  or      edi, 0FFFFFFFFh
0x180011e81  mov     rbx, qword ptr [rsp+0B8h+var_80+8]
0x180011e86  mov     [rsp+0B8h+var_88], 0
0x180011e8f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011e96  mov     ecx, 38h ; '8'; unsigned __int64
0x180011e9b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180011ea0  mov     rsi, rax
0x180011ea3  mov     [rsp+0B8h+var_70], rax
0x180011ea8  mov     [rsp+0B8h+var_68], rax
0x180011ead  test    rax, rax
0x180011eb0  jnz     short loc_180011EBD
0x180011eb2  mov     r14d, 8007000Eh
0x180011eb8  jmp     loc_180011F63
0x180011ebd  mov     [rsp+0B8h+var_58], rsi
0x180011ec2  mov     cl, 1; bool
0x180011ec4  call    ?_LockService@CServiceLocker@@CAX_N@Z; CServiceLocker::_LockService(bool)
0x180011ec9  nop
0x180011eca  mov     dword ptr [rsi+0Ch], 1
0x180011ed1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIEnumBackgroundCopyFiles@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IEnumBackgroundCopyFiles>::`vftable'
0x180011ed8  mov     [rsi], rax
0x180011edb  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180011ee2  test    rcx, rcx
0x180011ee5  jz      short loc_180011EF4
0x180011ee7  mov     rax, [rcx]
0x180011eea  mov     rax, [rax+8]
0x180011eee  call    _guard_dispatch_icall
0x180011ef3  nop
0x180011ef4  lea     rax, ??_7?$CEnumObjectsImpl@UIBackgroundCopyFile@@UIEnumBackgroundCopyFiles@@@@6B@; const CEnumObjectsImpl<IBackgroundCopyFile,IEnumBackgroundCopyFiles>::`vftable'
0x180011efb  mov     [rsi], rax
0x180011efe  lea     rcx, [rsi+18h]
0x180011f02  mov     qword ptr [rcx], 0
0x180011f09  mov     qword ptr [rcx+8], 0
0x180011f11  mov     qword ptr [rsi+28h], 0
0x180011f19  mov     qword ptr [rsi+30h], 0
0x180011f21  mov     [rsp+0B8h+var_68], rsi
0x180011f26  mov     [rsp+0B8h+var_70], 0
0x180011f2f  lea     rdx, [rsp+0B8h+var_80]
0x180011f34  call    ??4?$shared_ptr@V?$vector@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<std::vector<Microsoft::WRL::ComPtr<IUnknown>>>::operator=(std::shared_ptr<std::vector<Microsoft::WRL::ComPtr<IUnknown>>> const &)
0x180011f39  mov     rax, [rsi]
0x180011f3c  mov     rcx, rsi
0x180011f3f  mov     rax, [rax+28h]
0x180011f43  call    _guard_dispatch_icall
0x180011f48  mov     r14d, eax
0x180011f4b  test    eax, eax
0x180011f4d  jns     loc_180011FE0
0x180011f53  mov     rax, [rsi]
0x180011f56  mov     rcx, rsi
0x180011f59  mov     rax, [rax+10h]
0x180011f5d  call    _guard_dispatch_icall
0x180011f62  nop
0x180011f63  mov     rcx, [rsp+0B8h]; this
0x180011f6b  mov     r9d, r14d; char *
0x180011f6e  lea     r8, aCW1SSrcDeliver_81; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180011f75  mov     edx, 22Dh; void *
0x180011f7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011f7f  nop
0x180011f80  mov     rcx, [rsp+0B8h+var_88]
0x180011f85  test    rcx, rcx
0x180011f88  jz      short loc_180011FA0
0x180011f8a  mov     [rsp+0B8h+var_88], 0
0x180011f93  mov     rax, [rcx]
0x180011f96  mov     rax, [rax+10h]
0x180011f9a  call    _guard_dispatch_icall
0x180011f9f  nop
  ... truncated ...
```
