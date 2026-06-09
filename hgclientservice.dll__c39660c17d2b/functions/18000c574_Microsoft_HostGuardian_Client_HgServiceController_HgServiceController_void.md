# Microsoft::HostGuardian::Client::HgServiceController::~HgServiceController(void)

- ea: `0x18000c574`
- end: `0x18000c739`
- name: `??1HgServiceController@Client@HostGuardian@Microsoft@@QEAA@XZ`
- size: `453`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::HgServiceController *__hidden this)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009300`
- `0x1800096a0`
- `0x1800096d0`

## callees

- `0x180001770`
- `0x180001bb4`
- `0x180004274`
- `0x1800077a0`
- `0x18000bd7c`
- `0x18000c1d8`
- `0x18000c574`
- `0x18000ee6c`
- `0x1800136a4`
- `0x180013a88`
- `0x180013c00`
- `0x180013ffc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c6a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c6a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c5b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c5b3`
- `CRYPT32!CertFreeCertificateContext` at `0x18000c6e8`
- `CRYPT32!CertFreeCertificateContext` at `0x18000c6e8`

## string_xrefs

- `0x18000c668`: `Uninitialize CaAgent succeed.`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::HgServiceController::~HgServiceController(
        Microsoft::HostGuardian::Client::HgServiceController *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // rcx
  struct Microsoft::HostGuardian::Client::VsmCaAgent *v6; // rsi
  __int64 v7; // r8
  RPC_BINDING_HANDLE *v8; // rax
  Microsoft::HostGuardian::Client::VsmCaAgent *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  const CERT_CONTEXT *v12; // rcx
  void *v13; // rdi
  const char *v14; // r9
  _BYTE v15[16]; // [rsp+40h] [rbp-38h] BYREF
  const wchar_t *v16; // [rsp+50h] [rbp-28h]
  __int64 v17; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  try
  {
    if ( Microsoft::HostGuardian::Client::VsmCaAgent::s_initialized )
    {
      v2 = (struct _RTL_CRITICAL_SECTION *)((char *)Microsoft::HostGuardian::Client::VsmCaAgent::Instance() + 56);
      EnterCriticalSection(v2);
      if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
      {
        v16 = L"Uninitialize lock...";
        v17 = 42;
        McGenEventWrite_EventWriteTransfer(v3, ServiceDebugInformational, v4, 2, v15);
      }
      v6 = Microsoft::HostGuardian::Client::VsmCaAgent::Instance();
      if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
      {
        v16 = L"Set Exit Signal to TRUE";
        v17 = 48;
        McGenEventWrite_EventWriteTransfer(v5, ServiceDebugInformational, v7, 2, v15);
      }
      *((_BYTE *)v6 + 48) = 1;
      v8 = (RPC_BINDING_HANDLE *)Microsoft::HostGuardian::Client::VsmCaAgent::Instance();
      Microsoft::HostGuardian::Client::VsmCaAgent::TerminateCaTrustlet(v8);
      v9 = Microsoft::HostGuardian::Client::VsmCaAgent::Instance();
      Microsoft::HostGuardian::Client::VsmCaAgent::WaitCaTrustletMonitorThreadTerminate(v9);
      Microsoft::HostGuardian::Client::VsmCaAgent::s_initialized = 0;
      if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
      {
        v16 = L"Uninitialize CaAgent succeed.";
        v17 = 60;
        McGenEventWrite_EventWriteTransfer(v10, ServiceDebugInformational, v11, 2, v15);
      }
      if ( v2 )
        LeaveCriticalSection(v2);
    }
    *((_QWORD *)this + 20) = &Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::`vftable';
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>>>>>>((char **)this + 28);
    std::list<std::pair<std::wstring const,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>>::~list<std::pair<std::wstring const,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>>((void **)this + 26);
    std::wstring::~wstring((char **)this + 21);
    v12 = (const CERT_CONTEXT *)*((_QWORD *)this + 18);
    if ( v12 )
      CertFreeCertificateContext(v12);
    v13 = (void *)*((_QWORD *)this + 17);
    if ( v13 )
    {
      Microsoft::HostGuardian::Client::CertificateCache::~CertificateCache(*((Microsoft::HostGuardian::Client::CertificateCache **)this
                                                                           + 17));
      operator delete(v13);
    }
    Microsoft::HostGuardian::Client::HgServicePlugin::~HgServicePlugin(this);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1E,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      v14);
  }
}

