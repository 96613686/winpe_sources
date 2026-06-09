# EapLm::Peer::ThirdPartyEapMethodConfig::ThirdPartyEapMethodConfig(_EAP_METHOD_TYPE const &)

- ea: `0x18001e06c`
- end: `0x18001e6d8`
- name: `??0ThirdPartyEapMethodConfig@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z`
- size: `1644`
- prototype: `EapLm::Peer::ThirdPartyEapMethodConfig *__fastcall(EapLm::Peer::ThirdPartyEapMethodConfig *this, struct _EAP_METHOD_TYPE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016cf0`

## callees

- `0x1800017a0`
- `0x18000bf94`
- `0x18000d098`
- `0x18000eb94`
- `0x180016400`
- `0x18001b154`
- `0x18001e06c`
- `0x18001ff28`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001e5ae`
- `ntdll!EtwEventEnabled` at `0x18001e64d`
- `ntdll!EtwEventEnabled` at `0x18001e5ae`
- `ntdll!EtwEventEnabled` at `0x18001e64d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001e560`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001e560`

## string_xrefs

- `0x18001e251`: `PeerDllPath`
- `0x18001e65b`: `ThirdPartyEapMethodConfig : CoInitialize succeeded with %d`
- `0x18001e5c0`: `ThirdPartyEapMethodConfig : CoInitialize failed with %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
EapLm::Peer::ThirdPartyEapMethodConfig *__fastcall EapLm::Peer::ThirdPartyEapMethodConfig::ThirdPartyEapMethodConfig(
        EapLm::Peer::ThirdPartyEapMethodConfig *this,
        struct _EAP_METHOD_TYPE *a2)
{
  EapLm::Peer::ThirdPartyEapMethodConfig *v3; // rdi
  unsigned int v4; // eax
  unsigned __int16 v5; // bx
  _BYTE v9[32]; // [rsp+E8h] [rbp-B60h] BYREF
  _BYTE v10[32]; // [rsp+108h] [rbp-B40h] BYREF
  _BYTE v11[32]; // [rsp+128h] [rbp-B20h] BYREF
  _BYTE v12[32]; // [rsp+148h] [rbp-B00h] BYREF
  _BYTE v13[32]; // [rsp+168h] [rbp-AE0h] BYREF
  _BYTE v14[32]; // [rsp+188h] [rbp-AC0h] BYREF
  _BYTE v15[32]; // [rsp+1A8h] [rbp-AA0h] BYREF
  _BYTE v16[32]; // [rsp+1C8h] [rbp-A80h] BYREF
  _BYTE v17[32]; // [rsp+1E8h] [rbp-A60h] BYREF
  _BYTE v18[32]; // [rsp+208h] [rbp-A40h] BYREF
  _BYTE v19[32]; // [rsp+228h] [rbp-A20h] BYREF
  _BYTE v20[32]; // [rsp+248h] [rbp-A00h] BYREF
  _BYTE v21[32]; // [rsp+268h] [rbp-9E0h] BYREF
  _BYTE v22[32]; // [rsp+288h] [rbp-9C0h] BYREF
  _BYTE v23[32]; // [rsp+2A8h] [rbp-9A0h] BYREF
  _BYTE v24[32]; // [rsp+2C8h] [rbp-980h] BYREF
  _BYTE v25[32]; // [rsp+2E8h] [rbp-960h] BYREF
  _BYTE v26[32]; // [rsp+308h] [rbp-940h] BYREF
  _BYTE v27[32]; // [rsp+328h] [rbp-920h] BYREF
  _BYTE v28[32]; // [rsp+348h] [rbp-900h] BYREF
  _BYTE v29[32]; // [rsp+368h] [rbp-8E0h] BYREF
  _BYTE v30[32]; // [rsp+388h] [rbp-8C0h] BYREF
  _BYTE v31[32]; // [rsp+3A8h] [rbp-8A0h] BYREF
  _BYTE v32[32]; // [rsp+3C8h] [rbp-880h] BYREF
  _BYTE v33[32]; // [rsp+3E8h] [rbp-860h] BYREF
  char v34[40]; // [rsp+408h] [rbp-840h] BYREF
  char v35[2048]; // [rsp+430h] [rbp-818h] BYREF

  v3 = this;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v34,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v33,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v32,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v31,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v30,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v29,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v28,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v27,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v26,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v25,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v24,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v23,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v22,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v21,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v20,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v19,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v18,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v17,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v16,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v15,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v14,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v13,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v12,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v11,
    (__int64)&qword_18003A720);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v10,
    (__int64)L"PeerFriendlyName");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)v9,
    (__int64)L"PeerDllPath");
  EapLm::Peer::BaseEapMethodConfig::BaseEapMethodConfig(
    (__int64)v3,
    a2,
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
    (__int64)v32,
    (__int64)v33,
    (__int64)v34);
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
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v33);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v34);
  *(_QWORD *)v3 = &EapLm::Peer::ThirdPartyEapMethodConfig::`vftable';
  *((_DWORD *)v3 + 322) = 0;
  v4 = CoInitializeEx(0, 2u);
  try
  {
    v5 = v4;
    if ( v4 <= 1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids, v4);
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(v35, 0x800u, "ThirdPartyEapMethodConfig : CoInitialize succeeded with %d", v5) >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v35);
      }
      *((_DWORD *)v3 + 322) = 1;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids, v4);
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(v35, 0x800u, "ThirdPartyEapMethodConfig : CoInitialize failed with %d", v5) >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v35);
      }
    }
  }
  catch ( Exception )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids);
    return this;
  }
  v5 = v4;
}

