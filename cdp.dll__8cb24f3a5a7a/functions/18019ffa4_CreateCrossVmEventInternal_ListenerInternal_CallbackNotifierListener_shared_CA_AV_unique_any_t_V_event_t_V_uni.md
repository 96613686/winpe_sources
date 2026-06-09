# ?CreateCrossVmEventInternal@ListenerInternal@CallbackNotifierListener@shared@@CA?AV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@AEBVCDP_UUID@cdp@@@Z

- ea: `0x18019ffa4`
- end: `0x1801a0204`
- name: `?CreateCrossVmEventInternal@ListenerInternal@CallbackNotifierListener@shared@@CA?AV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@AEBVCDP_UUID@cdp@@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x18009240c`

## callees

- `0x1800624cc`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x18011d8c4`
- `0x180143248`
- `0x18019ffa4`
- `0x1801a020c`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18019ffe0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18019ffe0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801a003b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801a003b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801a0171`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801a0171`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019ffeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019ffeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0049`
- `ntdll!RtlNtStatusToDosError` at `0x1801a013a`
- `ntdll!RtlNtStatusToDosError` at `0x1801a013a`

## string_xrefs

- `0x1801a019c`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1801a0031`: `NtCreateCrossVmEvent`
- `0x18019ffd9`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
const char *__fastcall shared::CallbackNotifierListener::ListenerInternal::CreateCrossVmEventInternal(
        const char *a1,
        __int128 *a2)
{
  HMODULE ModuleHandleA; // rax
  signed int LastError; // eax
  __int64 v6; // rax
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v8)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // rsi
  signed int v9; // eax
  __int64 v10; // rax
  int v11; // ebx
  NTSTATUS v12; // eax
  signed int v13; // eax
  unsigned int v14; // ebx
  int v15; // ecx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  const char *v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  char v23; // [rsp+50h] [rbp-B0h]
  int v24; // [rsp+58h] [rbp-A8h]
  unsigned int v25; // [rsp+5Ch] [rbp-A4h] BYREF
  _QWORD v26[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v28[24]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v29[56]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v30; // [rsp+F8h] [rbp-8h] BYREF

  v26[1] = a1;
  v24 = 0;
  ModuleHandleA = GetModuleHandleA("ntdll.dll");
  if ( !ModuleHandleA )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v21 = ".\\callbacknotifierlistener.cpp";
    LODWORD(v22) = 243;
    v6 = cdp::MakeException<cdp::hresult_exception>(v29, &v21, (unsigned int)LastError);
    cdp::CdpThrow<cdp::hresult_exception>(&v21, v6);
  }
  ProcAddress = GetProcAddress(ModuleHandleA, "NtCreateCrossVmEvent");
  v8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
  if ( !ProcAddress )
  {
    v9 = GetLastError();
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    v21 = ".\\callbacknotifierlistener.cpp";
    LODWORD(v22) = 245;
    v10 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v21, (unsigned int)v9);
    cdp::CdpThrow<cdp::hresult_exception>(&v21, v10);
  }
  *(_QWORD *)a1 = 0;
  v24 = 1;
  v30 = *a2;
  v21 = a1;
  v22 = 0;
  v23 = 1;
  v11 = ((__int64 (__fastcall *)(__int64 *, __int64, _QWORD, _QWORD, __int128 *, _QWORD))ProcAddress)(
          &v22,
          2031619,
          0,
          0,
          &v30,
          0);
  __1__out_param_t_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAA_XZ(&v21);
  if ( v11 < 0 )
  {
    v21 = a1;
    v22 = 0;
    v23 = 1;
    v12 = v8(&v22, 2031619, 0, 0, &v30, 0);
    v13 = RtlNtStatusToDosError(v12);
    v14 = v13;
    if ( v13 > 0 )
      v14 = (unsigned __int16)v13 | 0x80070000;
    __1__out_param_t_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAA_XZ(&v21);
    v21 = ".\\callbacknotifierlistener.cpp";
    LODWORD(v22) = 250;
    v25 = v14;
    v26[0] = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v15,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v25,
      (unsigned int)&v21,
      (__int64)&v22,
      (__int64)v26);
    v16 = cdp::ExceptionStackFromSourceLocationInfo(v28, &v21);
    v19 = cdp::ErrorCodeToString(v14, v17, v18, v16);
    ConnectedDevices::Exception::Exception(pExceptionObject, v14, v19);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x18019ffa4  mov     [rsp-8+arg_10], rbx
0x18019ffa9  push    rbp
0x18019ffaa  push    rsi
0x18019ffab  push    rdi
0x18019ffac  lea     rbp, [rsp-10h]
0x18019ffb1  sub     rsp, 110h
0x18019ffb8  mov     rax, cs:__security_cookie
0x18019ffbf  xor     rax, rsp
0x18019ffc2  mov     [rbp+20h+var_18], rax
0x18019ffc6  mov     rbx, rdx
0x18019ffc9  mov     rdi, rcx
0x18019ffcc  mov     [rsp+120h+var_B8], rcx
0x18019ffd1  mov     [rsp+120h+var_C8], 0
0x18019ffd9  lea     rcx, ModuleName; "ntdll.dll"
0x18019ffe0  call    cs:__imp_GetModuleHandleA
0x18019ffe6  test    rax, rax
0x18019ffe9  jnz     short loc_1801A0031
0x18019ffeb  call    cs:__imp_GetLastError
0x18019fff1  test    eax, eax
0x18019fff3  jle     short loc_18019FFFD
0x18019fff5  movzx   eax, ax
0x18019fff8  or      eax, 80070000h
0x18019fffd  lea     rcx, aCallbacknotifi; ".\\callbacknotifierlistener.cpp"
0x1801a0004  mov     [rsp+120h+var_E0], rcx
0x1801a0009  mov     dword ptr [rsp+120h+var_D8], 0F3h
0x1801a0011  mov     r8d, eax
0x1801a0014  lea     rdx, [rsp+120h+var_E0]
0x1801a0019  lea     rcx, [rbp+20h+var_60]
0x1801a001d  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1801a0022  nop
0x1801a0023  mov     rdx, rax
0x1801a0026  lea     rcx, [rsp+120h+var_E0]
0x1801a002b  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801a0031  lea     rdx, ProcName; "NtCreateCrossVmEvent"
0x1801a0038  mov     rcx, rax; hModule
0x1801a003b  call    cs:__imp_GetProcAddress
0x1801a0041  mov     rsi, rax
0x1801a0044  test    rax, rax
0x1801a0047  jnz     short loc_1801A0090
0x1801a0049  call    cs:__imp_GetLastError
0x1801a004f  test    eax, eax
0x1801a0051  jle     short loc_1801A005B
0x1801a0053  movzx   eax, ax
0x1801a0056  or      eax, 80070000h
0x1801a005b  lea     rcx, aCallbacknotifi; ".\\callbacknotifierlistener.cpp"
0x1801a0062  mov     [rsp+120h+var_E0], rcx
0x1801a0067  mov     dword ptr [rsp+120h+var_D8], 0F5h
0x1801a006f  mov     r8d, eax
0x1801a0072  lea     rdx, [rsp+120h+var_E0]
0x1801a0077  lea     rcx, [rsp+120h+pExceptionObject]
0x1801a007c  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1801a0081  nop
0x1801a0082  mov     rdx, rax
0x1801a0085  lea     rcx, [rsp+120h+var_E0]
0x1801a008a  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801a0090  mov     qword ptr [rdi], 0
0x1801a0097  mov     [rsp+120h+var_C8], 1
0x1801a009f  movups  xmm0, xmmword ptr [rbx]
0x1801a00a2  movdqu  [rbp+20h+var_28], xmm0
0x1801a00a7  mov     [rsp+120h+var_E0], rdi
0x1801a00ac  mov     [rsp+120h+var_D8], 0
0x1801a00b5  mov     [rsp+120h+var_D0], 1
0x1801a00ba  mov     [rsp+120h+var_F8], 0
0x1801a00c3  lea     rax, [rbp+20h+var_28]
0x1801a00c7  mov     [rsp+120h+var_100], rax
0x1801a00cc  xor     r9d, r9d
0x1801a00cf  xor     r8d, r8d
0x1801a00d2  mov     edx, 1F0003h
0x1801a00d7  lea     rcx, [rsp+120h+var_D8]
0x1801a00dc  mov     rax, rsi
0x1801a00df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a00e4  mov     ebx, eax
0x1801a00e6  lea     rcx, [rsp+120h+var_E0]
0x1801a00eb  call    ??1?$out_param_t@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAA@XZ
0x1801a00f0  shr     ebx, 1Fh
0x1801a00f3  test    bl, bl
0x1801a00f5  jz      loc_1801A01E1
0x1801a00fb  mov     [rsp+120h+var_E0], rdi
0x1801a0100  mov     [rsp+120h+var_D8], 0
0x1801a0109  mov     [rsp+120h+var_D0], 1
0x1801a010e  mov     [rsp+120h+var_F8], 0
0x1801a0117  lea     rax, [rbp+20h+var_28]
0x1801a011b  mov     [rsp+120h+var_100], rax
0x1801a0120  xor     r9d, r9d
0x1801a0123  xor     r8d, r8d
0x1801a0126  mov     edx, 1F0003h
0x1801a012b  lea     rcx, [rsp+120h+var_D8]
0x1801a0130  mov     rax, rsi
0x1801a0133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a0138  mov     ecx, eax; Status
0x1801a013a  call    cs:__imp_RtlNtStatusToDosError
0x1801a0140  mov     ebx, eax
0x1801a0142  test    eax, eax
0x1801a0144  jle     short loc_1801A014F
0x1801a0146  movzx   ebx, ax
0x1801a0149  or      ebx, 80070000h
0x1801a014f  lea     rcx, [rsp+120h+var_E0]
0x1801a0154  call    ??1?$out_param_t@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAA@XZ
0x1801a0159  lea     rcx, aCallbacknotifi; ".\\callbacknotifierlistener.cpp"
0x1801a0160  mov     [rsp+120h+var_E0], rcx
0x1801a0165  mov     dword ptr [rsp+120h+var_D8], 0FAh
0x1801a016d  mov     [rsp+120h+var_C4], ebx
0x1801a0171  call    cs:__imp_GetCurrentThreadId
0x1801a0177  mov     eax, eax
0x1801a0179  mov     [rsp+120h+var_C0], rax
0x1801a017e  lea     rax, [rsp+120h+var_C0]
0x1801a0183  mov     [rsp+120h+var_F8], rax
0x1801a0188  lea     rax, [rsp+120h+var_D8]
0x1801a018d  mov     [rsp+120h+var_100], rax
0x1801a0192  lea     r9, [rsp+120h+var_E0]
0x1801a0197  lea     r8, [rsp+120h+var_C4]
0x1801a019c  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801a01a3  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801a01a8  lea     rdx, [rsp+120h+var_E0]
0x1801a01ad  lea     rcx, [rbp+20h+var_78]
0x1801a01b1  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801a01b6  mov     r9, rax
0x1801a01b9  mov     ecx, ebx
0x1801a01bb  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801a01c0  mov     r8, rax
0x1801a01c3  mov     edx, ebx
0x1801a01c5  lea     rcx, [rsp+120h+pExceptionObject]
0x1801a01ca  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801a01cf  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801a01d6  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1801a01db  call    _CxxThrowException_0
0x1801a01e1  mov     rax, rdi
0x1801a01e4  mov     rcx, [rbp+20h+var_18]
0x1801a01e8  xor     rcx, rsp; StackCookie
0x1801a01eb  call    __security_check_cookie
0x1801a01f0  mov     rbx, [rsp+120h+arg_10]
0x1801a01f8  add     rsp, 110h
0x1801a01ff  pop     rdi
0x1801a0200  pop     rsi
0x1801a0201  pop     rbp
0x1801a0202  retn
```
