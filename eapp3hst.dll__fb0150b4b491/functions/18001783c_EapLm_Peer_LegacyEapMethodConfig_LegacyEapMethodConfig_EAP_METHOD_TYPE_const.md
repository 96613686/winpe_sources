# EapLm::Peer::LegacyEapMethodConfig::LegacyEapMethodConfig(_EAP_METHOD_TYPE const &)

- ea: `0x18001783c`
- end: `0x180017d76`
- name: `??0LegacyEapMethodConfig@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z`
- size: `1338`
- prototype: `EapLm::Peer::LegacyEapMethodConfig *__fastcall(EapLm::Peer::LegacyEapMethodConfig *this, struct _EAP_METHOD_TYPE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180016cf0`

## callees

- `0x1800017a0`
- `0x1800034ec`
- `0x18000bba8`
- `0x18000d098`
- `0x18000eb94`
- `0x180015534`
- `0x180016b4c`
- `0x18001783c`
- `0x18001ff28`

## string_xrefs

- `0x1800179ea`: `ConfigUIPath`
- `0x1800179d9`: `InteractiveUIPath`
- `0x1800179c5`: `IdentityPath`
- `0x180017899`: `RasEapCreateMethodConfiguration`
- `0x1800178ad`: `RasEapGetConfigBlobAndUserBlob`
- `0x1800178fd`: `RasEapCreateConnectionPropertiesXml`
- `0x180017911`: `RasEapCreateUserProperties`
- `0x180017925`: `RasEapCreateConnectionProperties`
- `0x1800179b1`: `RasEapInvokeConfigUI`
- `0x180017a0c`: `RequireConfigUI`
- `0x180017cf2`: `System\CurrentControlSet\Services\Rasman\PPP\EAP`
- `0x180017d1b`: `eapMethodRegPath`
- `0x180017d22`: `LoadConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
EapLm::Peer::LegacyEapMethodConfig *__fastcall EapLm::Peer::LegacyEapMethodConfig::LegacyEapMethodConfig(
        EapLm::Peer::LegacyEapMethodConfig *this,
        struct _EAP_METHOD_TYPE *a2)
{
  __int64 v4; // rax
  __int64 v6; // [rsp+20h] [rbp-140h]
  _BYTE v7[32]; // [rsp+E8h] [rbp-78h] BYREF
  _BYTE v8[32]; // [rsp+108h] [rbp-58h] BYREF
  _BYTE v9[32]; // [rsp+128h] [rbp-38h] BYREF
  _BYTE v10[32]; // [rsp+148h] [rbp-18h] BYREF
  _BYTE v11[32]; // [rsp+168h] [rbp+8h] BYREF
  _BYTE v12[32]; // [rsp+188h] [rbp+28h] BYREF
  _BYTE v13[32]; // [rsp+1A8h] [rbp+48h] BYREF
  _BYTE v14[32]; // [rsp+1C8h] [rbp+68h] BYREF
  _BYTE v15[32]; // [rsp+1E8h] [rbp+88h] BYREF
  _BYTE v16[32]; // [rsp+208h] [rbp+A8h] BYREF
  _BYTE v17[32]; // [rsp+228h] [rbp+C8h] BYREF
  _BYTE v18[32]; // [rsp+248h] [rbp+E8h] BYREF
  _BYTE v19[32]; // [rsp+268h] [rbp+108h] BYREF
  _BYTE v20[32]; // [rsp+288h] [rbp+128h] BYREF
  _BYTE v21[32]; // [rsp+2A8h] [rbp+148h] BYREF
  _BYTE v22[32]; // [rsp+2C8h] [rbp+168h] BYREF
  _BYTE v23[32]; // [rsp+2E8h] [rbp+188h] BYREF
  _BYTE v24[32]; // [rsp+308h] [rbp+1A8h] BYREF
  _BYTE v25[32]; // [rsp+328h] [rbp+1C8h] BYREF
  _BYTE v26[32]; // [rsp+348h] [rbp+1E8h] BYREF
  _BYTE v27[32]; // [rsp+368h] [rbp+208h] BYREF
  _BYTE v28[32]; // [rsp+388h] [rbp+228h] BYREF
  _BYTE v29[32]; // [rsp+3A8h] [rbp+248h] BYREF
  _BYTE v30[32]; // [rsp+3C8h] [rbp+268h] BYREF
  _BYTE v31[32]; // [rsp+3E8h] [rbp+288h] BYREF
  _BYTE v32[40]; // [rsp+408h] [rbp+2A8h] BYREF
  wchar_t v33[264]; // [rsp+430h] [rbp+2D0h] BYREF

  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v32,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v31,
    (__int64)L"RasEapFreeMemory");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v30,
    (__int64)L"RasEapCreateMethodConfiguration");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v29,
    (__int64)L"RasEapGetConfigBlobAndUserBlob");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v28,
    (__int64)L"RasEapGetIdentityPageGuid");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v27,
    (__int64)L"RasEapGetNextPageGuid");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v26,
    (__int64)L"RasEapGetMethodProperties");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v25,
    (__int64)L"RasEapCreateConnectionPropertiesXml");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v24,
    (__int64)L"RasEapCreateUserProperties");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v23,
    (__int64)L"RasEapCreateConnectionProperties");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v22,
    (__int64)L"RasEapQueryUIBlobFromInteractiveUIInputFields");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v21,
    (__int64)L"RasEapQueryInteractiveUIInputFields");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v20,
    (__int64)L"RasEapQueryUserBlobFromCredentialInputFields");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v19,
    (__int64)L"RasEapQueryCredentialInputFields");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v18,
    (__int64)L"RasEapGetIdentity");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v17,
    (__int64)L"RasEapInvokeInteractiveUI");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v16,
    (__int64)L"RasEapInvokeConfigUI");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v15,
    (__int64)L"IdentityPath");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v14,
    (__int64)L"InteractiveUIPath");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v13,
    (__int64)L"ConfigUIPath");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v12,
    (__int64)L"RolesSupported");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v11,
    (__int64)L"RequireConfigUI");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v10,
    (__int64)L"InvokePasswordDialog");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v9,
    (__int64)L"InvokeUsernameDialog");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v8,
    (__int64)L"FriendlyName");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v7,
    (__int64)L"Path");
  EapLm::Peer::BaseEapMethodConfig::BaseEapMethodConfig(
    (__int64)this,
    a2,
    (__int64)v7,
    (__int64)v8,
    (__int64)v9,
    (__int64)v10,
    (__int64)v11,
    (__int64)v12,
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
    (__int64)v32);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v7);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v8);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v9);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v10);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v11);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v12);
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
  *(_QWORD *)this = &EapLm::Peer::LegacyEapMethodConfig::`vftable';
  LODWORD(v6) = *((unsigned __int8 *)this + 16);
  if ( (int)StringCchPrintfW(v33, 0x104u, L"%s\\%d", L"System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP", v6) < 0 )
    EapHost::EapException::Throw(L"LoadConfig", L"eapMethodRegPath", -2147024809);
  v4 = std::_WChar_traits<wchar_t>::length(v33);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(
    (char *)this + 32,
    v33,
    v4);
  return this;
}

