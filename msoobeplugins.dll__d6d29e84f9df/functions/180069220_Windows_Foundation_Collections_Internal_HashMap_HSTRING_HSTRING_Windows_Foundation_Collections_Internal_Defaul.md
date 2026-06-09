# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(HSTRING__ *,HSTRING__ *,uchar *)

- ea: `0x180069220`
- end: `0x1800693e3`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@0PEAE@Z`
- size: `451`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x180003470`
- `0x18005e668`
- `0x180062318`
- `0x180065734`
- `0x180066260`
- `0x180069220`
- `0x180069704`
- `0x18006a354`
- `0x18006b940`
- `0x18006ca5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180069373`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180069373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180069267`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180069267`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180069304`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006937c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180069386`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800693be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180069304`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006937c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180069386`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800693be`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(
        __int64 a1,
        HSTRING a2,
        __int64 a3,
        _BYTE *a4)
{
  int v7; // edi
  HSTRING v8; // rbx
  __int64 v9; // r14
  RTL_SRWLOCK *v10; // rcx
  _BYTE v12[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v13; // [rsp+38h] [rbp-40h] BYREF
  __int64 v14; // [rsp+40h] [rbp-38h] BYREF
  HSTRING string; // [rsp+48h] [rbp-30h] BYREF
  HSTRING newString; // [rsp+50h] [rbp-28h] BYREF
  RTL_SRWLOCK *v17; // [rsp+58h] [rbp-20h] BYREF

  v14 = a3;
  *a4 = 0;
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized();
  newString = 0;
  LODWORD(v13) = WindowsDuplicateString(a2, &newString);
  v7 = v13;
  if ( (int)v13 >= 0 )
  {
    XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(&string);
    v8 = 0;
    XWinRT::SerializingLockPolicy::Write(&v17, a1 + 128, &v13);
    v7 = v13;
    if ( (int)v13 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(v12, *(unsigned __int8 *)(a1 + 154), a1 + 156);
      XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 144));
      v13 = 0;
      v7 = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Lookup(
             a1 + 40,
             &newString,
             &v13);
      if ( v7 >= 0 )
      {
        v9 = v13;
        if ( v13 )
        {
          v8 = *(HSTRING *)(v13 + 8);
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
          v14 = 0;
          v7 = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::SetAt(
                 a1 + 40,
                 &newString,
                 &string,
                 &v14);
          if ( v7 >= 0 )
          {
            newString = 0;
            string = 0;
          }
        }
      }
    }
    if ( v17 )
    {
      v10 = v17 + 1;
      if ( LODWORD(v17->Ptr) == 1 )
        LODWORD(v10->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v10);
    }
    WindowsDeleteString(v8);
    WindowsDeleteString(string);
  }
  if ( v7 >= 0 )
    v7 = Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(
           v12[0],
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
0x180069220  push    rbp
0x180069222  push    rbx
0x180069223  push    rsi
0x180069224  push    rdi
0x180069225  push    r12
0x180069227  push    r13
0x180069229  push    r14
0x18006922b  push    r15
0x18006922d  mov     rbp, rsp
0x180069230  sub     rsp, 78h
0x180069234  mov     rax, cs:__security_cookie
0x18006923b  xor     rax, rsp
0x18006923e  mov     [rbp+var_18], rax
0x180069242  mov     r12, r9
0x180069245  mov     [rbp+var_38], r8
0x180069249  mov     r13, rdx
0x18006924c  mov     byte ptr [r9], 0
0x180069250  mov     rsi, rcx
0x180069253  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x180069258  lea     rdx, [rbp+newString]; newString
0x18006925c  mov     [rbp+newString], 0
0x180069264  mov     rcx, r13; string
0x180069267  call    cs:__imp_WindowsDuplicateString
0x18006926d  mov     dword ptr [rbp+var_40], eax
0x180069270  mov     edi, eax
0x180069272  test    eax, eax
0x180069274  js      loc_18006938C
0x18006927a  lea     r8, [rbp+var_40]
0x18006927e  lea     rdx, [rbp+var_38]
0x180069282  lea     rcx, [rbp+string]; newString
0x180069286  call    ??$?0PEAUHSTRING__@@@?$AutoValue@PEAUHSTRING__@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUHSTRING__@@PEAJ@Z; XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(HSTRING__ * const &,long *)
0x18006928b  mov     edi, dword ptr [rbp+var_40]
0x18006928e  xor     ebx, ebx
0x180069290  test    edi, edi
0x180069292  js      loc_180069379
0x180069298  lea     rdx, [rsi+80h]
0x18006929f  lea     r8, [rbp+var_40]
0x1800692a3  lea     rcx, [rbp+var_20]
0x1800692a7  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x1800692ac  mov     edi, dword ptr [rbp+var_40]
0x1800692af  test    edi, edi
0x1800692b1  js      loc_180069359
0x1800692b7  movzx   edx, byte ptr [rsi+9Ah]
0x1800692be  lea     r8, [rsi+9Ch]
0x1800692c5  lea     rcx, [rbp+var_48]
0x1800692c9  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x1800692ce  lea     rcx, [rsi+90h]; this
0x1800692d5  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x1800692da  lea     r8, [rbp+var_40]
0x1800692de  mov     [rbp+var_40], rbx
0x1800692e2  lea     rdx, [rbp+newString]
0x1800692e6  lea     rcx, [rsi+28h]
0x1800692ea  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::CPair * *)
0x1800692ef  mov     edi, eax
0x1800692f1  test    eax, eax
0x1800692f3  js      short loc_180069359
0x1800692f5  mov     r14, [rbp+var_40]
0x1800692f9  test    r14, r14
0x1800692fc  jz      short loc_180069321
0x1800692fe  mov     rbx, [r14+8]
0x180069302  xor     ecx, ecx; string
0x180069304  call    cs:__imp_WindowsDeleteString
0x18006930a  mov     rax, [rbp+string]
0x18006930e  mov     [r14+8], rax
0x180069312  mov     [rbp+string], 0
0x18006931a  mov     byte ptr [r12], 1
0x18006931f  jmp     short loc_180069359
0x180069321  cmp     qword ptr [rsi+38h], 7FFFFFFFh
0x180069329  jnz     short loc_180069332
0x18006932b  mov     edi, 8007000Eh
0x180069330  jmp     short loc_180069359
0x180069332  lea     r9, [rbp+var_38]
0x180069336  mov     [rbp+var_38], rbx
0x18006933a  lea     r8, [rbp+string]
0x18006933e  lea     rdx, [rbp+newString]
0x180069342  lea     rcx, [rsi+28h]
0x180069346  call    ?SetAt@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@0PEAPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::SetAt(HSTRING__ * const &,HSTRING__ * const &,XWinRT::TXPOSITION * *)
0x18006934b  mov     edi, eax
0x18006934d  test    eax, eax
0x18006934f  js      short loc_180069359
0x180069351  mov     [rbp+newString], rbx
0x180069355  mov     [rbp+string], rbx
0x180069359  mov     rax, [rbp+var_20]
0x18006935d  test    rax, rax
0x180069360  jz      short loc_180069379
0x180069362  cmp     dword ptr [rax], 1
0x180069365  lea     rcx, [rax+8]; SRWLock
0x180069369  jnz     short loc_180069373
0x18006936b  add     dword ptr [rcx], 10000000h
0x180069371  jmp     short loc_180069379
0x180069373  call    cs:__imp_ReleaseSRWLockExclusive
0x180069379  mov     rcx, rbx; string
0x18006937c  call    cs:__imp_WindowsDeleteString
0x180069382  mov     rcx, [rbp+string]; string
0x180069386  call    cs:__imp_WindowsDeleteString
0x18006938c  test    edi, edi
0x18006938e  js      short loc_1800693BA
0x180069390  mov     al, [r12]
0x180069394  mov     r8, rsi
0x180069397  movzx   edx, byte ptr [rsi+99h]
0x18006939e  neg     al
0x1800693a0  movzx   ecx, [rbp+var_48]
0x1800693a4  sbb     r9d, r9d
0x1800693a7  mov     [rsp+78h+var_58], r13
0x1800693ac  and     r9d, 2
0x1800693b0  inc     r9d
0x1800693b3  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(...)
0x1800693b8  mov     edi, eax
0x1800693ba  mov     rcx, [rbp+newString]; string
0x1800693be  call    cs:__imp_WindowsDeleteString
0x1800693c4  mov     eax, edi
0x1800693c6  mov     rcx, [rbp+var_18]
0x1800693ca  xor     rcx, rsp; StackCookie
0x1800693cd  call    __security_check_cookie
0x1800693d2  add     rsp, 78h
0x1800693d6  pop     r15
0x1800693d8  pop     r14
0x1800693da  pop     r13
0x1800693dc  pop     r12
0x1800693de  pop     rdi
0x1800693df  pop     rsi
0x1800693e0  pop     rbx
0x1800693e1  pop     rbp
0x1800693e2  retn
```
