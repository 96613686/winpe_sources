# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(HSTRING__ *,HSTRING__ *,uchar *)

- ea: `0x1800435d0`
- end: `0x180043782`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@0PEAE@Z`
- size: `434`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18002bfcc`
- `0x1800335b4`
- `0x180038144`
- `0x180038adc`
- `0x1800435d0`
- `0x180044100`
- `0x180045db0`
- `0x18004a000`
- `0x18004ac6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180043718`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180043718`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800436aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043721`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004372b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043762`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800436aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043721`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004372b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043762`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004360d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004360d`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(
        __int64 a1,
        HSTRING a2,
        __int64 a3,
        _BYTE *a4)
{
  int v7; // ebx
  HSTRING v8; // rdi
  __int64 v9; // r14
  RTL_SRWLOCK *v10; // rcx
  HSTRING string; // [rsp+30h] [rbp-20h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-18h] BYREF
  RTL_SRWLOCK *v14; // [rsp+40h] [rbp-10h] BYREF
  __int64 v15; // [rsp+A8h] [rbp+58h] BYREF

  *a4 = 0;
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized();
  newString = 0;
  LODWORD(v15) = WindowsDuplicateString(a2, &newString);
  v7 = v15;
  if ( (int)v15 >= 0 )
  {
    XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(&string);
    v7 = v15;
    v8 = 0;
    if ( (int)v15 >= 0 )
    {
      XWinRT::SerializingLockPolicy::Write(&v14, a1 + 128, &v15);
      v7 = v15;
      if ( (int)v15 >= 0 )
      {
        XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v15, *(unsigned __int8 *)(a1 + 154), a1 + 156);
        XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 144));
        v15 = 0;
        v7 = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Lookup(
               a1 + 40,
               &newString,
               &v15);
        if ( v7 >= 0 )
        {
          v9 = v15;
          if ( v15 )
          {
            v8 = *(HSTRING *)(v15 + 8);
            WindowsDeleteString(0);
            *(_QWORD *)(v9 + 8) = string;
            string = 0;
            *a4 = 1;
          }
          else if ( *(_QWORD *)(a1 + 56) == 0x7FFFFFFF )
          {
            v7 = -2147024882;
          }
          else
          {
            v15 = 0;
            v7 = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::SetAt(
                   a1 + 40,
                   &newString,
                   &string,
                   &v15);
            if ( v7 >= 0 )
            {
              newString = 0;
              string = 0;
            }
          }
        }
      }
      if ( v14 )
      {
        v10 = v14 + 1;
        if ( LODWORD(v14->Ptr) == 1 )
          LODWORD(v10->Ptr) += 0x10000000;
        else
          ReleaseSRWLockExclusive(v10);
      }
    }
    WindowsDeleteString(v8);
    WindowsDeleteString(string);
  }
  if ( v7 >= 0 )
    v7 = Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(
           (unsigned __int8)v15,
           *(unsigned __int8 *)(a1 + 153),
           a1,
           *a4 != 0 ? 3 : 1,
           a2);
  WindowsDeleteString(newString);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800435d0  mov     [rsp-38h+arg_0], rbx
