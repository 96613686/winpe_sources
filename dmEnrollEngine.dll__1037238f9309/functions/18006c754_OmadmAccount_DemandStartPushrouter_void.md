# OmadmAccount::DemandStartPushrouter(void)

- ea: `0x18006c754`
- end: `0x18006c8e7`
- name: `?DemandStartPushrouter@OmadmAccount@@AEAAJXZ`
- size: `403`
- prototype: `__int64 __fastcall(OmadmAccount *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006c8f0`

## callees

- `0x18000e508`
- `0x18003b0bc`
- `0x18006c754`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c7dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c7dc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006c892`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006c89b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006c892`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006c89b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18006c80a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18006c80a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18006c7ce`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18006c7ce`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18006c866`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18006c866`

## string_xrefs

- `0x18006c800`: `dmwappushservice`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OmadmAccount::DemandStartPushrouter(OmadmAccount *this)
{
  SC_HANDLE v1; // rdi
  SC_HANDLE v2; // rsi
  signed int v3; // ebx
  SC_HANDLE v4; // rax
  signed int LastError; // eax
  SC_HANDLE v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v10; // [rsp+70h] [rbp+8h] BYREF
  __int64 v11; // [rsp+78h] [rbp+10h] BYREF

  v10 = 0;
  v11 = 0;
  v1 = 0;
  v2 = 0;
  v3 = ((__int64 (__fastcall *)(void ***, __int64, __int64 *))off_1800AF740[4])(&off_1800AF740, 222306401, &v10);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 24LL))(v10, &v11);
    if ( v3 == 1 )
    {
      v4 = OpenSCManagerW(0, 0, 1u);
      v1 = v4;
      if ( v4
        && (v6 = OpenServiceW(v4, L"dmwappushservice", 2u), (v2 = v6) != 0)
        && ChangeServiceConfigW(v6, 0xFFFFFFFF, 3u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 2) != 0 )
          McTemplateU0d_EventWriteTransfer(v7, EnterpriseDiagnosticsDemandStartingPushRouter, 1);
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  CloseServiceHandle(v2);
  CloseServiceHandle(v1);
  if ( v3 < 0 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    McTemplateU0d_EventWriteTransfer(v8, EnterpriseDiagnosticsDemandStartingPushRouterFailed, (unsigned int)v3);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v11);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v10);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18006c754  mov     r11, rsp
0x18006c757  mov     [r11+18h], rbx
0x18006c75b  mov     [r11+20h], rsi
0x18006c75f  mov     [r11+8], rcx
0x18006c763  push    rdi
0x18006c764  sub     rsp, 60h
0x18006c768  mov     qword ptr [r11+8], 0
0x18006c770  mov     qword ptr [r11+10h], 0
0x18006c778  xor     edi, edi
0x18006c77a  xor     esi, esi
0x18006c77c  mov     rax, cs:off_1800AF740
0x18006c783  lea     r8, [r11+8]
0x18006c787  mov     edx, 0D402061h
0x18006c78c  lea     rcx, off_1800AF740
0x18006c793  mov     rax, [rax+20h]
0x18006c797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c79c  mov     ebx, eax
0x18006c79e  test    eax, eax
0x18006c7a0  js      loc_18006C88F
0x18006c7a6  mov     rcx, [rsp+68h+arg_0]
0x18006c7ab  mov     rax, [rcx]
0x18006c7ae  lea     rdx, [rsp+68h+arg_8]
0x18006c7b3  mov     rax, [rax+18h]
0x18006c7b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c7bc  mov     ebx, eax
0x18006c7be  cmp     eax, 1
0x18006c7c1  jnz     loc_18006C88F
0x18006c7c7  xor     edx, edx; lpDatabaseName
0x18006c7c9  xor     ecx, ecx; lpMachineName
0x18006c7cb  mov     r8d, eax; dwDesiredAccess
0x18006c7ce  call    cs:__imp_OpenSCManagerW
0x18006c7d4  mov     rdi, rax
0x18006c7d7  test    rax, rax
0x18006c7da  jnz     short loc_18006C7FA
0x18006c7dc  call    cs:__imp_GetLastError
0x18006c7e2  mov     ebx, eax
0x18006c7e4  test    eax, eax
0x18006c7e6  jle     loc_18006C88F
0x18006c7ec  movzx   ebx, ax
0x18006c7ef  or      ebx, 80070000h
0x18006c7f5  jmp     loc_18006C88F
0x18006c7fa  mov     r8d, 2; dwDesiredAccess
0x18006c800  lea     rdx, ServiceName; "dmwappushservice"
0x18006c807  mov     rcx, rax; hSCManager
0x18006c80a  call    cs:__imp_OpenServiceW
0x18006c810  mov     rsi, rax
0x18006c813  test    rax, rax
0x18006c816  jz      short loc_18006C7DC
0x18006c818  mov     [rsp+68h+lpDisplayName], 0; lpDisplayName
0x18006c821  mov     [rsp+68h+lpPassword], 0; lpPassword
0x18006c82a  mov     [rsp+68h+lpServiceStartName], 0; lpServiceStartName
0x18006c833  mov     [rsp+68h+lpDependencies], 0; lpDependencies
0x18006c83c  mov     [rsp+68h+lpdwTagId], 0; lpdwTagId
0x18006c845  mov     [rsp+68h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x18006c84e  mov     [rsp+68h+lpBinaryPathName], 0; lpBinaryPathName
0x18006c857  or      edx, 0FFFFFFFFh; dwServiceType
0x18006c85a  mov     r9d, edx; dwErrorControl
0x18006c85d  mov     r8d, 3; dwStartType
0x18006c863  mov     rcx, rax; hService
0x18006c866  call    cs:__imp_ChangeServiceConfigW
0x18006c86c  test    eax, eax
0x18006c86e  jz      loc_18006C7DC
0x18006c874  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 2
0x18006c87b  jz      short loc_18006C88F
0x18006c87d  mov     r8d, 1
0x18006c883  lea     rdx, EnterpriseDiagnosticsDemandStartingPushRouter
0x18006c88a  call    McTemplateU0d_EventWriteTransfer
0x18006c88f  mov     rcx, rsi; hSCObject
0x18006c892  call    cs:__imp_CloseServiceHandle
0x18006c898  mov     rcx, rdi; hSCObject
0x18006c89b  call    cs:__imp_CloseServiceHandle
0x18006c8a1  test    ebx, ebx
0x18006c8a3  jns     short loc_18006C8BE
0x18006c8a5  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x18006c8ac  jz      short loc_18006C8BE
0x18006c8ae  mov     r8d, ebx
0x18006c8b1  lea     rdx, EnterpriseDiagnosticsDemandStartingPushRouterFailed
0x18006c8b8  call    McTemplateU0d_EventWriteTransfer
0x18006c8bd  nop
0x18006c8be  lea     rcx, [rsp+68h+arg_8]
0x18006c8c3  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18006c8c8  nop
0x18006c8c9  lea     rcx, [rsp+68h+arg_0]
0x18006c8ce  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18006c8d3  mov     eax, ebx
0x18006c8d5  lea     r11, [rsp+68h+var_8]
0x18006c8da  mov     rbx, [r11+20h]
0x18006c8de  mov     rsi, [r11+28h]
0x18006c8e2  mov     rsp, r11
0x18006c8e5  pop     rdi
0x18006c8e6  retn
```
