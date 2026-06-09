# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(HSTRING__ *)

- ea: `0x180157b50`
- end: `0x180157cc7`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$HashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `375`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x180033284`
- `0x1800332a0`
- `0x180033300`
- `0x180071408`
- `0x180071438`
- `0x180084848`
- `0x180156224`
- `0x180157b50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180157c7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180157c7c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180157be7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180157be7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180157c06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180157c85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180157c06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180157c85`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(
        __int64 a1,
        __int64 a2)
{
  int v3; // edi
  HSTRING v4; // rbx
  __int64 v5; // rsi
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rcx
  RTL_SRWLOCK *v10; // rcx
  __int64 v12; // [rsp+68h] [rbp+38h] BYREF
  __int64 v13; // [rsp+70h] [rbp+40h] BYREF
  RTL_SRWLOCK *v14; // [rsp+78h] [rbp+48h] BYREF

  v12 = a2;
  v3 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized();
  if ( v3 >= 0 )
  {
    v4 = 0;
    LODWORD(v13) = 0;
    XWinRT::SerializingLockPolicy::Write(&v14, a1 + 160, &v13);
    v3 = v13;
    if ( (int)v13 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v13, *(unsigned __int8 *)(a1 + 186), a1 + 188);
      v13 = 0;
      v3 = XWinRT::XHashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<unsigned char>>::Lookup(
             a1 + 72,
             &v12,
             &v13);
      if ( v3 >= 0 )
      {
        v5 = v13;
        if ( v13 )
        {
          v3 = XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 176));
          if ( v3 >= 0 )
          {
            v4 = *(HSTRING *)v5;
            WindowsDeleteString(0);
            if ( v5 )
            {
              v6 = (unsigned int)(*(_DWORD *)(v5 + 24) % *(_DWORD *)(a1 + 96));
              v7 = *(_QWORD *)(a1 + 80);
              v8 = *(_QWORD *)(v7 + 8 * v6);
              if ( v5 == v8 )
              {
                v8 = 0;
              }
              else
              {
                while ( *(_QWORD *)(v8 + 16) != v5 )
                  v8 = *(_QWORD *)(v8 + 16);
              }
              v9 = *(_QWORD *)(v5 + 16);
              if ( v8 )
                *(_QWORD *)(v8 + 16) = v9;
              else
                *(_QWORD *)(v7 + 8 * v6) = v9;
              XWinRT::XHashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<unsigned char>>::FreeNode(
                a1 + 72,
                v5);
              v3 = 0;
            }
            else
            {
              v3 = -2147418113;
              v4 = 0;
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
    if ( v14 )
    {
      v10 = v14 + 1;
      if ( LODWORD(v14->Ptr) == 1 )
        LODWORD(v10->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v10);
    }
    WindowsDeleteString(v4);
  }
  if ( v3 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<_GUID,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>,0,1,0>::RaiseEvent(
                           (unsigned __int8)v13,
                           *(unsigned __int8 *)(a1 + 185),
                           a1,
                           2,
                           v12);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180157b50  mov     [rsp-28h+arg_0], rbx
0x180157b55  mov     [rsp-28h+arg_8], rdx
0x180157b5a  push    rbp
0x180157b5b  push    rsi
0x180157b5c  push    rdi
0x180157b5d  push    r14
0x180157b5f  push    r15
0x180157b61  mov     rbp, rsp
0x180157b64  sub     rsp, 30h
0x180157b68  mov     r14, rcx
0x180157b6b  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$HashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized(void)
0x180157b70  mov     edi, eax
0x180157b72  test    eax, eax
0x180157b74  js      loc_180157C8B
0x180157b7a  xor     ebx, ebx
0x180157b7c  lea     rdx, [r14+0A0h]
0x180157b83  lea     r8, [rbp+arg_10]
0x180157b87  mov     dword ptr [rbp+arg_10], ebx
0x180157b8a  lea     rcx, [rbp+arg_18]
0x180157b8e  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180157b93  mov     edi, dword ptr [rbp+arg_10]
0x180157b96  test    edi, edi
0x180157b98  js      loc_180157C62
0x180157b9e  movzx   edx, byte ptr [r14+0BAh]
0x180157ba6  lea     r8, [r14+0BCh]
0x180157bad  lea     rcx, [rbp+arg_10]
0x180157bb1  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180157bb6  lea     r8, [rbp+arg_10]
0x180157bba  mov     [rbp+arg_10], rbx
0x180157bbe  lea     rdx, [rbp+arg_8]
0x180157bc2  lea     rcx, [r14+48h]
0x180157bc6  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@EUKeyTraits@?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$HashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@E@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<uchar>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<uchar>>::CPair * *)
0x180157bcb  mov     edi, eax
0x180157bcd  test    eax, eax
0x180157bcf  js      loc_180157C62
0x180157bd5  mov     rsi, [rbp+arg_10]
0x180157bd9  test    rsi, rsi
0x180157bdc  jnz     short loc_180157BEF
0x180157bde  mov     edi, 8000000Bh
0x180157be3  xor     edx, edx
0x180157be5  mov     ecx, edi
0x180157be7  call    cs:__imp_RoOriginateError
0x180157bed  jmp     short loc_180157C62
0x180157bef  lea     rcx, [r14+0B0h]; this
0x180157bf6  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180157bfb  mov     edi, eax
0x180157bfd  test    eax, eax
0x180157bff  js      short loc_180157C62
0x180157c01  mov     rbx, [rsi]
0x180157c04  xor     ecx, ecx; string
0x180157c06  call    cs:__imp_WindowsDeleteString
0x180157c0c  test    rsi, rsi
0x180157c0f  jz      short loc_180157C5B
0x180157c11  mov     eax, [rsi+18h]
0x180157c14  xor     edx, edx
0x180157c16  div     dword ptr [r14+60h]
0x180157c1a  mov     r8d, edx
0x180157c1d  mov     rdx, [r14+50h]
0x180157c21  mov     rax, [rdx+r8*8]
0x180157c25  cmp     rsi, rax
0x180157c28  jnz     short loc_180157C32
0x180157c2a  xor     eax, eax
0x180157c2c  jmp     short loc_180157C38
0x180157c2e  mov     rax, [rax+10h]
0x180157c32  cmp     [rax+10h], rsi
0x180157c36  jnz     short loc_180157C2E
0x180157c38  mov     rcx, [rsi+10h]
0x180157c3c  test    rax, rax
0x180157c3f  jnz     short loc_180157C47
0x180157c41  mov     [rdx+r8*8], rcx
0x180157c45  jmp     short loc_180157C4B
0x180157c47  mov     [rax+10h], rcx
0x180157c4b  mov     rdx, rsi
0x180157c4e  lea     rcx, [r14+48h]
0x180157c52  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@EUKeyTraits@?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$HashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@E@XWinRT@@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<uchar>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<uchar>>::CNode *)
0x180157c57  xor     edi, edi
0x180157c59  jmp     short loc_180157C62
0x180157c5b  mov     edi, 8000FFFFh
0x180157c60  xor     ebx, ebx
0x180157c62  mov     rax, [rbp+arg_18]
0x180157c66  test    rax, rax
0x180157c69  jz      short loc_180157C82
0x180157c6b  cmp     dword ptr [rax], 1
0x180157c6e  lea     rcx, [rax+8]; SRWLock
0x180157c72  jnz     short loc_180157C7C
0x180157c74  add     dword ptr [rcx], 10000000h
0x180157c7a  jmp     short loc_180157C82
0x180157c7c  call    cs:__imp_ReleaseSRWLockExclusive
0x180157c82  mov     rcx, rbx; string
0x180157c85  call    cs:__imp_WindowsDeleteString
0x180157c8b  test    edi, edi
0x180157c8d  js      short loc_180157CB4
0x180157c8f  mov     rax, [rbp+arg_8]
0x180157c93  mov     r9d, 2
0x180157c99  movzx   edx, byte ptr [r14+0B9h]
0x180157ca1  mov     r8, r14
0x180157ca4  movzx   ecx, byte ptr [rbp+arg_10]
0x180157ca8  mov     [rsp+30h+var_10], rax
0x180157cad  call    ?RaiseEvent@?$HashMapOptions@U_GUID@@PEAUIInspectable@@U?$DefaultLifetimeTraits@U_GUID@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<_GUID,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>,0,1,0>::RaiseEvent(...)
0x180157cb2  mov     edi, eax
0x180157cb4  mov     rbx, [rsp+30h+arg_0]
0x180157cb9  mov     eax, edi
0x180157cbb  add     rsp, 30h
0x180157cbf  pop     r15
0x180157cc1  pop     r14
0x180157cc3  pop     rdi
0x180157cc4  pop     rsi
0x180157cc5  pop     rbp
0x180157cc6  retn
```
