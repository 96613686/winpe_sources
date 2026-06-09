# Microsoft::HostGuardian::Client::VsmCaAgent::CaTrustletMonitorThread(void *)

- ea: `0x180012890`
- end: `0x180012a00`
- name: `?CaTrustletMonitorThread@VsmCaAgent@Client@HostGuardian@Microsoft@@CAKPEAX@Z`
- size: `368`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001770`
- `0x1800077a0`
- `0x180007878`
- `0x180012890`
- `0x1800136a4`
- `0x180013954`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001297d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800129a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001297d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800129a1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800128ff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800128ff`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180012952`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180012952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012911`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012911`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180012992`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180012992`

## string_xrefs

- `0x180012923`: `Can't communicate to the CA trustlet, trying to restart`
- `0x1800129b2`: `Exit signal is set, terminated the CaTrustletMonitorThread.`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::VsmCaAgent::CaTrustletMonitorThread(PVOID Parameter)
{
  __int64 v1; // rcx
  __int64 v2; // r8
  struct Microsoft::HostGuardian::Client::VsmCaAgent *v3; // rax
  DWORD LastError; // eax
  __int64 v5; // rcx
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  Microsoft::HostGuardian::Client::VsmCaAgent *v8; // rax
  const char *v9; // r9
  _BYTE v11[16]; // [rsp+40h] [rbp-38h] BYREF
  const wchar_t *v12; // [rsp+50h] [rbp-28h]
  __int64 v13; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

LABEL_1:
  while ( 1 )
  {
    LOBYTE(v1) = *((_BYTE *)Microsoft::HostGuardian::Client::VsmCaAgent::Instance() + 48);
    if ( (_BYTE)v1 )
      break;
    if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
    {
      v12 = L"Wait m_caTrustletProcHandle...";
      v13 = 62;
      McGenEventWrite_EventWriteTransfer(v1, ServiceDebugInformational, v2, 2, v11);
    }
    v3 = Microsoft::HostGuardian::Client::VsmCaAgent::Instance();
    LastError = WaitForSingleObject(*((HANDLE *)v3 + 4), 0xFFFFFFFF);
    if ( LastError != 258 )
    {
      if ( LastError == -1 )
        LastError = GetLastError();
      if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 4) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          v5,
          ServiceDebugWarning,
          L"Can't communicate to the CA trustlet, trying to restart",
          LastError);
      while ( !*((_BYTE *)Microsoft::HostGuardian::Client::VsmCaAgent::Instance() + 48) )
      {
        v6 = (struct _RTL_CRITICAL_SECTION *)((char *)Microsoft::HostGuardian::Client::VsmCaAgent::Instance() + 56);
        v7 = (struct _RTL_CRITICAL_SECTION *)((unsigned __int64)v6 & -(__int64)TryEnterCriticalSection(v6));
        if ( v7 )
        {
          try
          {
            v8 = Microsoft::HostGuardian::Client::VsmCaAgent::Instance();
            Microsoft::HostGuardian::Client::VsmCaAgent::StartCaTrustlet(v8);
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x195,
              (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
              v9);
            goto LABEL_13;
          }
          LeaveCriticalSection(v7);
          goto LABEL_1;
        }
LABEL_13:
        Sleep(0x3E8u);
        if ( v7 )
          LeaveCriticalSection(v7);
      }
    }
  }
  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
  {
    v12 = L"Exit signal is set, terminated the CaTrustletMonitorThread.";
    v13 = 120;
    McGenEventWrite_EventWriteTransfer(v1, ServiceDebugInformational, v2, 2, v11);
  }
  return 0;
}

