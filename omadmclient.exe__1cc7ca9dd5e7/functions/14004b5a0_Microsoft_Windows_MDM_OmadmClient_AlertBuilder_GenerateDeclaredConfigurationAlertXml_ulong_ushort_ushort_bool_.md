# Microsoft::Windows::MDM::OmadmClient::AlertBuilder::GenerateDeclaredConfigurationAlertXml(ulong,ushort *,ushort *,bool *,ushort * *)

- ea: `0x14004b5a0`
- end: `0x14004b7d1`
- name: `?GenerateDeclaredConfigurationAlertXml@AlertBuilder@OmadmClient@MDM@Windows@Microsoft@@UEAAJKPEAG0PEA_NPEAPEAG@Z`
- size: `561`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::AlertBuilder *__hidden this, unsigned int, unsigned __int16 *, unsigned __int16 *, bool *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14000b0f4`
- `0x14000bf50`
- `0x14000e610`
- `0x140010f18`
- `0x140013404`
- `0x14004b5a0`
- `0x14004c098`
- `0x140056b74`
- `0x14005707c`
- `0x140058a5c`
- `0x140064af8`
- `0x14006572c`
- `0x140065a6c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004b733`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004b77a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004b792`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004b7a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004b733`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004b77a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004b792`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004b7a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14004b6ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14004b6ff`

## string_xrefs

- `0x14004b750`: `<Alert><CmdID>%d</CmdID><Data>1224</Data><Item><Meta><Type xmlns="syncml:metinf">com.microsoft.mdm.declaredconfigurationdocuments</Type></Meta><Data>%s</Data></Item></Alert>`
- `0x14004b5ce`: `GenerateDeclaredConfigurationAlertXml`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::AlertBuilder::GenerateDeclaredConfigurationAlertXml(
        Microsoft::Windows::MDM::OmadmClient::AlertBuilder *this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        bool *a5,
        unsigned __int16 **a6)
{
  int DeclaredConfigurationAlertImpl; // ebx
  unsigned __int16 **v10; // rsi
  CDeclaredConfigurationLogger *Logger; // rax
  HLOCAL v12; // rcx
  unsigned int v13; // r8d
  __int64 v14; // rax
  unsigned __int64 v15; // rbx
  unsigned __int16 *v16; // rdi
  __int64 v17; // r9
  __int64 v18; // rdx
  int v19; // eax
  int *v21; // [rsp+20h] [rbp-59h]
  int v22; // [rsp+40h] [rbp-39h] BYREF
  __int16 v23; // [rsp+44h] [rbp-35h]
  HLOCAL hMem; // [rsp+48h] [rbp-31h] BYREF
  HLOCAL v25; // [rsp+50h] [rbp-29h]
  __int64 v26; // [rsp+58h] [rbp-21h] BYREF
  _QWORD v27[3]; // [rsp+60h] [rbp-19h] BYREF
  int v28; // [rsp+78h] [rbp-1h]
  int *v29; // [rsp+80h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]
  int v31; // [rsp+E0h] [rbp+67h] BYREF

  v31 = 0;
  v27[0] = 0;
  v27[1] = "GenerateDeclaredConfigurationAlertXml";
  v27[2] = COmaDmLogger::GetLogger();
  v28 = 2;
  v29 = &v31;
  if ( !a3 )
  {
    DeclaredConfigurationAlertImpl = -805306128;
LABEL_5:
    v31 = DeclaredConfigurationAlertImpl;
    goto LABEL_26;
  }
  v10 = a6;
  if ( !a6 )
  {
    DeclaredConfigurationAlertImpl = -805306126;
    goto LABEL_5;
  }
  *a6 = 0;
  if ( !(unsigned int)DCCheckScheduleTaskExist("GenerateDeclaredConfigurationAlertXml", a3)
    && (int)CheckExistingWindcDcos(a3) >= 0 )
  {
    Logger = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogDeclaredConfigurationTaskMissing(Logger, a3);
    DeclaredConfigurationStore_ScheduleDeclaredConfigurationRefresh(a3);
  }
  v25 = 0;
  hMem = 0;
  DeclaredConfigurationAlertImpl = DeclaredConfigurationStore_GetDeclaredConfigurationAlertImpl(
                                     a3,
                                     a4,
                                     a5,
                                     (const unsigned __int16 **)&hMem);
  v31 = DeclaredConfigurationAlertImpl;
  if ( DeclaredConfigurationAlertImpl >= 0 )
  {
    v12 = hMem;
    if ( !hMem )
      goto LABEL_22;
    v13 = *(_DWORD *)Feature_MDM_Fix_WinDC_Alert_Size__descriptor;
    if ( (*(_DWORD *)Feature_MDM_Fix_WinDC_Alert_Size__descriptor & 4) == 0 )
    {
      v26 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MDM_Fix_WinDC_Alert_Size>::GetCachedFeatureEnabledState(
                         hMem,
                         &v26);
      v13 = v26;
    }
    v22 = 0;
    v23 = 3;
    v21 = &v22;
    wil::details::ReportUsageToService(&qword_140085278, 42280597, (v13 >> 10) & 1, (v13 >> 11) & 1);
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)hMem + v14) );
    v15 = v14 + 183;
    v16 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v14 + 183));
    if ( v16 )
    {
      LODWORD(v21) = (_DWORD)hMem;
      v19 = StringCchPrintfW(
              v16,
              v15,
              L"<Alert><CmdID>%d</CmdID><Data>1224</Data><Item><Meta><Type xmlns=\"syncml:metinf\">com.microsoft.mdm.decla"
               "redconfigurationdocuments</Type></Meta><Data>%s</Data></Item></Alert>",
              a2);
      DeclaredConfigurationAlertImpl = v19;
      v31 = v19;
      if ( v19 >= 0 )
      {
        *v10 = v16;
        LocalFree(0);
        DeclaredConfigurationAlertImpl = v31;
        v12 = hMem;
        goto LABEL_22;
      }
      v17 = (unsigned int)v19;
      v18 = 271;
    }
    else
    {
      DeclaredConfigurationAlertImpl = -2147024882;
      v17 = 2147942414LL;
      v18 = 268;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
      (const char *)v17,
      (int)v21);
    LocalFree(v16);
  }
  v12 = hMem;
LABEL_22:
  if ( v12 )
    LocalFree(v12);
  if ( v25 )
    LocalFree(v25);
LABEL_26:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v27);
  return (unsigned int)DeclaredConfigurationAlertImpl;
}

```

