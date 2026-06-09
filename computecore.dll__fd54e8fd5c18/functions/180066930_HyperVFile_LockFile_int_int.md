# HyperVFile::LockFile(int,int)

- ea: `0x180066930`
- end: `0x180066cde`
- name: `?LockFile@HyperVFile@@IEAAHHH@Z`
- size: `942`
- prototype: `__int64 __fastcall(HyperVFile *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `20`
- tags: `installer_update`

## callers

- `0x180066cf0`
- `0x180067740`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x180009e8c`
- `0x180060f70`
- `0x180061240`
- `0x180064e74`
- `0x180066930`
- `0x180066eb0`
- `0x180067068`
- `0x180068590`
- `0x180068908`
- `0x180069060`
- `0x1800697a8`
- `0x18006b5b4`
- `0x18006ba78`
- `0x180074298`
- `0x180082244`
- `0x1800886d0`
- `0x1800890cc`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180066b7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180066b7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180066c33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180066c33`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180066a49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180066a49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066a4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066a4f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall HyperVFile::LockFile(HyperVFile *this, int a2, int a3)
{
  bool v6; // di
  const unsigned __int16 *v7; // rbx
  _QWORD *v8; // rdx
  RTL_SRWLOCK *v9; // rcx
  unsigned int v10; // ebx
  _OWORD v12[2]; // [rsp+40h] [rbp-288h] BYREF
  char v13; // [rsp+60h] [rbp-268h]
  struct _GUID v14; // [rsp+70h] [rbp-258h] BYREF
  _QWORD v15[7]; // [rsp+80h] [rbp-248h] BYREF
  _QWORD *v16; // [rsp+B8h] [rbp-210h]
  int v17; // [rsp+C0h] [rbp-208h] BYREF
  _OWORD v18[2]; // [rsp+C8h] [rbp-200h] BYREF
  _QWORD v19[44]; // [rsp+F0h] [rbp-1D8h] BYREF
  __int128 v20; // [rsp+250h] [rbp-78h] BYREF
  __m128i si128; // [rsp+260h] [rbp-68h]
  _OWORD v22[2]; // [rsp+270h] [rbp-58h] BYREF
  int v23; // [rsp+2D8h] [rbp+10h] BYREF

  v23 = a2;
  v17 = 1;
  memset_0(v19, 0, 0x1A0u);
  v6 = a2 != 0;
  v7 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
  wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v19,
    "HyperVFile_Lock");
  v19[0] = &HyperVStorageTrace::HyperVFile_Lock::`vftable';
  v20 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v20) = 0;
  v22[0] = 0;
  v22[1] = si128;
  LOWORD(v22[0]) = 0;
  v14 = *(struct _GUID *)((char *)this + 568);
  HyperVStorageTrace::HyperVFile_Lock::StartActivity((HyperVStorageTrace::HyperVFile_Lock *)v19, &v14, v7, v6, a3 != 0);
  *(_QWORD *)&v14.Data1 = (char *)this + 752;
  AcquireSRWLockExclusive((PSRWLOCK)this + 94);
  *((_DWORD *)this + 190) = GetCurrentThreadId();
  if ( !*((_DWORD *)this + 192) && !*((_DWORD *)this + 101) )
  {
    if ( v23 || (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 40LL))(*((_QWORD *)this + 75)) )
    {
      HyperVStoragePerfTracker::StartOperation((char *)this + 432, v18);
      v15[0] = off_1800A5850;
      v15[1] = &v17;
      v15[2] = this;
      v15[3] = &v23;
      v16 = v15;
      HyperVFile::RetryOnDisconnect(this, v15);
      if ( v16 )
      {
        v8 = v15;
        LOBYTE(v8) = v16 != v15;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v16 + 32LL))(v16, v8);
      }
      if ( v17 )
      {
        v12[0] = v18[0];
        v12[1] = v18[1];
        v13 = 1;
        HyperVStoragePerfTracker::LogOperation((_DWORD)this + 432, (unsigned int)v12, 10, 0, 7);
        HyperVStorageTrace::HyperVFile_Lock::Locked((HyperVStorageTrace::HyperVFile_Lock *)v19);
        if ( a3 )
        {
          try
          {
            if ( *((_QWORD *)this + 9) == *((_QWORD *)this + 10) )
            {
              HyperVStorageTrace::HyperVFile_Lock::Reloading((HyperVStorageTrace::HyperVFile_Lock *)v19);
              HyperVStorage::InitializeInternal(this, 0);
              (*(void (__fastcall **)(HyperVFile *))(*(_QWORD *)this + 184LL))(this);
            }
            else
            {
              HyperVFile::UpdateCache(this);
            }
          }
          catch ( ... )
          {
            HvsGetHResultForThrownException();
          }
        }
      }
      else
      {
        HyperVStorageTrace::HyperVFile_Lock::Timeout((HyperVStorageTrace::HyperVFile_Lock *)v19);
      }
    }
    else if ( *((_QWORD *)this + 9) == *((_QWORD *)this + 10) )
    {
      HyperVStorageTrace::HyperVFile_Lock::NoCachedData((HyperVStorageTrace::HyperVFile_Lock *)v19);
      HvsThrowHResultError(-2147467259);
    }
  }
  if ( v17 )
    ++*((_DWORD *)this + 192);
  v9 = (RTL_SRWLOCK *)((char *)this + 752);
  if ( *((_DWORD *)this + 190) )
  {
    *((_DWORD *)this + 190) = 0;
    ReleaseSRWLockExclusive(v9);
  }
  else
  {
    ReleaseSRWLockShared(v9);
  }
  wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v19,
    v17 == 0 ? 0x80004005 : 0);
  v10 = v17;
  v19[0] = &HyperVStorageTrace::HyperVFile_Lock::`vftable';
  wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v19);
  std::wstring::~wstring(v22);
  std::wstring::~wstring(&v20);
  wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(v19);
  return v10;
}

```

