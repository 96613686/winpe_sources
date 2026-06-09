# Microsoft::HostGuardian::Client::VsmCaAgent::CreateSecurityProcess(void)

- ea: `0x180012b44`
- end: `0x180012e3d`
- name: `?CreateSecurityProcess@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXXZ`
- size: `761`
- prototype: `void __fastcall(UCHAR *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013954`

## callees

- `0x180001770`
- `0x1800021f0`
- `0x180003e24`
- `0x180006ea4`
- `0x1800077a0`
- `0x180008760`
- `0x1800087a4`
- `0x18000a7bc`
- `0x180012b44`
- `0x180012e44`
- `0x180013d08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012d20`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012d20`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012c56`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012c56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012d3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012d3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180012c8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180012c8d`
- `bcrypt!BCryptGenRandom` at `0x180012c0b`
- `bcrypt!BCryptGenRandom` at `0x180012c0b`

## string_xrefs

- `0x180012d78`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`
- `0x180012d9e`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`
- `0x180012dc1`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`
- `0x180012dd3`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`
- `0x180012de5`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`
- `0x180012dfd`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`
- `0x180012e12`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`
- `0x180012e2b`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`
- `0x180012b83`: `CreateSecurityProcess...`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::VsmCaAgent::CreateSecurityProcess(UCHAR *this, __int64 a2, __int64 a3)
{
  _QWORD *v4; // rsi
  NTSTATUS v5; // eax
  unsigned int v6; // r8d
  int v7; // eax
  HANDLE EventW; // rbx
  const char *v9; // r9
  const char *v10; // r9
  int v11; // eax
  int v12; // eax
  DWORD v13; // eax
  const char *v14; // r9
  unsigned int v15; // eax
  int v16; // [rsp+20h] [rbp-E0h]
  unsigned int v17[2]; // [rsp+20h] [rbp-E0h]
  int v18[4]; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v19; // [rsp+48h] [rbp-B8h]
  __int64 v20; // [rsp+50h] [rbp-B0h]
  WCHAR Name[64]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v22[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR Buffer[264]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wchar_t v24[296]; // [rsp+500h] [rbp+400h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+778h] [rbp+678h]

  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
  {
    v19 = L"CreateSecurityProcess...";
    v20 = 50;
    McGenEventWrite_EventWriteTransfer(this, ServiceDebugInformational, a3, 2, v18);
  }
  memset_0(Buffer, 0, 0x208u);
  memset_0(v22, 0, 0x208u);
  memset_0(v24, 0, 0x248u);
  memset_0(Name, 0, sizeof(Name));
  v4 = this + 24;
  v5 = BCryptGenRandom(0, this + 24, 8u, 2u);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0xBC, v6, (const char *)(unsigned int)v5, v16);
  v7 = StringCchPrintfW(Name, 0x40u, L"Global\\%016llX", *v4);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
      (const char *)(unsigned int)v7,
      v16);
  EventW = CreateEventW(0, 1, 0, Name);
  if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xC8,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
      v9);
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xCA,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
      v10);
  v11 = StringCchPrintfW(v22, 0x104u, L"%s\\%s", Buffer);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
      (const char *)(unsigned int)v11,
      (int)L"vmplatformca.exe");
  *(_QWORD *)v17 = *v4;
  v12 = StringCchPrintfW(v24, 0x124u, L"%s %016llX", v22);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCC,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
      (const char *)(unsigned int)v12,
      v17[0]);
  Microsoft::HostGuardian::Client::VsmCaAgent::CreateTrustlet(
    (Microsoft::HostGuardian::Client::VsmCaAgent *)this,
    v22,
    v24);
  v13 = WaitForSingleObject(EventW, 0xEA60u);
  if ( v13 )
  {
    if ( v13 != 258 )
    {
      if ( v13 == -1 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xDD,
          (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
          v14);
      v15 = wil::verify_hresult<long>(2147549183LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDF,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
        (const char *)v15,
        v17[0]);
    }
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xDB,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
      (const char *)0x5B4,
      v17[0]);
  }
  CloseHandle(EventW);
}

```

## disassembly

