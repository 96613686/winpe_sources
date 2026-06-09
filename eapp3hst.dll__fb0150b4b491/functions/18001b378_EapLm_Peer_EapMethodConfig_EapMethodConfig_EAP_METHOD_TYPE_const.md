# EapLm::Peer::EapMethodConfig::EapMethodConfig(_EAP_METHOD_TYPE const &)

- ea: `0x18001b378`
- end: `0x18001b8e1`
- name: `??0EapMethodConfig@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z`
- size: `1385`
- prototype: `EapLm::Peer::EapMethodConfig *__fastcall(EapLm::Peer::EapMethodConfig *this, struct _EAP_METHOD_TYPE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x180016cf0`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x18000bba8`
- `0x18000d098`
- `0x18000eb94`
- `0x18001549c`
- `0x180016b4c`
- `0x18001b378`
- `0x18001ff28`
- `0x18002e67c`

## string_xrefs

- `0x18001b586`: `PeerDllPath`
- `0x18001b520`: `PeerConfigUIPath`
- `0x18001b50f`: `PeerInteractiveUIPath`
- `0x18001b4fb`: `PeerIdentityPath`
- `0x18001b3cf`: `EapPeerCreateMethodConfiguration`
- `0x18001b3e3`: `EapPeerGetConfigBlobAndUserBlob`
- `0x18001b433`: `EapPeerConfigBlob2Xml`
- `0x18001b447`: `EapPeerCredentialsXml2Blob`
- `0x18001b45b`: `EapPeerConfigXml2Blob`
- `0x18001b4e7`: `EapPeerInvokeConfigUI`
- `0x18001b542`: `PeerRequireConfigUI`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
EapLm::Peer::EapMethodConfig *__fastcall EapLm::Peer::EapMethodConfig::EapMethodConfig(
        EapLm::Peer::EapMethodConfig *this,
        struct _EAP_METHOD_TYPE *a2)
{
  const wchar_t *v4; // rdx
  unsigned int v5; // r9d
  signed int v6; // esi
  __int64 v7; // rax
  void **v9; // [rsp+E8h] [rbp-78h] BYREF
  char v10; // [rsp+F0h] [rbp-70h]
  __int64 v11; // [rsp+F4h] [rbp-6Ch]
  int v12; // [rsp+100h] [rbp-60h]
  _BYTE v13[32]; // [rsp+108h] [rbp-58h] BYREF
  _BYTE v14[32]; // [rsp+128h] [rbp-38h] BYREF
  _BYTE v15[32]; // [rsp+148h] [rbp-18h] BYREF
  _BYTE v16[32]; // [rsp+168h] [rbp+8h] BYREF
  _BYTE v17[32]; // [rsp+188h] [rbp+28h] BYREF
  _BYTE v18[32]; // [rsp+1A8h] [rbp+48h] BYREF
  _BYTE v19[32]; // [rsp+1C8h] [rbp+68h] BYREF
  _BYTE v20[32]; // [rsp+1E8h] [rbp+88h] BYREF
  _BYTE v21[32]; // [rsp+208h] [rbp+A8h] BYREF
  _BYTE v22[32]; // [rsp+228h] [rbp+C8h] BYREF
  _BYTE v23[32]; // [rsp+248h] [rbp+E8h] BYREF
  _BYTE v24[32]; // [rsp+268h] [rbp+108h] BYREF
  _BYTE v25[32]; // [rsp+288h] [rbp+128h] BYREF
  _BYTE v26[32]; // [rsp+2A8h] [rbp+148h] BYREF
  _BYTE v27[32]; // [rsp+2C8h] [rbp+168h] BYREF
  _BYTE v28[32]; // [rsp+2E8h] [rbp+188h] BYREF
  _BYTE v29[32]; // [rsp+308h] [rbp+1A8h] BYREF
  _BYTE v30[32]; // [rsp+328h] [rbp+1C8h] BYREF
  _BYTE v31[32]; // [rsp+348h] [rbp+1E8h] BYREF
  _BYTE v32[32]; // [rsp+368h] [rbp+208h] BYREF
  _BYTE v33[32]; // [rsp+388h] [rbp+228h] BYREF
  _BYTE v34[32]; // [rsp+3A8h] [rbp+248h] BYREF
  _BYTE v35[32]; // [rsp+3C8h] [rbp+268h] BYREF
  _BYTE v36[32]; // [rsp+3E8h] [rbp+288h] BYREF
  _BYTE v37[40]; // [rsp+408h] [rbp+2A8h] BYREF
  wchar_t v38[264]; // [rsp+430h] [rbp+2D0h] BYREF

  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v37,
    (__int64)L"EapPeerFreeErrorMemory");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v36,
    (__int64)L"EapPeerFreeMemory");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v35,
    (__int64)L"EapPeerCreateMethodConfiguration");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v34,
    (__int64)L"EapPeerGetConfigBlobAndUserBlob");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v33,
    (__int64)L"EapPeerGetIdentityPageGuid");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v32,
    (__int64)L"EapPeerGetNextPageGuid");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v31,
    (__int64)L"EapPeerGetMethodProperties");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v30,
    (__int64)L"EapPeerConfigBlob2Xml");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v29,
    (__int64)L"EapPeerCredentialsXml2Blob");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v28,
    (__int64)L"EapPeerConfigXml2Blob");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v27,
    (__int64)L"EapPeerQueryUIBlobFromInteractiveUIInputFields");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v26,
    (__int64)L"EapPeerQueryInteractiveUIInputFields");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v25,
    (__int64)L"EapPeerQueryUserBlobFromCredentialInputFields");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v24,
    (__int64)L"EapPeerQueryCredentialInputFields");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v23,
    (__int64)L"EapPeerInvokeIdentityUI");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v22,
    (__int64)L"EapPeerInvokeInteractiveUI");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v21,
    (__int64)L"EapPeerInvokeConfigUI");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v20,
    (__int64)L"PeerIdentityPath");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v19,
    (__int64)L"PeerInteractiveUIPath");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v18,
    (__int64)L"PeerConfigUIPath");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v17,
    (__int64)L"Properties");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v16,
    (__int64)L"PeerRequireConfigUI");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v15,
    (__int64)L"PeerInvokePasswordDialog");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v14,
    (__int64)L"PeerInvokeUsernameDialog");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v13,
    (__int64)L"PeerFriendlyName");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)&v9,
    (__int64)L"PeerDllPath");
  EapLm::Peer::BaseEapMethodConfig::BaseEapMethodConfig(
    (__int64)this,
    a2,
    (__int64)&v9,
    (__int64)v13,
    (__int64)v14,
    (__int64)v15,
    (__int64)v16,
    (__int64)v17,
    (__int64)v18,
    (__int64)v19,
    (__int64)v20,
    (__int64)v21,
    (__int64)v22,
    (__int64)v23,
    (__int64)v24,
    (__int64)v25,
    (__int64)v26,
    (__int64)v27,
    (__int64)v28,
    (__int64)v29,
    (__int64)v30,
    (__int64)v31,
    (__int64)v32,
    (__int64)v33,
    (__int64)v34,
    (__int64)v35,
    (__int64)v36,
    (__int64)v37);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(&v9);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v13);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v14);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v15);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v16);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v17);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v18);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v19);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v20);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v21);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v22);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v23);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v24);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v25);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v26);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v27);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v28);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v29);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v30);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v31);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v32);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v33);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v34);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v35);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v36);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v37);
  *(_QWORD *)this = &EapLm::Peer::EapMethodConfig::`vftable';
  v6 = EapLm::IEapMethod::ConstructMethodRegPath((const struct _EAP_METHOD_TYPE *)this + 1, v4, v38, v5);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids);
    v10 = *((_BYTE *)this + 16);
    v11 = *(_QWORD *)((char *)this + 20);
    if ( v10 != -2 )
      v11 = 0;
    v9 = &EapHost::EapMethodType::`vftable';
    v12 = *((_DWORD *)this + 7);
    EapHost::EapException::Throw(v6, (const struct EapHost::EapMethodType *)&v9, 0);
  }
  v7 = std::_WChar_traits<wchar_t>::length(v38);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(
    (char *)this + 32,
    v38,
    v7);
  return this;
}

```

