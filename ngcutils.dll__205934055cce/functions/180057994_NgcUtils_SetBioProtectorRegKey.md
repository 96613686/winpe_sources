# NgcUtils::SetBioProtectorRegKey

- ea: `0x180057994`
- end: `0x180057be5`
- name: `NgcUtils::SetBioProtectorRegKey`
- size: `593`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180057bec`

## callees

- `0x18000113c`
- `0x180001464`
- `0x180003080`
- `0x18000ce74`
- `0x180014e34`
- `0x180056728`
- `0x1800578c0`
- `0x180057994`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057a27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057a27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057ae4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057ae4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057a45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057ab4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057bb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057a45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057ab4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057bb9`

## string_xrefs

- `0x180057ad9`: `ProtectorUpdateNeeded`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcUtils::SetBioProtectorRegKey(void *a1)
{
  __int64 v2; // rdx
  int RedirectedWinBioAccontInfoRegPath; // esi
  __int64 v4; // r8
  const WCHAR *v5; // rdx
  LSTATUS v6; // eax
  int v7; // ebx
  char *v8; // rdx
  int v9; // ecx
  int v10; // r9d
  int *v11; // rax
  char *v12; // rdx
  int *v14; // [rsp+30h] [rbp-59h]
  int v15; // [rsp+40h] [rbp-49h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-41h] BYREF
  int v17; // [rsp+50h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-31h] BYREF
  void *v19; // [rsp+60h] [rbp-29h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+68h] [rbp-21h] BYREF
  __m128i si128; // [rsp+78h] [rbp-11h]
  char v22[32]; // [rsp+88h] [rbp-1h] BYREF
  int *v23; // [rsp+A8h] [rbp+1Fh]
  __int64 v24; // [rsp+B0h] [rbp+27h]

  *(_DWORD *)Data = 1;
  *(_OWORD *)lpSubKey = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpSubKey[0]) = 0;
  RedirectedWinBioAccontInfoRegPath = anonymous_namespace_::GetRedirectedWinBioAccontInfoRegPath(lpSubKey);
  if ( RedirectedWinBioAccontInfoRegPath < 0 )
  {
LABEL_29:
    v7 = RedirectedWinBioAccontInfoRegPath;
    goto LABEL_30;
  }
  std::wstring::append(lpSubKey, a1);
  hKey = 0;
  v5 = (const WCHAR *)lpSubKey;
  if ( si128.m128i_i64[1] > 7uLL )
    v5 = lpSubKey[0];
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20006u, &hKey);
  v7 = v6;
  if ( !v6 )
  {
    v7 = RegSetValueExW(hKey, L"ProtectorUpdateNeeded", 0, 4u, Data, 4u);
    if ( v7 )
    {
      if ( (unsigned int)dword_180075000 <= 2 )
        goto LABEL_12;
      v8 = byte_18006A2F5;
      goto LABEL_11;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned int)dword_180075000 <= 5
        || (v9 = qword_180075018, v2 = 0x400000000000LL, (qword_180075010 & 0x400000000000LL) == 0)
        || (qword_180075018 & 0x400000000000LL) != qword_180075018 )
      {
LABEL_27:
        if ( hKey )
          RegCloseKey(hKey);
        goto LABEL_29;
      }
      v15 = *(_DWORD *)Data;
      v17 = RedirectedWinBioAccontInfoRegPath;
      v14 = &v15;
      v11 = &v17;
      v12 = byte_18006A2B1;
    }
    else
    {
      if ( (unsigned int)dword_180075000 <= 4 )
        goto LABEL_27;
      v17 = *(_DWORD *)Data;
      v15 = RedirectedWinBioAccontInfoRegPath;
      v14 = &v17;
      v11 = &v15;
      v12 = byte_18006A333;
    }
    v19 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v9,
      (_DWORD)v12,
      v4,
      v10,
      (__int64)v11,
      (__int64)&v19,
      (__int64)v14);
    goto LABEL_27;
  }
  if ( v6 == 2 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    v7 = 0;
    goto LABEL_30;
  }
  if ( (unsigned int)dword_180075000 > 2 )
  {
    v8 = byte_18006A375;
LABEL_11:
    v23 = &v15;
    v15 = v7;
    v24 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180075000, v8, 0, 0, 3, v22);
  }