## disassembly

```asm
0x14004b5a0  push    rbp
0x14004b5a2  push    rbx
0x14004b5a3  push    rsi
0x14004b5a4  push    rdi
0x14004b5a5  push    r14
0x14004b5a7  push    r15
0x14004b5a9  lea     rbp, [rsp-1Fh]
0x14004b5ae  sub     rsp, 98h
0x14004b5b5  mov     rdi, r9
0x14004b5b8  mov     rbx, r8
0x14004b5bb  mov     r14d, edx
0x14004b5be  xor     r15d, r15d
0x14004b5c1  mov     [rbp+47h+arg_10], r15d
0x14004b5c5  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14004b5ca  mov     [rbp+47h+var_60], r15
0x14004b5ce  lea     rcx, aGeneratedeclar; "GenerateDeclaredConfigurationAlertXml"
0x14004b5d5  mov     [rbp+47h+var_58], rcx
0x14004b5d9  mov     [rbp+47h+var_50], rax
0x14004b5dd  mov     [rbp+47h+var_48], 2
0x14004b5e4  lea     rax, [rbp+47h+arg_10]
0x14004b5e8  mov     [rbp+47h+var_40], rax
0x14004b5ec  test    rbx, rbx
0x14004b5ef  jnz     short loc_14004B5F8
0x14004b5f1  mov     ebx, 0D00000F0h
0x14004b5f6  jmp     short loc_14004B606
0x14004b5f8  mov     rsi, [rbp+47h+arg_28]
0x14004b5fc  test    rsi, rsi
0x14004b5ff  jnz     short loc_14004B60E
0x14004b601  mov     ebx, 0D00000F2h
0x14004b606  mov     [rbp+47h+arg_10], ebx
0x14004b609  jmp     loc_14004B7B5
0x14004b60e  mov     [rsi], r15
0x14004b611  mov     rdx, rbx; unsigned __int16 *
0x14004b614  call    ?DCCheckScheduleTaskExist@@YAHPEBG0@Z; DCCheckScheduleTaskExist(ushort const *,ushort const *)
0x14004b619  test    eax, eax
0x14004b61b  jnz     short loc_14004B641
0x14004b61d  mov     rcx, rbx; unsigned __int16 *
0x14004b620  call    ?CheckExistingWindcDcos@@YAJPEBG@Z; CheckExistingWindcDcos(ushort const *)
0x14004b625  test    eax, eax
0x14004b627  js      short loc_14004B641
0x14004b629  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x14004b62e  mov     rdx, rbx; unsigned __int16 *
0x14004b631  mov     rcx, rax; this
0x14004b634  call    ?LogDeclaredConfigurationTaskMissing@CDeclaredConfigurationLogger@@QEAAXPEBG@Z; CDeclaredConfigurationLogger::LogDeclaredConfigurationTaskMissing(ushort const *)
0x14004b639  mov     rcx, rbx; unsigned __int16 *
0x14004b63c  call    ?DeclaredConfigurationStore_ScheduleDeclaredConfigurationRefresh@@YAJPEBG@Z; DeclaredConfigurationStore_ScheduleDeclaredConfigurationRefresh(ushort const *)
0x14004b641  mov     [rbp+47h+var_70], r15
0x14004b645  mov     [rbp+47h+hMem], r15
0x14004b649  lea     r9, [rbp+47h+hMem]; unsigned __int16 **
0x14004b64d  mov     r8, [rbp+47h+arg_20]; bool *
0x14004b651  mov     rdx, rdi; unsigned __int16 *
0x14004b654  mov     rcx, rbx; unsigned __int16 *
0x14004b657  call    ?DeclaredConfigurationStore_GetDeclaredConfigurationAlertImpl@@YAJPEAG0PEA_NPEAPEAG@Z; DeclaredConfigurationStore_GetDeclaredConfigurationAlertImpl(ushort *,ushort *,bool *,ushort * *)
0x14004b65c  mov     ebx, eax
0x14004b65e  mov     [rbp+47h+arg_10], eax
0x14004b661  test    eax, eax
0x14004b663  jns     short loc_14004B66E
0x14004b665  mov     rcx, [rbp+47h+hMem]
0x14004b669  jmp     loc_14004B78D
0x14004b66e  mov     rcx, [rbp+47h+hMem]
0x14004b672  test    rcx, rcx
0x14004b675  jz      loc_14004B78D
0x14004b67b  mov     rax, cs:Feature_MDM_Fix_WinDC_Alert_Size__descriptor
0x14004b682  mov     r8d, [rax]
0x14004b685  test    r8b, 4
0x14004b689  jnz     short loc_14004B69E
0x14004b68b  lea     rdx, [rbp+47h+var_68]
0x14004b68f  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MDM_Fix_WinDC_Alert_Size@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MDM_Fix_WinDC_Alert_Size>::GetCachedFeatureEnabledState(void)
0x14004b694  mov     rcx, [rax]
0x14004b697  mov     [rbp+47h+var_68], rcx
0x14004b69b  mov     r8d, ecx
0x14004b69e  mov     [rbp+47h+var_80], r15d
0x14004b6a2  mov     [rbp+47h+var_7C], 3
0x14004b6a8  mov     r9d, r8d
0x14004b6ab  shr     r9d, 0Bh
0x14004b6af  and     r9d, 1
0x14004b6b3  shr     r8d, 0Ah
0x14004b6b7  and     r8d, 1
0x14004b6bb  mov     [rsp+0C0h+var_98], 1
0x14004b6c3  lea     rax, [rbp+47h+var_80]
0x14004b6c7  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x14004b6cc  mov     edx, 2852695h
0x14004b6d1  lea     rcx, qword_140085278
0x14004b6d8  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x14004b6dd  mov     rcx, [rbp+47h+hMem]
0x14004b6e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004b6e5  inc     rax
0x14004b6e8  cmp     [rcx+rax*2], r15w
0x14004b6ed  jnz     short loc_14004B6E5
0x14004b6ef  lea     rbx, [rax+0B7h]
0x14004b6f6  lea     rdx, [rbx+rbx]; uBytes
0x14004b6fa  mov     ecx, 40h ; '@'; uFlags
0x14004b6ff  call    cs:__imp_LocalAlloc
0x14004b706  nop     dword ptr [rax+rax+00h]
0x14004b70b  mov     rdi, rax
0x14004b70e  test    rax, rax
0x14004b711  jnz     short loc_14004B744
0x14004b713  mov     ebx, 8007000Eh
0x14004b718  mov     r9d, ebx; char *
0x14004b71b  mov     edx, 10Ch; void *
0x14004b720  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14004b727  mov     rcx, [rbp+4Fh]; this
0x14004b72b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004b730  mov     rcx, rdi; hMem
0x14004b733  call    cs:__imp_LocalFree
0x14004b73a  nop     dword ptr [rax+rax+00h]
0x14004b73f  jmp     loc_14004B665
0x14004b744  mov     rax, [rbp+47h+hMem]
0x14004b748  mov     qword ptr [rsp+0C0h+var_A0], rax
0x14004b74d  mov     r9d, r14d
0x14004b750  lea     r8, ?gc_szDeclaredConfigurationAlertTemplateUpdate@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "<Alert><CmdID>%d</CmdID><Data>1224</Dat"...
0x14004b757  mov     rdx, rbx; unsigned __int64
0x14004b75a  mov     rcx, rdi; unsigned __int16 *
0x14004b75d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14004b762  mov     ebx, eax
0x14004b764  mov     [rbp+47h+arg_10], eax
0x14004b767  test    eax, eax
0x14004b769  jns     short loc_14004B775
0x14004b76b  mov     r9d, eax
0x14004b76e  mov     edx, 10Fh
0x14004b773  jmp     short loc_14004B720
0x14004b775  mov     [rsi], rdi
0x14004b778  xor     ecx, ecx; hMem
0x14004b77a  call    cs:__imp_LocalFree
0x14004b781  nop     dword ptr [rax+rax+00h]
0x14004b786  mov     ebx, [rbp+47h+arg_10]
0x14004b789  mov     rcx, [rbp+47h+hMem]; hMem
0x14004b78d  test    rcx, rcx
0x14004b790  jz      short loc_14004B79F
0x14004b792  call    cs:__imp_LocalFree
0x14004b799  nop     dword ptr [rax+rax+00h]
0x14004b79e  nop
0x14004b79f  mov     rcx, [rbp+47h+var_70]; hMem
0x14004b7a3  test    rcx, rcx
0x14004b7a6  jz      short loc_14004B7B5
0x14004b7a8  call    cs:__imp_LocalFree
0x14004b7af  nop     dword ptr [rax+rax+00h]
0x14004b7b4  nop
0x14004b7b5  lea     rcx, [rbp+47h+var_60]; this
0x14004b7b9  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004b7be  mov     eax, ebx
0x14004b7c0  add     rsp, 98h
0x14004b7c7  pop     r15
0x14004b7c9  pop     r14
0x14004b7cb  pop     rdi
0x14004b7cc  pop     rsi
0x14004b7cd  pop     rbx
0x14004b7ce  pop     rbp
0x14004b7cf  retn
```
