# CDebugTargetManagerBrokerAdapter::GetDebugTargetsJson(ushort *,ushort * *)

- ea: `0x180072ccc`
- end: `0x180072e47`
- name: `?GetDebugTargetsJson@CDebugTargetManagerBrokerAdapter@@AEAAJPEAGPEAPEAG@Z`
- size: `379`
- prototype: `__int64 __fastcall(CDebugTargetManagerBrokerAdapter *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180072e50`

## callees

- `0x180009db8`
- `0x180018b30`
- `0x18002b530`
- `0x18002c5b0`
- `0x180037b5c`
- `0x180072b98`
- `0x180072ccc`
- `0x180072fa8`
- `0x180073064`
- `0x18007f104`
- `0x180081700`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180072dc1`
- `OLEAUT32!__imp_SysAllocString` at `0x180072dc1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180072d7e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180072d7e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072d0c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072d0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072e13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072e13`

## string_xrefs

- `0x180072d23`: `onecoreuap\inetcore\edgemanager\webruntime\webrtdiagnosticsbrokeradapter\debugtargetmanagerbrokeradapter.cpp`
- `0x180072dac`: `onecoreuap\inetcore\edgemanager\webruntime\webrtdiagnosticsbrokeradapter\debugtargetmanagerbrokeradapter.cpp`
- `0x180072dee`: `onecoreuap\inetcore\edgemanager\webruntime\webrtdiagnosticsbrokeradapter\debugtargetmanagerbrokeradapter.cpp`

## pseudocode

```c
__int64 __fastcall CDebugTargetManagerBrokerAdapter::GetDebugTargetsJson(
        CDebugTargetManagerBrokerAdapter *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  HANDLE EventW; // rax
  const char *v7; // r9
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // esi
  DWORD v11; // eax
  const char *v12; // r9
  const OLECHAR **v13; // rbx
  const OLECHAR *v14; // rcx
  const char *v15; // r9
  __int64 v16; // rcx
  __int64 result; // rax
  unsigned __int16 Src[2088]; // [rsp+30h] [rbp-1078h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+10A8h] [rbp+0h]

  CDebugTargetManagerBrokerAdapter::EnsureDebugTargetManagerInitialized(this);
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 6) = EventW;
  if ( !EventW )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webrtdiagnosticsbrokeradapter\\debugtargetmanagerbrokeradapter.cpp",
      v7);
  memset_0(Src, 0, 0x1048u);
  StringCchCopyW(Src, 0x824u, a2);
  v10 = TFlatIsoMessage<LCIE_MSGID_DEVTOOLS_GET_TARGETS_REQUEST_MSG>::Post(
          *((_DWORD *)this + 14),
          *((_DWORD *)this + 14),
          v8,
          v9,
          Src);
  if ( v10 )
  {
    *a3 = (unsigned __int16 *)SysAllocString_FF();
    MicrosoftTelemetryAssertTriggeredArgs(v16, v10);
  }
  else
  {
    v11 = WaitForSingleObject(*((HANDLE *)this + 6), 0x2710u);
    if ( v11 == 258 )
    {
      v10 = -2147023728;
    }
    else if ( v11 )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x8A,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webrtdiagnosticsbrokeradapter\\debugtargetmanagerbrokeradapter.cpp",
        v12);
    }
    v13 = (const OLECHAR **)((char *)this + 16);
    if ( *((_QWORD *)this + 5) <= 7u )
      v14 = (const OLECHAR *)((char *)this + 16);
    else
      v14 = *v13;
    *a3 = SysAllocString(v14);
    *((_QWORD *)this + 4) = 0;
    if ( *((_QWORD *)this + 5) > 7u )
      v13 = (const OLECHAR **)*v13;
    *(_WORD *)v13 = 0;
    if ( !*a3 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webrtdiagnosticsbrokeradapter\\debugtargetmanagerbrokeradapter.cpp",
        v15);
  }
  CloseHandle(*((HANDLE *)this + 6));
  result = v10;
  *((_QWORD *)this + 6) = 0;
  return result;
}

