# CFormatForDisplay::_FormatRangeFromValues(tagPROPVARIANT const &,tagPROPVARIANT const &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x18007a8f8`
- end: `0x18007aaa9`
- name: `?_FormatRangeFromValues@CFormatForDisplay@@AEAAJAEBUtagPROPVARIANT@@0AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180066dd4`

## callees

- `0x18000ccd0`
- `0x18000d240`
- `0x18001ae9c`
- `0x18001bfbc`
- `0x180062168`
- `0x18006ba10`
- `0x18006ed20`
- `0x18007a8f8`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18007a9df`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18007a9df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007aa68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007aa71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007aa68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007aa71`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFormatForDisplay::_FormatRangeFromValues(
        __int64 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4)
{
  int v7; // ebx
  WCHAR *v8; // rdi
  WCHAR *v9; // rsi
  _WORD *v11[3]; // [rsp+20h] [rbp-49h] BYREF
  LPCWSTR v12[3]; // [rsp+38h] [rbp-31h] BYREF
  LPCWSTR pszStr2; // [rsp+50h] [rbp-19h] BYREF
  __int64 v14; // [rsp+58h] [rbp-11h]
  __int64 v15; // [rsp+60h] [rbp-9h]
  LPCWSTR pszStr1; // [rsp+68h] [rbp-1h] BYREF
  __int64 v17; // [rsp+70h] [rbp+7h]
  __int64 v18; // [rsp+78h] [rbp+Fh]

  pszStr1 = 0;
  v17 = 0;
  v18 = 0;
  v7 = CFormatForDisplay::FormatForDisplay(a1, a2, (__int64)&pszStr1);
  if ( v7 >= 0 )
  {
    pszStr2 = 0;
    v14 = 0;
    v15 = 0;
    v7 = CFormatForDisplay::FormatForDisplay(a1, a3, (__int64)&pszStr2);
    if ( v7 >= 0 )
    {
      v8 = (WCHAR *)pszStr1;
      if ( pszStr1 )
        goto LABEL_6;
      v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
             &pszStr1,
             &Src,
             -1);
      if ( v7 >= 0 )
      {
        v8 = (WCHAR *)pszStr1;
LABEL_6:
        pszStr1 = 0;
        v18 = 0;
        v17 = 0;
        v9 = (WCHAR *)pszStr2;
        if ( !pszStr2 )
        {
          v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                 &pszStr2,
                 &Src,
                 -1);
          if ( v7 < 0 )
          {
LABEL_17:
            CoTaskMemFree(v8);
            goto LABEL_18;
          }
          v9 = (WCHAR *)pszStr2;
        }
        pszStr2 = 0;
        v15 = 0;
        v14 = 0;
        if ( StrCmpICW(v8, v9) )
        {
          memset(v12, 0, sizeof(v12));
          v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                 v12,
                 g_hModMUIResources,
                 196);
          if ( v7 >= 0 )
          {
            memset(v11, 0, sizeof(v11));
            v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeMessage(
                   v11,
                   v12[0],
                   v8,
                   v9);
            if ( v7 >= 0 )
              v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                     a4,
                     v11[0]);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v11);
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v12);
        }
        else
        {
          v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(a4, v8);
        }
        CoTaskMemFree(v9);
        goto LABEL_17;
      }
    }
