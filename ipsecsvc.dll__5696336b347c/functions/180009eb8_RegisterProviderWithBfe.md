# RegisterProviderWithBfe

- ea: `0x180009eb8`
- end: `0x18000a02b`
- name: `RegisterProviderWithBfe`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180009cb4`

## callees

- `0x180009eb8`
- `0x18000e510`
- `0x1800452d0`
- `0x18004d090`

## import_xrefs

- `fwpuclnt!FwpmEngineClose0` at `0x180009fcc`
- `fwpuclnt!FwpmEngineClose0` at `0x180009fcc`
- `fwpuclnt!FwpmEngineOpen0` at `0x180009f3a`
- `fwpuclnt!FwpmEngineOpen0` at `0x180009f3a`
- `fwpuclnt!FwpmProviderAdd0` at `0x180009f87`
- `fwpuclnt!FwpmProviderAdd0` at `0x180009f87`

## string_xrefs

- `0x180009ef5`: `Policyagent`

## pseudocode

```c
__int64 RegisterProviderWithBfe()
{
  DWORD v0; // eax
  DWORD v1; // ebx
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // r9
  DWORD v5; // eax
  HANDLE engineHandle; // [rsp+30h] [rbp-19h] BYREF
  FWPM_SESSION0 session; // [rsp+40h] [rbp-9h] BYREF

  engineHandle = 0;
  *(_QWORD *)&session.sessionKey.Data2 = 0;
  *(_DWORD *)&session.sessionKey.Data4[4] = 0;
  session.sessionKey.Data1 = 0;
  session.displayData.name = L"Policyagent";
  session.displayData.description = L"Policyagent";
  session.flags = 0;
  memset(&session.processId + 1, 0, 28);
  *(_QWORD *)&session.txnWaitTimeoutInMSec = 18000000;
  v0 = FwpmEngineOpen0(0, 0xAu, 0, &session, &engineHandle);
  v1 = v0;
  if ( v0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v3 = 74;
      v4 = v0;
LABEL_5:
      WPP_SF_d(v2[2], v3, WPP_47af9f0627fa340f85c21449576885fa_Traceguids, v4);
LABEL_13:
      v2 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v5 = FwpmProviderAdd0(engineHandle, &provider, 0);
    v1 = 0;
    if ( v5 != -2144206839 )
      v1 = v5;
    if ( !v1 )
    {
      v1 = 0;
      goto LABEL_13;
    }
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v3 = 75;
      v4 = v1;
      goto LABEL_5;
    }
  }
  if ( engineHandle )
  {
    FwpmEngineClose0(engineHandle);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v1 && v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x10) != 0 )
    WPP_SF_sD(
      v2[2],
      10,
      (unsigned int)WPP_f9bd4346a19839ab9ee18df0d3aaefbd_Traceguids,
      (unsigned int)"RegisterProviderWithBfe",
      v1);
  return v1;
}

