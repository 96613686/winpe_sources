# EndpointDlp::WindowsPlatformApi::ProcessDlpWebsiteRules(void)

- ea: `0x180180938`
- end: `0x180180b9a`
- name: `?ProcessDlpWebsiteRules@WindowsPlatformApi@EndpointDlp@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `610`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18017fa60`
- `0x180181030`

## callees

- `0x180024ac0`
- `0x180034420`
- `0x180038450`
- `0x1800499f0`
- `0x180061130`
- `0x180063438`
- `0x1800a1824`
- `0x1800a6bfc`
- `0x1800b9b34`
- `0x18010cb40`
- `0x180180938`
- `0x1801b7b74`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180180966`
- `KERNEL32!GetCurrentProcessId` at `0x180180966`
- `KERNEL32!OpenProcess` at `0x180180976`
- `KERNEL32!OpenProcess` at `0x180180976`
- `KERNEL32!LocalFree` at `0x180180b38`
- `KERNEL32!LocalFree` at `0x180180b38`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1801809fe`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1801809fe`

## string_xrefs

- `0x180180996`: `Failed to open an existing local process object`
- `0x180180a0c`: `Failed to retrieve the process user token`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
_OWORD *__fastcall EndpointDlp::WindowsPlatformApi::ProcessDlpWebsiteRules(__int64 a1, _OWORD *a2)
{
  DWORD CurrentProcessId; // eax
  unsigned int v4; // eax
  const char *v6; // [rsp+28h] [rbp-C0h]
  const char *v7; // [rsp+28h] [rbp-C0h]
  LPWSTR StringSid; // [rsp+70h] [rbp-78h] BYREF
  char *v9; // [rsp+78h] [rbp-70h] BYREF
  void *Src[2]; // [rsp+80h] [rbp-68h]
  __int64 v11; // [rsp+90h] [rbp-58h]
  WCHAR ValueName[8]; // [rsp+98h] [rbp-50h] BYREF
  __m128i si128; // [rsp+A8h] [rbp-40h]
  PSID Sid[2]; // [rsp+B8h] [rbp-30h] BYREF
  __int64 v15; // [rsp+C8h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  CurrentProcessId = GetCurrentProcessId();
  v9 = (char *)OpenProcess(0x1000u, 0, CurrentProcessId);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x248,
    (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\lib\\windowsPlatformApi.cpp",
    (const char *)((unsigned __int64)(v9 - 1) > 0xFFFFFFFFFFFFFFFDuLL),
    (bool)"Failed to open an existing local process object",
    v6);
  *(_OWORD *)Sid = 0;
  v15 = 0;
  EndpointDlp::Common::GetProcessUserSid((__int64)Sid, v9);
  StringSid = 0;
  v4 = ConvertSidToStringSidW(Sid[0], &StringSid);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x251,
    (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\lib\\windowsPlatformApi.cpp",
    (const char *)v4,
    (int)"Failed to retrieve the process user token",
    v7);
  *(_OWORD *)Src = 0;
  v11 = 0;
  std::wstring::wstring(ValueName, StringSid);
  EndpointDlp::Common::GetLocalMachineStringRegistryValue(
    &EndpointDlp::Registry::WindowsDefender::DlpWebsites_Rules::Key,
    ValueName);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(ValueName);
  *(_OWORD *)ValueName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  ValueName[0] = 0;
  std::wstring::assign(ValueName, Src[0]);
  *a2 = *(_OWORD *)ValueName;
  a2[1] = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  ValueName[0] = 0;
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(ValueName);
  if ( Src[0] )
  {
    std::_Deallocate<16>(Src[0], v11 - (unsigned __int64)Src[0]);
    *(_OWORD *)Src = 0;
    v11 = 0;
  }
  LocalFree(StringSid);
  std::vector<unsigned char>::_Tidy(Sid);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
  return a2;
}

```

## disassembly

