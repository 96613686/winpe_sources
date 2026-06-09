# GetComputerTokenForADRS(long (*)(ushort const *,ushort const *,ushort const *,ushort const *,_DSR_INSTANCE,ushort const *,_GUID const &,void (*)(ulong,ushort const *),ushort * *),std::shared_ptr<TenantInfo>,ushort * *,_GUID const &)

- ea: `0x18003b9b4`
- end: `0x18003c157`
- name: `?GetComputerTokenForADRS@@YAJP6AJPEBG000W4_DSR_INSTANCE@@0AEBU_GUID@@P6AXK0@ZPEAPEAG@ZV?$shared_ptr@VTenantInfo@@@std@@42@Z`
- size: `1955`
- prototype: ``
- caller_count: `2`
- callee_count: `27`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027a74`
- `0x1800aee10`

## callees

- `0x180005ba0`
- `0x18000bac0`
- `0x18000eda4`
- `0x180012c7c`
- `0x180016190`
- `0x180016ae0`
- `0x180026f8c`
- `0x18002927c`
- `0x1800292ac`
- `0x180029554`
- `0x180029c78`
- `0x18002b9b4`
- `0x18002b9f4`
- `0x18002dd24`
- `0x1800319ac`
- `0x18003b9b4`
- `0x18003c160`
- `0x18003c1cc`
- `0x18003c1f8`
- `0x180042278`
- `0x180043ef8`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`
- `0x180097d44`
- `0x1800ae000`
- `0x1800bf010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18003bed9`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18003bed9`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18003bef0`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18003bef0`

## string_xrefs

- `0x18003ba7e`: `GetComputerTokenForADRS: Invalid DSR_INSTANCE value`
- `0x18003bc5d`: `GetComputerTokenForADRS: Unable to parse auth code endpoint URL from discovery metadata`
- `0x18003ba2b`: `GetComputerTokenForADRS: Unable to read target environment`
- `0x18003bb06`: `https://login.microsoftonline.com/common`
- `0x18003bb2a`: `%s: Get token for ADRS\n`
- `0x18003ba9e`: `GetComputerTokenForADRS`
- `0x18003bb23`: `GetComputerTokenForADRS`
- `0x18003baa5`: `%s: Get token for enterprise DRS\n`
- `0x18003bcd7`: `/common`
- `0x18003be58`: `%s: Token is empty.\n`
- `0x18003bd3e`: `%s: Token request authority: "%s"\n`
- `0x18003bd84`: `%s: Token request authority: "%s"\n`
- `0x18003bda8`: `%s: Token request authority: "%s"\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetComputerTokenForADRS(
        __int64 (__fastcall *a1)(char **, const WCHAR *, _QWORD, const wchar_t *, int, __int64, __int64, void (*)(unsigned int, const unsigned __int16 *), void **),
        __int64 **a2,
        _QWORD *a3,
        __int64 a4)
{
  int TargetEnvironment; // ebx
  const unsigned __int16 *v9; // rax
  __int64 v10; // rcx
  std::_Ref_count_base *v11; // rcx
  TenantInfo *v13; // rcx
  __int64 v14; // rdx
  const unsigned __int16 *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  _QWORD *CurrentRef; // rax
  __int64 v20; // rdx
  _QWORD *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  _QWORD *v26; // rax
  __int64 v27; // rdx
  _QWORD *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rcx
  _QWORD *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rbx
  __int64 v40; // rax
  const unsigned __int16 *v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // r15
  char **v45; // r8
  __int64 v46; // rdx
  __int64 v47; // rcx
  _QWORD *v48; // rax
  __int64 v49; // rdx
  _QWORD *v50; // rax
  __int64 v51; // rdx
  char **v52; // rbx
  __int64 v53; // rax
  char **v54; // r8
  __int64 v55; // rdx
  __int64 v56; // rcx
  int v57; // ebx
  __int64 v58; // rax
  const wchar_t *v59; // r9
  char **v60; // rax
  int v61; // r15d
  __int64 v62; // rdx
  void *v63; // rcx
  __int64 v64; // rdx
  __int64 v65; // rcx
  _QWORD *v66; // rax
  __int64 v67; // rdx
  _QWORD *v68; // rax
  __int64 v69; // rcx
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rbx
  struct AutoJoinTelemetryInfo *AutoRegistrationJoinEventData; // rax
  __int64 v74; // rax
  __int64 v75; // rbx
  struct AutoJoinTelemetryInfo *v76; // rax
  _QWORD *v77; // rdx
  __int64 v78; // rax
  __int64 v79; // rdx
  __int64 v80; // rcx
  _QWORD *v81; // r8
  __int64 v82; // rdx
  __int64 v83; // rcx
  _QWORD *v84; // rax
  __int64 v85; // rdx
  __int64 v86; // rdx
  __int64 v87; // rcx
  _QWORD *v88; // rbx
  __int64 v89; // rax
  _QWORD *v90; // r8
  struct AutoJoinTelemetryInfo *v91; // rax
  __int64 v92; // rbx
  struct AutoJoinTelemetryInfo *v93; // rax
  const unsigned __int16 *v94; // rax
  const unsigned __int16 *v95; // r9
  const unsigned __int16 *v96; // rdx
  std::_Ref_count_base *v97; // rcx
  int v98; // [rsp+50h] [rbp-B0h] BYREF
  void *Block[3]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v100[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v101[232]; // [rsp+78h] [rbp-88h] BYREF
  char *Src[3]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v103; // [rsp+178h] [rbp+78h]
  _QWORD v104[3]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int64 v105; // [rsp+198h] [rbp+98h]
  unsigned __int16 *v106[4]; // [rsp+1A0h] [rbp+A0h] BYREF

  Block[1] = a2;
  v98 = 1;
  if ( a3 )
    *a3 = 0;
  TargetEnvironment = GetTargetEnvironment((enum _DSREG_TARGET_ENVIRONMENT *)&v98);
  if ( TargetEnvironment < 0 )
  {
    v9 = TenantInfo::TenantTypeName((TenantInfo *)*a2);
    Logger::WriteDsRegCmdAuthFailureEvent(
      TargetEnvironment,
      L"GetComputerTokenForADRS: Unable to read target environment",
      v9,
      *(const unsigned __int16 **)(v10 + 208));
LABEL_5:
    v11 = (std::_Ref_count_base *)a2[1];
    if ( v11 )
      std::_Ref_count_base::_Decref(v11);
    return (unsigned int)TargetEnvironment;
  }
  std::wstring::wstring((__int64)Src);
  v13 = (TenantInfo *)*a2;
  v14 = *((unsigned int *)*a2 + 60);
  if ( (_DWORD)v14 )
  {
    if ( (_DWORD)v14 != 1 )
    {
      v15 = TenantInfo::TenantTypeName(v13);
      TargetEnvironment = -2147024809;
      Logger::WriteDsRegCmdAuthFailureEvent(
        -2147024809,
        L"GetComputerTokenForADRS: Invalid DSR_INSTANCE value",
        v15,
        *(const unsigned __int16 **)(v16 + 208));
LABEL_26:
      std::wstring::_Tidy_deallocate((__int64)Src);
      goto LABEL_5;
    }
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v13, v14) )
    {
      wprintf(L"%s: Get token for enterprise DRS\n", L"GetComputerTokenForADRS");
      CurrentRef = (_QWORD *)CmdOptions::GetCurrentRef(v18, v17);
      if ( *(_BYTE *)(*CurrentRef + 12LL) )
      {
        v21 = (_QWORD *)CmdOptions::GetCurrentRef(*CurrentRef, v20);
        if ( *(_QWORD *)(*v21 + 184LL) )
        {
          v23 = CmdOptions::GetCurrentRef(v22, *v21);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v23 + 184LL),
            L"%s: Get token for enterprise DRS\n",
            L"GetComputerTokenForADRS");
        }
      }
    }
    Logger::TraceVerbose((wchar_t *)L"%s: Get token for enterprise DRS\n", L"GetComputerTokenForADRS");
    std::wstring::_Assign<unsigned short>(Src, L"https://login.microsoftonline.com/common", (char *)0x28);
  }
  else
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v13, v14) )
    {
      wprintf(L"%s: Get token for ADRS\n", L"GetComputerTokenForADRS");
      v26 = (_QWORD *)CmdOptions::GetCurrentRef(v25, v24);
      if ( *(_BYTE *)(*v26 + 12LL) )
      {
        v28 = (_QWORD *)CmdOptions::GetCurrentRef(*v26, v27);
        if ( *(_QWORD *)(*v28 + 184LL) )
        {
          v30 = CmdOptions::GetCurrentRef(v29, *v28);
          fwprintf_s(*(FILE *const *)(*(_QWORD *)v30 + 184LL), L"%s: Get token for ADRS\n", L"GetComputerTokenForADRS");
        }
      }
    }
    Logger::TraceVerbose((wchar_t *)L"%s: Get token for ADRS\n", L"GetComputerTokenForADRS");
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v32, v31) )
    {
      wprintf(L"%s: Auth code URL: \"%s\"\n", L"GetComputerTokenForADRS", *(_QWORD *)(**a2 + 24));
      v35 = (_QWORD *)CmdOptions::GetCurrentRef(v34, v33);
      if ( *(_BYTE *)(*v35 + 12LL) )
      {
        if ( *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(*v35, v36) + 184LL) )
        {
          v38 = **a2;
          v39 = *(_QWORD *)(v38 + 24);
          v40 = CmdOptions::GetCurrentRef(v38, v37);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v40 + 184LL),
            L"%s: Auth code URL: \"%s\"\n",
            L"GetComputerTokenForADRS",
            v39);
        }
      }
    }
    Logger::TraceVerbose((wchar_t *)L"%s: Auth code URL: \"%s\"\n", L"GetComputerTokenForADRS", *(_QWORD *)(**a2 + 24));
    std::wstring::wstring((__int64)v106);
    std::wstring::wstring((__int64)v104);
    TargetEnvironment = TenantInfo::GetUrlHostAndPath(*(LPCWSTR *)(**a2 + 24));
    if ( TargetEnvironment < 0 )
    {
      v41 = TenantInfo::TenantTypeName((TenantInfo *)*a2);
      Logger::WriteDsRegCmdAuthFailureEvent(
        TargetEnvironment,
        L"GetComputerTokenForADRS: Unable to parse auth code endpoint URL from discovery metadata",
        v41,
        *(const unsigned __int16 **)(v42 + 208));
      std::wstring::_Tidy_deallocate((__int64)v104);
      std::wstring::_Tidy_deallocate((__int64)v106);
      goto LABEL_26;
    }
    std::wstring::_Assign<unsigned short>(Src, L"https://", (char *)8);
    std::wstring::_Append<unsigned short>(Src);
    std::wstring::_Append<unsigned short>(Src);
    std::wstring::_Tidy_deallocate((__int64)v104);
    std::wstring::_Tidy_deallocate((__int64)v106);
  }
  Block[0] = 0;
  v43 = *((_DWORD *)*a2 + 60) != 0 ? 0x18 : 0;
  v44 = *(__int64 *)((char *)*a2 + v43 + 208);
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v43, *a2) )
  {
    v45 = Src;
    if ( v103 > 7 )
      v45 = (char **)Src[0];
    wprintf(L"%s: Token request authority: \"%s\"\n", L"GetComputerTokenForADRS", v45);
    v48 = (_QWORD *)CmdOptions::GetCurrentRef(v47, v46);
    if ( *(_BYTE *)(*v48 + 12LL) )
    {
      v50 = (_QWORD *)CmdOptions::GetCurrentRef(*v48, v49);
      if ( *(_QWORD *)(*v50 + 184LL) )
      {
        v52 = Src;
        if ( v103 > 7 )
          v52 = (char **)Src[0];
        v53 = CmdOptions::GetCurrentRef(*v50, v51);
        fwprintf_s(
          *(FILE *const *)(*(_QWORD *)v53 + 184LL),
          L"%s: Token request authority: \"%s\"\n",
          L"GetComputerTokenForADRS",
          v52);
      }
    }
  }
  v54 = Src;
  if ( v103 > 7 )
    v54 = (char **)Src[0];
  Logger::TraceVerbose((wchar_t *)L"%s: Token request authority: \"%s\"\n", L"GetComputerTokenForADRS", v54);
  v57 = *((_DWORD *)*a2 + 60);
  if ( v98 == 2
    || (v58 = CmdOptions::GetCurrentRef(v56, v55), v59 = &cchOriginalDestLength, *(_BYTE *)(*(_QWORD *)v58 + 2LL)) )
  {
    v59 = L"slice=testslice";
  }
  v60 = Src;
  if ( v103 > 7 )
    v60 = (char **)Src[0];
  v61 = a1(
          v60,
          L"dd762716-544d-4aeb-a526-687b73838a22",
          *(_QWORD *)(**a2 + 56),
          v59,
          v57,
          v44,
          a4,
          GetTokenLogCallback,
          Block);
  if ( v61 >= 0 )
  {
    if ( !(unsigned int)IsEmptyString((const unsigned __int16 *)Block[0]) )
    {
      if ( a3 )
      {
        *a3 = v63;
        v63 = 0;
        Block[0] = 0;
      }
      goto LABEL_68;
    }
    v61 = -2145647339;
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v63, v62) )
    {
      wprintf(L"%s: Token is empty.\n", L"GetComputerTokenForADRS");
      v66 = (_QWORD *)CmdOptions::GetCurrentRef(v65, v64);
      if ( *(_BYTE *)(*v66 + 12LL) )
      {
        v68 = (_QWORD *)CmdOptions::GetCurrentRef(*v66, v67);
        if ( *(_QWORD *)(*v68 + 184LL) )
        {
          v70 = CmdOptions::GetCurrentRef(v69, *v68);
          fwprintf_s(*(FILE *const *)(*(_QWORD *)v70 + 184LL), L"%s: Token is empty.\n", L"GetComputerTokenForADRS");
        }
      }
    }
    Logger::TraceVerbose((wchar_t *)L"%s: Token is empty.\n", L"GetComputerTokenForADRS");
  }
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v100);
  v71 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v100, (__int64)L"AdalErrorCode: 0x");
  v72 = std::basic_ostream<unsigned short>::operator<<(v71, std::hex);
  AutoRegistrationJoinEventData = GetAutoRegistrationJoinEventData();
  v74 = std::basic_ostream<unsigned short>::operator<<(v72, *((unsigned int *)AutoRegistrationJoinEventData + 64));
  std::basic_ostream<unsigned short>::operator<<(v74, 10);
  v75 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v100, (__int64)L"AdalCorrelationId: ");
  v76 = GetAutoRegistrationJoinEventData();
  v77 = (_QWORD *)((char *)v76 + 192);
  if ( *((_QWORD *)v76 + 27) > 7u )
    v77 = (_QWORD *)*v77;
  v78 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v75, (__int64)v77);
  std::basic_ostream<unsigned short>::operator<<(v78, 10);
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v80, v79) )
  {
    std::basic_stringbuf<unsigned short>::str(v101, v104);
    v81 = v104;
    if ( v105 > 7 )
      v81 = (_QWORD *)v104[0];
    wprintf(L"%s: %s", L"GetComputerTokenForADRS", v81);
    std::wstring::_Tidy_deallocate((__int64)v104);
    v84 = (_QWORD *)CmdOptions::GetCurrentRef(v83, v82);
    if ( *(_BYTE *)(*v84 + 12LL) && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(*v84, v85) + 184LL) )
    {
      std::basic_stringbuf<unsigned short>::str(v101, v104);
      v88 = v104;
      if ( v105 > 7 )
        v88 = (_QWORD *)v104[0];
      v89 = CmdOptions::GetCurrentRef(v87, v86);
      fwprintf_s(*(FILE *const *)(*(_QWORD *)v89 + 184LL), L"%s: %s", L"GetComputerTokenForADRS", v88);
      std::wstring::_Tidy_deallocate((__int64)v104);
    }
  }
  std::basic_stringbuf<unsigned short>::str(v101, v104);
  v90 = v104;
  if ( v105 > 7 )
    v90 = (_QWORD *)v104[0];
  Logger::TraceVerbose((wchar_t *)L"%s: %s", L"GetComputerTokenForADRS", v90);
  std::wstring::_Tidy_deallocate((__int64)v104);
  if ( *((_QWORD *)GetAutoRegistrationJoinEventData() + 30) )
  {
    v91 = GetAutoRegistrationJoinEventData();
    if ( (unsigned __int8)std::operator!=<unsigned short>((char *)v91 + 224) )
    {
      v92 = std::basic_ostream<unsigned short>::operator<<(v100, 10);
      v93 = GetAutoRegistrationJoinEventData();
      std::operator<<<unsigned short>(v92, (_QWORD *)v93 + 28);
    }
  }
  std::basic_stringbuf<unsigned short>::str(v101, v106);
  DsrCmdStringHelper::TrimMessageForEventViewer(v106);
  v94 = TenantInfo::TenantTypeName((TenantInfo *)*a2);
  v96 = (const unsigned __int16 *)v106;
  if ( v106[3] > (unsigned __int16 *)7 )
    v96 = v106[0];
  Logger::WriteDsRegCmdAuthFailureEvent(v61, v96, v94, v95);
  std::wstring::_Tidy_deallocate((__int64)v106);
  std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v100);
  v63 = Block[0];
LABEL_68:
  operator delete(v63);
  Block[0] = 0;
  std::wstring::_Tidy_deallocate((__int64)Src);
  v97 = (std::_Ref_count_base *)a2[1];
  if ( v97 )
    std::_Ref_count_base::_Decref(v97);
  return (unsigned int)v61;
}

```

