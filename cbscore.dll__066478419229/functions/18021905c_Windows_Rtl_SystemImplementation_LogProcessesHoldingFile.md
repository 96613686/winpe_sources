# Windows::Rtl::SystemImplementation::LogProcessesHoldingFile

- ea: `0x18021905c`
- end: `0x18021935b`
- name: `Windows::Rtl::SystemImplementation::LogProcessesHoldingFile`
- size: `767`
- prototype: `__int64 __fastcall(POBJECT_ATTRIBUTES ObjectAttributes)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x18021a180`

## callees

- `0x180010cc0`
- `0x180019bdc`
- `0x18002e280`
- `0x18002ec34`
- `0x18004a680`
- `0x1800eb920`
- `0x1800ec920`
- `0x18021078c`
- `0x180210830`
- `0x180211568`
- `0x1802116dc`
- `0x18021905c`

## import_xrefs

- `ntdll!NtOpenProcess` at `0x1802191bd`
- `ntdll!NtOpenProcess` at `0x1802191bd`
- `ntdll!NtQueryInformationFile` at `0x180219108`
- `ntdll!NtQueryInformationFile` at `0x180219108`
- `ntdll!NtOpenFile` at `0x1802190c8`
- `ntdll!NtOpenFile` at `0x1802190c8`
- `ntdll!NtQueryInformationProcess` at `0x18021921d`
- `ntdll!NtQueryInformationProcess` at `0x18021921d`

## string_xrefs

- `0x1802192bf`: `Failed to query image path for process {0} with status {1}.`
- `0x1802191d9`: `Failed to open process {0} with status {1}.`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::SystemImplementation::LogProcessesHoldingFile(
        POBJECT_ATTRIBUTES ObjectAttributes,
        __int64 a2)
{
  void **InitPointer; // rax
  NTSTATUS v4; // ebx
  NTSTATUS v5; // eax
  __int64 v6; // rcx
  __int64 v7; // r8
  PUNICODE_STRING ObjectName; // rdx
  __int64 v9; // rbx
  void **v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  const char *v13; // r8
  NTSTATUS **p_p_InformationProcess; // rax
  const wchar_t *v15; // rax
  int v16; // edi
  __int128 v17; // xmm2
  __int64 v18; // xmm3_8
  NTSTATUS *v20; // [rsp+30h] [rbp-D0h] BYREF
  NTSTATUS *p_InformationProcess; // [rsp+38h] [rbp-C8h] BYREF
  struct _CLIENT_ID ClientId; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributesa; // [rsp+50h] [rbp-B0h] BYREF
  NTSTATUS InformationProcess; // [rsp+80h] [rbp-80h] BYREF
  HANDLE ProcessHandle; // [rsp+88h] [rbp-78h] BYREF
  HANDLE FileHandle; // [rsp+90h] [rbp-70h] BYREF
  __int128 v27; // [rsp+98h] [rbp-68h] BYREF
  __int64 v28; // [rsp+A8h] [rbp-58h]
  __int128 v29; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v30; // [rsp+C0h] [rbp-40h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-38h] BYREF
  _DWORD FileInformation[132]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE ProcessInformation[544]; // [rsp+2F0h] [rbp+1F0h] BYREF

  FileHandle = 0;
  InformationProcess = 0;
  IoStatusBlock = 0;
  InitPointer = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(
                           &FileHandle,
                           a2);
  v4 = NtOpenFile(InitPointer, 0x100080u, ObjectAttributes, &IoStatusBlock, 7u, 0x4020u);
  if ( v4 >= 0 )
  {
    memset_0(FileInformation, 0, 0x208u);
    v5 = NtQueryInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x208u, FileProcessIdsUsingFileInformation);
    if ( v5 < 0 )
    {
      v4 = v5;
      goto LABEL_18;
    }
    ObjectName = ObjectAttributes->ObjectName;
    v28 = 0;
    ProcessHandle = &v27;
    v27 = 0;
    v4 = Windows::StringUtil::Rtl::ConcatenateStrings<wchar_t [19],_UNICODE_STRING,wchar_t [3],Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(
           v6,
           ObjectName,
           v7,
           &ProcessHandle);
    if ( v4 < 0 )
    {
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v27);
      goto LABEL_18;
    }
    v9 = 0;
    if ( !FileInformation[0] )
    {
LABEL_17:
      Windows::WCP::Rtl::RtlAutoTrace<Windows::Auto<_LUNICODE_STRING>>(0, &Windows::WCP::Rtl::Facility_SIL, "{0}", &v27);
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v27);
      v4 = 0;
      goto LABEL_18;
    }
    while ( 1 )
    {
      ClientId.UniqueThread = 0;
      *(_QWORD *)&ObjectAttributesa.Length = 48;
      ClientId.UniqueProcess = *(HANDLE *)&FileInformation[2 * v9 + 2];
      memset(&ObjectAttributesa.RootDirectory, 0, 40);
      ProcessHandle = 0;
      v10 = (void **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&ProcessHandle);
      InformationProcess = NtOpenProcess(v10, 0x1000u, &ObjectAttributesa, &ClientId);
      if ( InformationProcess < 0 )
        break;
      memset_0(ProcessInformation, 0, 0x218u);
      InformationProcess = NtQueryInformationProcess(ProcessHandle, ProcessImageFileName, ProcessInformation, 0x218u, 0);
      if ( InformationProcess < 0 )
      {
        p_InformationProcess = &InformationProcess;
        v13 = "Failed to query image path for process {0} with status {1}.";
        p_p_InformationProcess = &p_InformationProcess;
        goto LABEL_15;
      }
      v30 = 0;
      v20 = (NTSTATUS *)&v29;
      v15 = &qword_1802EB518;
      if ( (_DWORD)v9 )
        v15 = L", ";
      p_InformationProcess = (NTSTATUS *)v15;
      v29 = 0;
      v16 = Windows::StringUtil::Rtl::ConcatenateStrings<Windows::Auto<_LUNICODE_STRING>,wchar_t const *,_UNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(
              &v27,
              &p_InformationProcess,
              ProcessInformation,
              &v20);
      if ( v16 < 0 )
      {
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v29);
        Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ProcessHandle);
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v27);
        v4 = v16;
        goto LABEL_18;
      }
      v17 = v27;
      v18 = v28;
      v27 = v29;
      v29 = v17;
      v28 = v30;
      v30 = v18;
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v29);
LABEL_16:
      Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ProcessHandle);
      v9 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v9 >= FileInformation[0] )
        goto LABEL_17;
    }
    v20 = &InformationProcess;
    v13 = "Failed to open process {0} with status {1}.";
    p_p_InformationProcess = &v20;
