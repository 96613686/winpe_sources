# CDtcInstanceConfig::VerifyLogPathSettings(ushort *)

- ea: `0x18004be10`
- end: `0x18004c19d`
- name: `?VerifyLogPathSettings@CDtcInstanceConfig@@AEAAJPEAG@Z`
- size: `909`
- prototype: `int(CDtcInstanceConfig *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004b750`

## callees

- `0x180003cf0`
- `0x18000d5f4`
- `0x18001daf8`
- `0x180027920`
- `0x180027994`
- `0x18004be10`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c12f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c12f`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18004bf61`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18004bf61`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18004bf84`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18004bf84`
- `MTXCLU!MtxCluVerifyLogPathIsValidCSV` at `0x18004c069`
- `MTXCLU!MtxCluVerifyLogPathIsValidCSV` at `0x18004c069`
- `MTXCLU!MtxCluVerifyLogPathInDependantDiskResource` at `0x18004c0d5`
- `MTXCLU!MtxCluVerifyLogPathInDependantDiskResource` at `0x18004c0d5`
- `SHLWAPI!PathIsNetworkPathW` at `0x18004bf71`
- `SHLWAPI!PathIsNetworkPathW` at `0x18004bf71`

## string_xrefs

- `0x18004be6b`: `com\complus\dtc\dtc\msdtcprx\src\dtcinstanceconfig.cpp`
- `0x18004be72`: `CDtcInstanceConfig::VerifyLogPathSettings`
- `0x18004bfac`: `CDtcInstanceConfig::VerifyLogPathSettings`
- `0x18004c03c`: `CDtcInstanceConfig::VerifyLogPathSettings`
- `0x18004c111`: `CDtcInstanceConfig::VerifyLogPathSettings`
- `0x18004c150`: `CDtcInstanceConfig::VerifyLogPathSettings`
- `0x18004bea1`: `CDtcInstanceConfig::VerifyLogPathSettings (com\complus\dtc\dtc\msdtcprx\src\dtcinstanceconfig.cpp@550): wszPath shouldn't be NULL`
- `0x18004bec6`: `StringCbCopyW failed`
- `0x18004c024`: `Only UNC remote paths are supported`
- `0x18004c0df`: `MtxCluVerifyLogPathInDependantDiskResource failed.`

## pseudocode

