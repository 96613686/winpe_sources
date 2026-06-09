# Jot::CStorageCoreWin32::EnsureHandleSam_Internal(Jot::StorageAccessMode,MsoCF::CXReadPtr<Jot::CStorageCoreWin32::ThreadSyncHandleData,MsoCF::CSWMRLockExclusive<Jot::CStorageCoreWin32::ThreadSyncHandleData>> &,bool,std::exception_ptr *,bool,bool,bool)

- ea: `0x1801ef748`
- end: `0x1801efe7a`
- name: `?EnsureHandleSam_Internal@CStorageCoreWin32@Jot@@IEAAXW4StorageAccessMode@2@AEAV?$CXReadPtr@UThreadSyncHandleData@CStorageCoreWin32@Jot@@V?$CSWMRLockExclusive@UThreadSyncHandleData@CStorageCoreWin32@Jot@@@MsoCF@@@MsoCF@@_NPEAVexception_ptr@std@@222@Z`
- size: `1842`
- prototype: ``
- caller_count: `3`
- callee_count: `28`
- tags: `file_ops, installer_update`

## callers

- `0x1801ef718`
- `0x1801f13b0`
- `0x1801f1540`

## callees

- `0x18002efb0`
- `0x18004cb5c`
- `0x1801c3df4`
- `0x1801c5390`
- `0x1801c5510`
- `0x1801c55e4`
- `0x1801c6628`
- `0x1801eecf4`
- `0x1801eed34`
- `0x1801ef748`
- `0x1801efe7c`
- `0x1801efea0`
- `0x1801f05b0`
- `0x1801f3508`
- `0x1801f4b14`
- `0x1801f9534`
- `0x1801f9ab4`
- `0x1801f9f80`
- `0x1801fa3a8`
- `0x1802b0cb8`
- `0x1802e50d0`
- `0x1802e5170`
- `0x1802e5190`
- `0x180444d58`
- `0x18071b2a0`
- `0x180875ad8`
- `0x180dad178`
- `0x180db1474`

## import_xrefs

- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1801efc7c`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1801efe12`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1801efc7c`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1801efe12`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1801ef91e`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1801efb6f`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1801efba0`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1801ef91e`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1801efb6f`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1801efba0`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1801efa8c`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1801efdc2`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1801efa8c`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1801efdc2`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1801efa36`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1801efd31`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1801efa36`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1801efd31`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801ef929`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801efa9f`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801efb7a`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801efbab`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801efe39`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801ef929`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801efa9f`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801efb7a`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801efbab`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801efe39`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1801efc5e`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1801efdfa`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1801efc5e`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1801efdfa`

## pseudocode

