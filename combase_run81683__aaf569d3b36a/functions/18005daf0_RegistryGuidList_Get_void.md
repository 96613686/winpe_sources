# RegistryGuidList::Get(void)

- ea: `0x18005daf0`
- end: `0x18005df40`
- name: `?Get@RegistryGuidList@@QEAA?AV?$ReferencedPtr@VArrayOfGuids@@@ObjectLibrary@@XZ`
- size: `1104`
- prototype: `ObjectLibrary::ReferencedPtr<ArrayOfGuids> *__fastcall(RegistryGuidList *this, ObjectLibrary::ReferencedPtr<ArrayOfGuids> *result)`
- caller_count: `4`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019690`
- `0x18005d8ec`
- `0x1800c6088`
- `0x1801514b4`

## callees

- `0x18000833c`
- `0x180020e14`
- `0x18004cce8`
- `0x18005aa10`
- `0x18005b0a0`
- `0x18005b454`
- `0x18005b7cc`
- `0x18005c72c`
- `0x18005c75c`
- `0x18005daf0`
- `0x18005df48`
- `0x18005f688`
- `0x180084480`
- `0x18008cdd8`
- `0x18012eb3c`
- `0x180179024`
- `0x1801999b0`
- `0x18019a654`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005dca8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005df04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005dca8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005df04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005ddda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005ddda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dbfc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005de3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005de4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005de61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dbfc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005de3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005de4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005de61`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005deab`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005deab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005dbc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005dd3b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005dbc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005dd3b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005dc0e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005dc0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ddec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ddec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005db85`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005db85`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005db7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005dc33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005db7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005dc33`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005db2d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005db2d`

## string_xrefs

- `0x18005dc79`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005de0a`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005dec8`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005dc6d`: `path:%ls`
- `0x18005ddfe`: `path:%ls`
- `0x18005db62`: `onecore\com\combase\inc\RegistryWatcher.hpp`

## pseudocode

