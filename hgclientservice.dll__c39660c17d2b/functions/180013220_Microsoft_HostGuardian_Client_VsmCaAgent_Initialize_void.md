# Microsoft::HostGuardian::Client::VsmCaAgent::Initialize(void)

- ea: `0x180013220`
- end: `0x18001342f`
- name: `?Initialize@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXXZ`
- size: `527`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::VsmCaAgent *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800125f4`

## callees

- `0x180001770`
- `0x1800077a0`
- `0x1800087a4`
- `0x180013220`
- `0x180013954`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800133b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800133b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013243`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013243`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001340c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001340c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800133f5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800133f5`

## string_xrefs

- `0x18001341d`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`
- `0x18001334c`: `StartCaTrustletMonitorThread succeed.`
- `0x180013386`: `Initialize CaAgent succeed.`
- `0x180013319`: `CaTrustletMonitorThread is running`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::VsmCaAgent::Initialize(
        Microsoft::HostGuardian::Client::VsmCaAgent *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // r8
  DWORD LastError; // eax
  unsigned int dwCreationFlags; // [rsp+20h] [rbp-68h]
  _BYTE v11[16]; // [rsp+38h] [rbp-50h] BYREF
  const wchar_t *v12; // [rsp+48h] [rbp-40h]
  __int64 v13; // [rsp+50h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
  {
    v12 = L"Initialize lock...";
    v13 = 38;
    McGenEventWrite_EventWriteTransfer(v3, ServiceDebugInformational, v4, 2, v11);
    if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
    {
      v12 = L"Set Exit Signal to FALSE";
      v13 = 50;
      McGenEventWrite_EventWriteTransfer(v5, ServiceDebugInformational, v6, 2, v11);
    }
  }
  *((_BYTE *)this + 48) = 0;
  Microsoft::HostGuardian::Client::VsmCaAgent::StartCaTrustlet(this);
  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
  {
    v12 = L"StartCaTrustlet succeed.";
    v13 = 50;
    McGenEventWrite_EventWriteTransfer(v7, ServiceDebugInformational, v8, 2, v11);
  }
  if ( *((_QWORD *)this + 5) )
  {
    if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) == 0 )
      goto LABEL_11;
    v12 = L"CaTrustletMonitorThread is running";
    v13 = 70;
    McGenEventWrite_EventWriteTransfer(v7, ServiceDebugInformational, v8, 2, v11);
  }
  else
  {
    *((_QWORD *)this + 5) = CreateThread(
                              0,
                              0,
                              Microsoft::HostGuardian::Client::VsmCaAgent::CaTrustletMonitorThread,
                              0,
                              0,
                              0);
    if ( !*((_QWORD *)this + 5) )
    {
      LastError = GetLastError();
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x16A,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
        (const char *)LastError,
        dwCreationFlags);
    }
  }
  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
  {
    v12 = L"StartCaTrustletMonitorThread succeed.";
    v13 = 76;
    McGenEventWrite_EventWriteTransfer(v7, ServiceDebugInformational, v8, 2, v11);
  }
LABEL_11:
  Microsoft::HostGuardian::Client::VsmCaAgent::s_initialized = 1;
  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
  {
    v12 = L"Initialize CaAgent succeed.";
    v13 = 56;
    McGenEventWrite_EventWriteTransfer(v7, ServiceDebugInformational, v8, 2, v11);
  }
  if ( v2 )
    LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x180013220  push    rbx
0x180013222  push    rsi
0x180013223  push    rdi
0x180013224  push    r15
0x180013226  sub     rsp, 68h
0x18001322a  mov     rax, cs:__security_cookie
0x180013231  xor     rax, rsp
0x180013234  mov     [rsp+88h+var_30], rax
0x180013239  mov     rbx, rcx
0x18001323c  lea     rdi, [rcx+38h]
0x180013240  mov     rcx, rdi; lpCriticalSection
0x180013243  call    cs:__imp_EnterCriticalSection
0x180013249  mov     [rsp+88h+var_58], rdi
0x18001324e  mov     eax, cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits
0x180013254  lea     r15, ServiceDebugInformational
0x18001325b  mov     esi, 2
0x180013260  test    sil, al
0x180013263  jz      short loc_1800132C4
0x180013265  lea     rax, aInitializeLock; "Initialize lock..."
0x18001326c  mov     [rsp+88h+var_40], rax
0x180013271  mov     [rsp+88h+var_38], 26h ; '&'
0x18001327a  lea     rax, [rsp+88h+var_50]
0x18001327f  mov     qword ptr [rsp+88h+dwCreationFlags], rax
0x180013284  mov     r9d, esi
0x180013287  mov     rdx, r15
0x18001328a  call    McGenEventWrite_EventWriteTransfer
0x18001328f  mov     eax, cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits
0x180013295  test    sil, al
0x180013298  jz      short loc_1800132C4
0x18001329a  lea     rax, aSetExitSignalT; "Set Exit Signal to FALSE"
0x1800132a1  mov     [rsp+88h+var_40], rax
0x1800132a6  mov     [rsp+88h+var_38], 32h ; '2'
0x1800132af  lea     rax, [rsp+88h+var_50]
0x1800132b4  mov     qword ptr [rsp+88h+dwCreationFlags], rax
0x1800132b9  mov     r9d, esi
0x1800132bc  mov     rdx, r15
0x1800132bf  call    McGenEventWrite_EventWriteTransfer
0x1800132c4  mov     byte ptr [rbx+30h], 0
0x1800132c8  mov     rcx, rbx; this
0x1800132cb  call    ?StartCaTrustlet@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXXZ; Microsoft::HostGuardian::Client::VsmCaAgent::StartCaTrustlet(void)
0x1800132d0  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, sil
0x1800132d7  jz      short loc_180013303
0x1800132d9  lea     rax, aStartcatrustle; "StartCaTrustlet succeed."
0x1800132e0  mov     [rsp+88h+var_40], rax
0x1800132e5  mov     [rsp+88h+var_38], 32h ; '2'
0x1800132ee  lea     rax, [rsp+88h+var_50]
0x1800132f3  mov     qword ptr [rsp+88h+dwCreationFlags], rax
0x1800132f8  mov     r9d, esi
0x1800132fb  mov     rdx, r15
0x1800132fe  call    McGenEventWrite_EventWriteTransfer
0x180013303  mov     rax, [rbx+28h]
0x180013307  test    rax, rax
0x18001330a  jz      loc_1800133D6
0x180013310  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, sil
0x180013317  jz      short loc_180013376
0x180013319  lea     rax, aCatrustletmoni_0; "CaTrustletMonitorThread is running"
0x180013320  mov     [rsp+88h+var_40], rax
0x180013325  mov     [rsp+88h+var_38], 46h ; 'F'
0x18001332e  lea     rax, [rsp+88h+var_50]
0x180013333  mov     qword ptr [rsp+88h+dwCreationFlags], rax
0x180013338  mov     r9d, esi
0x18001333b  mov     rdx, r15
0x18001333e  call    McGenEventWrite_EventWriteTransfer
0x180013343  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, sil
0x18001334a  jz      short loc_180013376
0x18001334c  lea     rax, aStartcatrustle_0; "StartCaTrustletMonitorThread succeed."
0x180013353  mov     [rsp+88h+var_40], rax
0x180013358  mov     [rsp+88h+var_38], 4Ch ; 'L'
0x180013361  lea     rax, [rsp+88h+var_50]
0x180013366  mov     qword ptr [rsp+88h+dwCreationFlags], rax
0x18001336b  mov     r9d, esi
0x18001336e  mov     rdx, r15
0x180013371  call    McGenEventWrite_EventWriteTransfer
0x180013376  mov     cs:?s_initialized@VsmCaAgent@Client@HostGuardian@Microsoft@@0_NA, 1; bool Microsoft::HostGuardian::Client::VsmCaAgent::s_initialized
0x18001337d  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, sil
0x180013384  jz      short loc_1800133B1
0x180013386  lea     rax, aInitializeCaag; "Initialize CaAgent succeed."
0x18001338d  mov     [rsp+88h+var_40], rax
0x180013392  mov     [rsp+88h+var_38], 38h ; '8'
0x18001339b  lea     rax, [rsp+88h+var_50]
0x1800133a0  mov     qword ptr [rsp+88h+dwCreationFlags], rax
0x1800133a5  mov     r9d, esi
0x1800133a8  mov     rdx, r15
0x1800133ab  call    McGenEventWrite_EventWriteTransfer
0x1800133b0  nop
0x1800133b1  test    rdi, rdi
0x1800133b4  jz      short loc_1800133BF
0x1800133b6  mov     rcx, rdi; lpCriticalSection
0x1800133b9  call    cs:__imp_LeaveCriticalSection
0x1800133bf  mov     rcx, [rsp+88h+var_30]
0x1800133c4  xor     rcx, rsp; StackCookie
0x1800133c7  call    __security_check_cookie
0x1800133cc  add     rsp, 68h
0x1800133d0  pop     r15
0x1800133d2  pop     rdi
0x1800133d3  pop     rsi
0x1800133d4  pop     rbx
0x1800133d5  retn
0x1800133d6  mov     [rsp+88h+lpThreadId], 0; lpThreadId
0x1800133df  mov     [rsp+88h+dwCreationFlags], 0; unsigned int
0x1800133e7  xor     r9d, r9d; lpParameter
0x1800133ea  lea     r8, ?CaTrustletMonitorThread@VsmCaAgent@Client@HostGuardian@Microsoft@@CAKPEAX@Z; lpStartAddress
0x1800133f1  xor     edx, edx; dwStackSize
0x1800133f3  xor     ecx, ecx; lpThreadAttributes
0x1800133f5  call    cs:__imp_CreateThread
0x1800133fb  mov     [rbx+28h], rax
0x1800133ff  mov     rax, [rbx+28h]
0x180013403  test    rax, rax
0x180013406  jnz     loc_180013343
0x18001340c  call    cs:__imp_GetLastError
0x180013412  mov     rcx, [rsp+88h]; this
0x18001341a  mov     r9d, eax; char *
0x18001341d  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x180013424  mov     edx, 16Ah; void *
0x180013429  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
