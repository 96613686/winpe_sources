# ClusterSetAccountAccess

- ea: `0x18002c820`
- end: `0x18002cc91`
- name: `ClusterSetAccountAccess`
- size: `1137`
- prototype: `DWORD __stdcall(HCLUSTER hCluster, LPCWSTR szAccountSID, DWORD dwAccess, DWORD dwControlType)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002f50`
- `0x180013ae4`
- `0x180013fe8`
- `0x180014638`
- `0x18001cc2c`
- `0x18001e760`
- `0x180029410`
- `0x180029578`
- `0x18002c820`
- `0x1800538c0`
- `0x18006f910`
- `0x180094ce8`
- `0x180095144`
- `0x180096894`
- `0x180096b88`
- `0x180097dd4`
- `0x18009fa68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c9ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c9ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c898`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c8b0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c8b0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002c98f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002c98f`

## string_xrefs

- `0x18002c928`: `Passed in string is not a valid SID string or account name : %d`
- `0x18002c93a`: `ClusterSetAccountAccess`
- `0x18002c9f9`: `AccountSID`
- `0x18002ca81`: `AccountSID`
- `0x18002caeb`: `AccountAccessMask`
- `0x18002cb4a`: `AccountAccessType`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
DWORD __stdcall ClusterSetAccountAccess(HCLUSTER hCluster, LPCWSTR szAccountSID, DWORD dwAccess, DWORD dwControlType)
{
  BOOL v9; // eax
  DWORD v10; // ebx
  BOOL v11; // eax
  unsigned __int64 v12; // rdx
  DWORD LastError; // ebx
  DWORD v14; // [rsp+50h] [rbp-E8h] BYREF
  PSID Sid[2]; // [rsp+58h] [rbp-E0h] BYREF
  PSID *v16; // [rsp+68h] [rbp-D0h] BYREF
  PSID *v17; // [rsp+70h] [rbp-C8h]
  HLOCAL (__stdcall *v18)(HLOCAL); // [rsp+78h] [rbp-C0h] BYREF
  PSID v19; // [rsp+80h] [rbp-B8h]
  __int64 v20; // [rsp+88h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+90h] [rbp-A8h]
  _BYTE v22[56]; // [rsp+A0h] [rbp-98h] BYREF
  _BYTE v23[32]; // [rsp+D8h] [rbp-60h] BYREF
  _BYTE v24[32]; // [rsp+F8h] [rbp-40h] BYREF

  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           hCluster,
                           hCluster) )
    return 6;
  std::vector<_GUID>::vector<_GUID>(&v20);
  cxl::PropertyList::PropertyList((cxl::PropertyList *)v22);
  if ( szAccountSID && dwControlType <= 2 )
  {
    Sid[0] = 0;
    v9 = ConvertStringSidToSidW(szAccountSID, Sid);
    v18 = LocalFree;
    v19 = (PSID)((unsigned __int64)Sid[0] & -(__int64)v9);
    if ( v19 )
    {
      std::wstring::wstring(v24, szAccountSID);
      std::wstring::wstring(v23, L"AccountSID");
      v14 = 65539;
      v16 = (PSID *)v24;
      v17 = (PSID *)&v14;
      cxl::PropertyList::AddPropertyT<_lambda_5d897758465b3281188928bc355bf98e_>(v22, v23, &v16);
      std::wstring::_Tidy_deallocate(v23);
      std::wstring::_Tidy_deallocate(v24);
    }
    else
    {
      Sid[0] = 0;
      v14 = 0;
      v10 = ClRtlConvertDomainAccountToSid(szAccountSID);
      v16 = (PSID *)LocalFree;
      v17 = (PSID *)Sid[0];
      std::unique_ptr<void,void * (*)(void *)>::operator=<void * (*)(void *),0>(&v18, &v16);
      std::unique_ptr<wchar_t,void * (*)(void *)>::~unique_ptr<wchar_t,void * (*)(void *)>(&v16);
      if ( v10 )
      {
        TraceMsg(
          2,
          0,
          L"ClusterSetAccountAccess",
          9008,
          L"Passed in string is not a valid SID string or account name : %d",
          v10);
        std::unique_ptr<wchar_t,void * (*)(void *)>::~unique_ptr<wchar_t,void * (*)(void *)>(&v18);
        cxl::PropertyList::~PropertyList((cxl::PropertyList *)v22);
        std::vector<unsigned char>::_Tidy(&v20);
        return v10;
      }
      Sid[0] = 0;
      v11 = ConvertSidToStringSidW(v19, (LPWSTR *)Sid);
      v12 = (unsigned __int64)Sid[0] & -(__int64)v11;
      v16 = (PSID *)LocalFree;
      v17 = (PSID *)v12;
      if ( !v12 )
      {
        LastError = GetLastError();
        std::unique_ptr<wchar_t,void * (*)(void *)>::~unique_ptr<wchar_t,void * (*)(void *)>(&v16);
        std::unique_ptr<wchar_t,void * (*)(void *)>::~unique_ptr<wchar_t,void * (*)(void *)>(&v18);
        cxl::PropertyList::~PropertyList((cxl::PropertyList *)v22);
        std::vector<unsigned char>::_Tidy(&v20);
        return LastError;
      }
      std::wstring::wstring(v23, v12);
      std::wstring::wstring(v24, L"AccountSID");
      v14 = 65539;
      Sid[0] = v23;
      Sid[1] = &v14;
      cxl::PropertyList::AddPropertyT<_lambda_5d897758465b3281188928bc355bf98e_>(v22, v24, Sid);
      std::wstring::_Tidy_deallocate(v24);
      std::wstring::_Tidy_deallocate(v23);
      std::unique_ptr<wchar_t,void * (*)(void *)>::~unique_ptr<wchar_t,void * (*)(void *)>(&v16);
    }
    std::wstring::wstring(v23, L"AccountAccessMask");
    v14 = dwAccess;
    LODWORD(Sid[0]) = 65538;
    v16 = (PSID *)&v14;
    v17 = Sid;
    cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v22, v23, &v16);
    std::wstring::_Tidy_deallocate(v23);
    std::wstring::wstring(v23, L"AccountAccessType");
    LODWORD(Sid[0]) = dwControlType;
    v14 = 65538;
    v16 = Sid;
    v17 = (PSID *)&v14;
    cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v22, v23, &v16);
    std::wstring::_Tidy_deallocate(v23);
    cxl::PropertyList::GetBuffer(v22, &v20);
    v14 = ClusterControlEx(hCluster, (int)v21 - (int)v20, 0, 0, (__int64)Sid, 0);
    std::unique_ptr<wchar_t,void * (*)(void *)>::~unique_ptr<wchar_t,void * (*)(void *)>(&v18);
    cxl::PropertyList::~PropertyList((cxl::PropertyList *)v22);
    std::vector<unsigned char>::_Tidy(&v20);
    return v14;
  }
  else
  {
    cxl::PropertyList::~PropertyList((cxl::PropertyList *)v22);
    std::vector<unsigned char>::_Tidy(&v20);
    return 87;
  }
}

```

