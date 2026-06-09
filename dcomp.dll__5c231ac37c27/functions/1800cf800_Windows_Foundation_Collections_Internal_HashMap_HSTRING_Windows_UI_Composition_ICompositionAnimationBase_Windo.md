# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(HSTRING__ *)

- ea: `0x1800cf800`
- end: `0x1800cf96e`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@5@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUICompositionAnimationBase@Composition@UI@Windows@@@7895@U?$HashMapOptions@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$0A@$00$0A@@7895@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800cf760`

## callees

- `0x180074fa4`
- `0x180075074`
- `0x180075090`
- `0x1800750e4`
- `0x1800751d0`
- `0x1800bb3a0`
- `0x1800cf800`
- `0x18013d240`
- `0x18013d284`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cf8fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cf8fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf8bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf928`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf8bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf928`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800cf89c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800cf89c`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(
        unsigned __int8 *a1,
        __int64 a2)
{
  int v3; // edi
  HSTRING v4; // rbx
  void *v5; // rsi
  char v6; // r12
  __int64 v7; // r15
  RTL_SRWLOCK *v8; // rcx
  __int64 v10; // [rsp+78h] [rbp+48h] BYREF
  __int64 v11; // [rsp+80h] [rbp+50h] BYREF
  RTL_SRWLOCK *v12; // [rsp+88h] [rbp+58h] BYREF

  v10 = a2;
  v3 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized();
  if ( v3 >= 0 )
  {
    v4 = 0;
    LODWORD(v11) = 0;
    v5 = 0;
    v6 = 0;
    XWinRT::SerializingLockPolicy::Write(&v12, a1 + 160, &v11);
    v3 = v11;
    if ( (int)v11 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v11, a1[186], a1 + 188);
      v11 = 0;
      v3 = XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>>>::Lookup(
             a1 + 72,
             &v10,
             &v11);
      if ( v3 >= 0 )
      {
        v7 = v11;
        if ( v11 )
        {
          v3 = XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 176));
          if ( v3 >= 0 )
          {
            v4 = *(HSTRING *)v7;
            WindowsDeleteString(0);
            v5 = *(void **)(v7 + 8);
            v6 = *(_BYTE *)(v7 + 16);
            v3 = XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>>>::RemoveAtPos(
                   a1 + 72,
                   v7);
            if ( v3 < 0 )
            {
              v4 = 0;
              v5 = 0;
              v6 = 0;
            }
          }
        }
        else
        {
          v3 = -2147483637;
          RoOriginateError(2147483659LL);
        }
      }
    }
    if ( v12 )
    {
      v8 = v12 + 1;
      if ( LODWORD(v12->Ptr) == 1 )
        LODWORD(v8->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v8);
    }
    if ( v6 )
    {
      XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>::ReferencedGitCookie::Release(v5);
    }
    else if ( v5 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
    }
    WindowsDeleteString(v4);
  }
  if ( v3 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
                           (unsigned __int8)v11,
                           a1[185],
                           a1,
                           2,
                           v10);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800cf800  mov     [rsp-38h+arg_0], rbx
