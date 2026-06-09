# LogINetworkInterface1(INetworkInterfacePrivate *,ulong)

- ea: `0x180036a3c`
- end: `0x180037427`
- name: `?LogINetworkInterface1@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUINetworkInterfacePrivate@@K@Z`
- size: `2539`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003500c`
- `0x18003580c`

## callees

- `0x18000f388`
- `0x18000f700`
- `0x1800100d8`
- `0x180010124`
- `0x180011614`
- `0x1800120d0`
- `0x180034dac`
- `0x1800351d0`
- `0x1800353a4`
- `0x180036a3c`
- `0x180037430`
- `0x180037c74`
- `0x180037e9c`
- `0x180037fc0`
- `0x18003830c`
- `0x180038338`
- `0x1800384d0`
- `0x18003a37c`
- `0x18003a624`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800373e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800373e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=43
__int64 __fastcall LogINetworkInterface1(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rax
  const wchar_t *v9; // r8
  __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  _BYTE *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rax
  __int64 v35; // r14
  __int64 v36; // r13
  __int64 v37; // rax
  const wchar_t *v38; // r8
  __int64 v39; // rsi
  __int64 v40; // rax
  __int64 v41; // rdi
  __int64 v42; // rax
  __int64 v43; // rbx
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rcx
  void *v48; // rcx
  _BYTE v50[32]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+80h] [rbp-80h] BYREF
  __int64 v52; // [rsp+88h] [rbp-78h]
  __int64 v53; // [rsp+98h] [rbp-68h]
  _BYTE v54[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v55[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v56[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v57[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v58[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v59[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v60[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v61[32]; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v62; // [rsp+1A0h] [rbp+A0h] BYREF
  int v63; // [rsp+1A4h] [rbp+A4h] BYREF
  LPVOID pv; // [rsp+1A8h] [rbp+A8h] BYREF
  int v65; // [rsp+1B0h] [rbp+B0h] BYREF
  int v66; // [rsp+1B4h] [rbp+B4h] BYREF
  __int64 v67; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v68; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v69[16]; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v70; // [rsp+1D8h] [rbp+D8h]
  _BYTE v71[32]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v72[16]; // [rsp+208h] [rbp+108h] BYREF
  __int64 v73; // [rsp+218h] [rbp+118h]
  __int128 v74; // [rsp+228h] [rbp+128h] BYREF
  __int128 v75; // [rsp+238h] [rbp+138h] BYREF
  _BYTE v76[32]; // [rsp+248h] [rbp+148h] BYREF
  _BYTE v77[32]; // [rsp+268h] [rbp+168h] BYREF
  _BYTE v78[32]; // [rsp+288h] [rbp+188h] BYREF
  _BYTE v79[32]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v80[32]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _BYTE v81[32]; // [rsp+2E8h] [rbp+1E8h] BYREF
  _BYTE v82[32]; // [rsp+308h] [rbp+208h] BYREF
  _BYTE v83[32]; // [rsp+328h] [rbp+228h] BYREF
  _OWORD v84[3]; // [rsp+348h] [rbp+248h] BYREF
  __int64 v85; // [rsp+378h] [rbp+278h]
  _BYTE v86[32]; // [rsp+380h] [rbp+280h] BYREF

  v52 = a1;
  std::wstring::wstring((__int64)v79);
  v63 = 0;
  pv = 0;
  if ( (*(int (__fastcall **)(__int64, int *, LPVOID *))(*(_QWORD *)v6 + 24LL))(a2, &v63, &pv) < 0 )
  {
    v7 = wil::str_printf<std::wstring>((__int64)v54, (__int64)L"  ! <INetworkInterfacePrivate::GetId failed (0x%x)>", 1);
    std::wstring::operator=((__int64)v79, v7);
    std::wstring::_Tidy_deallocate((__int64)v54);
  }
  std::wstring::wstring((__int64)v78);
  if ( v63 != 84 )
  {
    v8 = wil::str_printf<std::wstring>(
           (__int64)v54,
           (__int64)L"<INetworkInterfacePrivate::GetId returned a byte buffer of an unexpected size: expected %u, but returned %u>");
    std::wstring::operator=((__int64)v78, v8);
    std::wstring::_Tidy_deallocate((__int64)v54);
  }
  v9 = L"True";
  if ( !*((_DWORD *)pv + 20) )
    v9 = L"False";
  ToStringCheckingErrors(v50, v78, v9);
  v10 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v11 = ToString(v55, (char *)pv + 32, 48);
  ToStringCheckingErrors(v59, v78, v11);
  v12 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v13 = ToString(v58, (char *)pv + 16);
  ToStringCheckingErrors(v57, v79, v13);
  v14 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v15 = ToString(v56, pv);
  ToStringCheckingErrors(v54, v79, v15);
  v16 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  wil::str_printf<std::wstring>(
    (__int64)v86,
    (__int64)L"    Network Interface Id:\n"
              "      InterfaceGuid: %ws\n"
              "      profileId: %ws\n"
              "      Signature: %ws\n"
              "      Unmanaged: %ws\n",
    v16,
    v14,
    v12,
    v10);
  std::wstring::_Tidy_deallocate((__int64)v54);
  std::wstring::_Tidy_deallocate((__int64)v56);
  std::wstring::_Tidy_deallocate((__int64)v57);
  std::wstring::_Tidy_deallocate((__int64)v58);
  std::wstring::_Tidy_deallocate((__int64)v59);
  std::wstring::_Tidy_deallocate((__int64)v55);
  std::wstring::_Tidy_deallocate((__int64)v50);
  std::wstring::wstring((__int64)v69);
  v62 = 0;
  if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 64LL))(a2, &v62) < 0 )
  {
    v17 = wil::str_printf<std::wstring>(
            (__int64)v50,
            (__int64)L"  ! <INetworkInterfacePrivate::GetCost failed (0x%x)>",
            1);
    std::wstring::operator=((__int64)v69, v17);
    std::wstring::_Tidy_deallocate((__int64)v50);
  }
  std::wstring::wstring((__int64)v72);
  memset(v84, 0, sizeof(v84));
  v85 = 0;
  if ( (*(int (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)a2 + 72LL))(a2, v84) < 0 )
  {
    v18 = wil::str_printf<std::wstring>(
            (__int64)v50,
            (__int64)L"  ! <INetworkInterfacePrivate::GetDataPlanStatus failed (0x%x)>",
            1);
    std::wstring::operator=((__int64)v72, v18);
    std::wstring::_Tidy_deallocate((__int64)v50);
  }
  std::wstring::wstring((__int64)v71);
  if ( !v73 )
  {
    if ( v70 )
    {
      v19 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      v20 = Log(v50, v84, v19);
    }
    else
    {
      v20 = Log(v50, v84, v62);
    }
    goto LABEL_14;
  }
  v22 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  if ( v70 )
  {
    v23 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    v20 = wil::str_printf<std::wstring>(
            (__int64)v50,
            (__int64)L"    DataPlanStatus:\n      Cost: %ws\n      DataplanStatus: %ws\n",
            v23);
LABEL_14:
    std::wstring::operator=((__int64)v71, v20);
    v21 = v50;
    goto LABEL_19;
  }
  v24 = v22;
  LODWORD(v51) = v62;
  ToString(v55, &v51);
  v25 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v26 = wil::str_printf<std::wstring>(
          (__int64)v50,
          (__int64)L"    DataPlanStatus:\n      Cost: %ws\n      DataplanStatus: %ws\n",
          v25,
          v24);
  std::wstring::operator=((__int64)v71, v26);
  std::wstring::_Tidy_deallocate((__int64)v50);
  v21 = v55;
LABEL_19:
  std::wstring::_Tidy_deallocate((__int64)v21);
  std::wstring::wstring((__int64)v83);
  v75 = 0;
  if ( (*(int (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 32LL))(a2, &v75) < 0 )
  {
    v27 = wil::str_printf<std::wstring>(
            (__int64)v50,
            (__int64)L"  ! <INetworkInterfacePrivate::GetInterfaceGuid failed (0x%x)>",
            1);
    std::wstring::operator=((__int64)v83, v27);
    std::wstring::_Tidy_deallocate((__int64)v50);
  }
  std::wstring::wstring((__int64)v82);
  v74 = 0;
  if ( (*(int (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 40LL))(a2, &v74) < 0 )
  {
    v28 = wil::str_printf<std::wstring>(
            (__int64)v50,
            (__int64)L"  ! <INetworkInterfacePrivate::GetNetworkId failed (0x%x)>",
            1);
    std::wstring::operator=((__int64)v82, v28);
    std::wstring::_Tidy_deallocate((__int64)v50);
  }
  std::wstring::wstring((__int64)v81);
  v66 = 0;
  if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 56LL))(a2, &v66) < 0 )
  {
    v29 = wil::str_printf<std::wstring>(
            (__int64)v50,
            (__int64)L"  ! <INetworkInterfacePrivate::GetState failed (0x%x)>",
            1);
    std::wstring::operator=((__int64)v81, v29);
    std::wstring::_Tidy_deallocate((__int64)v50);
  }
  std::wstring::wstring((__int64)v80);
  v65 = 0;
  if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 48LL))(a2, &v65) < 0 )
  {
    v30 = wil::str_printf<std::wstring>(
            (__int64)v50,
            (__int64)L"  ! <INetworkInterfacePrivate::GetType failed (0x%x)>",
            1);
    std::wstring::operator=((__int64)v80, v30);
    std::wstring::_Tidy_deallocate((__int64)v50);
  }
  std::wstring::wstring((__int64)v77);
  v68 = 0;
  v31 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a2)(
          a2,
          &GUID_84d31176_4a5a_4419_b07f_809fba936a0a,
          &v68);
  if ( v31 < 0 )
  {
    v32 = wil::str_printf<std::wstring>(
            (__int64)v50,
            (__int64)L"  ! <INetworkInterfacePrivate::QueryInterface(INetworkInterfacePrivate2) failed (0x%x)>",
            (unsigned int)v31);
    std::wstring::operator=((__int64)v77, v32);
    std::wstring::_Tidy_deallocate((__int64)v50);
  }
  if ( v68 )
  {
    std::wstring::push_back(v77);
    LogINetworkInterface2(v50, v68, a3);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)v50);
  }
  std::wstring::wstring((__int64)v76);
  v67 = 0;
  v33 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a2)(
          a2,
          &GUID_85d85ddf_7da6_499e_ba87_b58af906435f,
          &v67);
  if ( v33 < 0 )
  {
    v34 = wil::str_printf<std::wstring>(
            (__int64)v50,
            (__int64)L"  ! <INetworkInterfacePrivate::QueryInterface(INetworkInterfacePrivate3) failed (0x%x)>",
            (unsigned int)v33);
    std::wstring::operator=((__int64)v76, v34);
    std::wstring::_Tidy_deallocate((__int64)v50);
  }
  if ( v67 )
  {
    std::wstring::push_back(v76);
    LogINetworkInterface3(v50, v67, a3);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)v50);
  }
  v35 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v36 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v53 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v52 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  LODWORD(v51) = v62;
  v37 = ToString(v61, &v51);
  ToStringCheckingErrors(v60, v69, v37);
  v51 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  if ( v65 )
  {
    if ( v65 == 1 )
    {
      v38 = L"Managed";
    }
    else if ( v65 == 2 )
    {
      v38 = L"Domain Authenticated";
    }
    else
    {
      v38 = L"(unknown NP_NETWORK_INTERFACE_TYPE)";
    }
  }
  else
  {
    v38 = L"Unmanaged";
  }
  ToStringCheckingErrors(v54, v80, v38);
  v39 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v40 = ToString(v56, &v66);
  ToStringCheckingErrors(v57, v81, v40);
  v41 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v42 = ToString(v58, &v74);
  ToStringCheckingErrors(v59, v82, v42);
  v43 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v44 = ToString(v55, &v75);
  ToStringCheckingErrors(v50, v83, v44);
  v45 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  wil::str_printf<std::wstring>(
    a1,
    (__int64)L"\n"
              " >>>>>> INetworkInterfacePrivate [%u] <<<<<< \n"
              "    InterfaceGuid (Interface GUID): %ws\n"
              "    NetworkId: %ws\n"
              "    Interface State: %ws\n"
              "    Interface Type: %ws\n"
              "    Cost: %ws\n"
              "%ws%ws%ws%ws",
    a3,
    v45,
    v43,
    v41,
    v39,
    v51,
    v52,
    v53,
    v36,
    v35);
  std::wstring::_Tidy_deallocate((__int64)v50);
  std::wstring::_Tidy_deallocate((__int64)v55);
  std::wstring::_Tidy_deallocate((__int64)v59);
  std::wstring::_Tidy_deallocate((__int64)v58);
  std::wstring::_Tidy_deallocate((__int64)v57);
  std::wstring::_Tidy_deallocate((__int64)v56);
  std::wstring::_Tidy_deallocate((__int64)v54);
  std::wstring::_Tidy_deallocate((__int64)v60);
  std::wstring::_Tidy_deallocate((__int64)v61);
  v46 = v67;
  if ( v67 )
  {
    v67 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  std::wstring::_Tidy_deallocate((__int64)v76);
  v47 = v68;
  if ( v68 )
  {
    v68 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  std::wstring::_Tidy_deallocate((__int64)v77);
  std::wstring::_Tidy_deallocate((__int64)v80);
  std::wstring::_Tidy_deallocate((__int64)v81);
  std::wstring::_Tidy_deallocate((__int64)v82);
  std::wstring::_Tidy_deallocate((__int64)v83);
  std::wstring::_Tidy_deallocate((__int64)v71);
  std::wstring::_Tidy_deallocate((__int64)v72);
  std::wstring::_Tidy_deallocate((__int64)v69);
  std::wstring::_Tidy_deallocate((__int64)v86);
  std::wstring::_Tidy_deallocate((__int64)v78);
  v48 = pv;
  pv = 0;
  if ( v48 )
    CoTaskMemFree(v48);
  std::wstring::_Tidy_deallocate((__int64)v79);
  return a1;
}

```

