# LipsBfeBind

- ea: `0x180009d44`
- end: `0x180009eb0`
- name: `LipsBfeBind`
- size: `364`
- prototype: `__int64()`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x180009cb4`
- `0x180047e20`
- `0x180047f60`
- `0x1800480b8`
- `0x1800482dc`
- `0x180048570`
- `0x1800487ac`
- `0x180048988`

## callees

- `0x180009d44`
- `0x18000c4d0`
- `0x18000e510`
- `0x18000f6ac`
- `0x18004d090`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180009dd1`
- `ntdll!EtwEventWrite` at `0x180009e11`
- `ntdll!EtwEventWrite` at `0x180009dd1`
- `ntdll!EtwEventWrite` at `0x180009e11`
- `fwpuclnt!FwpmEngineOpen0` at `0x180009df0`
- `fwpuclnt!FwpmEngineOpen0` at `0x180009df0`

## string_xrefs

- `0x180009d90`: `PolicyAgent Session`
- `0x180009e79`: `FwpmEngineOpen0`

## pseudocode

```c
__int64 LipsBfeBind()
{
  DWORD v0; // ebx
  FWPM_SESSION0 session; // [rsp+30h] [rbp-9h] BYREF

  if ( gLipsBfeEngineHandle )
    return 0;
  *(_QWORD *)&session.sessionKey.Data2 = 0;
  *(_DWORD *)&session.sessionKey.Data4[4] = 0;
  session.displayData.name = L"POLICYAGNT";
  session.displayData.description = L"PolicyAgent Session";
  session.sessionKey.Data1 = 0;
  *(_QWORD *)&session.txnWaitTimeoutInMSec = 300000;
  memset(&session.processId + 1, 0, 28);
  session.flags = 1;
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_BFE_EngineOpen_Begin, 0, 0);
  v0 = FwpmEngineOpen0(0, 0xAu, 0, &session, &gLipsBfeEngineHandle);
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_BFE_EngineOpen_End, 0, 0);
  if ( !v0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_47af9f0627fa340f85c21449576885fa_Traceguids,
        "FwpmEngineOpen0");
    return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_47af9f0627fa340f85c21449576885fa_Traceguids, v0);
  return LipsReportError(v0, "LipsBfeBind");
}

```

## disassembly

```asm
0x180009d44  mov     [rsp-8+arg_0], rbx
0x180009d49  push    rbp
0x180009d4a  lea     rbp, [rsp-57h]
0x180009d4f  sub     rsp, 90h
0x180009d56  mov     rax, cs:__security_cookie
0x180009d5d  xor     rax, rsp
0x180009d60  mov     [rbp+57h+var_10], rax
0x180009d64  cmp     cs:gLipsBfeEngineHandle, 0
0x180009d6c  jnz     loc_180009E91
0x180009d72  mov     rcx, cs:g_Provider
0x180009d79  xor     eax, eax
0x180009d7b  mov     qword ptr [rbp+57h+session.sessionKey.Data2], rax
0x180009d7f  xorps   xmm0, xmm0
0x180009d82  mov     dword ptr [rbp+57h+session.sessionKey.Data4+4], eax
0x180009d85  lea     rax, aPolicyagnt; "POLICYAGNT"
0x180009d8c  mov     [rbp+57h+session.displayData.name], rax
0x180009d90  lea     rax, aPolicyagentSes; "PolicyAgent Session"
0x180009d97  mov     [rbp+57h+session.displayData.description], rax
0x180009d9b  xor     eax, eax
0x180009d9d  mov     [rbp+57h+session.sessionKey.Data1], 0
0x180009da4  mov     qword ptr [rbp+57h+session.txnWaitTimeoutInMSec], 493E0h
0x180009dac  mov     dword ptr [rbp+57h+session+2Ch], eax
0x180009daf  movdqa  xmmword ptr [rbp+57h+session.sid], xmm0
0x180009db4  mov     qword ptr [rbp+57h+session.kernelMode], rax
0x180009db8  mov     [rbp+57h+session.flags], 1
0x180009dbf  test    rcx, rcx
0x180009dc2  jz      short loc_180009DD7
0x180009dc4  xor     r9d, r9d
0x180009dc7  lea     rdx, IPSEC_BFE_EngineOpen_Begin
0x180009dce  xor     r8d, r8d
0x180009dd1  call    cs:__imp_EtwEventWrite
0x180009dd7  xor     r8d, r8d; authIdentity
0x180009dda  lea     rax, gLipsBfeEngineHandle
0x180009de1  lea     r9, [rbp+57h+session]; session
0x180009de5  mov     [rsp+90h+engineHandle], rax; engineHandle
0x180009dea  xor     ecx, ecx; serverName
0x180009dec  lea     edx, [r8+0Ah]; authnService
0x180009df0  call    cs:__imp_FwpmEngineOpen0
0x180009df6  mov     rcx, cs:g_Provider
0x180009dfd  mov     ebx, eax
0x180009dff  test    rcx, rcx
0x180009e02  jz      short loc_180009E17
0x180009e04  xor     r9d, r9d
0x180009e07  lea     rdx, IPSEC_BFE_EngineOpen_End
0x180009e0e  xor     r8d, r8d
0x180009e11  call    cs:__imp_EtwEventWrite
0x180009e17  test    ebx, ebx
0x180009e19  jz      short loc_180009E5C
0x180009e1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e22  lea     rax, WPP_GLOBAL_Control
0x180009e29  cmp     rcx, rax
0x180009e2c  jz      short loc_180009E4C
0x180009e2e  test    byte ptr [rcx+1Ch], 10h
0x180009e32  jz      short loc_180009E4C
0x180009e34  mov     rcx, [rcx+10h]
0x180009e38  lea     r8, WPP_47af9f0627fa340f85c21449576885fa_Traceguids
0x180009e3f  mov     edx, 0Dh
0x180009e44  mov     r9d, ebx
0x180009e47  call    WPP_SF_d
0x180009e4c  lea     rdx, aLipsbfebind; "LipsBfeBind"
0x180009e53  mov     ecx, ebx
0x180009e55  call    LipsReportError
0x180009e5a  jmp     short loc_180009E93
0x180009e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e63  lea     rax, WPP_GLOBAL_Control
0x180009e6a  cmp     rcx, rax
0x180009e6d  jz      short loc_180009E91
0x180009e6f  test    byte ptr [rcx+1Ch], 4
0x180009e73  jz      short loc_180009E91
0x180009e75  mov     rcx, [rcx+10h]
0x180009e79  lea     r9, aFwpmengineopen; "FwpmEngineOpen0"
0x180009e80  mov     edx, 0Eh
0x180009e85  lea     r8, WPP_47af9f0627fa340f85c21449576885fa_Traceguids
0x180009e8c  call    WPP_SF_s
0x180009e91  xor     eax, eax
0x180009e93  mov     rcx, [rbp+57h+var_10]
0x180009e97  xor     rcx, rsp; StackCookie
0x180009e9a  call    __security_check_cookie
0x180009e9f  mov     rbx, [rsp+90h+arg_0]
0x180009ea7  add     rsp, 90h
0x180009eae  pop     rbp
0x180009eaf  retn
```
