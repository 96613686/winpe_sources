# ReportGenerateBegin(ulong,ushort const *,ulong,_TLSReport *)

- ea: `0x1800553a4`
- end: `0x180055beb`
- name: `?ReportGenerateBegin@@YAKKPEBGKPEAU_TLSReport@@@Z`
- size: `2119`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int16 *, __int64, struct _TLSReport *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, installer_update`

## callers

- `0x180017a90`

## callees

- `0x180002d26`
- `0x180005665`
- `0x18000575c`
- `0x18000d060`
- `0x180021548`
- `0x1800517b8`
- `0x1800518f8`
- `0x18005191c`
- `0x180051940`
- `0x1800519ac`
- `0x1800519d4`
- `0x1800519fc`
- `0x180051dcc`
- `0x180052054`
- `0x180052304`
- `0x1800526f4`
- `0x180053ec0`
- `0x1800540c4`
- `0x1800541c4`
- `0x180054408`
- `0x18005464c`
- `0x18005491c`
- `0x180054ba4`
- `0x1800553a4`
- `0x180055e80`
- `0x1800a0fb0`

## import_xrefs

- `msvcrt!fwprintf` at `0x180055a71`
- `msvcrt!fwprintf` at `0x180055a71`
- `msvcrt!fseek` at `0x1800558db`
- `msvcrt!fseek` at `0x1800558db`
- `msvcrt!fputws` at `0x180055607`
- `msvcrt!fputws` at `0x18005565e`
- `msvcrt!fputws` at `0x1800556f3`
- `msvcrt!fputws` at `0x180055747`
- `msvcrt!fputws` at `0x1800557aa`
- `msvcrt!fputws` at `0x180055887`
- `msvcrt!fputws` at `0x180055a2e`
- `msvcrt!fputws` at `0x180055607`
- `msvcrt!fputws` at `0x18005565e`
- `msvcrt!fputws` at `0x1800556f3`
- `msvcrt!fputws` at `0x180055747`
- `msvcrt!fputws` at `0x1800557aa`
- `msvcrt!fputws` at `0x180055887`
- `msvcrt!fputws` at `0x180055a2e`
- `msvcrt!ferror` at `0x18005561a`
- `msvcrt!ferror` at `0x180055a41`
- `msvcrt!ferror` at `0x18005561a`
- `msvcrt!ferror` at `0x180055a41`
- `msvcrt!fclose` at `0x180055acc`
- `msvcrt!fclose` at `0x180055acc`
- `ole32!CoUninitialize` at `0x180055b03`
- `ole32!CoUninitialize` at `0x180055b03`
- `ole32!CoInitialize` at `0x18005548e`
- `ole32!CoInitialize` at `0x18005548e`
- `RPCRT4!RpcTestCancel` at `0x18005544f`
- `RPCRT4!RpcTestCancel` at `0x180055513`
- `RPCRT4!RpcTestCancel` at `0x18005558e`
- `RPCRT4!RpcTestCancel` at `0x1800555e9`
- `RPCRT4!RpcTestCancel` at `0x180055640`
- `RPCRT4!RpcTestCancel` at `0x18005578c`
- `RPCRT4!RpcTestCancel` at `0x180055aae`
- `RPCRT4!RpcTestCancel` at `0x18005544f`
- `RPCRT4!RpcTestCancel` at `0x180055513`
- `RPCRT4!RpcTestCancel` at `0x18005558e`
- `RPCRT4!RpcTestCancel` at `0x1800555e9`
- `RPCRT4!RpcTestCancel` at `0x180055640`
- `RPCRT4!RpcTestCancel` at `0x18005578c`
- `RPCRT4!RpcTestCancel` at `0x180055aae`
- `KERNEL32!DeleteFileW` at `0x180055ae3`
- `KERNEL32!DeleteFileW` at `0x180055ae3`
- `KERNEL32!LocalAlloc` at `0x1800554a4`
- `KERNEL32!LocalAlloc` at `0x180055b2a`
- `KERNEL32!LocalAlloc` at `0x1800554a4`
- `KERNEL32!LocalAlloc` at `0x180055b2a`
- `KERNEL32!LocalFree` at `0x180055af7`
- `KERNEL32!LocalFree` at `0x180055b6c`
- `KERNEL32!LocalFree` at `0x180055af7`
- `KERNEL32!LocalFree` at `0x180055b6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReportGenerateBegin(unsigned int a1, const unsigned __int16 *a2, __int64 a3, struct _TLSReport *a4)
{
  FILE *v7; // rsi
  unsigned int PerUserDetailsFromDB; // edi
  struct _TLSReport *v9; // rax
  unsigned int v10; // r8d
  struct _TLSReport *v11; // r14
  __int64 v12; // rbx
  __int64 v13; // rax
  int v14; // eax
  FILE *v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  _QWORD **v18; // r8
  int v19; // r15d
  __int64 *v20; // r9
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 i; // rcx
  __int64 v24; // rbx
  __int64 j; // rax
  __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rbx
  __int64 k; // rax
  int v32; // r12d
  int v33; // r13d
  __int64 v34; // rbx
  __int64 v35; // rax
  __int64 v36; // rbx
  __int64 v37; // rax
  int v38; // ebx
  unsigned __int16 *v39; // rax
  unsigned __int16 *v40; // rbx
  __int64 v42; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v43; // [rsp+28h] [rbp-D8h]
  char *v44; // [rsp+30h] [rbp-D0h]
  FILE *Stream; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v46; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v47[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v48; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v49; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v50; // [rsp+80h] [rbp-80h] BYREF
  __int64 v51; // [rsp+88h] [rbp-78h]
  _QWORD v52[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v53; // [rsp+A0h] [rbp-60h] BYREF
  int v54; // [rsp+A8h] [rbp-58h]
  _BYTE v55[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v56[16]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v57[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v58[16]; // [rsp+E0h] [rbp-20h] BYREF
  void *v59; // [rsp+F0h] [rbp-10h]
  _BYTE v60[16]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v61[16]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v62[16]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE *v63; // [rsp+128h] [rbp+28h]
  _BYTE *v64; // [rsp+130h] [rbp+30h]
  wchar_t Buffer[256]; // [rsp+140h] [rbp+40h] BYREF
  wchar_t v66[256]; // [rsp+340h] [rbp+240h] BYREF
  WCHAR FileName[256]; // [rsp+540h] [rbp+440h] BYREF

  v59 = a4;
  v7 = 0;
  Stream = 0;
  std::map<CString,unsigned long>::map<CString,unsigned long>(v56);
  std::map<CString,unsigned long>::map<CString,unsigned long>(v55);
  std::map<CString,unsigned long>::map<CString,unsigned long>(v58);
  std::map<CString,unsigned long>::map<CString,unsigned long>(v57);
  v51 = 0;
  v50 = (__int64 *)std::_Tree_alloc<0,std::_Tree_base_types<std::pair<CString const,unsigned long>>>::_Buyheadnode();
  std::map<CString,unsigned long>::map<CString,unsigned long>(&v53);
  std::multimap<CString,UserReportLicInfo>::multimap<CString,UserReportLicInfo>(v60);
  memset_0(FileName, 0, 0xFFu);
  if ( !RpcTestCancel() )
  {
    PerUserDetailsFromDB = 1223;
    goto LABEL_77;
  }
  if ( a1 == 2 && !a2 || !a4 || a1 - 1 > 2 )
  {
    PerUserDetailsFromDB = 87;
LABEL_75:
    v39 = (unsigned __int16 *)LocalAlloc(0x40u, 0x1FEu);
    v40 = v39;
    if ( v39 )
    {
      StringCchPrintfW(v39, 0xFFu, L"0x%x", PerUserDetailsFromDB);
      CrimsonHelper::RaiseEvent<unsigned short *>(CrimsonHelper::s_instance, TLS_W_REPORT_GENERATE, v40);
      LocalFree(v40);
    }
    goto LABEL_77;
  }
  CoInitialize(0);
  v9 = (struct _TLSReport *)LocalAlloc(0x40u, 0x810u);
  v11 = v9;
  if ( !v9 )
  {
    PerUserDetailsFromDB = 8;
    goto LABEL_64;
  }
  PerUserDetailsFromDB = CreateUniqueReportFile(v9, &Stream, v10, FileName, a1, a2);
  v7 = Stream;
  if ( !PerUserDetailsFromDB )
  {
    PerUserDetailsFromDB = AddHeaderToReport(Stream, v11);
    if ( !PerUserDetailsFromDB )
    {
      PerUserDetailsFromDB = AddEntryDetailHeaderToReport(v7);
      if ( !PerUserDetailsFromDB )
      {
        if ( RpcTestCancel() )
        {
          PerUserDetailsFromDB = GetPerUserDetailsFromDB(v60);
          if ( !PerUserDetailsFromDB )
          {
            Stream = (FILE *)v47;
            std::_Tree<std::_Tmap_traits<CString,UserReportLicInfo,std::less<CString>,std::allocator<std::pair<CString const,UserReportLicInfo>>,1>>::_Tree<std::_Tmap_traits<CString,UserReportLicInfo,std::less<CString>,std::allocator<std::pair<CString const,UserReportLicInfo>>,1>>(
              v47,
              v60);
            PerUserDetailsFromDB = AddSuccessFullPerUserLicensesToReport(v47, v7, v56);
            if ( !PerUserDetailsFromDB )
            {
              NumberOfLicensesInstalled(L"C50", v55);
              NumberOfLicensesInstalled(L"A02", v57);
              if ( RpcTestCancel() )
              {
                Stream = (FILE *)v47;
                v12 = std::map<CString,unsigned long>::map<CString,unsigned long>(v47, v56);
                v46 = v52;
                v13 = std::map<CString,unsigned long>::map<CString,unsigned long>(v52, v55);
                PerUserDetailsFromDB = LogReportingEvents(v13, v12);
                if ( !PerUserDetailsFromDB )
                {
                  if ( RpcTestCancel() )
                  {
                    v14 = fputws(L"DETAIL : PER-DEVICE LICENSING ISSUANCE ,START\n", v7);
                    v15 = v7;
                    if ( v14 < 0 )
                    {
LABEL_19:
                      PerUserDetailsFromDB = ferror(v15);
                      goto LABEL_64;
                    }
                    PerUserDetailsFromDB = GetPerDeviceLicensingInfoFromDB(v7, v58);
                    if ( !PerUserDetailsFromDB && RpcTestCancel() )
                    {
                      v16 = fputws(L"DETAIL : PER-USER LICENSING FAILED ISSUANCE,START\n", v7);
                      v15 = v7;
                      if ( v16 < 0 )
                        goto LABEL_19;
                      PerUserDetailsFromDB = GetFailedPerUserDetailsFromDB(v7, &v53);
                      v18 = (_QWORD **)std::map<CString,unsigned long>::map<CString,unsigned long>(v47, &v53);
                      v46 = v18;
                      v19 = 0;
                      v20 = *v18;
                      v21 = **v18;
                      while ( (__int64 *)v21 != v20 )
                      {
                        v19 += *(_DWORD *)(v21 + 64);
                        if ( !*(_BYTE *)(v21 + 25) )
                        {
                          v22 = *(_QWORD *)(v21 + 16);
                          if ( *(_BYTE *)(v22 + 25) )
                          {
                            for ( i = *(_QWORD *)(v21 + 8);
                                  !*(_BYTE *)(i + 25) && v21 == *(_QWORD *)(i + 16);
                                  i = *(_QWORD *)(i + 8) )
                            {
                              v21 = i;
                            }
                            v21 = i;
                          }
                          else
                          {
                            v21 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CWorkObject *>>>::_Min(
                                    v22,
                                    v17,
                                    v18);
                          }
                        }
                      }
                      std::_Tree<std::_Tmap_traits<CString,unsigned long,std::less<CString>,std::allocator<std::pair<CString const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<CString,unsigned long,std::less<CString>,std::allocator<std::pair<CString const,unsigned long>>,0>>(v18);
                      if ( !PerUserDetailsFromDB )
                      {
                        if ( fputws(L"SUMMARY : PER-USER LICENSING FAILED ISSUANCE,START\n", v7) < 0 )
                        {
LABEL_35:
                          v15 = v7;
                          goto LABEL_19;
                        }
                        v24 = *v53;
                        while ( (__int64 *)v24 != v53 )
                        {
                          StringCchPrintfW(Buffer, 0xFFu, L"%s,%016u,\n");
                          if ( fputws(Buffer, v7) < 0 )
                            goto LABEL_35;
                          if ( !*(_BYTE *)(v24 + 25) )
                          {
                            if ( *(_BYTE *)(*(_QWORD *)(v24 + 16) + 25LL) )
                            {
                              for ( j = *(_QWORD *)(v24 + 8);
                                    !*(_BYTE *)(j + 25) && v24 == *(_QWORD *)(j + 16);
                                    j = *(_QWORD *)(j + 8) )
                              {
                                v24 = j;
                              }
                            }
                            else
                            {
                              j = ((__int64 (*)(void))std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CWorkObject *>>>::_Min)();
                            }
                            v24 = j;
                          }
                        }
                        if ( RpcTestCancel() )
                        {
                          if ( fputws(L"CALINFOHEADER,START\n", v7) < 0 )
                            goto LABEL_35;
                          Stream = (FILE *)v47;
                          v26 = std::map<CString,unsigned long>::map<CString,unsigned long>(v47, v56);
                          v46 = v52;
                          v27 = std::map<CString,unsigned long>::map<CString,unsigned long>(v52, v55);
                          GetInstalledIssuedMap(v27, v26, &v50);
                          v49 = v47;
                          v28 = std::map<CString,unsigned long>::map<CString,unsigned long>(v47, v58);
                          v48 = v52;
                          v29 = std::map<CString,unsigned long>::map<CString,unsigned long>(v52, v57);
                          GetInstalledIssuedMap(v29, v28, &v50);
                          v30 = *v50;
                          while ( (__int64 *)v30 != v50 )
                          {
                            StringCchPrintfW(Buffer, 0xFFu, L"%s,%016u,%016u,\n");
                            if ( fputws(Buffer, v7) < 0 )
                              goto LABEL_35;
                            if ( !*(_BYTE *)(v30 + 25) )
                            {
                              if ( *(_BYTE *)(*(_QWORD *)(v30 + 16) + 25LL) )
                              {
                                for ( k = *(_QWORD *)(v30 + 8);
                                      !*(_BYTE *)(k + 25) && v30 == *(_QWORD *)(k + 16);
                                      k = *(_QWORD *)(k + 8) )
                                {
                                  v30 = k;
                                }
                              }
                              else
                              {
                                k = ((__int64 (*)(void))std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CWorkObject *>>>::_Min)();
                              }
                              v30 = k;
                            }
                          }
                          PerUserDetailsFromDB = fseek(v7, 0, 0);
                          if ( !PerUserDetailsFromDB )
                          {
                            LODWORD(v46) = 0;
                            LODWORD(v49) = 0;
                            LODWORD(Stream) = 0;
                            LODWORD(v48) = 0;
                            v32 = v54;
                            v33 = v51;
                            v63 = v61;
                            v34 = std::map<CString,unsigned long>::map<CString,unsigned long>(v61, v56);
                            v64 = v62;
                            v35 = std::map<CString,unsigned long>::map<CString,unsigned long>(v62, v55);
                            GetTotalInstalledAndIssuedCals(v35, v34, &v46, &v49);
                            v52[0] = v62;
                            v36 = std::map<CString,unsigned long>::map<CString,unsigned long>(v62, v58);
                            v47[0] = v61;
                            v37 = std::map<CString,unsigned long>::map<CString,unsigned long>(v61, v57);
                            GetTotalInstalledAndIssuedCals(v37, v36, &Stream, &v48);
                            v38 = (_DWORD)v49 + (_DWORD)v48 + v32 + v19 + v33;
                            memset_0(v66, 0, 0x1FEu);
                            LODWORD(Stream) = (_DWORD)v46 + (_DWORD)Stream;
                            v44 = (char *)v11 + 514;
                            v43 = (unsigned __int16 *)((char *)v11 + 4);
                            StringCchPrintfW(v66, 0xFFu, L"%016u,%016u,%s,%s,%u,%u,%s,\n");
                            if ( fputws(v66, v7) >= 0 )
                            {
                              LODWORD(v44) = v33;
                              LODWORD(v43) = v32;
                              LODWORD(v42) = v19;
                              fwprintf(
                                v7,
                                L"%016u,%016u,%016u,%016u,%016u,",
                                (unsigned int)v49,
                                (unsigned int)v48,
                                v42,
                                v43,
                                v44);
                              *((_DWORD *)v11 + 515) = (_DWORD)Stream;
                              *(_DWORD *)v11 = v38;
                              *((_DWORD *)v11 + 385) = 3;
                              memcpy_0(v59, v11, 0x810u);
                            }
                            else
                            {
                              PerUserDetailsFromDB = ferror(v7);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_64:
  if ( !RpcTestCancel() )
    PerUserDetailsFromDB = 1223;
  if ( v7 )
    fclose(v7);
  if ( PerUserDetailsFromDB )
  {
    DeleteFileW(FileName);
    if ( v11 )
      LocalFree(v11);
  }
  CoUninitialize();
  if ( PerUserDetailsFromDB && PerUserDetailsFromDB != 1223 )
    goto LABEL_75;
LABEL_77:
  std::_Tree<std::_Tmap_traits<CString,UserReportLicInfo,std::less<CString>,std::allocator<std::pair<CString const,UserReportLicInfo>>,1>>::~_Tree<std::_Tmap_traits<CString,UserReportLicInfo,std::less<CString>,std::allocator<std::pair<CString const,UserReportLicInfo>>,1>>(v60);
  std::_Tree<std::_Tmap_traits<CString,unsigned long,std::less<CString>,std::allocator<std::pair<CString const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<CString,unsigned long,std::less<CString>,std::allocator<std::pair<CString const,unsigned long>>,0>>(&v53);
  std::_Tree<std::_Tmap_traits<CString,_TLSCALInfo,std::less<CString>,std::allocator<std::pair<CString const,_TLSCALInfo>>,0>>::~_Tree<std::_Tmap_traits<CString,_TLSCALInfo,std::less<CString>,std::allocator<std::pair<CString const,_TLSCALInfo>>,0>>(&v50);
  std::_Tree<std::_Tmap_traits<CString,unsigned long,std::less<CString>,std::allocator<std::pair<CString const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<CString,unsigned long,std::less<CString>,std::allocator<std::pair<CString const,unsigned long>>,0>>(v57);
  std::_Tree<std::_Tmap_traits<CString,unsigned long,std::less<CString>,std::allocator<std::pair<CString const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<CString,unsigned long,std::less<CString>,std::allocator<std::pair<CString const,unsigned long>>,0>>(v58);
  std::_Tree<std::_Tmap_traits<CString,unsigned long,std::less<CString>,std::allocator<std::pair<CString const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<CString,unsigned long,std::less<CString>,std::allocator<std::pair<CString const,unsigned long>>,0>>(v55);
  std::_Tree<std::_Tmap_traits<CString,unsigned long,std::less<CString>,std::allocator<std::pair<CString const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<CString,unsigned long,std::less<CString>,std::allocator<std::pair<CString const,unsigned long>>,0>>(v56);
  return PerUserDetailsFromDB;
}

```

## disassembly

```asm
0x1800553a4  mov     [rsp-8+arg_10], rbx
0x1800553a9  push    rbp
0x1800553aa  push    rsi
0x1800553ab  push    rdi
0x1800553ac  push    r12
0x1800553ae  push    r13
0x1800553b0  push    r14
0x1800553b2  push    r15
0x1800553b4  lea     rbp, [rsp-650h]
0x1800553bc  sub     rsp, 750h
0x1800553c3  mov     rax, cs:__security_cookie
0x1800553ca  xor     rax, rsp
0x1800553cd  mov     [rbp+680h+var_40], rax
0x1800553d4  mov     r14, r9
0x1800553d7  mov     [rbp+680h+var_690], r9
0x1800553db  mov     rdi, rdx
0x1800553de  mov     ebx, ecx
0x1800553e0  xor     r12d, r12d
0x1800553e3  mov     esi, r12d
0x1800553e6  mov     [rsp+780h+Stream], r12
0x1800553eb  lea     rcx, [rbp+680h+var_6C0]
0x1800553ef  call    ??0?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@QEAA@XZ; std::map<CString,ulong>::map<CString,ulong>(void)
0x1800553f4  nop
0x1800553f5  lea     rcx, [rbp+680h+var_6D0]
0x1800553f9  call    ??0?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@QEAA@XZ; std::map<CString,ulong>::map<CString,ulong>(void)
0x1800553fe  nop
0x1800553ff  lea     rcx, [rbp+680h+var_6A0]
0x180055403  call    ??0?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@QEAA@XZ; std::map<CString,ulong>::map<CString,ulong>(void)
0x180055408  nop
0x180055409  lea     rcx, [rbp+680h+var_6B0]
0x18005540d  call    ??0?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@QEAA@XZ; std::map<CString,ulong>::map<CString,ulong>(void)
0x180055412  nop
0x180055413  mov     [rbp+680h+var_700], r12
0x180055417  mov     [rbp+680h+var_6F8], r12
0x18005541b  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBVCString@@K@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBVCString@@K@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<CString const,ulong>>>::_Buyheadnode(void)
0x180055420  mov     [rbp+680h+var_700], rax
0x180055424  lea     rcx, [rbp+680h+var_6E0]
0x180055428  call    ??0?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@QEAA@XZ; std::map<CString,ulong>::map<CString,ulong>(void)
0x18005542d  nop
0x18005542e  lea     rcx, [rbp+680h+var_688]
0x180055432  call    ??0?$multimap@VCString@@UUserReportLicInfo@@U?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@UUserReportLicInfo@@@std@@@4@@std@@QEAA@XZ; std::multimap<CString,UserReportLicInfo>::multimap<CString,UserReportLicInfo>(void)
0x180055437  nop
0x180055438  mov     r13d, 0FFh
0x18005543e  mov     r8d, r13d; Size
0x180055441  xor     edx, edx; Val
0x180055443  lea     rcx, [rbp+680h+FileName]; void *
0x18005544a  call    memset_0
0x18005544f  call    cs:__imp_RpcTestCancel
0x180055456  nop     dword ptr [rax+rax+00h]
0x18005545b  test    eax, eax
0x18005545d  jnz     short loc_180055469
0x18005545f  mov     edi, 4C7h
0x180055464  jmp     loc_180055B79
0x180055469  cmp     ebx, 2
0x18005546c  jnz     short loc_180055477
0x18005546e  test    rdi, rdi
0x180055471  jz      loc_180055B1B
0x180055477  test    r14, r14
0x18005547a  jz      loc_180055B1B
0x180055480  lea     eax, [rbx-1]
0x180055483  cmp     eax, 2
0x180055486  ja      loc_180055B1B
0x18005548c  xor     ecx, ecx; pvReserved
0x18005548e  call    cs:__imp_CoInitialize
0x180055495  nop     dword ptr [rax+rax+00h]
0x18005549a  mov     edx, 810h; uBytes
0x18005549f  mov     ecx, 40h ; '@'; uFlags
0x1800554a4  call    cs:__imp_LocalAlloc
0x1800554ab  nop     dword ptr [rax+rax+00h]
0x1800554b0  mov     r14, rax
0x1800554b3  test    rax, rax
0x1800554b6  jnz     short loc_1800554C0
0x1800554b8  lea     edi, [rax+8]
0x1800554bb  jmp     loc_180055AAE
0x1800554c0  mov     [rsp+780h+var_758], rdi; unsigned __int16 *
0x1800554c5  mov     dword ptr [rsp+780h+var_760], ebx; unsigned int
0x1800554c9  lea     r9, [rbp+680h+FileName]; unsigned __int16 *
0x1800554d0  lea     rdx, [rsp+780h+Stream]; struct _iobuf **
0x1800554d5  mov     rcx, r14; struct _TLSReport *
0x1800554d8  call    ?CreateUniqueReportFile@@YAKPEAU_TLSReport@@PEAPEAU_iobuf@@KPEAGKPEBG@Z; CreateUniqueReportFile(_TLSReport *,_iobuf * *,ulong,ushort *,ulong,ushort const *)
0x1800554dd  mov     edi, eax
0x1800554df  mov     rsi, [rsp+780h+Stream]
0x1800554e4  test    eax, eax
0x1800554e6  jnz     loc_180055AAE
0x1800554ec  mov     rdx, r14; struct _TLSReport *
0x1800554ef  mov     rcx, rsi; Stream
0x1800554f2  call    ?AddHeaderToReport@@YAKPEAU_iobuf@@PEAU_TLSReport@@@Z; AddHeaderToReport(_iobuf *,_TLSReport *)
0x1800554f7  mov     edi, eax
0x1800554f9  test    eax, eax
0x1800554fb  jnz     loc_180055AAE
0x180055501  mov     rcx, rsi; Stream
0x180055504  call    ?AddEntryDetailHeaderToReport@@YAKPEAU_iobuf@@@Z; AddEntryDetailHeaderToReport(_iobuf *)
0x180055509  mov     edi, eax
0x18005550b  test    eax, eax
0x18005550d  jnz     loc_180055AAE
0x180055513  call    cs:__imp_RpcTestCancel
0x18005551a  nop     dword ptr [rax+rax+00h]
0x18005551f  test    eax, eax
0x180055521  jz      loc_180055AAE
0x180055527  lea     rcx, [rbp+680h+var_688]
0x18005552b  call    ?GetPerUserDetailsFromDB@@YAKPEAV?$multimap@VCString@@UUserReportLicInfo@@U?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@UUserReportLicInfo@@@std@@@4@@std@@@Z; GetPerUserDetailsFromDB(std::multimap<CString,UserReportLicInfo> *)
0x180055530  mov     edi, eax
0x180055532  test    eax, eax
0x180055534  jnz     loc_180055AAE
0x18005553a  lea     rax, [rsp+780h+var_720]
0x18005553f  mov     [rsp+780h+Stream], rax
0x180055544  lea     rdx, [rbp+680h+var_688]
0x180055548  lea     rcx, [rsp+780h+var_720]
0x18005554d  call    ??0?$_Tree@V?$_Tmap_traits@VCString@@UUserReportLicInfo@@U?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@UUserReportLicInfo@@@std@@@4@$00@std@@@std@@QEAA@AEBV01@AEBV?$allocator@U?$pair@$$CBVCString@@UUserReportLicInfo@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<CString,UserReportLicInfo,std::less<CString>,std::allocator<std::pair<CString const,UserReportLicInfo>>,1>>::_Tree<std::_Tmap_traits<CString,UserReportLicInfo,std::less<CString>,std::allocator<std::pair<CString const,UserReportLicInfo>>,1>>(std::_Tree<std::_Tmap_traits<CString,UserReportLicInfo,std::less<CString>,std::allocator<std::pair<CString const,UserReportLicInfo>>,1>> const &,std::allocator<std::pair<CString const,UserReportLicInfo>> const &)
0x180055552  nop
0x180055553  lea     r8, [rbp+680h+var_6C0]
0x180055557  mov     rdx, rsi
0x18005555a  lea     rcx, [rsp+780h+var_720]
0x18005555f  call    ?AddSuccessFullPerUserLicensesToReport@@YAKV?$multimap@VCString@@UUserReportLicInfo@@U?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@UUserReportLicInfo@@@std@@@4@@std@@PEAU_iobuf@@PEAV?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@2@@Z; AddSuccessFullPerUserLicensesToReport(std::multimap<CString,UserReportLicInfo>,_iobuf *,std::map<CString,ulong> *)
0x180055564  mov     edi, eax
0x180055566  test    eax, eax
0x180055568  jnz     loc_180055AAE
0x18005556e  lea     rdx, [rbp+680h+var_6D0]
0x180055572  lea     rcx, aC50; "C50"
0x180055579  call    ?NumberOfLicensesInstalled@@YAKPEBGPEAV?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@@Z; NumberOfLicensesInstalled(ushort const *,std::map<CString,ulong> *)
0x18005557e  lea     rdx, [rbp+680h+var_6B0]
0x180055582  lea     rcx, aA02; "A02"
0x180055589  call    ?NumberOfLicensesInstalled@@YAKPEBGPEAV?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@@Z; NumberOfLicensesInstalled(ushort const *,std::map<CString,ulong> *)
0x18005558e  call    cs:__imp_RpcTestCancel
0x180055595  nop     dword ptr [rax+rax+00h]
0x18005559a  test    eax, eax
0x18005559c  jz      loc_180055AAE
0x1800555a2  lea     rax, [rsp+780h+var_720]
0x1800555a7  mov     [rsp+780h+Stream], rax
0x1800555ac  lea     rdx, [rbp+680h+var_6C0]
0x1800555b0  lea     rcx, [rsp+780h+var_720]
0x1800555b5  call    ??0?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@QEAA@AEBV01@@Z; std::map<CString,ulong>::map<CString,ulong>(std::map<CString,ulong> const &)
0x1800555ba  mov     rbx, rax
0x1800555bd  lea     rax, [rbp+680h+var_6F0]
0x1800555c1  mov     [rsp+780h+var_728], rax
0x1800555c6  lea     rdx, [rbp+680h+var_6D0]
0x1800555ca  lea     rcx, [rbp+680h+var_6F0]
0x1800555ce  call    ??0?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@QEAA@AEBV01@@Z; std::map<CString,ulong>::map<CString,ulong>(std::map<CString,ulong> const &)
0x1800555d3  nop
0x1800555d4  mov     rdx, rbx
0x1800555d7  mov     rcx, rax
0x1800555da  call    ?LogReportingEvents@@YAKV?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@0@Z; LogReportingEvents(std::map<CString,ulong>,std::map<CString,ulong>)
0x1800555df  mov     edi, eax
0x1800555e1  test    eax, eax
0x1800555e3  jnz     loc_180055AAE
0x1800555e9  call    cs:__imp_RpcTestCancel
0x1800555f0  nop     dword ptr [rax+rax+00h]
0x1800555f5  test    eax, eax
0x1800555f7  jz      loc_180055AAE
0x1800555fd  mov     rdx, rsi; Stream
0x180055600  lea     rcx, aDetailPerDevic; "DETAIL : PER-DEVICE LICENSING ISSUANCE "...
0x180055607  call    cs:__imp_fputws
0x18005560e  nop     dword ptr [rax+rax+00h]
0x180055613  mov     rcx, rsi; Stream
0x180055616  test    eax, eax
0x180055618  jns     short loc_18005562D
0x18005561a  call    cs:__imp_ferror
0x180055621  nop     dword ptr [rax+rax+00h]
0x180055626  mov     edi, eax
0x180055628  jmp     loc_180055AAE
0x18005562d  lea     rdx, [rbp+680h+var_6A0]
0x180055631  call    ?GetPerDeviceLicensingInfoFromDB@@YAKPEAU_iobuf@@PEAV?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@@Z; GetPerDeviceLicensingInfoFromDB(_iobuf *,std::map<CString,ulong> *)
0x180055636  mov     edi, eax
0x180055638  test    eax, eax
0x18005563a  jnz     loc_180055AAE
0x180055640  call    cs:__imp_RpcTestCancel
0x180055647  nop     dword ptr [rax+rax+00h]
0x18005564c  test    eax, eax
0x18005564e  jz      loc_180055AAE
0x180055654  mov     rdx, rsi; Stream
0x180055657  lea     rcx, aDetailPerUserL; "DETAIL : PER-USER LICENSING FAILED ISSU"...
0x18005565e  call    cs:__imp_fputws
0x180055665  nop     dword ptr [rax+rax+00h]
0x18005566a  mov     rcx, rsi
0x18005566d  test    eax, eax
0x18005566f  js      short loc_18005561A
0x180055671  lea     rdx, [rbp+680h+var_6E0]
0x180055675  call    ?GetFailedPerUserDetailsFromDB@@YAKPEAU_iobuf@@PEAV?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@@Z; GetFailedPerUserDetailsFromDB(_iobuf *,std::map<CString,ulong> *)
0x18005567a  mov     edi, eax
0x18005567c  lea     rdx, [rbp+680h+var_6E0]
0x180055680  lea     rcx, [rsp+780h+var_720]
0x180055685  call    ??0?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@QEAA@AEBV01@@Z; std::map<CString,ulong>::map<CString,ulong>(std::map<CString,ulong> const &)
0x18005568a  mov     r8, rax
0x18005568d  mov     [rsp+780h+var_728], rax
0x180055692  mov     r15d, r12d
0x180055695  mov     r9, [rax]
0x180055698  mov     rax, [r9]
0x18005569b  cmp     rax, r9
0x18005569e  jz      short loc_1800556D9
0x1800556a0  add     r15d, [rax+40h]
0x1800556a4  cmp     [rax+19h], r12b
0x1800556a8  jnz     short loc_18005569B
0x1800556aa  mov     rcx, [rax+10h]
0x1800556ae  cmp     [rcx+19h], r12b
0x1800556b2  jnz     short loc_1800556BB
0x1800556b4  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVCWorkObject@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBKPEAVCWorkObject@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CWorkObject *>>>::_Min(std::_Tree_node<std::pair<ulong const,CWorkObject *>,void *> *)
0x1800556b9  jmp     short loc_18005569B
0x1800556bb  mov     rcx, [rax+8]
0x1800556bf  jmp     short loc_1800556CE
0x1800556c1  cmp     rax, [rcx+10h]
0x1800556c5  jnz     short loc_1800556D4
0x1800556c7  mov     rax, rcx
0x1800556ca  mov     rcx, [rcx+8]
0x1800556ce  cmp     [rcx+19h], r12b
0x1800556d2  jz      short loc_1800556C1
0x1800556d4  mov     rax, rcx
0x1800556d7  jmp     short loc_18005569B
0x1800556d9  mov     rcx, r8
0x1800556dc  call    ??1?$_Tree@V?$_Tmap_traits@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<CString,ulong,std::less<CString>,std::allocator<std::pair<CString const,ulong>>,0>>::~_Tree<std::_Tmap_traits<CString,ulong,std::less<CString>,std::allocator<std::pair<CString const,ulong>>,0>>(void)
0x1800556e1  test    edi, edi
0x1800556e3  jnz     loc_180055AAE
0x1800556e9  mov     rdx, rsi; Stream
0x1800556ec  lea     rcx, aSummaryPerUser; "SUMMARY : PER-USER LICENSING FAILED ISS"...
0x1800556f3  call    cs:__imp_fputws
0x1800556fa  nop     dword ptr [rax+rax+00h]
0x1800556ff  test    eax, eax
0x180055701  jns     short loc_18005570B
0x180055703  mov     rcx, rsi
0x180055706  jmp     loc_18005561A
0x18005570b  mov     rbx, [rbp+680h+var_6E0]
0x18005570f  mov     rbx, [rbx]
0x180055712  cmp     rbx, [rbp+680h+var_6E0]
0x180055716  jz      short loc_18005578C
0x180055718  mov     eax, [rbx+40h]
0x18005571b  lea     r9, [rbx+20h]
0x18005571f  cmp     qword ptr [r9+18h], 8
0x180055724  jb      short loc_180055729
0x180055726  mov     r9, [r9]
0x180055729  mov     dword ptr [rsp+780h+var_760], eax
0x18005572d  lea     r8, aS016u; "%s,%016u,\n"
0x180055734  mov     rdx, r13; unsigned __int64
0x180055737  lea     rcx, [rbp+680h+Buffer]; unsigned __int16 *
0x18005573b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180055740  mov     rdx, rsi; Stream
0x180055743  lea     rcx, [rbp+680h+Buffer]; Buffer
0x180055747  call    cs:__imp_fputws
0x18005574e  nop     dword ptr [rax+rax+00h]
0x180055753  test    eax, eax
0x180055755  js      short loc_180055703
0x180055757  cmp     [rbx+19h], r12b
0x18005575b  jnz     short loc_180055712
0x18005575d  mov     rcx, [rbx+10h]
0x180055761  cmp     [rcx+19h], r12b
0x180055765  jnz     short loc_18005576E
0x180055767  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVCWorkObject@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBKPEAVCWorkObject@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CWorkObject *>>>::_Min(std::_Tree_node<std::pair<ulong const,CWorkObject *>,void *> *)
0x18005576c  jmp     short loc_180055787
0x18005576e  mov     rax, [rbx+8]
0x180055772  jmp     short loc_180055781
0x180055774  cmp     rbx, [rax+10h]
0x180055778  jnz     short loc_180055787
0x18005577a  mov     rbx, rax
0x18005577d  mov     rax, [rax+8]
0x180055781  cmp     [rax+19h], r12b
0x180055785  jz      short loc_180055774
0x180055787  mov     rbx, rax
0x18005578a  jmp     short loc_180055712
0x18005578c  call    cs:__imp_RpcTestCancel
0x180055793  nop     dword ptr [rax+rax+00h]
0x180055798  test    eax, eax
0x18005579a  jz      loc_180055AAE
0x1800557a0  mov     rdx, rsi; Stream
0x1800557a3  lea     rcx, aCalinfoheaderS; "CALINFOHEADER,START\n"
0x1800557aa  call    cs:__imp_fputws
0x1800557b1  nop     dword ptr [rax+rax+00h]
0x1800557b6  test    eax, eax
0x1800557b8  js      loc_180055703
0x1800557be  lea     rax, [rsp+780h+var_720]
0x1800557c3  mov     [rsp+780h+Stream], rax
0x1800557c8  lea     rdx, [rbp+680h+var_6C0]
0x1800557cc  lea     rcx, [rsp+780h+var_720]
0x1800557d1  call    ??0?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@QEAA@AEBV01@@Z; std::map<CString,ulong>::map<CString,ulong>(std::map<CString,ulong> const &)
0x1800557d6  mov     rbx, rax
0x1800557d9  lea     rax, [rbp+680h+var_6F0]
0x1800557dd  mov     [rsp+780h+var_728], rax
0x1800557e2  lea     rdx, [rbp+680h+var_6D0]
0x1800557e6  lea     rcx, [rbp+680h+var_6F0]
0x1800557ea  call    ??0?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@QEAA@AEBV01@@Z; std::map<CString,ulong>::map<CString,ulong>(std::map<CString,ulong> const &)
0x1800557ef  nop
0x1800557f0  lea     r8, [rbp+680h+var_700]
0x1800557f4  mov     rdx, rbx
0x1800557f7  mov     rcx, rax
0x1800557fa  call    ?GetInstalledIssuedMap@@YAXV?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@0PEAV?$map@VCString@@U_TLSCALInfo@@U?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@U_TLSCALInfo@@@std@@@4@@2@@Z; GetInstalledIssuedMap(std::map<CString,ulong>,std::map<CString,ulong>,std::map<CString,_TLSCALInfo> *)
0x1800557ff  lea     rax, [rsp+780h+var_720]
0x180055804  mov     [rsp+780h+var_708], rax
0x180055809  lea     rdx, [rbp+680h+var_6A0]
0x18005580d  lea     rcx, [rsp+780h+var_720]
0x180055812  call    ??0?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@QEAA@AEBV01@@Z; std::map<CString,ulong>::map<CString,ulong>(std::map<CString,ulong> const &)
0x180055817  mov     rbx, rax
0x18005581a  lea     rax, [rbp+680h+var_6F0]
0x18005581e  mov     [rsp+780h+var_710], rax
0x180055823  lea     rdx, [rbp+680h+var_6B0]
0x180055827  lea     rcx, [rbp+680h+var_6F0]
0x18005582b  call    ??0?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@QEAA@AEBV01@@Z; std::map<CString,ulong>::map<CString,ulong>(std::map<CString,ulong> const &)
0x180055830  nop
0x180055831  lea     r8, [rbp+680h+var_700]
0x180055835  mov     rdx, rbx
0x180055838  mov     rcx, rax
0x18005583b  call    ?GetInstalledIssuedMap@@YAXV?$map@VCString@@KU?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@K@std@@@3@@std@@0PEAV?$map@VCString@@U_TLSCALInfo@@U?$less@VCString@@@std@@V?$allocator@U?$pair@$$CBVCString@@U_TLSCALInfo@@@std@@@4@@2@@Z; GetInstalledIssuedMap(std::map<CString,ulong>,std::map<CString,ulong>,std::map<CString,_TLSCALInfo> *)
0x180055840  mov     rbx, [rbp+680h+var_700]
0x180055844  mov     rbx, [rbx]
  ... truncated ...
```