```c
ObjectLibrary::ReferencedPtr<ArrayOfGuids> *__fastcall RegistryGuidList::Get(
        RegistryGuidList *this,
        ObjectLibrary::ReferencedPtr<ArrayOfGuids> *result)
{
  Microsoft::WRL::Wrappers::SRWLock *p_lock; // rbx
  std::unique_ptr<RegistryPathWatcher> *p_pathWatcher; // rdi
  void *m_ptr; // rcx
  unsigned int v7; // r8d
  LSTATUS v8; // eax
  HRESULT v9; // r15d
  HKEY__ *volatile hkey; // rax
  ArrayOfGuids *ptr; // rax
  RegistryPathWatcher *v13; // rax
  _GUID *v14; // rax
  std::default_delete<RegistryPathWatcher> *v15; // rcx
  const wchar_t *listRootPath; // r12
  _GUID *Myval2; // rdi
  LSTATUS v18; // eax
  HRESULT v19; // r15d
  unsigned int v20; // r15d
  ObjectLibrary::ReferencedPtr<ArrayOfGuids> *v21; // rax
  ArrayOfGuids *v22; // rcx
  ArrayOfGuids *v23; // rax
  _GUID *v24; // rcx
  ArrayOfGuids *v25; // rax
  HKEY__ *volatile v26; // rax
  HRESULT v27; // eax
  bool v28; // sf
  SIZE_T v29; // rax
  unsigned int i; // r12d
  unsigned __int64 v31; // rax
  __int64 v32; // rax
  LPDWORD lpcbMaxSubKeyLen; // [rsp+28h] [rbp-D8h]
  unsigned int *lpcbMaxClassLen; // [rsp+30h] [rbp-D0h]
  RegistryKey valueNameLength; // [rsp+60h] [rbp-A0h] BYREF
  RegistryKey listRootKey; // [rsp+68h] [rbp-98h] BYREF
  unsigned int count; // [rsp+70h] [rbp-90h] BYREF
  std::unique_ptr<_GUID [0]> guids; // [rsp+78h] [rbp-88h] BYREF
  unsigned int valueType; // [rsp+80h] [rbp-80h] BYREF
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive lock; // [rsp+88h] [rbp-78h] BYREF
  _GUID guid; // [rsp+90h] [rbp-70h] BYREF
  char v42; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t valueName[264]; // [rsp+B0h] [rbp-50h] BYREF
  void *retaddr; // [rsp+308h] [rbp+208h]

  p_lock = &this->_lock;
  AcquireSRWLockShared(&this->_lock.SRWLock_);
  p_pathWatcher = &this->_pathWatcher;
  if ( this->_cachedGuidList.ptr_ && p_pathWatcher->_Mypair._Myval2->_indexCurrentlyRegistered != 0xFFFF )
  {
    m_ptr = p_pathWatcher->_Mypair._Myval2->_watchedKey._changedEvent.m_ptr;
    if ( !m_ptr )
      wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0x92u, "onecore\\com\\combase\\inc\\RegistryWatcher.hpp");
    if ( WaitForSingleObject(m_ptr, 0) )
    {
      ptr = this->_cachedGuidList.ptr_;
      result->ptr_ = ptr;
      if ( ptr )
        _InterlockedIncrement((volatile signed __int32 *)ptr);
      if ( p_lock )
        ReleaseSRWLockShared(&p_lock->SRWLock_);
      return result;
    }
  }
  if ( p_lock )
    ReleaseSRWLockShared(&p_lock->SRWLock_);
  AcquireSRWLockExclusive(&p_lock->SRWLock_);
  lock.sync_ = &p_lock->SRWLock_;
  if ( !p_pathWatcher->_Mypair._Myval2 )
  {
    valueNameLength._hkey = 0;
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, &pszValueToSet, 0, 0x20119u, (PHKEY)&valueNameLength._hkey);
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v9 == -2147024894
      || (wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            0x10Eu,
            "onecore\\com\\combase\\inc\\RegistryKey.hpp",
            v9,
            "path:%ls",
            &pszValueToSet),
          v9 < 0) )
    {
      hkey = valueNameLength._hkey;
    }
    else
    {
      v13 = (RegistryPathWatcher *)HeapAlloc(g_hHeap, 0, 0x28u);
      if ( v13 )
        RegistryPathWatcher::RegistryPathWatcher(v13, &valueNameLength, this->_listRootPath);
      else
        v14 = 0;
      guids._Mypair._Myval2 = v14;
      std::unique_ptr<RegistryPathWatcher>::operator=<std::default_delete<RegistryPathWatcher>,0>(
        &this->_pathWatcher,
        (std::unique_ptr<RegistryPathWatcher> *)&guids);
      if ( guids._Mypair._Myval2 )
        std::default_delete<RegistryPathWatcher>::operator()(v15, (RegistryPathWatcher *)guids._Mypair._Myval2);
      hkey = valueNameLength._hkey;
      if ( p_pathWatcher->_Mypair._Myval2 )
      {
        if ( valueNameLength._hkey )
        {
          RegCloseKey(valueNameLength._hkey);
          valueNameLength._hkey = 0;
        }
        goto LABEL_28;
      }
    }
    result->ptr_ = 0;
    if ( hkey )
    {
      RegCloseKey(valueNameLength._hkey);
      valueNameLength._hkey = 0;
    }
    goto LABEL_44;
  }
LABEL_28:
  RegistryPathWatcher::RegisterNotification(p_pathWatcher->_Mypair._Myval2, 0, v7);
  listRootPath = this->_listRootPath;
  count = 0;
  guids._Mypair._Myval2 = 0;
  listRootKey._hkey = 0;
  Myval2 = 0;
  v18 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, listRootPath, 0, 0x20119u, (PHKEY)&listRootKey._hkey);
  v19 = v18;
  if ( v18 > 0 )
    v19 = (unsigned __int16)v18 | 0x80070000;
  if ( v19 != -2147024894 )
  {
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      0x10Eu,
      "onecore\\com\\combase\\inc\\RegistryKey.hpp",
      v19,
      "path:%ls",
      listRootPath);
    if ( v19 >= 0 )
    {
      v27 = RegQueryInfoKeyW(listRootKey._hkey, 0, 0, 0, 0, 0, 0, &count, 0, 0, 0, 0);
      v28 = v27 < 0;
      if ( v27 > 0 )
      {
        v27 = (unsigned __int16)v27 | 0x80070000;
        v28 = v27 < 0;
      }
      if ( !v28 )
      {
        v29 = 16LL * count;
        if ( !is_mul_ok(count, 0x10u) )
          v29 = -1;
        valueNameLength._hkey = (HKEY__ *volatile)HeapAlloc(g_hHeap, 0, v29);
        std::unique_ptr<unsigned __int64 [0]>::operator=<std::default_delete<unsigned __int64 [0]>,0>(
          (std::unique_ptr<unsigned char [0]> *)&guids,
          (std::unique_ptr<unsigned char [0]> *)&valueNameLength);
        Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<unsigned int>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0>>::View>::~MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<unsigned int>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0>>::View>((std::unique_ptr<wchar_t const * [0]> *)&valueNameLength);
        Myval2 = guids._Mypair._Myval2;
        v20 = 0;
        for ( i = 0; i < count; ++i )
        {
          memset_0(valueName, 0, 0x208u);
          LODWORD(valueNameLength._hkey) = 260;
          valueType = 0;
          if ( RegistryKey::EnumValue(
                 &listRootKey,
                 i,
                 valueName,
                 (unsigned int *)&valueNameLength,
                 &valueType,
                 lpcbMaxSubKeyLen,
                 lpcbMaxClassLen) < 0 )
          {
            result->ptr_ = 0;
            RegistryKey::Close(&listRootKey);
            Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<unsigned int>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0>>::View>::~MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<unsigned int>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0>>::View>((std::unique_ptr<wchar_t const * [0]> *)&guids);
            Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(&lock);
            return result;
          }
          guid = 0;
          v31 = -1;
          do
            ++v31;
          while ( valueName[v31] );
          if ( v31 >= 0x26 && wGUIDFromString(valueName, &guid) )
          {
            v32 = v20++;
            Myval2[v32] = guid;
          }
        }
        count = v20;
        goto LABEL_32;
      }
      wil::details::in1diag3::_Log_Hr(retaddr, 0x67Fu, "onecore\\com\\combase\\inc\\RegistryKey.hpp", v27);
    }
    v26 = listRootKey._hkey;
    result->ptr_ = 0;
    if ( v26 )
    {
      RegCloseKey(listRootKey._hkey);
      listRootKey._hkey = 0;
    }
    goto LABEL_44;
  }
  v20 = count;
LABEL_32:
  v21 = ArrayOfGuids::Create((ObjectLibrary::ReferencedPtr<ArrayOfGuids> *)&guids, v20, Myval2);
  v22 = 0;
  if ( &v42 != (char *)v21 )
  {
    v22 = v21->ptr_;
    v21->ptr_ = 0;
  }
  v23 = this->_cachedGuidList.ptr_;
  this->_cachedGuidList.ptr_ = v22;
  if ( v23 )
    ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<ArrayOfGuids,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<ArrayOfGuids,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<ArrayOfGuids,ObjectLibrary::Details::MixinBase<ArrayOfGuids,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>>>::Release(v23);
  v24 = guids._Mypair._Myval2;
  if ( guids._Mypair._Myval2 )
  {
    guids._Mypair._Myval2 = 0;
    ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<ArrayOfGuids,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<ArrayOfGuids,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<ArrayOfGuids,ObjectLibrary::Details::MixinBase<ArrayOfGuids,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>>>::Release((ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<ArrayOfGuids,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<ArrayOfGuids,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<ArrayOfGuids,ObjectLibrary::Details::MixinBase<ArrayOfGuids,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer> > > > *)v24);
  }
  v25 = this->_cachedGuidList.ptr_;
  result->ptr_ = v25;
  if ( v25 )
    _InterlockedIncrement((volatile signed __int32 *)v25);
  if ( listRootKey._hkey )
  {
    RegCloseKey(listRootKey._hkey);
    listRootKey._hkey = 0;
  }
  if ( Myval2 )
    HeapFree(g_hHeap, 0, Myval2);
LABEL_44:
  if ( p_lock )
    ReleaseSRWLockExclusive(&p_lock->SRWLock_);
  return result;
}

```