## disassembly

```asm
0x18002c820  mov     [rsp+arg_10], rbx
0x18002c825  mov     [rsp+arg_18], rsi
0x18002c82a  push    rdi
0x18002c82b  push    r14
0x18002c82d  push    r15
0x18002c82f  sub     rsp, 120h
0x18002c836  mov     rax, cs:__security_cookie
0x18002c83d  xor     rax, rsp
0x18002c840  mov     [rsp+138h+var_20], rax
0x18002c848  mov     esi, r9d
0x18002c84b  mov     r14d, r8d
0x18002c84e  mov     rbx, rdx
0x18002c851  mov     r15, rcx
0x18002c854  mov     rdx, rcx
0x18002c857  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x18002c85c  test    al, al
0x18002c85e  jnz     short loc_18002C86A
0x18002c860  mov     eax, 6
0x18002c865  jmp     loc_18002CC67
0x18002c86a  lea     rcx, [rsp+138h+var_B0]
0x18002c872  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18002c877  nop
0x18002c878  lea     rcx, [rsp+138h+var_98]; this
0x18002c880  call    ??0PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::PropertyList(void)
0x18002c885  nop
0x18002c886  test    rbx, rbx
0x18002c889  jz      loc_18002CC39
0x18002c88f  cmp     esi, 2
0x18002c892  ja      loc_18002CC39
0x18002c898  mov     rdi, cs:__imp_LocalFree
0x18002c89f  mov     [rsp+138h+Sid], 0
0x18002c8a8  lea     rdx, [rsp+138h+Sid]; Sid
0x18002c8ad  mov     rcx, rbx; StringSid
0x18002c8b0  call    cs:__imp_ConvertStringSidToSidW
0x18002c8b6  neg     eax
0x18002c8b8  sbb     rcx, rcx
0x18002c8bb  and     rcx, [rsp+138h+Sid]
0x18002c8c0  mov     [rsp+138h+var_C0], rdi
0x18002c8c5  mov     [rsp+138h+var_B8], rcx
0x18002c8cd  jnz     loc_18002CA70
0x18002c8d3  mov     [rsp+138h+Sid], 0
0x18002c8dc  mov     [rsp+138h+var_E8], 0
0x18002c8e4  lea     r8, [rsp+138h+var_E8]
0x18002c8e9  lea     rdx, [rsp+138h+Sid]
0x18002c8ee  mov     rcx, rbx; lpAccountName
0x18002c8f1  call    ClRtlConvertDomainAccountToSid
0x18002c8f6  mov     ebx, eax
0x18002c8f8  mov     [rsp+138h+var_D0], rdi
0x18002c8fd  mov     rcx, [rsp+138h+Sid]
0x18002c902  mov     [rsp+138h+var_C8], rcx
0x18002c907  lea     rdx, [rsp+138h+var_D0]
0x18002c90c  lea     rcx, [rsp+138h+var_C0]
0x18002c911  call    ??$?4P6APEAXPEAX@Z$0A@@?$unique_ptr@XP6APEAXPEAX@Z@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<void,void * (*)(void *)>::operator=<void * (*)(void *),0>(std::unique_ptr<void,void * (*)(void *)> &&)
0x18002c916  lea     rcx, [rsp+138h+var_D0]
0x18002c91b  call    ??1?$unique_ptr@_WP6APEAXPEAX@Z@std@@QEAA@XZ; std::unique_ptr<wchar_t,void * (*)(void *)>::~unique_ptr<wchar_t,void * (*)(void *)>(void)
0x18002c920  test    ebx, ebx
0x18002c922  jz      short loc_18002C979
0x18002c924  mov     dword ptr [rsp+138h+var_110], ebx
0x18002c928  lea     rax, aPassedInString; "Passed in string is not a valid SID str"...
0x18002c92f  mov     qword ptr [rsp+138h+var_118], rax
0x18002c934  mov     r9d, 2330h
0x18002c93a  lea     r8, aClustersetacco_0; "ClusterSetAccountAccess"
0x18002c941  xor     edx, edx
0x18002c943  lea     ecx, [rdx+2]
0x18002c946  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18002c94b  nop
0x18002c94c  lea     rcx, [rsp+138h+var_C0]
0x18002c951  call    ??1?$unique_ptr@_WP6APEAXPEAX@Z@std@@QEAA@XZ; std::unique_ptr<wchar_t,void * (*)(void *)>::~unique_ptr<wchar_t,void * (*)(void *)>(void)
0x18002c956  nop
0x18002c957  lea     rcx, [rsp+138h+var_98]; this
0x18002c95f  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x18002c964  nop
0x18002c965  lea     rcx, [rsp+138h+var_B0]
0x18002c96d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002c972  mov     eax, ebx
0x18002c974  jmp     loc_18002CC67
0x18002c979  mov     [rsp+138h+Sid], 0
0x18002c982  lea     rdx, [rsp+138h+Sid]; StringSid
0x18002c987  mov     rcx, [rsp+138h+var_B8]; Sid
0x18002c98f  call    cs:__imp_ConvertSidToStringSidW
0x18002c995  neg     eax
0x18002c997  sbb     rdx, rdx
0x18002c99a  and     rdx, [rsp+138h+Sid]
0x18002c99f  mov     [rsp+138h+var_D0], rdi
0x18002c9a4  mov     [rsp+138h+var_C8], rdx
0x18002c9a9  jnz     short loc_18002C9EB
0x18002c9ab  call    cs:__imp_GetLastError
0x18002c9b1  mov     ebx, eax
0x18002c9b3  lea     rcx, [rsp+138h+var_D0]
0x18002c9b8  call    ??1?$unique_ptr@_WP6APEAXPEAX@Z@std@@QEAA@XZ; std::unique_ptr<wchar_t,void * (*)(void *)>::~unique_ptr<wchar_t,void * (*)(void *)>(void)
0x18002c9bd  nop
0x18002c9be  lea     rcx, [rsp+138h+var_C0]
0x18002c9c3  call    ??1?$unique_ptr@_WP6APEAXPEAX@Z@std@@QEAA@XZ; std::unique_ptr<wchar_t,void * (*)(void *)>::~unique_ptr<wchar_t,void * (*)(void *)>(void)
0x18002c9c8  nop
0x18002c9c9  lea     rcx, [rsp+138h+var_98]; this
0x18002c9d1  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x18002c9d6  nop
0x18002c9d7  lea     rcx, [rsp+138h+var_B0]
0x18002c9df  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002c9e4  mov     eax, ebx
0x18002c9e6  jmp     loc_18002CC67
0x18002c9eb  lea     rcx, [rsp+138h+var_60]
0x18002c9f3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002c9f8  nop
0x18002c9f9  lea     rdx, aAccountsid; "AccountSID"
0x18002ca00  lea     rcx, [rsp+138h+var_40]
0x18002ca08  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002ca0d  nop
0x18002ca0e  mov     [rsp+138h+var_E8], 10003h
0x18002ca16  lea     rax, [rsp+138h+var_60]
0x18002ca1e  mov     [rsp+138h+Sid], rax
0x18002ca23  lea     rax, [rsp+138h+var_E8]
0x18002ca28  mov     [rsp+138h+var_D8], rax
0x18002ca2d  lea     r8, [rsp+138h+Sid]
0x18002ca32  lea     rdx, [rsp+138h+var_40]
0x18002ca3a  lea     rcx, [rsp+138h+var_98]
0x18002ca42  call    ??$AddPropertyT@V_lambda_5d897758465b3281188928bc355bf98e_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_5d897758465b3281188928bc355bf98e_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_5d897758465b3281188928bc355bf98e_>(std::wstring const &,_lambda_5d897758465b3281188928bc355bf98e_ const &)
0x18002ca47  nop
0x18002ca48  lea     rcx, [rsp+138h+var_40]
0x18002ca50  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ca55  nop
0x18002ca56  lea     rcx, [rsp+138h+var_60]
0x18002ca5e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ca63  nop
0x18002ca64  lea     rcx, [rsp+138h+var_D0]
0x18002ca69  call    ??1?$unique_ptr@_WP6APEAXPEAX@Z@std@@QEAA@XZ; std::unique_ptr<wchar_t,void * (*)(void *)>::~unique_ptr<wchar_t,void * (*)(void *)>(void)
0x18002ca6e  jmp     short loc_18002CAEB
0x18002ca70  mov     rdx, rbx
0x18002ca73  lea     rcx, [rsp+138h+var_40]
0x18002ca7b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002ca80  nop
0x18002ca81  lea     rdx, aAccountsid; "AccountSID"
0x18002ca88  lea     rcx, [rsp+138h+var_60]
0x18002ca90  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002ca95  nop
0x18002ca96  mov     [rsp+138h+var_E8], 10003h
0x18002ca9e  lea     rax, [rsp+138h+var_40]
0x18002caa6  mov     [rsp+138h+var_D0], rax
0x18002caab  lea     rax, [rsp+138h+var_E8]
0x18002cab0  mov     [rsp+138h+var_C8], rax
0x18002cab5  lea     r8, [rsp+138h+var_D0]
0x18002caba  lea     rdx, [rsp+138h+var_60]
0x18002cac2  lea     rcx, [rsp+138h+var_98]
0x18002caca  call    ??$AddPropertyT@V_lambda_5d897758465b3281188928bc355bf98e_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_5d897758465b3281188928bc355bf98e_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_5d897758465b3281188928bc355bf98e_>(std::wstring const &,_lambda_5d897758465b3281188928bc355bf98e_ const &)
0x18002cacf  nop
0x18002cad0  lea     rcx, [rsp+138h+var_60]
0x18002cad8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cadd  nop
0x18002cade  lea     rcx, [rsp+138h+var_40]
0x18002cae6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002caeb  lea     rdx, aAccountaccessm; "AccountAccessMask"
0x18002caf2  lea     rcx, [rsp+138h+var_60]
0x18002cafa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002caff  nop
0x18002cb00  mov     [rsp+138h+var_E8], r14d
0x18002cb05  mov     ebx, 10002h
0x18002cb0a  mov     dword ptr [rsp+138h+Sid], ebx
0x18002cb0e  lea     rax, [rsp+138h+var_E8]
0x18002cb13  mov     [rsp+138h+var_D0], rax
0x18002cb18  lea     rax, [rsp+138h+Sid]
0x18002cb1d  mov     [rsp+138h+var_C8], rax
0x18002cb22  lea     r8, [rsp+138h+var_D0]
0x18002cb27  lea     rdx, [rsp+138h+var_60]
0x18002cb2f  lea     rcx, [rsp+138h+var_98]
0x18002cb37  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x18002cb3c  nop
0x18002cb3d  lea     rcx, [rsp+138h+var_60]
0x18002cb45  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cb4a  lea     rdx, aAccountaccesst; "AccountAccessType"
0x18002cb51  lea     rcx, [rsp+138h+var_60]
0x18002cb59  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002cb5e  nop
0x18002cb5f  mov     dword ptr [rsp+138h+Sid], esi
0x18002cb63  mov     [rsp+138h+var_E8], ebx
0x18002cb67  lea     rax, [rsp+138h+Sid]
0x18002cb6c  mov     [rsp+138h+var_D0], rax
0x18002cb71  lea     rax, [rsp+138h+var_E8]
0x18002cb76  mov     [rsp+138h+var_C8], rax
0x18002cb7b  lea     r8, [rsp+138h+var_D0]
0x18002cb80  lea     rdx, [rsp+138h+var_60]
0x18002cb88  lea     rcx, [rsp+138h+var_98]
0x18002cb90  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x18002cb95  nop
0x18002cb96  lea     rcx, [rsp+138h+var_60]
0x18002cb9e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cba3  lea     rdx, [rsp+138h+var_B0]
0x18002cbab  lea     rcx, [rsp+138h+var_98]
0x18002cbb3  call    ?GetBuffer@PropertyList@cxl@@QEBAXAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; cxl::PropertyList::GetBuffer(std::vector<uchar> &)
0x18002cbb8  mov     rax, [rsp+138h+var_A8]
0x18002cbc0  xor     r9d, r9d
0x18002cbc3  sub     rax, [rsp+138h+var_B0]
0x18002cbcb  cmovnz  r9, [rsp+138h+var_B0]
0x18002cbd4  mov     [rsp+138h+var_F8], 0; wchar_t *
0x18002cbdd  lea     rcx, [rsp+138h+Sid]
0x18002cbe2  mov     [rsp+138h+var_100], rcx; __int64
0x18002cbe7  mov     [rsp+138h+var_108], 0; int
0x18002cbef  mov     [rsp+138h+var_110], 0; __int64
0x18002cbf8  mov     [rsp+138h+var_118], eax; int
0x18002cbfc  xor     edx, edx
0x18002cbfe  mov     r8d, 74000F2h
0x18002cc04  mov     rcx, r15; struct _HCLUSTER *
0x18002cc07  call    ClusterControlEx
0x18002cc0c  mov     [rsp+138h+var_E8], eax
0x18002cc10  lea     rcx, [rsp+138h+var_C0]
0x18002cc15  call    ??1?$unique_ptr@_WP6APEAXPEAX@Z@std@@QEAA@XZ; std::unique_ptr<wchar_t,void * (*)(void *)>::~unique_ptr<wchar_t,void * (*)(void *)>(void)
0x18002cc1a  nop
0x18002cc1b  lea     rcx, [rsp+138h+var_98]; this
0x18002cc23  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x18002cc28  nop
0x18002cc29  lea     rcx, [rsp+138h+var_B0]
0x18002cc31  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002cc36  nop
0x18002cc37  jmp     short loc_18002CC63
0x18002cc39  lea     rcx, [rsp+138h+var_98]; this
0x18002cc41  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x18002cc46  nop
0x18002cc47  lea     rcx, [rsp+138h+var_B0]
0x18002cc4f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002cc54  mov     eax, 57h ; 'W'
0x18002cc59  jmp     short loc_18002CC67
0x18002cc5b  jmp     short loc_18002CC63
0x18002cc5d  jmp     short loc_18002CC63
0x18002cc5f  jmp     short loc_18002CC63
0x18002cc61  jmp     short $+2
0x18002cc63  mov     eax, [rsp+138h+var_E8]
0x18002cc67  mov     rcx, [rsp+138h+var_20]
0x18002cc6f  xor     rcx, rsp; StackCookie
0x18002cc72  call    __security_check_cookie
0x18002cc77  lea     r11, [rsp+138h+var_18]
0x18002cc7f  mov     rbx, [r11+30h]
0x18002cc83  mov     rsi, [r11+38h]
0x18002cc87  mov     rsp, r11
0x18002cc8a  pop     r15
0x18002cc8c  pop     r14
0x18002cc8e  pop     rdi
0x18002cc8f  retn
```