```c
void __fastcall Jot::CStorageCoreWin32::EnsureHandleSam_Internal(
        Jot::CStorageCoreWin32 *this,
        unsigned int a2,
        _QWORD *a3,
        char a4,
        void *a5,
        char a6,
        char a7)
{
  __m128i si128; // xmm6
  __int64 v12; // rax
  char *v13; // rdx
  __int64 v14; // rcx
  _DWORD *v15; // rax
  __int64 v16; // rax
  const void *v17; // rax
  __int64 v18; // rsi
  Jot::CFileHandle *v19; // r15
  __int64 v20; // rcx
  __int64 v21; // rax
  const void *v22; // rax
  const void *Win32ExceptionTag; // rax
  unsigned int v24; // r9d
  int v25; // edx
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  Jot *v29; // rdx
  __int64 v30[2]; // [rsp+70h] [rbp-358h] BYREF
  int v31; // [rsp+80h] [rbp-348h]
  unsigned int v32[2]; // [rsp+88h] [rbp-340h]
  __int64 v33[2]; // [rsp+90h] [rbp-338h] BYREF
  void *v34; // [rsp+A8h] [rbp-320h]
  void **v35; // [rsp+B8h] [rbp-310h] BYREF
  __int128 v36; // [rsp+C0h] [rbp-308h]
  _BYTE v37[16]; // [rsp+D8h] [rbp-2F0h] BYREF
  _BYTE v38[16]; // [rsp+E8h] [rbp-2E0h] BYREF
  _BYTE v39[32]; // [rsp+F8h] [rbp-2D0h] BYREF
  _BYTE v40[32]; // [rsp+118h] [rbp-2B0h] BYREF
  _BYTE v41[136]; // [rsp+138h] [rbp-290h] BYREF
  _BYTE v42[72]; // [rsp+1C0h] [rbp-208h] BYREF
  Jot *v43[3]; // [rsp+208h] [rbp-1C0h] BYREF
  unsigned __int64 v44; // [rsp+220h] [rbp-1A8h]
  _QWORD v45[10]; // [rsp+230h] [rbp-198h] BYREF
  _BYTE pExceptionObject[80]; // [rsp+280h] [rbp-148h] BYREF
  _BYTE v47[80]; // [rsp+2D0h] [rbp-F8h] BYREF
  _BYTE v48[80]; // [rsp+320h] [rbp-A8h] BYREF

  v34 = a5;
  v31 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    v12 = *a3;
    v13 = (char *)this + 128;
    if ( a6 )
      break;
    (*(void (__fastcall **)(_QWORD *, char *))(v12 + 8))(a3, v13);
LABEL_4:
    if ( (a2 & 2) != 0 && (*(unsigned __int8 (__fastcall **)(Jot::CStorageCoreWin32 *))(*(_QWORD *)this + 376LL))(this) )
    {
      if ( a5 )
      {
        Win32ExceptionTag = (const void *)Jot::CreateWin32ExceptionTag(v30, 5, 22062593);
        __ExceptionPtrAssign(a5, Win32ExceptionTag);
        __ExceptionPtrDestroy(v30);
      }
      if ( a4 )
        Jot::CStorageCoreWin32::ThrowError(this, 5u);
      return;
    }
    v14 = a3[2];
    v15 = (_DWORD *)(v14 + 40);
    if ( (unsigned __int64)(*(_QWORD *)(v14 + 32) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL && *v15 || *v15 != a2 )
    {
      Jot::CFileHandle::CFileHandle((Jot::CFileHandle *)v37);
      v36 = 0;
      v35 = &MsoCF::CXWritePtr<Jot::CStorageCoreWin32::ThreadSyncHandleData,MsoCF::CSWMRLockExclusive<Jot::CStorageCoreWin32::ThreadSyncHandleData>>::`vftable';
      if ( a6 )
      {
        if ( !a5 || a4 )
        {
          Jot::ErrCannotPerformSynchronouslyQuick::ErrCannotPerformSynchronouslyQuick(v47, 17147394);
          throw (Jot::ErrCannotPerformSynchronouslyQuick *)v47;
        }
        v16 = Jot::ErrCannotPerformSynchronouslyQuick::ErrCannotPerformSynchronouslyQuick(v42, 22062594);
        v17 = (const void *)std::make_exception_ptr<Jot::ErrCannotPerformSynchronouslyQuick>(v30, v16);
        __ExceptionPtrAssign(a5, v17);
        __ExceptionPtrDestroy(v30);
        v35 = &MsoCF::CXReadPtr<Jot::CStorageCoreWin32::ThreadSyncHandleData,MsoCF::CSWMRLockExclusive<Jot::CStorageCoreWin32::ThreadSyncHandleData>>::`vftable';
        Jot::CFileHandle::CloseHandle((Jot::CFileHandle *)v37);
        Jot::CFileRegionLock::Unlock((Jot::CFileRegionLock *)v41);
        Jot::CFileRegionLock::Unlock((Jot::CFileRegionLock *)v40);
        Jot::CFileRegionLock::Unlock((Jot::CFileRegionLock *)v39);
        MsoCF::CSemaphore::~CSemaphore((MsoCF::CSemaphore *)v38);
        MsoCF::CSemaphore::~CSemaphore((MsoCF::CSemaphore *)v37);
        return;
      }
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD *))(*a3 + 32LL))(a3) )
        (*(void (__fastcall **)(_QWORD *))(*a3 + 24LL))(a3);
      MsoCF::CXWritePtr<Jot::CStorageCoreWin32::ThreadSyncHandleData,MsoCF::CSWMRLockExclusive<Jot::CStorageCoreWin32::ThreadSyncHandleData>>::Set(
        &v35,
        (char *)this + 128);
      v18 = *((_QWORD *)&v36 + 1);
      v19 = (Jot::CFileHandle *)(*((_QWORD *)&v36 + 1) + 32LL);
      v20 = *(_QWORD *)(*((_QWORD *)&v36 + 1) + 32LL);
      if ( (((v20 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 || !*(_DWORD *)(*((_QWORD *)&v36 + 1) + 40LL))
        && *(_DWORD *)(*((_QWORD *)&v36 + 1) + 40LL) == a2 )
      {
        goto LABEL_37;
      }
      if ( (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && *((_BYTE *)this + 859) )
        Jot::CStorageCoreWin32::UpdateReconnectData(v20, &v35);
      if ( a2 && *(_BYTE *)(v18 + 496) )
      {
        Jot::ErrJotStorage_NoReconnectServerChanged::ErrJotStorage_NoReconnectServerChanged(v48, 17147395);
        throw (Jot::ErrJotStorage_NoReconnectServerChanged *)v48;
      }
      (*(void (__fastcall **)(Jot::CStorageCoreWin32 *, Jot **))(*(_QWORD *)this + 352LL))(this, v43);
      if ( (unsigned __int8)Jot::CFileHandle::CanTransitionToSam(v19, a2) )
      {
        *(_OWORD *)v30 = 0;
        __ExceptionPtrCreate(v30);
        (*(void (__fastcall **)(Jot::CStorageCoreWin32 *, _QWORD))(*(_QWORD *)this + 360LL))(
          this,
          *((unsigned int *)this + 213));
        Jot::CFileHandle::TransitionToSam(v19, (__int64)v30);
        if ( !__ExceptionPtrToBool(v30) )
        {
          __ExceptionPtrDestroy(v30);
          *(__m128i *)v30 = si128;
LABEL_34:
          if ( v44 > 7 )
            std::_Deallocate<16>(v43[0], 2 * v44 + 2);
LABEL_37:
          if ( (_QWORD)v36 )
            Ofc::CSWMRLock::LeaveWrite((Ofc::CSWMRLock *)(v36 + 544));
          Jot::CFileHandle::CloseHandle((Jot::CFileHandle *)v37);
          Jot::CFileRegionLock::Unlock((Jot::CFileRegionLock *)v41);
          Jot::CFileRegionLock::Unlock((Jot::CFileRegionLock *)v40);
          Jot::CFileRegionLock::Unlock((Jot::CFileRegionLock *)v39);
          MsoCF::CSemaphore::~CSemaphore((MsoCF::CSemaphore *)v38);
          MsoCF::CSemaphore::~CSemaphore((MsoCF::CSemaphore *)v37);
          goto LABEL_8;
        }
        *(_OWORD *)v33 = 0;
        __ExceptionPtrCopy(v33, v30);
        *(_QWORD *)v32 = v33;
        __ExceptionPtrRethrow(v33);
      }
      v32[0] = (*(__int64 (__fastcall **)(Jot::CStorageCoreWin32 *, _QWORD))(*(_QWORD *)this + 360LL))(
                 this,
                 *((unsigned int *)this + 213));
      if ( !(*(unsigned __int8 (__fastcall **)(Jot::CStorageCoreWin32 *))(*(_QWORD *)this + 368LL))(this) )
      {
        if ( Jot::ShouldLogTtid((Jot *)0x40C0CB, 0x100ACu, 3u, v24) )
          Jot::Log_Impl<wchar_t [95],std::wstring>(v26, v25, v27, v28, (__int64)v43);
        Jot::ExceptionWithErrorCode::ExceptionWithErrorCode(v45, 17147397);
        v45[0] = &Jot::ErrFileHandleDeniedByClientCode::`vftable';
        throw (Jot::ErrFileHandleDeniedByClientCode *)v45;
      }
      *(_OWORD *)v33 = 0;
      __ExceptionPtrCreate(v33);
      v29 = (Jot *)v43;
      if ( v44 > 7 )
        v29 = v43[0];
      Jot::CFileHandle::_CreateFile(
        (struct Jot::ReconnectCoherencyData *)v37,
        v29,
        v32[0],
        *((_BYTE *)this + 856),
        a7,
        v19,
        (__int64)v33,
        (Jot *)(v18 + 497),
        v19,
        *((_QWORD *)this + 100));
      if ( __ExceptionPtrToBool(v33) )
      {
        if ( (unsigned __int8)Jot::IsError<Jot::ErrJotStorage_NoReconnectServerChanged>(v33) )
          *(_BYTE *)(v18 + 496) = 1;
        *(_OWORD *)v30 = 0;
        __ExceptionPtrCopy(v30, v33);
        *(_QWORD *)v32 = v30;
        __ExceptionPtrRethrow(v30);
      }
      Jot::CFileHandle::CloseHandle(v19);
      Jot::CFileHandle::TransferFrom(v19, (struct Jot::CFileHandle *)v37);
      __ExceptionPtrDestroy(v33);
      *(__m128i *)v33 = si128;
      goto LABEL_34;
    }