```

## disassembly

```asm
0x18000c574  mov     [rsp+arg_8], rbx
0x18000c579  mov     [rsp+arg_10], rsi
0x18000c57e  push    rdi
0x18000c57f  sub     rsp, 70h
0x18000c583  mov     rax, cs:__security_cookie
0x18000c58a  xor     rax, rsp
0x18000c58d  mov     [rsp+78h+var_18], rax
0x18000c592  mov     rbx, rcx
0x18000c595  mov     [rsp+78h+var_48], rcx
0x18000c59a  cmp     cs:?s_initialized@VsmCaAgent@Client@HostGuardian@Microsoft@@0_NA, 0; bool Microsoft::HostGuardian::Client::VsmCaAgent::s_initialized
0x18000c5a1  jz      loc_18000C6A9
0x18000c5a7  call    ?Instance@VsmCaAgent@Client@HostGuardian@Microsoft@@SAAEAV1234@XZ; Microsoft::HostGuardian::Client::VsmCaAgent::Instance(void)
0x18000c5ac  lea     rdi, [rax+38h]
0x18000c5b0  mov     rcx, rdi; lpCriticalSection
0x18000c5b3  call    cs:__imp_EnterCriticalSection
0x18000c5b9  mov     [rsp+78h+var_40], rdi
0x18000c5be  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 2
0x18000c5c5  jz      short loc_18000C5F8
0x18000c5c7  lea     rax, aUninitializeLo; "Uninitialize lock..."
0x18000c5ce  mov     [rsp+78h+var_28], rax
0x18000c5d3  mov     [rsp+78h+var_20], 2Ah ; '*'
0x18000c5dc  lea     rax, [rsp+78h+var_38]
0x18000c5e1  mov     [rsp+78h+var_58], rax
0x18000c5e6  mov     r9d, 2
0x18000c5ec  lea     rdx, ServiceDebugInformational
0x18000c5f3  call    McGenEventWrite_EventWriteTransfer
0x18000c5f8  call    ?Instance@VsmCaAgent@Client@HostGuardian@Microsoft@@SAAEAV1234@XZ; Microsoft::HostGuardian::Client::VsmCaAgent::Instance(void)
0x18000c5fd  mov     rsi, rax
0x18000c600  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 2
0x18000c607  jz      short loc_18000C63A
0x18000c609  lea     rax, aSetExitSignalT_0; "Set Exit Signal to TRUE"
0x18000c610  mov     [rsp+78h+var_28], rax
0x18000c615  mov     [rsp+78h+var_20], 30h ; '0'
0x18000c61e  lea     rax, [rsp+78h+var_38]
0x18000c623  mov     [rsp+78h+var_58], rax
0x18000c628  mov     r9d, 2
0x18000c62e  lea     rdx, ServiceDebugInformational
0x18000c635  call    McGenEventWrite_EventWriteTransfer
0x18000c63a  mov     byte ptr [rsi+30h], 1
0x18000c63e  call    ?Instance@VsmCaAgent@Client@HostGuardian@Microsoft@@SAAEAV1234@XZ; Microsoft::HostGuardian::Client::VsmCaAgent::Instance(void)
0x18000c643  mov     rcx, rax; Binding
0x18000c646  call    ?TerminateCaTrustlet@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXXZ; Microsoft::HostGuardian::Client::VsmCaAgent::TerminateCaTrustlet(void)
0x18000c64b  call    ?Instance@VsmCaAgent@Client@HostGuardian@Microsoft@@SAAEAV1234@XZ; Microsoft::HostGuardian::Client::VsmCaAgent::Instance(void)
0x18000c650  mov     rcx, rax; this
0x18000c653  call    ?WaitCaTrustletMonitorThreadTerminate@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXXZ; Microsoft::HostGuardian::Client::VsmCaAgent::WaitCaTrustletMonitorThreadTerminate(void)
0x18000c658  mov     cs:?s_initialized@VsmCaAgent@Client@HostGuardian@Microsoft@@0_NA, 0; bool Microsoft::HostGuardian::Client::VsmCaAgent::s_initialized
0x18000c65f  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 2
0x18000c666  jz      short loc_18000C69A
0x18000c668  lea     rax, aUninitializeCa; "Uninitialize CaAgent succeed."
0x18000c66f  mov     [rsp+78h+var_28], rax
0x18000c674  mov     [rsp+78h+var_20], 3Ch ; '<'
0x18000c67d  lea     rax, [rsp+78h+var_38]
0x18000c682  mov     [rsp+78h+var_58], rax
0x18000c687  mov     r9d, 2
0x18000c68d  lea     rdx, ServiceDebugInformational
0x18000c694  call    McGenEventWrite_EventWriteTransfer
0x18000c699  nop
0x18000c69a  test    rdi, rdi
0x18000c69d  jz      short loc_18000C6A9
0x18000c69f  mov     rcx, rdi; lpCriticalSection
0x18000c6a2  call    cs:__imp_LeaveCriticalSection
0x18000c6a8  nop
0x18000c6a9  lea     rax, ??_7HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@6B@; const Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::`vftable'
0x18000c6b0  mov     [rbx+0A0h], rax
0x18000c6b7  lea     rcx, [rbx+0E0h]
0x18000c6be  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>>>>>>(void)
0x18000c6c3  lea     rcx, [rbx+0D0h]
0x18000c6ca  call    ??1?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::wstring const,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>>::~list<std::pair<std::wstring const,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>>(void)
0x18000c6cf  lea     rcx, [rbx+0A8h]
0x18000c6d6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c6db  nop
0x18000c6dc  mov     rcx, [rbx+90h]; pCertContext
0x18000c6e3  test    rcx, rcx
0x18000c6e6  jz      short loc_18000C6EF
0x18000c6e8  call    cs:__imp_CertFreeCertificateContext
0x18000c6ee  nop
0x18000c6ef  mov     rdi, [rbx+88h]
0x18000c6f6  test    rdi, rdi
0x18000c6f9  jz      short loc_18000C711
0x18000c6fb  mov     rcx, rdi; this
0x18000c6fe  call    ??1CertificateCache@Client@HostGuardian@Microsoft@@QEAA@XZ; Microsoft::HostGuardian::Client::CertificateCache::~CertificateCache(void)
0x18000c703  mov     edx, 30h ; '0'
0x18000c708  mov     rcx, rdi; Block
0x18000c70b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c710  nop
0x18000c711  mov     rcx, rbx; this
0x18000c714  call    ??1HgServicePlugin@Client@HostGuardian@Microsoft@@UEAA@XZ; Microsoft::HostGuardian::Client::HgServicePlugin::~HgServicePlugin(void)
0x18000c719  nop
0x18000c71a  mov     rcx, [rsp+78h+var_18]
0x18000c71f  xor     rcx, rsp; StackCookie
0x18000c722  call    __security_check_cookie
0x18000c727  lea     r11, [rsp+78h+var_8]
0x18000c72c  mov     rbx, [r11+18h]
0x18000c730  mov     rsi, [r11+20h]
0x18000c734  mov     rsp, r11
0x18000c737  pop     rdi
0x18000c738  retn
```