## disassembly

```asm
0x18003b9b4  mov     [rsp-8+arg_8], rdx
0x18003b9b9  push    rbp
0x18003b9ba  push    rbx
0x18003b9bb  push    rsi
0x18003b9bc  push    rdi
0x18003b9bd  push    r12
0x18003b9bf  push    r13
0x18003b9c1  push    r14
0x18003b9c3  push    r15
0x18003b9c5  lea     rbp, [rsp-0D8h]
0x18003b9cd  sub     rsp, 1D8h
0x18003b9d4  mov     rax, cs:__security_cookie
0x18003b9db  xor     rax, rsp
0x18003b9de  mov     [rbp+110h+var_50], rax
0x18003b9e5  mov     r13, r9
0x18003b9e8  mov     r14, r8
0x18003b9eb  mov     rsi, rdx
0x18003b9ee  mov     r12, rcx
0x18003b9f1  mov     [rsp+210h+var_1B0], rdx
0x18003b9f6  xor     r15d, r15d
0x18003b9f9  mov     [rsp+210h+var_1C0], 1
0x18003ba01  test    r8, r8
0x18003ba04  jz      short loc_18003BA09
0x18003ba06  mov     [r8], r15
0x18003ba09  lea     rcx, [rsp+210h+var_1C0]; enum _DSREG_TARGET_ENVIRONMENT *
0x18003ba0e  call    ?GetTargetEnvironment@@YAJPEAW4_DSREG_TARGET_ENVIRONMENT@@@Z; GetTargetEnvironment(_DSREG_TARGET_ENVIRONMENT *)
0x18003ba13  mov     ebx, eax
0x18003ba15  test    eax, eax
0x18003ba17  jns     short loc_18003BA4F
0x18003ba19  mov     rcx, [rsi]; this
0x18003ba1c  call    ?TenantTypeName@TenantInfo@@QEBAPEBGXZ; TenantInfo::TenantTypeName(void)
0x18003ba21  mov     r9, [rcx+0D0h]; unsigned __int16 *
0x18003ba28  mov     r8, rax; unsigned __int16 *
0x18003ba2b  lea     rdx, aGetcomputertok_2; "GetComputerTokenForADRS: Unable to read"...
0x18003ba32  mov     ecx, ebx; int
0x18003ba34  call    ?WriteDsRegCmdAuthFailureEvent@Logger@@SAJJPEBG00@Z; Logger::WriteDsRegCmdAuthFailureEvent(long,ushort const *,ushort const *,ushort const *)
0x18003ba39  nop
0x18003ba3a  mov     rcx, [rsi+8]; this
0x18003ba3e  test    rcx, rcx
0x18003ba41  jz      short loc_18003BA48
0x18003ba43  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003ba48  mov     eax, ebx
0x18003ba4a  jmp     loc_18003C121
0x18003ba4f  lea     rcx, [rbp+110h+Src]
0x18003ba53  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003ba58  nop
0x18003ba59  mov     rcx, [rsi]; this
0x18003ba5c  mov     edx, [rcx+0F0h]
0x18003ba62  test    edx, edx
0x18003ba64  jz      loc_18003BB1B
0x18003ba6a  cmp     edx, 1
0x18003ba6d  jz      short loc_18003BA96
0x18003ba6f  call    ?TenantTypeName@TenantInfo@@QEBAPEBGXZ; TenantInfo::TenantTypeName(void)
0x18003ba74  mov     r9, [rcx+0D0h]; unsigned __int16 *
0x18003ba7b  mov     r8, rax; unsigned __int16 *
0x18003ba7e  lea     rdx, aGetcomputertok_0; "GetComputerTokenForADRS: Invalid DSR_IN"...
0x18003ba85  mov     ebx, 80070057h
0x18003ba8a  mov     ecx, ebx; int
0x18003ba8c  call    ?WriteDsRegCmdAuthFailureEvent@Logger@@SAJJPEBG00@Z; Logger::WriteDsRegCmdAuthFailureEvent(long,ushort const *,ushort const *,ushort const *)
0x18003ba91  jmp     loc_18003BC86
0x18003ba96  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003ba9b  mov     rcx, [rax]
0x18003ba9e  lea     rdi, aGetcomputertok_1; "GetComputerTokenForADRS"
0x18003baa5  lea     rbx, aSGetTokenForEn; "%s: Get token for enterprise DRS\n"
0x18003baac  cmp     [rcx], r15b
0x18003baaf  jz      short loc_18003BAF5
0x18003bab1  mov     rdx, rdi
0x18003bab4  mov     rcx, rbx; Format
0x18003bab7  call    wprintf
0x18003babc  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003bac1  mov     rcx, [rax]
0x18003bac4  cmp     [rcx+0Ch], r15b
0x18003bac8  jz      short loc_18003BAF5
0x18003baca  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003bacf  mov     rdx, [rax]
0x18003bad2  cmp     [rdx+0B8h], r15
0x18003bad9  jz      short loc_18003BAF5
0x18003badb  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003bae0  mov     rcx, [rax]
0x18003bae3  mov     r8, rdi
0x18003bae6  mov     rdx, rbx; Format
0x18003bae9  mov     rcx, [rcx+0B8h]; Stream
0x18003baf0  call    fwprintf_s
0x18003baf5  mov     rdx, rdi
0x18003baf8  mov     rcx, rbx; Format
0x18003bafb  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18003bb00  mov     r8d, 28h ; '('
0x18003bb06  lea     rdx, aHttpsLoginMicr_2; "https://login.microsoftonline.com/commo"...
0x18003bb0d  lea     rcx, [rbp+110h+Src]
0x18003bb11  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18003bb16  jmp     loc_18003BD01
0x18003bb1b  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003bb20  mov     rcx, [rax]
0x18003bb23  lea     rdi, aGetcomputertok_1; "GetComputerTokenForADRS"
0x18003bb2a  lea     rbx, aSGetTokenForAd; "%s: Get token for ADRS\n"
0x18003bb31  cmp     [rcx], r15b
0x18003bb34  jz      short loc_18003BB7A
0x18003bb36  mov     rdx, rdi
0x18003bb39  mov     rcx, rbx; Format
0x18003bb3c  call    wprintf
0x18003bb41  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003bb46  mov     rcx, [rax]
0x18003bb49  cmp     [rcx+0Ch], r15b
0x18003bb4d  jz      short loc_18003BB7A
0x18003bb4f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003bb54  mov     rdx, [rax]
0x18003bb57  cmp     [rdx+0B8h], r15
0x18003bb5e  jz      short loc_18003BB7A
0x18003bb60  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003bb65  mov     rcx, [rax]
0x18003bb68  mov     r8, rdi
0x18003bb6b  mov     rdx, rbx; Format
0x18003bb6e  mov     rcx, [rcx+0B8h]; Stream
0x18003bb75  call    fwprintf_s
0x18003bb7a  mov     rdx, rdi
0x18003bb7d  mov     rcx, rbx; Format
0x18003bb80  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18003bb85  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003bb8a  mov     rcx, [rax]
0x18003bb8d  cmp     [rcx], r15b
0x18003bb90  jz      short loc_18003BBF5
0x18003bb92  mov     rax, [rsi]
0x18003bb95  mov     r8, [rax]
0x18003bb98  mov     r8, [r8+18h]
0x18003bb9c  mov     rdx, rdi
0x18003bb9f  lea     rcx, aSAuthCodeUrlS; "%s: Auth code URL: \"%s\"\n"
0x18003bba6  call    wprintf
0x18003bbab  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003bbb0  mov     rcx, [rax]
0x18003bbb3  cmp     [rcx+0Ch], r15b
0x18003bbb7  jz      short loc_18003BBF5
0x18003bbb9  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003bbbe  mov     rcx, [rax]
0x18003bbc1  cmp     [rcx+0B8h], r15
0x18003bbc8  jz      short loc_18003BBF5
0x18003bbca  mov     rax, [rsi]
0x18003bbcd  mov     rcx, [rax]
0x18003bbd0  mov     rbx, [rcx+18h]
0x18003bbd4  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003bbd9  mov     rcx, [rax]
0x18003bbdc  mov     r9, rbx
0x18003bbdf  mov     r8, rdi
0x18003bbe2  lea     rdx, aSAuthCodeUrlS; "%s: Auth code URL: \"%s\"\n"
0x18003bbe9  mov     rcx, [rcx+0B8h]; Stream
0x18003bbf0  call    fwprintf_s
0x18003bbf5  mov     rax, [rsi]
0x18003bbf8  mov     r8, [rax]
0x18003bbfb  mov     r8, [r8+18h]
0x18003bbff  mov     rdx, rdi
0x18003bc02  lea     rcx, aSAuthCodeUrlS; "%s: Auth code URL: \"%s\"\n"
0x18003bc09  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18003bc0e  lea     rcx, [rbp+110h+var_70]
0x18003bc15  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003bc1a  nop
0x18003bc1b  lea     rcx, [rbp+110h+var_90]
0x18003bc22  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003bc27  nop
0x18003bc28  mov     rax, [rsi]
0x18003bc2b  mov     rcx, [rax]
0x18003bc2e  lea     r8, [rbp+110h+var_90]
0x18003bc35  lea     rdx, [rbp+110h+var_70]
0x18003bc3c  mov     rcx, [rcx+18h]; pwszUrl
0x18003bc40  call    ?GetUrlHostAndPath@TenantInfo@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; TenantInfo::GetUrlHostAndPath(ushort const *,std::wstring &,std::wstring &)
0x18003bc45  mov     ebx, eax
0x18003bc47  test    eax, eax
0x18003bc49  jns     short loc_18003BC94
0x18003bc4b  mov     rcx, [rsi]; this
0x18003bc4e  call    ?TenantTypeName@TenantInfo@@QEBAPEBGXZ; TenantInfo::TenantTypeName(void)
0x18003bc53  mov     r9, [rcx+0D0h]; unsigned __int16 *
0x18003bc5a  mov     r8, rax; unsigned __int16 *
0x18003bc5d  lea     rdx, aGetcomputertok; "GetComputerTokenForADRS: Unable to pars"...
0x18003bc64  mov     ecx, ebx; int
0x18003bc66  call    ?WriteDsRegCmdAuthFailureEvent@Logger@@SAJJPEBG00@Z; Logger::WriteDsRegCmdAuthFailureEvent(long,ushort const *,ushort const *,ushort const *)
0x18003bc6b  nop
0x18003bc6c  lea     rcx, [rbp+110h+var_90]
0x18003bc73  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003bc78  nop
0x18003bc79  lea     rcx, [rbp+110h+var_70]
0x18003bc80  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003bc85  nop
0x18003bc86  lea     rcx, [rbp+110h+Src]
0x18003bc8a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003bc8f  jmp     loc_18003BA3A
0x18003bc94  mov     r8d, 8
0x18003bc9a  lea     rdx, aHttps; "https://"
0x18003bca1  lea     rcx, [rbp+110h+Src]
0x18003bca5  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18003bcaa  lea     rdx, [rbp+110h+var_70]
0x18003bcb1  cmp     [rbp+110h+var_58], 7
0x18003bcb9  cmova   rdx, [rbp+110h+var_70]
0x18003bcc1  mov     r8, [rbp+110h+var_60]
0x18003bcc8  lea     rcx, [rbp+110h+Src]; Src
0x18003bccc  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003bcd1  mov     r8d, 7
0x18003bcd7  lea     rdx, aCommon; "/common"
0x18003bcde  lea     rcx, [rbp+110h+Src]; Src
0x18003bce2  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003bce7  nop
0x18003bce8  lea     rcx, [rbp+110h+var_90]
0x18003bcef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003bcf4  nop
0x18003bcf5  lea     rcx, [rbp+110h+var_70]
0x18003bcfc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003bd01  mov     [rsp+210h+Block], r15
0x18003bd06  mov     rdx, [rsi]
0x18003bd09  mov     eax, [rdx+0F0h]
0x18003bd0f  neg     eax
0x18003bd11  sbb     rcx, rcx
0x18003bd14  and     ecx, 18h
0x18003bd17  mov     r15, [rcx+rdx+0D0h]
0x18003bd1f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003bd24  mov     rcx, [rax]
0x18003bd27  xor     ebx, ebx
0x18003bd29  cmp     [rcx], bl
0x18003bd2b  jz      short loc_18003BD97
0x18003bd2d  lea     r8, [rbp+110h+Src]
0x18003bd31  cmp     [rbp+110h+var_98], 7
0x18003bd36  cmova   r8, [rbp+110h+Src]
0x18003bd3b  mov     rdx, rdi
0x18003bd3e  lea     rcx, aSTokenRequestA; "%s: Token request authority: \"%s\"\n"
0x18003bd45  call    wprintf
0x18003bd4a  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003bd4f  mov     rcx, [rax]
0x18003bd52  cmp     [rcx+0Ch], bl
0x18003bd55  jz      short loc_18003BD97
0x18003bd57  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003bd5c  mov     rcx, [rax]
0x18003bd5f  cmp     [rcx+0B8h], rbx
0x18003bd66  jz      short loc_18003BD97
0x18003bd68  lea     rbx, [rbp+110h+Src]
0x18003bd6c  cmp     [rbp+110h+var_98], 7
0x18003bd71  cmova   rbx, [rbp+110h+Src]
0x18003bd76  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003bd7b  mov     rcx, [rax]
0x18003bd7e  mov     r9, rbx
0x18003bd81  mov     r8, rdi
0x18003bd84  lea     rdx, aSTokenRequestA; "%s: Token request authority: \"%s\"\n"
0x18003bd8b  mov     rcx, [rcx+0B8h]; Stream
0x18003bd92  call    fwprintf_s
0x18003bd97  lea     r8, [rbp+110h+Src]
0x18003bd9b  cmp     [rbp+110h+var_98], 7
0x18003bda0  cmova   r8, [rbp+110h+Src]
0x18003bda5  mov     rdx, rdi
0x18003bda8  lea     rcx, aSTokenRequestA; "%s: Token request authority: \"%s\"\n"
0x18003bdaf  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18003bdb4  mov     rax, [rsi]
0x18003bdb7  mov     ebx, [rax+0F0h]
0x18003bdbd  cmp     [rsp+210h+var_1C0], 2
0x18003bdc2  jz      short loc_18003BDD9
0x18003bdc4  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003bdc9  mov     rcx, [rax]
0x18003bdcc  cmp     byte ptr [rcx+2], 0
0x18003bdd0  lea     r9, cchOriginalDestLength
0x18003bdd7  jz      short loc_18003BDE0
0x18003bdd9  lea     r9, aSliceTestslice; "slice=testslice"
0x18003bde0  mov     rax, [rsi]
0x18003bde3  mov     rcx, [rax]
0x18003bde6  lea     rax, [rbp+110h+Src]
0x18003bdea  cmp     [rbp+110h+var_98], 7
0x18003bdef  cmova   rax, [rbp+110h+Src]
0x18003bdf4  lea     rdx, [rsp+210h+Block]
0x18003bdf9  mov     [rsp+210h+var_1D0], rdx
0x18003bdfe  lea     rdx, ?GetTokenLogCallback@@YAXKPEBG@Z; GetTokenLogCallback(ulong,ushort const *)
0x18003be05  mov     [rsp+210h+var_1D8], rdx
0x18003be0a  mov     [rsp+210h+var_1E0], r13
0x18003be0f  mov     [rsp+210h+var_1E8], r15
0x18003be14  mov     [rsp+210h+var_1F0], ebx
0x18003be18  mov     r8, [rcx+38h]
0x18003be1c  lea     rdx, aDd762716544d4a; "dd762716-544d-4aeb-a526-687b73838a22"
0x18003be23  mov     rcx, rax
0x18003be26  mov     rax, r12
0x18003be29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be2e  mov     r15d, eax
0x18003be31  xor     r12d, r12d
0x18003be34  test    eax, eax
0x18003be36  js      short loc_18003BEB3
0x18003be38  mov     rcx, [rsp+210h+Block]; unsigned __int16 *
0x18003be3d  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18003be42  test    eax, eax
0x18003be44  jz      loc_18003C144
0x18003be4a  mov     r15d, 801C0515h
0x18003be50  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003be55  mov     rcx, [rax]
0x18003be58  lea     rbx, aSTokenIsEmpty; "%s: Token is empty.\n"
0x18003be5f  cmp     [rcx], r12b
0x18003be62  jz      short loc_18003BEA8
0x18003be64  mov     rdx, rdi
0x18003be67  mov     rcx, rbx; Format
0x18003be6a  call    wprintf
0x18003be6f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003be74  mov     rcx, [rax]
0x18003be77  cmp     [rcx+0Ch], r12b
0x18003be7b  jz      short loc_18003BEA8
0x18003be7d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003be82  mov     rdx, [rax]
0x18003be85  cmp     [rdx+0B8h], r12
0x18003be8c  jz      short loc_18003BEA8
0x18003be8e  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003be93  mov     rcx, [rax]
0x18003be96  mov     r8, rdi
  ... truncated ...
```
