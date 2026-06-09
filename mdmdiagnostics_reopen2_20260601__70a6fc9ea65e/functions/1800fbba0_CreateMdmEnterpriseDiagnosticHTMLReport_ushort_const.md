# CreateMdmEnterpriseDiagnosticHTMLReport(ushort const *)

- ea: `0x1800fbba0`
- end: `0x1800fbe2b`
- name: `?CreateMdmEnterpriseDiagnosticHTMLReport@@YAJPEBG@Z`
- size: `651`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800fabb4`

## callees

- `0x1800e6b14`
- `0x1800ed44c`
- `0x1800ed46c`
- `0x1800eef08`
- `0x1800eef28`
- `0x1800fa314`
- `0x1800fa50c`
- `0x1800fbba0`
- `0x1801055f4`
- `0x180105744`
- `0x180127a74`
- `0x180127eb8`
- `0x180127f24`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800fbc0d`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800fbc0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fbc6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fbc6b`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800fbcce`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800fbcce`
- `DMCmnUtils!DmCreateFileSafe` at `0x1800fbc4f`
- `DMCmnUtils!DmCreateFileSafe` at `0x1800fbc4f`

## string_xrefs

- `0x1800fbd7b`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\dllmain.cpp`
- `0x1800fbde3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\dllmain.cpp`

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
0x1800fbba0  mov     rax, rsp
0x1800fbba3  mov     [rax+8], rbx
0x1800fbba7  push    rdi
0x1800fbba8  sub     rsp, 80h
0x1800fbbaf  mov     rdi, rcx
0x1800fbbb2  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x1800fbbba  call    ?EnsureDirectoriesArePresent@@YAJPEBG@Z; EnsureDirectoriesArePresent(ushort const *)
0x1800fbbbf  mov     ebx, eax
0x1800fbbc1  test    eax, eax
0x1800fbbc3  jns     short loc_1800FBBF5
0x1800fbbc5  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x1800fbbcc  jz      short loc_1800FBBE1
0x1800fbbce  mov     r9d, eax
0x1800fbbd1  mov     r8, rdi
0x1800fbbd4  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsCreatingOrCheckingDirectoryFailure
0x1800fbbdb  call    McTemplateU0zd_EventWriteTransfer
0x1800fbbe0  nop
0x1800fbbe1  lea     rcx, [rsp+88h+arg_10]
0x1800fbbe9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800fbbee  mov     eax, ebx
0x1800fbbf0  jmp     loc_1800FBE19
0x1800fbbf5  mov     [rsp+88h+arg_8], 0
0x1800fbc00  xor     r8d, r8d
0x1800fbc03  lea     rdx, [rsp+88h+arg_8]
0x1800fbc0b  xor     ecx, ecx
0x1800fbc0d  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800fbc14  nop     dword ptr [rax+rax+00h]
0x1800fbc19  cmp     [rsp+88h+arg_8], 0Ah
0x1800fbc21  jz      loc_1800FBCB3
0x1800fbc27  mov     [rsp+88h+var_58], 0
0x1800fbc30  mov     [rsp+88h+var_60], 80h
0x1800fbc38  mov     [rsp+88h+var_68], 4
0x1800fbc40  xor     r9d, r9d
0x1800fbc43  mov     edx, 80000000h
0x1800fbc48  lea     r8d, [r9+3]
0x1800fbc4c  mov     rcx, rdi
0x1800fbc4f  call    cs:__imp_?DmCreateFileSafe@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; DmCreateFileSafe(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x1800fbc56  nop     dword ptr [rax+rax+00h]
0x1800fbc5b  mov     rdx, rax
0x1800fbc5e  lea     rcx, [rsp+88h+arg_10]
0x1800fbc66  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800fbc6b  call    cs:__imp_GetLastError
0x1800fbc72  nop     dword ptr [rax+rax+00h]
0x1800fbc77  mov     ebx, eax
0x1800fbc79  test    eax, eax
0x1800fbc7b  jle     short loc_1800FBC86
0x1800fbc7d  movzx   ebx, ax
0x1800fbc80  or      ebx, 80070000h
0x1800fbc86  cmp     [rsp+88h+arg_10], 0FFFFFFFFFFFFFFFFh
0x1800fbc8f  jnz     short loc_1800FBCB3
0x1800fbc91  lea     rcx, [rsp+88h+arg_10]
0x1800fbc99  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800fbc9e  test    ebx, ebx
0x1800fbca0  jns     short loc_1800FBCA9
0x1800fbca2  mov     eax, ebx
0x1800fbca4  jmp     loc_1800FBE19
0x1800fbca9  mov     eax, 80070057h
0x1800fbcae  jmp     loc_1800FBE19
0x1800fbcb3  mov     qword ptr [rsp+88h+var_68], 0; int
0x1800fbcbc  mov     edx, 0C0000000h
0x1800fbcc1  mov     r9d, 2
0x1800fbcc7  lea     r8d, [r9-1]
0x1800fbccb  mov     rcx, rdi
0x1800fbcce  call    cs:__imp_CreateFile2
0x1800fbcd5  nop     dword ptr [rax+rax+00h]
0x1800fbcda  mov     rdx, rax
0x1800fbcdd  lea     rcx, [rsp+88h+var_38]
0x1800fbce2  call    ??0?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@PEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void *)
0x1800fbce7  nop
0x1800fbce8  mov     rax, [rsp+88h+var_38]
0x1800fbced  test    rax, rax
0x1800fbcf0  jz      loc_1800FBDDB
0x1800fbcf6  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1800fbcfa  jz      loc_1800FBDDB
0x1800fbd00  lea     rdx, [rsp+88h+var_38]
0x1800fbd05  lea     rcx, [rsp+88h+var_28]
0x1800fbd0a  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x1800fbd0f  xorps   xmm0, xmm0
0x1800fbd12  movups  [rsp+88h+var_48], xmm0
0x1800fbd17  lea     rdx, [rsp+88h+var_28]
0x1800fbd1c  lea     rcx, [rsp+88h+var_18]
0x1800fbd21  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x1800fbd26  mov     rcx, [rax]
0x1800fbd29  mov     qword ptr [rax], 0
0x1800fbd30  mov     qword ptr [rsp+88h+var_48], rcx
0x1800fbd35  mov     rcx, [rax+8]
0x1800fbd39  mov     qword ptr [rax+8], 0
0x1800fbd41  mov     qword ptr [rsp+88h+var_48+8], rcx
0x1800fbd46  mov     rcx, [rsp+88h+var_10]; this
0x1800fbd4b  test    rcx, rcx
0x1800fbd4e  jz      short loc_1800FBD55
0x1800fbd50  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800fbd55  lea     rcx, [rsp+88h+var_28]
0x1800fbd5a  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x1800fbd5f  nop
0x1800fbd60  lea     rcx, [rsp+88h+var_48]; this
0x1800fbd65  call    ?Run@HTMLReport@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::HTMLReport::Run(void)
0x1800fbd6a  mov     ebx, eax
0x1800fbd6c  test    eax, eax
0x1800fbd6e  jns     short loc_1800FBDB4
0x1800fbd70  mov     rcx, [rsp+88h]; this
0x1800fbd78  mov     r9d, eax; char *
0x1800fbd7b  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800fbd82  mov     edx, 264h; void *
0x1800fbd87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fbd8c  nop
0x1800fbd8d  lea     rcx, [rsp+88h+var_48]; this
0x1800fbd92  call    ??1HTMLReport@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::HTMLReport::~HTMLReport(void)
0x1800fbd97  nop
0x1800fbd98  lea     rcx, [rsp+88h+var_38]
0x1800fbd9d  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x1800fbda2  nop
0x1800fbda3  lea     rcx, [rsp+88h+arg_10]
0x1800fbdab  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800fbdb0  mov     eax, ebx
0x1800fbdb2  jmp     short loc_1800FBE19
0x1800fbdb4  lea     rcx, [rsp+88h+var_48]; this
0x1800fbdb9  call    ??1HTMLReport@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::HTMLReport::~HTMLReport(void)
0x1800fbdbe  nop
0x1800fbdbf  lea     rcx, [rsp+88h+var_38]
0x1800fbdc4  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x1800fbdc9  nop
0x1800fbdca  lea     rcx, [rsp+88h+arg_10]
0x1800fbdd2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800fbdd7  xor     eax, eax
0x1800fbdd9  jmp     short loc_1800FBE19
0x1800fbddb  mov     rcx, [rsp+88h]; this
0x1800fbde3  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800fbdea  mov     edx, 25Fh; void *
0x1800fbdef  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800fbdf4  mov     ebx, eax
0x1800fbdf6  lea     rcx, [rsp+88h+var_38]
0x1800fbdfb  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x1800fbe00  nop
0x1800fbe01  lea     rcx, [rsp+88h+arg_10]
0x1800fbe09  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800fbe0e  mov     eax, ebx
0x1800fbe10  jmp     short loc_1800FBE19
0x1800fbe12  mov     eax, [rsp+88h+arg_8]
0x1800fbe19  mov     rbx, [rsp+88h+arg_0]
0x1800fbe21  add     rsp, 80h
0x1800fbe28  pop     rdi
0x1800fbe29  retn
```
