# Microsoft::HostGuardian::Client::VsmCaAgent::StartCaTrustlet(void)

- ea: `0x180013954`
- end: `0x180013a82`
- name: `?StartCaTrustlet@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXXZ`
- size: `302`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::VsmCaAgent *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012890`
- `0x180013220`

## callees

- `0x180001770`
- `0x180003e24`
- `0x1800077a0`
- `0x180007878`
- `0x180008760`
- `0x1800127f4`
- `0x180012b44`
- `0x180013954`
- `0x180013a88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013a1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013a1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013977`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013977`

## string_xrefs

- `0x180013a70`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::VsmCaAgent::StartCaTrustlet(
        Microsoft::HostGuardian::Client::VsmCaAgent *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // r8
  unsigned int v9; // eax
  int v10; // [rsp+20h] [rbp-48h]
  int v11[4]; // [rsp+38h] [rbp-30h] BYREF
  const wchar_t *v12; // [rsp+48h] [rbp-20h]
  __int64 v13; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
  {
    v12 = L"StartCATrustlet lock...";
    v13 = 48;
    McGenEventWrite_EventWriteTransfer(v3, ServiceDebugInformational, v4, 2, v11);
  }
  if ( *((_BYTE *)this + 48) )
  {
    if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 4) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v3,
        ServiceDebugWarning,
        L"Exit Signal is set, no need to start CATrustlet.",
        1115);
    v9 = wil::verify_hresult<long>(2147943515LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A9,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
      (const char *)v9,
      v10);
  }
  Microsoft::HostGuardian::Client::VsmCaAgent::TerminateCaTrustlet((RPC_BINDING_HANDLE *)this);
  Microsoft::HostGuardian::Client::VsmCaAgent::CreateSecurityProcess((UCHAR *)this, v5, v6);
  Microsoft::HostGuardian::Client::VsmCaAgent::BindingAndConnectRpcClient((void **)this);
  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
  {
    v12 = L"CATrustlet started.";
    v13 = 40;
    McGenEventWrite_EventWriteTransfer(v7, ServiceDebugInformational, v8, 2, v11);
  }
  if ( v2 )
    LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x180013954  mov     [rsp+arg_8], rbx
0x180013959  push    rdi
0x18001395a  sub     rsp, 60h
0x18001395e  mov     rax, cs:__security_cookie
0x180013965  xor     rax, rsp
0x180013968  mov     [rsp+68h+var_10], rax
0x18001396d  mov     rdi, rcx
0x180013970  lea     rbx, [rcx+38h]
0x180013974  mov     rcx, rbx; lpCriticalSection
0x180013977  call    cs:__imp_EnterCriticalSection
0x18001397d  mov     [rsp+68h+var_38], rbx
0x180013982  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 2
0x180013989  jz      short loc_1800139BC
0x18001398b  lea     rax, aStartcatrustle_1; "StartCATrustlet lock..."
0x180013992  mov     [rsp+68h+var_20], rax
0x180013997  mov     [rsp+68h+var_18], 30h ; '0'
0x1800139a0  lea     rax, [rsp+68h+var_30]
0x1800139a5  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800139aa  mov     r9d, 2
0x1800139b0  lea     rdx, ServiceDebugInformational
0x1800139b7  call    McGenEventWrite_EventWriteTransfer
0x1800139bc  mov     al, [rdi+30h]
0x1800139bf  test    al, al
0x1800139c1  jnz     short loc_180013A3C
0x1800139c3  mov     rcx, rdi; Binding
0x1800139c6  call    ?TerminateCaTrustlet@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXXZ; Microsoft::HostGuardian::Client::VsmCaAgent::TerminateCaTrustlet(void)
0x1800139cb  mov     rcx, rdi; this
0x1800139ce  call    ?CreateSecurityProcess@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXXZ; Microsoft::HostGuardian::Client::VsmCaAgent::CreateSecurityProcess(void)
0x1800139d3  mov     rcx, rdi; this
0x1800139d6  call    ?BindingAndConnectRpcClient@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXXZ; Microsoft::HostGuardian::Client::VsmCaAgent::BindingAndConnectRpcClient(void)
0x1800139db  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 2
0x1800139e2  jz      short loc_180013A16
0x1800139e4  lea     rax, aCatrustletStar; "CATrustlet started."
0x1800139eb  mov     [rsp+68h+var_20], rax
0x1800139f0  mov     [rsp+68h+var_18], 28h ; '('
0x1800139f9  lea     rax, [rsp+68h+var_30]
0x1800139fe  mov     qword ptr [rsp+68h+var_48], rax
0x180013a03  mov     r9d, 2
0x180013a09  lea     rdx, ServiceDebugInformational
0x180013a10  call    McGenEventWrite_EventWriteTransfer
0x180013a15  nop
0x180013a16  test    rbx, rbx
0x180013a19  jz      short loc_180013A24
0x180013a1b  mov     rcx, rbx; lpCriticalSection
0x180013a1e  call    cs:__imp_LeaveCriticalSection
0x180013a24  mov     rcx, [rsp+68h+var_10]
0x180013a29  xor     rcx, rsp; StackCookie
0x180013a2c  call    __security_check_cookie
0x180013a31  mov     rbx, [rsp+68h+arg_8]
0x180013a36  add     rsp, 60h
0x180013a3a  pop     rdi
0x180013a3b  retn
0x180013a3c  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 4
0x180013a43  jz      short loc_180013A5E
0x180013a45  mov     r9d, 45Bh
0x180013a4b  lea     r8, aExitSignalIsSe_0; "Exit Signal is set, no need to start CA"...
0x180013a52  lea     rdx, ServiceDebugWarning
0x180013a59  call    McTemplateU0zq_EventWriteTransfer
0x180013a5e  mov     ecx, 8007045Bh
0x180013a63  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180013a68  mov     r9d, eax; char *
0x180013a6b  mov     rcx, [rsp+68h]; this
0x180013a70  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x180013a77  mov     edx, 1A9h; void *
0x180013a7c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
