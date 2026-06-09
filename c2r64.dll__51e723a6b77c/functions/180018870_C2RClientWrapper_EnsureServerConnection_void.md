# C2RClientWrapper::EnsureServerConnection(void)

- ea: `0x180018870`
- end: `0x1800189ff`
- name: `?EnsureServerConnection@C2RClientWrapper@@UEAA_NXZ`
- size: `399`
- prototype: `bool __fastcall(C2RClientWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x18001bd80`

## callees

- `0x180009488`
- `0x18000aa64`
- `0x18000c0a4`
- `0x18000c2dc`
- `0x180018870`
- `0x180018f00`
- `0x180018f4c`
- `0x1800338d0`
- `0x1800392b4`
- `0x18003e690`
- `0x180136a40`
- `0x180136b54`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180018996`
- `KERNEL32!GetLastError` at `0x180018996`
- `ADVAPI32!OpenServiceW` at `0x18001893d`
- `ADVAPI32!OpenServiceW` at `0x18001893d`
- `ADVAPI32!CloseServiceHandle` at `0x18001898a`
- `ADVAPI32!CloseServiceHandle` at `0x18001898a`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char __fastcall C2RClientWrapper::EnsureServerConnection(C2RClientWrapper *this)
{
  __int64 *RpcClient; // rax
  unsigned int v3; // edx
  unsigned int IsListening; // ebx
  bool v5; // r8
  bool v6; // di
  const WCHAR *v8; // rdx
  bool v9; // zf
  bool v10; // bl
  int v11; // edx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  __int64 *v15; // rax
  std::_Ref_count_base *v16[2]; // [rsp+48h] [rbp-19h] BYREF
  SC_HANDLE hSCManager; // [rsp+58h] [rbp-9h] BYREF
  SC_HANDLE hSCObject; // [rsp+60h] [rbp-1h]
  LPCWSTR lpServiceName[3]; // [rsp+88h] [rbp+27h] BYREF
  unsigned __int64 v20; // [rsp+A0h] [rbp+3Fh]

  RpcClient = C2RClientWrapper::get_RpcClient((__int64)this, (__int64 *)v16);
  IsListening = EnsureServerIsListening(*(RPC_BINDING_HANDLE *)*RpcClient, 0x2710u);
  v6 = 0;
  if ( v16[1] )
    std::_Ref_count_base::_Decref(v16[1]);
  *(__m128i *)v16 = _mm_load_si128((const __m128i *)&_xmm);
  if ( !IsListening )
    return 1;
  OService::OService((OService *)&hSCManager, v3, v5);
  std::wstring::wstring(lpServiceName, L"ClickToRunSvc");
  if ( hSCObject )
  {
    CloseServiceHandle(hSCObject);
    hSCObject = 0;
  }
  v8 = (const WCHAR *)lpServiceName;
  if ( v20 > 7 )
    v8 = lpServiceName[0];
  hSCObject = OpenServiceW(hSCManager, v8, 0x10u);
  v9 = hSCObject == 0;
  if ( !hSCObject )
  {
    LODWORD(v16[0]) = GetLastError();
    Mso::Logging::MsoSendTraceTag<std::wstring,int>(v12, v11, v13, v14);
    v9 = hSCObject == 0;
  }
  v10 = !v9;
  std::wstring::_Tidy_deallocate(lpServiceName);
  v16[0] = (std::_Ref_count_base *)lpServiceName;
  lpServiceName[0] = (LPCWSTR)19937;
  lpServiceName[2] = 0;
  v20 = 15;
  if ( v10 && OService::StartService((OService *)&hSCManager) )
  {
    v15 = C2RClientWrapper::get_RpcClient((__int64)this, (__int64 *)v16);
    v6 = EnsureServerIsListening(*(RPC_BINDING_HANDLE *)*v15, 0x7530u) == 0;
    std::shared_ptr<C2R::SettingValidator>::~shared_ptr<C2R::SettingValidator>(v16);
  }
  OService::~OService((OService *)&hSCManager);
  return v6;
}

```

## disassembly

