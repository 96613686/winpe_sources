# FirmwareDeviceQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)

- ea: `0x18004f450`
- end: `0x18004f6e2`
- name: `?FirmwareDeviceQueryCallback@@YAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z`
- size: `658`
- prototype: `void __fastcall(struct HDEVQUERY__ *, HANDLE *, const struct _DEV_QUERY_RESULT_ACTION_DATA *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003270`
- `0x18000c458`
- `0x18000c5cc`
- `0x18000ca1c`
- `0x18000dfe0`
- `0x18000e260`
- `0x180013e6c`
- `0x18001af5c`
- `0x18002d5ec`
- `0x180035678`
- `0x18004f450`
- `0x18004fe98`
- `0x180050c3c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18004f5ae`
- `ntdll!EtwEventWrite` at `0x18004f5ae`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004f606`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004f648`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004f606`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004f648`

## string_xrefs

- `0x18004f54a`: `ProcessFirmwareUpdate`
- `0x18004f4ea`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x18004f559`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x18004f5f7`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x18004f639`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x18004f664`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x18004f56c`: `Process firmware update`
- `0x18004f5e8`: `DevQueryStateEnumCompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall FirmwareDeviceQueryCallback(
        struct HDEVQUERY__ *a1,
        HANDLE *a2,
        const struct _DEV_QUERY_RESULT_ACTION_DATA *a3)
{
  int v5; // edx
  int v6; // ebx
  unsigned int v7; // eax
  BOOL v8; // eax
  const char *v9; // r9
  wil::details::in1diag3 *v10; // rcx
  __int64 v11; // rdx
  BOOL v12; // eax
  unsigned int v13; // [rsp+20h] [rbp-E0h]
  char *v14; // [rsp+28h] [rbp-D8h]
  const char *v15; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v16[42]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v17[2]; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v15 = "FirmwareDeviceQueryCallback";
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "FirmwareDeviceQueryCallback");
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v16,
    "FirmwareDeviceQueryCallbackActivity");
  v16[0] = &PpfTraceLoggingProvider::FirmwareDeviceQueryCallbackActivity::`vftable';
  PpfTraceLoggingProvider::FirmwareDeviceQueryCallbackActivity::StartActivity((PpfTraceLoggingProvider::FirmwareDeviceQueryCallbackActivity *)v16);
  v5 = *(_DWORD *)a3;
  if ( !*(_DWORD *)a3 )
  {
    if ( *((_DWORD *)a3 + 2) == 1 )
    {
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
        0x167u,
        "FirmwareDeviceQueryCallback",
        "DevQueryStateEnumCompleted");
      v8 = SetEvent(*a2);
      v10 = retaddr;
      if ( v8 )
        goto LABEL_14;
      v11 = 360;
    }
    else
    {
      if ( *((_DWORD *)a3 + 2) != 2 )
        goto LABEL_14;
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
        0x16Cu,
        "FirmwareDeviceQueryCallback",
        "DevQueryStateAborted");
      v12 = SetEvent(*a2);
      v10 = retaddr;
      if ( v12 )
        goto LABEL_14;
      v11 = 365;
    }
    wil::details::in1diag3::_Log_GetLastError(
      v10,
      (void *)v11,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
      v9);
    goto LABEL_14;
  }
  if ( v5 == 1 )
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
      0x158u,
      "FirmwareDeviceQueryCallback",
      "Found firmware device: %ws, propertyCount: %u\n",
      *((_QWORD *)a3 + 2),
      *((_DWORD *)a3 + 6));
    v6 = ProcessFirmwareUpdate(a3);
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x15C,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
        (const char *)(unsigned int)v6,
        (int)"ProcessFirmwareUpdate",
        v14);
      PpfhLogEventGenericActivityError(L"Process firmware update", v6);
      LODWORD(v15) = v6;
      v17[0] = &v15;
      v17[1] = 4;
      v7 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_FIRMWARE_UPDATE_PROCESSING_ERROR, 1, v17);
      if ( v7 )
        wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x1C7,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
          (const char *)v7,
          v13);
    }
  }
  else
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
      0x172u,
      "FirmwareDeviceQueryCallback",
      "Ignored action: %u",
      v5);
  }
LABEL_14:
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v16);
  v16[0] = &PpfTraceLoggingProvider::FirmwareDeviceQueryCallbackActivity::`vftable';
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v16);
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v16);
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x89u,
    "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
    "Leaving %hs",
    "FirmwareDeviceQueryCallback");
}

