# WriteToFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180131690`
- end: `0x180131915`
- name: `?WriteToFile@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `645`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801264e8`
- `0x1801266fc`
- `0x1801268f0`
- `0x1801283b0`
- `0x18012f3c0`
- `0x18013191c`

## callees

- `0x180019000`
- `0x1800e691c`
- `0x1800ece5c`
- `0x1800ee878`
- `0x1800ef164`
- `0x1800ef188`
- `0x1800ef598`
- `0x1800f9a0c`
- `0x1801282b0`
- `0x180131690`
- `0x1801330f8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180131876`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180131876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013174a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801317e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180131880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013174a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801317e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180131880`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180131740`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1801317de`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180131740`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1801317de`

## string_xrefs

- `0x1801316e2`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180131703`: `WriteToFile failed`
- `0x18013176f`: `WriteToFile failed`
- `0x180131819`: `WriteToFile failed`
- `0x1801318b1`: `WriteToFile failed`
- `0x1801318df`: `WriteToFile failed`

## pseudocode

```c
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
0x180131690  mov     [rsp-18h+arg_8], rbx
0x180131695  mov     [rsp-18h+arg_10], rsi
0x18013169a  push    rbp
0x18013169b  push    rdi
0x18013169c  push    r14
0x18013169e  mov     rbp, rsp
0x1801316a1  sub     rsp, 80h
0x1801316a8  mov     rax, cs:__security_cookie
0x1801316af  xor     rax, rsp
0x1801316b2  mov     [rbp+var_8], rax
0x1801316b6  mov     rdi, rcx
0x1801316b9  xor     r14d, r14d
0x1801316bc  mov     [rbp+var_40], r14d
0x1801316c0  lea     rax, [rbp+var_40]
0x1801316c4  mov     [rbp+var_38], rax
0x1801316c8  mov     [rbp+var_30], 1
0x1801316cc  mov     esi, [rcx+10h]
0x1801316cf  test    esi, esi
0x1801316d1  jnz     short loc_18013171A
0x1801316d3  mov     ebx, 80070057h
0x1801316d8  mov     [rbp+var_40], ebx
0x1801316db  mov     rcx, [rbp+18h]; this
0x1801316df  mov     r9d, ebx; char *
0x1801316e2  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801316e9  mov     edx, 27Bh; void *
0x1801316ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801316f3  nop
0x1801316f4  cmp     [rbp+var_40], r14d
0x1801316f8  jge     short loc_180131713
0x1801316fa  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x1801316ff  mov     r8d, [rbp+var_40]; int
0x180131703  lea     rdx, aWritetofileFai; "WriteToFile failed"
0x18013170a  mov     rcx, rax; this
0x18013170d  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180131712  nop
0x180131713  mov     eax, ebx
0x180131715  jmp     loc_1801318F1
0x18013171a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013171f  mov     [rsp+80h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x180131724  mov     [rsp+80h+lpDefaultChar], r14; lpDefaultChar
0x180131729  mov     [rsp+80h+cbMultiByte], r14d; cbMultiByte
0x18013172e  mov     [rsp+80h+lpMultiByteStr], r14; lpMultiByteStr
0x180131733  mov     r9d, esi; cchWideChar
0x180131736  mov     r8, rax; lpWideCharStr
0x180131739  xor     edx, edx; dwFlags
0x18013173b  mov     ecx, 0FDE9h; CodePage
0x180131740  call    cs:__imp_WideCharToMultiByte
0x180131746  test    eax, eax
0x180131748  jnz     short loc_180131781
0x18013174a  call    cs:__imp_GetLastError
0x180131750  mov     ebx, eax
0x180131752  test    eax, eax
0x180131754  jle     short loc_18013175F
0x180131756  movzx   ebx, ax
0x180131759  or      ebx, 80070000h
0x18013175f  mov     [rbp+var_40], ebx
0x180131762  test    ebx, ebx
0x180131764  jns     short loc_18013177F
0x180131766  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013176b  mov     r8d, [rbp+var_40]; int
0x18013176f  lea     rdx, aWritetofileFai; "WriteToFile failed"
0x180131776  mov     rcx, rax; this
0x180131779  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013177e  nop
0x18013177f  jmp     short loc_180131713
0x180131781  xorps   xmm0, xmm0
0x180131784  movups  [rbp+var_28], xmm0
0x180131788  mov     qword ptr [rbp+nNumberOfBytesToWrite], r14
0x18013178c  mov     [rbp+var_10], 0Fh
0x180131794  mov     byte ptr [rbp+var_28], r14b
0x180131798  movsxd  rdx, eax
0x18013179b  xor     r8d, r8d
0x18013179e  lea     rcx, [rbp+var_28]
0x1801317a2  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_KD@Z; std::string::resize(unsigned __int64,char)
0x1801317a7  mov     ebx, [rbp+nNumberOfBytesToWrite]
0x1801317aa  mov     rcx, rdi
0x1801317ad  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801317b2  mov     rdi, rax
0x1801317b5  lea     rcx, [rbp+var_28]
0x1801317b9  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1801317be  mov     [rsp+80h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x1801317c3  mov     [rsp+80h+lpDefaultChar], r14; lpDefaultChar
0x1801317c8  mov     [rsp+80h+cbMultiByte], ebx; cbMultiByte
0x1801317cc  mov     [rsp+80h+lpMultiByteStr], rax; lpMultiByteStr
0x1801317d1  mov     r9d, esi; cchWideChar
0x1801317d4  mov     r8, rdi; lpWideCharStr
0x1801317d7  xor     edx, edx; dwFlags
0x1801317d9  mov     ecx, 0FDE9h; CodePage
0x1801317de  call    cs:__imp_WideCharToMultiByte
0x1801317e4  test    eax, eax
0x1801317e6  jnz     short loc_18013182E
0x1801317e8  call    cs:__imp_GetLastError
0x1801317ee  mov     ebx, eax
0x1801317f0  test    eax, eax
0x1801317f2  jle     short loc_1801317FD
0x1801317f4  movzx   ebx, ax
0x1801317f7  or      ebx, 80070000h
0x1801317fd  mov     [rbp+var_40], ebx
0x180131800  lea     rcx, [rbp+var_28]
0x180131804  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180131809  nop
0x18013180a  cmp     [rbp+var_40], r14d
0x18013180e  jge     short loc_180131829
0x180131810  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180131815  mov     r8d, [rbp+var_40]; int
0x180131819  lea     rdx, aWritetofileFai; "WriteToFile failed"
0x180131820  mov     rcx, rax; this
0x180131823  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180131828  nop
0x180131829  jmp     loc_180131713
0x18013182e  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180131833  lea     rdx, [rax+10h]
0x180131837  lea     rcx, [rbp+var_38]
0x18013183b  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180131840  mov     rcx, [rbp+var_38]
0x180131844  test    rcx, rcx
0x180131847  jz      short loc_18013184E
0x180131849  mov     rbx, [rcx]
0x18013184c  jmp     short loc_180131852
0x18013184e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180131852  lea     rcx, [rbp+var_38]
0x180131856  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18013185b  lea     rcx, [rbp+var_28]
0x18013185f  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180131864  mov     rdx, rax; lpBuffer
0x180131867  mov     [rsp+80h+lpMultiByteStr], r14; lpOverlapped
0x18013186c  xor     r9d, r9d; lpNumberOfBytesWritten
0x18013186f  mov     r8d, [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180131873  mov     rcx, rbx; hFile
0x180131876  call    cs:__imp_WriteFile
0x18013187c  test    eax, eax
0x18013187e  jnz     short loc_1801318C6
0x180131880  call    cs:__imp_GetLastError
0x180131886  mov     ebx, eax
0x180131888  test    eax, eax
0x18013188a  jle     short loc_180131895
0x18013188c  movzx   ebx, ax
0x18013188f  or      ebx, 80070000h
0x180131895  mov     [rbp+var_40], ebx
0x180131898  lea     rcx, [rbp+var_28]
0x18013189c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801318a1  nop
0x1801318a2  cmp     [rbp+var_40], r14d
0x1801318a6  jge     short loc_1801318C1
0x1801318a8  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x1801318ad  mov     r8d, [rbp+var_40]; int
0x1801318b1  lea     rdx, aWritetofileFai; "WriteToFile failed"
0x1801318b8  mov     rcx, rax; this
0x1801318bb  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x1801318c0  nop
0x1801318c1  jmp     loc_180131713
0x1801318c6  lea     rcx, [rbp+var_28]
0x1801318ca  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801318cf  nop
0x1801318d0  cmp     [rbp+var_40], r14d
0x1801318d4  jge     short loc_1801318EF
0x1801318d6  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x1801318db  mov     r8d, [rbp+var_40]; int
0x1801318df  lea     rdx, aWritetofileFai; "WriteToFile failed"
0x1801318e6  mov     rcx, rax; this
0x1801318e9  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x1801318ee  nop
0x1801318ef  xor     eax, eax
0x1801318f1  mov     rcx, [rbp+var_8]
0x1801318f5  xor     rcx, rsp; StackCookie
0x1801318f8  call    __security_check_cookie
0x1801318fd  lea     r11, [rsp+80h+var_s0]
0x180131905  mov     rbx, [r11+28h]
0x180131909  mov     rsi, [r11+30h]
0x18013190d  mov     rsp, r11
0x180131910  pop     r14
0x180131912  pop     rdi
0x180131913  pop     rbp
0x180131914  retn
```
