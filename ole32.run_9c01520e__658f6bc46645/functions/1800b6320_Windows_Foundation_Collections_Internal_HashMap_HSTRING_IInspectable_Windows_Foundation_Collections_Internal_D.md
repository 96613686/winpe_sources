# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(HSTRING__ *)

- ea: `0x1800b6320`
- end: `0x1800b64d3`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `435`
- prototype: `HRESULT __fastcall(Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > > *this, HSTRING__ *key)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18004508c`
- `0x1800b1a60`
- `0x1800b2858`
- `0x1800b30cc`
- `0x1800b35cc`
- `0x1800b4b1c`
- `0x1800b5d94`
- `0x1800b6320`
- `0x1800b720c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b6472`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b6472`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b63eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b648a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b63eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b648a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800b63bb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800b63bb`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(
        Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > > *this,
        HSTRING__ *key)
{
  int v3; // edi
  HSTRING m_key; // rbx
  int v5; // eax
  XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode *v6; // rsi
  IInspectable *m_value; // rdi
  unsigned int v8; // edx
  __int64 v9; // r8
  XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode **m_ppBins; // rdx
  XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode *v11; // rax
  XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode *i; // rcx
  XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode *m_pNext; // rcx
  _RTL_SRWLOCK *v14; // rcx
  XWinRT::detail::LockHolder<XWinRT::ComLock,XWinRT::detail::AcquireWrite> acquired; // [rsp+30h] [rbp-10h] BYREF
  HSTRING__ *v17; // [rsp+78h] [rbp+38h] BYREF
  XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CPair *pPair; // [rsp+80h] [rbp+40h] BYREF
  XWinRT::AutoValue<IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *> > sOldValue; // [rsp+88h] [rbp+48h] BYREF

  v17 = key;
  v3 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(this);
  if ( v3 >= 0 )
  {
    m_key = 0;
    sOldValue._value = 0;
    LODWORD(pPair) = 0;
    XWinRT::SerializingLockPolicy::Write(&acquired, &this->_comLock, (HRESULT *)&pPair);
    v3 = (int)pPair;
    if ( (int)pPair >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(
        (XWinRT::detail::ReentrancyGuard<0> *)&pPair,
        *(_BYTE *)&this->_listeners,
        &this->_reentrancyGuard);
      pPair = 0;
      v5 = XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(
             &this->_hashMap,
             &v17,
             &pPair);
      v6 = (XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode *)pPair;
      v3 = v5;
      if ( v5 >= 0 )
      {
        if ( pPair )
        {
          v3 = XWinRT::SecureVersionTag::TagManager::ChangeVersion(&this->_versionManager);
          if ( v3 >= 0 )
          {
            m_key = v6->m_key;
            WindowsDeleteString(0);
            m_value = v6->m_value;
            CStmBufRead::Release(&sOldValue._value);
            v8 = v6->m_nHash % this->_hashMap.m_nBins;
            sOldValue._value = m_value;
            v9 = v8;
            m_ppBins = this->_hashMap.m_ppBins;
            v11 = m_ppBins[v9];
            if ( v6 == v11 )
            {
              v11 = 0;
            }
            else
            {
              for ( i = v11->m_pNext; i != v6; i = i->m_pNext )
                v11 = i;
            }
            m_pNext = v6->m_pNext;
            if ( v11 )
              v11->m_pNext = m_pNext;
            else
              m_ppBins[v9] = m_pNext;
            XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::FreeNode(
              &this->_hashMap,
              v6);
            v3 = 0;
          }
        }
        else
        {
          v3 = -2147483637;
          RoOriginateError(2147483659LL, 0);
        }
      }
    }
    if ( acquired._pLock )
    {
      v14 = (_RTL_SRWLOCK *)&acquired._pLock->8;
      if ( acquired._pLock->kind == Kind_StaReentrancy )
        *(_DWORD *)&v14->0 += 0x10000000;
      else
        ReleaseSRWLockExclusive(v14);
    }
    CStmBufRead::Release(&sOldValue._value);
    WindowsDeleteString(m_key);
  }
  if ( v3 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(
                           (unsigned __int8)pPair,
                           *(_BYTE *)&this->_evtMapChanged,
                           this,
                           2,
                           v17);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800b6320  mov     [rsp-28h+arg_0], rbx
0x1800b6325  mov     [rsp-28h+arg_8], key
0x1800b632a  push    rbp
0x1800b632b  push    rsi
0x1800b632c  push    rdi
0x1800b632d  push    r14
0x1800b632f  push    r15
0x1800b6331  mov     rbp, rsp
0x1800b6334  sub     rsp, 40h
0x1800b6338  mov     r14, this
0x1800b633b  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x1800b6340  mov     edi, eax
0x1800b6342  test    eax, eax
0x1800b6344  js      loc_1800B6496
0x1800b634a  xor     ebx, ebx
0x1800b634c  lea     key, [r14+80h]; lock
0x1800b6353  and     [rbp+sOldValue._value], rbx
0x1800b6357  lea     r8, [rbp+pPair]; phr
0x1800b635b  and     dword ptr [rbp+pPair], ebx
0x1800b635e  lea     this, [rbp+acquired]; result
0x1800b6362  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x1800b6367  mov     edi, dword ptr [rbp+pPair]
0x1800b636a  test    edi, edi
0x1800b636c  js      loc_1800B6458
0x1800b6372  movzx   edx, byte ptr [r14+9Ah]
0x1800b637a  lea     r8, [r14+9Ch]
0x1800b6381  lea     this, [rbp+pPair]; this
0x1800b6385  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x1800b638a  and     [rbp+pPair], rbx
0x1800b638e  lea     r8, [rbp+pPair]; retval
0x1800b6392  lea     key, [rbp+arg_8]; key
0x1800b6396  lea     this, [r14+28h]; this
0x1800b639a  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::CPair * *)
0x1800b639f  mov     rsi, [rbp+pPair]
0x1800b63a3  mov     edi, eax
0x1800b63a5  test    eax, eax
0x1800b63a7  js      loc_1800B6458
0x1800b63ad  test    rsi, rsi
0x1800b63b0  jnz     short loc_1800B63CC
0x1800b63b2  mov     edi, 8000000Bh
0x1800b63b7  xor     edx, edx
0x1800b63b9  mov     ecx, edi
0x1800b63bb  call    cs:__imp_RoOriginateError
0x1800b63c2  nop     dword ptr [rax+rax+00h]
0x1800b63c7  jmp     loc_1800B6458
0x1800b63cc  test    eax, eax
0x1800b63ce  js      loc_1800B6458
0x1800b63d4  lea     this, [r14+90h]; this
0x1800b63db  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x1800b63e0  mov     edi, eax
0x1800b63e2  test    eax, eax
0x1800b63e4  js      short loc_1800B6458
0x1800b63e6  mov     rbx, [rsi]
0x1800b63e9  xor     ecx, ecx; string
0x1800b63eb  call    cs:__imp_WindowsDeleteString
0x1800b63f2  nop     dword ptr [rax+rax+00h]
0x1800b63f7  mov     rdi, [rsi+8]
0x1800b63fb  lea     this, [rbp+sOldValue]; initializedElement
0x1800b63ff  call    ?Release@CStmBufRead@@QEAAXXZ; CStmBufRead::Release(void)
0x1800b6404  mov     eax, [rsi+18h]
0x1800b6407  xor     edx, edx
0x1800b6409  div     dword ptr [r14+40h]
0x1800b640d  mov     [rbp+sOldValue._value], rdi
0x1800b6411  mov     r8d, edx
0x1800b6414  mov     key, [r14+30h]
0x1800b6418  mov     rax, [key+r8*8]
0x1800b641c  cmp     rsi, rax
0x1800b641f  jnz     short loc_1800B6425
0x1800b6421  xor     eax, eax
0x1800b6423  jmp     short loc_1800B6437
0x1800b6425  mov     this, [rax+10h]
0x1800b6429  jmp     short loc_1800B6432
0x1800b642b  mov     rax, this
0x1800b642e  mov     this, [this+10h]
0x1800b6432  cmp     this, rsi
0x1800b6435  jnz     short loc_1800B642B
0x1800b6437  mov     this, [rsi+10h]
0x1800b643b  test    rax, rax
0x1800b643e  jnz     short loc_1800B6446
0x1800b6440  mov     [key+r8*8], this
0x1800b6444  jmp     short loc_1800B644A
0x1800b6446  mov     [rax+10h], this
0x1800b644a  mov     key, rsi; pNode
0x1800b644d  lea     this, [r14+28h]; this
0x1800b6451  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::CNode *)
0x1800b6456  xor     edi, edi
0x1800b6458  mov     rax, [rbp+acquired._pLock]
0x1800b645c  test    rax, rax
0x1800b645f  jz      short loc_1800B647E
0x1800b6461  cmp     dword ptr [rax], 1
0x1800b6464  lea     this, [rax+8]; SRWLock
0x1800b6468  jnz     short loc_1800B6472
0x1800b646a  add     dword ptr [this], 10000000h
0x1800b6470  jmp     short loc_1800B647E
0x1800b6472  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b6479  nop     dword ptr [rax+rax+00h]
0x1800b647e  lea     this, [rbp+sOldValue]; initializedElement
0x1800b6482  call    ?Release@CStmBufRead@@QEAAXXZ; CStmBufRead::Release(void)
0x1800b6487  mov     this, rbx; string
0x1800b648a  call    cs:__imp_WindowsDeleteString
0x1800b6491  nop     dword ptr [rax+rax+00h]
0x1800b6496  test    edi, edi
0x1800b6498  js      short loc_1800B64BF
0x1800b649a  mov     rax, [rbp+arg_8]
0x1800b649e  mov     r9d, 2
0x1800b64a4  movzx   edx, byte ptr [r14+99h]
0x1800b64ac  mov     r8, r14
0x1800b64af  movzx   ecx, byte ptr [rbp+pPair]
0x1800b64b3  mov     [rsp+40h+var_20], rax
0x1800b64b8  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(...)
0x1800b64bd  mov     edi, eax
0x1800b64bf  mov     rbx, [rsp+40h+arg_0]
0x1800b64c4  mov     eax, edi
0x1800b64c6  add     rsp, 40h
0x1800b64ca  pop     r15
0x1800b64cc  pop     r14
0x1800b64ce  pop     rdi
0x1800b64cf  pop     rsi
0x1800b64d0  pop     rbp
0x1800b64d1  retn
```