LABEL_12:
  if ( v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80070000;
  if ( hKey )
    RegCloseKey(hKey);
LABEL_30:
  std::wstring::~wstring(lpSubKey, v2, v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180057994  push    rbp
0x180057996  push    rbx
0x180057997  push    rsi
0x180057998  push    r14
0x18005799a  lea     rbp, [rsp-3Fh]
0x18005799f  sub     rsp, 0C8h
0x1800579a6  mov     rax, cs:__security_cookie
0x1800579ad  xor     rax, rsp
0x1800579b0  mov     [rbp+57h+var_28], rax
0x1800579b4  mov     r14, rcx
0x1800579b7  mov     dword ptr [rbp+57h+Data], 1
0x1800579be  xorps   xmm0, xmm0
0x1800579c1  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x1800579c5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800579cd  movdqu  [rbp+57h+var_68], xmm1
0x1800579d2  xor     eax, eax
0x1800579d4  mov     word ptr [rbp+57h+lpSubKey], ax
0x1800579d8  lea     rcx, [rbp+57h+lpSubKey]
0x1800579dc  call    _anonymous_namespace___GetRedirectedWinBioAccontInfoRegPath
0x1800579e1  mov     esi, eax
0x1800579e3  test    eax, eax
0x1800579e5  js      loc_180057BBF
0x1800579eb  mov     rdx, r14; void *
0x1800579ee  lea     rcx, [rbp+57h+lpSubKey]; Src
0x1800579f2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800579f7  nop
0x1800579f8  mov     [rbp+57h+hKey], 0
0x180057a00  lea     rdx, [rbp+57h+lpSubKey]
0x180057a04  cmp     qword ptr [rbp+57h+var_68+8], 7
0x180057a09  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180057a0e  lea     rax, [rbp+57h+hKey]
0x180057a12  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180057a17  mov     r9d, 20006h; samDesired
0x180057a1d  xor     r8d, r8d; ulOptions
0x180057a20  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180057a27  call    cs:__imp_RegOpenKeyExW
0x180057a2d  mov     ebx, eax
0x180057a2f  test    eax, eax
0x180057a31  jz      loc_180057ABF
0x180057a37  cmp     eax, 2
0x180057a3a  jnz     short loc_180057A52
0x180057a3c  mov     rcx, [rbp+57h+hKey]; hKey
0x180057a40  test    rcx, rcx
0x180057a43  jz      short loc_180057A4B
0x180057a45  call    cs:__imp_RegCloseKey
0x180057a4b  xor     ebx, ebx
0x180057a4d  jmp     loc_180057BC1
0x180057a52  mov     eax, cs:dword_180075000
0x180057a58  cmp     eax, 2
0x180057a5b  jbe     short loc_180057A9A
0x180057a5d  lea     rdx, byte_18006A375
0x180057a64  lea     rax, [rbp+57h+var_A0]
0x180057a68  mov     [rbp+57h+var_38], rax
0x180057a6c  lea     rax, [rbp+57h+var_58]
0x180057a70  mov     qword ptr [rsp+0E0h+cbData], rax
0x180057a75  mov     dword ptr [rsp+0E0h+phkResult], 3
0x180057a7d  mov     [rbp+57h+var_A0], ebx
0x180057a80  mov     [rbp+57h+var_30], 4
0x180057a88  xor     r9d, r9d
0x180057a8b  xor     r8d, r8d
0x180057a8e  lea     rcx, dword_180075000
0x180057a95  call    _tlgWriteTransfer_EventWriteTransfer
0x180057a9a  test    ebx, ebx
0x180057a9c  jle     short loc_180057AA7
0x180057a9e  movzx   ebx, bx
0x180057aa1  or      ebx, 80070000h
0x180057aa7  mov     rcx, [rbp+57h+hKey]; hKey
0x180057aab  test    rcx, rcx
0x180057aae  jz      loc_180057BC1
0x180057ab4  call    cs:__imp_RegCloseKey
0x180057aba  jmp     loc_180057BC1
0x180057abf  mov     [rsp+0E0h+cbData], 4; cbData
0x180057ac7  lea     rax, [rbp+57h+Data]
0x180057acb  mov     [rsp+0E0h+phkResult], rax; lpData
0x180057ad0  mov     r9d, 4; dwType
0x180057ad6  xor     r8d, r8d; Reserved
0x180057ad9  lea     rdx, aProtectorupdat; "ProtectorUpdateNeeded"
0x180057ae0  mov     rcx, [rbp+57h+hKey]; hKey
0x180057ae4  call    cs:__imp_RegSetValueExW
0x180057aea  mov     ebx, eax
0x180057aec  test    eax, eax
0x180057aee  jz      short loc_180057B07
0x180057af0  mov     eax, cs:dword_180075000
0x180057af6  cmp     eax, 2
0x180057af9  jbe     short loc_180057A9A
0x180057afb  lea     rdx, byte_18006A2F5
0x180057b02  jmp     loc_180057A64
0x180057b07  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x180057b0e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x180057b13  test    al, al
0x180057b15  mov     eax, cs:dword_180075000
0x180057b1b  jz      short loc_180057B76
0x180057b1d  cmp     eax, 5
0x180057b20  jbe     loc_180057BB0
0x180057b26  mov     rcx, cs:qword_180075018
0x180057b2d  mov     rax, cs:qword_180075010
0x180057b34  mov     rdx, 400000000000h
0x180057b3e  test    rdx, rax
0x180057b41  jz      short loc_180057BB0
0x180057b43  mov     rax, rcx
0x180057b46  and     rax, rdx
0x180057b49  cmp     rax, rcx
0x180057b4c  jnz     short loc_180057BB0
0x180057b4e  mov     eax, dword ptr [rbp+57h+Data]
0x180057b51  mov     [rbp+57h+var_A0], eax
0x180057b54  mov     [rbp+57h+var_90], esi
0x180057b57  lea     rax, [rbp+57h+var_A0]
0x180057b5b  mov     [rsp+0E0h+var_B0], rax
0x180057b60  lea     rax, [rbp+57h+var_80]
0x180057b64  mov     qword ptr [rsp+0E0h+cbData], rax
0x180057b69  lea     rax, [rbp+57h+var_90]
0x180057b6d  lea     rdx, byte_18006A2B1
0x180057b74  jmp     short loc_180057BA1
0x180057b76  cmp     eax, 4
0x180057b79  jbe     short loc_180057BB0
0x180057b7b  mov     eax, dword ptr [rbp+57h+Data]
0x180057b7e  mov     [rbp+57h+var_90], eax
0x180057b81  mov     [rbp+57h+var_A0], esi
0x180057b84  lea     rax, [rbp+57h+var_90]
0x180057b88  mov     [rsp+0E0h+var_B0], rax
0x180057b8d  lea     rax, [rbp+57h+var_80]
0x180057b91  mov     qword ptr [rsp+0E0h+cbData], rax
0x180057b96  lea     rax, [rbp+57h+var_A0]
0x180057b9a  lea     rdx, byte_18006A333
0x180057ba1  mov     [rsp+0E0h+phkResult], rax
0x180057ba6  mov     [rbp+57h+var_80], r14
0x180057baa  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180057baf  nop
0x180057bb0  mov     rcx, [rbp+57h+hKey]; hKey
0x180057bb4  test    rcx, rcx
0x180057bb7  jz      short loc_180057BBF
0x180057bb9  call    cs:__imp_RegCloseKey
0x180057bbf  mov     ebx, esi
0x180057bc1  lea     rcx, [rbp+57h+lpSubKey]
0x180057bc5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180057bca  mov     eax, ebx
0x180057bcc  mov     rcx, [rbp+57h+var_28]
0x180057bd0  xor     rcx, rsp; StackCookie
0x180057bd3  call    __security_check_cookie
0x180057bd8  add     rsp, 0C8h
0x180057bdf  pop     r14
0x180057be1  pop     rsi
0x180057be2  pop     rbx
0x180057be3  pop     rbp
0x180057be4  retn
```