```asm
0x180180938  mov     [rsp+arg_0], rbx
0x18018093d  mov     [rsp+arg_10], rsi
0x180180942  push    rdi
0x180180943  sub     rsp, 0E0h
0x18018094a  mov     rax, cs:__security_cookie
0x180180951  xor     rax, rsp
0x180180954  mov     [rsp+0E8h+var_18], rax
0x18018095c  mov     rdi, rdx
0x18018095f  mov     [rsp+0E8h+var_A8], rdx
0x180180964  xor     esi, esi
0x180180966  call    cs:__imp_GetCurrentProcessId
0x18018096c  mov     r8d, eax; dwProcessId
0x18018096f  xor     edx, edx; bInheritHandle
0x180180971  mov     ecx, 1000h; dwDesiredAccess
0x180180976  call    cs:__imp_OpenProcess
0x18018097c  mov     rbx, rax
0x18018097f  mov     [rsp+0E8h+var_70], rax
0x180180984  dec     rax
0x180180987  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18018098b  setnbe  al
0x18018098e  mov     rcx, [rsp+0E8h]; this
0x180180996  lea     rdx, aFailedToOpenAn; "Failed to open an existing local proces"...
0x18018099d  mov     qword ptr [rsp+0E8h+var_C8], rdx; bool
0x1801809a2  movzx   r9d, al; char *
0x1801809a6  lea     r8, aSrcEppDlpEndpo_5; "src\\epp\\Dlp\\EndpointDlp\\lib\\window"...
0x1801809ad  mov     edx, 248h; void *
0x1801809b2  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1801809b7  xorps   xmm0, xmm0
0x1801809ba  xor     eax, eax
0x1801809bc  movups  xmmword ptr [rsp+0E8h+Sid], xmm0
0x1801809c4  mov     [rsp+0E8h+var_20], rax
0x1801809cc  mov     rdx, rbx
0x1801809cf  lea     rcx, [rsp+0E8h+Sid]
0x1801809d7  call    ?GetProcessUserSid@Common@EndpointDlp@@YA?AV?$vector@EV?$allocator@E@std@@@std@@PEAX@Z; EndpointDlp::Common::GetProcessUserSid(void *)
0x1801809dc  nop
0x1801809dd  mov     [rsp+0E8h+StringSid], rsi
0x1801809e2  mov     [rsp+0E8h+var_98], sil
0x1801809e7  lea     rax, [rsp+0E8h+StringSid]
0x1801809ec  mov     [rsp+0E8h+var_90], rax
0x1801809f1  lea     rdx, [rsp+0E8h+StringSid]; StringSid
0x1801809f6  mov     rcx, [rsp+0E8h+Sid]; Sid
0x1801809fe  call    cs:__imp_ConvertSidToStringSidW
0x180180a04  mov     rcx, [rsp+0E8h]; this
0x180180a0c  lea     rdx, aFailedToRetrie_0; "Failed to retrieve the process user tok"...
0x180180a13  mov     qword ptr [rsp+0E8h+var_C8], rdx; int
0x180180a18  mov     r9d, eax; char *
0x180180a1b  lea     r8, aSrcEppDlpEndpo_5; "src\\epp\\Dlp\\EndpointDlp\\lib\\window"...
0x180180a22  mov     edx, 251h; void *
0x180180a27  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180180a2c  xorps   xmm1, xmm1
0x180180a2f  movdqu  xmmword ptr [rsp+0E8h+Src], xmm1
0x180180a38  mov     [rsp+0E8h+var_58], rsi
0x180180a40  mov     rdx, [rsp+0E8h+StringSid]
0x180180a45  lea     rcx, [rsp+0E8h+ValueName]
0x180180a4d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180180a52  nop
0x180180a53  lea     r8, [rsp+0E8h+Src]
0x180180a5b  lea     rdx, [rsp+0E8h+ValueName]; lpValueName
0x180180a63  lea     rcx, ?Key@DlpWebsites_Rules@WindowsDefender@Registry@EndpointDlp@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; lpSubKey
0x180180a6a  call    ?GetLocalMachineStringRegistryValue@Common@EndpointDlp@@YAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV?$vector@EV?$allocator@E@std@@@4@@Z; EndpointDlp::Common::GetLocalMachineStringRegistryValue(std::wstring const &,std::wstring const &,std::vector<uchar> &)
0x180180a6f  nop
0x180180a70  lea     rcx, [rsp+0E8h+ValueName]; void *
0x180180a78  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180180a7d  xorps   xmm0, xmm0
0x180180a80  movups  xmmword ptr [rsp+0E8h+ValueName], xmm0
0x180180a88  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180180a90  movdqu  [rsp+0E8h+var_40], xmm1
0x180180a99  mov     [rsp+0E8h+ValueName], si
0x180180aa1  mov     r8, [rsp+0E8h+Src+8]
0x180180aa9  mov     rdx, [rsp+0E8h+Src]; Src
0x180180ab1  sub     r8, rdx
0x180180ab4  shr     r8, 1
0x180180ab7  lea     rcx, [rsp+0E8h+ValueName]; void *
0x180180abf  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x180180ac4  movups  xmm0, xmmword ptr [rsp+0E8h+ValueName]
0x180180acc  movups  xmmword ptr [rdi], xmm0
0x180180acf  movups  xmm1, [rsp+0E8h+var_40]
0x180180ad7  movups  xmmword ptr [rdi+10h], xmm1
0x180180adb  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180180ae3  movdqu  [rsp+0E8h+var_40], xmm0
0x180180aec  mov     [rsp+0E8h+ValueName], si
0x180180af4  lea     rcx, [rsp+0E8h+ValueName]; void *
0x180180afc  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180180b01  nop
0x180180b02  mov     rcx, [rsp+0E8h+Src]
0x180180b0a  test    rcx, rcx
0x180180b0d  jz      short loc_180180B33
0x180180b0f  mov     rdx, [rsp+0E8h+var_58]
0x180180b17  sub     rdx, rcx
0x180180b1a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180180b1f  xorps   xmm0, xmm0
0x180180b22  movdqu  xmmword ptr [rsp+0E8h+Src], xmm0
0x180180b2b  mov     [rsp+0E8h+var_58], rsi
0x180180b33  mov     rcx, [rsp+0E8h+StringSid]; hMem
0x180180b38  call    cs:__imp_LocalFree
0x180180b3e  nop
0x180180b3f  lea     rcx, [rsp+0E8h+Sid]
0x180180b47  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180180b4c  nop
0x180180b4d  lea     rcx, [rsp+0E8h+var_70]
0x180180b52  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180180b57  mov     rax, rdi
0x180180b5a  jmp     short loc_180180B74
0x180180b5c  jmp     short $+2
0x180180b5e  lea     rdx, qword_18025C818
0x180180b65  mov     rcx, [rsp+0E8h+var_A8]
0x180180b6a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180180b6f  mov     rax, [rsp+0E8h+var_A8]
0x180180b74  mov     rcx, [rsp+0E8h+var_18]
0x180180b7c  xor     rcx, rsp; StackCookie
0x180180b7f  call    __security_check_cookie
0x180180b84  lea     r11, [rsp+0E8h+var_8]
0x180180b8c  mov     rbx, [r11+10h]
0x180180b90  mov     rsi, [r11+20h]
0x180180b94  mov     rsp, r11
0x180180b97  pop     rdi
0x180180b98  retn
```
