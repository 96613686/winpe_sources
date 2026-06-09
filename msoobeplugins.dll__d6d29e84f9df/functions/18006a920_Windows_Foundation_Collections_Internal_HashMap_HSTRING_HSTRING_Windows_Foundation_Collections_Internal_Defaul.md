# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(HSTRING__ *)

- ea: `0x18006a920`
- end: `0x18006aadb`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `443`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callees

- `0x180003470`
- `0x180062318`
- `0x180065734`
- `0x180066260`
- `0x180067708`
- `0x180069704`
- `0x18006a354`
- `0x18006a920`
- `0x18006ca5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006aa73`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006aa73`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006a9cc`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006a9cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a9ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a9fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006aa7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006aa85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a9ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a9fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006aa7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006aa85`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(
        __int64 a1,
        __int64 a2)
{
  int v3; // esi
  HSTRING v4; // rbx
  HSTRING v5; // rdi
  __int64 v6; // r14
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rcx
  RTL_SRWLOCK *v11; // rcx
  _BYTE v13[8]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v14; // [rsp+38h] [rbp-28h] BYREF
  __int64 v15; // [rsp+40h] [rbp-20h] BYREF
  RTL_SRWLOCK *v16; // [rsp+48h] [rbp-18h] BYREF

  v15 = a2;
  v3 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized();
  if ( v3 >= 0 )
  {
    v4 = 0;
    LODWORD(v14) = 0;
    v5 = 0;
    XWinRT::SerializingLockPolicy::Write(&v16, a1 + 128, &v14);
    v3 = v14;
    if ( (int)v14 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(v13, *(unsigned __int8 *)(a1 + 154), a1 + 156);
      v14 = 0;
      v3 = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Lookup(
             a1 + 40,
             &v15,
             &v14);
      if ( v3 >= 0 )
      {
        v6 = v14;
        if ( v14 )
        {
          v3 = XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 144));
          if ( v3 >= 0 )
          {
            v4 = *(HSTRING *)v6;
            WindowsDeleteString(0);
            v5 = *(HSTRING *)(v6 + 8);
            WindowsDeleteString(0);
            if ( v6 )
            {
              v7 = (unsigned int)(*(_DWORD *)(v6 + 24) % *(_DWORD *)(a1 + 64));
              v8 = *(_QWORD *)(a1 + 48);
              v9 = *(_QWORD *)(v8 + 8 * v7);
              if ( v6 == v9 )
              {
                v9 = 0;
              }
              else
              {
                while ( *(_QWORD *)(v9 + 16) != v6 )
                  v9 = *(_QWORD *)(v9 + 16);
              }
              v10 = *(_QWORD *)(v6 + 16);
              if ( v9 )
                *(_QWORD *)(v9 + 16) = v10;
              else
                *(_QWORD *)(v8 + 8 * v7) = v10;
              XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::FreeNode(
                a1 + 40,
                v6);
              v3 = 0;
            }
            else
            {
              v4 = 0;
              v3 = -2147418113;
              v5 = 0;
            }
          }
        }
        else
        {
          v3 = -2147483637;
          RoOriginateError(2147483659LL, 0);
        }
      }
    }
    if ( v16 )
    {
      v11 = v16 + 1;
      if ( LODWORD(v16->Ptr) == 1 )
        LODWORD(v11->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v11);
    }
    WindowsDeleteString(v5);
    WindowsDeleteString(v4);
  }
  if ( v3 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(
                           v13[0],
                           *(unsigned __int8 *)(a1 + 153),
                           a1,
                           2,
                           v15);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18006a920  mov     [rsp-28h+arg_10], rbx
0x18006a925  mov     [rsp-28h+arg_18], rsi
0x18006a92a  push    rbp
0x18006a92b  push    rdi
0x18006a92c  push    r13
0x18006a92e  push    r14
0x18006a930  push    r15
0x18006a932  mov     rbp, rsp
0x18006a935  sub     rsp, 60h
0x18006a939  mov     rax, cs:__security_cookie
0x18006a940  xor     rax, rsp
0x18006a943  mov     [rbp+var_10], rax
0x18006a947  mov     r15, rcx
0x18006a94a  mov     [rbp+var_20], rdx
0x18006a94e  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x18006a953  mov     esi, eax
0x18006a955  test    eax, eax
0x18006a957  js      loc_18006AA8B
0x18006a95d  xor     ebx, ebx
0x18006a95f  lea     rdx, [r15+80h]
0x18006a966  lea     r8, [rbp+var_28]
0x18006a96a  mov     dword ptr [rbp+var_28], ebx
0x18006a96d  lea     rcx, [rbp+var_18]
0x18006a971  xor     edi, edi
0x18006a973  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18006a978  mov     esi, dword ptr [rbp+var_28]
0x18006a97b  test    esi, esi
0x18006a97d  js      loc_18006AA59
0x18006a983  movzx   edx, byte ptr [r15+9Ah]
0x18006a98b  lea     r8, [r15+9Ch]
0x18006a992  lea     rcx, [rbp+var_30]
0x18006a996  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18006a99b  lea     r8, [rbp+var_28]
0x18006a99f  mov     [rbp+var_28], rbx
0x18006a9a3  lea     rdx, [rbp+var_20]
0x18006a9a7  lea     rcx, [r15+28h]
0x18006a9ab  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::CPair * *)
0x18006a9b0  mov     esi, eax
0x18006a9b2  test    eax, eax
0x18006a9b4  js      loc_18006AA59
0x18006a9ba  mov     r14, [rbp+var_28]
0x18006a9be  test    r14, r14
0x18006a9c1  jnz     short loc_18006A9D7
0x18006a9c3  mov     esi, 8000000Bh
0x18006a9c8  xor     edx, edx
0x18006a9ca  mov     ecx, esi
0x18006a9cc  call    cs:__imp_RoOriginateError
0x18006a9d2  jmp     loc_18006AA59
0x18006a9d7  lea     rcx, [r15+90h]; this
0x18006a9de  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x18006a9e3  mov     esi, eax
0x18006a9e5  test    eax, eax
0x18006a9e7  js      short loc_18006AA59
0x18006a9e9  mov     rbx, [r14]
0x18006a9ec  xor     ecx, ecx; string
0x18006a9ee  call    cs:__imp_WindowsDeleteString
0x18006a9f4  mov     rdi, [r14+8]
0x18006a9f8  xor     ecx, ecx; string
0x18006a9fa  call    cs:__imp_WindowsDeleteString
0x18006aa00  test    r14, r14
0x18006aa03  jz      short loc_18006AA50
0x18006aa05  mov     eax, [r14+18h]
0x18006aa09  xor     edx, edx
0x18006aa0b  div     dword ptr [r15+40h]
0x18006aa0f  mov     r8d, edx
0x18006aa12  mov     rdx, [r15+30h]
0x18006aa16  mov     rax, [rdx+r8*8]
0x18006aa1a  cmp     r14, rax
0x18006aa1d  jnz     short loc_18006AA27
0x18006aa1f  xor     eax, eax
0x18006aa21  jmp     short loc_18006AA2D
0x18006aa23  mov     rax, [rax+10h]
0x18006aa27  cmp     [rax+10h], r14
0x18006aa2b  jnz     short loc_18006AA23
0x18006aa2d  mov     rcx, [r14+10h]
0x18006aa31  test    rax, rax
0x18006aa34  jnz     short loc_18006AA3C
0x18006aa36  mov     [rdx+r8*8], rcx
0x18006aa3a  jmp     short loc_18006AA40
0x18006aa3c  mov     [rax+10h], rcx
0x18006aa40  mov     rdx, r14
0x18006aa43  lea     rcx, [r15+28h]
0x18006aa47  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::CNode *)
0x18006aa4c  xor     esi, esi
0x18006aa4e  jmp     short loc_18006AA59
0x18006aa50  xor     ebx, ebx
0x18006aa52  mov     esi, 8000FFFFh
0x18006aa57  xor     edi, edi
0x18006aa59  mov     rax, [rbp+var_18]
0x18006aa5d  test    rax, rax
0x18006aa60  jz      short loc_18006AA79
0x18006aa62  cmp     dword ptr [rax], 1
0x18006aa65  lea     rcx, [rax+8]; SRWLock
0x18006aa69  jnz     short loc_18006AA73
0x18006aa6b  add     dword ptr [rcx], 10000000h
0x18006aa71  jmp     short loc_18006AA79
0x18006aa73  call    cs:__imp_ReleaseSRWLockExclusive
0x18006aa79  mov     rcx, rdi; string
0x18006aa7c  call    cs:__imp_WindowsDeleteString
0x18006aa82  mov     rcx, rbx; string
0x18006aa85  call    cs:__imp_WindowsDeleteString
0x18006aa8b  test    esi, esi
0x18006aa8d  js      short loc_18006AAB4
0x18006aa8f  mov     rax, [rbp+var_20]
0x18006aa93  mov     r9d, 2
0x18006aa99  movzx   edx, byte ptr [r15+99h]
0x18006aaa1  mov     r8, r15
0x18006aaa4  movzx   ecx, [rbp+var_30]
0x18006aaa8  mov     [rsp+60h+var_40], rax
0x18006aaad  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(...)
0x18006aab2  mov     esi, eax
0x18006aab4  mov     eax, esi
0x18006aab6  mov     rcx, [rbp+var_10]
0x18006aaba  xor     rcx, rsp; StackCookie
0x18006aabd  call    __security_check_cookie
0x18006aac2  lea     r11, [rsp+60h+var_s0]
0x18006aac7  mov     rbx, [r11+40h]
0x18006aacb  mov     rsi, [r11+48h]
0x18006aacf  mov     rsp, r11
0x18006aad2  pop     r15
0x18006aad4  pop     r14
0x18006aad6  pop     r13
0x18006aad8  pop     rdi
0x18006aad9  pop     rbp
0x18006aada  retn
```