```

## disassembly

```asm
0x180072ccc  mov     [rsp+arg_18], rbx
0x180072cd1  push    rsi
0x180072cd2  push    rdi
0x180072cd3  push    r14
0x180072cd5  mov     eax, 1090h
0x180072cda  call    _alloca_probe
0x180072cdf  sub     rsp, rax
0x180072ce2  mov     rax, cs:__security_cookie
0x180072ce9  xor     rax, rsp
0x180072cec  mov     [rsp+10A8h+var_28], rax
0x180072cf4  mov     r14, r8
0x180072cf7  mov     rbx, rdx
0x180072cfa  mov     rdi, rcx
0x180072cfd  call    ?EnsureDebugTargetManagerInitialized@CDebugTargetManagerBrokerAdapter@@AEAAXXZ; CDebugTargetManagerBrokerAdapter::EnsureDebugTargetManagerInitialized(void)
0x180072d02  xor     r9d, r9d; lpName
0x180072d05  xor     r8d, r8d; bInitialState
0x180072d08  xor     edx, edx; bManualReset
0x180072d0a  xor     ecx, ecx; lpEventAttributes
0x180072d0c  call    cs:__imp_CreateEventW
0x180072d12  mov     [rdi+30h], rax
0x180072d16  test    rax, rax
0x180072d19  jnz     short loc_180072D33
0x180072d1b  mov     rcx, [rsp+10A8h]; this
0x180072d23  lea     r8, aOnecoreuapInet_42; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180072d2a  lea     edx, [rax+78h]; void *
0x180072d2d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180072d33  xor     edx, edx; Val
0x180072d35  lea     rcx, [rsp+10A8h+var_1078]; void *
0x180072d3a  mov     r8d, 1048h; Size
0x180072d40  call    memset_0
0x180072d45  mov     r8, rbx; unsigned __int16 *
0x180072d48  lea     rcx, [rsp+10A8h+var_1078]; unsigned __int16 *
0x180072d4d  mov     edx, 824h; unsigned __int64
0x180072d52  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180072d57  mov     ecx, [rdi+38h]; int
0x180072d5a  lea     rax, [rsp+10A8h+var_1078]
0x180072d5f  mov     edx, ecx; int
0x180072d61  mov     [rsp+10A8h+Src], rax; Src
0x180072d66  call    ?Post@?$TFlatIsoMessage@ULCIE_MSGID_DEVTOOLS_GET_TARGETS_REQUEST_MSG@@@@SAJKKKKPEBULCIE_MSGID_DEVTOOLS_GET_TARGETS_REQUEST_MSG@@@Z; TFlatIsoMessage<LCIE_MSGID_DEVTOOLS_GET_TARGETS_REQUEST_MSG>::Post(ulong,ulong,ulong,ulong,LCIE_MSGID_DEVTOOLS_GET_TARGETS_REQUEST_MSG const *)
0x180072d6b  mov     esi, eax
0x180072d6d  test    eax, eax
0x180072d6f  jnz     loc_180072E00
0x180072d75  mov     rcx, [rdi+30h]; hHandle
0x180072d79  mov     edx, 2710h; dwMilliseconds
0x180072d7e  call    cs:__imp_WaitForSingleObject
0x180072d84  cmp     eax, 102h
0x180072d89  jnz     short loc_180072DA0
0x180072d8b  mov     esi, 80070490h
0x180072d90  lea     rbx, [rdi+10h]
0x180072d94  cmp     qword ptr [rbx+18h], 7
0x180072d99  jbe     short loc_180072DBE
0x180072d9b  mov     rcx, [rbx]
0x180072d9e  jmp     short loc_180072DC1
0x180072da0  test    eax, eax
0x180072da2  jz      short loc_180072D90
0x180072da4  mov     rcx, [rsp+10A8h]; this
0x180072dac  lea     r8, aOnecoreuapInet_42; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180072db3  mov     edx, 8Ah; void *
0x180072db8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180072dbe  mov     rcx, rbx; psz
0x180072dc1  call    cs:__imp_SysAllocString
0x180072dc7  mov     [r14], rax
0x180072dca  mov     qword ptr [rbx+10h], 0
0x180072dd2  cmp     qword ptr [rbx+18h], 7
0x180072dd7  jbe     short loc_180072DDC
0x180072dd9  mov     rbx, [rbx]
0x180072ddc  xor     eax, eax
0x180072dde  mov     [rbx], ax
0x180072de1  cmp     [r14], rax
0x180072de4  jnz     short loc_180072E0F
0x180072de6  mov     rcx, [rsp+10A8h]; this
0x180072dee  lea     r8, aOnecoreuapInet_42; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180072df5  mov     edx, 90h; void *
0x180072dfa  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180072e00  call    SysAllocString_FF
0x180072e05  mov     [r14], rax
0x180072e08  mov     edx, esi
0x180072e0a  call    MicrosoftTelemetryAssertTriggeredArgs
0x180072e0f  mov     rcx, [rdi+30h]; hObject
0x180072e13  call    cs:__imp_CloseHandle
0x180072e19  mov     eax, esi
0x180072e1b  mov     qword ptr [rdi+30h], 0
0x180072e23  mov     rcx, [rsp+10A8h+var_28]
0x180072e2b  xor     rcx, rsp; StackCookie
0x180072e2e  call    __security_check_cookie
0x180072e33  mov     rbx, [rsp+10A8h+arg_18]
0x180072e3b  add     rsp, 1090h
0x180072e42  pop     r14
0x180072e44  pop     rdi
0x180072e45  pop     rsi
0x180072e46  retn
```
