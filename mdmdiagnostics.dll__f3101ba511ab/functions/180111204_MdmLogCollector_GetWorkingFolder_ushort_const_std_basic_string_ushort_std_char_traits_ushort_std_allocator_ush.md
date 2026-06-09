# MdmLogCollector::GetWorkingFolder(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,void *)

- ea: `0x180111204`
- end: `0x1801114d6`
- name: `?GetWorkingFolder@MdmLogCollector@@CAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18010cb20`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800e688c`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00ac`
- `0x1800f00e4`
- `0x180104cec`
- `0x180105744`
- `0x180107298`
- `0x1801090a4`
- `0x180109344`
- `0x180111204`
- `0x18011273c`
- `0x180112960`
- `0x180127a74`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x1801112fb`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180111433`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x1801112fb`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180111433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801113da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801113da`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1801113ca`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1801113ca`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18011127b`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18011127b`

## string_xrefs

- `0x180111402`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MdmLogCollector::GetWorkingFolder(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  int v8; // eax
  wil *v9; // rax
  const unsigned __int16 *v10; // rax
  signed int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rcx
  signed int LastError; // eax
  int v15; // eax
  wil *v16; // rax
  int v18[2]; // [rsp+20h] [rbp-278h] BYREF
  int *v19; // [rsp+28h] [rbp-270h] BYREF
  PWSTR ppszPath; // [rsp+30h] [rbp-268h] BYREF
  char v21; // [rsp+38h] [rbp-260h]
  _BYTE v22[40]; // [rsp+48h] [rbp-250h] BYREF
  _BYTE v23[528]; // [rsp+70h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  *(_QWORD *)v18 = 0;
  std::wstring::wstring(v22);
  if ( a3 != -1 )
  {
    v19 = v18;
    ppszPath = 0;
    v21 = 1;
    v6 = SHGetKnownFolderPath(&FOLDERID_ProgramData, 0x4000u, 0, &ppszPath);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v19);
    if ( v6 < 0 )
    {
      v7 = 1064;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
        (const char *)(unsigned int)v6,
        v18[0]);
      goto LABEL_15;
    }
    try
    {
      std::wstring::assign(v22, *(_QWORD *)v18);
      std::wstring::append(v22, L"\\");
      std::wstring::append(v22, L"Microsoft\\MdmDiagnostics");
      std::wstring::append(v22, L"\\");
      std::wstring::operator=(a2, v22);
      std::wstring::append(a2, a1);
      v8 = rand();
      std::to_wstring(&v19, (unsigned int)(v8 % 10000));
      std::wstring::append(a2, &v19);
      std::wstring::_Tidy_deallocate(&v19);
      v9 = (wil *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      wil::RemoveDirectoryRecursiveNoThrow(v9, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
      v10 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      v11 = EnsureDirectoriesArePresent(v10);
    }
    catch ( ... )
    {
      v6 = -2147024882;
      goto LABEL_15;
    }
    v6 = v11;
    if ( v11 < 0 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
      {
        v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
        McTemplateU0zd_EventWriteTransfer(
          v13,
          EnterpriseDiagnosticsMdmDiagnosticsCreatingOrCheckingDirectoryFailure,
          v12,
          (unsigned int)v6);
      }
      goto LABEL_15;
    }
LABEL_14:
    v6 = 0;
    goto LABEL_15;
  }
  memset_0(v23, 0, 0x208u);
  if ( (unsigned int)GetTempPath2W(260, v23) )
  {
    std::wstring::assign(a2, v23);
    std::wstring::append(a2, a1);
    v15 = rand();
    std::to_wstring(&v19, (unsigned int)(v15 % 10000));
    std::wstring::append(a2, &v19);
    std::wstring::_Tidy_deallocate(&v19);
    v16 = (wil *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    wil::RemoveDirectoryRecursiveNoThrow(v16, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
    goto LABEL_14;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 < 0 )
  {
    v7 = 1099;
    goto LABEL_12;
  }
LABEL_15:
  std::wstring::_Tidy_deallocate(v22);
  wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(v18, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180111204  mov     [rsp+arg_10], rbx
0x180111209  mov     [rsp+arg_18], rsi
0x18011120e  push    rdi
0x18011120f  sub     rsp, 290h
0x180111216  mov     rax, cs:__security_cookie
0x18011121d  xor     rax, rsp
0x180111220  mov     [rsp+298h+var_18], rax
0x180111228  mov     rbx, r8
0x18011122b  mov     rdi, rdx
0x18011122e  mov     rsi, rcx
0x180111231  mov     qword ptr [rsp+298h+var_278], 0; int
0x18011123a  lea     rcx, [rsp+298h+var_250]
0x18011123f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180111244  nop
0x180111245  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180111249  jz      loc_1801113AE
0x18011124f  lea     rax, [rsp+298h+var_278]
0x180111254  mov     [rsp+298h+var_270], rax
0x180111259  mov     [rsp+298h+ppszPath], 0
0x180111262  mov     [rsp+298h+var_260], 1
0x180111267  lea     r9, [rsp+298h+ppszPath]; ppszPath
0x18011126c  xor     r8d, r8d; hToken
0x18011126f  mov     edx, 4000h; dwFlags
0x180111274  lea     rcx, FOLDERID_ProgramData; rfid
0x18011127b  call    cs:__imp_SHGetKnownFolderPath
0x180111282  nop     dword ptr [rax+rax+00h]
0x180111287  mov     ebx, eax
0x180111289  lea     rcx, [rsp+298h+var_270]
0x18011128e  call    ??1?$out_param_t@V?$unique_ptr@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180111293  test    ebx, ebx
0x180111295  jns     short loc_1801112A1
0x180111297  mov     edx, 428h
0x18011129c  jmp     loc_180111402
0x1801112a1  mov     rdx, qword ptr [rsp+298h+var_278]
0x1801112a6  lea     rcx, [rsp+298h+var_250]
0x1801112ab  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801112b0  lea     rdx, psz; "\\"
0x1801112b7  lea     rcx, [rsp+298h+var_250]
0x1801112bc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1801112c1  lea     rdx, aMicrosoftMdmdi; "Microsoft\\MdmDiagnostics"
0x1801112c8  lea     rcx, [rsp+298h+var_250]
0x1801112cd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1801112d2  lea     rdx, psz; "\\"
0x1801112d9  lea     rcx, [rsp+298h+var_250]
0x1801112de  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1801112e3  lea     rdx, [rsp+298h+var_250]
0x1801112e8  mov     rcx, rdi
0x1801112eb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801112f0  mov     rdx, rsi
0x1801112f3  mov     rcx, rdi
0x1801112f6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1801112fb  call    cs:__imp_rand
0x180111302  nop     dword ptr [rax+rax+00h]
0x180111307  mov     ecx, eax
0x180111309  mov     eax, 68DB8BADh
0x18011130e  imul    ecx
0x180111310  sar     edx, 0Ch
0x180111313  mov     eax, edx
0x180111315  shr     eax, 1Fh
0x180111318  add     edx, eax
0x18011131a  imul    eax, edx, 2710h
0x180111320  sub     ecx, eax
0x180111322  mov     edx, ecx
0x180111324  lea     rcx, [rsp+298h+var_270]
0x180111329  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@J@Z; std::to_wstring(long)
0x18011132e  nop
0x18011132f  lea     rdx, [rsp+298h+var_270]
0x180111334  mov     rcx, rdi
0x180111337  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011133c  nop
0x18011133d  lea     rcx, [rsp+298h+var_270]
0x180111342  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180111347  nop
0x180111348  mov     rcx, rdi
0x18011134b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180111350  or      r8, 0FFFFFFFFFFFFFFFFh
0x180111354  xor     edx, edx
0x180111356  mov     rcx, rax
0x180111359  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18011135e  mov     rcx, rdi
0x180111361  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180111366  mov     rcx, rax; unsigned __int16 *
0x180111369  call    ?EnsureDirectoriesArePresent@@YAJPEBG@Z; EnsureDirectoriesArePresent(ushort const *)
0x18011136e  mov     ebx, eax
0x180111370  test    eax, eax
0x180111372  jns     loc_180111495
0x180111378  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x18011137f  jz      loc_180111497
0x180111385  mov     rcx, rdi
0x180111388  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011138d  mov     r9d, ebx
0x180111390  mov     r8, rax
0x180111393  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsCreatingOrCheckingDirectoryFailure
0x18011139a  call    McTemplateU0zd_EventWriteTransfer
0x18011139f  jmp     loc_180111497
0x1801113a4  mov     ebx, 8007000Eh
0x1801113a9  jmp     loc_180111497
0x1801113ae  xor     edx, edx; Val
0x1801113b0  mov     r8d, 208h; Size
0x1801113b6  lea     rcx, [rsp+298h+var_228]; void *
0x1801113bb  call    memset_0
0x1801113c0  lea     rdx, [rsp+298h+var_228]
0x1801113c5  mov     ecx, 104h
0x1801113ca  call    cs:__imp_GetTempPath2W
0x1801113d1  nop     dword ptr [rax+rax+00h]
0x1801113d6  test    eax, eax
0x1801113d8  jnz     short loc_18011141B
0x1801113da  call    cs:__imp_GetLastError
0x1801113e1  nop     dword ptr [rax+rax+00h]
0x1801113e6  mov     ebx, eax
0x1801113e8  test    eax, eax
0x1801113ea  jle     short loc_1801113F5
0x1801113ec  movzx   ebx, ax
0x1801113ef  or      ebx, 80070000h
0x1801113f5  test    ebx, ebx
0x1801113f7  jns     loc_180111497
0x1801113fd  mov     edx, 44Bh; void *
0x180111402  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180111409  mov     r9d, ebx; char *
0x18011140c  mov     rcx, [rsp+298h]; this
0x180111414  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180111419  jmp     short loc_180111497
0x18011141b  lea     rdx, [rsp+298h+var_228]
0x180111420  mov     rcx, rdi
0x180111423  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180111428  mov     rdx, rsi
0x18011142b  mov     rcx, rdi
0x18011142e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180111433  call    cs:__imp_rand
0x18011143a  nop     dword ptr [rax+rax+00h]
0x18011143f  mov     ecx, eax
0x180111441  mov     eax, 68DB8BADh
0x180111446  imul    ecx
0x180111448  sar     edx, 0Ch
0x18011144b  mov     eax, edx
0x18011144d  shr     eax, 1Fh
0x180111450  add     edx, eax
0x180111452  imul    eax, edx, 2710h
0x180111458  sub     ecx, eax
0x18011145a  mov     edx, ecx
0x18011145c  lea     rcx, [rsp+298h+var_270]
0x180111461  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@J@Z; std::to_wstring(long)
0x180111466  nop
0x180111467  lea     rdx, [rsp+298h+var_270]
0x18011146c  mov     rcx, rdi
0x18011146f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180111474  nop
0x180111475  lea     rcx, [rsp+298h+var_270]
0x18011147a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011147f  mov     rcx, rdi
0x180111482  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180111487  or      r8, 0FFFFFFFFFFFFFFFFh
0x18011148b  xor     edx, edx
0x18011148d  mov     rcx, rax
0x180111490  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x180111495  xor     ebx, ebx
0x180111497  lea     rcx, [rsp+298h+var_250]
0x18011149c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801114a1  nop
0x1801114a2  xor     edx, edx
0x1801114a4  lea     rcx, [rsp+298h+var_278]
0x1801114a9  call    ?reset@?$unique_ptr@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(ushort *)
0x1801114ae  mov     eax, ebx
0x1801114b0  mov     rcx, [rsp+298h+var_18]
0x1801114b8  xor     rcx, rsp; StackCookie
0x1801114bb  call    __security_check_cookie
0x1801114c0  lea     r11, [rsp+298h+var_8]
0x1801114c8  mov     rbx, [r11+20h]
0x1801114cc  mov     rsi, [r11+28h]
0x1801114d0  mov     rsp, r11
0x1801114d3  pop     rdi
0x1801114d4  retn
```