```

## disassembly

```asm
0x18004f450  mov     [rsp-8+arg_0], rbx
0x18004f455  mov     [rsp-8+arg_18], rsi
0x18004f45a  push    rbp
0x18004f45b  push    rdi
0x18004f45c  push    r14
0x18004f45e  lea     rbp, [rsp-0B0h]
0x18004f466  sub     rsp, 1B0h
0x18004f46d  mov     rax, cs:__security_cookie
0x18004f474  xor     rax, rsp
0x18004f477  mov     [rbp+0C0h+var_20], rax
0x18004f47e  mov     rbx, r8
0x18004f481  mov     rdi, rdx
0x18004f484  lea     rsi, aFirmwaredevice; "FirmwareDeviceQueryCallback"
0x18004f48b  mov     [rsp+1C0h+var_190], rsi
0x18004f490  mov     qword ptr [rsp+1C0h+var_1A0], rsi
0x18004f495  lea     r9, aEnteringHs; "Entering %hs"
0x18004f49c  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x18004f4a3  mov     edx, 84h; unsigned int
0x18004f4a8  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18004f4af  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18004f4b4  nop
0x18004f4b5  lea     rdx, aFirmwaredevice_0; "FirmwareDeviceQueryCallbackActivity"
0x18004f4bc  lea     rcx, [rsp+1C0h+var_180]
0x18004f4c1  call    ??0?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18004f4c6  lea     r14, ??_7FirmwareDeviceQueryCallbackActivity@PpfTraceLoggingProvider@@6B@; const PpfTraceLoggingProvider::FirmwareDeviceQueryCallbackActivity::`vftable'
0x18004f4cd  mov     [rsp+1C0h+var_180], r14
0x18004f4d2  lea     rcx, [rsp+1C0h+var_180]; this
0x18004f4d7  call    ?StartActivity@FirmwareDeviceQueryCallbackActivity@PpfTraceLoggingProvider@@QEAAXXZ; PpfTraceLoggingProvider::FirmwareDeviceQueryCallbackActivity::StartActivity(void)
0x18004f4dc  nop
0x18004f4dd  mov     edx, [rbx]
0x18004f4df  test    edx, edx
0x18004f4e1  jz      loc_18004F5E2
0x18004f4e7  mov     r8, rsi; char *
0x18004f4ea  lea     rcx, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18004f4f1  cmp     edx, 1
0x18004f4f4  jz      short loc_18004F510
0x18004f4f6  mov     [rsp+1C0h+var_1A0], edx
0x18004f4fa  lea     r9, aIgnoredActionU; "Ignored action: %u"
0x18004f501  mov     edx, 172h; unsigned int
0x18004f506  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18004f50b  jmp     loc_18004F670
0x18004f510  mov     eax, [rbx+18h]
0x18004f513  mov     dword ptr [rsp+1C0h+var_198], eax; char *
0x18004f517  mov     rax, [rbx+10h]
0x18004f51b  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18004f520  lea     r9, aFoundFirmwareD; "Found firmware device: %ws, propertyCou"...
0x18004f527  mov     edx, 158h; unsigned int
0x18004f52c  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18004f531  mov     rcx, rbx; struct _DEV_QUERY_RESULT_ACTION_DATA *
0x18004f534  call    ?ProcessFirmwareUpdate@@YAJPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; ProcessFirmwareUpdate(_DEV_QUERY_RESULT_ACTION_DATA const *)
0x18004f539  mov     ebx, eax
0x18004f53b  test    eax, eax
0x18004f53d  jns     loc_18004F670
0x18004f543  mov     rcx, [rbp+0C8h]; this
0x18004f54a  lea     rax, aProcessfirmwar; "ProcessFirmwareUpdate"
0x18004f551  mov     qword ptr [rsp+1C0h+var_1A0], rax; unsigned int
0x18004f556  mov     r9d, ebx; char *
0x18004f559  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18004f560  mov     edx, 15Ch; void *
0x18004f565  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004f56a  mov     edx, ebx; int
0x18004f56c  lea     rcx, aProcessFirmwar; "Process firmware update"
0x18004f573  call    ?PpfhLogEventGenericActivityError@@YAJPEBGJ@Z; PpfhLogEventGenericActivityError(ushort const *,long)
0x18004f578  mov     dword ptr [rsp+1C0h+var_190], ebx
0x18004f57c  lea     rax, [rsp+1C0h+var_190]
0x18004f581  mov     [rbp+0C0h+var_30], rax
0x18004f588  mov     [rbp+0C0h+var_28], 4
0x18004f593  lea     r9, [rbp+0C0h+var_30]
0x18004f59a  mov     r8d, 1
0x18004f5a0  lea     rdx, PCRPF_EVENT_FIRMWARE_UPDATE_PROCESSING_ERROR
0x18004f5a7  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x18004f5ae  call    cs:__imp_EtwEventWrite
0x18004f5b5  nop     dword ptr [rax+rax+00h]
0x18004f5ba  test    eax, eax
0x18004f5bc  jz      loc_18004F670
0x18004f5c2  mov     rcx, [rbp+0C8h]; this
0x18004f5c9  mov     r9d, eax; char *
0x18004f5cc  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18004f5d3  mov     edx, 1C7h; void *
0x18004f5d8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004f5dd  jmp     loc_18004F670
0x18004f5e2  cmp     dword ptr [rbx+8], 1
0x18004f5e6  jnz     short loc_18004F624
0x18004f5e8  lea     r9, aDevquerystatee; "DevQueryStateEnumCompleted"
0x18004f5ef  mov     r8, rsi; char *
0x18004f5f2  mov     edx, 167h; unsigned int
0x18004f5f7  lea     rcx, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18004f5fe  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18004f603  mov     rcx, [rdi]; hEvent
0x18004f606  call    cs:__imp_SetEvent
0x18004f60d  nop     dword ptr [rax+rax+00h]
0x18004f612  mov     rcx, [rbp+0C8h]
0x18004f619  test    eax, eax
0x18004f61b  jnz     short loc_18004F670
0x18004f61d  mov     edx, 168h
0x18004f622  jmp     short loc_18004F664
0x18004f624  cmp     dword ptr [rbx+8], 2
0x18004f628  jnz     short loc_18004F670
0x18004f62a  lea     r9, aDevquerystatea; "DevQueryStateAborted"
0x18004f631  mov     r8, rsi; char *
0x18004f634  mov     edx, 16Ch; unsigned int
0x18004f639  lea     rcx, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18004f640  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18004f645  mov     rcx, [rdi]; hEvent
0x18004f648  call    cs:__imp_SetEvent
0x18004f64f  nop     dword ptr [rax+rax+00h]
0x18004f654  mov     rcx, [rbp+0C8h]; this
0x18004f65b  test    eax, eax
0x18004f65d  jnz     short loc_18004F670
0x18004f65f  mov     edx, 16Dh; void *
0x18004f664  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18004f66b  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18004f670  lea     rcx, [rsp+1C0h+var_180]
0x18004f675  call    ?Stop@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18004f67a  nop
0x18004f67b  mov     [rsp+1C0h+var_180], r14
0x18004f680  lea     rcx, [rsp+1C0h+var_180]
0x18004f685  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18004f68a  lea     rcx, [rsp+1C0h+var_180]
0x18004f68f  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18004f694  nop
0x18004f695  mov     qword ptr [rsp+1C0h+var_1A0], rsi
0x18004f69a  lea     r9, aLeavingHs; "Leaving %hs"
0x18004f6a1  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18004f6a8  mov     edx, 89h; unsigned int
0x18004f6ad  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18004f6b4  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18004f6b9  nop
0x18004f6ba  mov     rcx, [rbp+0C0h+var_20]
0x18004f6c1  xor     rcx, rsp; StackCookie
0x18004f6c4  call    __security_check_cookie
0x18004f6c9  lea     r11, [rsp+1C0h+var_10]
0x18004f6d1  mov     rbx, [r11+20h]
0x18004f6d5  mov     rsi, [r11+38h]
0x18004f6d9  mov     rsp, r11
0x18004f6dc  pop     r14
0x18004f6de  pop     rdi
0x18004f6df  pop     rbp
0x18004f6e0  retn
```
