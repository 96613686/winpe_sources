# MdmLogCollector::GetWorkingFolder(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,void *)

- ea: `0x18010fd74`
- end: `0x180110083`
- name: `?GetWorkingFolder@MdmLogCollector@@CAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `783`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18010b6d4`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800e66b8`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef8c8`
- `0x1800ef900`
- `0x180103bc4`
- `0x18010450c`
- `0x180105fec`
- `0x180107db8`
- `0x180108060`
- `0x18010fd74`
- `0x18011129c`
- `0x18012605c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18010fea4`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18010ffda`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18010fea4`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18010ffda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010ff9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010ff9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010fe3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010ff65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180110055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010fe3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010ff65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180110055`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18010ff91`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18010ff91`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18010fdec`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18010fdec`

## string_xrefs

- `0x18010fe07`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MdmLogCollector::GetWorkingFolder(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  void *v8; // rcx
  int v10; // eax
  wil *v11; // rax
  const unsigned __int16 *v12; // rax
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rcx
  void *v16; // rcx
  signed int LastError; // eax
  int v18; // eax
  wil *v19; // rax
  void *v20; // rcx
  bool v21; // zf
  LPVOID pv; // [rsp+20h] [rbp-278h] BYREF
  _BYTE v23[32]; // [rsp+28h] [rbp-270h] BYREF
  LPVOID *p_pv; // [rsp+48h] [rbp-250h] BYREF
  PWSTR ppszPath; // [rsp+50h] [rbp-248h] BYREF
  char v26; // [rsp+58h] [rbp-240h]
  _BYTE v27[528]; // [rsp+70h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  pv = 0;
  std::wstring::wstring(v23);
  if ( a3 == -1 )
  {
    memset_0(v27, 0, 0x208u);
    if ( !(unsigned int)GetTempPath2W(260, v27) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 >= 0 )
        goto LABEL_5;
      v7 = 1100;
      goto LABEL_4;
    }
    std::wstring::assign(a2, v27);
    std::wstring::append(a2, a1);
    v18 = rand();
    std::to_wstring(&p_pv, (unsigned int)(v18 % 10000));
    std::wstring::append(a2, &p_pv);
    std::wstring::_Tidy_deallocate(&p_pv);
    v19 = (wil *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    wil::RemoveDirectoryRecursiveNoThrow(v19, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
  }
  else
  {
    p_pv = &pv;
    ppszPath = 0;
    v26 = 1;
    v6 = SHGetKnownFolderPath(&FOLDERID_ProgramData, 0x4000u, 0, &ppszPath);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    if ( v6 < 0 )
    {
      v7 = 1065;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
        (const char *)(unsigned int)v6,
        (int)pv);
LABEL_5:
      std::wstring::_Tidy_deallocate(v23);
      v8 = pv;
      pv = 0;
      if ( v8 )
        CoTaskMemFree(v8);
      return (unsigned int)v6;
    }
    try
    {
      std::wstring::assign(v23, pv);
      std::wstring::append(v23, L"\\");
      std::wstring::append(v23, L"Microsoft\\MdmDiagnostics");
      std::wstring::append(v23, L"\\");
      std::wstring::operator=(a2, v23);
      std::wstring::append(a2, a1);
      v10 = rand();
      std::to_wstring(&p_pv, (unsigned int)(v10 % 10000));
      std::wstring::append(a2, &p_pv);
      std::wstring::_Tidy_deallocate(&p_pv);
      v11 = (wil *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      wil::RemoveDirectoryRecursiveNoThrow(v11, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
      v12 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      v13 = EnsureDirectoriesArePresent(v12);
    }
    catch ( ... )
    {
      std::wstring::_Tidy_deallocate(v23);
      v16 = pv;
      pv = 0;
      if ( v16 )
        CoTaskMemFree(v16);
      return 2147942414LL;
    }
    v6 = v13;
    if ( v13 < 0 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
      {
        v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
        McTemplateU0zd_EventWriteTransfer(
          v15,
          EnterpriseDiagnosticsMdmDiagnosticsCreatingOrCheckingDirectoryFailure,
          v14,
          (unsigned int)v6);
      }
      goto LABEL_5;
    }
  }
  std::wstring::_Tidy_deallocate(v23);
  v20 = pv;
  v21 = pv == 0;
  pv = 0;
  if ( !v21 )
    CoTaskMemFree(v20);
  return 0;
}

```

## disassembly

