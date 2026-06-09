# WriteToFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1801334ac`
- end: `0x180133756`
- name: `?WriteToFile@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `682`
- prototype: ``
- caller_count: `6`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180127f24`
- `0x180128138`
- `0x180128330`
- `0x180129ee0`
- `0x18013116c`
- `0x18013375c`

## callees

- `0x180019080`
- `0x1800e6b14`
- `0x1800ed46c`
- `0x1800eef08`
- `0x1800ef89c`
- `0x1800ef8c4`
- `0x1800efd5c`
- `0x1800faa0c`
- `0x180129dc4`
- `0x1801334ac`
- `0x180134fc8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801336aa`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801336aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013356c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180133616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801336ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013356c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180133616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801336ba`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18013355c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180133606`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18013355c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180133606`

## string_xrefs

- `0x1801334fe`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18013351f`: `WriteToFile failed`
- `0x180133597`: `WriteToFile failed`
- `0x18013364d`: `WriteToFile failed`
- `0x1801336f1`: `WriteToFile failed`
- `0x18013371f`: `WriteToFile failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WriteToFile(__int64 a1)
{
  int v2; // esi
  unsigned int v3; // ebx
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v4; // rax
  const WCHAR *v6; // rax
  int v7; // eax
  signed int LastError; // eax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v9; // rax
  int cbMultiByte; // ebx
  const WCHAR *v11; // rdi
  CHAR *v12; // rax
  signed int v13; // eax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v14; // rax
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v15; // rax
  __int64 v16; // rbx
  const void *v17; // rax
  signed int v18; // eax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v19; // rax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v20; // rax
  int lpMultiByteStr; // [rsp+20h] [rbp-60h]
  int v22; // [rsp+40h] [rbp-40h] BYREF
  int *v23; // [rsp+48h] [rbp-38h] BYREF
  char v24; // [rsp+50h] [rbp-30h]
  __int128 v25; // [rsp+58h] [rbp-28h] BYREF
  DWORD nNumberOfBytesToWrite[2]; // [rsp+68h] [rbp-18h]
  __int64 v27; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v22 = 0;
  v23 = &v22;
  v24 = 1;
  v2 = *(_DWORD *)(a1 + 16);
  if ( !v2 )
  {
    v3 = -2147024809;
    v22 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)0x80070057LL,
      lpMultiByteStr);
    if ( v22 < 0 )
    {
      v4 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v4, L"WriteToFile failed", v22);
    }
    return v3;
  }
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  v7 = WideCharToMultiByte(0xFDE9u, 0, v6, v2, 0, 0, 0, 0);
  if ( !v7 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v22 = v3;
    if ( (v3 & 0x80000000) != 0 )
    {
      v9 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v9, L"WriteToFile failed", v22);
    }
    return v3;
  }
  v25 = 0;
  *(_QWORD *)nNumberOfBytesToWrite = 0;
  v27 = 15;
  LOBYTE(v25) = 0;
  std::string::resize(&v25, v7, 0);
  cbMultiByte = nNumberOfBytesToWrite[0];
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  v12 = (CHAR *)std::_String_val<std::_Simple_types<char>>::_Myptr(&v25);
  if ( !WideCharToMultiByte(0xFDE9u, 0, v11, v2, v12, cbMultiByte, 0, 0) )
  {
    v13 = GetLastError();
    v3 = v13;
    if ( v13 > 0 )
      v3 = (unsigned __int16)v13 | 0x80070000;
    v22 = v3;
    std::string::_Tidy_deallocate(&v25);
    if ( v22 < 0 )
    {
      v14 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v14, L"WriteToFile failed", v22);
    }
    return v3;
  }
  v15 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
  std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
    &v23,
    (char *)v15 + 16);
  if ( v23 )
    v16 = *(_QWORD *)v23;
  else
    v16 = -1;
  std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v23);
  v17 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(&v25);
  if ( !WriteFile((HANDLE)v16, v17, nNumberOfBytesToWrite[0], 0, 0) )
  {
    v18 = GetLastError();
    v3 = v18;
    if ( v18 > 0 )
      v3 = (unsigned __int16)v18 | 0x80070000;
    v22 = v3;
    std::string::_Tidy_deallocate(&v25);
    if ( v22 < 0 )
    {
      v19 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v19, L"WriteToFile failed", v22);
    }
    return v3;
  }
  std::string::_Tidy_deallocate(&v25);
  if ( v22 < 0 )
  {
    v20 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
    Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v20, L"WriteToFile failed", v22);
  }
  return 0;
}

```

