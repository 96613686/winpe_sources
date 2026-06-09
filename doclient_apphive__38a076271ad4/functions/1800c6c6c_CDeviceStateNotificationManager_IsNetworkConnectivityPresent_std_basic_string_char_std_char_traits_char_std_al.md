# CDeviceStateNotificationManager::IsNetworkConnectivityPresent(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &,bool &)

- ea: `0x1800c6c6c`
- end: `0x1800c71b2`
- name: `?IsNetworkConnectivityPresent@CDeviceStateNotificationManager@@SA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEA_N@Z`
- size: `1350`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009942c`

## callees

- `0x180008d14`
- `0x180008fb8`
- `0x1800095a0`
- `0x1800179a4`
- `0x18003ae04`
- `0x18003aebc`
- `0x18003af9c`
- `0x18003eedc`
- `0x180043d28`
- `0x18005125c`
- `0x18007cf1c`
- `0x1800a1ea4`
- `0x1800a98f8`
- `0x1800c6c6c`
- `0x1800c79e4`
- `0x1800c81dc`
- `0x1800f82f0`
- `0x1800f8320`
- `0x180108e50`
- `0x180108ed0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c6ce0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c6ce0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6fd9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6fd9`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6e94`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6eb3`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6ef4`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6e94`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6eb3`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6ef4`
- `OLEAUT32!__imp_VariantClear` at `0x1800c6ea9`
- `OLEAUT32!__imp_VariantClear` at `0x1800c6eea`
- `OLEAUT32!__imp_VariantClear` at `0x1800c6fa5`
- `OLEAUT32!__imp_VariantClear` at `0x1800c6ea9`
- `OLEAUT32!__imp_VariantClear` at `0x1800c6eea`
- `OLEAUT32!__imp_VariantClear` at `0x1800c6fa5`

## string_xrefs

- `0x1800c6ced`: `Failed to CoCreate NLM`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int8 __fastcall CDeviceStateNotificationManager::IsNetworkConnectivityPresent(
        const char *a1,
        unsigned __int8 *a2)
{
  const char *v3; // r14
  const char *v4; // rax
  unsigned __int8 v5; // r15
  unsigned int v6; // eax
  int v7; // eax
  char v8; // al
  unsigned int v9; // eax
  _QWORD *v10; // rax
  __int64 v11; // rbx
  unsigned int (__fastcall *v12)(__int64, __int64, _QWORD **); // rdi
  _QWORD *v13; // rcx
  __int64 (__fastcall **v14)(_QWORD *, GUID *, _QWORD *); // rax
  int v15; // eax
  unsigned int v16; // eax
  __int64 v17; // rbx
  int (__fastcall *v18)(__int64, const wchar_t *, VARIANTARG *, _QWORD); // rdi
  BYTE bVal; // si
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, const wchar_t *, VARIANTARG *, _QWORD); // rdi
  int v22; // eax
  BYTE v23; // cl
  __int64 v24; // rax
  char *v25; // rdx
  __int64 v26; // rcx
  __int64 *v27; // rbx
  _QWORD *v28; // rdi
  _QWORD *v29; // rax
  __int64 **v30; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v33; // rax
  _QWORD *v34; // rcx
  __int64 v35; // rcx
  LPVOID v36; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  const char *v40; // [rsp+28h] [rbp-D8h]
  const char *v41; // [rsp+28h] [rbp-D8h]
  const char *v42; // [rsp+28h] [rbp-D8h]
  _BYTE v43[32]; // [rsp+40h] [rbp-C0h] BYREF
  char v44; // [rsp+60h] [rbp-A0h] BYREF
  char v45; // [rsp+70h] [rbp-90h] BYREF
  __int16 v46; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v47; // [rsp+88h] [rbp-78h] BYREF
  __int64 v48; // [rsp+90h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-68h] BYREF
  LPVOID v50; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v51; // [rsp+A8h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v53[3]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v54[32]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v3 = a1;
  *((_QWORD *)a1 + 2) = 0;
  v4 = a1;
  if ( *((_QWORD *)a1 + 3) > 0xFu )
    v4 = *(const char **)a1;
  *v4 = 0;
  *a2 = 1;
  v5 = 1;
  v50 = 0;
  v6 = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b, &v50);
  if ( wil::details::in1diag3::Log_IfFailedMsg(
         retaddr,
         (void *)0x9B,
         (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\DeviceStateNotificationManager.cpp",
         (const char *)v6,
         (int)"Failed to CoCreate NLM",
         v40) < 0 )
    goto LABEL_54;
  v46 = 0;
  v7 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)v50 + 96LL))(v50, &v46);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\DeviceStateNotificationManager.cpp",
      (const char *)(unsigned int)v7,
      ppv);
LABEL_7:
    v8 = 0;
    goto LABEL_8;
  }
  v8 = 1;
  if ( v46 != -1 )
    goto LABEL_7;
LABEL_8:
  *a2 = v8;
  v51 = 0;
  v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v50 + 56LL))(v50, 1, &v51);
  if ( wil::details::in1diag3::Log_IfFailedMsg(
         retaddr,
         (void *)0xA4,
         (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\DeviceStateNotificationManager.cpp",
         (const char *)v9,
         (int)"NLM->GetNetworks failed",
         v41) < 0 )
    goto LABEL_52;
  v5 = 0;
  v53[1] = 0;
  v10 = operator new(0x40u);
  *v10 = v10;
  v10[1] = v10;
  v10[2] = v10;
  *((_WORD *)v10 + 12) = 257;
  v53[0] = v10;
  v47 = 0;
  while ( 1 )
  {
    v11 = v51;
    v12 = *(unsigned int (__fastcall **)(__int64, __int64, _QWORD **))(*(_QWORD *)v51 + 64LL);
    v13 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v13 + 16LL))(v13);
    }
    if ( v12(v11, 1, &v47) )
      break;
    v14 = (__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD *))*v47;
    bstrString = 0;
    v15 = ((__int64 (__fastcall *)(_QWORD *, BSTR *))v14[7])(v47, &bstrString);
    if ( v15 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB0,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\DeviceStateNotificationManager.cpp",
        (const char *)(unsigned int)v15,
        ppva);
    v48 = 0;
    v16 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v47)(
            v47,
            &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
            &v48);
    if ( wil::details::in1diag3::Log_IfFailedMsg(
           retaddr,
           (void *)0xB3,
           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\DeviceStateNotificationManager.cpp",
           (const char *)v16,
           (int)"Failed to QI for IPropertyBag",
           v42) >= 0 )
    {
      VariantInit(&pvarg);
      v17 = v48;
      v18 = *(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v48 + 24LL);
      VariantClear(&pvarg);
      VariantInit(&pvarg);
      bVal = 0;
      if ( v18(v17, L"NA_InternetConnectivityV4", &pvarg, 0) >= 0 )
        bVal = pvarg.bVal;
      v20 = v48;
      v21 = *(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v48 + 24LL);
      VariantClear(&pvarg);
      VariantInit(&pvarg);
      v22 = v21(v20, L"NA_InternetConnectivityV6", &pvarg, 0);
      v23 = 0;
      if ( v22 >= 0 )
        v23 = pvarg.bVal;
      if ( ((bVal | v23) & 1) != 0 )
      {
        LogMessage(
          4u,
          "CDeviceStateNotificationManager::IsNetworkConnectivityPresent",
          0xCEu,
          "Captive Portal detected on network '%ls'",
          bstrString);
        if ( *a2 && bstrString )
        {
          v24 = WstrToUTF8(v43, bstrString, 0);
          v25 = &v45;
LABEL_26:
          std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::_Emplace<std::string>(
            v53,
            v25,
            v24);
          std::string::~string(v43);
        }
      }
      else
      {
        v5 = 1;
        if ( bstrString )
        {
          v24 = WstrToUTF8(v43, bstrString, 0);
          v25 = &v44;
          goto LABEL_26;
        }
      }
      VariantClear(&pvarg);
    }
    v26 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    if ( bstrString )
      SysFreeString(bstrString);
  }
  if ( v5 || *a2 )
  {
    memset(v54, 0, 0xF8u);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v54);
    v27 = *(__int64 **)v53[0];
    while ( !*((_BYTE *)v27 + 25) )
    {
      v28 = v27 + 4;
      v29 = (_QWORD *)std::ostream::tellp(&v54[2], &pvarg);
      if ( *v29 + v29[1] )
        std::operator<<<std::char_traits<char>>(&v54[2], ";");
      if ( (unsigned __int64)v27[7] > 0xF )
        v28 = (_QWORD *)*v28;
      std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(&v54[2], v28, v27[6]);
      v30 = (__int64 **)v27[2];
      if ( *((_BYTE *)v30 + 25) )
      {
        for ( i = (__int64 *)v27[1]; !*((_BYTE *)i + 25) && v27 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v27 = i;
        v27 = i;
      }
      else
      {
        v27 = (__int64 *)v27[2];
        for ( j = *v30; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v27 = j;
      }
    }
    v33 = std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::str(v54, v43);
    std::string::operator=(v3, v33);
    std::string::~string(v43);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(&v54[19]);
    v54[19] = &std::ios::`vftable';
    std::ios_base::~ios_base((std::ios_base *)&v54[19]);
  }
  v34 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
  }
  std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::~_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>(v53);