## disassembly

```asm
0x18005daf0  mov     [rsp-8+arg_10], rbx
0x18005daf5  push    rbp
0x18005daf6  push    rsi
0x18005daf7  push    rdi
0x18005daf8  push    r12
0x18005dafa  push    r13
0x18005dafc  push    r14
0x18005dafe  push    r15
0x18005db00  lea     rbp, [rsp-1D0h]
0x18005db08  sub     rsp, 2D0h
0x18005db0f  mov     rax, cs:__security_cookie
0x18005db16  xor     rax, rsp
0x18005db19  mov     [rbp+200h+var_40], rax
0x18005db20  lea     rbx, [this+8]
0x18005db24  mov     r14, this
0x18005db27  mov     this, rbx; SRWLock
0x18005db2a  mov     rsi, rdx
0x18005db2d  call    cs:__imp_AcquireSRWLockShared
0x18005db33  xor     r13d, r13d
0x18005db36  lea     rdi, [r14+10h]
0x18005db3a  cmp     [r14+18h], r13
0x18005db3e  jz      short loc_18005DB74
0x18005db40  mov     rax, [rdi]
0x18005db43  mov     ecx, 0FFFFh
0x18005db48  cmp     [rax+14h], cx
0x18005db4c  jz      short loc_18005DB74
0x18005db4e  mov     this, [rax+20h]; hHandle
0x18005db52  test    this, this
0x18005db55  jnz     loc_18005DC0C
0x18005db5b  mov     this, [rbp+208h]; callerReturnAddress
0x18005db62  lea     r8, aOnecoreComComb_29; "onecore\\com\\combase\\inc\\RegistryWat"...
0x18005db69  mov     edx, 92h; lineNumber
0x18005db6e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005db74  test    rbx, rbx
0x18005db77  jz      short loc_18005DB82
0x18005db79  mov     this, rbx; SRWLock
0x18005db7c  call    cs:__imp_ReleaseSRWLockShared
0x18005db82  mov     this, rbx; SRWLock
0x18005db85  call    cs:__imp_AcquireSRWLockExclusive
0x18005db8b  mov     [rbp+200h+lock.sync_], rbx
0x18005db8f  cmp     [rdi], r13
0x18005db92  jnz     loc_18005DCFF
0x18005db98  lea     rax, [rsp+300h+valueNameLength]
0x18005db9d  mov     [rsp+300h+valueNameLength], r13
0x18005dba2  lea     r12, pszValueToSet
0x18005dba9  mov     [rsp+300h+phkResult], rax; phkResult
0x18005dbae  mov     rdx, r12; lpSubKey
0x18005dbb1  mov     r9d, 20119h; samDesired
0x18005dbb7  xor     r8d, r8d; ulOptions
0x18005dbba  mov     this, 0FFFFFFFF80000002h; hKey
0x18005dbc1  call    cs:__imp_RegOpenKeyExW
0x18005dbc7  mov     r15d, eax
0x18005dbca  test    eax, eax
0x18005dbcc  jle     short loc_18005DBD9
0x18005dbce  movzx   r15d, ax
0x18005dbd2  or      r15d, 80070000h
0x18005dbd9  cmp     r15d, 80070002h
0x18005dbe0  jnz     loc_18005DC66
0x18005dbe6  mov     rax, [rsp+300h+valueNameLength]
0x18005dbeb  mov     [rsi], r13
0x18005dbee  test    rax, rax
0x18005dbf1  jz      loc_18005DDE0
0x18005dbf7  mov     this, [rsp+300h+valueNameLength]; hKey
0x18005dbfc  call    cs:__imp_RegCloseKey
0x18005dc02  mov     [rsp+300h+valueNameLength], r13
0x18005dc07  jmp     loc_18005DDE0
0x18005dc0c  xor     edx, edx; dwMilliseconds
0x18005dc0e  call    cs:__imp_WaitForSingleObject
0x18005dc14  test    eax, eax
0x18005dc16  jz      loc_18005DB74
0x18005dc1c  mov     rax, [r14+18h]
0x18005dc20  mov     [rsi], rax
0x18005dc23  test    rax, rax
0x18005dc26  jz      short loc_18005DC2B
0x18005dc28  lock inc dword ptr [rax]
0x18005dc2b  test    rbx, rbx
0x18005dc2e  jz      short loc_18005DC39
0x18005dc30  mov     this, rbx; SRWLock
0x18005dc33  call    cs:__imp_ReleaseSRWLockShared
0x18005dc39  mov     rax, rsi
0x18005dc3c  mov     this, [rbp+200h+var_40]
0x18005dc43  xor     this, rsp; StackCookie
0x18005dc46  call    __security_check_cookie
0x18005dc4b  mov     rbx, [rsp+300h+arg_10]
0x18005dc53  add     rsp, 2D0h
0x18005dc5a  pop     r15
0x18005dc5c  pop     r14
0x18005dc5e  pop     r13
0x18005dc60  pop     r12
0x18005dc62  pop     rdi
0x18005dc63  pop     rsi
0x18005dc64  pop     rbp
0x18005dc65  retn
0x18005dc66  mov     this, [rbp+208h]; callerReturnAddress
0x18005dc6d  lea     rax, aPathLs; "path:%ls"
0x18005dc74  mov     [rsp+300h+lpcbMaxSubKeyLen], r12
0x18005dc79  lea     r8, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18005dc80  mov     r9d, r15d; hr
0x18005dc83  mov     [rsp+300h+phkResult], rax; formatString
0x18005dc88  mov     edx, 10Eh; lineNumber
0x18005dc8d  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005dc92  test    r15d, r15d
0x18005dc95  js      loc_18005DBE6
0x18005dc9b  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18005dca2  xor     edx, edx; dwFlags
0x18005dca4  lea     r8d, [rdx+28h]; dwBytes
0x18005dca8  call    cs:__imp_HeapAlloc
0x18005dcae  test    rax, rax
0x18005dcb1  jz      loc_18005DF38
0x18005dcb7  mov     r8, [r14]; path
0x18005dcba  lea     rdx, [rsp+300h+valueNameLength]; ancestor
0x18005dcbf  mov     this, rax; this
0x18005dcc2  call    ??0RegistryPathWatcher@@QEAA@$$QEAVRegistryKey@@PEBG@Z; RegistryPathWatcher::RegistryPathWatcher(RegistryKey &&,ushort const *)
0x18005dcc7  lea     rdx, [rsp+300h+guids]; _Right
0x18005dccc  mov     [rsp+300h+guids._Mypair._Myval2], rax
0x18005dcd1  mov     this, rdi; this
0x18005dcd4  call    ??$?4U?$default_delete@VRegistryPathWatcher@@@std@@$0A@@?$unique_ptr@VRegistryPathWatcher@@U?$default_delete@VRegistryPathWatcher@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<RegistryPathWatcher>::operator=<std::default_delete<RegistryPathWatcher>,0>(std::unique_ptr<RegistryPathWatcher> &&)
0x18005dcd9  mov     rdx, [rsp+300h+guids._Mypair._Myval2]; _Ptr
0x18005dcde  test    rdx, rdx
0x18005dce1  jz      short loc_18005DCE8
0x18005dce3  call    ??R?$default_delete@VRegistryPathWatcher@@@std@@QEBAXPEAVRegistryPathWatcher@@@Z; std::default_delete<RegistryPathWatcher>::operator()(RegistryPathWatcher *)
0x18005dce8  mov     rax, [rsp+300h+valueNameLength]
0x18005dced  cmp     [rdi], r13
0x18005dcf0  jz      loc_18005DBEB
0x18005dcf6  test    rax, rax
0x18005dcf9  jnz     loc_18005DE5C
0x18005dcff  mov     this, [rdi]; this
0x18005dd02  xor     edx, edx; bWatchSubtree
0x18005dd04  call    ?RegisterNotification@RegistryPathWatcher@@QEAAJHK@Z; RegistryPathWatcher::RegisterNotification(int,ulong)
0x18005dd09  mov     r12, [r14]
0x18005dd0c  lea     rax, [rsp+300h+listRootKey]
0x18005dd11  mov     [rsp+300h+count], r13d
0x18005dd16  mov     rdx, r12; lpSubKey
0x18005dd19  mov     [rsp+300h+guids._Mypair._Myval2], r13
0x18005dd1e  mov     r9d, 20119h; samDesired
0x18005dd24  xor     r8d, r8d; ulOptions
0x18005dd27  mov     [rsp+300h+phkResult], rax; phkResult
0x18005dd2c  mov     this, 0FFFFFFFF80000002h; hKey
0x18005dd33  mov     [rsp+300h+listRootKey._hkey], r13
0x18005dd38  mov     rdi, r13
0x18005dd3b  call    cs:__imp_RegOpenKeyExW
0x18005dd41  mov     r15d, eax
0x18005dd44  test    eax, eax
0x18005dd46  jle     short loc_18005DD53
0x18005dd48  movzx   r15d, ax
0x18005dd4c  or      r15d, 80070000h
0x18005dd53  cmp     r15d, 80070002h
0x18005dd5a  jnz     loc_18005DDF7
0x18005dd60  mov     r15d, [rsp+300h+count]
0x18005dd65  mov     edx, r15d; count
0x18005dd68  lea     this, [rsp+300h+guids]; result
0x18005dd6d  mov     r8, rdi; guids
0x18005dd70  call    ?Create@ArrayOfGuids@@SA?AV?$ReferencedPtr@VArrayOfGuids@@@ObjectLibrary@@_KPEBU_GUID@@@Z; ArrayOfGuids::Create(unsigned __int64,_GUID const *)
0x18005dd75  lea     rdx, [rbp+200h+var_260]
0x18005dd79  mov     this, r13
0x18005dd7c  cmp     rdx, rax
0x18005dd7f  jz      short loc_18005DD87
0x18005dd81  mov     this, [rax]
0x18005dd84  mov     [rax], r13
0x18005dd87  mov     rax, [r14+18h]
0x18005dd8b  mov     [r14+18h], this
0x18005dd8f  test    rax, rax
0x18005dd92  jz      short loc_18005DD9C
0x18005dd94  mov     this, rax; this
0x18005dd97  call    ?Release@?$AddComReferenceCounting_StandardReferenceCountingLayer@VArrayOfGuids@@V?$AddComReferenceCounting_ReferenceCountLayer@VArrayOfGuids@@V?$Allocation_SealedClassDeleteSelfLayer@VArrayOfGuids@@V?$MixinBase@VArrayOfGuids@@VMixins_NilBaseForwarderLayer@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@QEAAKXZ; ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<ArrayOfGuids,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<ArrayOfGuids,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<ArrayOfGuids,ObjectLibrary::Details::MixinBase<ArrayOfGuids,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>>>::Release(void)
0x18005dd9c  mov     this, [rsp+300h+guids._Mypair._Myval2]; this
0x18005dda1  test    this, this
0x18005dda4  jz      short loc_18005DDB0
0x18005dda6  mov     [rsp+300h+guids._Mypair._Myval2], r13
0x18005ddab  call    ?Release@?$AddComReferenceCounting_StandardReferenceCountingLayer@VArrayOfGuids@@V?$AddComReferenceCounting_ReferenceCountLayer@VArrayOfGuids@@V?$Allocation_SealedClassDeleteSelfLayer@VArrayOfGuids@@V?$MixinBase@VArrayOfGuids@@VMixins_NilBaseForwarderLayer@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@QEAAKXZ; ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<ArrayOfGuids,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<ArrayOfGuids,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<ArrayOfGuids,ObjectLibrary::Details::MixinBase<ArrayOfGuids,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>>>::Release(void)
0x18005ddb0  mov     rax, [r14+18h]
0x18005ddb4  mov     [rsi], rax
0x18005ddb7  test    rax, rax
0x18005ddba  jz      short loc_18005DDBF
0x18005ddbc  lock inc dword ptr [rax]
0x18005ddbf  mov     rax, [rsp+300h+listRootKey._hkey]
0x18005ddc4  test    rax, rax
0x18005ddc7  jnz     short loc_18005DE47
0x18005ddc9  test    rdi, rdi
0x18005ddcc  jz      short loc_18005DDE0
0x18005ddce  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18005ddd5  mov     r8, rdi; lpMem
0x18005ddd8  xor     edx, edx; dwFlags
0x18005ddda  call    cs:__imp_HeapFree
0x18005dde0  test    rbx, rbx
0x18005dde3  jz      loc_18005DC39
0x18005dde9  mov     this, rbx; SRWLock
0x18005ddec  call    cs:__imp_ReleaseSRWLockExclusive
0x18005ddf2  jmp     loc_18005DC39
0x18005ddf7  mov     this, [rbp+208h]; callerReturnAddress
0x18005ddfe  lea     rax, aPathLs; "path:%ls"
0x18005de05  mov     [rsp+300h+lpcbMaxSubKeyLen], r12
0x18005de0a  lea     r8, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18005de11  mov     r9d, r15d; hr
0x18005de14  mov     [rsp+300h+phkResult], rax; formatString
0x18005de19  mov     edx, 10Eh; lineNumber
0x18005de1e  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005de23  test    r15d, r15d
0x18005de26  jns     short loc_18005DE71
0x18005de28  mov     rax, [rsp+300h+listRootKey._hkey]
0x18005de2d  mov     [rsi], r13
0x18005de30  test    rax, rax
0x18005de33  jz      short loc_18005DDE0
0x18005de35  mov     this, [rsp+300h+listRootKey._hkey]; hKey
0x18005de3a  call    cs:__imp_RegCloseKey
0x18005de40  mov     [rsp+300h+listRootKey._hkey], r13
0x18005de45  jmp     short loc_18005DDE0
0x18005de47  mov     this, [rsp+300h+listRootKey._hkey]; hKey
0x18005de4c  call    cs:__imp_RegCloseKey
0x18005de52  mov     [rsp+300h+listRootKey._hkey], r13
0x18005de57  jmp     loc_18005DDC9
0x18005de5c  mov     this, [rsp+300h+valueNameLength]; hKey
0x18005de61  call    cs:__imp_RegCloseKey
0x18005de67  mov     [rsp+300h+valueNameLength], r13
0x18005de6c  jmp     loc_18005DCFF
0x18005de71  mov     this, [rsp+300h+listRootKey._hkey]; hKey
0x18005de76  lea     rax, [rsp+300h+count]
0x18005de7b  mov     [rsp+300h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18005de80  xor     r9d, r9d; lpReserved
0x18005de83  mov     [rsp+300h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18005de88  xor     r8d, r8d; lpcchClass
0x18005de8b  mov     [rsp+300h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18005de90  xor     edx, edx; lpClass
0x18005de92  mov     [rsp+300h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18005de97  mov     [rsp+300h+lpcValues], rax; lpcValues
0x18005de9c  mov     [rsp+300h+lpcbMaxClassLen], r13; pszValueName
0x18005dea1  mov     [rsp+300h+lpcbMaxSubKeyLen], r13; dwIndex
0x18005dea6  mov     [rsp+300h+phkResult], r13; lpcSubKeys
0x18005deab  call    cs:__imp_RegQueryInfoKeyW
0x18005deb1  test    eax, eax
0x18005deb3  jle     short loc_18005DEBF
0x18005deb5  movzx   eax, ax
0x18005deb8  or      eax, 80070000h
0x18005debd  test    eax, eax
0x18005debf  jns     short loc_18005DEE1
0x18005dec1  mov     this, [rbp+208h]; callerReturnAddress
0x18005dec8  lea     r8, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18005decf  mov     r9d, eax; hr
0x18005ded2  mov     edx, 67Fh; lineNumber
0x18005ded7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005dedc  jmp     loc_18005DE28
0x18005dee1  mov     ecx, [rsp+300h+count]
0x18005dee5  mov     eax, 10h
0x18005deea  mul     this
0x18005deed  mov     this, 0FFFFFFFFFFFFFFFFh
0x18005def4  cmovb   rax, this
0x18005def8  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18005deff  mov     r8, rax; dwBytes
0x18005df02  xor     edx, edx; dwFlags
0x18005df04  call    cs:__imp_HeapAlloc
0x18005df0a  lea     rdx, [rsp+300h+valueNameLength]; _Right
0x18005df0f  mov     [rsp+300h+valueNameLength], rax
0x18005df14  lea     this, [rsp+300h+guids]; this
0x18005df19  call    ??$?4U?$default_delete@$$BY0A@_K@std@@$0A@@?$unique_ptr@$$BY0A@_KU?$default_delete@$$BY0A@_K@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<unsigned __int64 [0]>::operator=<std::default_delete<unsigned __int64 [0]>,0>(std::unique_ptr<unsigned __int64 [0]> &&)
0x18005df1e  lea     this, [rsp+300h+valueNameLength]; this
0x18005df23  call    ??1?$MakeAllocator@VView@?$HashMap@IPEAUHSTRING__@@U?$DefaultHash@I@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@I@3456@U?$DefaultLifetimeTraits@I@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$HashMapOptions@IPEAUHSTRING__@@U?$DefaultLifetimeTraits@I@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<uint,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<uint>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<uint,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,0,1,0>>::View>::~MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<uint,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<uint>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<uint,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,0,1,0>>::View>(void)
0x18005df28  mov     rdi, [rsp+300h+guids._Mypair._Myval2]
0x18005df2d  mov     r15d, r13d
0x18005df30  mov     r12d, r13d
0x18005df33  jmp     loc_180247798
0x18005df38  mov     rax, r13
0x18005df3b  jmp     loc_18005DCC7
0x180247798  cmp     r12d, [rsp+300h+count]
0x18024779d  jnb     loc_180247853
0x1802477a3  xor     edx, edx; Val
0x1802477a5  lea     rcx, [rbp+200h+valueName]; void *
0x1802477a9  mov     r8d, 208h; Size
0x1802477af  call    memset_0
0x1802477b4  lea     rax, [rbp+200h+valueType]
0x1802477b8  mov     dword ptr [rsp+300h+valueNameLength], 104h
0x1802477c0  lea     r9, [rsp+300h+valueNameLength]; pcchValueName
0x1802477c5  mov     [rsp+300h+phkResult], rax; pdwType
0x1802477ca  lea     r8, [rbp+200h+valueName]; pszValueName
0x1802477ce  mov     [rbp+200h+valueType], r13d
0x1802477d2  mov     edx, r12d; dwIndex
0x1802477d5  lea     rcx, [rsp+300h+listRootKey]; this
0x1802477da  call    ?EnumValue@RegistryKey@@QEBAJKPEAGPEAK1PEAX1@Z; RegistryKey::EnumValue(ulong,ushort *,ulong *,ulong *,void *,ulong *)
0x1802477df  test    eax, eax
0x1802477e1  js      short loc_18024782D
0x1802477e3  xorps   xmm0, xmm0
0x1802477e6  lea     rcx, [rbp+200h+valueName]
0x1802477ea  movups  xmmword ptr [rbp+200h+guid.Data1], xmm0
0x1802477ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802477f2  inc     rax
0x1802477f5  cmp     [rcx+rax*2], r13w
0x1802477fa  jnz     short loc_1802477F2
0x1802477fc  cmp     rax, 26h ; '&'
0x180247800  jb      short loc_180247825
0x180247802  lea     rdx, [rbp+200h+guid]; pguid
0x180247806  lea     rcx, [rbp+200h+valueName]; lpsz
0x18024780a  call    ?wGUIDFromString@@YAHPEBGPEAU_GUID@@@Z; wGUIDFromString(ushort const *,_GUID *)
0x18024780f  test    eax, eax
0x180247811  jz      short loc_180247825
0x180247813  movups  xmm0, xmmword ptr [rbp+200h+guid.Data1]
0x180247817  mov     eax, r15d
0x18024781a  add     rax, rax
0x18024781d  inc     r15d
0x180247820  movdqu  xmmword ptr [rdi+rax*8], xmm0
0x180247825  inc     r12d
0x180247828  jmp     loc_180247798
  ... truncated ...
```