0x1800435d5  mov     [rsp-38h+arg_10], r8
0x1800435da  push    rbp
0x1800435db  push    rsi
0x1800435dc  push    rdi
0x1800435dd  push    r12
0x1800435df  push    r13
0x1800435e1  push    r14
0x1800435e3  push    r15
0x1800435e5  mov     rbp, rsp
0x1800435e8  sub     rsp, 50h
0x1800435ec  mov     r15, r9
0x1800435ef  mov     byte ptr [r9], 0
0x1800435f3  mov     r13, rdx
0x1800435f6  mov     rsi, rcx
0x1800435f9  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x1800435fe  lea     rdx, [rbp+newString]; newString
0x180043602  mov     [rbp+newString], 0
0x18004360a  mov     rcx, r13; string
0x18004360d  call    cs:__imp_WindowsDuplicateString
0x180043613  mov     dword ptr [rbp+arg_18], eax
0x180043616  mov     ebx, eax
0x180043618  test    eax, eax
0x18004361a  js      loc_180043731
0x180043620  lea     r8, [rbp+arg_18]
0x180043624  lea     rdx, [rbp+arg_10]
0x180043628  lea     rcx, [rbp+string]; newString
0x18004362c  call    ??$?0PEAUHSTRING__@@@?$AutoValue@PEAUHSTRING__@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUHSTRING__@@PEAJ@Z; XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(HSTRING__ * const &,long *)
0x180043631  mov     ebx, dword ptr [rbp+arg_18]
0x180043634  xor     edi, edi
0x180043636  test    ebx, ebx
0x180043638  js      loc_18004371E
0x18004363e  lea     rdx, [rsi+80h]
0x180043645  lea     r8, [rbp+arg_18]
0x180043649  lea     rcx, [rbp+var_10]
0x18004364d  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180043652  mov     ebx, dword ptr [rbp+arg_18]
0x180043655  test    ebx, ebx
0x180043657  js      loc_1800436FE
0x18004365d  movzx   edx, byte ptr [rsi+9Ah]
0x180043664  lea     r8, [rsi+9Ch]
0x18004366b  lea     rcx, [rbp+arg_18]
0x18004366f  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180043674  lea     rcx, [rsi+90h]; this
0x18004367b  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180043680  lea     r8, [rbp+arg_18]
0x180043684  mov     [rbp+arg_18], rdi
0x180043688  lea     rdx, [rbp+newString]
0x18004368c  lea     rcx, [rsi+28h]
0x180043690  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::CPair * *)
0x180043695  mov     ebx, eax
0x180043697  test    eax, eax
0x180043699  js      short loc_1800436FE
0x18004369b  mov     r14, [rbp+arg_18]
0x18004369f  test    r14, r14
0x1800436a2  jz      short loc_1800436C6
0x1800436a4  mov     rdi, [r14+8]
0x1800436a8  xor     ecx, ecx; string
0x1800436aa  call    cs:__imp_WindowsDeleteString
0x1800436b0  mov     rax, [rbp+string]
0x1800436b4  mov     [r14+8], rax
0x1800436b8  mov     [rbp+string], 0
0x1800436c0  mov     byte ptr [r15], 1
0x1800436c4  jmp     short loc_1800436FE
0x1800436c6  cmp     qword ptr [rsi+38h], 7FFFFFFFh
0x1800436ce  jnz     short loc_1800436D7
0x1800436d0  mov     ebx, 8007000Eh
0x1800436d5  jmp     short loc_1800436FE
0x1800436d7  lea     r9, [rbp+arg_18]
0x1800436db  mov     [rbp+arg_18], rdi
0x1800436df  lea     r8, [rbp+string]
0x1800436e3  lea     rdx, [rbp+newString]
0x1800436e7  lea     rcx, [rsi+28h]
0x1800436eb  call    ?SetAt@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@0PEAPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::SetAt(HSTRING__ * const &,HSTRING__ * const &,XWinRT::TXPOSITION * *)
0x1800436f0  mov     ebx, eax
0x1800436f2  test    eax, eax
0x1800436f4  js      short loc_1800436FE
0x1800436f6  mov     [rbp+newString], rdi
0x1800436fa  mov     [rbp+string], rdi
0x1800436fe  mov     rax, [rbp+var_10]
0x180043702  test    rax, rax
0x180043705  jz      short loc_18004371E
0x180043707  cmp     dword ptr [rax], 1
0x18004370a  lea     rcx, [rax+8]; SRWLock
0x18004370e  jnz     short loc_180043718
0x180043710  add     dword ptr [rcx], 10000000h
0x180043716  jmp     short loc_18004371E
0x180043718  call    cs:__imp_ReleaseSRWLockExclusive
0x18004371e  mov     rcx, rdi; string
0x180043721  call    cs:__imp_WindowsDeleteString
0x180043727  mov     rcx, [rbp+string]; string
0x18004372b  call    cs:__imp_WindowsDeleteString
0x180043731  test    ebx, ebx
0x180043733  js      short loc_18004375E
0x180043735  mov     al, [r15]
0x180043738  mov     r8, rsi
0x18004373b  movzx   edx, byte ptr [rsi+99h]
0x180043742  neg     al
0x180043744  movzx   ecx, byte ptr [rbp+arg_18]
0x180043748  sbb     r9d, r9d
0x18004374b  mov     [rsp+50h+var_30], r13
0x180043750  and     r9d, 2
0x180043754  inc     r9d
0x180043757  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(...)
0x18004375c  mov     ebx, eax
0x18004375e  mov     rcx, [rbp+newString]; string
0x180043762  call    cs:__imp_WindowsDeleteString
0x180043768  mov     eax, ebx
0x18004376a  mov     rbx, [rsp+50h+arg_0]
0x180043772  add     rsp, 50h
0x180043776  pop     r15
0x180043778  pop     r14
0x18004377a  pop     r13
0x18004377c  pop     r12
0x18004377e  pop     rdi
0x18004377f  pop     rsi
0x180043780  pop     rbp
0x180043781  retn
```