0x1800cf805  mov     [rsp-38h+arg_8], rdx
0x1800cf80a  push    rbp
0x1800cf80b  push    rsi
0x1800cf80c  push    rdi
0x1800cf80d  push    r12
0x1800cf80f  push    r13
0x1800cf811  push    r14
0x1800cf813  push    r15
0x1800cf815  mov     rbp, rsp
0x1800cf818  sub     rsp, 30h
0x1800cf81c  mov     r14, rcx
0x1800cf81f  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@5@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUICompositionAnimationBase@Composition@UI@Windows@@@7895@U?$HashMapOptions@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$0A@$00$0A@@7895@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized(void)
0x1800cf824  mov     edi, eax
0x1800cf826  test    eax, eax
0x1800cf828  js      loc_1800CF92E
0x1800cf82e  xor     ebx, ebx
0x1800cf830  lea     rdx, [r14+0A0h]
0x1800cf837  lea     r8, [rbp+arg_10]
0x1800cf83b  mov     dword ptr [rbp+arg_10], ebx
0x1800cf83e  lea     rcx, [rbp+arg_18]
0x1800cf842  xor     esi, esi
0x1800cf844  xor     r12b, r12b
0x1800cf847  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x1800cf84c  mov     edi, dword ptr [rbp+arg_10]
0x1800cf84f  test    edi, edi
0x1800cf851  js      loc_1800CF8E2
0x1800cf857  movzx   edx, byte ptr [r14+0BAh]
0x1800cf85f  lea     r8, [r14+0BCh]
0x1800cf866  lea     rcx, [rbp+arg_10]
0x1800cf86a  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x1800cf86f  lea     r8, [rbp+arg_10]
0x1800cf873  mov     [rbp+arg_10], rbx
0x1800cf877  lea     rdx, [rbp+arg_8]
0x1800cf87b  lea     rcx, [r14+48h]
0x1800cf87f  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UICompositionAnimationBase@Composition@UI@Windows@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@5@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUICompositionAnimationBase@Composition@UI@Windows@@@7895@U?$HashMapOptions@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$0A@$00$0A@@7895@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UICompositionAnimationBase@Composition@UI@Windows@@@detail@XWinRT@@@4@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>>>::CPair * *)
0x1800cf884  mov     edi, eax
0x1800cf886  test    eax, eax
0x1800cf888  js      short loc_1800CF8E2
0x1800cf88a  mov     r15, [rbp+arg_10]
0x1800cf88e  test    r15, r15
0x1800cf891  jnz     short loc_1800CF8A4
0x1800cf893  mov     edi, 8000000Bh
0x1800cf898  xor     edx, edx
0x1800cf89a  mov     ecx, edi
0x1800cf89c  call    cs:__imp_RoOriginateError
0x1800cf8a2  jmp     short loc_1800CF8E2
0x1800cf8a4  lea     rcx, [r14+0B0h]; this
0x1800cf8ab  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x1800cf8b0  mov     edi, eax
0x1800cf8b2  test    eax, eax
0x1800cf8b4  js      short loc_1800CF8E2
0x1800cf8b6  mov     rbx, [r15]
0x1800cf8b9  xor     ecx, ecx; string
0x1800cf8bb  call    cs:__imp_WindowsDeleteString
0x1800cf8c1  mov     rsi, [r15+8]
0x1800cf8c5  lea     rcx, [r14+48h]
0x1800cf8c9  mov     r12b, [r15+10h]
0x1800cf8cd  mov     rdx, r15
0x1800cf8d0  call    ?RemoveAtPos@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UICompositionAnimationBase@Composition@UI@Windows@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@5@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUICompositionAnimationBase@Composition@UI@Windows@@@7895@U?$HashMapOptions@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$0A@$00$0A@@7895@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UICompositionAnimationBase@Composition@UI@Windows@@@detail@XWinRT@@@4@@XWinRT@@QEAAJPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>>>::RemoveAtPos(XWinRT::TXPOSITION *)
0x1800cf8d5  mov     edi, eax
0x1800cf8d7  test    eax, eax
0x1800cf8d9  jns     short loc_1800CF8E2
0x1800cf8db  xor     ebx, ebx
0x1800cf8dd  xor     esi, esi
0x1800cf8df  xor     r12b, r12b
0x1800cf8e2  mov     rax, [rbp+arg_18]
0x1800cf8e6  test    rax, rax
0x1800cf8e9  jz      short loc_1800CF902
0x1800cf8eb  cmp     dword ptr [rax], 1
0x1800cf8ee  lea     rcx, [rax+8]; SRWLock
0x1800cf8f2  jnz     short loc_1800CF8FC
0x1800cf8f4  add     dword ptr [rcx], 10000000h
0x1800cf8fa  jmp     short loc_1800CF902
0x1800cf8fc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cf902  test    r12b, r12b
0x1800cf905  jz      short loc_1800CF911
0x1800cf907  mov     rcx, rsi; void *
0x1800cf90a  call    ?Release@ReferencedGitCookie@?$GitStorageType@UICompositionAnimationBase@Composition@UI@Windows@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>::ReferencedGitCookie::Release(void)
0x1800cf90f  jmp     short loc_1800CF925
0x1800cf911  test    rsi, rsi
0x1800cf914  jz      short loc_1800CF925
0x1800cf916  mov     rax, [rsi]
0x1800cf919  mov     rcx, rsi
0x1800cf91c  mov     rax, [rax+10h]
0x1800cf920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf925  mov     rcx, rbx; string
0x1800cf928  call    cs:__imp_WindowsDeleteString
0x1800cf92e  test    edi, edi
0x1800cf930  js      short loc_1800CF957
0x1800cf932  mov     rax, [rbp+arg_8]
0x1800cf936  mov     r9d, 2
0x1800cf93c  movzx   edx, byte ptr [r14+0B9h]
0x1800cf944  mov     r8, r14
0x1800cf947  movzx   ecx, byte ptr [rbp+arg_10]
0x1800cf94b  mov     [rsp+30h+var_10], rax
0x1800cf950  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x1800cf955  mov     edi, eax
0x1800cf957  mov     rbx, [rsp+30h+arg_0]
0x1800cf95c  mov     eax, edi
0x1800cf95e  add     rsp, 30h
0x1800cf962  pop     r15
0x1800cf964  pop     r14
0x1800cf966  pop     r13
0x1800cf968  pop     r12
0x1800cf96a  pop     rdi
0x1800cf96b  pop     rsi
0x1800cf96c  pop     rbp
0x1800cf96d  retn
```