```asm
0x180018870  mov     rax, rsp
0x180018873  mov     [rax+10h], rbx
0x180018877  mov     [rax+18h], rsi
0x18001887b  mov     [rax+20h], rdi
0x18001887f  push    rbp
0x180018880  lea     rbp, [rax-5Fh]
0x180018884  sub     rsp, 0B0h
0x18001888b  mov     rax, cs:__security_cookie
0x180018892  xor     rax, rsp
0x180018895  mov     [rbp+57h+var_10], rax
0x180018899  mov     rsi, rcx
0x18001889c  lea     rdx, [rbp+57h+var_70]
0x1800188a0  call    ?get_RpcClient@C2RClientWrapper@@AEAA?AV?$shared_ptr@VORpcClient@@@std@@XZ; C2RClientWrapper::get_RpcClient(void)
0x1800188a5  nop
0x1800188a6  mov     rcx, [rax]
0x1800188a9  mov     edx, 2710h; unsigned int
0x1800188ae  mov     rcx, [rcx]; Binding
0x1800188b1  call    ?EnsureServerIsListening@@YAKPEAXK@Z; EnsureServerIsListening(void *,ulong)
0x1800188b6  mov     ebx, eax
0x1800188b8  mov     rcx, [rbp+57h+var_70+8]; this
0x1800188bc  xor     edi, edi
0x1800188be  test    rcx, rcx
0x1800188c1  jz      short loc_1800188C9
0x1800188c3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800188c8  nop
0x1800188c9  movdqa  xmm0, cs:__xmm@0000000000004de10000000000004de1
0x1800188d1  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x1800188d6  test    ebx, ebx
0x1800188d8  jnz     short loc_180018901
0x1800188da  mov     al, 1
0x1800188dc  mov     rcx, [rbp+57h+var_10]
0x1800188e0  xor     rcx, rsp; StackCookie
0x1800188e3  call    __security_check_cookie
0x1800188e8  lea     r11, [rsp+0B0h+var_s0]
0x1800188f0  mov     rbx, [r11+18h]
0x1800188f4  mov     rsi, [r11+20h]
0x1800188f8  mov     rdi, [r11+28h]
0x1800188fc  mov     rsp, r11
0x1800188ff  pop     rbp
0x180018900  retn
0x180018901  lea     rcx, [rbp+57h+hSCManager]; this
0x180018905  call    ??0OService@@QEAA@K_N@Z; OService::OService(ulong,bool)
0x18001890a  nop
0x18001890b  lea     rdx, aClicktorunsvc; "ClickToRunSvc"
0x180018912  lea     rcx, [rbp+57h+lpServiceName]
0x180018916  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001891b  nop
0x18001891c  mov     rcx, [rbp+57h+hSCObject]; hSCObject
0x180018920  test    rcx, rcx
0x180018923  jnz     short loc_18001898A
0x180018925  lea     rdx, [rbp+57h+lpServiceName]
0x180018929  cmp     [rbp+57h+var_18], 7
0x18001892e  cmova   rdx, [rbp+57h+lpServiceName]; lpServiceName
0x180018933  mov     r8d, 10h; dwDesiredAccess
0x180018939  mov     rcx, [rbp+57h+hSCManager]; hSCManager
0x18001893d  call    cs:__imp_OpenServiceW
0x180018943  mov     [rbp+57h+hSCObject], rax
0x180018947  test    rax, rax
0x18001894a  jz      short loc_180018996
0x18001894c  setnz   bl
0x18001894f  lea     rcx, [rbp+57h+lpServiceName]
0x180018953  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018958  nop
0x180018959  lea     rax, [rbp+57h+lpServiceName]
0x18001895d  mov     [rbp+57h+var_70], rax
0x180018961  mov     [rbp+57h+lpServiceName], 4DE1h
0x180018969  mov     [rbp+57h+var_20], rdi
0x18001896d  mov     [rbp+57h+var_18], 0Fh
0x180018975  test    bl, bl
0x180018977  jnz     short loc_1800189BF
0x180018979  lea     rcx, [rbp+57h+hSCManager]; this
0x18001897d  call    ??1OService@@QEAA@XZ; OService::~OService(void)
0x180018982  mov     al, dil
0x180018985  jmp     loc_1800188DC
0x18001898a  call    cs:__imp_CloseServiceHandle
0x180018990  mov     [rbp+57h+hSCObject], rdi
0x180018994  jmp     short loc_180018925
0x180018996  call    cs:__imp_GetLastError
0x18001899c  mov     dword ptr [rbp+57h+var_70], eax
0x18001899f  lea     rax, [rbp+57h+var_70]
0x1800189a3  mov     [rsp+0B0h+var_80], rax
0x1800189a8  lea     rax, [rbp+57h+lpServiceName]
0x1800189ac  mov     [rsp+0B0h+var_88], rax
0x1800189b1  call    ??$MsoSendTraceTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@H@Logging@Mso@@YAXKW4Category@01@W4Severity@01@W4DataCategories@01@PEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBH@Z; Mso::Logging::MsoSendTraceTag<std::wstring,int>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,std::wstring const &,int const &)
0x1800189b6  mov     rax, [rbp+57h+hSCObject]
0x1800189ba  test    rax, rax
0x1800189bd  jmp     short loc_18001894C
0x1800189bf  lea     rcx, [rbp+57h+hSCManager]; this
0x1800189c3  call    ?StartService@OService@@QEAA_NXZ; OService::StartService(void)
0x1800189c8  test    al, al
0x1800189ca  jz      short loc_180018979
0x1800189cc  lea     rdx, [rbp+57h+var_70]
0x1800189d0  mov     rcx, rsi
0x1800189d3  call    ?get_RpcClient@C2RClientWrapper@@AEAA?AV?$shared_ptr@VORpcClient@@@std@@XZ; C2RClientWrapper::get_RpcClient(void)
0x1800189d8  nop
0x1800189d9  mov     rcx, [rax]
0x1800189dc  mov     edx, 7530h; unsigned int
0x1800189e1  mov     rcx, [rcx]; Binding
0x1800189e4  call    ?EnsureServerIsListening@@YAKPEAXK@Z; EnsureServerIsListening(void *,ulong)
0x1800189e9  nop
0x1800189ea  test    eax, eax
0x1800189ec  setz    dil
0x1800189f0  lea     rcx, [rbp+57h+var_70]
0x1800189f4  call    ??1?$shared_ptr@VSettingValidator@C2R@@@std@@QEAA@XZ; std::shared_ptr<C2R::SettingValidator>::~shared_ptr<C2R::SettingValidator>(void)
0x1800189f9  jmp     loc_180018979
```