```

## disassembly

```asm
0x180012890  mov     [rsp+arg_0], rbx
0x180012895  push    rdi
0x180012896  sub     rsp, 70h
0x18001289a  mov     rax, cs:__security_cookie
0x1800128a1  xor     rax, rsp
0x1800128a4  mov     [rsp+78h+var_18], rax
0x1800128a9  call    ?Instance@VsmCaAgent@Client@HostGuardian@Microsoft@@SAAEAV1234@XZ; Microsoft::HostGuardian::Client::VsmCaAgent::Instance(void)
0x1800128ae  mov     cl, [rax+30h]
0x1800128b1  test    cl, cl
0x1800128b3  jnz     loc_1800129A9
0x1800128b9  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 2
0x1800128c0  jz      short loc_1800128F3
0x1800128c2  lea     rax, aWaitMCatrustle; "Wait m_caTrustletProcHandle..."
0x1800128c9  mov     [rsp+78h+var_28], rax
0x1800128ce  mov     [rsp+78h+var_20], 3Eh ; '>'
0x1800128d7  lea     rax, [rsp+78h+var_38]
0x1800128dc  mov     [rsp+78h+var_58], rax
0x1800128e1  mov     r9d, 2
0x1800128e7  lea     rdx, ServiceDebugInformational
0x1800128ee  call    McGenEventWrite_EventWriteTransfer
0x1800128f3  call    ?Instance@VsmCaAgent@Client@HostGuardian@Microsoft@@SAAEAV1234@XZ; Microsoft::HostGuardian::Client::VsmCaAgent::Instance(void)
0x1800128f8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800128fb  mov     rcx, [rax+20h]; hHandle
0x1800128ff  call    cs:__imp_WaitForSingleObject
0x180012905  cmp     eax, 102h
0x18001290a  jz      short loc_1800128A9
0x18001290c  cmp     eax, 0FFFFFFFFh
0x18001290f  jnz     short loc_180012917
0x180012911  call    cs:__imp_GetLastError
0x180012917  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 4
0x18001291e  jz      short loc_180012936
0x180012920  mov     r9d, eax
0x180012923  lea     r8, aCanTCommunicat; "Can't communicate to the CA trustlet, t"...
0x18001292a  lea     rdx, ServiceDebugWarning
0x180012931  call    McTemplateU0zq_EventWriteTransfer
0x180012936  call    ?Instance@VsmCaAgent@Client@HostGuardian@Microsoft@@SAAEAV1234@XZ; Microsoft::HostGuardian::Client::VsmCaAgent::Instance(void)
0x18001293b  mov     cl, [rax+30h]
0x18001293e  test    cl, cl
0x180012940  jnz     loc_1800128A9
0x180012946  call    ?Instance@VsmCaAgent@Client@HostGuardian@Microsoft@@SAAEAV1234@XZ; Microsoft::HostGuardian::Client::VsmCaAgent::Instance(void)
0x18001294b  lea     rdi, [rax+38h]
0x18001294f  mov     rcx, rdi; lpCriticalSection
0x180012952  call    cs:__imp_TryEnterCriticalSection
0x180012958  neg     eax
0x18001295a  sbb     rbx, rbx
0x18001295d  and     rbx, rdi
0x180012960  mov     [rsp+78h+var_48], rbx
0x180012965  mov     [rsp+78h+var_40], rbx
0x18001296a  jz      short loc_18001298D
0x18001296c  call    ?Instance@VsmCaAgent@Client@HostGuardian@Microsoft@@SAAEAV1234@XZ; Microsoft::HostGuardian::Client::VsmCaAgent::Instance(void)
0x180012971  mov     rcx, rax; this
0x180012974  call    ?StartCaTrustlet@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXXZ; Microsoft::HostGuardian::Client::VsmCaAgent::StartCaTrustlet(void)
0x180012979  nop
0x18001297a  mov     rcx, rbx; lpCriticalSection
0x18001297d  call    cs:__imp_LeaveCriticalSection
0x180012983  jmp     loc_1800128A9
0x180012988  mov     rbx, [rsp+78h+var_48]
0x18001298d  mov     ecx, 3E8h; dwMilliseconds
0x180012992  call    cs:__imp_Sleep
0x180012998  nop
0x180012999  test    rbx, rbx
0x18001299c  jz      short loc_180012936
0x18001299e  mov     rcx, rbx; lpCriticalSection
0x1800129a1  call    cs:__imp_LeaveCriticalSection
0x1800129a7  jmp     short loc_180012936
0x1800129a9  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 2
0x1800129b0  jz      short loc_1800129E3
0x1800129b2  lea     rax, aExitSignalIsSe; "Exit signal is set, terminated the CaTr"...
0x1800129b9  mov     [rsp+78h+var_28], rax
0x1800129be  mov     [rsp+78h+var_20], 78h ; 'x'
0x1800129c7  lea     rax, [rsp+78h+var_38]
0x1800129cc  mov     [rsp+78h+var_58], rax
0x1800129d1  mov     r9d, 2
0x1800129d7  lea     rdx, ServiceDebugInformational
0x1800129de  call    McGenEventWrite_EventWriteTransfer
0x1800129e3  xor     eax, eax
0x1800129e5  mov     rcx, [rsp+78h+var_18]
0x1800129ea  xor     rcx, rsp; StackCookie
0x1800129ed  call    __security_check_cookie
0x1800129f2  mov     rbx, [rsp+78h+arg_0]
0x1800129fa  add     rsp, 70h
0x1800129fe  pop     rdi
0x1800129ff  retn
```
