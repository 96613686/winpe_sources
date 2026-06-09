# PrivateNlm::GetConnectivity(void)

- ea: `0x1800104b8`
- end: `0x180010cd7`
- name: `?GetConnectivity@PrivateNlm@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `2079`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f888`

## callees

- `0x18000f388`
- `0x18000f700`
- `0x1800100d8`
- `0x180010124`
- `0x1800104b8`
- `0x180011614`
- `0x1800120d0`
- `0x180034dac`
- `0x1800351d0`
- `0x1800353a4`
- `0x18003580c`
- `0x180037e9c`
- `0x18003816c`
- `0x18003830c`
- `0x180038338`
- `0x18003a37c`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010c63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010c63`
- `IPHLPAPI!FreeMibTable` at `0x180010c15`
- `IPHLPAPI!FreeMibTable` at `0x180010c15`
- `IPHLPAPI!GetIfTable2` at `0x180010812`
- `IPHLPAPI!GetIfTable2` at `0x180010812`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
struct _MIB_IF_TABLE2 *__fastcall PrivateNlm::GetConnectivity(_QWORD *a1, struct _MIB_IF_TABLE2 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  PMIB_IF_TABLE2 **v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int i; // ebx
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned int IfTable2; // eax
  __int64 v19; // rax
  MIB_IF_ROW2 *v20; // rsi
  struct _MIB_IF_TABLE2 *v21; // r15
  GUID *p_InterfaceGuid; // r14
  int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // rax
  _BYTE *v26; // rcx
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // r12
  const wchar_t *v33; // rbx
  const wchar_t *v34; // r8
  __int64 v35; // r15
  __int64 v36; // r14
  __int64 v37; // rax
  __int64 v38; // rsi
  __int64 v39; // rbx
  unsigned int v40; // edi
  __int64 v41; // rax
  __int64 v42; // rax
  _QWORD *v43; // rcx
  unsigned int v44; // ebx
  unsigned int j; // edx
  __int64 v46; // r8
  _QWORD v48[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v49; // [rsp+60h] [rbp-A0h]
  unsigned int v50; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v51[40]; // [rsp+78h] [rbp-88h] BYREF
  PMIB_IF_TABLE2 *p_Table; // [rsp+A0h] [rbp-60h] BYREF
  char v53; // [rsp+A8h] [rbp-58h]
  _BYTE v54[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v55[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v56[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v57[32]; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v58; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v59; // [rsp+144h] [rbp+44h] BYREF
  LPVOID pv; // [rsp+148h] [rbp+48h] BYREF
  PMIB_IF_TABLE2 Table; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v62; // [rsp+158h] [rbp+58h] BYREF
  __int16 v63; // [rsp+15Ch] [rbp+5Ch] BYREF
  __int16 v64; // [rsp+160h] [rbp+60h] BYREF
  _OWORD v65[2]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v66[32]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v67[16]; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v68; // [rsp+1B8h] [rbp+B8h]
  __int128 v69; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v70[16]; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v71; // [rsp+1E8h] [rbp+E8h]
  _BYTE v72[32]; // [rsp+1F8h] [rbp+F8h] BYREF
  _BYTE v73[32]; // [rsp+218h] [rbp+118h] BYREF
  _BYTE v74[32]; // [rsp+238h] [rbp+138h] BYREF
  _BYTE v75[32]; // [rsp+258h] [rbp+158h] BYREF
  _BYTE v76[32]; // [rsp+278h] [rbp+178h] BYREF
  _BYTE v77[32]; // [rsp+298h] [rbp+198h] BYREF
  _OWORD v78[3]; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int64 v79; // [rsp+2E8h] [rbp+1E8h]
  _BYTE v80[32]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v81[32]; // [rsp+310h] [rbp+210h] BYREF

  Table = a2;
  std::wstring::wstring((__int64)v81);
  std::wstring::wstring((__int64)v77);
  v59 = 0;
  if ( (*(int (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)*a1 + 136LL))(*a1, &v59) < 0 )
  {
    v4 = wil::str_printf<std::wstring>(
           (__int64)v48,
           (__int64)L"  ! <INetworkListManagerPrivate::GetConnectivity failed (0x%x)>",
           1);
    std::wstring::operator=((__int64)v77, v4);
    std::wstring::_Tidy_deallocate((__int64)v48);
  }
  std::wstring::wstring((__int64)v67);
  v58 = 0;
  if ( (*(int (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)*a1 + 144LL))(*a1, &v58) < 0 )
  {
    v5 = wil::str_printf<std::wstring>(
           (__int64)v48,
           (__int64)L"  ! <INetworkListManagerPrivate::GetCost failed (0x%x)>",
           1);
    std::wstring::operator=((__int64)v67, v5);
    std::wstring::_Tidy_deallocate((__int64)v48);
  }
  std::wstring::wstring((__int64)v70);
  memset(v78, 0, sizeof(v78));
  v79 = 0;
  if ( (*(int (__fastcall **)(_QWORD, _OWORD *))(*(_QWORD *)*a1 + 152LL))(*a1, v78) < 0 )
  {
    v6 = wil::str_printf<std::wstring>(
           (__int64)v48,
           (__int64)L"  ! <INetworkListManagerPrivate::GetDataPlanStatus failed (0x%x)>",
           1);
    std::wstring::operator=((__int64)v70, v6);
    std::wstring::_Tidy_deallocate((__int64)v48);
  }
  std::wstring::wstring((__int64)v66);
  if ( !v71 )
  {
    if ( v68 )
    {
      v7 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      v8 = Log(v48, v78, v7);
    }
    else
    {
      v8 = Log(v48, v78, v58);
    }
    goto LABEL_10;
  }
  v10 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  if ( v68 )
  {
    v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    v8 = wil::str_printf<std::wstring>(
           (__int64)v48,
           (__int64)L"    DataPlanStatus:\n      Cost: %ws\n      DataplanStatus: %ws\n",
           v11);
LABEL_10:
    std::wstring::operator=((__int64)v66, v8);
    v9 = (PMIB_IF_TABLE2 **)v48;
    goto LABEL_15;
  }
  v12 = v10;
  v50 = v58;
  ToString(&p_Table, &v50);
  v13 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v14 = wil::str_printf<std::wstring>(
          (__int64)v48,
          (__int64)L"    DataPlanStatus:\n      Cost: %ws\n      DataplanStatus: %ws\n",
          v13,
          v12);
  std::wstring::operator=((__int64)v66, v14);
  std::wstring::_Tidy_deallocate((__int64)v48);
  v9 = &p_Table;
LABEL_15:
  std::wstring::_Tidy_deallocate((__int64)v9);
  v62 = 0;
  pv = 0;
  v48[0] = &pv;
  v48[1] = &v62;
  v49 = 1;
  std::wstring::wstring((__int64)v72);
  if ( (*(int (__fastcall **)(_QWORD, unsigned int *, LPVOID *))(*(_QWORD *)*a1 + 112LL))(*a1, &v62, &pv) < 0 )
  {
    v17 = wil::str_printf<std::wstring>(
            (__int64)&p_Table,
            (__int64)L"  ! <INetworkListManagerPrivate::GetNewNetworks failed (0x%x)>",
            1);
    std::wstring::operator=((__int64)v72, v17);
    std::wstring::_Tidy_deallocate((__int64)&p_Table);
  }
  else
  {
    for ( i = 0; i < v62; ++i )
    {
      v16 = Log((__int64)&p_Table, *((_QWORD *)pv + i), i);
      std::wstring::operator=((__int64)v72, v16);
      std::wstring::_Tidy_deallocate((__int64)&p_Table);
    }
  }
  Table = 0;
  p_Table = &Table;
  v53 = 1;
  std::wstring::wstring((__int64)v80);
  std::wstring::wstring((__int64)v76);
  IfTable2 = GetIfTable2(&Table);
  if ( IfTable2 )
  {
    v19 = wil::str_printf<std::wstring>((__int64)v65, (__int64)L"  ! <GetIfTable2 failed (0x%x)>", IfTable2);
    std::wstring::operator=((__int64)v76, v19);
    std::wstring::_Tidy_deallocate((__int64)v65);
  }
  else
  {
    v20 = Table->Table;
    v21 = (struct _MIB_IF_TABLE2 *)&Table->Table[Table->NumEntries];
    if ( Table->Table != (MIB_IF_ROW2 *)v21 )
    {
      p_InterfaceGuid = &Table->Table[0].InterfaceGuid;
      do
      {
        v65[0] = 0;
        v23 = (*(__int64 (__fastcall **)(_QWORD, GUID *, _OWORD *))(*(_QWORD *)*a1 + 160LL))(*a1, p_InterfaceGuid, v65);
        v24 = (unsigned int)v23 >> 31;
        if ( v23 >= 0 )
        {
          ToString(v51, v65);
          v27 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          ToString(v54, p_InterfaceGuid);
          v28 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          wil::str_printf<std::wstring>(
            (__int64)v55,
            (__int64)L"\nIP Interface %ws --> Physical Interface %ws",
            v28,
            v27);
          std::wstring::append();
          std::wstring::_Tidy_deallocate((__int64)v55);
          std::wstring::_Tidy_deallocate((__int64)v54);
          v26 = v51;
        }
        else
        {
          ToString(v55, p_InterfaceGuid);
          v25 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          wil::str_printf<std::wstring>(
            (__int64)v54,
            (__int64)L"\n<INetworkListManagerPrivate::GetPhysicalInterfaceForInternet (%ws) failed (0x%x)>",
            v25,
            (unsigned __int8)v24);
          std::wstring::append();
          std::wstring::_Tidy_deallocate((__int64)v54);
          v26 = v55;
        }
        std::wstring::_Tidy_deallocate((__int64)v26);
        ++v20;
        p_InterfaceGuid = (GUID *)((char *)p_InterfaceGuid + 1352);
      }
      while ( v20 != (MIB_IF_ROW2 *)v21 );
    }
  }
  std::wstring::wstring((__int64)v75);
  v69 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*a1 + 200LL))(*a1, &v69) < 0 )
  {
    v29 = wil::str_printf<std::wstring>(
            (__int64)v51,
            (__int64)L"  ! <INetworkListManagerPrivate::GetPreferredInterface failed (0x%x)>",
            1);
    std::wstring::operator=((__int64)v75, v29);
    std::wstring::_Tidy_deallocate((__int64)v51);
  }
  std::wstring::wstring((__int64)v74);
  v64 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int16 *))(*(_QWORD *)*a1 + 128LL))(*a1, &v64) < 0 )
  {
    v30 = wil::str_printf<std::wstring>(
            (__int64)v51,
            (__int64)L"  ! <INetworkListManagerPrivate::IsConnected failed (0x%x)>",
            1);
    std::wstring::operator=((__int64)v74, v30);
    std::wstring::_Tidy_deallocate((__int64)v51);
  }
  std::wstring::wstring((__int64)v73);
  v63 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int16 *))(*(_QWORD *)*a1 + 120LL))(*a1, &v63) < 0 )
  {
    v31 = wil::str_printf<std::wstring>(
            (__int64)v51,
            (__int64)L"  ! <INetworkListManagerPrivate::IsConnectedToInternet failed (0x%x)>",
            1);
    std::wstring::operator=((__int64)v73, v31);
    std::wstring::_Tidy_deallocate((__int64)v51);
  }
  v32 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v33 = L"true";
  v34 = L"true";
  if ( !v63 )
    v34 = L"false";
  ToStringCheckingErrors(v57, v73, v34);
  v35 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  if ( !v64 )
    v33 = L"false";
  ToStringCheckingErrors(v56, v74, v33);
  v36 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v37 = ToString(v65, &v69);
  ToStringCheckingErrors(v54, v75, v37);
  v38 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v39 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v40 = v62;
  v41 = ToString(v55, v59);
  ToStringCheckingErrors(v51, v77, v41);
  v42 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  wil::str_printf<std::wstring>(
    (__int64)a2,
    (__int64)L"\n"
              " >>>>>> INetworkListManagerPrivate information <<<<<< \n"
              "    Connectivity: %ws\n"
              "    NewNetworks: [%u]\n"
              "%ws\n"
              "    PreferredInterface: %ws\n"
              "    IsConnected: %ws\n"
              "    IsConnectedToInternet: %ws\n"
              "    %ws",
    v42,
    v40,
    v39,
    v38,
    v36,
    v35,
    v32);
  std::wstring::_Tidy_deallocate((__int64)v51);
  std::wstring::_Tidy_deallocate((__int64)v55);
  std::wstring::_Tidy_deallocate((__int64)v54);
  std::wstring::_Tidy_deallocate((__int64)v65);
  std::wstring::_Tidy_deallocate((__int64)v56);
  std::wstring::_Tidy_deallocate((__int64)v57);
  std::wstring::_Tidy_deallocate((__int64)v73);
  std::wstring::_Tidy_deallocate((__int64)v74);
  std::wstring::_Tidy_deallocate((__int64)v75);
  std::wstring::_Tidy_deallocate((__int64)v76);
  std::wstring::_Tidy_deallocate((__int64)v80);
  if ( Table )
    FreeMibTable(Table);
  std::wstring::_Tidy_deallocate((__int64)v72);
  v43 = pv;
  if ( pv )
  {
    v44 = 0;
    for ( j = v62; v44 < j; ++v44 )
    {
      v46 = v43[v44];
      if ( v46 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v46 + 16LL))(v43[v44]);
        j = v62;
        v43 = pv;
      }
    }
    CoTaskMemFree(v43);
  }
  std::wstring::_Tidy_deallocate((__int64)v66);
  std::wstring::_Tidy_deallocate((__int64)v70);
  std::wstring::_Tidy_deallocate((__int64)v67);
  std::wstring::_Tidy_deallocate((__int64)v77);
  std::wstring::_Tidy_deallocate((__int64)v81);
  return a2;
}

```

