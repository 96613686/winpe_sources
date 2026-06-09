# CNonClusterTmInstance::PerfCounterFileMappingNameAndSDDL(ushort * *,ushort * *)

- ea: `0x1800065c0`
- end: `0x18000675d`
- name: `?PerfCounterFileMappingNameAndSDDL@CNonClusterTmInstance@@UEAAJPEAPEAG0@Z`
- size: `413`
- prototype: `__int64 __fastcall(CNonClusterTmInstance *this, LPVOID *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800065c0`
- `0x180006764`
- `0x18000d5f4`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000672e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006737`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006741`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000672e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006737`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006741`

## string_xrefs

- `0x180006639`: `com\complus\dtc\dtc\adme\nonclustertminstance.cpp`
- `0x1800066ed`: `com\complus\dtc\dtc\adme\nonclustertminstance.cpp`
- `0x1800065f3`: `CNonClusterTmInstance::PerfCounterFileMappingNameAndSDDL (com\complus\dtc\dtc\adme\nonclustertminstance.cpp@1321): NULL != ppwszFileMappingName`
- `0x180006605`: `CNonClusterTmInstance::PerfCounterFileMappingNameAndSDDL (com\complus\dtc\dtc\adme\nonclustertminstance.cpp@1322): NULL != ppwszSDDL`
- `0x1800066a4`: `GetServiceSidString failed.`

## pseudocode

```c
__int64 __fastcall CNonClusterTmInstance::PerfCounterFileMappingNameAndSDDL(
        CNonClusterTmInstance *this,
        LPVOID *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v3; // rsi
  int StringW; // ebx
  const wchar_t *v8; // rax
  __int64 v9; // r9
  __int64 v10; // rcx
  __int64 v12; // [rsp+28h] [rbp-28h]
  LPVOID v13[2]; // [rsp+40h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+38h] BYREF
  unsigned __int16 *v15; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  pv = 0;
  v15 = 0;
  v13[0] = 0;
  if ( !a2 )
    DtcInternalErrorW(
      L"CNonClusterTmInstance::PerfCounterFileMappingNameAndSDDL (com\\complus\\dtc\\dtc\\adme\\nonclustertminstance.cpp@1"
       "321): NULL != ppwszFileMappingName");
  if ( !a3 )
    DtcInternalErrorW(
      L"CNonClusterTmInstance::PerfCounterFileMappingNameAndSDDL (com\\complus\\dtc\\dtc\\adme\\nonclustertminstance.cpp@1"
       "322): NULL != ppwszSDDL");
  *a2 = 0;
  *a3 = 0;
  if ( *((_DWORD *)this + 6) )
  {
    StringW = -2147168241;
    v8 = L"Request made for a RemoteProxyTmInstance - not supported.";
    v9 = 1332;
LABEL_7:
    v10 = 7;
LABEL_8:
    LODWORD(v12) = StringW;
    TraceStringInline(
      v10,
      1,
      L"com\\complus\\dtc\\dtc\\adme\\nonclustertminstance.cpp",
      v9,
      L"CNonClusterTmInstance::PerfCounterFileMappingNameAndSDDL",
      v12,
      v8);
    goto LABEL_16;
  }
  StringW = MakeStringW((unsigned __int16 **)&pv, L"%s", L"Global\\MSDTC_STATS_FILE");
  if ( StringW < 0 )
  {
    v8 = L"Error from MakeStringW for FileMappingName";
    v9 = 1339;
    goto LABEL_7;
  }
  StringW = (*(__int64 (__fastcall **)(CNonClusterTmInstance *, LPVOID *))(*(_QWORD *)this + 72LL))(this, v13);
  if ( StringW < 0 )
  {
    v8 = L"GetServiceSidString failed.";
    v9 = 1346;
    v10 = 8;
    goto LABEL_8;
  }
  StringW = MakeStringW(
              &v15,
              L"%s%s)",
              L"D:(A;OICI;CCLCRC;;;WD)(A;OICI;CCDCLCSWRPSDRCWDWO;;;BA)(A;OICI;CCDCLCSWRPSDRCWDWO;;;SY)(A;OICI;CCDCLCRC;;;",
              v13[0]);
  if ( StringW >= 0 )
  {
    *a2 = pv;
    *a3 = v15;
    pv = 0;
  }
  else
  {
    LODWORD(v12) = StringW;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\dtc\\adme\\nonclustertminstance.cpp",
      1352,
      L"CNonClusterTmInstance::PerfCounterFileMappingNameAndSDDL",
      v12,
      L"Error from MakeStringW for SDDL");
    v3 = v15;
  }
LABEL_16:
  CoTaskMemFree(pv);
  CoTaskMemFree(v3);
  CoTaskMemFree(v13[0]);
  return (unsigned int)StringW;
}

```

## disassembly

