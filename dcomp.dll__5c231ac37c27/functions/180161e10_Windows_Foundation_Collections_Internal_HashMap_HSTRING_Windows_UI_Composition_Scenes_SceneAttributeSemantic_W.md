# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,uchar *)

- ea: `0x180161e10`
- end: `0x180161f88`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@5@PEAE@Z`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180162018`

## callees

- `0x180075074`
- `0x180075090`
- `0x1800751d0`
- `0x1800bb3a0`
- `0x180160e18`
- `0x180161e10`
- `0x18016229c`
- `0x180162f1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180161f30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180161f30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180161e4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180161e4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180161f67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180161f67`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(
        __int64 a1,
        HSTRING a2,
        int a3,
        _BYTE *a4)
{
  HRESULT v8; // ebx
  RTL_SRWLOCK *v9; // rcx
  int v11; // [rsp+30h] [rbp-20h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-18h] BYREF
  RTL_SRWLOCK *v13; // [rsp+40h] [rbp-10h] BYREF
  __int64 v14; // [rsp+98h] [rbp+48h] BYREF

  *a4 = 0;
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized();
  newString = 0;
  v8 = WindowsDuplicateString(a2, &newString);
  if ( v8 >= 0 )
  {
    v11 = a3;
    LODWORD(v14) = 0;
    XWinRT::SerializingLockPolicy::Write(&v13, a1 + 160, &v14);
    v8 = v14;
    if ( (int)v14 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v14, *(unsigned __int8 *)(a1 + 186), a1 + 188);
      XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 176));
      v14 = 0;
      v8 = XWinRT::XHashMap<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<enum Windows::UI::Composition::Scenes::SceneAttributeSemantic>>::Lookup(
             a1 + 72,
             &newString,
             &v14);
      if ( v8 >= 0 )
      {
        if ( v14 )
        {
          *(_DWORD *)(v14 + 8) = a3;
          *a4 = 1;
        }
        else if ( *(_QWORD *)(a1 + 88) == 0x7FFFFFFF )
        {
          v8 = -2147024882;
        }
        else
        {
          v14 = 0;
          v8 = XWinRT::XHashMap<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<enum Windows::UI::Composition::Scenes::SceneAttributeSemantic>>::SetAt(
                 a1 + 72,
                 &newString,
                 &v11,
                 &v14);
          if ( v8 >= 0 )
            newString = 0;
        }
      }
    }
    if ( v13 )
    {
      v9 = v13 + 1;
      if ( LODWORD(v13->Ptr) == 1 )
        LODWORD(v9->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v9);
    }
  }
  if ( v8 >= 0 )
    v8 = Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
           (unsigned __int8)v14,
           *(unsigned __int8 *)(a1 + 185),
           a1,
           *a4 != 0 ? 3 : 1,
           a2);
  WindowsDeleteString(newString);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180161e10  mov     [rsp-28h+arg_0], rbx
