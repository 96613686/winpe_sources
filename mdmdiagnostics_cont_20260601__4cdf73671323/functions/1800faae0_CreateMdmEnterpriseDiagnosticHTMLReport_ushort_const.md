# CreateMdmEnterpriseDiagnosticHTMLReport(ushort const *)

- ea: `0x1800faae0`
- end: `0x1800fad53`
- name: `?CreateMdmEnterpriseDiagnosticHTMLReport@@YAJPEBG@Z`
- size: `627`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f9bb4`

## callees

- `0x1800e691c`
- `0x1800ece3c`
- `0x1800ece5c`
- `0x1800ee878`
- `0x1800ee898`
- `0x1800f934c`
- `0x1800f9534`
- `0x1800faae0`
- `0x1801043d4`
- `0x18010450c`
- `0x18012605c`
- `0x18012647c`
- `0x1801264e8`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800fab4d`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800fab4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fab9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fab9f`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800fabfc`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800fabfc`
- `DMCmnUtils!DmCreateFileSafe` at `0x1800fab89`
- `DMCmnUtils!DmCreateFileSafe` at `0x1800fab89`

## string_xrefs

- `0x1800faca3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\dllmain.cpp`
- `0x1800fad0b`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\dllmain.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreateMdmEnterpriseDiagnosticHTMLReport(const unsigned __int16 *a1)
{
  int v2; // eax
  __int64 v3; // rcx
  unsigned int v4; // ebx
  __int64 result; // rax
  void *FileSafe; // rax
  signed int LastError; // eax
  signed int v8; // ebx
  const char *v9; // r9
  __int64 File2; // rax
  const char *v11; // r9
  __int64 *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  __int128 v18; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v19[2]; // [rsp+50h] [rbp-38h] BYREF
  _BYTE v20[16]; // [rsp+60h] [rbp-28h] BYREF
  _BYTE v21[8]; // [rsp+70h] [rbp-18h] BYREF
  std::_Ref_count_base *v22; // [rsp+78h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  int v24; // [rsp+98h] [rbp+10h] BYREF
  __int64 v25; // [rsp+A0h] [rbp+18h] BYREF

  v25 = -1;
  v2 = EnsureDirectoriesArePresent(a1);
  v4 = v2;
  if ( v2 >= 0 )
  {
    v24 = 0;
    RtlGetDeviceFamilyInfoEnum(0, &v24, 0);
    try
    {
      if ( v24 == 10 )
        goto LABEL_13;
      FileSafe = DmCreateFileSafe(a1, 0x80000000, 3u, 0, 4u, 0x80u, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v25,
        FileSafe);
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v25 != -1 )
      {
LABEL_13:
        File2 = CreateFile2(a1, 3221225472LL, 1);
        wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(
          v19,
          File2);
        if ( !v19[0] || *(_QWORD *)v19[0] == -1 )
        {
          v17 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x25F,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\dllmain.cpp",
                  v11);
          std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(v19);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v25);
          result = v17;
        }
        else
        {
          std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
            v20,
            v19);
          v18 = 0;
          v12 = (__int64 *)std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
                             v21,
                             v20);
          v13 = *v12;
          *v12 = 0;
          *(_QWORD *)&v18 = v13;
          v14 = v12[1];
          v12[1] = 0;
          *((_QWORD *)&v18 + 1) = v14;
          if ( v22 )
            std::_Ref_count_base::_Decref(v22);
          std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(v20);
          v15 = Microsoft::Windows::Mdm::MdmDiagnosticSource::HTMLReport::Run((Microsoft::Windows::Mdm::MdmDiagnosticSource::HTMLReport *)&v18);
          v16 = v15;
          if ( v15 >= 0 )
          {
            Microsoft::Windows::Mdm::MdmDiagnosticSource::HTMLReport::~HTMLReport((Microsoft::Windows::Mdm::MdmDiagnosticSource::HTMLReport *)&v18);
            std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(v19);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v25);
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x264,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\dllmain.cpp",
              (const char *)(unsigned int)v15,
              0);
            Microsoft::Windows::Mdm::MdmDiagnosticSource::HTMLReport::~HTMLReport((Microsoft::Windows::Mdm::MdmDiagnosticSource::HTMLReport *)&v18);
            std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(v19);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v25);
            result = v16;
          }
        }
      }
      else
      {
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v25);
        if ( v8 >= 0 )
          result = 2147942487LL;
        else
          result = (unsigned int)v8;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x267,
                             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\dllmain.cpp",
                             v9);
    }
  }
  else
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
      McTemplateU0zd_EventWriteTransfer(
        v3,
        EnterpriseDiagnosticsMdmDiagnosticsCreatingOrCheckingDirectoryFailure,
        a1,
        (unsigned int)v2);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v25);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800faae0  mov     rax, rsp
0x1800faae3  mov     [rax+8], rbx
0x1800faae7  push    rdi
0x1800faae8  sub     rsp, 80h
0x1800faaef  mov     rdi, rcx
0x1800faaf2  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x1800faafa  call    ?EnsureDirectoriesArePresent@@YAJPEBG@Z; EnsureDirectoriesArePresent(ushort const *)
0x1800faaff  mov     ebx, eax
0x1800fab01  test    eax, eax
0x1800fab03  jns     short loc_1800FAB35
0x1800fab05  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x1800fab0c  jz      short loc_1800FAB21
0x1800fab0e  mov     r9d, eax
0x1800fab11  mov     r8, rdi
0x1800fab14  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsCreatingOrCheckingDirectoryFailure
0x1800fab1b  call    McTemplateU0zd_EventWriteTransfer
0x1800fab20  nop
0x1800fab21  lea     rcx, [rsp+88h+arg_10]
0x1800fab29  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800fab2e  mov     eax, ebx
0x1800fab30  jmp     loc_1800FAD41
0x1800fab35  mov     [rsp+88h+arg_8], 0
0x1800fab40  xor     r8d, r8d
0x1800fab43  lea     rdx, [rsp+88h+arg_8]
0x1800fab4b  xor     ecx, ecx
0x1800fab4d  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800fab53  cmp     [rsp+88h+arg_8], 0Ah
0x1800fab5b  jz      loc_1800FABE1
0x1800fab61  mov     [rsp+88h+var_58], 0
0x1800fab6a  mov     [rsp+88h+var_60], 80h
0x1800fab72  mov     [rsp+88h+var_68], 4
0x1800fab7a  xor     r9d, r9d
0x1800fab7d  mov     edx, 80000000h
0x1800fab82  lea     r8d, [r9+3]
0x1800fab86  mov     rcx, rdi
0x1800fab89  call    cs:__imp_?DmCreateFileSafe@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; DmCreateFileSafe(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x1800fab8f  mov     rdx, rax
0x1800fab92  lea     rcx, [rsp+88h+arg_10]
0x1800fab9a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800fab9f  call    cs:__imp_GetLastError
0x1800faba5  mov     ebx, eax
0x1800faba7  test    eax, eax
0x1800faba9  jle     short loc_1800FABB4
0x1800fabab  movzx   ebx, ax
0x1800fabae  or      ebx, 80070000h
0x1800fabb4  cmp     [rsp+88h+arg_10], 0FFFFFFFFFFFFFFFFh
0x1800fabbd  jnz     short loc_1800FABE1
0x1800fabbf  lea     rcx, [rsp+88h+arg_10]
0x1800fabc7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800fabcc  test    ebx, ebx
0x1800fabce  jns     short loc_1800FABD7
0x1800fabd0  mov     eax, ebx
0x1800fabd2  jmp     loc_1800FAD41
0x1800fabd7  mov     eax, 80070057h
0x1800fabdc  jmp     loc_1800FAD41
0x1800fabe1  mov     qword ptr [rsp+88h+var_68], 0; int
0x1800fabea  mov     edx, 0C0000000h
0x1800fabef  mov     r9d, 2
0x1800fabf5  lea     r8d, [r9-1]
0x1800fabf9  mov     rcx, rdi
0x1800fabfc  call    cs:__imp_CreateFile2
0x1800fac02  mov     rdx, rax
0x1800fac05  lea     rcx, [rsp+88h+var_38]
0x1800fac0a  call    ??0?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@PEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void *)
0x1800fac0f  nop
0x1800fac10  mov     rax, [rsp+88h+var_38]
0x1800fac15  test    rax, rax
0x1800fac18  jz      loc_1800FAD03
0x1800fac1e  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1800fac22  jz      loc_1800FAD03
0x1800fac28  lea     rdx, [rsp+88h+var_38]
0x1800fac2d  lea     rcx, [rsp+88h+var_28]
0x1800fac32  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x1800fac37  xorps   xmm0, xmm0
0x1800fac3a  movups  [rsp+88h+var_48], xmm0
0x1800fac3f  lea     rdx, [rsp+88h+var_28]
0x1800fac44  lea     rcx, [rsp+88h+var_18]
0x1800fac49  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x1800fac4e  mov     rcx, [rax]
0x1800fac51  mov     qword ptr [rax], 0
0x1800fac58  mov     qword ptr [rsp+88h+var_48], rcx
0x1800fac5d  mov     rcx, [rax+8]
0x1800fac61  mov     qword ptr [rax+8], 0
0x1800fac69  mov     qword ptr [rsp+88h+var_48+8], rcx
0x1800fac6e  mov     rcx, [rsp+88h+var_10]; this
0x1800fac73  test    rcx, rcx
0x1800fac76  jz      short loc_1800FAC7D
0x1800fac78  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800fac7d  lea     rcx, [rsp+88h+var_28]
0x1800fac82  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x1800fac87  nop
0x1800fac88  lea     rcx, [rsp+88h+var_48]; this
0x1800fac8d  call    ?Run@HTMLReport@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::HTMLReport::Run(void)
0x1800fac92  mov     ebx, eax
0x1800fac94  test    eax, eax
0x1800fac96  jns     short loc_1800FACDC
0x1800fac98  mov     rcx, [rsp+88h]; this
0x1800faca0  mov     r9d, eax; char *
0x1800faca3  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800facaa  mov     edx, 264h; void *
0x1800facaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800facb4  nop
0x1800facb5  lea     rcx, [rsp+88h+var_48]; this
0x1800facba  call    ??1HTMLReport@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::HTMLReport::~HTMLReport(void)
0x1800facbf  nop
0x1800facc0  lea     rcx, [rsp+88h+var_38]
0x1800facc5  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x1800facca  nop
0x1800faccb  lea     rcx, [rsp+88h+arg_10]
0x1800facd3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800facd8  mov     eax, ebx
0x1800facda  jmp     short loc_1800FAD41
0x1800facdc  lea     rcx, [rsp+88h+var_48]; this
0x1800face1  call    ??1HTMLReport@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::HTMLReport::~HTMLReport(void)
0x1800face6  nop
0x1800face7  lea     rcx, [rsp+88h+var_38]
0x1800facec  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x1800facf1  nop
0x1800facf2  lea     rcx, [rsp+88h+arg_10]
0x1800facfa  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800facff  xor     eax, eax
0x1800fad01  jmp     short loc_1800FAD41
0x1800fad03  mov     rcx, [rsp+88h]; this
0x1800fad0b  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800fad12  mov     edx, 25Fh; void *
0x1800fad17  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800fad1c  mov     ebx, eax
0x1800fad1e  lea     rcx, [rsp+88h+var_38]
0x1800fad23  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x1800fad28  nop
0x1800fad29  lea     rcx, [rsp+88h+arg_10]
0x1800fad31  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800fad36  mov     eax, ebx
0x1800fad38  jmp     short loc_1800FAD41
0x1800fad3a  mov     eax, [rsp+88h+arg_8]
0x1800fad41  mov     rbx, [rsp+88h+arg_0]
0x1800fad49  add     rsp, 80h
0x1800fad50  pop     rdi
0x1800fad51  retn
```