```c
__int64 __fastcall CDtcInstanceConfig::VerifyLogPathSettings(CDtcInstanceConfig *this, unsigned __int16 *a2)
{
  int v4; // ebx
  int v5; // r8d
  WCHAR *v6; // rcx
  int v7; // edx
  int v8; // r9d
  const wchar_t *v9; // rcx
  __int64 v10; // r9
  unsigned __int64 v11; // rcx
  __int64 v13; // [rsp+28h] [rbp-D8h]
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR RootPathName[261]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v17[6]; // [rsp+25Ah] [rbp+15Ah] BYREF

  pv = 0;
  v15 = 0;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
    548,
    L"CDtcInstanceConfig::VerifyLogPathSettings",
    0,
    L"In");
  if ( !a2 )
    DtcInternalErrorW(
      L"CDtcInstanceConfig::VerifyLogPathSettings (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp@550): wszP"
       "ath shouldn't be NULL");
  v4 = StringCbCopyW(RootPathName, 0x20Au, a2);
  if ( v4 < 0 )
  {
    LODWORD(v13) = v4;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
      555,
      L"CDtcInstanceConfig::VerifyLogPathSettings",
      v13,
      L"StringCbCopyW failed");
    goto LABEL_37;
  }
  v5 = 0;
  v6 = RootPathName;
  v7 = 0;
  v8 = 0;
  while ( *v6 )
  {
    if ( *v6 == 92 )
    {
      v8 = 1;
      if ( v6[1] == 92 )
      {
        v5 = 1;
        ++v6;
      }
      else
      {
        if ( !v5 || v7 )
          goto LABEL_15;
        v7 = 1;
      }
    }
    if ( ++v6 >= (WCHAR *)v17 )
      break;
  }
  if ( !v8 )
    goto LABEL_34;
LABEL_15:
  if ( (int)((v17 - (_BYTE *)v6) >> 1) < 2 )
  {
LABEL_34:
    v9 = L"TruncateAtRoot failed";
    v10 = 562;
LABEL_35:
    LODWORD(v13) = -2147024809;
    v4 = -2147024809;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
      v10,
      L"CDtcInstanceConfig::VerifyLogPathSettings",
      v13,
      v9);
    goto LABEL_37;
  }
  *(_DWORD *)v6 = 92;
  if ( GetDriveTypeW(RootPathName) != 3 )
  {
    if ( !PathIsNetworkPathW(RootPathName) )
    {
      v9 = L"DriveType is not fixed or remote/network.";
      v10 = 584;
      goto LABEL_35;
    }
    if ( !PathIsUNCW(RootPathName) )
    {
      v4 = -2147024809;
      LODWORD(v13) = -2147024809;
      TraceStringInline(
        15,
        1,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
        578,
        L"CDtcInstanceConfig::VerifyLogPathSettings",
        v13,
        L"Only UNC remote paths are supported");
      goto LABEL_37;
    }
    TraceStringInline(
      15,
      3,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
      573,
      L"CDtcInstanceConfig::VerifyLogPathSettings",
      0,
      L"DTC LOG has been set to a remote location please ensure the necessary permissions have been set");
  }
  if ( !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 24LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 8LL)) )
    goto LABEL_37;
  v4 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 64LL))(
         *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
         &pv);
  if ( v4 < 0 )
  {
    LODWORD(v13) = v4;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
      596,
      L"CDtcInstanceConfig::VerifyLogPathSettings",
      v13,
      L"GetResourceName failed");
    goto LABEL_37;
  }
  if ( !(unsigned int)MtxCluVerifyLogPathIsValidCSV(pv, a2) )
  {
    v4 = StringCchLengthW(RootPathName, 0x105u, &v15);
    if ( v4 < 0 )
    {
      LODWORD(v13) = v4;
      TraceStringInline(
        15,
        1,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
        609,
        L"CDtcInstanceConfig::VerifyLogPathSettings",
        v13,
        L"StringChLengthW failed");
      goto LABEL_37;
    }
    if ( v15 )
    {
      v11 = 2 * v15 - 2;
      if ( v11 >= 0x20A )
        _report_rangecheckfailure();
      *(WCHAR *)((char *)RootPathName + v11) = 0;
    }
    if ( !(unsigned int)MtxCluVerifyLogPathInDependantDiskResource(pv, RootPathName) )
    {
      v9 = L"MtxCluVerifyLogPathInDependantDiskResource failed.";
      v10 = 621;
      goto LABEL_35;
    }
  }
LABEL_37:
  CoTaskMemFree(pv);
  pv = 0;
  LODWORD(v13) = v4;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
    629,
    L"CDtcInstanceConfig::VerifyLogPathSettings",
    v13,
    L"Out");
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004be10  mov     [rsp-8+arg_10], rbx
0x18004be15  mov     [rsp-8+arg_18], rsi
0x18004be1a  push    rbp
0x18004be1b  push    rdi
0x18004be1c  push    r12
0x18004be1e  push    r13
0x18004be20  push    r14
0x18004be22  lea     rbp, [rsp-170h]
0x18004be2a  sub     rsp, 270h
0x18004be31  mov     rax, cs:__security_cookie
0x18004be38  xor     rax, rsp
0x18004be3b  mov     [rbp+190h+var_30], rax
0x18004be42  mov     rsi, rdx
0x18004be45  mov     [rsp+290h+pv], 0
0x18004be4e  mov     edx, 6
0x18004be53  mov     [rsp+290h+var_248], 0
0x18004be5c  lea     rax, aIn_0; "In"
0x18004be63  mov     r14, rcx
0x18004be66  mov     [rsp+290h+var_260], rax
0x18004be6b  lea     r12, aComComplusDtcD_12; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004be72  lea     rdi, aCdtcinstanceco_2; "CDtcInstanceConfig::VerifyLogPathSettin"...
0x18004be79  mov     [rsp+290h+var_268], 0
0x18004be82  lea     r13d, [rdx+9]
0x18004be86  mov     [rsp+290h+var_270], rdi
0x18004be8b  mov     ecx, r13d
0x18004be8e  mov     r9d, 224h
0x18004be94  mov     r8, r12
0x18004be97  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004be9c  test    rsi, rsi
0x18004be9f  jnz     short loc_18004BEAE
0x18004bea1  lea     rcx, aCdtcinstanceco_6; "CDtcInstanceConfig::VerifyLogPathSettin"...
0x18004bea8  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18004beae  mov     r8, rsi; unsigned __int16 *
0x18004beb1  lea     rcx, [rsp+290h+RootPathName]; unsigned __int16 *
0x18004beb6  mov     edx, 20Ah; unsigned __int64
0x18004bebb  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18004bec0  mov     ebx, eax
0x18004bec2  test    eax, eax
0x18004bec4  jns     short loc_18004BEEB
0x18004bec6  lea     rax, aStringcbcopywF_0; "StringCbCopyW failed"
0x18004becd  mov     r9d, 22Bh
0x18004bed3  mov     [rsp+290h+var_260], rax
0x18004bed8  mov     edx, 1
0x18004bedd  mov     dword ptr [rsp+290h+var_268], ebx
0x18004bee1  mov     [rsp+290h+var_270], rdi
0x18004bee6  jmp     loc_18004C11F
0x18004beeb  xor     r8d, r8d
0x18004beee  lea     rcx, [rsp+290h+RootPathName]
0x18004bef3  xor     edx, edx
0x18004bef5  xor     r9d, r9d
0x18004bef8  lea     r10d, [r8+5Ch]
0x18004befc  lea     edi, [rdx+1]
0x18004beff  xor     eax, eax
0x18004bf01  cmp     ax, [rcx]
0x18004bf04  jz      short loc_18004BF3A
0x18004bf06  cmp     r10w, [rcx]
0x18004bf0a  jnz     short loc_18004BF2A
0x18004bf0c  mov     r9d, edi
0x18004bf0f  cmp     r10w, [rcx+2]
0x18004bf14  jnz     short loc_18004BF1F
0x18004bf16  mov     r8d, edi
0x18004bf19  add     rcx, 2
0x18004bf1d  jmp     short loc_18004BF2A
0x18004bf1f  test    r8d, r8d
0x18004bf22  jz      short loc_18004BF43
0x18004bf24  test    edx, edx
0x18004bf26  jnz     short loc_18004BF43
0x18004bf28  mov     edx, edi
0x18004bf2a  add     rcx, 2
0x18004bf2e  lea     rax, [rbp+190h+var_36]
0x18004bf35  cmp     rcx, rax
0x18004bf38  jb      short loc_18004BEFF
0x18004bf3a  test    r9d, r9d
0x18004bf3d  jz      loc_18004C0F4
0x18004bf43  lea     rax, [rbp+190h+var_36]
0x18004bf4a  sub     rax, rcx
0x18004bf4d  sar     rax, 1
0x18004bf50  cmp     eax, 2
0x18004bf53  jl      loc_18004C0F4
0x18004bf59  mov     [rcx], r10d
0x18004bf5c  lea     rcx, [rsp+290h+RootPathName]; lpRootPathName
0x18004bf61  call    cs:__imp_GetDriveTypeW
0x18004bf67  cmp     eax, 3
0x18004bf6a  jz      short loc_18004BFC9
0x18004bf6c  lea     rcx, [rsp+290h+RootPathName]; pszPath
0x18004bf71  call    cs:__imp_PathIsNetworkPathW
0x18004bf77  test    eax, eax
0x18004bf79  jz      loc_18004C04F
0x18004bf7f  lea     rcx, [rsp+290h+RootPathName]; pszPath
0x18004bf84  call    cs:__imp_PathIsUNCW
0x18004bf8a  mov     r8, r12
0x18004bf8d  test    eax, eax
0x18004bf8f  jz      loc_18004C01F
0x18004bf95  lea     rax, aDtcLogHasBeenS; "DTC LOG has been set to a remote locati"...
0x18004bf9c  mov     r9d, 23Dh
0x18004bfa2  mov     [rsp+290h+var_260], rax
0x18004bfa7  mov     edx, 3
0x18004bfac  lea     rax, aCdtcinstanceco_2; "CDtcInstanceConfig::VerifyLogPathSettin"...
0x18004bfb3  mov     [rsp+290h+var_268], 0
0x18004bfbc  mov     ecx, r13d
0x18004bfbf  mov     [rsp+290h+var_270], rax
0x18004bfc4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004bfc9  mov     rax, [r14+10h]
0x18004bfcd  mov     rcx, [rax+8]
0x18004bfd1  mov     rax, [rcx]
0x18004bfd4  mov     rax, [rax+18h]
0x18004bfd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bfdd  test    eax, eax
0x18004bfdf  jz      loc_18004C12A
0x18004bfe5  mov     rax, [r14+10h]
0x18004bfe9  lea     rdx, [rsp+290h+pv]
0x18004bfee  mov     rcx, [rax+8]
0x18004bff2  mov     rax, [rcx]
0x18004bff5  mov     rax, [rax+40h]
0x18004bff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bffe  mov     ebx, eax
0x18004c000  test    eax, eax
0x18004c002  jns     short loc_18004C061
0x18004c004  lea     rax, aGetresourcenam; "GetResourceName failed"
0x18004c00b  mov     r9d, 254h
0x18004c011  mov     [rsp+290h+var_260], rax
0x18004c016  mov     dword ptr [rsp+290h+var_268], ebx
0x18004c01a  jmp     loc_18004C111
0x18004c01f  mov     eax, 80070057h
0x18004c024  lea     rcx, aOnlyUncRemoteP; "Only UNC remote paths are supported"
0x18004c02b  mov     [rsp+290h+var_260], rcx
0x18004c030  mov     ebx, eax
0x18004c032  mov     dword ptr [rsp+290h+var_268], eax
0x18004c036  mov     r9d, 242h
0x18004c03c  lea     rax, aCdtcinstanceco_2; "CDtcInstanceConfig::VerifyLogPathSettin"...
0x18004c043  mov     edx, edi
0x18004c045  mov     [rsp+290h+var_270], rax
0x18004c04a  jmp     loc_18004C122
0x18004c04f  lea     rcx, aDrivetypeIsNot; "DriveType is not fixed or remote/networ"...
0x18004c056  mov     r9d, 248h
0x18004c05c  jmp     loc_18004C101
0x18004c061  mov     rcx, [rsp+290h+pv]
0x18004c066  mov     rdx, rsi
0x18004c069  call    cs:__imp_MtxCluVerifyLogPathIsValidCSV
0x18004c06f  test    eax, eax
0x18004c071  jnz     loc_18004C12A
0x18004c077  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x18004c07c  mov     edx, 105h; unsigned __int64
0x18004c081  lea     rcx, [rsp+290h+RootPathName]; unsigned __int16 *
0x18004c086  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004c08b  mov     ebx, eax
0x18004c08d  test    eax, eax
0x18004c08f  jns     short loc_18004C0A9
0x18004c091  lea     rax, aStringchlength; "StringChLengthW failed"
0x18004c098  mov     r9d, 261h
0x18004c09e  mov     [rsp+290h+var_260], rax
0x18004c0a3  mov     dword ptr [rsp+290h+var_268], ebx
0x18004c0a7  jmp     short loc_18004C111
0x18004c0a9  mov     rax, [rsp+290h+var_248]
0x18004c0ae  test    rax, rax
0x18004c0b1  jz      short loc_18004C0CB
0x18004c0b3  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18004c0bb  cmp     rcx, 20Ah
0x18004c0c2  jnb     short loc_18004C0EE
0x18004c0c4  xor     eax, eax
0x18004c0c6  mov     [rsp+rcx+290h+RootPathName], ax
0x18004c0cb  mov     rcx, [rsp+290h+pv]
0x18004c0d0  lea     rdx, [rsp+290h+RootPathName]
0x18004c0d5  call    cs:__imp_MtxCluVerifyLogPathInDependantDiskResource
0x18004c0db  test    eax, eax
0x18004c0dd  jnz     short loc_18004C12A
0x18004c0df  lea     rcx, aMtxcluverifylo; "MtxCluVerifyLogPathInDependantDiskResou"...
0x18004c0e6  mov     r9d, 26Dh
0x18004c0ec  jmp     short loc_18004C101
0x18004c0ee  call    __report_rangecheckfailure
0x18004c0f4  lea     rcx, aTruncateatroot; "TruncateAtRoot failed"
0x18004c0fb  mov     r9d, 232h
0x18004c101  mov     eax, 80070057h
0x18004c106  mov     [rsp+290h+var_260], rcx
0x18004c10b  mov     dword ptr [rsp+290h+var_268], eax
0x18004c10f  mov     ebx, eax
0x18004c111  lea     rax, aCdtcinstanceco_2; "CDtcInstanceConfig::VerifyLogPathSettin"...
0x18004c118  mov     edx, edi
0x18004c11a  mov     [rsp+290h+var_270], rax
0x18004c11f  mov     r8, r12
0x18004c122  mov     ecx, r13d
0x18004c125  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004c12a  mov     rcx, [rsp+290h+pv]; pv
0x18004c12f  call    cs:__imp_CoTaskMemFree
0x18004c135  lea     rax, aOut; "Out"
0x18004c13c  mov     [rsp+290h+pv], 0
0x18004c145  mov     [rsp+290h+var_260], rax
0x18004c14a  mov     r9d, 275h
0x18004c150  lea     rax, aCdtcinstanceco_2; "CDtcInstanceConfig::VerifyLogPathSettin"...
0x18004c157  mov     dword ptr [rsp+290h+var_268], ebx
0x18004c15b  mov     r8, r12
0x18004c15e  mov     [rsp+290h+var_270], rax
0x18004c163  mov     edx, 6
0x18004c168  mov     ecx, r13d
0x18004c16b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004c170  mov     eax, ebx
0x18004c172  mov     rcx, [rbp+190h+var_30]
0x18004c179  xor     rcx, rsp; StackCookie
0x18004c17c  call    __security_check_cookie
0x18004c181  lea     r11, [rsp+290h+var_20]
0x18004c189  mov     rbx, [r11+40h]
0x18004c18d  mov     rsi, [r11+48h]
0x18004c191  mov     rsp, r11
0x18004c194  pop     r14
0x18004c196  pop     r13
0x18004c198  pop     r12
0x18004c19a  pop     rdi
0x18004c19b  pop     rbp
0x18004c19c  retn
```