LABEL_52:
  v35 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
LABEL_54:
  if ( *((_QWORD *)v3 + 3) > 0xFu )
    v3 = *(const char **)v3;
  LogMessage(
    5u,
    "CDeviceStateNotificationManager::IsNetworkConnectivityPresent",
    0xF2u,
    "fInternetConnectivity = %u, fBasicConnectivity = %u, name = '%s'",
    v5,
    *a2,
    v3);
  v36 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
  }
  return v5;
}

```

## disassembly

```asm
0x1800c6c6c  mov     [rsp-8+arg_10], rbx
0x1800c6c71  push    rbp
0x1800c6c72  push    rsi
0x1800c6c73  push    rdi
0x1800c6c74  push    r12
0x1800c6c76  push    r13
0x1800c6c78  push    r14
0x1800c6c7a  push    r15
0x1800c6c7c  lea     rbp, [rsp-0F0h]
0x1800c6c84  sub     rsp, 1F0h
0x1800c6c8b  mov     rax, cs:__security_cookie
0x1800c6c92  xor     rax, rsp
0x1800c6c95  mov     [rbp+120h+var_40], rax
0x1800c6c9c  mov     r12, rdx
0x1800c6c9f  mov     r14, rcx
0x1800c6ca2  xor     r13d, r13d
0x1800c6ca5  mov     [rcx+10h], r13
0x1800c6ca9  mov     rax, rcx
0x1800c6cac  cmp     qword ptr [rcx+18h], 0Fh
0x1800c6cb1  jbe     short loc_1800C6CB6
0x1800c6cb3  mov     rax, [rcx]
0x1800c6cb6  mov     [rax], r13b
0x1800c6cb9  mov     byte ptr [rdx], 1
0x1800c6cbc  mov     r15b, 1
0x1800c6cbf  mov     [rbp+120h+var_180], r13
0x1800c6cc3  lea     rax, [rbp+120h+var_180]
0x1800c6cc7  mov     [rsp+220h+ppv], rax; ppv
0x1800c6ccc  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x1800c6cd3  xor     edx, edx; pUnkOuter
0x1800c6cd5  lea     r8d, [rdx+1]; dwClsContext
0x1800c6cd9  lea     rcx, CLSID_NetworkListManager; rclsid
0x1800c6ce0  call    cs:__imp_CoCreateInstance
0x1800c6ce6  mov     rcx, [rbp+128h]; this
0x1800c6ced  lea     rdx, aFailedToCocrea; "Failed to CoCreate NLM"
0x1800c6cf4  mov     [rsp+220h+ppv], rdx; int
0x1800c6cf9  mov     r9d, eax; char *
0x1800c6cfc  lea     rsi, aCW1SSrcDeliver_80; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c6d03  mov     r8, rsi; unsigned int
0x1800c6d06  mov     edx, 9Bh; void *
0x1800c6d0b  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800c6d10  test    eax, eax
0x1800c6d12  js      loc_1800C712C
0x1800c6d18  mov     [rbp+120h+var_1A0], r13w
0x1800c6d1d  mov     rcx, [rbp+120h+var_180]
0x1800c6d21  mov     rax, [rcx]
0x1800c6d24  lea     rdx, [rbp+120h+var_1A0]
0x1800c6d28  mov     rax, [rax+60h]
0x1800c6d2c  call    _guard_dispatch_icall
0x1800c6d31  mov     rcx, [rbp+128h]; this
0x1800c6d38  test    eax, eax
0x1800c6d3a  jns     short loc_1800C6D4E
0x1800c6d3c  mov     r9d, eax; char *
0x1800c6d3f  mov     r8, rsi; unsigned int
0x1800c6d42  mov     edx, 9Fh; void *
0x1800c6d47  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c6d4c  jmp     short loc_1800C6D57
0x1800c6d4e  cmp     [rbp+120h+var_1A0], 0FFFFh
0x1800c6d53  mov     al, 1
0x1800c6d55  jz      short loc_1800C6D5A
0x1800c6d57  mov     al, r13b
0x1800c6d5a  mov     [r12], al
0x1800c6d5e  mov     [rbp+120h+var_178], r13
0x1800c6d62  mov     rcx, [rbp+120h+var_180]
0x1800c6d66  mov     rax, [rcx]
0x1800c6d69  lea     r8, [rbp+120h+var_178]
0x1800c6d6d  mov     edx, 1
0x1800c6d72  mov     rax, [rax+38h]
0x1800c6d76  call    _guard_dispatch_icall
0x1800c6d7b  mov     rcx, [rbp+128h]; this
0x1800c6d82  lea     rdx, aNlmGetnetworks; "NLM->GetNetworks failed"
0x1800c6d89  mov     [rsp+220h+ppv], rdx; int
0x1800c6d8e  mov     r9d, eax; char *
0x1800c6d91  mov     r8, rsi; unsigned int
0x1800c6d94  mov     edx, 0A4h; void *
0x1800c6d99  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800c6d9e  test    eax, eax
0x1800c6da0  js      loc_1800C7112
0x1800c6da6  mov     r15b, r13b
0x1800c6da9  mov     [rbp+120h+var_150], r13
0x1800c6dad  mov     ecx, 40h ; '@'; Size
0x1800c6db2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c6db7  mov     [rax], rax
0x1800c6dba  mov     [rax+8], rax
0x1800c6dbe  mov     [rax+10h], rax
0x1800c6dc2  mov     word ptr [rax+18h], 101h
0x1800c6dc8  mov     [rbp+120h+var_158], rax
0x1800c6dcc  mov     [rbp+120h+var_198], r13
0x1800c6dd0  mov     rbx, [rbp+120h+var_178]
0x1800c6dd4  mov     rax, [rbx]
0x1800c6dd7  mov     rdi, [rax+40h]
0x1800c6ddb  mov     rcx, [rbp+120h+var_198]
0x1800c6ddf  test    rcx, rcx
0x1800c6de2  jz      short loc_1800C6DF5
0x1800c6de4  mov     [rbp+120h+var_198], r13
0x1800c6de8  mov     rax, [rcx]
0x1800c6deb  mov     rax, [rax+10h]
0x1800c6def  call    _guard_dispatch_icall
0x1800c6df4  nop
0x1800c6df5  xor     r9d, r9d
0x1800c6df8  lea     r8, [rbp+120h+var_198]
0x1800c6dfc  lea     edx, [r9+1]
0x1800c6e00  mov     rcx, rbx
0x1800c6e03  mov     rax, rdi
0x1800c6e06  call    _guard_dispatch_icall
0x1800c6e0b  test    eax, eax
0x1800c6e0d  jnz     loc_1800C6FE4
0x1800c6e13  mov     rcx, [rbp+120h+var_198]
0x1800c6e17  mov     rax, [rcx]
0x1800c6e1a  mov     [rbp+120h+bstrString], r13
0x1800c6e1e  lea     rdx, [rbp+120h+bstrString]
0x1800c6e22  mov     rax, [rax+38h]
0x1800c6e26  call    _guard_dispatch_icall
0x1800c6e2b  mov     rcx, [rbp+128h]; this
0x1800c6e32  test    eax, eax
0x1800c6e34  jns     short loc_1800C6E46
0x1800c6e36  mov     r9d, eax; char *
0x1800c6e39  mov     r8, rsi; unsigned int
0x1800c6e3c  mov     edx, 0B0h; void *
0x1800c6e41  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c6e46  mov     [rbp+120h+var_190], r13
0x1800c6e4a  mov     rcx, [rbp+120h+var_198]
0x1800c6e4e  mov     rax, [rcx]
0x1800c6e51  lea     r8, [rbp+120h+var_190]
0x1800c6e55  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x1800c6e5c  mov     rax, [rax]
0x1800c6e5f  call    _guard_dispatch_icall
0x1800c6e64  nop
0x1800c6e65  mov     rcx, [rbp+128h]; this
0x1800c6e6c  lea     rdx, aFailedToQiForI; "Failed to QI for IPropertyBag"
0x1800c6e73  mov     [rsp+220h+ppv], rdx; int
0x1800c6e78  mov     r9d, eax; char *
0x1800c6e7b  mov     r8, rsi; unsigned int
0x1800c6e7e  mov     edx, 0B3h; void *
0x1800c6e83  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800c6e88  test    eax, eax
0x1800c6e8a  js      loc_1800C6FB2
0x1800c6e90  lea     rcx, [rbp+120h+pvarg]; pvarg
0x1800c6e94  call    cs:__imp_VariantInit
0x1800c6e9a  mov     rbx, [rbp+120h+var_190]
0x1800c6e9e  mov     rax, [rbx]
0x1800c6ea1  mov     rdi, [rax+18h]
0x1800c6ea5  lea     rcx, [rbp+120h+pvarg]; pvarg
0x1800c6ea9  call    cs:__imp_VariantClear
0x1800c6eaf  lea     rcx, [rbp+120h+pvarg]; pvarg
0x1800c6eb3  call    cs:__imp_VariantInit
0x1800c6eb9  xor     r9d, r9d
0x1800c6ebc  lea     r8, [rbp+120h+pvarg]
0x1800c6ec0  lea     rdx, aNaInternetconn_0; "NA_InternetConnectivityV4"
0x1800c6ec7  mov     rcx, rbx
0x1800c6eca  mov     rax, rdi
0x1800c6ecd  call    _guard_dispatch_icall
0x1800c6ed2  mov     esi, r13d
0x1800c6ed5  test    eax, eax
0x1800c6ed7  cmovns  esi, dword ptr [rbp+120h+pvarg+8]
0x1800c6edb  mov     rbx, [rbp+120h+var_190]
0x1800c6edf  mov     rax, [rbx]
0x1800c6ee2  mov     rdi, [rax+18h]
0x1800c6ee6  lea     rcx, [rbp+120h+pvarg]; pvarg
0x1800c6eea  call    cs:__imp_VariantClear
0x1800c6ef0  lea     rcx, [rbp+120h+pvarg]; pvarg
0x1800c6ef4  call    cs:__imp_VariantInit
0x1800c6efa  xor     r9d, r9d
0x1800c6efd  lea     r8, [rbp+120h+pvarg]
0x1800c6f01  lea     rdx, aNaInternetconn; "NA_InternetConnectivityV6"
0x1800c6f08  mov     rcx, rbx
0x1800c6f0b  mov     rax, rdi
0x1800c6f0e  call    _guard_dispatch_icall
0x1800c6f13  mov     ecx, r13d
0x1800c6f16  test    eax, eax
0x1800c6f18  cmovns  ecx, dword ptr [rbp+120h+pvarg+8]
0x1800c6f1c  or      ecx, esi
0x1800c6f1e  test    cl, 1
0x1800c6f21  jnz     short loc_1800C6F43
0x1800c6f23  mov     r15b, 1
0x1800c6f26  mov     rdx, [rbp+120h+bstrString]
0x1800c6f2a  test    rdx, rdx
0x1800c6f2d  jz      short loc_1800C6FA1
0x1800c6f2f  xor     r8d, r8d
0x1800c6f32  lea     rcx, [rsp+220h+var_1E0]
0x1800c6f37  call    ?WstrToUTF8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEB_W_K@Z; WstrToUTF8(wchar_t const *,unsigned __int64)
0x1800c6f3c  lea     rdx, [rsp+220h+var_1C0]
0x1800c6f41  jmp     short loc_1800C6F8B
0x1800c6f43  mov     rax, [rbp+120h+bstrString]
0x1800c6f47  mov     [rsp+220h+ppv], rax
0x1800c6f4c  lea     r9, aCaptivePortalD; "Captive Portal detected on network '%ls"...
0x1800c6f53  mov     r8d, 0CEh; unsigned int
0x1800c6f59  lea     rdx, aCdevicestateno; "CDeviceStateNotificationManager::IsNetw"...
0x1800c6f60  mov     ecx, 4; unsigned __int8
0x1800c6f65  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800c6f6a  cmp     [r12], r13b
0x1800c6f6e  jz      short loc_1800C6FA1
0x1800c6f70  mov     rdx, [rbp+120h+bstrString]
0x1800c6f74  test    rdx, rdx
0x1800c6f77  jz      short loc_1800C6FA1
0x1800c6f79  xor     r8d, r8d
0x1800c6f7c  lea     rcx, [rsp+220h+var_1E0]
0x1800c6f81  call    ?WstrToUTF8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEB_W_K@Z; WstrToUTF8(wchar_t const *,unsigned __int64)
0x1800c6f86  lea     rdx, [rsp+220h+var_1B0]
0x1800c6f8b  mov     r8, rax
0x1800c6f8e  lea     rcx, [rbp+120h+var_158]
0x1800c6f92  call    ??$_Emplace@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::_Emplace<std::string>(std::string &&)
0x1800c6f97  lea     rcx, [rsp+220h+var_1E0]; void *
0x1800c6f9c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800c6fa1  lea     rcx, [rbp+120h+pvarg]; pvarg
0x1800c6fa5  call    cs:__imp_VariantClear
0x1800c6fab  lea     rsi, aCW1SSrcDeliver_80; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c6fb2  mov     rcx, [rbp+120h+var_190]
0x1800c6fb6  test    rcx, rcx
0x1800c6fb9  jz      short loc_1800C6FCC
0x1800c6fbb  mov     [rbp+120h+var_190], r13
0x1800c6fbf  mov     rax, [rcx]
0x1800c6fc2  mov     rax, [rax+10h]
0x1800c6fc6  call    _guard_dispatch_icall
0x1800c6fcb  nop
0x1800c6fcc  mov     rcx, [rbp+120h+bstrString]; bstrString
0x1800c6fd0  test    rcx, rcx
0x1800c6fd3  jz      loc_1800C6DD0
0x1800c6fd9  call    cs:__imp_SysFreeString
0x1800c6fdf  jmp     loc_1800C6DD0
0x1800c6fe4  test    r15b, r15b
0x1800c6fe7  jnz     short loc_1800C6FF3
0x1800c6fe9  cmp     [r12], r13b
0x1800c6fed  jz      loc_1800C70EE
0x1800c6ff3  xor     edx, edx; Val
0x1800c6ff5  mov     r8d, 0F8h; Size
0x1800c6ffb  lea     rcx, [rbp+120h+var_140]; void *
0x1800c6fff  call    memset
0x1800c7004  lea     rcx, [rbp+120h+var_140]
0x1800c7008  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x1800c700d  mov     rbx, [rbp+120h+var_158]
0x1800c7011  mov     rbx, [rbx]
0x1800c7014  jmp     loc_1800C70A3
0x1800c7019  lea     rdi, [rbx+20h]
0x1800c701d  lea     rdx, [rbp+120h+pvarg]
0x1800c7021  lea     rcx, [rbp+120h+var_130]
0x1800c7025  call    ?tellp@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::ostream::tellp(void)
0x1800c702a  mov     rcx, rax
0x1800c702d  mov     rax, [rax+8]
0x1800c7031  add     rax, [rcx]
0x1800c7034  jz      short loc_1800C7046
0x1800c7036  lea     rdx, asc_18013A968; ";"
0x1800c703d  lea     rcx, [rbp+120h+var_130]
0x1800c7041  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800c7046  mov     r8, [rdi+10h]
0x1800c704a  cmp     qword ptr [rdi+18h], 0Fh
0x1800c704f  jbe     short loc_1800C7054
0x1800c7051  mov     rdi, [rdi]
0x1800c7054  mov     rdx, rdi
0x1800c7057  lea     rcx, [rbp+120h+var_130]
0x1800c705b  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1800c7060  mov     rcx, [rbx+10h]
0x1800c7064  cmp     [rcx+19h], r13b
0x1800c7068  jz      short loc_1800C7088
0x1800c706a  mov     rax, [rbx+8]
0x1800c706e  jmp     short loc_1800C707D
0x1800c7070  cmp     rbx, [rax+10h]
0x1800c7074  jnz     short loc_1800C7083
0x1800c7076  mov     rbx, rax
0x1800c7079  mov     rax, [rax+8]
0x1800c707d  cmp     [rax+19h], r13b
0x1800c7081  jz      short loc_1800C7070
0x1800c7083  mov     rbx, rax
0x1800c7086  jmp     short loc_1800C70A3
0x1800c7088  mov     rbx, rcx
0x1800c708b  mov     rcx, [rcx]
0x1800c708e  cmp     [rcx+19h], r13b
0x1800c7092  jnz     short loc_1800C70A3
0x1800c7094  mov     rbx, rcx
0x1800c7097  mov     rax, [rcx]
0x1800c709a  mov     rcx, rax
0x1800c709d  cmp     [rax+19h], r13b
0x1800c70a1  jz      short loc_1800C7094
0x1800c70a3  cmp     [rbx+19h], r13b
0x1800c70a7  jz      loc_1800C7019
0x1800c70ad  lea     rdx, [rsp+220h+var_1E0]
0x1800c70b2  lea     rcx, [rbp+120h+var_140]
0x1800c70b6  call    ?str@?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEGBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::str(void)
0x1800c70bb  mov     rdx, rax
0x1800c70be  mov     rcx, r14
0x1800c70c1  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800c70c6  lea     rcx, [rsp+220h+var_1E0]; void *
0x1800c70cb  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800c70d0  lea     rcx, [rbp+120h+var_A8]
0x1800c70d4  call    ??1?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x1800c70d9  lea     rax, ??_7?$basic_ios@DU?$char_traits@D@std@@@std@@6B@; const std::ios::`vftable'
0x1800c70e0  mov     [rbp+120h+var_A8], rax
0x1800c70e4  lea     rcx, [rbp+120h+var_A8]; this
0x1800c70e8  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x1800c70ed  nop
0x1800c70ee  mov     rcx, [rbp+120h+var_198]
0x1800c70f2  test    rcx, rcx
0x1800c70f5  jz      short loc_1800C7108
0x1800c70f7  mov     [rbp+120h+var_198], r13
0x1800c70fb  mov     rax, [rcx]
0x1800c70fe  mov     rax, [rax+10h]
0x1800c7102  call    _guard_dispatch_icall
0x1800c7107  nop
0x1800c7108  lea     rcx, [rbp+120h+var_158]
0x1800c710c  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::~_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>(void)
0x1800c7111  nop
  ... truncated ...
```