```

## disassembly

```asm
0x18001783c  mov     [rsp-8+arg_8], rbx
0x180017841  mov     [rsp-8+arg_10], rdi
0x180017846  push    rbp
0x180017847  lea     rbp, [rsp-4F0h]
0x18001784f  sub     rsp, 650h
0x180017856  mov     rax, cs:__security_cookie
0x18001785d  xor     rax, rsp
0x180017860  mov     [rbp+4F0h+var_10], rax
0x180017867  mov     rbx, rdx
0x18001786a  mov     rdi, rcx
0x18001786d  mov     [rbp+4F0h+var_570], rcx
0x180017871  lea     rdx, qword_18003A720
0x180017878  lea     rcx, [rbp+4F0h+var_248]
0x18001787f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180017884  nop
0x180017885  lea     rdx, aRaseapfreememo_0; "RasEapFreeMemory"
0x18001788c  lea     rcx, [rbp+4F0h+var_268]
0x180017893  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180017898  nop
0x180017899  lea     rdx, aRaseapcreateme; "RasEapCreateMethodConfiguration"
0x1800178a0  lea     rcx, [rbp+4F0h+var_288]
0x1800178a7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x1800178ac  nop
0x1800178ad  lea     rdx, aRaseapgetconfi; "RasEapGetConfigBlobAndUserBlob"
0x1800178b4  lea     rcx, [rbp+4F0h+var_2A8]
0x1800178bb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x1800178c0  nop
0x1800178c1  lea     rdx, aRaseapgetident_2; "RasEapGetIdentityPageGuid"
0x1800178c8  lea     rcx, [rbp+4F0h+var_2C8]
0x1800178cf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x1800178d4  nop
0x1800178d5  lea     rdx, aRaseapgetnextp; "RasEapGetNextPageGuid"
0x1800178dc  lea     rcx, [rbp+4F0h+var_2E8]
0x1800178e3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x1800178e8  nop
0x1800178e9  lea     rdx, aRaseapgetmetho; "RasEapGetMethodProperties"
0x1800178f0  lea     rcx, [rbp+4F0h+var_308]
0x1800178f7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x1800178fc  nop
0x1800178fd  lea     rdx, aRaseapcreateco_5; "RasEapCreateConnectionPropertiesXml"
0x180017904  lea     rcx, [rbp+4F0h+var_328]
0x18001790b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180017910  nop
0x180017911  lea     rdx, aRaseapcreateus_1; "RasEapCreateUserProperties"
0x180017918  lea     rcx, [rbp+4F0h+var_348]
0x18001791f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180017924  nop
0x180017925  lea     rdx, aRaseapcreateco_6; "RasEapCreateConnectionProperties"
0x18001792c  lea     rcx, [rbp+4F0h+var_368]
0x180017933  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180017938  nop
0x180017939  lea     rdx, aRaseapqueryuib_2; "RasEapQueryUIBlobFromInteractiveUIInput"...
0x180017940  lea     rcx, [rbp+4F0h+var_388]
0x180017947  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001794c  nop
0x18001794d  lea     rdx, aRaseapqueryint_1; "RasEapQueryInteractiveUIInputFields"
0x180017954  lea     rcx, [rbp+4F0h+var_3A8]
0x18001795b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180017960  nop
0x180017961  lea     rdx, aRaseapqueryuse_0; "RasEapQueryUserBlobFromCredentialInputF"...
0x180017968  lea     rcx, [rbp+4F0h+var_3C8]
0x18001796f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180017974  nop
0x180017975  lea     rdx, aRaseapquerycre_2; "RasEapQueryCredentialInputFields"
0x18001797c  lea     rcx, [rbp+4F0h+var_3E8]
0x180017983  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180017988  nop
0x180017989  lea     rdx, aRaseapgetident_1; "RasEapGetIdentity"
0x180017990  lea     rcx, [rbp+4F0h+var_408]
0x180017997  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001799c  nop
0x18001799d  lea     rdx, aRaseapinvokein; "RasEapInvokeInteractiveUI"
0x1800179a4  lea     rcx, [rbp+4F0h+var_428]
0x1800179ab  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x1800179b0  nop
0x1800179b1  lea     rdx, aRaseapinvokeco_0; "RasEapInvokeConfigUI"
0x1800179b8  lea     rcx, [rbp+4F0h+var_448]
0x1800179bf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x1800179c4  nop
0x1800179c5  lea     rdx, aIdentitypath; "IdentityPath"
0x1800179cc  lea     rcx, [rbp+4F0h+var_468]
0x1800179d3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x1800179d8  nop
0x1800179d9  lea     rdx, aInteractiveuip; "InteractiveUIPath"
0x1800179e0  lea     rcx, [rbp+4F0h+var_488]
0x1800179e4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x1800179e9  nop
0x1800179ea  lea     rdx, aConfiguipath; "ConfigUIPath"
0x1800179f1  lea     rcx, [rbp+4F0h+var_4A8]
0x1800179f5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x1800179fa  nop
0x1800179fb  lea     rdx, aRolessupported; "RolesSupported"
0x180017a02  lea     rcx, [rbp+4F0h+var_4C8]
0x180017a06  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180017a0b  nop
0x180017a0c  lea     rdx, aRequireconfigu; "RequireConfigUI"
0x180017a13  lea     rcx, [rbp+4F0h+var_4E8]
0x180017a17  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180017a1c  nop
0x180017a1d  lea     rdx, aInvokepassword; "InvokePasswordDialog"
0x180017a24  lea     rcx, [rbp+4F0h+var_508]
0x180017a28  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180017a2d  nop
0x180017a2e  lea     rdx, aInvokeusername; "InvokeUsernameDialog"
0x180017a35  lea     rcx, [rbp+4F0h+var_528]
0x180017a39  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180017a3e  nop
0x180017a3f  lea     rdx, aFriendlyname; "FriendlyName"
0x180017a46  lea     rcx, [rbp+4F0h+var_548]
0x180017a4a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180017a4f  nop
0x180017a50  lea     rdx, aPath; "Path"
0x180017a57  lea     rcx, [rbp+4F0h+var_568]
0x180017a5b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180017a60  nop
0x180017a61  lea     rax, [rbp+4F0h+var_248]
0x180017a68  mov     [rsp+650h+var_578], rax
0x180017a70  lea     rax, [rbp+4F0h+var_268]
0x180017a77  mov     [rsp+650h+var_580], rax
0x180017a7f  lea     rax, [rbp+4F0h+var_288]
0x180017a86  mov     [rsp+650h+var_588], rax
0x180017a8e  lea     rax, [rbp+4F0h+var_2A8]
0x180017a95  mov     [rsp+650h+var_590], rax
0x180017a9d  lea     rax, [rbp+4F0h+var_2C8]
0x180017aa4  mov     [rsp+650h+var_598], rax
0x180017aac  lea     rax, [rbp+4F0h+var_2E8]
0x180017ab3  mov     [rsp+650h+var_5A0], rax
0x180017abb  lea     rax, [rbp+4F0h+var_308]
0x180017ac2  mov     [rsp+650h+var_5A8], rax
0x180017aca  lea     rax, [rbp+4F0h+var_328]
0x180017ad1  mov     [rsp+650h+var_5B0], rax
0x180017ad9  lea     rax, [rbp+4F0h+var_348]
0x180017ae0  mov     [rsp+650h+var_5B8], rax
0x180017ae8  lea     rax, [rbp+4F0h+var_368]
0x180017aef  mov     [rsp+650h+var_5C0], rax
0x180017af7  lea     rax, [rbp+4F0h+var_388]
0x180017afe  mov     [rsp+650h+var_5C8], rax
0x180017b06  lea     rax, [rbp+4F0h+var_3A8]
0x180017b0d  mov     [rsp+650h+var_5D0], rax
0x180017b15  lea     rax, [rbp+4F0h+var_3C8]
0x180017b1c  mov     [rsp+650h+var_5D8], rax
0x180017b21  lea     rax, [rbp+4F0h+var_3E8]
0x180017b28  mov     [rsp+650h+var_5E0], rax
0x180017b2d  lea     rax, [rbp+4F0h+var_408]
0x180017b34  mov     [rsp+650h+var_5E8], rax
0x180017b39  lea     rax, [rbp+4F0h+var_428]
0x180017b40  mov     [rsp+650h+var_5F0], rax
0x180017b45  lea     rax, [rbp+4F0h+var_448]
0x180017b4c  mov     [rsp+650h+var_5F8], rax
0x180017b51  lea     rax, [rbp+4F0h+var_468]
0x180017b58  mov     [rsp+650h+var_600], rax
0x180017b5d  lea     rax, [rbp+4F0h+var_488]
0x180017b61  mov     [rsp+650h+var_608], rax
0x180017b66  lea     rax, [rbp+4F0h+var_4A8]
0x180017b6a  mov     [rsp+650h+var_610], rax
0x180017b6f  lea     rax, [rbp+4F0h+var_4C8]
0x180017b73  mov     [rsp+650h+var_618], rax
0x180017b78  lea     rax, [rbp+4F0h+var_4E8]
0x180017b7c  mov     [rsp+650h+var_620], rax
0x180017b81  lea     rax, [rbp+4F0h+var_508]
0x180017b85  mov     [rsp+650h+var_628], rax
0x180017b8a  lea     rax, [rbp+4F0h+var_528]
0x180017b8e  mov     [rsp+650h+var_630], rax
0x180017b93  lea     r9, [rbp+4F0h+var_548]
0x180017b97  lea     r8, [rbp+4F0h+var_568]
0x180017b9b  mov     rdx, rbx
0x180017b9e  mov     rcx, rdi
0x180017ba1  call    ??0BaseEapMethodConfig@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@1111111111111111111111111@Z; EapLm::Peer::BaseEapMethodConfig::BaseEapMethodConfig(_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x180017ba6  nop
0x180017ba7  lea     rcx, [rbp+4F0h+var_568]
0x180017bab  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017bb0  nop
0x180017bb1  lea     rcx, [rbp+4F0h+var_548]
0x180017bb5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017bba  nop
0x180017bbb  lea     rcx, [rbp+4F0h+var_528]
0x180017bbf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017bc4  nop
0x180017bc5  lea     rcx, [rbp+4F0h+var_508]
0x180017bc9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017bce  nop
0x180017bcf  lea     rcx, [rbp+4F0h+var_4E8]
0x180017bd3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017bd8  nop
0x180017bd9  lea     rcx, [rbp+4F0h+var_4C8]
0x180017bdd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017be2  nop
0x180017be3  lea     rcx, [rbp+4F0h+var_4A8]
0x180017be7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017bec  nop
0x180017bed  lea     rcx, [rbp+4F0h+var_488]
0x180017bf1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017bf6  nop
0x180017bf7  lea     rcx, [rbp+4F0h+var_468]
0x180017bfe  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017c03  nop
0x180017c04  lea     rcx, [rbp+4F0h+var_448]
0x180017c0b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017c10  nop
0x180017c11  lea     rcx, [rbp+4F0h+var_428]
0x180017c18  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017c1d  nop
0x180017c1e  lea     rcx, [rbp+4F0h+var_408]
0x180017c25  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017c2a  nop
0x180017c2b  lea     rcx, [rbp+4F0h+var_3E8]
0x180017c32  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017c37  nop
0x180017c38  lea     rcx, [rbp+4F0h+var_3C8]
0x180017c3f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017c44  nop
0x180017c45  lea     rcx, [rbp+4F0h+var_3A8]
0x180017c4c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017c51  nop
0x180017c52  lea     rcx, [rbp+4F0h+var_388]
0x180017c59  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017c5e  nop
0x180017c5f  lea     rcx, [rbp+4F0h+var_368]
0x180017c66  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017c6b  nop
0x180017c6c  lea     rcx, [rbp+4F0h+var_348]
0x180017c73  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017c78  nop
0x180017c79  lea     rcx, [rbp+4F0h+var_328]
0x180017c80  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017c85  nop
0x180017c86  lea     rcx, [rbp+4F0h+var_308]
0x180017c8d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017c92  nop
0x180017c93  lea     rcx, [rbp+4F0h+var_2E8]
0x180017c9a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017c9f  nop
0x180017ca0  lea     rcx, [rbp+4F0h+var_2C8]
0x180017ca7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017cac  nop
0x180017cad  lea     rcx, [rbp+4F0h+var_2A8]
0x180017cb4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017cb9  nop
0x180017cba  lea     rcx, [rbp+4F0h+var_288]
0x180017cc1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017cc6  nop
0x180017cc7  lea     rcx, [rbp+4F0h+var_268]
0x180017cce  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017cd3  nop
0x180017cd4  lea     rcx, [rbp+4F0h+var_248]
0x180017cdb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017ce0  lea     rax, ??_7LegacyEapMethodConfig@Peer@EapLm@@6B@; const EapLm::Peer::LegacyEapMethodConfig::`vftable'
0x180017ce7  mov     [rdi], rax
0x180017cea  movzx   eax, byte ptr [rdi+10h]
0x180017cee  mov     dword ptr [rsp+650h+var_630], eax
0x180017cf2  lea     r9, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Ra"...
0x180017cf9  lea     r8, aSD; "%s\\%d"
0x180017d00  mov     edx, 104h; unsigned __int64
0x180017d05  lea     rcx, [rbp+4F0h+var_220]; wchar_t *
0x180017d0c  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180017d11  test    eax, eax
0x180017d13  jns     short loc_180017D2F
0x180017d15  mov     r8d, 80070057h; int
0x180017d1b  lea     rdx, aEapmethodregpa; "eapMethodRegPath"
0x180017d22  lea     rcx, aLoadconfig; "LoadConfig"
0x180017d29  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180017d2f  lea     rcx, [rbp+4F0h+var_220]
0x180017d36  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180017d3b  mov     r8, rax
0x180017d3e  lea     rcx, [rdi+20h]
0x180017d42  lea     rdx, [rbp+4F0h+var_220]
0x180017d49  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180017d4e  nop
0x180017d4f  mov     rax, rdi
0x180017d52  mov     rcx, [rbp+4F0h+var_10]
0x180017d59  xor     rcx, rsp; StackCookie
0x180017d5c  call    __security_check_cookie
0x180017d61  lea     r11, [rsp+650h+var_s0]
0x180017d69  mov     rbx, [r11+18h]
0x180017d6d  mov     rdi, [r11+20h]
0x180017d71  mov     rsp, r11
0x180017d74  pop     rbp
0x180017d75  retn
```
