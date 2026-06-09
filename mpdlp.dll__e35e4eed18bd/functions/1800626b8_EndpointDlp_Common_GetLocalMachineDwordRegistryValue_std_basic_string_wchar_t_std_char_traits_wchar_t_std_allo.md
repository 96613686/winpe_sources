# EndpointDlp::Common::GetLocalMachineDwordRegistryValue(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong &)

- ea: `0x1800626b8`
- end: `0x180062812`
- name: `?GetLocalMachineDwordRegistryValue@Common@EndpointDlp@@YAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAK@Z`
- size: `346`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801f8754`

## callees

- `0x1800068e4`
- `0x1800301a0`
- `0x1800626b8`
- `0x180063ce0`
- `0x18010cb40`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180062777`
- `ADVAPI32!RegQueryValueExW` at `0x180062777`
- `ADVAPI32!RegCloseKey` at `0x1800627f5`
- `ADVAPI32!RegCloseKey` at `0x1800627f5`
- `ADVAPI32!RegOpenKeyExW` at `0x180062704`
- `ADVAPI32!RegOpenKeyExW` at `0x180062704`

## string_xrefs

- `0x18006271d`: `src\epp\Dlp\EndpointDlp\Common\src\registry.cpp`
- `0x180062790`: `src\epp\Dlp\EndpointDlp\Common\src\registry.cpp`
- `0x18006270e`: `Failed to open registry key `
- `0x180062781`: `Failed to query registry value`
- `0x1800627bb`: `GetLocalMachineDwordRegistryValue: wrong reg data type`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall EndpointDlp::Common::GetLocalMachineDwordRegistryValue(const WCHAR *lpSubKey, __int64 a2, _DWORD *a3)
{
  unsigned int v4; // eax
  const WCHAR *v5; // rdx
  unsigned int v6; // eax
  struct EndpointDlp::TraceLoggingProvider *v7; // rax
  _DWORD *v8; // rcx
  const char *lpcbData; // [rsp+28h] [rbp-38h]
  const char *lpcbDataa; // [rsp+28h] [rbp-38h]
  __int64 v12; // [rsp+30h] [rbp-30h] BYREF
  __int64 v13; // [rsp+38h] [rbp-28h] BYREF
  DWORD Type; // [rsp+40h] [rbp-20h] BYREF
  BYTE Data[4]; // [rsp+44h] [rbp-1Ch] BYREF
  DWORD cbData; // [rsp+48h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  hKey = 0;
  if ( *((_QWORD *)lpSubKey + 3) > 7u )
    lpSubKey = *(const WCHAR **)lpSubKey;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &hKey);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x3F,
    (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\Common\\src\\registry.cpp",
    (const char *)v4,
    (unsigned int)"Failed to open registry key ",
    lpcbData);
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  v5 = (const WCHAR *)&EndpointDlp::Registry::WindowsDefender::Features::Values::DlpEnableBrowserPasteEnforcement;
  if ( (unsigned __int64)qword_180313F90 > 7 )
    v5 = EndpointDlp::Registry::WindowsDefender::Features::Values::DlpEnableBrowserPasteEnforcement;
  v6 = RegQueryValueExW(hKey, v5, 0, &Type, Data, &cbData);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x45,
    (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\Common\\src\\registry.cpp",
    (const char *)v6,
    (unsigned int)"Failed to query registry value",
    lpcbDataa);
  if ( Type == 4 )
  {
    LODWORD(v7) = *(_DWORD *)Data;
    *a3 = *(_DWORD *)Data;
  }
  else
  {
    v7 = EndpointDlp::TraceLoggingProvider::Instance();
    v8 = *(_DWORD **)v7;
    if ( **(_DWORD **)v7 > 2u )
    {
      v13 = (__int64)"GetLocalMachineDwordRegistryValue: wrong reg data type";
      LODWORD(v12) = -2147467259;
      LODWORD(v7) = _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                      (int)v8,
                      (__int64)&v12,
                      (__int64)&v13);
    }
  }
  if ( hKey )
    LODWORD(v7) = RegCloseKey(hKey);
  return (int)v7;
}