## disassembly

```asm
0x1800104b8  mov     [rsp-8+arg_10], rbx
0x1800104bd  push    rbp
0x1800104be  push    rsi
0x1800104bf  push    rdi
0x1800104c0  push    r12
0x1800104c2  push    r13
0x1800104c4  push    r14
0x1800104c6  push    r15
0x1800104c8  lea     rbp, [rsp-240h]
0x1800104d0  sub     rsp, 340h
0x1800104d7  mov     rax, cs:__security_cookie
0x1800104de  xor     rax, rsp
0x1800104e1  mov     [rbp+270h+var_40], rax
0x1800104e8  mov     r13, rdx
0x1800104eb  mov     rdi, rcx
0x1800104ee  mov     [rbp+270h+Table], rdx
0x1800104f2  xor     r14d, r14d
0x1800104f5  lea     rcx, [rbp+270h+var_60]
0x1800104fc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180010501  nop
0x180010502  lea     rcx, [rbp+270h+var_D8]
0x180010509  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001050e  nop
0x18001050f  mov     [rbp+270h+var_22C], r14d
0x180010513  mov     rcx, [rdi]
0x180010516  mov     rax, [rcx]
0x180010519  lea     rdx, [rbp+270h+var_22C]
0x18001051d  mov     rax, [rax+88h]
0x180010524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010529  lea     esi, [r14+1]
0x18001052d  test    eax, eax
0x18001052f  jns     short loc_18001055E
0x180010531  mov     r8d, esi
0x180010534  lea     rdx, aInetworklistma_4; "  ! <INetworkListManagerPrivate::GetCon"...
0x18001053b  lea     rcx, [rsp+370h+var_320]
0x180010540  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180010545  mov     rdx, rax
0x180010548  lea     rcx, [rbp+270h+var_D8]
0x18001054f  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180010554  lea     rcx, [rsp+370h+var_320]
0x180010559  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001055e  lea     rcx, [rbp+270h+var_1C8]
0x180010565  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001056a  nop
0x18001056b  mov     [rbp+270h+var_230], r14d
0x18001056f  mov     rcx, [rdi]
0x180010572  mov     rax, [rcx]
0x180010575  lea     rdx, [rbp+270h+var_230]
0x180010579  mov     rax, [rax+90h]
0x180010580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010585  test    eax, eax
0x180010587  jns     short loc_1800105B6
0x180010589  mov     r8d, esi
0x18001058c  lea     rdx, aInetworklistma_18; "  ! <INetworkListManagerPrivate::GetCos"...
0x180010593  lea     rcx, [rsp+370h+var_320]
0x180010598  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18001059d  mov     rdx, rax
0x1800105a0  lea     rcx, [rbp+270h+var_1C8]
0x1800105a7  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800105ac  lea     rcx, [rsp+370h+var_320]
0x1800105b1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800105b6  lea     rcx, [rbp+270h+var_198]
0x1800105bd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800105c2  nop
0x1800105c3  xorps   xmm1, xmm1
0x1800105c6  xor     eax, eax
0x1800105c8  movups  [rbp+270h+var_B8], xmm1
0x1800105cf  movups  [rbp+270h+var_A8], xmm1
0x1800105d6  movups  [rbp+270h+var_98], xmm1
0x1800105dd  mov     [rbp+270h+var_88], rax
0x1800105e4  mov     rcx, [rdi]
0x1800105e7  mov     rax, [rcx]
0x1800105ea  lea     rdx, [rbp+270h+var_B8]
0x1800105f1  mov     rax, [rax+98h]
0x1800105f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105fd  test    eax, eax
0x1800105ff  jns     short loc_18001062E
0x180010601  mov     r8d, esi
0x180010604  lea     rdx, aInetworklistma_19; "  ! <INetworkListManagerPrivate::GetDat"...
0x18001060b  lea     rcx, [rsp+370h+var_320]
0x180010610  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180010615  mov     rdx, rax
0x180010618  lea     rcx, [rbp+270h+var_198]
0x18001061f  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180010624  lea     rcx, [rsp+370h+var_320]
0x180010629  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001062e  lea     rcx, [rbp+270h+var_1E8]
0x180010635  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001063a  nop
0x18001063b  cmp     [rbp+270h+var_188], r14
0x180010642  jnz     short loc_18001069D
0x180010644  cmp     [rbp+270h+var_1B8], r14
0x18001064b  jz      short loc_180010686
0x18001064d  lea     rcx, [rbp+270h+var_1C8]
0x180010654  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180010659  mov     r8, rax
0x18001065c  lea     rdx, [rbp+270h+var_B8]
0x180010663  lea     rcx, [rsp+370h+var_320]
0x180010668  call    ?Log@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUNP_DATAPLAN_STATUS@@PEB_W@Z; Log(NP_DATAPLAN_STATUS const &,wchar_t const *)
0x18001066d  mov     rdx, rax
0x180010670  lea     rcx, [rbp+270h+var_1E8]
0x180010677  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001067c  lea     rcx, [rsp+370h+var_320]
0x180010681  jmp     loc_18001072D
0x180010686  mov     r8d, [rbp+270h+var_230]
0x18001068a  lea     rdx, [rbp+270h+var_B8]
0x180010691  lea     rcx, [rsp+370h+var_320]
0x180010696  call    ?Log@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUNP_DATAPLAN_STATUS@@W4NP_CONNECTION_COST@@@Z; Log(NP_DATAPLAN_STATUS const &,NP_CONNECTION_COST)
0x18001069b  jmp     short loc_18001066D
0x18001069d  lea     rcx, [rbp+270h+var_198]
0x1800106a4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800106a9  cmp     [rbp+270h+var_1B8], r14
0x1800106b0  jz      short loc_1800106D7
0x1800106b2  mov     r9, rax
0x1800106b5  lea     rcx, [rbp+270h+var_1C8]
0x1800106bc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800106c1  mov     r8, rax
0x1800106c4  lea     rdx, aDataplanstatus_0; "    DataPlanStatus:\n      Cost: %ws\n "...
0x1800106cb  lea     rcx, [rsp+370h+var_320]
0x1800106d0  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x1800106d5  jmp     short loc_18001066D
0x1800106d7  mov     rbx, rax
0x1800106da  mov     eax, [rbp+270h+var_230]
0x1800106dd  mov     [rsp+370h+var_300], eax
0x1800106e1  lea     rdx, [rsp+370h+var_300]
0x1800106e6  lea     rcx, [rbp+270h+var_2D0]
0x1800106ea  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBW4NP_CONNECTION_COST@@@Z; ToString(NP_CONNECTION_COST const &)
0x1800106ef  nop
0x1800106f0  mov     rcx, rax
0x1800106f3  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800106f8  mov     r9, rbx
0x1800106fb  mov     r8, rax
0x1800106fe  lea     rdx, aDataplanstatus_0; "    DataPlanStatus:\n      Cost: %ws\n "...
0x180010705  lea     rcx, [rsp+370h+var_320]
0x18001070a  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18001070f  mov     rdx, rax
0x180010712  lea     rcx, [rbp+270h+var_1E8]
0x180010719  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001071e  lea     rcx, [rsp+370h+var_320]
0x180010723  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010728  nop
0x180010729  lea     rcx, [rbp+270h+var_2D0]
0x18001072d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010732  mov     [rbp+270h+var_218], r14d
0x180010736  mov     [rbp+270h+pv], r14
0x18001073a  lea     rax, [rbp+270h+pv]
0x18001073e  mov     [rsp+370h+var_320], rax
0x180010743  lea     rax, [rbp+270h+var_218]
0x180010747  mov     [rsp+370h+var_318], rax
0x18001074c  mov     [rsp+370h+var_310], sil
0x180010751  lea     rcx, [rbp+270h+var_178]
0x180010758  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001075d  nop
0x18001075e  mov     rcx, [rdi]
0x180010761  mov     rax, [rcx]
0x180010764  lea     r8, [rbp+270h+pv]
0x180010768  lea     rdx, [rbp+270h+var_218]
0x18001076c  mov     rax, [rax+70h]
0x180010770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010775  test    eax, eax
0x180010777  js      short loc_1800107B9
0x180010779  mov     ebx, r14d
0x18001077c  cmp     [rbp+270h+var_218], r14d
0x180010780  jbe     short loc_1800107E4
0x180010782  mov     eax, ebx
0x180010784  mov     r8d, ebx
0x180010787  mov     rdx, [rbp+270h+pv]
0x18001078b  mov     rdx, [rdx+rax*8]
0x18001078f  lea     rcx, [rbp+270h+var_2D0]
0x180010793  call    ?Log@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUINetworkPrivate@@K@Z; Log(INetworkPrivate *,ulong)
0x180010798  mov     rdx, rax
0x18001079b  lea     rcx, [rbp+270h+var_178]
0x1800107a2  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800107a7  lea     rcx, [rbp+270h+var_2D0]
0x1800107ab  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800107b0  add     ebx, esi
0x1800107b2  cmp     ebx, [rbp+270h+var_218]
0x1800107b5  jb      short loc_180010782
0x1800107b7  jmp     short loc_1800107E4
0x1800107b9  mov     r8d, esi
0x1800107bc  lea     rdx, aInetworklistma_13; "  ! <INetworkListManagerPrivate::GetNew"...
0x1800107c3  lea     rcx, [rbp+270h+var_2D0]
0x1800107c7  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x1800107cc  mov     rdx, rax
0x1800107cf  lea     rcx, [rbp+270h+var_178]
0x1800107d6  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800107db  lea     rcx, [rbp+270h+var_2D0]
0x1800107df  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800107e4  mov     [rbp+270h+Table], r14
0x1800107e8  lea     rax, [rbp+270h+Table]
0x1800107ec  mov     [rbp+270h+var_2D0], rax
0x1800107f0  mov     [rbp+270h+var_2C8], sil
0x1800107f4  lea     rcx, [rbp+270h+var_80]
0x1800107fb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180010800  nop
0x180010801  lea     rcx, [rbp+270h+var_F8]
0x180010808  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001080d  nop
0x18001080e  lea     rcx, [rbp+270h+Table]; Table
0x180010812  call    cs:__imp_GetIfTable2
0x180010818  test    eax, eax
0x18001081a  jz      short loc_18001084C
0x18001081c  mov     r8d, eax
0x18001081f  lea     rdx, aGetiftable2Fai; "  ! <GetIfTable2 failed (0x%x)>"
0x180010826  lea     rcx, [rbp+270h+var_208]
0x18001082a  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18001082f  mov     rdx, rax
0x180010832  lea     rcx, [rbp+270h+var_F8]
0x180010839  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001083e  lea     rcx, [rbp+270h+var_208]
0x180010842  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010847  jmp     loc_180010973
0x18001084c  mov     rax, [rbp+270h+Table]
0x180010850  lea     rsi, [rax+8]
0x180010854  mov     eax, [rax]
0x180010856  imul    r15, rax, 548h
0x18001085d  add     r15, rsi
0x180010860  cmp     rsi, r15
0x180010863  jz      loc_18001096E
0x180010869  lea     r14, [rsi+0Ch]
0x18001086d  xorps   xmm0, xmm0
0x180010870  movups  [rbp+270h+var_208], xmm0
0x180010874  mov     rcx, [rdi]
0x180010877  mov     rax, [rcx]
0x18001087a  lea     r8, [rbp+270h+var_208]
0x18001087e  mov     rdx, r14
0x180010881  mov     rax, [rax+0A0h]
0x180010888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001088d  mov     ebx, eax
0x18001088f  shr     ebx, 1Fh
0x180010892  test    bl, bl
0x180010894  jz      short loc_1800108E3
0x180010896  mov     rdx, r14
0x180010899  lea     rcx, [rbp+270h+var_290]
0x18001089d  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; ToString(_GUID const &)
0x1800108a2  nop
0x1800108a3  mov     rcx, rax
0x1800108a6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800108ab  movzx   r9d, bl
0x1800108af  mov     r8, rax
0x1800108b2  lea     rdx, aInetworklistma; "\n<INetworkListManagerPrivate::GetPhysi"...
0x1800108b9  lea     rcx, [rbp+270h+var_2B0]
0x1800108bd  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x1800108c2  nop
0x1800108c3  mov     rdx, rax
0x1800108c6  lea     rcx, [rbp+270h+var_F8]
0x1800108cd  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800108d2  nop
0x1800108d3  lea     rcx, [rbp+270h+var_2B0]
0x1800108d7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800108dc  nop
0x1800108dd  lea     rcx, [rbp+270h+var_290]
0x1800108e1  jmp     short loc_180010952
0x1800108e3  lea     rdx, [rbp+270h+var_208]
0x1800108e7  lea     rcx, [rsp+370h+var_2F8]
0x1800108ec  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; ToString(_GUID const &)
0x1800108f1  nop
0x1800108f2  mov     rcx, rax
0x1800108f5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800108fa  mov     rbx, rax
0x1800108fd  mov     rdx, r14
0x180010900  lea     rcx, [rbp+270h+var_2B0]
0x180010904  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; ToString(_GUID const &)
0x180010909  nop
0x18001090a  mov     rcx, rax
0x18001090d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180010912  mov     r9, rbx
0x180010915  mov     r8, rax
0x180010918  lea     rdx, aIpInterfaceWsP; "\nIP Interface %ws --> Physical Interfa"...
0x18001091f  lea     rcx, [rbp+270h+var_290]
0x180010923  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180010928  nop
0x180010929  mov     rdx, rax
0x18001092c  lea     rcx, [rbp+270h+var_80]
0x180010933  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180010938  nop
0x180010939  lea     rcx, [rbp+270h+var_290]
0x18001093d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010942  nop
0x180010943  lea     rcx, [rbp+270h+var_2B0]
0x180010947  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001094c  nop
0x18001094d  lea     rcx, [rsp+370h+var_2F8]
0x180010952  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010957  mov     eax, 548h
0x18001095c  add     rsi, rax
0x18001095f  add     r14, rax
0x180010962  cmp     rsi, r15
0x180010965  jnz     loc_18001086D
0x18001096b  xor     r14d, r14d
0x18001096e  mov     esi, 1
0x180010973  lea     rcx, [rbp+270h+var_118]
0x18001097a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001097f  nop
0x180010980  xorps   xmm1, xmm1
0x180010983  movups  [rbp+270h+var_1A8], xmm1
0x18001098a  mov     rcx, [rdi]
0x18001098d  mov     rax, [rcx]
0x180010990  lea     rdx, [rbp+270h+var_1A8]
0x180010997  mov     rax, [rax+0C8h]
  ... truncated ...
```