```asm
0x1800065c0  mov     [rsp-28h+arg_0], rbx
0x1800065c5  push    rbp
0x1800065c6  push    rsi
0x1800065c7  push    rdi
0x1800065c8  push    r14
0x1800065ca  push    r15
0x1800065cc  mov     rbp, rsp
0x1800065cf  sub     rsp, 50h
0x1800065d3  xor     esi, esi
0x1800065d5  mov     [rbp+pv], 0
0x1800065dd  mov     [rbp+arg_18], rsi
0x1800065e1  mov     rdi, r8
0x1800065e4  mov     [rbp+var_10], rsi
0x1800065e8  mov     r14, rdx
0x1800065eb  mov     r15, rcx
0x1800065ee  test    rdx, rdx
0x1800065f1  jnz     short loc_180006600
0x1800065f3  lea     rcx, aCnonclustertmi_4; "CNonClusterTmInstance::PerfCounterFileM"...
0x1800065fa  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180006600  test    rdi, rdi
0x180006603  jnz     short loc_180006612
0x180006605  lea     rcx, aCnonclustertmi_6; "CNonClusterTmInstance::PerfCounterFileM"...
0x18000660c  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180006612  mov     [rdx], rsi
0x180006615  mov     [r8], rsi
0x180006618  cmp     [rcx+18h], esi
0x18000661b  jz      short loc_18000665F
0x18000661d  mov     ebx, 8004D00Fh
0x180006622  lea     rax, aRequestMadeFor; "Request made for a RemoteProxyTmInstanc"...
0x180006629  mov     r9d, 534h
0x18000662f  mov     ecx, 7
0x180006634  mov     [rsp+50h+var_20], rax
0x180006639  lea     r8, aComComplusDtcD_46; "com\\complus\\dtc\\dtc\\adme\\noncluste"...
0x180006640  lea     rax, aCnonclustertmi; "CNonClusterTmInstance::PerfCounterFileM"...
0x180006647  mov     dword ptr [rsp+50h+var_28], ebx
0x18000664b  mov     edx, 1
0x180006650  mov     [rsp+50h+var_30], rax
0x180006655  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000665a  jmp     loc_18000672A
0x18000665f  lea     r8, aGlobalMsdtcSta; "Global\\MSDTC_STATS_FILE"
0x180006666  lea     rdx, aS; "%s"
0x18000666d  lea     rcx, [rbp+pv]; unsigned __int16 **
0x180006671  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x180006676  mov     ebx, eax
0x180006678  test    eax, eax
0x18000667a  jns     short loc_18000668B
0x18000667c  lea     rax, aErrorFromMakes; "Error from MakeStringW for FileMappingN"...
0x180006683  mov     r9d, 53Bh
0x180006689  jmp     short loc_18000662F
0x18000668b  mov     rax, [r15]
0x18000668e  lea     rdx, [rbp+var_10]
0x180006692  mov     rcx, r15
0x180006695  mov     rax, [rax+48h]
0x180006699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000669e  mov     ebx, eax
0x1800066a0  test    eax, eax
0x1800066a2  jns     short loc_1800066BB
0x1800066a4  lea     rax, aGetservicesids; "GetServiceSidString failed."
0x1800066ab  mov     r9d, 542h
0x1800066b1  mov     ecx, 8
0x1800066b6  jmp     loc_180006634
0x1800066bb  mov     r9, [rbp+var_10]
0x1800066bf  lea     r8, aDAOiciCclcrcWd; "D:(A;OICI;CCLCRC;;;WD)(A;OICI;CCDCLCSWR"...
0x1800066c6  lea     rdx, aSS_2; "%s%s)"
0x1800066cd  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x1800066d1  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x1800066d6  mov     ebx, eax
0x1800066d8  test    eax, eax
0x1800066da  jns     short loc_180006718
0x1800066dc  mov     edx, 1
0x1800066e1  lea     rax, aErrorFromMakes_0; "Error from MakeStringW for SDDL"
0x1800066e8  mov     [rsp+50h+var_20], rax
0x1800066ed  lea     r8, aComComplusDtcD_46; "com\\complus\\dtc\\dtc\\adme\\noncluste"...
0x1800066f4  lea     rax, aCnonclustertmi; "CNonClusterTmInstance::PerfCounterFileM"...
0x1800066fb  mov     dword ptr [rsp+50h+var_28], ebx
0x1800066ff  mov     r9d, 548h
0x180006705  mov     [rsp+50h+var_30], rax
0x18000670a  lea     ecx, [rdx+6]
0x18000670d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180006712  mov     rsi, [rbp+arg_18]
0x180006716  jmp     short loc_18000672A
0x180006718  mov     rax, [rbp+pv]
0x18000671c  mov     [r14], rax
0x18000671f  mov     rax, [rbp+arg_18]
0x180006723  mov     [rdi], rax
0x180006726  mov     [rbp+pv], rsi
0x18000672a  mov     rcx, [rbp+pv]; pv
0x18000672e  call    cs:__imp_CoTaskMemFree
0x180006734  mov     rcx, rsi; pv
0x180006737  call    cs:__imp_CoTaskMemFree
0x18000673d  mov     rcx, [rbp+var_10]; pv
0x180006741  call    cs:__imp_CoTaskMemFree
0x180006747  mov     eax, ebx
0x180006749  mov     rbx, [rsp+50h+arg_0]
0x180006751  add     rsp, 50h
0x180006755  pop     r15
0x180006757  pop     r14
0x180006759  pop     rdi
0x18000675a  pop     rsi
0x18000675b  pop     rbp
0x18000675c  retn
```
