# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(HSTRING__ *)

- ea: `0x180046d40`
- end: `0x180046e8a`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `330`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x1800335b4`
- `0x180038144`
- `0x180038adc`
- `0x180044100`
- `0x180045db0`
- `0x180046d40`
- `0x1800473c4`
- `0x18004ac6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046e39`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046e39`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180046dd2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180046dd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046e0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046e1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046e42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046e4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046e0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046e1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046e42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046e4b`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(
        unsigned __int8 *a1,
        __int64 a2)
{
  int v3; // ebx
  HSTRING *v4; // r15
  HSTRING v5; // r14
  HSTRING v6; // rsi
  RTL_SRWLOCK *v7; // rcx
  __int64 v9; // [rsp+78h] [rbp+48h] BYREF
  HSTRING *v10; // [rsp+80h] [rbp+50h] BYREF
  RTL_SRWLOCK *v11; // [rsp+88h] [rbp+58h] BYREF

  v9 = a2;
  v3 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized();
  if ( v3 < 0 )
    goto LABEL_15;
  LODWORD(v10) = 0;
  XWinRT::SerializingLockPolicy::Write(&v11, a1 + 128, &v10);
  v3 = (int)v10;
  if ( (int)v10 >= 0 )
  {
    XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v10, a1[154], a1 + 156);
    v10 = 0;
    v3 = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Lookup(
           a1 + 40,
           &v9,
           &v10);
    if ( v3 >= 0 )
    {
      v4 = v10;
      if ( v10 )
      {
        v3 = XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 144));
        if ( v3 >= 0 )
        {
          v5 = *v4;
          WindowsDeleteString(0);
          v6 = v4[1];
          WindowsDeleteString(0);
          v3 = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::RemoveAtPos(
                 a1 + 40,
                 v4);
          if ( v3 < 0 )
          {
            v6 = 0;
            v5 = 0;
          }
          goto LABEL_7;
        }
      }
      else
      {
        v3 = -2147483637;
        RoOriginateError(2147483659LL, 0);
      }
    }
  }
  v5 = 0;
  v6 = 0;
LABEL_7:
  if ( v11 )
  {
    v7 = v11 + 1;
    if ( LODWORD(v11->Ptr) == 1 )
      LODWORD(v7->Ptr) += 0x10000000;
    else
      ReleaseSRWLockExclusive(v7);
  }
  WindowsDeleteString(v6);
  WindowsDeleteString(v5);
LABEL_15:
  if ( v3 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(
                           (unsigned __int8)v10,
                           a1[153],
                           a1,
                           2,
                           v9);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180046d40  mov     [rsp-38h+arg_8], rdx
0x180046d45  push    rbp
0x180046d46  push    rbx
0x180046d47  push    rsi
0x180046d48  push    rdi
0x180046d49  push    r12
0x180046d4b  push    r14
0x180046d4d  push    r15
0x180046d4f  mov     rbp, rsp
0x180046d52  sub     rsp, 30h
0x180046d56  mov     rdi, rcx
0x180046d59  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x180046d5e  mov     ebx, eax
0x180046d60  test    eax, eax
0x180046d62  js      loc_180046E51
0x180046d68  lea     rdx, [rdi+80h]
0x180046d6f  mov     dword ptr [rbp+arg_10], 0
0x180046d76  lea     r8, [rbp+arg_10]
0x180046d7a  lea     rcx, [rbp+arg_18]
0x180046d7e  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180046d83  mov     ebx, dword ptr [rbp+arg_10]
0x180046d86  test    ebx, ebx
0x180046d88  js      short loc_180046DD8
0x180046d8a  movzx   edx, byte ptr [rdi+9Ah]
0x180046d91  lea     r8, [rdi+9Ch]
0x180046d98  lea     rcx, [rbp+arg_10]
0x180046d9c  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180046da1  lea     r8, [rbp+arg_10]
0x180046da5  mov     [rbp+arg_10], 0
0x180046dad  lea     rdx, [rbp+arg_8]
0x180046db1  lea     rcx, [rdi+28h]
0x180046db5  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::CPair * *)
0x180046dba  mov     ebx, eax
0x180046dbc  test    eax, eax
0x180046dbe  js      short loc_180046DD8
0x180046dc0  mov     r15, [rbp+arg_10]
0x180046dc4  test    r15, r15
0x180046dc7  jnz     short loc_180046DF7
0x180046dc9  mov     ebx, 8000000Bh
0x180046dce  xor     edx, edx
0x180046dd0  mov     ecx, ebx
0x180046dd2  call    cs:__imp_RoOriginateError
0x180046dd8  xor     r14d, r14d
0x180046ddb  xor     esi, esi
0x180046ddd  mov     rax, [rbp+arg_18]
0x180046de1  test    rax, rax
0x180046de4  jz      short loc_180046E3F
0x180046de6  cmp     dword ptr [rax], 1
0x180046de9  lea     rcx, [rax+8]; SRWLock
0x180046ded  jnz     short loc_180046E39
0x180046def  add     dword ptr [rcx], 10000000h
0x180046df5  jmp     short loc_180046E3F
0x180046df7  lea     rcx, [rdi+90h]; this
0x180046dfe  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180046e03  mov     ebx, eax
0x180046e05  test    eax, eax
0x180046e07  js      short loc_180046DD8
0x180046e09  mov     r14, [r15]
0x180046e0c  xor     ecx, ecx; string
0x180046e0e  call    cs:__imp_WindowsDeleteString
0x180046e14  mov     rsi, [r15+8]
0x180046e18  xor     ecx, ecx; string
0x180046e1a  call    cs:__imp_WindowsDeleteString
0x180046e20  mov     rdx, r15
0x180046e23  lea     rcx, [rdi+28h]
0x180046e27  call    ?RemoveAtPos@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@QEAAJPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::RemoveAtPos(XWinRT::TXPOSITION *)
0x180046e2c  mov     ebx, eax
0x180046e2e  test    eax, eax
0x180046e30  jns     short loc_180046DDD
0x180046e32  xor     esi, esi
0x180046e34  xor     r14d, r14d
0x180046e37  jmp     short loc_180046DDD
0x180046e39  call    cs:__imp_ReleaseSRWLockExclusive
0x180046e3f  mov     rcx, rsi; string
0x180046e42  call    cs:__imp_WindowsDeleteString
0x180046e48  mov     rcx, r14; string
0x180046e4b  call    cs:__imp_WindowsDeleteString
0x180046e51  test    ebx, ebx
0x180046e53  js      short loc_180046E79
0x180046e55  mov     rax, [rbp+arg_8]
0x180046e59  mov     r9d, 2
0x180046e5f  movzx   edx, byte ptr [rdi+99h]
0x180046e66  mov     r8, rdi
0x180046e69  movzx   ecx, byte ptr [rbp+arg_10]
0x180046e6d  mov     [rsp+30h+var_10], rax
0x180046e72  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(...)
0x180046e77  mov     ebx, eax
0x180046e79  mov     eax, ebx
0x180046e7b  add     rsp, 30h
0x180046e7f  pop     r15
0x180046e81  pop     r14
0x180046e83  pop     r12
0x180046e85  pop     rdi
0x180046e86  pop     rsi
0x180046e87  pop     rbx
0x180046e88  pop     rbp
0x180046e89  retn
```