0x180161e15  mov     [rsp-28h+arg_8], rsi
0x180161e1a  push    rbp
0x180161e1b  push    rdi
0x180161e1c  push    r12
0x180161e1e  push    r14
0x180161e20  push    r15
0x180161e22  mov     rbp, rsp
0x180161e25  sub     rsp, 50h
0x180161e29  mov     r14, r9
0x180161e2c  mov     byte ptr [r9], 0
0x180161e30  mov     esi, r8d
0x180161e33  mov     r12, rdx
0x180161e36  mov     rdi, rcx
0x180161e39  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized(void)
0x180161e3e  lea     rdx, [rbp+newString]; newString
0x180161e42  mov     [rbp+newString], 0
0x180161e4a  mov     rcx, r12; string
0x180161e4d  call    cs:__imp_WindowsDuplicateString
0x180161e53  mov     ebx, eax
0x180161e55  test    eax, eax
0x180161e57  js      loc_180161F36
0x180161e5d  lea     rdx, [rdi+0A0h]
0x180161e64  mov     [rbp+var_20], esi
0x180161e67  lea     r8, [rbp+arg_18]
0x180161e6b  mov     dword ptr [rbp+arg_18], 0
0x180161e72  lea     rcx, [rbp+var_10]
0x180161e76  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180161e7b  mov     ebx, dword ptr [rbp+arg_18]
0x180161e7e  test    ebx, ebx
0x180161e80  js      loc_180161F16
0x180161e86  movzx   edx, byte ptr [rdi+0BAh]
0x180161e8d  lea     r8, [rdi+0BCh]
0x180161e94  lea     rcx, [rbp+arg_18]
0x180161e98  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180161e9d  lea     rcx, [rdi+0B0h]; this
0x180161ea4  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180161ea9  lea     r8, [rbp+arg_18]
0x180161ead  mov     [rbp+arg_18], 0
0x180161eb5  lea     rdx, [rbp+newString]
0x180161eb9  lea     rcx, [rdi+48h]
0x180161ebd  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@UKeyTraits@?$HashMap@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@6@V?$CElementTraits@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<Windows::UI::Composition::Scenes::SceneAttributeSemantic>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<Windows::UI::Composition::Scenes::SceneAttributeSemantic>>::CPair * *)
0x180161ec2  mov     ebx, eax
0x180161ec4  test    eax, eax
0x180161ec6  js      short loc_180161F16
0x180161ec8  mov     rax, [rbp+arg_18]
0x180161ecc  test    rax, rax
0x180161ecf  jz      short loc_180161EDA
0x180161ed1  mov     [rax+8], esi
0x180161ed4  mov     byte ptr [r14], 1
0x180161ed8  jmp     short loc_180161F16
0x180161eda  cmp     qword ptr [rdi+58h], 7FFFFFFFh
0x180161ee2  jnz     short loc_180161EEB
0x180161ee4  mov     ebx, 8007000Eh
0x180161ee9  jmp     short loc_180161F16
0x180161eeb  lea     r9, [rbp+arg_18]
0x180161eef  mov     [rbp+arg_18], 0
0x180161ef7  lea     r8, [rbp+var_20]
0x180161efb  lea     rdx, [rbp+newString]
0x180161eff  lea     rcx, [rdi+48h]
0x180161f03  call    ?SetAt@?$XHashMap@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@UKeyTraits@?$HashMap@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@6@V?$CElementTraits@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@AEBW4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@PEAPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<Windows::UI::Composition::Scenes::SceneAttributeSemantic>>::SetAt(HSTRING__ * const &,Windows::UI::Composition::Scenes::SceneAttributeSemantic const &,XWinRT::TXPOSITION * *)
0x180161f08  mov     ebx, eax
0x180161f0a  test    eax, eax
0x180161f0c  js      short loc_180161F16
0x180161f0e  mov     [rbp+newString], 0
0x180161f16  mov     rax, [rbp+var_10]
0x180161f1a  test    rax, rax
0x180161f1d  jz      short loc_180161F36
0x180161f1f  cmp     dword ptr [rax], 1
0x180161f22  lea     rcx, [rax+8]; SRWLock
0x180161f26  jnz     short loc_180161F30
0x180161f28  add     dword ptr [rcx], 10000000h
0x180161f2e  jmp     short loc_180161F36
0x180161f30  call    cs:__imp_ReleaseSRWLockExclusive
0x180161f36  test    ebx, ebx
0x180161f38  js      short loc_180161F63
0x180161f3a  mov     al, [r14]
0x180161f3d  mov     r8, rdi
0x180161f40  movzx   edx, byte ptr [rdi+0B9h]
0x180161f47  neg     al
0x180161f49  movzx   ecx, byte ptr [rbp+arg_18]
0x180161f4d  sbb     r9d, r9d
0x180161f50  mov     [rsp+50h+var_30], r12
0x180161f55  and     r9d, 2
0x180161f59  inc     r9d
0x180161f5c  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x180161f61  mov     ebx, eax
0x180161f63  mov     rcx, [rbp+newString]; string
0x180161f67  call    cs:__imp_WindowsDeleteString
0x180161f6d  lea     r11, [rsp+50h+var_s0]
0x180161f72  mov     eax, ebx
0x180161f74  mov     rbx, [r11+30h]
0x180161f78  mov     rsi, [r11+38h]
0x180161f7c  mov     rsp, r11
0x180161f7f  pop     r15
0x180161f81  pop     r14
0x180161f83  pop     r12
0x180161f85  pop     rdi
0x180161f86  pop     rbp
0x180161f87  retn
```