## disassembly

```asm
0x180036a3c  mov     [rsp-8+arg_18], rbx
0x180036a41  push    rbp
0x180036a42  push    rsi
0x180036a43  push    rdi
0x180036a44  push    r12
0x180036a46  push    r13
0x180036a48  push    r14
0x180036a4a  push    r15
0x180036a4c  lea     rbp, [rsp-2B0h]
0x180036a54  sub     rsp, 3B0h
0x180036a5b  mov     rax, cs:__security_cookie
0x180036a62  xor     rax, rsp
0x180036a65  mov     [rbp+2E0h+var_40], rax
0x180036a6c  mov     r12d, r8d
0x180036a6f  mov     r14, rdx
0x180036a72  mov     r15, rcx
0x180036a75  mov     [rbp+2E0h+var_358], rcx
0x180036a79  xor     r13d, r13d
0x180036a7c  lea     rcx, [rbp+2E0h+var_138]
0x180036a83  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180036a88  nop
0x180036a89  mov     [rbp+2E0h+var_23C], r13d
0x180036a90  mov     [rbp+2E0h+pv], r13
0x180036a97  mov     rax, [rdx]
0x180036a9a  lea     r8, [rbp+2E0h+pv]
0x180036aa1  lea     rdx, [rbp+2E0h+var_23C]
0x180036aa8  mov     rcx, r14
0x180036aab  mov     rax, [rax+18h]
0x180036aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ab4  test    eax, eax
0x180036ab6  jns     short loc_180036AE4
0x180036ab8  lea     r8d, [r13+1]
0x180036abc  lea     rdx, aInetworkinterf_14; "  ! <INetworkInterfacePrivate::GetId fa"...
0x180036ac3  lea     rcx, [rbp+2E0h+var_340]
0x180036ac7  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180036acc  mov     rdx, rax
0x180036acf  lea     rcx, [rbp+2E0h+var_138]
0x180036ad6  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180036adb  lea     rcx, [rbp+2E0h+var_340]
0x180036adf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036ae4  lea     rcx, [rbp+2E0h+var_158]
0x180036aeb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180036af0  nop
0x180036af1  mov     r9d, [rbp+2E0h+var_23C]
0x180036af8  mov     r8d, 54h ; 'T'
0x180036afe  cmp     r9d, r8d
0x180036b01  jz      short loc_180036B2B
0x180036b03  lea     rdx, aInetworkinterf_1; "<INetworkInterfacePrivate::GetId return"...
0x180036b0a  lea     rcx, [rbp+2E0h+var_340]
0x180036b0e  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180036b13  mov     rdx, rax
0x180036b16  lea     rcx, [rbp+2E0h+var_158]
0x180036b1d  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180036b22  lea     rcx, [rbp+2E0h+var_340]
0x180036b26  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036b2b  mov     rax, [rbp+2E0h+pv]
0x180036b32  lea     rcx, aFalse_1; "False"
0x180036b39  lea     r8, aTrue_1; "True"
0x180036b40  cmp     [rax+50h], r13d
0x180036b44  cmovz   r8, rcx
0x180036b48  lea     rdx, [rbp+2E0h+var_158]
0x180036b4f  lea     rcx, [rsp+3E0h+var_380]
0x180036b54  call    ?ToStringCheckingErrors@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV12@PEB_W@Z; ToStringCheckingErrors(std::wstring const &,wchar_t const *)
0x180036b59  nop
0x180036b5a  mov     rcx, rax
0x180036b5d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180036b62  mov     rsi, rax
0x180036b65  mov     rdx, [rbp+2E0h+pv]
0x180036b6c  add     rdx, 20h ; ' '
0x180036b70  mov     r8d, 30h ; '0'
0x180036b76  lea     rcx, [rbp+2E0h+var_320]
0x180036b7a  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBEK@Z; ToString(uchar const *,ulong)
0x180036b7f  nop
0x180036b80  mov     r8, rax
0x180036b83  lea     rdx, [rbp+2E0h+var_158]
0x180036b8a  lea     rcx, [rbp+2E0h+var_2A0]
0x180036b8e  call    ?ToStringCheckingErrors@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV12@0@Z; ToStringCheckingErrors(std::wstring const &,std::wstring const &)
0x180036b93  nop
0x180036b94  mov     rcx, rax
0x180036b97  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180036b9c  mov     rdi, rax
0x180036b9f  mov     rdx, [rbp+2E0h+pv]
0x180036ba6  add     rdx, 10h
0x180036baa  lea     rcx, [rbp+2E0h+var_2C0]
0x180036bae  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; ToString(_GUID const &)
0x180036bb3  nop
0x180036bb4  mov     r8, rax
0x180036bb7  lea     rdx, [rbp+2E0h+var_138]
0x180036bbe  lea     rcx, [rbp+2E0h+var_2E0]
0x180036bc2  call    ?ToStringCheckingErrors@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV12@0@Z; ToStringCheckingErrors(std::wstring const &,std::wstring const &)
0x180036bc7  nop
0x180036bc8  mov     rcx, rax
0x180036bcb  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180036bd0  mov     rbx, rax
0x180036bd3  mov     rdx, [rbp+2E0h+pv]
0x180036bda  lea     rcx, [rbp+2E0h+var_300]
0x180036bde  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; ToString(_GUID const &)
0x180036be3  nop
0x180036be4  mov     r8, rax
0x180036be7  lea     rdx, [rbp+2E0h+var_138]
0x180036bee  lea     rcx, [rbp+2E0h+var_340]
0x180036bf2  call    ?ToStringCheckingErrors@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV12@0@Z; ToStringCheckingErrors(std::wstring const &,std::wstring const &)
0x180036bf7  nop
0x180036bf8  mov     rcx, rax
0x180036bfb  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180036c00  mov     [rsp+3E0h+var_3B8], rsi
0x180036c05  mov     [rsp+3E0h+var_3C0], rdi
0x180036c0a  mov     r9, rbx
0x180036c0d  mov     r8, rax
0x180036c10  lea     rdx, aNetworkInterfa; "    Network Interface Id:\n      Interf"...
0x180036c17  lea     rcx, [rbp+2E0h+var_60]
0x180036c1e  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180036c23  nop
0x180036c24  lea     rcx, [rbp+2E0h+var_340]
0x180036c28  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036c2d  nop
0x180036c2e  lea     rcx, [rbp+2E0h+var_300]
0x180036c32  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036c37  nop
0x180036c38  lea     rcx, [rbp+2E0h+var_2E0]
0x180036c3c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036c41  nop
0x180036c42  lea     rcx, [rbp+2E0h+var_2C0]
0x180036c46  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036c4b  nop
0x180036c4c  lea     rcx, [rbp+2E0h+var_2A0]
0x180036c50  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036c55  nop
0x180036c56  lea     rcx, [rbp+2E0h+var_320]
0x180036c5a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036c5f  nop
0x180036c60  lea     rcx, [rsp+3E0h+var_380]
0x180036c65  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036c6a  lea     rcx, [rbp+2E0h+var_218]
0x180036c71  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180036c76  nop
0x180036c77  mov     [rbp+2E0h+var_240], r13d
0x180036c7e  mov     rax, [r14]
0x180036c81  lea     rdx, [rbp+2E0h+var_240]
0x180036c88  mov     rcx, r14
0x180036c8b  mov     rax, [rax+40h]
0x180036c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c94  mov     edi, 1
0x180036c99  test    eax, eax
0x180036c9b  jns     short loc_180036CCA
0x180036c9d  mov     r8d, edi
0x180036ca0  lea     rdx, aInetworkinterf_8; "  ! <INetworkInterfacePrivate::GetCost "...
0x180036ca7  lea     rcx, [rsp+3E0h+var_380]
0x180036cac  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180036cb1  mov     rdx, rax
0x180036cb4  lea     rcx, [rbp+2E0h+var_218]
0x180036cbb  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180036cc0  lea     rcx, [rsp+3E0h+var_380]
0x180036cc5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036cca  lea     rcx, [rbp+2E0h+var_1D8]
0x180036cd1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180036cd6  nop
0x180036cd7  xorps   xmm1, xmm1
0x180036cda  xor     eax, eax
0x180036cdc  movups  [rbp+2E0h+var_98], xmm1
0x180036ce3  movups  [rbp+2E0h+var_88], xmm1
0x180036cea  movups  [rbp+2E0h+var_78], xmm1
0x180036cf1  mov     [rbp+2E0h+var_68], rax
0x180036cf8  mov     rax, [r14]
0x180036cfb  lea     rdx, [rbp+2E0h+var_98]
0x180036d02  mov     rcx, r14
0x180036d05  mov     rax, [rax+48h]
0x180036d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036d0e  test    eax, eax
0x180036d10  jns     short loc_180036D3F
0x180036d12  mov     r8d, edi
0x180036d15  lea     rdx, aInetworkinterf_5; "  ! <INetworkInterfacePrivate::GetDataP"...
0x180036d1c  lea     rcx, [rsp+3E0h+var_380]
0x180036d21  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180036d26  mov     rdx, rax
0x180036d29  lea     rcx, [rbp+2E0h+var_1D8]
0x180036d30  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180036d35  lea     rcx, [rsp+3E0h+var_380]
0x180036d3a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036d3f  lea     rcx, [rbp+2E0h+var_1F8]
0x180036d46  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180036d4b  nop
0x180036d4c  cmp     [rbp+2E0h+var_1C8], r13
0x180036d53  jnz     short loc_180036DB1
0x180036d55  cmp     [rbp+2E0h+var_208], r13
0x180036d5c  jz      short loc_180036D97
0x180036d5e  lea     rcx, [rbp+2E0h+var_218]
0x180036d65  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180036d6a  mov     r8, rax
0x180036d6d  lea     rdx, [rbp+2E0h+var_98]
0x180036d74  lea     rcx, [rsp+3E0h+var_380]
0x180036d79  call    ?Log@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUNP_DATAPLAN_STATUS@@PEB_W@Z; Log(NP_DATAPLAN_STATUS const &,wchar_t const *)
0x180036d7e  mov     rdx, rax
0x180036d81  lea     rcx, [rbp+2E0h+var_1F8]
0x180036d88  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180036d8d  lea     rcx, [rsp+3E0h+var_380]
0x180036d92  jmp     loc_180036E42
0x180036d97  mov     r8d, [rbp+2E0h+var_240]
0x180036d9e  lea     rdx, [rbp+2E0h+var_98]
0x180036da5  lea     rcx, [rsp+3E0h+var_380]
0x180036daa  call    ?Log@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUNP_DATAPLAN_STATUS@@W4NP_CONNECTION_COST@@@Z; Log(NP_DATAPLAN_STATUS const &,NP_CONNECTION_COST)
0x180036daf  jmp     short loc_180036D7E
0x180036db1  lea     rcx, [rbp+2E0h+var_1D8]
0x180036db8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180036dbd  cmp     [rbp+2E0h+var_208], r13
0x180036dc4  jz      short loc_180036DEB
0x180036dc6  mov     r9, rax
0x180036dc9  lea     rcx, [rbp+2E0h+var_218]
0x180036dd0  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180036dd5  mov     r8, rax
0x180036dd8  lea     rdx, aDataplanstatus_0; "    DataPlanStatus:\n      Cost: %ws\n "...
0x180036ddf  lea     rcx, [rsp+3E0h+var_380]
0x180036de4  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180036de9  jmp     short loc_180036D7E
0x180036deb  mov     rbx, rax
0x180036dee  mov     eax, [rbp+2E0h+var_240]
0x180036df4  mov     dword ptr [rbp+2E0h+var_360], eax
0x180036df7  lea     rdx, [rbp+2E0h+var_360]
0x180036dfb  lea     rcx, [rbp+2E0h+var_320]
0x180036dff  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBW4NP_CONNECTION_COST@@@Z; ToString(NP_CONNECTION_COST const &)
0x180036e04  nop
0x180036e05  mov     rcx, rax
0x180036e08  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180036e0d  mov     r9, rbx
0x180036e10  mov     r8, rax
0x180036e13  lea     rdx, aDataplanstatus_0; "    DataPlanStatus:\n      Cost: %ws\n "...
0x180036e1a  lea     rcx, [rsp+3E0h+var_380]
0x180036e1f  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180036e24  mov     rdx, rax
0x180036e27  lea     rcx, [rbp+2E0h+var_1F8]
0x180036e2e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180036e33  lea     rcx, [rsp+3E0h+var_380]
0x180036e38  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036e3d  nop
0x180036e3e  lea     rcx, [rbp+2E0h+var_320]
0x180036e42  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036e47  lea     rcx, [rbp+2E0h+var_B8]
0x180036e4e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180036e53  nop
0x180036e54  xorps   xmm1, xmm1
0x180036e57  movups  [rbp+2E0h+var_1A8], xmm1
0x180036e5e  mov     rax, [r14]
0x180036e61  lea     rdx, [rbp+2E0h+var_1A8]
0x180036e68  mov     rcx, r14
0x180036e6b  mov     rax, [rax+20h]
0x180036e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e74  test    eax, eax
0x180036e76  jns     short loc_180036EA5
0x180036e78  mov     r8d, edi
0x180036e7b  lea     rdx, aInetworkinterf_12; "  ! <INetworkInterfacePrivate::GetInter"...
0x180036e82  lea     rcx, [rsp+3E0h+var_380]
0x180036e87  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180036e8c  mov     rdx, rax
0x180036e8f  lea     rcx, [rbp+2E0h+var_B8]
0x180036e96  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180036e9b  lea     rcx, [rsp+3E0h+var_380]
0x180036ea0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036ea5  lea     rcx, [rbp+2E0h+var_D8]
0x180036eac  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180036eb1  nop
0x180036eb2  xorps   xmm1, xmm1
0x180036eb5  movups  [rbp+2E0h+var_1B8], xmm1
0x180036ebc  mov     rax, [r14]
0x180036ebf  lea     rdx, [rbp+2E0h+var_1B8]
0x180036ec6  mov     rcx, r14
0x180036ec9  mov     rax, [rax+28h]
0x180036ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ed2  test    eax, eax
0x180036ed4  jns     short loc_180036F03
0x180036ed6  mov     r8d, edi
0x180036ed9  lea     rdx, aInetworkinterf_9; "  ! <INetworkInterfacePrivate::GetNetwo"...
0x180036ee0  lea     rcx, [rsp+3E0h+var_380]
0x180036ee5  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180036eea  mov     rdx, rax
0x180036eed  lea     rcx, [rbp+2E0h+var_D8]
0x180036ef4  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180036ef9  lea     rcx, [rsp+3E0h+var_380]
0x180036efe  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036f03  lea     rcx, [rbp+2E0h+var_F8]
0x180036f0a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180036f0f  nop
0x180036f10  mov     [rbp+2E0h+var_22C], r13d
0x180036f17  mov     rax, [r14]
0x180036f1a  lea     rdx, [rbp+2E0h+var_22C]
0x180036f21  mov     rcx, r14
0x180036f24  mov     rax, [rax+38h]
0x180036f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f2d  test    eax, eax
0x180036f2f  jns     short loc_180036F5E
0x180036f31  mov     r8d, edi
0x180036f34  lea     rdx, aInetworkinterf_4; "  ! <INetworkInterfacePrivate::GetState"...
0x180036f3b  lea     rcx, [rsp+3E0h+var_380]
0x180036f40  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180036f45  mov     rdx, rax
0x180036f48  lea     rcx, [rbp+2E0h+var_F8]
0x180036f4f  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180036f54  lea     rcx, [rsp+3E0h+var_380]
0x180036f59  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036f5e  lea     rcx, [rbp+2E0h+var_118]
0x180036f65  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
  ... truncated ...
```
