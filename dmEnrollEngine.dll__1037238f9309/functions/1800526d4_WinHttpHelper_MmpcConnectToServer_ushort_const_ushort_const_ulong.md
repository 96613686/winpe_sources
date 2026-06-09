# WinHttpHelper::MmpcConnectToServer(ushort const *,ushort const *,ulong)

- ea: `0x1800526d4`
- end: `0x18005288c`
- name: `?MmpcConnectToServer@WinHttpHelper@@QEAAJPEBG0K@Z`
- size: `440`
- prototype: `int(WinHttpHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180052e0c`

## callees

- `0x1800140d0`
- `0x18003b170`
- `0x1800424fc`
- `0x1800526d4`
- `0x180053d20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005278a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800527a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005278a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800527a1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800527fc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800527fc`
- `WINHTTP!WinHttpConnect` at `0x180052842`
- `WINHTTP!WinHttpConnect` at `0x180052842`
- `WINHTTP!WinHttpOpen` at `0x180052773`
- `WINHTTP!WinHttpOpen` at `0x180052773`
- `WINHTTP!WinHttpSetTimeouts` at `0x180052817`
- `WINHTTP!WinHttpSetTimeouts` at `0x180052817`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinHttpHelper::MmpcConnectToServer(
        HINTERNET *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  int LastError; // ebx
  HINTERNET v9; // rax
  HINTERNET v10; // rax
  int nSendTimeout; // [rsp+40h] [rbp-20h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-1Ch] BYREF
  DWORD pdwType; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v15[2]; // [rsp+50h] [rbp-10h] BYREF
  int v16; // [rsp+90h] [rbp+30h] BYREF

  v16 = 0;
  v15[0] = "WinHttpHelper::MmpcConnectToServer";
  v15[1] = &v16;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, ConnectingToServerEvent, a3);
  if ( !a3 )
  {
    LastError = -2147024809;
LABEL_17:
    v16 = LastError;
    goto LABEL_18;
  }
  if ( !a2
    || (LastError = AutoImpersonate::ImpersonateSID((AutoImpersonate *)(this + 5), a2), v16 = LastError, LastError >= 0) )
  {
    v9 = WinHttpOpen(L"MMP-C Discovery Client", 4u, 0, 0, 0);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      this,
      v9);
    if ( !*this )
      goto LABEL_8;
    nSendTimeout = 0;
    pcbData = 4;
    pdwType = 0;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Enrollments",
            L"HTTPTimeout",
            0x10u,
            &pdwType,
            &nSendTimeout,
            &pcbData)
      && !WinHttpSetTimeouts(*this, 0, nSendTimeout, nSendTimeout, nSendTimeout) )
    {
      goto LABEL_8;
    }
    if ( a4 > 0xFFFF )
    {
      LastError = -2147024362;
      goto LABEL_17;
    }
    v16 = 0;
    v10 = WinHttpConnect(*this, a3, a4, 0);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      this + 1,
      v10);
    if ( !this[1] )
    {
LABEL_8:
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80190000;
      else
        LastError = GetLastError();
      goto LABEL_17;
    }
    LastError = v16;
  }