```

## disassembly

```asm
0x1800626b8  mov     [rsp-8+arg_8], rbx
0x1800626bd  push    rbp
0x1800626be  mov     rbp, rsp
0x1800626c1  sub     rsp, 60h
0x1800626c5  mov     rax, cs:__security_cookie
0x1800626cc  xor     rax, rsp
0x1800626cf  mov     [rbp+var_8], rax
0x1800626d3  mov     rbx, r8
0x1800626d6  mov     [rbp+hKey], 0
0x1800626de  cmp     qword ptr [rcx+18h], 7
0x1800626e3  jbe     short loc_1800626E8
0x1800626e5  mov     rcx, [rcx]
0x1800626e8  lea     rax, [rbp+hKey]
0x1800626ec  mov     [rsp+60h+phkResult], rax; phkResult
0x1800626f1  mov     r9d, 20119h; samDesired
0x1800626f7  xor     r8d, r8d; ulOptions
0x1800626fa  mov     rdx, rcx; lpSubKey
0x1800626fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180062704  call    cs:__imp_RegOpenKeyExW
0x18006270a  mov     rcx, [rbp+8]; this
0x18006270e  lea     rdx, aFailedToOpenRe; "Failed to open registry key "
0x180062715  mov     [rsp+60h+phkResult], rdx; unsigned int
0x18006271a  mov     r9d, eax; char *
0x18006271d  lea     r8, aSrcEppDlpEndpo_2; "src\\epp\\Dlp\\EndpointDlp\\Common\\src"...
0x180062724  mov     edx, 3Fh ; '?'; void *
0x180062729  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18006272e  mov     [rbp+Type], 0
0x180062735  mov     dword ptr [rbp+Data], 0
0x18006273c  mov     [rbp+cbData], 4
0x180062743  lea     rdx, ?DlpEnableBrowserPasteEnforcement@Values@Features@WindowsDefender@Registry@EndpointDlp@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const EndpointDlp::Registry::WindowsDefender::Features::Values::DlpEnableBrowserPasteEnforcement
0x18006274a  cmp     cs:qword_180313F90, 7
0x180062752  cmova   rdx, cs:?DlpEnableBrowserPasteEnforcement@Values@Features@WindowsDefender@Registry@EndpointDlp@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; lpValueName
0x18006275a  lea     rax, [rbp+cbData]
0x18006275e  mov     [rsp+60h+lpcbData], rax; char *
0x180062763  lea     rax, [rbp+Data]
0x180062767  mov     [rsp+60h+phkResult], rax; lpData
0x18006276c  lea     r9, [rbp+Type]; lpType
0x180062770  xor     r8d, r8d; lpReserved
0x180062773  mov     rcx, [rbp+hKey]; hKey
0x180062777  call    cs:__imp_RegQueryValueExW
0x18006277d  mov     rcx, [rbp+8]; this
0x180062781  lea     rdx, aFailedToQueryR; "Failed to query registry value"
0x180062788  mov     [rsp+60h+phkResult], rdx; unsigned int
0x18006278d  mov     r9d, eax; char *
0x180062790  lea     r8, aSrcEppDlpEndpo_2; "src\\epp\\Dlp\\EndpointDlp\\Common\\src"...
0x180062797  mov     edx, 45h ; 'E'; void *
0x18006279c  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800627a1  cmp     [rbp+Type], 4
0x1800627a5  jnz     short loc_1800627AE
0x1800627a7  mov     eax, dword ptr [rbp+Data]
0x1800627aa  mov     [rbx], eax
0x1800627ac  jmp     short loc_1800627EC
0x1800627ae  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x1800627b3  mov     rcx, [rax]; int
0x1800627b6  cmp     dword ptr [rcx], 2
0x1800627b9  jbe     short loc_1800627EC
0x1800627bb  lea     rax, aGetlocalmachin; "GetLocalMachineDwordRegistryValue: wron"...
0x1800627c2  mov     [rbp+var_28], rax
0x1800627c6  mov     dword ptr [rbp+var_30], 80004005h
0x1800627cd  lea     rax, [rbp+var_28]
0x1800627d1  mov     [rsp+60h+lpcbData], rax; __int64
0x1800627d6  lea     rax, [rbp+var_30]
0x1800627da  mov     [rsp+60h+phkResult], rax; __int64
0x1800627df  lea     rdx, word_1802C4D76
0x1800627e6  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800627eb  nop
0x1800627ec  mov     rcx, [rbp+hKey]; hKey
0x1800627f0  test    rcx, rcx
0x1800627f3  jz      short loc_1800627FB
0x1800627f5  call    cs:__imp_RegCloseKey
0x1800627fb  mov     rcx, [rbp+var_8]
0x1800627ff  xor     rcx, rsp; StackCookie
0x180062802  call    __security_check_cookie
0x180062807  mov     rbx, [rsp+60h+arg_8]
0x18006280c  add     rsp, 60h
0x180062810  pop     rbp
0x180062811  retn
```