LABEL_8:
    if ( a3[1] )
    {
      if ( a5 )
        std::exception_ptr::operator=(a5);
      return;
    }
  }
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, char *))(v12 + 16))(a3, v13) )
    goto LABEL_4;
  if ( a5 )
  {
    v21 = Jot::ErrCannotPerformSynchronouslyQuick::ErrCannotPerformSynchronouslyQuick(v42, 22062563);
    v22 = (const void *)std::make_exception_ptr<Jot::ErrCannotPerformSynchronouslyQuick>(v30, v21);
    __ExceptionPtrAssign(a5, v22);
    __ExceptionPtrDestroy(v30);
  }
  if ( a4 )
  {
    Jot::ErrCannotPerformSynchronouslyQuick::ErrCannotPerformSynchronouslyQuick(pExceptionObject, 22062592);
    throw (Jot::ErrCannotPerformSynchronouslyQuick *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x1801ef748  mov     rax, rsp
0x1801ef74b  push    rbx
0x1801ef74c  push    rsi
0x1801ef74d  push    rdi
0x1801ef74e  push    r12
0x1801ef750  push    r13
0x1801ef752  push    r14
0x1801ef754  push    r15
0x1801ef756  sub     rsp, 390h
0x1801ef75d  movaps  xmmword ptr [rax-48h], xmm6
0x1801ef761  mov     rax, cs:__security_cookie
0x1801ef768  xor     rax, rsp
0x1801ef76b  mov     [rsp+3C8h+var_58], rax
0x1801ef773  mov     r13b, r9b
0x1801ef776  mov     r14, r8
0x1801ef779  mov     r12d, edx
0x1801ef77c  mov     rbx, rcx
0x1801ef77f  mov     [rsp+3C8h+var_368], r9b
0x1801ef784  mov     rdi, [rsp+3C8h+arg_20]
0x1801ef78c  mov     [rsp+3C8h+var_320], rdi
0x1801ef794  xor     r15d, r15d
0x1801ef797  mov     [rsp+3C8h+var_348], r15d
0x1801ef79f  movdqa  xmm6, cs:__xmm@0000000000004de10000000000004de1
0x1801ef7a7  mov     rax, [r14]
0x1801ef7aa  lea     rsi, [rbx+80h]
0x1801ef7b1  mov     rdx, rsi
0x1801ef7b4  mov     rcx, r14
0x1801ef7b7  cmp     [rsp+3C8h+arg_28], r15b
0x1801ef7bf  jnz     loc_1801EF869
0x1801ef7c5  mov     rax, [rax+8]
0x1801ef7c9  call    cs:__guard_dispatch_icall_fptr
0x1801ef7cf  test    r12b, 2
0x1801ef7d3  jnz     short loc_1801EF836
0x1801ef7d5  mov     rcx, [r14+10h]
0x1801ef7d9  mov     rax, [rcx+20h]
0x1801ef7dd  dec     rax
0x1801ef7e0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801ef7e4  lea     rax, [rcx+28h]
0x1801ef7e8  jbe     short loc_1801EF7F3
0x1801ef7ea  cmp     [rax], r15d
0x1801ef7ed  jnz     loc_1801EF8B0
0x1801ef7f3  cmp     [rax], r12d
0x1801ef7f6  jnz     loc_1801EF8B0
0x1801ef7fc  cmp     [r14+8], r15
0x1801ef800  jz      short loc_1801EF7A7
0x1801ef802  test    rdi, rdi
0x1801ef805  jnz     loc_1801EFE4D
0x1801ef80b  mov     rcx, [rsp+3C8h+var_58]
0x1801ef813  xor     rcx, rsp; StackCookie
0x1801ef816  call    __security_check_cookie
0x1801ef81b  movaps  xmm6, [rsp+3C8h+var_48]
0x1801ef823  add     rsp, 390h
0x1801ef82a  pop     r15
0x1801ef82c  pop     r14
0x1801ef82e  pop     r13
0x1801ef830  pop     r12
0x1801ef832  pop     rdi
0x1801ef833  pop     rsi
0x1801ef834  pop     rbx
0x1801ef835  retn
0x1801ef836  mov     rax, [rbx]
0x1801ef839  mov     rcx, rbx
0x1801ef83c  mov     rax, [rax+178h]
0x1801ef843  call    cs:__guard_dispatch_icall_fptr
0x1801ef849  test    al, al
0x1801ef84b  jz      short loc_1801EF7D5
0x1801ef84d  test    rdi, rdi
0x1801ef850  jnz     loc_1801EFB85
0x1801ef856  test    r13b, r13b
0x1801ef859  jz      short loc_1801EF80B
0x1801ef85b  mov     edx, 5; unsigned int
0x1801ef860  mov     rcx, rbx; this
0x1801ef863  call    ?ThrowError@CStorageCoreWin32@Jot@@IEAAXK@Z; Jot::CStorageCoreWin32::ThrowError(ulong)
0x1801ef869  mov     rax, [rax+10h]
0x1801ef86d  call    cs:__guard_dispatch_icall_fptr
0x1801ef873  test    al, al
0x1801ef875  jnz     loc_1801EF7CF
0x1801ef87b  test    rdi, rdi
0x1801ef87e  jnz     loc_1801EFB4A
0x1801ef884  test    r13b, r13b
0x1801ef887  jz      short loc_1801EF80B
0x1801ef889  mov     edx, 150A600h
0x1801ef88e  lea     rcx, [rsp+3C8h+pExceptionObject]
0x1801ef896  call    ??0ErrCannotPerformSynchronouslyQuick@Jot@@QEAA@VExceptionTag@1@@Z; Jot::ErrCannotPerformSynchronouslyQuick::ErrCannotPerformSynchronouslyQuick(Jot::ExceptionTag)
0x1801ef89b  lea     rdx, _TI3?AUErrCannotPerformSynchronouslyQuick@Jot@@; pThrowInfo
0x1801ef8a2  lea     rcx, [rsp+3C8h+pExceptionObject]; pExceptionObject
0x1801ef8aa  call    _CxxThrowException_0
0x1801ef8b0  lea     rcx, [rsp+3C8h+var_2F0]; this
0x1801ef8b8  call    ??0CFileHandle@Jot@@QEAA@XZ; Jot::CFileHandle::CFileHandle(void)
0x1801ef8bd  nop
0x1801ef8be  xorps   xmm0, xmm0
0x1801ef8c1  movdqu  [rsp+3C8h+var_308], xmm0
0x1801ef8ca  lea     rax, ??_7?$CXWritePtr@UThreadSyncHandleData@CStorageCoreWin32@Jot@@V?$CSWMRLockExclusive@UThreadSyncHandleData@CStorageCoreWin32@Jot@@@MsoCF@@@MsoCF@@6B@; const MsoCF::CXWritePtr<Jot::CStorageCoreWin32::ThreadSyncHandleData,MsoCF::CSWMRLockExclusive<Jot::CStorageCoreWin32::ThreadSyncHandleData>>::`vftable'
0x1801ef8d1  mov     [rsp+3C8h+var_310], rax
0x1801ef8d9  cmp     [rsp+3C8h+arg_28], r15b
0x1801ef8e1  jz      loc_1801EF991
0x1801ef8e7  test    rdi, rdi
0x1801ef8ea  jz      loc_1801EFBB6
0x1801ef8f0  test    r13b, r13b
0x1801ef8f3  jnz     loc_1801EFBB6
0x1801ef8f9  mov     edx, 150A602h
0x1801ef8fe  lea     rcx, [rsp+3C8h+var_208]
0x1801ef906  call    ??0ErrCannotPerformSynchronouslyQuick@Jot@@QEAA@VExceptionTag@1@@Z; Jot::ErrCannotPerformSynchronouslyQuick::ErrCannotPerformSynchronouslyQuick(Jot::ExceptionTag)
0x1801ef90b  mov     rdx, rax
0x1801ef90e  lea     rcx, [rsp+3C8h+var_358]
0x1801ef913  call    ??$make_exception_ptr@UErrCannotPerformSynchronouslyQuick@Jot@@@std@@YA?AVexception_ptr@0@UErrCannotPerformSynchronouslyQuick@Jot@@@Z; std::make_exception_ptr<Jot::ErrCannotPerformSynchronouslyQuick>(Jot::ErrCannotPerformSynchronouslyQuick)
0x1801ef918  mov     rdx, rax
0x1801ef91b  mov     rcx, rdi
0x1801ef91e  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1801ef924  lea     rcx, [rsp+3C8h+var_358]
0x1801ef929  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1801ef92f  lea     rax, ??_7?$CXReadPtr@UThreadSyncHandleData@CStorageCoreWin32@Jot@@V?$CSWMRLockExclusive@UThreadSyncHandleData@CStorageCoreWin32@Jot@@@MsoCF@@@MsoCF@@6B@; const MsoCF::CXReadPtr<Jot::CStorageCoreWin32::ThreadSyncHandleData,MsoCF::CSWMRLockExclusive<Jot::CStorageCoreWin32::ThreadSyncHandleData>>::`vftable'
0x1801ef936  mov     [rsp+3C8h+var_310], rax
0x1801ef93e  lea     rcx, [rsp+3C8h+var_2F0]; this
0x1801ef946  call    ?CloseHandle@CFileHandle@Jot@@QEAAXXZ; Jot::CFileHandle::CloseHandle(void)
0x1801ef94b  lea     rcx, [rsp+3C8h+var_290]; this
0x1801ef953  call    ?Unlock@CFileRegionLock@Jot@@QEAAXXZ; Jot::CFileRegionLock::Unlock(void)
0x1801ef958  lea     rcx, [rsp+3C8h+var_2B0]; this
0x1801ef960  call    ?Unlock@CFileRegionLock@Jot@@QEAAXXZ; Jot::CFileRegionLock::Unlock(void)
0x1801ef965  lea     rcx, [rsp+3C8h+var_2D0]; this
0x1801ef96d  call    ?Unlock@CFileRegionLock@Jot@@QEAAXXZ; Jot::CFileRegionLock::Unlock(void)
0x1801ef972  lea     rcx, [rsp+3C8h+var_2E0]; this
0x1801ef97a  call    ??1CSemaphore@MsoCF@@QEAA@XZ; MsoCF::CSemaphore::~CSemaphore(void)
0x1801ef97f  lea     rcx, [rsp+3C8h+var_2F0]; this
0x1801ef987  call    ??1CSemaphore@MsoCF@@QEAA@XZ; MsoCF::CSemaphore::~CSemaphore(void)
0x1801ef98c  jmp     loc_1801EF80B
0x1801ef991  mov     rax, [r14]
0x1801ef994  mov     rcx, r14
0x1801ef997  mov     rax, [rax+20h]
0x1801ef99b  call    cs:__guard_dispatch_icall_fptr
0x1801ef9a1  test    al, al
0x1801ef9a3  jz      loc_1801EFBDC
0x1801ef9a9  mov     rdx, rsi
0x1801ef9ac  lea     rcx, [rsp+3C8h+var_310]
0x1801ef9b4  call    ?Set@?$CXWritePtr@UThreadSyncHandleData@CStorageCoreWin32@Jot@@V?$CSWMRLockExclusive@UThreadSyncHandleData@CStorageCoreWin32@Jot@@@MsoCF@@@MsoCF@@UEAAXPEAV?$CSWMRLockExclusive@UThreadSyncHandleData@CStorageCoreWin32@Jot@@@2@@Z; MsoCF::CXWritePtr<Jot::CStorageCoreWin32::ThreadSyncHandleData,MsoCF::CSWMRLockExclusive<Jot::CStorageCoreWin32::ThreadSyncHandleData>>::Set(MsoCF::CSWMRLockExclusive<Jot::CStorageCoreWin32::ThreadSyncHandleData> *)
0x1801ef9b9  mov     rsi, qword ptr [rsp+3C8h+var_308+8]
0x1801ef9c1  lea     r15, [rsi+20h]
0x1801ef9c5  mov     rcx, [r15]
0x1801ef9c8  lea     rax, [rcx+1]
0x1801ef9cc  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801ef9d2  jnz     loc_1801EFAD0
0x1801ef9d8  cmp     dword ptr [rsi+28h], 0
0x1801ef9dc  jz      loc_1801EFAD0
0x1801ef9e2  lea     rax, [rcx-1]
0x1801ef9e6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801ef9ea  jbe     loc_1801EFBF1
0x1801ef9f0  test    r12d, r12d
0x1801ef9f3  jnz     loc_1801EFC11
0x1801ef9f9  mov     rax, [rbx]
0x1801ef9fc  lea     rdx, [rsp+3C8h+var_1C0]
0x1801efa04  mov     rcx, rbx
0x1801efa07  mov     rax, [rax+160h]
0x1801efa0e  call    cs:__guard_dispatch_icall_fptr
0x1801efa14  nop
0x1801efa15  mov     edx, r12d
0x1801efa18  mov     rcx, r15
0x1801efa1b  call    ?CanTransitionToSam@CFileHandle@Jot@@QEBA_NW4StorageAccessMode@2@@Z; Jot::CFileHandle::CanTransitionToSam(Jot::StorageAccessMode)
0x1801efa20  test    al, al
0x1801efa22  jz      loc_1801EFC83
0x1801efa28  xorps   xmm0, xmm0
0x1801efa2b  movdqu  xmmword ptr [rsp+3C8h+var_358], xmm0
0x1801efa31  lea     rcx, [rsp+3C8h+var_358]
0x1801efa36  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1801efa3c  mov     rax, [rbx]
0x1801efa3f  mov     edx, [rbx+354h]
0x1801efa45  mov     rcx, rbx
0x1801efa48  mov     rax, [rax+168h]
0x1801efa4f  call    cs:__guard_dispatch_icall_fptr
0x1801efa55  lea     r8, [rsp+3C8h+var_1C0]
0x1801efa5d  cmp     [rsp+3C8h+var_1A8], 7
0x1801efa66  cmova   r8, [rsp+3C8h+var_1C0]
0x1801efa6f  lea     rcx, [rsp+3C8h+var_358]
0x1801efa74  mov     qword ptr [rsp+3C8h+var_3A8], rcx; __int64
0x1801efa79  mov     r9d, eax
0x1801efa7c  mov     edx, r12d
0x1801efa7f  mov     rcx, r15; this
0x1801efa82  call    ?TransitionToSam@CFileHandle@Jot@@QEAAXW4StorageAccessMode@2@V?$String@UWzTraits@MsoCF@@@MsoCF@@KPEAVexception_ptr@std@@@Z; Jot::CFileHandle::TransitionToSam(Jot::StorageAccessMode,MsoCF::String<MsoCF::WzTraits>,ulong,std::exception_ptr *)
0x1801efa87  lea     rcx, [rsp+3C8h+var_358]
0x1801efa8c  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1801efa92  test    al, al
0x1801efa94  jnz     loc_1801EFC45
0x1801efa9a  lea     rcx, [rsp+3C8h+var_358]
0x1801efa9f  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1801efaa5  movdqu  xmmword ptr [rsp+3C8h+var_358], xmm6
0x1801efaab  mov     rdx, [rsp+3C8h+var_1A8]
0x1801efab3  cmp     rdx, 7
0x1801efab7  jbe     short loc_1801EFADA
0x1801efab9  lea     rdx, ds:2[rdx*2]
0x1801efac1  mov     rcx, [rsp+3C8h+var_1C0]
0x1801efac9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801eface  jmp     short loc_1801EFADA
0x1801efad0  cmp     [rsi+28h], r12d
0x1801efad4  jnz     loc_1801EF9E2
0x1801efada  mov     rcx, qword ptr [rsp+3C8h+var_308]
0x1801efae2  xor     r15d, r15d
0x1801efae5  test    rcx, rcx
0x1801efae8  jz      short loc_1801EFAF7
0x1801efaea  add     rcx, 220h; this
0x1801efaf1  call    ?LeaveWrite@CSWMRLock@Ofc@@QEAAXXZ; Ofc::CSWMRLock::LeaveWrite(void)
0x1801efaf6  nop
0x1801efaf7  lea     rcx, [rsp+3C8h+var_2F0]; this
0x1801efaff  call    ?CloseHandle@CFileHandle@Jot@@QEAAXXZ; Jot::CFileHandle::CloseHandle(void)
0x1801efb04  lea     rcx, [rsp+3C8h+var_290]; this
0x1801efb0c  call    ?Unlock@CFileRegionLock@Jot@@QEAAXXZ; Jot::CFileRegionLock::Unlock(void)
0x1801efb11  lea     rcx, [rsp+3C8h+var_2B0]; this
0x1801efb19  call    ?Unlock@CFileRegionLock@Jot@@QEAAXXZ; Jot::CFileRegionLock::Unlock(void)
0x1801efb1e  lea     rcx, [rsp+3C8h+var_2D0]; this
0x1801efb26  call    ?Unlock@CFileRegionLock@Jot@@QEAAXXZ; Jot::CFileRegionLock::Unlock(void)
0x1801efb2b  lea     rcx, [rsp+3C8h+var_2E0]; this
0x1801efb33  call    ??1CSemaphore@MsoCF@@QEAA@XZ; MsoCF::CSemaphore::~CSemaphore(void)
0x1801efb38  lea     rcx, [rsp+3C8h+var_2F0]; this
0x1801efb40  call    ??1CSemaphore@MsoCF@@QEAA@XZ; MsoCF::CSemaphore::~CSemaphore(void)
0x1801efb45  jmp     loc_1801EF7FC
0x1801efb4a  mov     edx, 150A5E3h
0x1801efb4f  lea     rcx, [rsp+3C8h+var_208]
0x1801efb57  call    ??0ErrCannotPerformSynchronouslyQuick@Jot@@QEAA@VExceptionTag@1@@Z; Jot::ErrCannotPerformSynchronouslyQuick::ErrCannotPerformSynchronouslyQuick(Jot::ExceptionTag)
0x1801efb5c  mov     rdx, rax
0x1801efb5f  lea     rcx, [rsp+3C8h+var_358]
0x1801efb64  call    ??$make_exception_ptr@UErrCannotPerformSynchronouslyQuick@Jot@@@std@@YA?AVexception_ptr@0@UErrCannotPerformSynchronouslyQuick@Jot@@@Z; std::make_exception_ptr<Jot::ErrCannotPerformSynchronouslyQuick>(Jot::ErrCannotPerformSynchronouslyQuick)
0x1801efb69  mov     rdx, rax
0x1801efb6c  mov     rcx, rdi
0x1801efb6f  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1801efb75  lea     rcx, [rsp+3C8h+var_358]
0x1801efb7a  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1801efb80  jmp     loc_1801EF884
0x1801efb85  mov     edx, 5
0x1801efb8a  mov     r8d, 150A601h
0x1801efb90  lea     rcx, [rsp+3C8h+var_358]
0x1801efb95  call    ?CreateWin32ExceptionTag@Jot@@YA?AVexception_ptr@std@@KK@Z; Jot::CreateWin32ExceptionTag(ulong,ulong)
0x1801efb9a  mov     rdx, rax
0x1801efb9d  mov     rcx, rdi
0x1801efba0  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1801efba6  lea     rcx, [rsp+3C8h+var_358]
0x1801efbab  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1801efbb1  jmp     loc_1801EF856
0x1801efbb6  mov     edx, 105A602h
0x1801efbbb  lea     rcx, [rsp+3C8h+var_F8]
0x1801efbc3  call    ??0ErrCannotPerformSynchronouslyQuick@Jot@@QEAA@VExceptionTag@1@@Z; Jot::ErrCannotPerformSynchronouslyQuick::ErrCannotPerformSynchronouslyQuick(Jot::ExceptionTag)
0x1801efbc8  lea     rdx, _TI3?AUErrCannotPerformSynchronouslyQuick@Jot@@; pThrowInfo
0x1801efbcf  lea     rcx, [rsp+3C8h+var_F8]; pExceptionObject
0x1801efbd7  call    _CxxThrowException_0
0x1801efbdc  mov     rax, [r14]
0x1801efbdf  mov     rcx, r14
0x1801efbe2  mov     rax, [rax+18h]
0x1801efbe6  call    cs:__guard_dispatch_icall_fptr
0x1801efbec  jmp     loc_1801EF9A9
0x1801efbf1  mov     al, [rbx+35Bh]
0x1801efbf7  test    al, al
0x1801efbf9  jz      loc_1801EF9F0
0x1801efbff  lea     rdx, [rsp+3C8h+var_310]
0x1801efc07  call    ?UpdateReconnectData@CStorageCoreWin32@Jot@@IEAAXAEAV?$CXWritePtr@UThreadSyncHandleData@CStorageCoreWin32@Jot@@V?$CSWMRLockExclusive@UThreadSyncHandleData@CStorageCoreWin32@Jot@@@MsoCF@@@MsoCF@@PEAVexception_ptr@std@@@Z; Jot::CStorageCoreWin32::UpdateReconnectData(MsoCF::CXWritePtr<Jot::CStorageCoreWin32::ThreadSyncHandleData,MsoCF::CSWMRLockExclusive<Jot::CStorageCoreWin32::ThreadSyncHandleData>> &,std::exception_ptr *)
0x1801efc0c  jmp     loc_1801EF9F0
0x1801efc11  cmp     byte ptr [rsi+1F0h], 0
0x1801efc18  jz      loc_1801EF9F9
0x1801efc1e  mov     edx, 105A603h
0x1801efc23  lea     rcx, [rsp+3C8h+var_A8]
0x1801efc2b  call    ??0ErrJotStorage_NoReconnectServerChanged@Jot@@QEAA@VExceptionTag@1@@Z; Jot::ErrJotStorage_NoReconnectServerChanged::ErrJotStorage_NoReconnectServerChanged(Jot::ExceptionTag)
0x1801efc30  lea     rdx, _TI5?AUErrJotStorage_NoReconnectServerChanged@Jot@@; pThrowInfo
0x1801efc37  lea     rcx, [rsp+3C8h+var_A8]; pExceptionObject
0x1801efc3f  call    _CxxThrowException_0
0x1801efc45  xorps   xmm0, xmm0
0x1801efc48  movdqu  xmmword ptr [rsp+3C8h+var_338], xmm0
0x1801efc51  lea     rdx, [rsp+3C8h+var_358]
0x1801efc56  lea     rcx, [rsp+3C8h+var_338]
0x1801efc5e  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1801efc64  lea     rax, [rsp+3C8h+var_338]
0x1801efc6c  mov     qword ptr [rsp+3C8h+var_340], rax
0x1801efc74  lea     rcx, [rsp+3C8h+var_338]
0x1801efc7c  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1801efc82  nop
0x1801efc83  mov     rax, [rbx]
0x1801efc86  mov     edx, [rbx+354h]
0x1801efc8c  mov     rcx, rbx
0x1801efc8f  mov     rax, [rax+168h]
0x1801efc96  call    cs:__guard_dispatch_icall_fptr
0x1801efc9c  mov     [rsp+3C8h+var_340], eax
0x1801efca3  mov     rcx, [rbx]
0x1801efca6  mov     rax, [rcx+170h]
0x1801efcad  mov     rcx, rbx
0x1801efcb0  call    cs:__guard_dispatch_icall_fptr
0x1801efcb6  test    al, al
0x1801efcb8  jnz     short loc_1801EFD1D
0x1801efcba  mov     edx, 100ACh; unsigned int
0x1801efcbf  mov     ecx, 40C0CBh; this
0x1801efcc4  mov     r8d, 3; unsigned int
0x1801efcca  call    ?ShouldLogTtid@Jot@@YA_NKII@Z; Jot::ShouldLogTtid(ulong,uint,uint)
0x1801efccf  test    al, al
0x1801efcd1  jz      short loc_1801EFCE6
0x1801efcd3  lea     rax, [rsp+3C8h+var_1C0]
0x1801efcdb  mov     qword ptr [rsp+3C8h+var_3A8], rax
0x1801efce0  call    ??$Log_Impl@$$BY0FP@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Jot@@YAXKIW4LogMessageSeverity@0@AEAY0FP@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Jot::Log_Impl<wchar_t [95],std::wstring>(ulong,uint,Jot::LogMessageSeverity,wchar_t const (&)[95],std::wstring const &)
0x1801efce5  nop
0x1801efce6  jmp     short $+2
0x1801efce8  mov     edx, 105A605h
0x1801efced  lea     rcx, [rsp+3C8h+var_198]
0x1801efcf5  call    ??0ExceptionWithErrorCode@Jot@@QEAA@VExceptionTag@1@@Z; Jot::ExceptionWithErrorCode::ExceptionWithErrorCode(Jot::ExceptionTag)
0x1801efcfa  lea     rax, ??_7ErrFileHandleDeniedByClientCode@Jot@@6B@; const Jot::ErrFileHandleDeniedByClientCode::`vftable'
0x1801efd01  mov     [rsp+3C8h+var_198], rax
0x1801efd09  lea     rdx, _TI3?AUErrFileHandleDeniedByClientCode@Jot@@; pThrowInfo
0x1801efd10  lea     rcx, [rsp+3C8h+var_198]; pExceptionObject
  ... truncated ...
```