LABEL_18:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszStr2);
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszStr1);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007a8f8  push    rbp
0x18007a8fa  push    rbx
0x18007a8fb  push    rsi
0x18007a8fc  push    rdi
0x18007a8fd  push    r14
0x18007a8ff  push    r15
0x18007a901  lea     rbp, [rsp-2Fh]
0x18007a906  sub     rsp, 98h
0x18007a90d  mov     rax, cs:__security_cookie
0x18007a914  xor     rax, rsp
0x18007a917  mov     [rbp+57h+var_40], rax
0x18007a91b  mov     r14, r9
0x18007a91e  mov     rsi, r8
0x18007a921  mov     rdi, rcx
0x18007a924  xor     r15d, r15d
0x18007a927  mov     [rbp+57h+pszStr1], r15
0x18007a92b  mov     [rbp+57h+var_50], r15
0x18007a92f  mov     [rbp+57h+var_48], r15
0x18007a933  lea     r8, [rbp+57h+pszStr1]
0x18007a937  call    ?FormatForDisplay@CFormatForDisplay@@QEAAJAEBUtagPROPVARIANT@@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; CFormatForDisplay::FormatForDisplay(tagPROPVARIANT const &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x18007a93c  mov     ebx, eax
0x18007a93e  test    eax, eax
0x18007a940  js      loc_18007AA82
0x18007a946  mov     [rbp+57h+pszStr2], r15
0x18007a94a  mov     [rbp+57h+var_68], r15
0x18007a94e  mov     [rbp+57h+var_60], r15
0x18007a952  lea     r8, [rbp+57h+pszStr2]
0x18007a956  mov     rdx, rsi
0x18007a959  mov     rcx, rdi
0x18007a95c  call    ?FormatForDisplay@CFormatForDisplay@@QEAAJAEBUtagPROPVARIANT@@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; CFormatForDisplay::FormatForDisplay(tagPROPVARIANT const &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x18007a961  mov     ebx, eax
0x18007a963  test    eax, eax
0x18007a965  js      loc_18007AA78
0x18007a96b  mov     rdi, [rbp+57h+pszStr1]
0x18007a96f  test    rdi, rdi
0x18007a972  jnz     short loc_18007A996
0x18007a974  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007a978  lea     rdx, Src
0x18007a97f  lea     rcx, [rbp+57h+pszStr1]
0x18007a983  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18007a988  mov     ebx, eax
0x18007a98a  test    eax, eax
0x18007a98c  js      loc_18007AA78
0x18007a992  mov     rdi, [rbp+57h+pszStr1]
0x18007a996  mov     [rbp+57h+pszStr1], r15
0x18007a99a  mov     [rbp+57h+var_48], r15
0x18007a99e  mov     [rbp+57h+var_50], r15
0x18007a9a2  mov     rsi, [rbp+57h+pszStr2]
0x18007a9a6  test    rsi, rsi
0x18007a9a9  jnz     short loc_18007A9CD
0x18007a9ab  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007a9af  lea     rdx, Src
0x18007a9b6  lea     rcx, [rbp+57h+pszStr2]
0x18007a9ba  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18007a9bf  mov     ebx, eax
0x18007a9c1  test    eax, eax
0x18007a9c3  js      loc_18007AA6E
0x18007a9c9  mov     rsi, [rbp+57h+pszStr2]
0x18007a9cd  mov     [rbp+57h+pszStr2], r15
0x18007a9d1  mov     [rbp+57h+var_60], r15
0x18007a9d5  mov     [rbp+57h+var_68], r15
0x18007a9d9  mov     rdx, rsi; pszStr2
0x18007a9dc  mov     rcx, rdi; pszStr1
0x18007a9df  call    cs:__imp_StrCmpICW
0x18007a9e5  test    eax, eax
0x18007a9e7  jnz     short loc_18007A9F8
0x18007a9e9  mov     rdx, rdi
0x18007a9ec  mov     rcx, r14
0x18007a9ef  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18007a9f4  mov     ebx, eax
0x18007a9f6  jmp     short loc_18007AA65
0x18007a9f8  mov     [rbp+57h+var_88], r15
0x18007a9fc  mov     [rbp+57h+var_80], r15
0x18007aa00  mov     [rbp+57h+var_78], r15
0x18007aa04  mov     r8d, 0C4h
0x18007aa0a  mov     rdx, cs:?g_hModMUIResources@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hModMUIResources
0x18007aa11  lea     rcx, [rbp+57h+var_88]
0x18007aa15  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x18007aa1a  mov     ebx, eax
0x18007aa1c  test    eax, eax
0x18007aa1e  js      short loc_18007AA5C
0x18007aa20  mov     [rbp+57h+var_A0], r15
0x18007aa24  mov     [rbp+57h+var_98], r15
0x18007aa28  mov     [rbp+57h+var_90], r15
0x18007aa2c  mov     r9, rsi
0x18007aa2f  mov     r8, rdi
0x18007aa32  mov     rdx, [rbp+57h+var_88]
0x18007aa36  lea     rcx, [rbp+57h+var_A0]
0x18007aa3a  call    ?InitializeMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeMessage(ushort const *,...)
0x18007aa3f  mov     ebx, eax
0x18007aa41  test    eax, eax
0x18007aa43  js      short loc_18007AA53
0x18007aa45  mov     rdx, [rbp+57h+var_A0]
0x18007aa49  mov     rcx, r14
0x18007aa4c  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18007aa51  mov     ebx, eax
0x18007aa53  lea     rcx, [rbp+57h+var_A0]
0x18007aa57  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18007aa5c  lea     rcx, [rbp+57h+var_88]
0x18007aa60  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18007aa65  mov     rcx, rsi; pv
0x18007aa68  call    cs:__imp_CoTaskMemFree
0x18007aa6e  mov     rcx, rdi; pv
0x18007aa71  call    cs:__imp_CoTaskMemFree
0x18007aa77  nop
0x18007aa78  lea     rcx, [rbp+57h+pszStr2]
0x18007aa7c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18007aa81  nop
0x18007aa82  lea     rcx, [rbp+57h+pszStr1]
0x18007aa86  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18007aa8b  mov     eax, ebx
0x18007aa8d  mov     rcx, [rbp+57h+var_40]
0x18007aa91  xor     rcx, rsp; StackCookie
0x18007aa94  call    __security_check_cookie
0x18007aa99  add     rsp, 98h
0x18007aaa0  pop     r15
0x18007aaa2  pop     r14
0x18007aaa4  pop     rdi
0x18007aaa5  pop     rsi
0x18007aaa6  pop     rbx
0x18007aaa7  pop     rbp
0x18007aaa8  retn
```