LABEL_18:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v15, (__int64)a2);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800526d4  mov     [rsp-18h+arg_0], rbx
0x1800526d9  mov     [rsp-18h+arg_8], rsi
0x1800526de  push    rbp
0x1800526df  push    rdi
0x1800526e0  push    r14
0x1800526e2  mov     rbp, rsp
0x1800526e5  sub     rsp, 60h
0x1800526e9  mov     r14d, r9d
0x1800526ec  mov     rsi, r8
0x1800526ef  mov     rbx, rdx
0x1800526f2  mov     rdi, rcx
0x1800526f5  mov     [rbp+arg_10], 0
0x1800526fc  lea     rax, aWinhttphelperM; "WinHttpHelper::MmpcConnectToServer"
0x180052703  mov     [rbp+var_10], rax
0x180052707  lea     rax, [rbp+arg_10]
0x18005270b  mov     [rbp+var_8], rax
0x18005270f  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x180052716  jz      short loc_18005272B
0x180052718  lea     rdx, ConnectingToServerEvent
0x18005271f  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180052726  call    McTemplateU0z_EventWriteTransfer
0x18005272b  test    rsi, rsi
0x18005272e  jnz     short loc_18005273A
0x180052730  mov     ebx, 80070057h
0x180052735  jmp     loc_180052869
0x18005273a  test    rbx, rbx
0x18005273d  jz      short loc_180052758
0x18005273f  lea     rcx, [rdi+28h]; this
0x180052743  mov     rdx, rbx; unsigned __int16 *
0x180052746  call    ?ImpersonateSID@AutoImpersonate@@QEAAJPEBG@Z; AutoImpersonate::ImpersonateSID(ushort const *)
0x18005274b  mov     ebx, eax
0x18005274d  mov     [rbp+arg_10], eax
0x180052750  test    eax, eax
0x180052752  js      loc_18005286C
0x180052758  mov     [rsp+60h+dwFlags], 0; dwFlags
0x180052760  xor     r9d, r9d; pszProxyBypassW
0x180052763  xor     r8d, r8d; pszProxyW
0x180052766  lea     ebx, [r9+4]
0x18005276a  mov     edx, ebx; dwAccessType
0x18005276c  lea     rcx, aMmpCDiscoveryC; "MMP-C Discovery Client"
0x180052773  call    cs:__imp_WinHttpOpen
0x180052779  mov     rdx, rax
0x18005277c  mov     rcx, rdi
0x18005277f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180052784  cmp     qword ptr [rdi], 0
0x180052788  jnz     short loc_1800527B5
0x18005278a  call    cs:__imp_GetLastError
0x180052790  test    eax, eax
0x180052792  jg      short loc_1800527A1
0x180052794  call    cs:__imp_GetLastError
0x18005279a  mov     ebx, eax
0x18005279c  jmp     loc_180052869
0x1800527a1  call    cs:__imp_GetLastError
0x1800527a7  movzx   ebx, ax
0x1800527aa  or      ebx, 80190000h
0x1800527b0  jmp     loc_180052869
0x1800527b5  mov     [rbp+nSendTimeout], 0
0x1800527bc  mov     [rbp+var_1C], ebx
0x1800527bf  mov     [rbp+pdwType], 0
0x1800527c6  lea     rax, [rbp+var_1C]
0x1800527ca  mov     [rsp+60h+pcbData], rax; pcbData
0x1800527cf  lea     rax, [rbp+nSendTimeout]
0x1800527d3  mov     [rsp+60h+pvData], rax; pvData
0x1800527d8  lea     rax, [rbp+pdwType]
0x1800527dc  mov     qword ptr [rsp+60h+dwFlags], rax; pdwType
0x1800527e1  mov     r9d, 10h; dwFlags
0x1800527e7  lea     r8, aHttptimeout; "HTTPTimeout"
0x1800527ee  lea     rdx, SubKey; "Software\\Microsoft\\Enrollments"
0x1800527f5  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800527fc  call    cs:__imp_RegGetValueW
0x180052802  test    eax, eax
0x180052804  jnz     short loc_180052825
0x180052806  mov     r8d, [rbp+nSendTimeout]; nConnectTimeout
0x18005280a  mov     [rsp+60h+dwFlags], r8d; nReceiveTimeout
0x18005280f  mov     r9d, r8d; nSendTimeout
0x180052812  xor     edx, edx; nResolveTimeout
0x180052814  mov     rcx, [rdi]; hInternet
0x180052817  call    cs:__imp_WinHttpSetTimeouts
0x18005281d  test    eax, eax
0x18005281f  jz      loc_18005278A
0x180052825  cmp     r14d, 0FFFFh
0x18005282c  ja      short loc_180052864
0x18005282e  mov     [rbp+arg_10], 0
0x180052835  xor     r9d, r9d; dwReserved
0x180052838  movzx   r8d, r14w; nServerPort
0x18005283c  mov     rdx, rsi; pswzServerName
0x18005283f  mov     rcx, [rdi]; hSession
0x180052842  call    cs:__imp_WinHttpConnect
0x180052848  mov     rdx, rax
0x18005284b  lea     rcx, [rdi+8]
0x18005284f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180052854  cmp     qword ptr [rdi+8], 0
0x180052859  jz      loc_18005278A
0x18005285f  mov     ebx, [rbp+arg_10]
0x180052862  jmp     short loc_18005286C
0x180052864  mov     ebx, 80070216h
0x180052869  mov     [rbp+arg_10], ebx
0x18005286c  lea     rcx, [rbp+var_10]; this
0x180052870  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180052875  mov     eax, ebx
0x180052877  lea     r11, [rsp+60h+var_s0]
0x18005287c  mov     rbx, [r11+20h]
0x180052880  mov     rsi, [r11+28h]
0x180052884  mov     rsp, r11
0x180052887  pop     r14
0x180052889  pop     rdi
0x18005288a  pop     rbp
0x18005288b  retn
```