## disassembly

```asm
0x180066930  mov     [rsp+arg_10], rbx
0x180066935  mov     [rsp+arg_8], edx
0x180066939  push    rsi
0x18006693a  push    rdi
0x18006693b  push    r13
0x18006693d  push    r14
0x18006693f  push    r15
0x180066941  sub     rsp, 2A0h
0x180066948  mov     rax, cs:__security_cookie
0x18006694f  xor     rax, rsp
0x180066952  mov     [rsp+2C8h+var_38], rax
0x18006695a  mov     r15d, r8d
0x18006695d  mov     ebx, edx
0x18006695f  mov     r14, rcx
0x180066962  mov     [rsp+2C8h+var_298], rcx
0x180066967  mov     [rsp+2C8h+var_208], 1
0x180066972  xor     edx, edx; Val
0x180066974  mov     r8d, 1A0h; Size
0x18006697a  lea     rcx, [rsp+2C8h+var_1D8]; void *
0x180066982  call    memset_0
0x180066987  test    r15d, r15d
0x18006698a  setnz   sil
0x18006698e  test    ebx, ebx
0x180066990  setnz   dil
0x180066994  mov     rcx, [r14+258h]
0x18006699b  mov     rax, [rcx]
0x18006699e  mov     rax, [rax+48h]
0x1800669a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800669a7  mov     rbx, rax
0x1800669aa  lea     rdx, aHypervfileLock_0; "HyperVFile_Lock"
0x1800669b1  lea     rcx, [rsp+2C8h+var_1D8]
0x1800669b9  call    ??0?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800669be  lea     r13, ??_7HyperVFile_Lock@HyperVStorageTrace@@6B@; const HyperVStorageTrace::HyperVFile_Lock::`vftable'
0x1800669c5  mov     [rsp+2C8h+var_1D8], r13
0x1800669cd  xorps   xmm0, xmm0
0x1800669d0  movups  [rsp+2C8h+var_78], xmm0
0x1800669d8  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800669e0  movdqa  [rsp+2C8h+var_68], xmm1
0x1800669e9  xor     ecx, ecx
0x1800669eb  mov     word ptr [rsp+2C8h+var_78], cx
0x1800669f3  movups  [rsp+2C8h+var_58], xmm0
0x1800669fb  movdqa  [rsp+2C8h+var_48], xmm1
0x180066a04  xor     eax, eax
0x180066a06  mov     word ptr [rsp+2C8h+var_58], ax
0x180066a0e  movups  xmm0, xmmword ptr [r14+238h]
0x180066a16  movdqu  xmmword ptr [rsp+2C8h+var_258.Data1], xmm0
0x180066a1c  mov     [rsp+2C8h+var_2A8], sil; bool
0x180066a21  mov     r9b, dil; bool
0x180066a24  mov     r8, rbx; unsigned __int16 *
0x180066a27  lea     rdx, [rsp+2C8h+var_258]; struct _GUID *
0x180066a2c  lea     rcx, [rsp+2C8h+var_1D8]; this
0x180066a34  call    ?StartActivity@HyperVFile_Lock@HyperVStorageTrace@@QEAAXU_GUID@@PEBG_N2@Z; HyperVStorageTrace::HyperVFile_Lock::StartActivity(_GUID,ushort const *,bool,bool)
0x180066a39  nop
0x180066a3a  lea     rbx, [r14+2F0h]
0x180066a41  mov     qword ptr [rsp+2C8h+var_258.Data1], rbx
0x180066a46  mov     rcx, rbx; SRWLock
0x180066a49  call    cs:__imp_AcquireSRWLockExclusive
0x180066a4f  call    cs:__imp_GetCurrentThreadId
0x180066a55  mov     [rbx+8], eax
0x180066a58  cmp     dword ptr [r14+300h], 0
0x180066a60  jnz     loc_180066B55
0x180066a66  cmp     dword ptr [r14+194h], 0
0x180066a6e  jnz     loc_180066B55
0x180066a74  cmp     [rsp+2C8h+arg_8], 0
0x180066a7c  jnz     short loc_180066AA8
0x180066a7e  mov     rcx, [r14+258h]
0x180066a85  mov     rax, [rcx]
0x180066a88  mov     rax, [rax+28h]
0x180066a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066a91  test    eax, eax
0x180066a93  jnz     short loc_180066AA8
0x180066a95  mov     rax, [r14+50h]
0x180066a99  cmp     [r14+48h], rax
0x180066a9d  jz      loc_180066CC6
0x180066aa3  jmp     loc_180066B55
0x180066aa8  lea     rdi, [r14+1B0h]
0x180066aaf  lea     rdx, [rsp+2C8h+var_200]
0x180066ab7  mov     rcx, rdi
0x180066aba  call    ?StartOperation@HyperVStoragePerfTracker@@QEAA?AUTimedOperation@1@XZ; HyperVStoragePerfTracker::StartOperation(void)
0x180066abf  lea     rax, off_1800A5850
0x180066ac6  mov     [rsp+2C8h+var_248], rax
0x180066ace  lea     rax, [rsp+2C8h+var_208]
0x180066ad6  mov     [rsp+2C8h+var_240], rax
0x180066ade  mov     [rsp+2C8h+var_238], r14
0x180066ae6  lea     rax, [rsp+2C8h+arg_8]
0x180066aee  mov     [rsp+2C8h+var_230], rax
0x180066af6  lea     rax, [rsp+2C8h+var_248]
0x180066afe  mov     [rsp+2C8h+var_210], rax
0x180066b06  lea     rdx, [rsp+2C8h+var_248]
0x180066b0e  mov     rcx, r14
0x180066b11  call    ?RetryOnDisconnect@HyperVFile@@AEAAX$$QEAV?$function@$$A6AXXZ@std@@@Z; HyperVFile::RetryOnDisconnect(std::function<void (void)> &&)
0x180066b16  nop
0x180066b17  mov     rcx, [rsp+2C8h+var_210]
0x180066b1f  test    rcx, rcx
0x180066b22  jz      short loc_180066B3E
0x180066b24  mov     rax, [rcx]
0x180066b27  lea     rdx, [rsp+2C8h+var_248]
0x180066b2f  cmp     rcx, rdx
0x180066b32  setnz   dl
0x180066b35  mov     rax, [rax+20h]
0x180066b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b3e  cmp     [rsp+2C8h+var_208], 0
0x180066b46  jnz     short loc_180066B85
0x180066b48  lea     rcx, [rsp+2C8h+var_1D8]; this
0x180066b50  call    ?Timeout@HyperVFile_Lock@HyperVStorageTrace@@QEAAXXZ; HyperVStorageTrace::HyperVFile_Lock::Timeout(void)
0x180066b55  cmp     [rsp+2C8h+var_208], 0
0x180066b5d  jz      short loc_180066B66
0x180066b5f  inc     dword ptr [r14+300h]
0x180066b66  mov     rcx, rbx; SRWLock
0x180066b69  cmp     dword ptr [rbx+8], 0
0x180066b6d  jz      loc_180066C33
0x180066b73  mov     dword ptr [rbx+8], 0
0x180066b7a  call    cs:__imp_ReleaseSRWLockExclusive
0x180066b80  jmp     loc_180066C39
0x180066b85  movups  xmm0, [rsp+2C8h+var_200]
0x180066b8d  movaps  [rsp+2C8h+var_288], xmm0
0x180066b92  movups  xmm1, [rsp+2C8h+var_1F0]
0x180066b9a  movaps  [rsp+2C8h+var_278], xmm1
0x180066b9f  mov     [rsp+2C8h+var_268], 1
0x180066ba4  mov     eax, [rsp+2C8h+var_267]
0x180066ba8  mov     [rsp+2C8h+var_267], eax
0x180066bac  movzx   eax, [rsp+2C8h+var_263]
0x180066bb1  mov     [rsp+2C8h+var_263], ax
0x180066bb6  mov     al, [rsp+2C8h+var_261]
0x180066bba  mov     [rsp+2C8h+var_261], al
0x180066bbe  mov     dword ptr [rsp+2C8h+var_2A8], 7
0x180066bc6  xor     r9d, r9d
0x180066bc9  lea     r8d, [r9+0Ah]
0x180066bcd  lea     rdx, [rsp+2C8h+var_288]
0x180066bd2  mov     rcx, rdi
0x180066bd5  call    ?LogOperation@HyperVStoragePerfTracker@@QEAAXV?$optional@UTimedOperation@HyperVStoragePerfTracker@@@std@@W4HvsPerfOperationType@@_KW4HvsPerfRecordType@@@Z; HyperVStoragePerfTracker::LogOperation(std::optional<HyperVStoragePerfTracker::TimedOperation>,HvsPerfOperationType,unsigned __int64,HvsPerfRecordType)
0x180066bda  lea     rcx, [rsp+2C8h+var_1D8]; this
0x180066be2  call    ?Locked@HyperVFile_Lock@HyperVStorageTrace@@QEAAXXZ; HyperVStorageTrace::HyperVFile_Lock::Locked(void)
0x180066be7  test    r15d, r15d
0x180066bea  jz      loc_180066B55
0x180066bf0  mov     rax, [r14+50h]
0x180066bf4  cmp     [r14+48h], rax
0x180066bf8  jz      short loc_180066C04
0x180066bfa  mov     rcx, r14; this
0x180066bfd  call    ?UpdateCache@HyperVFile@@IEAAXXZ; HyperVFile::UpdateCache(void)
0x180066c02  jmp     short loc_180066C2E
0x180066c04  lea     rcx, [rsp+2C8h+var_1D8]; this
0x180066c0c  call    ?Reloading@HyperVFile_Lock@HyperVStorageTrace@@QEAAXXZ; HyperVStorageTrace::HyperVFile_Lock::Reloading(void)
0x180066c11  xor     edx, edx; int
0x180066c13  mov     rcx, r14; this
0x180066c16  call    ?InitializeInternal@HyperVStorage@@IEAAXH@Z; HyperVStorage::InitializeInternal(int)
0x180066c1b  mov     rax, [r14]
0x180066c1e  mov     rcx, r14
0x180066c21  mov     rax, [rax+0B8h]
0x180066c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066c2d  nop
0x180066c2e  jmp     loc_180066B55
0x180066c33  call    cs:__imp_ReleaseSRWLockShared
0x180066c39  mov     eax, [rsp+2C8h+var_208]
0x180066c40  neg     eax
0x180066c42  sbb     edx, edx
0x180066c44  not     edx
0x180066c46  and     edx, 80004005h
0x180066c4c  lea     rcx, [rsp+2C8h+var_1D8]
0x180066c54  call    ?Stop@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180066c59  mov     ebx, [rsp+2C8h+var_208]
0x180066c60  mov     [rsp+2C8h+var_1D8], r13
0x180066c68  lea     rcx, [rsp+2C8h+var_1D8]
0x180066c70  call    ?Destroy@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180066c75  lea     rcx, [rsp+2C8h+var_58]
0x180066c7d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180066c82  lea     rcx, [rsp+2C8h+var_78]
0x180066c8a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180066c8f  lea     rcx, [rsp+2C8h+var_1D8]
0x180066c97  call    ??1?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180066c9c  mov     eax, ebx
0x180066c9e  mov     rcx, [rsp+2C8h+var_38]
0x180066ca6  xor     rcx, rsp; StackCookie
0x180066ca9  call    __security_check_cookie
0x180066cae  mov     rbx, [rsp+2C8h+arg_10]
0x180066cb6  add     rsp, 2A0h
0x180066cbd  pop     r15
0x180066cbf  pop     r14
0x180066cc1  pop     r13
0x180066cc3  pop     rdi
0x180066cc4  pop     rsi
0x180066cc5  retn
0x180066cc6  lea     rcx, [rsp+2C8h+var_1D8]; this
0x180066cce  call    ?NoCachedData@HyperVFile_Lock@HyperVStorageTrace@@QEAAXXZ; HyperVStorageTrace::HyperVFile_Lock::NoCachedData(void)
0x180066cd3  mov     ecx, 80004005h; int
0x180066cd8  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
```