## disassembly

```asm
0x1801334ac  mov     [rsp-18h+arg_8], rbx
0x1801334b1  mov     [rsp-18h+arg_10], rsi
0x1801334b6  push    rbp
0x1801334b7  push    rdi
0x1801334b8  push    r14
0x1801334ba  mov     rbp, rsp
0x1801334bd  sub     rsp, 80h
0x1801334c4  mov     rax, cs:__security_cookie
0x1801334cb  xor     rax, rsp
0x1801334ce  mov     [rbp+var_8], rax
0x1801334d2  mov     rdi, rcx
0x1801334d5  xor     r14d, r14d
0x1801334d8  mov     [rbp+var_40], r14d
0x1801334dc  lea     rax, [rbp+var_40]
0x1801334e0  mov     [rbp+var_38], rax
0x1801334e4  mov     [rbp+var_30], 1
0x1801334e8  mov     esi, [rcx+10h]
0x1801334eb  test    esi, esi
0x1801334ed  jnz     short loc_180133536
0x1801334ef  mov     ebx, 80070057h
0x1801334f4  mov     [rbp+var_40], ebx
0x1801334f7  mov     rcx, [rbp+18h]; this
0x1801334fb  mov     r9d, ebx; char *
0x1801334fe  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180133505  mov     edx, 27Bh; void *
0x18013350a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013350f  nop
0x180133510  cmp     [rbp+var_40], r14d
0x180133514  jge     short loc_18013352F
0x180133516  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013351b  mov     r8d, [rbp+var_40]; int
0x18013351f  lea     rdx, aWritetofileFai; "WriteToFile failed"
0x180133526  mov     rcx, rax; this
0x180133529  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013352e  nop
0x18013352f  mov     eax, ebx
0x180133531  jmp     loc_180133731
0x180133536  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013353b  mov     [rsp+80h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x180133540  mov     [rsp+80h+lpDefaultChar], r14; lpDefaultChar
0x180133545  mov     [rsp+80h+cbMultiByte], r14d; cbMultiByte
0x18013354a  mov     [rsp+80h+lpMultiByteStr], r14; lpMultiByteStr
0x18013354f  mov     r9d, esi; cchWideChar
0x180133552  mov     r8, rax; lpWideCharStr
0x180133555  xor     edx, edx; dwFlags
0x180133557  mov     ecx, 0FDE9h; CodePage
0x18013355c  call    cs:__imp_WideCharToMultiByte
0x180133563  nop     dword ptr [rax+rax+00h]
0x180133568  test    eax, eax
0x18013356a  jnz     short loc_1801335A9
0x18013356c  call    cs:__imp_GetLastError
0x180133573  nop     dword ptr [rax+rax+00h]
0x180133578  mov     ebx, eax
0x18013357a  test    eax, eax
0x18013357c  jle     short loc_180133587
0x18013357e  movzx   ebx, ax
0x180133581  or      ebx, 80070000h
0x180133587  mov     [rbp+var_40], ebx
0x18013358a  test    ebx, ebx
0x18013358c  jns     short loc_1801335A7
0x18013358e  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180133593  mov     r8d, [rbp+var_40]; int
0x180133597  lea     rdx, aWritetofileFai; "WriteToFile failed"
0x18013359e  mov     rcx, rax; this
0x1801335a1  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x1801335a6  nop
0x1801335a7  jmp     short loc_18013352F
0x1801335a9  xorps   xmm0, xmm0
0x1801335ac  movups  [rbp+var_28], xmm0
0x1801335b0  mov     qword ptr [rbp+nNumberOfBytesToWrite], r14
0x1801335b4  mov     [rbp+var_10], 0Fh
0x1801335bc  mov     byte ptr [rbp+var_28], r14b
0x1801335c0  movsxd  rdx, eax
0x1801335c3  xor     r8d, r8d
0x1801335c6  lea     rcx, [rbp+var_28]
0x1801335ca  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_KD@Z; std::string::resize(unsigned __int64,char)
0x1801335cf  mov     ebx, [rbp+nNumberOfBytesToWrite]
0x1801335d2  mov     rcx, rdi
0x1801335d5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801335da  mov     rdi, rax
0x1801335dd  lea     rcx, [rbp+var_28]
0x1801335e1  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1801335e6  mov     [rsp+80h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x1801335eb  mov     [rsp+80h+lpDefaultChar], r14; lpDefaultChar
0x1801335f0  mov     [rsp+80h+cbMultiByte], ebx; cbMultiByte
0x1801335f4  mov     [rsp+80h+lpMultiByteStr], rax; lpMultiByteStr
0x1801335f9  mov     r9d, esi; cchWideChar
0x1801335fc  mov     r8, rdi; lpWideCharStr
0x1801335ff  xor     edx, edx; dwFlags
0x180133601  mov     ecx, 0FDE9h; CodePage
0x180133606  call    cs:__imp_WideCharToMultiByte
0x18013360d  nop     dword ptr [rax+rax+00h]
0x180133612  test    eax, eax
0x180133614  jnz     short loc_180133662
0x180133616  call    cs:__imp_GetLastError
0x18013361d  nop     dword ptr [rax+rax+00h]
0x180133622  mov     ebx, eax
0x180133624  test    eax, eax
0x180133626  jle     short loc_180133631
0x180133628  movzx   ebx, ax
0x18013362b  or      ebx, 80070000h
0x180133631  mov     [rbp+var_40], ebx
0x180133634  lea     rcx, [rbp+var_28]
0x180133638  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013363d  nop
0x18013363e  cmp     [rbp+var_40], r14d
0x180133642  jge     short loc_18013365D
0x180133644  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180133649  mov     r8d, [rbp+var_40]; int
0x18013364d  lea     rdx, aWritetofileFai; "WriteToFile failed"
0x180133654  mov     rcx, rax; this
0x180133657  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013365c  nop
0x18013365d  jmp     loc_18013352F
0x180133662  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180133667  lea     rdx, [rax+10h]
0x18013366b  lea     rcx, [rbp+var_38]
0x18013366f  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180133674  mov     rcx, [rbp+var_38]
0x180133678  test    rcx, rcx
0x18013367b  jz      short loc_180133682
0x18013367d  mov     rbx, [rcx]
0x180133680  jmp     short loc_180133686
0x180133682  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180133686  lea     rcx, [rbp+var_38]
0x18013368a  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18013368f  lea     rcx, [rbp+var_28]
0x180133693  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180133698  mov     rdx, rax; lpBuffer
0x18013369b  mov     [rsp+80h+lpMultiByteStr], r14; lpOverlapped
0x1801336a0  xor     r9d, r9d; lpNumberOfBytesWritten
0x1801336a3  mov     r8d, [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x1801336a7  mov     rcx, rbx; hFile
0x1801336aa  call    cs:__imp_WriteFile
0x1801336b1  nop     dword ptr [rax+rax+00h]
0x1801336b6  test    eax, eax
0x1801336b8  jnz     short loc_180133706
0x1801336ba  call    cs:__imp_GetLastError
0x1801336c1  nop     dword ptr [rax+rax+00h]
0x1801336c6  mov     ebx, eax
0x1801336c8  test    eax, eax
0x1801336ca  jle     short loc_1801336D5
0x1801336cc  movzx   ebx, ax
0x1801336cf  or      ebx, 80070000h
0x1801336d5  mov     [rbp+var_40], ebx
0x1801336d8  lea     rcx, [rbp+var_28]
0x1801336dc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801336e1  nop
0x1801336e2  cmp     [rbp+var_40], r14d
0x1801336e6  jge     short loc_180133701
0x1801336e8  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x1801336ed  mov     r8d, [rbp+var_40]; int
0x1801336f1  lea     rdx, aWritetofileFai; "WriteToFile failed"
0x1801336f8  mov     rcx, rax; this
0x1801336fb  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180133700  nop
0x180133701  jmp     loc_18013352F
0x180133706  lea     rcx, [rbp+var_28]
0x18013370a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013370f  nop
0x180133710  cmp     [rbp+var_40], r14d
0x180133714  jge     short loc_18013372F
0x180133716  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013371b  mov     r8d, [rbp+var_40]; int
0x18013371f  lea     rdx, aWritetofileFai; "WriteToFile failed"
0x180133726  mov     rcx, rax; this
0x180133729  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013372e  nop
0x18013372f  xor     eax, eax
0x180133731  mov     rcx, [rbp+var_8]
0x180133735  xor     rcx, rsp; StackCookie
0x180133738  call    __security_check_cookie
0x18013373d  lea     r11, [rsp+80h+var_s0]
0x180133745  mov     rbx, [r11+28h]
0x180133749  mov     rsi, [r11+30h]
0x18013374d  mov     rsp, r11
0x180133750  pop     r14
0x180133752  pop     rdi
0x180133753  pop     rbp
0x180133754  retn
```