LABEL_15:
    Windows::WCP::Rtl::RtlAutoTrace<unsigned __int64,Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
      v12,
      v11,
      v13,
      &FileInformation[2 * v9 + 2],
      p_p_InformationProcess);
    goto LABEL_16;
  }
LABEL_18:
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&FileHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18021905c  mov     [rsp-8+arg_8], rbx
0x180219061  mov     [rsp-8+arg_10], rdi
0x180219066  push    rbp
0x180219067  lea     rbp, [rsp-420h]
0x18021906f  sub     rsp, 520h
0x180219076  mov     rax, cs:__security_cookie
0x18021907d  xor     rax, rsp
0x180219080  mov     [rbp+420h+var_10], rax
0x180219087  mov     rdi, rcx
0x18021908a  mov     [rbp+420h+FileHandle], 0
0x180219092  xorps   xmm0, xmm0
0x180219095  mov     [rbp+420h+var_4A0], 0
0x18021909c  lea     rcx, [rbp+420h+FileHandle]
0x1802190a0  movups  xmmword ptr [rbp+420h+IoStatusBlock], xmm0
0x1802190a4  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x1802190a9  mov     rcx, rax; FileHandle
0x1802190ac  mov     [rsp+520h+OpenOptions], 4020h; OpenOptions
0x1802190b4  lea     r9, [rbp+420h+IoStatusBlock]; IoStatusBlock
0x1802190b8  mov     [rsp+520h+ShareAccess], 7; ShareAccess
0x1802190c0  mov     r8, rdi; ObjectAttributes
0x1802190c3  mov     edx, 100080h; DesiredAccess
0x1802190c8  call    cs:__imp_NtOpenFile
0x1802190cf  nop     dword ptr [rax+rax+00h]
0x1802190d4  mov     ebx, eax
0x1802190d6  test    eax, eax
0x1802190d8  js      loc_180219310
0x1802190de  mov     ebx, 208h
0x1802190e3  lea     rcx, [rbp+420h+FileInformation]; void *
0x1802190e7  mov     r8d, ebx; Size
0x1802190ea  xor     edx, edx; Val
0x1802190ec  call    memset_0
0x1802190f1  mov     rcx, [rbp+420h+FileHandle]; FileHandle
0x1802190f5  lea     r8, [rbp+420h+FileInformation]; FileInformation
0x1802190f9  mov     r9d, ebx; Length
0x1802190fc  mov     [rsp+520h+ShareAccess], 2Fh ; '/'; FileInformationClass
0x180219104  lea     rdx, [rbp+420h+IoStatusBlock]; IoStatusBlock
0x180219108  call    cs:__imp_NtQueryInformationFile
0x18021910f  nop     dword ptr [rax+rax+00h]
0x180219114  test    eax, eax
0x180219116  jns     short loc_18021911F
0x180219118  mov     ebx, eax
0x18021911a  jmp     loc_180219310
0x18021911f  mov     rdx, [rdi+10h]
0x180219123  lea     r9, [rbp+420h+ProcessHandle]
0x180219127  xor     eax, eax
0x180219129  xorps   xmm0, xmm0
0x18021912c  mov     [rbp+420h+var_478], rax
0x180219130  lea     rax, [rbp+420h+var_488]
0x180219134  mov     [rbp+420h+ProcessHandle], rax
0x180219138  movups  [rbp+420h+var_488], xmm0
0x18021913c  call    ??$ConcatenateStrings@$$BY0BD@_WU_UNICODE_STRING@@$$BY02_WV?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Windows@@@Rtl@StringUtil@Windows@@YAJAEAY0BD@$$CB_WAEBU_UNICODE_STRING@@AEAY02$$CB_WV?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::ConcatenateStrings<wchar_t [19],_UNICODE_STRING,wchar_t [3],Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(wchar_t const (&)[19],_UNICODE_STRING const &,wchar_t const (&)[3],Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>)
0x180219141  mov     ebx, eax
0x180219143  test    eax, eax
0x180219145  jns     short loc_180219155
0x180219147  lea     rcx, [rbp+420h+var_488]
0x18021914b  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180219150  jmp     loc_180219310
0x180219155  xor     ebx, ebx
0x180219157  cmp     [rbp+420h+FileInformation], ebx
0x18021915a  jbe     loc_1802192EC
0x180219160  xorps   xmm0, xmm0
0x180219163  mov     [rsp+520h+ClientId.UniqueThread], 0
0x18021916c  lea     rdi, [rbp+420h+var_438]
0x180219170  mov     qword ptr [rsp+520h+ObjectAttributes.Length], 30h ; '0'
0x180219179  lea     rdi, [rdi+rbx*8]
0x18021917d  mov     qword ptr [rsp+520h+ObjectAttributes.Attributes], 0
0x180219186  mov     rax, [rdi]
0x180219189  lea     rcx, [rbp+420h+ProcessHandle]
0x18021918d  mov     [rsp+520h+ClientId.UniqueProcess], rax
0x180219192  movdqu  xmmword ptr [rsp+520h+ObjectAttributes.RootDirectory], xmm0
0x180219198  mov     [rbp+420h+ProcessHandle], 0
0x1802191a0  movdqu  xmmword ptr [rsp+520h+ObjectAttributes.SecurityDescriptor], xmm0
0x1802191a6  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1802191ab  mov     rcx, rax; ProcessHandle
0x1802191ae  lea     r9, [rsp+520h+ClientId]; ClientId
0x1802191b3  lea     r8, [rsp+520h+ObjectAttributes]; ObjectAttributes
0x1802191b8  mov     edx, 1000h; DesiredAccess
0x1802191bd  call    cs:__imp_NtOpenProcess
0x1802191c4  nop     dword ptr [rax+rax+00h]
0x1802191c9  mov     [rbp+420h+var_4A0], eax
0x1802191cc  test    eax, eax
0x1802191ce  jns     short loc_1802191EA
0x1802191d0  lea     rax, [rbp+420h+var_4A0]
0x1802191d4  mov     [rsp+520h+var_4F0], rax
0x1802191d9  lea     r8, aFailedToOpenPr_0; "Failed to open process {0} with status "...
0x1802191e0  lea     rax, [rsp+520h+var_4F0]
0x1802191e5  jmp     loc_1802192CB
0x1802191ea  xor     edx, edx; Val
0x1802191ec  lea     rcx, [rbp+420h+ProcessInformation]; void *
0x1802191f3  mov     r8d, 218h; Size
0x1802191f9  call    memset_0
0x1802191fe  mov     rcx, [rbp+420h+ProcessHandle]; ProcessHandle
0x180219202  lea     r8, [rbp+420h+ProcessInformation]; ProcessInformation
0x180219209  mov     r9d, 218h; ProcessInformationLength
0x18021920f  mov     qword ptr [rsp+520h+ShareAccess], 0; ReturnLength
0x180219218  mov     edx, 1Bh; ProcessInformationClass
0x18021921d  call    cs:__imp_NtQueryInformationProcess
0x180219224  nop     dword ptr [rax+rax+00h]
0x180219229  mov     [rbp+420h+var_4A0], eax
0x18021922c  test    eax, eax
0x18021922e  js      loc_1802192B6
0x180219234  xor     eax, eax
0x180219236  lea     rcx, asc_18036BC3C; ", "
0x18021923d  mov     [rbp+420h+var_460], rax
0x180219241  lea     r9, [rsp+520h+var_4F0]
0x180219246  lea     rax, [rbp+420h+var_470]
0x18021924a  xorps   xmm0, xmm0
0x18021924d  mov     [rsp+520h+var_4F0], rax
0x180219252  lea     r8, [rbp+420h+ProcessInformation]
0x180219259  test    ebx, ebx
0x18021925b  lea     rax, qword_1802EB518
0x180219262  lea     rdx, [rsp+520h+var_4E8]
0x180219267  cmovnz  rax, rcx
0x18021926b  lea     rcx, [rbp+420h+var_488]
0x18021926f  mov     [rsp+520h+var_4E8], rax
0x180219274  movups  [rbp+420h+var_470], xmm0
0x180219278  call    ??$ConcatenateStrings@V?$Auto@U_LUNICODE_STRING@@@Windows@@PEB_WU_UNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@2@@Rtl@StringUtil@Windows@@YAJAEBV?$Auto@U_LUNICODE_STRING@@@2@AEBQEB_WAEBU_UNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::ConcatenateStrings<Windows::Auto<_LUNICODE_STRING>,wchar_t const *,_UNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(Windows::Auto<_LUNICODE_STRING> const &,wchar_t const * const &,_UNICODE_STRING const &,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>)
0x18021927d  lea     rcx, [rbp+420h+var_470]
0x180219281  mov     edi, eax
0x180219283  test    eax, eax
0x180219285  js      loc_180219340
0x18021928b  movups  xmm2, [rbp+420h+var_488]
0x18021928f  movups  xmm0, [rbp+420h+var_470]
0x180219293  movsd   xmm3, [rbp+420h+var_478]
0x180219298  movsd   xmm1, [rbp+420h+var_460]
0x18021929d  movups  [rbp+420h+var_488], xmm0
0x1802192a1  movups  [rbp+420h+var_470], xmm2
0x1802192a5  movsd   [rbp+420h+var_478], xmm1
0x1802192aa  movsd   [rbp+420h+var_460], xmm3
0x1802192af  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1802192b4  jmp     short loc_1802192D8
0x1802192b6  lea     rax, [rbp+420h+var_4A0]
0x1802192ba  mov     [rsp+520h+var_4E8], rax
0x1802192bf  lea     r8, aFailedToQueryI_2; "Failed to query image path for process "...
0x1802192c6  lea     rax, [rsp+520h+var_4E8]
0x1802192cb  mov     r9, rdi
0x1802192ce  mov     qword ptr [rsp+520h+ShareAccess], rax
0x1802192d3  call    ??$RtlAutoTrace@_KU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@012@QEBDAEB_KAEBU?$FormatNtStatusWrapper@J@012@@Z; Windows::WCP::Rtl::RtlAutoTrace<unsigned __int64,Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64 const &,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x1802192d8  lea     rcx, [rbp+420h+ProcessHandle]
0x1802192dc  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1802192e1  inc     ebx
0x1802192e3  cmp     ebx, [rbp+420h+FileInformation]
0x1802192e6  jb      loc_180219160
0x1802192ec  lea     r9, [rbp+420h+var_488]
0x1802192f0  xor     ecx, ecx
0x1802192f2  lea     r8, a0_2; "{0}"
0x1802192f9  lea     rdx, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_SIL
0x180219300  call    ??$RtlAutoTrace@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@012@QEBDAEBV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::WCP::Rtl::RtlAutoTrace<Windows::Auto<_LUNICODE_STRING>>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,Windows::Auto<_LUNICODE_STRING> const &)
0x180219305  lea     rcx, [rbp+420h+var_488]
0x180219309  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18021930e  xor     ebx, ebx
0x180219310  lea     rcx, [rbp+420h+FileHandle]
0x180219314  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x180219319  mov     eax, ebx
0x18021931b  mov     rcx, [rbp+420h+var_10]
0x180219322  xor     rcx, rsp; StackCookie
0x180219325  call    __security_check_cookie
0x18021932a  lea     r11, [rsp+520h+var_s0]
0x180219332  mov     rbx, [r11+18h]
0x180219336  mov     rdi, [r11+20h]
0x18021933a  mov     rsp, r11
0x18021933d  pop     rbp
0x18021933e  retn
0x180219340  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180219345  lea     rcx, [rbp+420h+ProcessHandle]
0x180219349  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18021934e  lea     rcx, [rbp+420h+var_488]
0x180219352  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180219357  mov     ebx, edi
0x180219359  jmp     short loc_180219310
```