```

## disassembly

```asm
0x18001e06c  mov     r11, rsp
0x18001e06f  mov     [r11+10h], rbx
0x18001e073  mov     [r11+18h], rsi
0x18001e077  push    rdi
0x18001e078  sub     rsp, 0C40h
0x18001e07f  mov     rax, cs:__security_cookie
0x18001e086  xor     rax, rsp
0x18001e089  mov     [rsp+0C48h+var_18], rax
0x18001e091  mov     rbx, rdx
0x18001e094  mov     rdi, rcx
0x18001e097  mov     [r11-0B68h], rcx
0x18001e09e  lea     rsi, qword_18003A720
0x18001e0a5  mov     rdx, rsi
0x18001e0a8  lea     rcx, [r11-840h]
0x18001e0af  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e0b4  nop
0x18001e0b5  mov     rdx, rsi
0x18001e0b8  lea     rcx, [rsp+0C48h+var_860]
0x18001e0c0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e0c5  nop
0x18001e0c6  mov     rdx, rsi
0x18001e0c9  lea     rcx, [rsp+0C48h+var_880]
0x18001e0d1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e0d6  nop
0x18001e0d7  mov     rdx, rsi
0x18001e0da  lea     rcx, [rsp+0C48h+var_8A0]
0x18001e0e2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e0e7  nop
0x18001e0e8  mov     rdx, rsi
0x18001e0eb  lea     rcx, [rsp+0C48h+var_8C0]
0x18001e0f3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e0f8  nop
0x18001e0f9  mov     rdx, rsi
0x18001e0fc  lea     rcx, [rsp+0C48h+var_8E0]
0x18001e104  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e109  nop
0x18001e10a  mov     rdx, rsi
0x18001e10d  lea     rcx, [rsp+0C48h+var_900]
0x18001e115  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e11a  nop
0x18001e11b  mov     rdx, rsi
0x18001e11e  lea     rcx, [rsp+0C48h+var_920]
0x18001e126  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e12b  nop
0x18001e12c  mov     rdx, rsi
0x18001e12f  lea     rcx, [rsp+0C48h+var_940]
0x18001e137  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e13c  nop
0x18001e13d  mov     rdx, rsi
0x18001e140  lea     rcx, [rsp+0C48h+var_960]
0x18001e148  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e14d  nop
0x18001e14e  mov     rdx, rsi
0x18001e151  lea     rcx, [rsp+0C48h+var_980]
0x18001e159  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e15e  nop
0x18001e15f  mov     rdx, rsi
0x18001e162  lea     rcx, [rsp+0C48h+var_9A0]
0x18001e16a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e16f  nop
0x18001e170  mov     rdx, rsi
0x18001e173  lea     rcx, [rsp+0C48h+var_9C0]
0x18001e17b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e180  nop
0x18001e181  mov     rdx, rsi
0x18001e184  lea     rcx, [rsp+0C48h+var_9E0]
0x18001e18c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e191  nop
0x18001e192  mov     rdx, rsi
0x18001e195  lea     rcx, [rsp+0C48h+var_A00]
0x18001e19d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e1a2  nop
0x18001e1a3  mov     rdx, rsi
0x18001e1a6  lea     rcx, [rsp+0C48h+var_A20]
0x18001e1ae  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e1b3  nop
0x18001e1b4  mov     rdx, rsi
0x18001e1b7  lea     rcx, [rsp+0C48h+var_A40]
0x18001e1bf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e1c4  nop
0x18001e1c5  mov     rdx, rsi
0x18001e1c8  lea     rcx, [rsp+0C48h+var_A60]
0x18001e1d0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e1d5  nop
0x18001e1d6  mov     rdx, rsi
0x18001e1d9  lea     rcx, [rsp+0C48h+var_A80]
0x18001e1e1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e1e6  nop
0x18001e1e7  mov     rdx, rsi
0x18001e1ea  lea     rcx, [rsp+0C48h+var_AA0]
0x18001e1f2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e1f7  nop
0x18001e1f8  mov     rdx, rsi
0x18001e1fb  lea     rcx, [rsp+0C48h+var_AC0]
0x18001e203  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e208  nop
0x18001e209  mov     rdx, rsi
0x18001e20c  lea     rcx, [rsp+0C48h+var_AE0]
0x18001e214  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e219  nop
0x18001e21a  mov     rdx, rsi
0x18001e21d  lea     rcx, [rsp+0C48h+var_B00]
0x18001e225  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e22a  nop
0x18001e22b  mov     rdx, rsi
0x18001e22e  lea     rcx, [rsp+0C48h+var_B20]
0x18001e236  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e23b  nop
0x18001e23c  lea     rdx, aPeerfriendlyna; "PeerFriendlyName"
0x18001e243  lea     rcx, [rsp+0C48h+var_B40]
0x18001e24b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e250  nop
0x18001e251  lea     rdx, aPeerdllpath; "PeerDllPath"
0x18001e258  lea     rcx, [rsp+0C48h+var_B60]
0x18001e260  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001e265  nop
0x18001e266  lea     rax, [rsp+0C48h+var_840]
0x18001e26e  mov     [rsp+0C48h+var_B70], rax
0x18001e276  lea     rax, [rsp+0C48h+var_860]
0x18001e27e  mov     [rsp+0C48h+var_B78], rax
0x18001e286  lea     rax, [rsp+0C48h+var_880]
0x18001e28e  mov     [rsp+0C48h+var_B80], rax
0x18001e296  lea     rax, [rsp+0C48h+var_8A0]
0x18001e29e  mov     [rsp+0C48h+var_B88], rax
0x18001e2a6  lea     rax, [rsp+0C48h+var_8C0]
0x18001e2ae  mov     [rsp+0C48h+var_B90], rax
0x18001e2b6  lea     rax, [rsp+0C48h+var_8E0]
0x18001e2be  mov     [rsp+0C48h+var_B98], rax
0x18001e2c6  lea     rax, [rsp+0C48h+var_900]
0x18001e2ce  mov     [rsp+0C48h+var_BA0], rax
0x18001e2d6  lea     rax, [rsp+0C48h+var_920]
0x18001e2de  mov     [rsp+0C48h+var_BA8], rax
0x18001e2e6  lea     rax, [rsp+0C48h+var_940]
0x18001e2ee  mov     [rsp+0C48h+var_BB0], rax
0x18001e2f6  lea     rax, [rsp+0C48h+var_960]
0x18001e2fe  mov     [rsp+0C48h+var_BB8], rax
0x18001e306  lea     rax, [rsp+0C48h+var_980]
0x18001e30e  mov     [rsp+0C48h+var_BC0], rax
0x18001e316  lea     rax, [rsp+0C48h+var_9A0]
0x18001e31e  mov     [rsp+0C48h+var_BC8], rax
0x18001e326  lea     rax, [rsp+0C48h+var_9C0]
0x18001e32e  mov     [rsp+0C48h+var_BD0], rax
0x18001e333  lea     rax, [rsp+0C48h+var_9E0]
0x18001e33b  mov     [rsp+0C48h+var_BD8], rax
0x18001e340  lea     rax, [rsp+0C48h+var_A00]
0x18001e348  mov     [rsp+0C48h+var_BE0], rax
0x18001e34d  lea     rax, [rsp+0C48h+var_A20]
0x18001e355  mov     [rsp+0C48h+var_BE8], rax
0x18001e35a  lea     rax, [rsp+0C48h+var_A40]
0x18001e362  mov     [rsp+0C48h+var_BF0], rax
0x18001e367  lea     rax, [rsp+0C48h+var_A60]
0x18001e36f  mov     [rsp+0C48h+var_BF8], rax
0x18001e374  lea     rax, [rsp+0C48h+var_A80]
0x18001e37c  mov     [rsp+0C48h+var_C00], rax
0x18001e381  lea     rax, [rsp+0C48h+var_AA0]
0x18001e389  mov     [rsp+0C48h+var_C08], rax
0x18001e38e  lea     rax, [rsp+0C48h+var_AC0]
0x18001e396  mov     [rsp+0C48h+var_C10], rax
0x18001e39b  lea     rax, [rsp+0C48h+var_AE0]
0x18001e3a3  mov     [rsp+0C48h+var_C18], rax
0x18001e3a8  lea     rax, [rsp+0C48h+var_B00]
0x18001e3b0  mov     [rsp+0C48h+var_C20], rax
0x18001e3b5  lea     rax, [rsp+0C48h+var_B20]
0x18001e3bd  mov     [rsp+0C48h+var_C28], rax
0x18001e3c2  lea     r9, [rsp+0C48h+var_B40]
0x18001e3ca  lea     r8, [rsp+0C48h+var_B60]
0x18001e3d2  mov     rdx, rbx
0x18001e3d5  mov     rcx, rdi
0x18001e3d8  call    ??0BaseEapMethodConfig@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@1111111111111111111111111@Z; EapLm::Peer::BaseEapMethodConfig::BaseEapMethodConfig(_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001e3dd  nop
0x18001e3de  lea     rcx, [rsp+0C48h+var_B60]
0x18001e3e6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e3eb  nop
0x18001e3ec  lea     rcx, [rsp+0C48h+var_B40]
0x18001e3f4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e3f9  nop
0x18001e3fa  lea     rcx, [rsp+0C48h+var_B20]
0x18001e402  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e407  nop
0x18001e408  lea     rcx, [rsp+0C48h+var_B00]
0x18001e410  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e415  nop
0x18001e416  lea     rcx, [rsp+0C48h+var_AE0]
0x18001e41e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e423  nop
0x18001e424  lea     rcx, [rsp+0C48h+var_AC0]
0x18001e42c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e431  nop
0x18001e432  lea     rcx, [rsp+0C48h+var_AA0]
0x18001e43a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e43f  nop
0x18001e440  lea     rcx, [rsp+0C48h+var_A80]
0x18001e448  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e44d  nop
0x18001e44e  lea     rcx, [rsp+0C48h+var_A60]
0x18001e456  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e45b  nop
0x18001e45c  lea     rcx, [rsp+0C48h+var_A40]
0x18001e464  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e469  nop
0x18001e46a  lea     rcx, [rsp+0C48h+var_A20]
0x18001e472  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e477  nop
0x18001e478  lea     rcx, [rsp+0C48h+var_A00]
0x18001e480  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e485  nop
0x18001e486  lea     rcx, [rsp+0C48h+var_9E0]
0x18001e48e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e493  nop
0x18001e494  lea     rcx, [rsp+0C48h+var_9C0]
0x18001e49c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e4a1  nop
0x18001e4a2  lea     rcx, [rsp+0C48h+var_9A0]
0x18001e4aa  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e4af  nop
0x18001e4b0  lea     rcx, [rsp+0C48h+var_980]
0x18001e4b8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e4bd  nop
0x18001e4be  lea     rcx, [rsp+0C48h+var_960]
0x18001e4c6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e4cb  nop
0x18001e4cc  lea     rcx, [rsp+0C48h+var_940]
0x18001e4d4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e4d9  nop
0x18001e4da  lea     rcx, [rsp+0C48h+var_920]
0x18001e4e2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e4e7  nop
0x18001e4e8  lea     rcx, [rsp+0C48h+var_900]
0x18001e4f0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e4f5  nop
0x18001e4f6  lea     rcx, [rsp+0C48h+var_8E0]
0x18001e4fe  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e503  nop
0x18001e504  lea     rcx, [rsp+0C48h+var_8C0]
0x18001e50c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e511  nop
0x18001e512  lea     rcx, [rsp+0C48h+var_8A0]
0x18001e51a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e51f  nop
0x18001e520  lea     rcx, [rsp+0C48h+var_880]
0x18001e528  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e52d  nop
0x18001e52e  lea     rcx, [rsp+0C48h+var_860]
0x18001e536  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e53b  nop
0x18001e53c  lea     rcx, [rsp+0C48h+var_840]
0x18001e544  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001e549  lea     rax, ??_7ThirdPartyEapMethodConfig@Peer@EapLm@@6B@; const EapLm::Peer::ThirdPartyEapMethodConfig::`vftable'
0x18001e550  mov     [rdi], rax
0x18001e553  xor     esi, esi
0x18001e555  mov     [rdi+508h], esi
0x18001e55b  lea     edx, [rsi+2]; dwCoInit
0x18001e55e  xor     ecx, ecx; pvReserved
0x18001e560  call    cs:__imp_CoInitializeEx
0x18001e566  mov     ebx, eax
0x18001e568  cmp     eax, 1
0x18001e56b  jbe     loc_18001E60E
0x18001e571  lea     rax, WPP_GLOBAL_Control
0x18001e578  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e57f  cmp     rcx, rax
0x18001e582  jz      short loc_18001E5A0
0x18001e584  test    byte ptr [rcx+1Ch], 4
0x18001e588  jz      short loc_18001E5A0
0x18001e58a  lea     edx, [rsi+0Bh]
0x18001e58d  mov     r9d, ebx
0x18001e590  lea     r8, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids
0x18001e597  mov     rcx, [rcx+10h]
0x18001e59b  call    WPP_SF_d
0x18001e5a0  lea     rdx, DebugInfoEvent
0x18001e5a7  mov     rcx, cs:eaphost_Context
0x18001e5ae  call    cs:__imp_EtwEventEnabled
0x18001e5b4  test    al, al
0x18001e5b6  jz      loc_18001E6A6
0x18001e5bc  movzx   r9d, bx
0x18001e5c0  lea     r8, aThirdpartyeapm_0; "ThirdPartyEapMethodConfig : CoInitializ"...
0x18001e5c7  mov     edx, 800h; unsigned __int64
0x18001e5cc  lea     rcx, [rsp+0C48h+var_818]; char *
0x18001e5d4  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001e5d9  test    eax, eax
0x18001e5db  js      loc_18001E6A6
0x18001e5e1  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x18001e5e8  jge     loc_18001E6A6
0x18001e5ee  lea     r8, [rsp+0C48h+var_818]
0x18001e5f6  lea     rdx, DebugInfoEvent
0x18001e5fd  lea     rcx, eaphost_Context
0x18001e604  call    McTemplateU0s_EtwEventWriteTransfer
0x18001e609  jmp     loc_18001E6A6
0x18001e60e  lea     rax, WPP_GLOBAL_Control
0x18001e615  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e61c  cmp     rcx, rax
0x18001e61f  jz      short loc_18001E63F
0x18001e621  test    byte ptr [rcx+1Ch], 4
0x18001e625  jz      short loc_18001E63F
0x18001e627  mov     edx, 0Ah
0x18001e62c  mov     r9d, ebx
0x18001e62f  lea     r8, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids
0x18001e636  mov     rcx, [rcx+10h]
0x18001e63a  call    WPP_SF_d
0x18001e63f  lea     rdx, DebugInfoEvent
0x18001e646  mov     rcx, cs:eaphost_Context
  ... truncated ...
```