```asm
0x18010fd74  mov     [rsp+arg_10], rbx
0x18010fd79  mov     [rsp+arg_18], rsi
0x18010fd7e  push    r14
0x18010fd80  sub     rsp, 290h
0x18010fd87  mov     rax, cs:__security_cookie
0x18010fd8e  xor     rax, rsp
0x18010fd91  mov     [rsp+298h+var_18], rax
0x18010fd99  mov     rbx, r8
0x18010fd9c  mov     rsi, rdx
0x18010fd9f  mov     r14, rcx
0x18010fda2  mov     [rsp+298h+pv], 0; int
0x18010fdab  lea     rcx, [rsp+298h+var_270]
0x18010fdb0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18010fdb5  nop
0x18010fdb6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18010fdba  jz      loc_18010FF75
0x18010fdc0  lea     rax, [rsp+298h+pv]
0x18010fdc5  mov     [rsp+298h+var_250], rax
0x18010fdca  mov     [rsp+298h+ppszPath], 0
0x18010fdd3  mov     [rsp+298h+var_240], 1
0x18010fdd8  lea     r9, [rsp+298h+ppszPath]; ppszPath
0x18010fddd  xor     r8d, r8d; hToken
0x18010fde0  mov     edx, 4000h; dwFlags
0x18010fde5  lea     rcx, FOLDERID_ProgramData; rfid
0x18010fdec  call    cs:__imp_SHGetKnownFolderPath
0x18010fdf2  mov     ebx, eax
0x18010fdf4  lea     rcx, [rsp+298h+var_250]
0x18010fdf9  call    ??1?$out_param_t@V?$unique_ptr@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18010fdfe  test    ebx, ebx
0x18010fe00  jns     short loc_18010FE4A
0x18010fe02  mov     edx, 429h; void *
0x18010fe07  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010fe0e  mov     r9d, ebx; char *
0x18010fe11  mov     rcx, [rsp+298h]; this
0x18010fe19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010fe1e  nop
0x18010fe1f  lea     rcx, [rsp+298h+var_270]
0x18010fe24  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010fe29  nop
0x18010fe2a  mov     rcx, [rsp+298h+pv]; pv
0x18010fe2f  mov     [rsp+298h+pv], 0
0x18010fe38  test    rcx, rcx
0x18010fe3b  jz      short loc_18010FE43
0x18010fe3d  call    cs:__imp_CoTaskMemFree
0x18010fe43  mov     eax, ebx
0x18010fe45  jmp     loc_18011005D
0x18010fe4a  mov     rdx, [rsp+298h+pv]
0x18010fe4f  lea     rcx, [rsp+298h+var_270]
0x18010fe54  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18010fe59  lea     rdx, psz; "\\"
0x18010fe60  lea     rcx, [rsp+298h+var_270]
0x18010fe65  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010fe6a  lea     rdx, aMicrosoftMdmdi; "Microsoft\\MdmDiagnostics"
0x18010fe71  lea     rcx, [rsp+298h+var_270]
0x18010fe76  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010fe7b  lea     rdx, psz; "\\"
0x18010fe82  lea     rcx, [rsp+298h+var_270]
0x18010fe87  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010fe8c  lea     rdx, [rsp+298h+var_270]
0x18010fe91  mov     rcx, rsi
0x18010fe94  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18010fe99  mov     rdx, r14
0x18010fe9c  mov     rcx, rsi
0x18010fe9f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010fea4  call    cs:__imp_rand
0x18010feaa  mov     ecx, eax
0x18010feac  mov     eax, 68DB8BADh
0x18010feb1  imul    ecx
0x18010feb3  sar     edx, 0Ch
0x18010feb6  mov     eax, edx
0x18010feb8  shr     eax, 1Fh
0x18010febb  add     edx, eax
0x18010febd  imul    eax, edx, 2710h
0x18010fec3  sub     ecx, eax
0x18010fec5  mov     edx, ecx
0x18010fec7  lea     rcx, [rsp+298h+var_250]
0x18010fecc  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@J@Z; std::to_wstring(long)
0x18010fed1  nop
0x18010fed2  lea     rdx, [rsp+298h+var_250]
0x18010fed7  mov     rcx, rsi
0x18010feda  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18010fedf  nop
0x18010fee0  lea     rcx, [rsp+298h+var_250]
0x18010fee5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010feea  nop
0x18010feeb  mov     rcx, rsi
0x18010feee  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010fef3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18010fef7  xor     edx, edx
0x18010fef9  mov     rcx, rax
0x18010fefc  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18010ff01  mov     rcx, rsi
0x18010ff04  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010ff09  mov     rcx, rax; unsigned __int16 *
0x18010ff0c  call    ?EnsureDirectoriesArePresent@@YAJPEBG@Z; EnsureDirectoriesArePresent(ushort const *)
0x18010ff11  mov     ebx, eax
0x18010ff13  test    eax, eax
0x18010ff15  jns     loc_180110037
0x18010ff1b  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x18010ff22  jz      loc_18010FE1F
0x18010ff28  mov     rcx, rsi
0x18010ff2b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010ff30  mov     r9d, ebx
0x18010ff33  mov     r8, rax
0x18010ff36  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsCreatingOrCheckingDirectoryFailure
0x18010ff3d  call    McTemplateU0zd_EventWriteTransfer
0x18010ff42  jmp     loc_18010FE1F
0x18010ff47  lea     rcx, [rsp+298h+var_270]
0x18010ff4c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ff51  nop
0x18010ff52  mov     rcx, [rsp+298h+pv]; pv
0x18010ff57  mov     [rsp+298h+pv], 0
0x18010ff60  test    rcx, rcx
0x18010ff63  jz      short loc_18010FF6B
0x18010ff65  call    cs:__imp_CoTaskMemFree
0x18010ff6b  mov     eax, 8007000Eh
0x18010ff70  jmp     loc_18011005D
0x18010ff75  xor     edx, edx; Val
0x18010ff77  mov     r8d, 208h; Size
0x18010ff7d  lea     rcx, [rsp+298h+var_228]; void *
0x18010ff82  call    memset_0
0x18010ff87  lea     rdx, [rsp+298h+var_228]
0x18010ff8c  mov     ecx, 104h
0x18010ff91  call    cs:__imp_GetTempPath2W
0x18010ff97  test    eax, eax
0x18010ff99  jnz     short loc_18010FFC2
0x18010ff9b  call    cs:__imp_GetLastError
0x18010ffa1  mov     ebx, eax
0x18010ffa3  test    eax, eax
0x18010ffa5  jle     short loc_18010FFB0
0x18010ffa7  movzx   ebx, ax
0x18010ffaa  or      ebx, 80070000h
0x18010ffb0  test    ebx, ebx
0x18010ffb2  jns     loc_18010FE1F
0x18010ffb8  mov     edx, 44Ch
0x18010ffbd  jmp     loc_18010FE07
0x18010ffc2  lea     rdx, [rsp+298h+var_228]
0x18010ffc7  mov     rcx, rsi
0x18010ffca  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18010ffcf  mov     rdx, r14
0x18010ffd2  mov     rcx, rsi
0x18010ffd5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010ffda  call    cs:__imp_rand
0x18010ffe0  mov     ecx, eax
0x18010ffe2  mov     eax, 68DB8BADh
0x18010ffe7  imul    ecx
0x18010ffe9  sar     edx, 0Ch
0x18010ffec  mov     eax, edx
0x18010ffee  shr     eax, 1Fh
0x18010fff1  add     edx, eax
0x18010fff3  imul    eax, edx, 2710h
0x18010fff9  sub     ecx, eax
0x18010fffb  mov     edx, ecx
0x18010fffd  lea     rcx, [rsp+298h+var_250]
0x180110002  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@J@Z; std::to_wstring(long)
0x180110007  nop
0x180110008  lea     rdx, [rsp+298h+var_250]
0x18011000d  mov     rcx, rsi
0x180110010  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180110015  nop
0x180110016  lea     rcx, [rsp+298h+var_250]
0x18011001b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180110020  mov     rcx, rsi
0x180110023  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180110028  or      r8, 0FFFFFFFFFFFFFFFFh
0x18011002c  xor     edx, edx
0x18011002e  mov     rcx, rax
0x180110031  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x180110036  nop
0x180110037  lea     rcx, [rsp+298h+var_270]
0x18011003c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180110041  nop
0x180110042  mov     rcx, [rsp+298h+pv]; pv
0x180110047  test    rcx, rcx
0x18011004a  mov     [rsp+298h+pv], 0
0x180110053  jz      short loc_18011005B
0x180110055  call    cs:__imp_CoTaskMemFree
0x18011005b  xor     eax, eax
0x18011005d  mov     rcx, [rsp+298h+var_18]
0x180110065  xor     rcx, rsp; StackCookie
0x180110068  call    __security_check_cookie
0x18011006d  lea     r11, [rsp+298h+var_8]
0x180110075  mov     rbx, [r11+20h]
0x180110079  mov     rsi, [r11+28h]
0x18011007d  mov     rsp, r11
0x180110080  pop     r14
0x180110082  retn
```