```asm
0x180012b44  mov     [rsp-8+arg_8], rbx
0x180012b49  mov     [rsp-8+arg_10], rsi
0x180012b4e  push    rbp
0x180012b4f  push    rdi
0x180012b50  push    r14
0x180012b52  lea     rbp, [rsp-660h]
0x180012b5a  sub     rsp, 760h
0x180012b61  mov     rax, cs:__security_cookie
0x180012b68  xor     rax, rsp
0x180012b6b  mov     [rbp+670h+var_20], rax
0x180012b72  mov     r14, rcx
0x180012b75  mov     edi, 2
0x180012b7a  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, dil
0x180012b81  jz      short loc_180012BB1
0x180012b83  lea     rax, aCreatesecurity; "CreateSecurityProcess..."
0x180012b8a  mov     [rsp+770h+var_728], rax
0x180012b8f  mov     [rsp+770h+var_720], 32h ; '2'
0x180012b98  lea     rax, [rsp+770h+var_738]
0x180012b9d  mov     qword ptr [rsp+770h+var_750], rax; int
0x180012ba2  mov     r9d, edi
0x180012ba5  lea     rdx, ServiceDebugInformational
0x180012bac  call    McGenEventWrite_EventWriteTransfer
0x180012bb1  mov     ebx, 208h
0x180012bb6  mov     r8d, ebx; Size
0x180012bb9  xor     edx, edx; Val
0x180012bbb  lea     rcx, [rbp+670h+Buffer]; void *
0x180012bc2  call    memset_0
0x180012bc7  mov     r8d, ebx; Size
0x180012bca  xor     edx, edx; Val
0x180012bcc  lea     rcx, [rbp+670h+var_690]; void *
0x180012bd0  call    memset_0
0x180012bd5  xor     edx, edx; Val
0x180012bd7  lea     r8d, [rbx+40h]; Size
0x180012bdb  lea     rcx, [rbp+670h+var_270]; void *
0x180012be2  call    memset_0
0x180012be7  xor     edx, edx; Val
0x180012be9  mov     r8d, 80h; Size
0x180012bef  lea     rcx, [rsp+770h+Name]; void *
0x180012bf4  call    memset_0
0x180012bf9  lea     rsi, [r14+18h]
0x180012bfd  mov     r9d, edi; dwFlags
0x180012c00  mov     r8d, 8; cbBuffer
0x180012c06  mov     rdx, rsi; pbBuffer
0x180012c09  xor     ecx, ecx; hAlgorithm
0x180012c0b  call    cs:__imp_BCryptGenRandom
0x180012c11  mov     rcx, [rbp+678h]; this
0x180012c18  test    eax, eax
0x180012c1a  js      loc_180012DB0
0x180012c20  mov     r9, [rsi]
0x180012c23  lea     r8, aGlobal016llx; "Global\\%016llX"
0x180012c2a  mov     edx, 40h ; '@'; unsigned __int64
0x180012c2f  lea     rcx, [rsp+770h+Name]; wchar_t *
0x180012c34  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180012c39  mov     rcx, [rbp+678h]; this
0x180012c40  test    eax, eax
0x180012c42  js      loc_180012DBE
0x180012c48  lea     r9, [rsp+770h+Name]; lpName
0x180012c4d  xor     r8d, r8d; bInitialState
0x180012c50  lea     edx, [r8+1]; bManualReset
0x180012c54  xor     ecx, ecx; lpEventAttributes
0x180012c56  call    cs:__imp_CreateEventW
0x180012c5c  mov     rbx, rax
0x180012c5f  mov     [rsp+770h+var_740], rax
0x180012c64  mov     rcx, [rbp+678h]; this
0x180012c6b  inc     rax
0x180012c6e  test    rax, 0FFFFFFFFFFFFFFFEh
0x180012c74  jz      loc_180012DD3
0x180012c7a  mov     rdi, [rbp+678h]
0x180012c81  mov     edx, 104h; uSize
0x180012c86  lea     rcx, [rbp+670h+Buffer]; lpBuffer
0x180012c8d  call    cs:__imp_GetSystemDirectoryW
0x180012c93  test    eax, eax
0x180012c95  jz      loc_180012DE5
0x180012c9b  lea     rax, aVmplatformcaEx; "vmplatformca.exe"
0x180012ca2  mov     qword ptr [rsp+770h+var_750], rax; int
0x180012ca7  lea     r9, [rbp+670h+Buffer]
0x180012cae  lea     r8, aSS; "%s\\%s"
0x180012cb5  mov     edx, 104h; unsigned __int64
0x180012cba  lea     rcx, [rbp+670h+var_690]; wchar_t *
0x180012cbe  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180012cc3  mov     rcx, [rbp+678h]; this
0x180012cca  test    eax, eax
0x180012ccc  js      loc_180012DFA
0x180012cd2  mov     rax, [rsi]
0x180012cd5  mov     qword ptr [rsp+770h+var_750], rax; int
0x180012cda  lea     r9, [rbp+670h+var_690]
0x180012cde  lea     r8, aS016llx; "%s %016llX"
0x180012ce5  mov     edx, 124h; unsigned __int64
0x180012cea  lea     rcx, [rbp+670h+var_270]; wchar_t *
0x180012cf1  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180012cf6  mov     rcx, [rbp+678h]; this
0x180012cfd  test    eax, eax
0x180012cff  js      loc_180012E0F
0x180012d05  lea     r8, [rbp+670h+var_270]; wchar_t *
0x180012d0c  lea     rdx, [rbp+670h+var_690]; wchar_t *
0x180012d10  mov     rcx, r14; this
0x180012d13  call    ?CreateTrustlet@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXPEB_W0@Z; Microsoft::HostGuardian::Client::VsmCaAgent::CreateTrustlet(wchar_t const *,wchar_t const *)
0x180012d18  mov     edx, 0EA60h; dwMilliseconds
0x180012d1d  mov     rcx, rbx; hHandle
0x180012d20  call    cs:__imp_WaitForSingleObject
0x180012d26  test    eax, eax
0x180012d28  jz      short loc_180012D3B
0x180012d2a  cmp     eax, 102h
0x180012d2f  jz      short loc_180012D6B
0x180012d31  cmp     eax, 0FFFFFFFFh
0x180012d34  jnz     short loc_180012D8A
0x180012d36  jmp     loc_180012E24
0x180012d3b  mov     rcx, rbx; hObject
0x180012d3e  call    cs:__imp_CloseHandle
0x180012d44  mov     rcx, [rbp+670h+var_20]
0x180012d4b  xor     rcx, rsp; StackCookie
0x180012d4e  call    __security_check_cookie
0x180012d53  lea     r11, [rsp+770h+var_10]
0x180012d5b  mov     rbx, [r11+28h]
0x180012d5f  mov     rsi, [r11+30h]
0x180012d63  mov     rsp, r11
0x180012d66  pop     r14
0x180012d68  pop     rdi
0x180012d69  pop     rbp
0x180012d6a  retn
0x180012d6b  mov     rcx, [rbp+678h]; this
0x180012d72  mov     r9d, 5B4h; char *
0x180012d78  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x180012d7f  mov     edx, 0DBh; void *
0x180012d84  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180012d8a  mov     ecx, 8000FFFFh
0x180012d8f  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180012d94  mov     r9d, eax; char *
0x180012d97  mov     rcx, [rbp+678h]; this
0x180012d9e  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x180012da5  mov     edx, 0DFh; void *
0x180012daa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012db0  mov     r9d, eax; char *
0x180012db3  mov     edx, 0BCh; void *
0x180012db8  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180012dbe  mov     r9d, eax; char *
0x180012dc1  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x180012dc8  mov     edx, 0C1h; void *
0x180012dcd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012dd3  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x180012dda  mov     edx, 0C8h; void *
0x180012ddf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180012de5  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x180012dec  mov     edx, 0CAh; void *
0x180012df1  mov     rcx, rdi; this
0x180012df4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180012dfa  mov     r9d, eax; char *
0x180012dfd  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x180012e04  mov     edx, 0CBh; void *
0x180012e09  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012e0f  mov     r9d, eax; char *
0x180012e12  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x180012e19  mov     edx, 0CCh; void *
0x180012e1e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012e24  mov     rcx, [rbp+678h]; this
0x180012e2b  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x180012e32  mov     edx, 0DDh; void *
0x180012e37  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