```

## disassembly

```asm
0x180009eb8  mov     [rsp-8+arg_0], rbx
0x180009ebd  mov     [rsp-8+arg_8], r14
0x180009ec2  push    rbp
0x180009ec3  lea     rbp, [rsp-57h]
0x180009ec8  sub     rsp, 0A0h
0x180009ecf  mov     rax, cs:__security_cookie
0x180009ed6  xor     rax, rsp
0x180009ed9  mov     [rbp+57h+var_10], rax
0x180009edd  xor     eax, eax
0x180009edf  mov     [rbp+57h+var_70], 0
0x180009ee7  mov     qword ptr [rbp+57h+session.sessionKey.Data2], rax
0x180009eeb  lea     r9, [rbp+57h+session]; session
0x180009eef  mov     dword ptr [rbp+57h+session.sessionKey.Data4+4], eax
0x180009ef2  xor     r8d, r8d; authIdentity
0x180009ef5  lea     rax, aPolicyagent; "Policyagent"
0x180009efc  mov     [rbp+57h+session.sessionKey.Data1], 0
0x180009f03  mov     [rbp+57h+session.displayData.name], rax
0x180009f07  xorps   xmm0, xmm0
0x180009f0a  mov     [rbp+57h+session.displayData.description], rax
0x180009f0e  xor     ecx, ecx; serverName
0x180009f10  xor     eax, eax
0x180009f12  mov     [rbp+57h+session.flags], 0
0x180009f19  mov     dword ptr [rbp+57h+session+2Ch], eax
0x180009f1c  lea     edx, [r8+0Ah]; authnService
0x180009f20  mov     qword ptr [rbp+57h+session.kernelMode], rax
0x180009f24  lea     rax, [rbp+57h+var_70]
0x180009f28  mov     [rsp+0A0h+engineHandle], rax; engineHandle
0x180009f2d  mov     qword ptr [rbp+57h+session.txnWaitTimeoutInMSec], 112A880h
0x180009f35  movdqa  xmmword ptr [rbp+57h+session.sid], xmm0
0x180009f3a  call    cs:__imp_FwpmEngineOpen0
0x180009f40  lea     r14, WPP_GLOBAL_Control
0x180009f47  mov     ebx, eax
0x180009f49  test    eax, eax
0x180009f4b  jz      short loc_180009F79
0x180009f4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f54  cmp     rcx, r14
0x180009f57  jz      short loc_180009FC0
0x180009f59  test    byte ptr [rcx+1Ch], 10h
0x180009f5d  jz      short loc_180009FC0
0x180009f5f  mov     edx, 4Ah ; 'J'
0x180009f64  mov     r9d, eax
0x180009f67  mov     rcx, [rcx+10h]
0x180009f6b  lea     r8, WPP_47af9f0627fa340f85c21449576885fa_Traceguids
0x180009f72  call    WPP_SF_d
0x180009f77  jmp     short loc_180009FB9
0x180009f79  mov     rcx, [rbp+57h+var_70]; engineHandle
0x180009f7d  lea     rdx, provider; provider
0x180009f84  xor     r8d, r8d; sd
0x180009f87  call    cs:__imp_FwpmProviderAdd0
0x180009f8d  xor     ebx, ebx
0x180009f8f  cmp     eax, 80320009h
0x180009f94  cmovnz  ebx, eax
0x180009f97  test    ebx, ebx
0x180009f99  jz      short loc_180009FB7
0x180009f9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fa2  cmp     rcx, r14
0x180009fa5  jz      short loc_180009FC0
0x180009fa7  test    byte ptr [rcx+1Ch], 10h
0x180009fab  jz      short loc_180009FC0
0x180009fad  mov     edx, 4Bh ; 'K'
0x180009fb2  mov     r9d, ebx
0x180009fb5  jmp     short loc_180009F67
0x180009fb7  xor     ebx, ebx
0x180009fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fc0  mov     rax, [rbp+57h+var_70]
0x180009fc4  test    rax, rax
0x180009fc7  jz      short loc_180009FD9
0x180009fc9  mov     rcx, rax; engineHandle
0x180009fcc  call    cs:__imp_FwpmEngineClose0
0x180009fd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fd9  test    ebx, ebx
0x180009fdb  jz      short loc_18000A008
0x180009fdd  cmp     rcx, r14
0x180009fe0  jz      short loc_18000A008
0x180009fe2  test    byte ptr [rcx+1Ch], 10h
0x180009fe6  jz      short loc_18000A008
0x180009fe8  mov     rcx, [rcx+10h]
0x180009fec  lea     r9, aRegisterprovid; "RegisterProviderWithBfe"
0x180009ff3  mov     edx, 0Ah
0x180009ff8  mov     dword ptr [rsp+0A0h+engineHandle], ebx
0x180009ffc  lea     r8, WPP_f9bd4346a19839ab9ee18df0d3aaefbd_Traceguids
0x18000a003  call    WPP_SF_sD
0x18000a008  mov     eax, ebx
0x18000a00a  mov     rcx, [rbp+57h+var_10]
0x18000a00e  xor     rcx, rsp; StackCookie
0x18000a011  call    __security_check_cookie
0x18000a016  lea     r11, [rsp+0A0h+var_s0]
0x18000a01e  mov     rbx, [r11+10h]
0x18000a022  mov     r14, [r11+18h]
0x18000a026  mov     rsp, r11
0x18000a029  pop     rbp
0x18000a02a  retn
```