## disassembly

```asm
0x18001b378  push    rbp
0x18001b37a  push    rbx
0x18001b37b  push    rsi
0x18001b37c  push    rdi
0x18001b37d  lea     rbp, [rsp-4F8h]
0x18001b385  sub     rsp, 658h
0x18001b38c  mov     rax, cs:__security_cookie
0x18001b393  xor     rax, rsp
0x18001b396  mov     [rbp+510h+var_30], rax
0x18001b39d  mov     rbx, rdx
0x18001b3a0  mov     rdi, rcx
0x18001b3a3  mov     [rbp+510h+var_590], rcx
0x18001b3a7  lea     rdx, aEappeerfreeerr; "EapPeerFreeErrorMemory"
0x18001b3ae  lea     rcx, [rbp+510h+var_268]
0x18001b3b5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b3ba  nop
0x18001b3bb  lea     rdx, aEappeerfreemem_0; "EapPeerFreeMemory"
0x18001b3c2  lea     rcx, [rbp+510h+var_288]
0x18001b3c9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b3ce  nop
0x18001b3cf  lea     rdx, aEappeercreatem; "EapPeerCreateMethodConfiguration"
0x18001b3d6  lea     rcx, [rbp+510h+var_2A8]
0x18001b3dd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b3e2  nop
0x18001b3e3  lea     rdx, aEappeergetconf; "EapPeerGetConfigBlobAndUserBlob"
0x18001b3ea  lea     rcx, [rbp+510h+var_2C8]
0x18001b3f1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b3f6  nop
0x18001b3f7  lea     rdx, aEappeergetiden; "EapPeerGetIdentityPageGuid"
0x18001b3fe  lea     rcx, [rbp+510h+var_2E8]
0x18001b405  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b40a  nop
0x18001b40b  lea     rdx, aEappeergetnext; "EapPeerGetNextPageGuid"
0x18001b412  lea     rcx, [rbp+510h+var_308]
0x18001b419  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b41e  nop
0x18001b41f  lea     rdx, aEappeergetmeth; "EapPeerGetMethodProperties"
0x18001b426  lea     rcx, [rbp+510h+var_328]
0x18001b42d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b432  nop
0x18001b433  lea     rdx, aEappeerconfigb; "EapPeerConfigBlob2Xml"
0x18001b43a  lea     rcx, [rbp+510h+var_348]
0x18001b441  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b446  nop
0x18001b447  lea     rdx, aEappeercredent_2; "EapPeerCredentialsXml2Blob"
0x18001b44e  lea     rcx, [rbp+510h+var_368]
0x18001b455  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b45a  nop
0x18001b45b  lea     rdx, aEappeerconfigx_0; "EapPeerConfigXml2Blob"
0x18001b462  lea     rcx, [rbp+510h+var_388]
0x18001b469  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b46e  nop
0x18001b46f  lea     rdx, aEappeerqueryui; "EapPeerQueryUIBlobFromInteractiveUIInpu"...
0x18001b476  lea     rcx, [rbp+510h+var_3A8]
0x18001b47d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b482  nop
0x18001b483  lea     rdx, aEappeerqueryin_0; "EapPeerQueryInteractiveUIInputFields"
0x18001b48a  lea     rcx, [rbp+510h+var_3C8]
0x18001b491  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b496  nop
0x18001b497  lea     rdx, aEappeerqueryus_0; "EapPeerQueryUserBlobFromCredentialInput"...
0x18001b49e  lea     rcx, [rbp+510h+var_3E8]
0x18001b4a5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b4aa  nop
0x18001b4ab  lea     rdx, aEappeerquerycr_1; "EapPeerQueryCredentialInputFields"
0x18001b4b2  lea     rcx, [rbp+510h+var_408]
0x18001b4b9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b4be  nop
0x18001b4bf  lea     rdx, aEappeerinvokei_3; "EapPeerInvokeIdentityUI"
0x18001b4c6  lea     rcx, [rbp+510h+var_428]
0x18001b4cd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b4d2  nop
0x18001b4d3  lea     rdx, aEappeerinvokei_2; "EapPeerInvokeInteractiveUI"
0x18001b4da  lea     rcx, [rbp+510h+var_448]
0x18001b4e1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b4e6  nop
0x18001b4e7  lea     rdx, aEappeerinvokec; "EapPeerInvokeConfigUI"
0x18001b4ee  lea     rcx, [rbp+510h+var_468]
0x18001b4f5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b4fa  nop
0x18001b4fb  lea     rdx, aPeeridentitypa; "PeerIdentityPath"
0x18001b502  lea     rcx, [rbp+510h+var_488]
0x18001b509  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b50e  nop
0x18001b50f  lea     rdx, aPeerinteractiv; "PeerInteractiveUIPath"
0x18001b516  lea     rcx, [rbp+510h+var_4A8]
0x18001b51a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b51f  nop
0x18001b520  lea     rdx, aPeerconfiguipa; "PeerConfigUIPath"
0x18001b527  lea     rcx, [rbp+510h+var_4C8]
0x18001b52b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b530  nop
0x18001b531  lea     rdx, aProperties; "Properties"
0x18001b538  lea     rcx, [rbp+510h+var_4E8]
0x18001b53c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b541  nop
0x18001b542  lea     rdx, aPeerrequirecon; "PeerRequireConfigUI"
0x18001b549  lea     rcx, [rbp+510h+var_508]
0x18001b54d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b552  nop
0x18001b553  lea     rdx, aPeerinvokepass; "PeerInvokePasswordDialog"
0x18001b55a  lea     rcx, [rbp+510h+var_528]
0x18001b55e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b563  nop
0x18001b564  lea     rdx, aPeerinvokeuser; "PeerInvokeUsernameDialog"
0x18001b56b  lea     rcx, [rbp+510h+var_548]
0x18001b56f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b574  nop
0x18001b575  lea     rdx, aPeerfriendlyna; "PeerFriendlyName"
0x18001b57c  lea     rcx, [rbp+510h+var_568]
0x18001b580  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b585  nop
0x18001b586  lea     rdx, aPeerdllpath; "PeerDllPath"
0x18001b58d  lea     rcx, [rbp+510h+var_588]
0x18001b591  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001b596  nop
0x18001b597  lea     rax, [rbp+510h+var_268]
0x18001b59e  mov     [rsp+670h+var_598], rax
0x18001b5a6  lea     rax, [rbp+510h+var_288]
0x18001b5ad  mov     [rsp+670h+var_5A0], rax
0x18001b5b5  lea     rax, [rbp+510h+var_2A8]
0x18001b5bc  mov     [rsp+670h+var_5A8], rax
0x18001b5c4  lea     rax, [rbp+510h+var_2C8]
0x18001b5cb  mov     [rsp+670h+var_5B0], rax
0x18001b5d3  lea     rax, [rbp+510h+var_2E8]
0x18001b5da  mov     [rsp+670h+var_5B8], rax
0x18001b5e2  lea     rax, [rbp+510h+var_308]
0x18001b5e9  mov     [rsp+670h+var_5C0], rax
0x18001b5f1  lea     rax, [rbp+510h+var_328]
0x18001b5f8  mov     [rsp+670h+var_5C8], rax
0x18001b600  lea     rax, [rbp+510h+var_348]
0x18001b607  mov     [rsp+670h+var_5D0], rax
0x18001b60f  lea     rax, [rbp+510h+var_368]
0x18001b616  mov     [rsp+670h+var_5D8], rax
0x18001b61e  lea     rax, [rbp+510h+var_388]
0x18001b625  mov     [rsp+670h+var_5E0], rax
0x18001b62d  lea     rax, [rbp+510h+var_3A8]
0x18001b634  mov     [rsp+670h+var_5E8], rax
0x18001b63c  lea     rax, [rbp+510h+var_3C8]
0x18001b643  mov     [rsp+670h+var_5F0], rax
0x18001b64b  lea     rax, [rbp+510h+var_3E8]
0x18001b652  mov     [rsp+670h+var_5F8], rax
0x18001b657  lea     rax, [rbp+510h+var_408]
0x18001b65e  mov     [rsp+670h+var_600], rax
0x18001b663  lea     rax, [rbp+510h+var_428]
0x18001b66a  mov     [rsp+670h+var_608], rax
0x18001b66f  lea     rax, [rbp+510h+var_448]
0x18001b676  mov     [rsp+670h+var_610], rax
0x18001b67b  lea     rax, [rbp+510h+var_468]
0x18001b682  mov     [rsp+670h+var_618], rax
0x18001b687  lea     rax, [rbp+510h+var_488]
0x18001b68e  mov     [rsp+670h+var_620], rax
0x18001b693  lea     rax, [rbp+510h+var_4A8]
0x18001b697  mov     [rsp+670h+var_628], rax
0x18001b69c  lea     rax, [rbp+510h+var_4C8]
0x18001b6a0  mov     [rsp+670h+var_630], rax
0x18001b6a5  lea     rax, [rbp+510h+var_4E8]
0x18001b6a9  mov     [rsp+670h+var_638], rax
0x18001b6ae  lea     rax, [rbp+510h+var_508]
0x18001b6b2  mov     [rsp+670h+var_640], rax
0x18001b6b7  lea     rax, [rbp+510h+var_528]
0x18001b6bb  mov     [rsp+670h+var_648], rax
0x18001b6c0  lea     rax, [rbp+510h+var_548]
0x18001b6c4  mov     [rsp+670h+var_650], rax
0x18001b6c9  lea     r9, [rbp+510h+var_568]
0x18001b6cd  lea     r8, [rbp+510h+var_588]
0x18001b6d1  mov     rdx, rbx
0x18001b6d4  mov     rcx, rdi
0x18001b6d7  call    ??0BaseEapMethodConfig@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@1111111111111111111111111@Z; EapLm::Peer::BaseEapMethodConfig::BaseEapMethodConfig(_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001b6dc  nop
0x18001b6dd  lea     rcx, [rbp+510h+var_588]
0x18001b6e1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b6e6  nop
0x18001b6e7  lea     rcx, [rbp+510h+var_568]
0x18001b6eb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b6f0  nop
0x18001b6f1  lea     rcx, [rbp+510h+var_548]
0x18001b6f5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b6fa  nop
0x18001b6fb  lea     rcx, [rbp+510h+var_528]
0x18001b6ff  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b704  nop
0x18001b705  lea     rcx, [rbp+510h+var_508]
0x18001b709  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b70e  nop
0x18001b70f  lea     rcx, [rbp+510h+var_4E8]
0x18001b713  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b718  nop
0x18001b719  lea     rcx, [rbp+510h+var_4C8]
0x18001b71d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b722  nop
0x18001b723  lea     rcx, [rbp+510h+var_4A8]
0x18001b727  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b72c  nop
0x18001b72d  lea     rcx, [rbp+510h+var_488]
0x18001b734  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b739  nop
0x18001b73a  lea     rcx, [rbp+510h+var_468]
0x18001b741  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b746  nop
0x18001b747  lea     rcx, [rbp+510h+var_448]
0x18001b74e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b753  nop
0x18001b754  lea     rcx, [rbp+510h+var_428]
0x18001b75b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b760  nop
0x18001b761  lea     rcx, [rbp+510h+var_408]
0x18001b768  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b76d  nop
0x18001b76e  lea     rcx, [rbp+510h+var_3E8]
0x18001b775  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b77a  nop
0x18001b77b  lea     rcx, [rbp+510h+var_3C8]
0x18001b782  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b787  nop
0x18001b788  lea     rcx, [rbp+510h+var_3A8]
0x18001b78f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b794  nop
0x18001b795  lea     rcx, [rbp+510h+var_388]
0x18001b79c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b7a1  nop
0x18001b7a2  lea     rcx, [rbp+510h+var_368]
0x18001b7a9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b7ae  nop
0x18001b7af  lea     rcx, [rbp+510h+var_348]
0x18001b7b6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b7bb  nop
0x18001b7bc  lea     rcx, [rbp+510h+var_328]
0x18001b7c3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b7c8  nop
0x18001b7c9  lea     rcx, [rbp+510h+var_308]
0x18001b7d0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b7d5  nop
0x18001b7d6  lea     rcx, [rbp+510h+var_2E8]
0x18001b7dd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b7e2  nop
0x18001b7e3  lea     rcx, [rbp+510h+var_2C8]
0x18001b7ea  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b7ef  nop
0x18001b7f0  lea     rcx, [rbp+510h+var_2A8]
0x18001b7f7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b7fc  nop
0x18001b7fd  lea     rcx, [rbp+510h+var_288]
0x18001b804  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b809  nop
0x18001b80a  lea     rcx, [rbp+510h+var_268]
0x18001b811  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b816  lea     rax, ??_7EapMethodConfig@Peer@EapLm@@6B@; const EapLm::Peer::EapMethodConfig::`vftable'
0x18001b81d  mov     [rdi], rax
0x18001b820  lea     r8, [rbp+510h+var_240]; wchar_t *
0x18001b827  lea     rcx, [rdi+10h]; struct _EAP_METHOD_TYPE *
0x18001b82b  call    ?ConstructMethodRegPath@IEapMethod@EapLm@@SAJAEBU_EAP_METHOD_TYPE@@QEB_WPEA_WK@Z; EapLm::IEapMethod::ConstructMethodRegPath(_EAP_METHOD_TYPE const &,wchar_t const * const,wchar_t *,ulong)
0x18001b830  mov     esi, eax
0x18001b832  test    eax, eax
0x18001b834  jns     short loc_18001B8A3
0x18001b836  lea     rax, WPP_GLOBAL_Control
0x18001b83d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b844  cmp     rcx, rax
0x18001b847  jz      short loc_18001B864
0x18001b849  test    byte ptr [rcx+1Ch], 1
0x18001b84d  jz      short loc_18001B864
0x18001b84f  mov     edx, 0Ah
0x18001b854  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001b85b  mov     rcx, [rcx+10h]
0x18001b85f  call    WPP_SF_
0x18001b864  mov     cl, [rdi+10h]
0x18001b867  mov     [rbp+510h+var_580], cl
0x18001b86a  mov     eax, [rdi+14h]
0x18001b86d  mov     dword ptr [rbp+510h+var_57C], eax
0x18001b870  mov     eax, [rdi+18h]
0x18001b873  mov     dword ptr [rbp+510h+var_57C+4], eax
0x18001b876  cmp     cl, 0FEh
0x18001b879  jz      short loc_18001B883
0x18001b87b  mov     [rbp+510h+var_57C], 0
0x18001b883  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001b88a  mov     [rbp+510h+var_588], rax
0x18001b88e  mov     eax, [rdi+1Ch]
0x18001b891  mov     [rbp+510h+var_570], eax
0x18001b894  xor     r8d, r8d; unsigned int
0x18001b897  lea     rdx, [rbp+510h+var_588]; struct EapHost::EapMethodType *
0x18001b89b  mov     ecx, esi; unsigned int
0x18001b89d  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x18001b8a3  lea     rcx, [rbp+510h+var_240]
0x18001b8aa  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18001b8af  mov     r8, rax
0x18001b8b2  lea     rcx, [rdi+20h]
0x18001b8b6  lea     rdx, [rbp+510h+var_240]
0x18001b8bd  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001b8c2  nop
0x18001b8c3  mov     rax, rdi
0x18001b8c6  mov     rcx, [rbp+510h+var_30]
0x18001b8cd  xor     rcx, rsp; StackCookie
0x18001b8d0  call    __security_check_cookie
0x18001b8d5  add     rsp, 658h
0x18001b8dc  pop     rdi
0x18001b8dd  pop     rsi
0x18001b8de  pop     rbx
0x18001b8df  pop     rbp
0x18001b8e0  retn
```
