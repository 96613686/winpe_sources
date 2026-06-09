# ServiceModule::ServiceShutdown(void *)

- ea: `0x180016a9c`
- end: `0x180016e14`
- name: `?ServiceShutdown@ServiceModule@@SAKPEAX@Z`
- size: `888`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180012690`

## callees

- `0x18000538c`
- `0x180014894`
- `0x180016a9c`
- `0x1800171b8`
- `0x180019200`
- `0x1800204d4`
- `0x18002e4e4`
- `0x18003060c`
- `0x1800306f8`
- `0x180036010`

## import_xrefs

- `KERNEL32!UnregisterWaitEx` at `0x180016b38`
- `KERNEL32!UnregisterWaitEx` at `0x180016b38`
- `KERNEL32!FreeLibrary` at `0x180016d34`
- `KERNEL32!FreeLibrary` at `0x180016d34`
- `KERNEL32!CloseHandle` at `0x180016b9e`
- `KERNEL32!CloseHandle` at `0x180016b9e`
- `KERNEL32!DeleteCriticalSection` at `0x180016cdd`
- `KERNEL32!DeleteCriticalSection` at `0x180016cdd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016dac`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016dac`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016b15`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016b15`

## string_xrefs

- `0x180016d72`: `ServiceShutdownFinal`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ServiceModule::ServiceShutdown(void *a1)
{
  PVOID *v1; // rcx
  ServiceModule *v2; // rcx
  int v3; // ebx
  PVOID *v4; // rcx
  unsigned int Win32Error; // eax
  PVOID *v6; // rcx
  ServiceModule *v7; // rcx

  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids);
      v1 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 8) != 0 )
      WPP_SF_(v1[2], 35, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids);
  }
  CLchManager::ActivateLch(L"Shutdown");
  v3 = CoInitializeEx(0, 0);
  if ( v3 < 0 )
    goto LABEL_49;
  if ( WaitHandle )
  {
    if ( !UnregisterWaitEx(WaitHandle, 0) )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_14;
      Win32Error = HrFromLastWin32Error();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids, Win32Error);
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_14:
    WaitHandle = 0;
    goto LABEL_16;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    WPP_SF_(v4[2], 37, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids);
  CLchManager::ActivateLch(L"RevokeClassObjects");
  if ( g_pContextSwitcher )
  {
    (*(void (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)g_pContextSwitcher + 24LL))(
      g_pContextSwitcher,
      EnterDisconnectCallback,
      0,
      &IID_IContextCallback,
      5,
      0);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g_pContextSwitcher + 16LL))(g_pContextSwitcher);
  }
  g_pContextSwitcher = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids);
  CLchManager::ActivateLch(L"ReleaseSingletons");
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids);
  v3 = UninitializeEventHandler();
  if ( v3 >= 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( g_bHnetInitialized )
    {
      ReleaseObj(g_pHNetCfgMgr);
      DeleteCriticalSection(&g_csHNetCfgMgr);
      g_bHnetInitialized = 0;
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    {
      WPP_SF_(v6[2], 41, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( ghMsTcpDll )
    {
      ((void (__fastcall *)(PVOID *))gpfnStopWsdpSvc)(v6);
      FreeLibrary(ghMsTcpDll);
      ghMsTcpDll = 0;
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
      WPP_SF_(v6[2], 42, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids);
    ServiceModule::ReferenceRasman(v6, 2);
    CLchManager::ActivateLch(L"ServiceShutdownFinal");
    ServiceModule::SetServiceStatus(v7, 1u);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids);
  CoUninitialize();
  if ( v3 >= 0 )
    return 0;
LABEL_49:
  ServiceModule::SetServiceStatus(v2, 4u);
  switch ( v3 & 0x1FFF0000 )
  {
    case 983040:
      v3 = (unsigned __int16)v3 | 0xE0000000;
      break;
    case 458752:
      v3 = (unsigned __int16)v3;
      break;
    case 262144:
      v3 = 31;
      break;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180016a9c  mov     [rsp+arg_8], rbx
0x180016aa1  mov     [rsp+arg_10], rbp
0x180016aa6  mov     [rsp+arg_0], rcx
0x180016aab  push    r14
0x180016aad  sub     rsp, 40h
0x180016ab1  lea     rbp, WPP_GLOBAL_Control
0x180016ab8  lea     r14, WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids
0x180016abf  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ac6  cmp     rcx, rbp
0x180016ac9  jz      short loc_180016B05
0x180016acb  test    byte ptr [rcx+1Ch], 8
0x180016acf  jz      short loc_180016AE9
0x180016ad1  mov     edx, 22h ; '"'
0x180016ad6  mov     r8, r14
0x180016ad9  mov     rcx, [rcx+10h]
0x180016add  call    WPP_SF_
0x180016ae2  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ae9  cmp     rcx, rbp
0x180016aec  jz      short loc_180016B05
0x180016aee  test    byte ptr [rcx+1Ch], 8
0x180016af2  jz      short loc_180016B05
0x180016af4  mov     edx, 23h ; '#'
0x180016af9  mov     r8, r14
0x180016afc  mov     rcx, [rcx+10h]
0x180016b00  call    WPP_SF_
0x180016b05  lea     rcx, aShutdown; "Shutdown"
0x180016b0c  call    ?ActivateLch@CLchManager@@SAKPEBG@Z; CLchManager::ActivateLch(ushort const *)
0x180016b11  xor     edx, edx; dwCoInit
0x180016b13  xor     ecx, ecx; pvReserved
0x180016b15  call    cs:__imp_CoInitializeEx
0x180016b1b  mov     ebx, eax
0x180016b1d  test    eax, eax
0x180016b1f  js      loc_180016DBA
0x180016b25  mov     byte ptr [rsp+48h+arg_0], 1
0x180016b2a  mov     rcx, cs:WaitHandle; WaitHandle
0x180016b31  test    rcx, rcx
0x180016b34  jz      short loc_180016B88
0x180016b36  xor     edx, edx; CompletionEvent
0x180016b38  call    cs:__imp_UnregisterWaitEx
0x180016b3e  test    eax, eax
0x180016b40  jnz     short loc_180016B74
0x180016b42  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b49  cmp     rcx, rbp
0x180016b4c  jz      short loc_180016B7B
0x180016b4e  test    byte ptr [rcx+1Ch], 8
0x180016b52  jz      short loc_180016B7B
0x180016b54  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180016b59  mov     edx, 24h ; '$'
0x180016b5e  mov     r9d, eax
0x180016b61  mov     r8, r14
0x180016b64  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b6b  mov     rcx, [rcx+10h]
0x180016b6f  call    WPP_SF_d
0x180016b74  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b7b  mov     cs:WaitHandle, 0
0x180016b86  jmp     short loc_180016B8F
0x180016b88  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b8f  mov     rax, cs:hObject
0x180016b96  test    rax, rax
0x180016b99  jz      short loc_180016BB6
0x180016b9b  mov     rcx, rax; hObject
0x180016b9e  call    cs:__imp_CloseHandle
0x180016ba4  mov     cs:hObject, 0
0x180016baf  mov     rcx, cs:WPP_GLOBAL_Control
0x180016bb6  cmp     rcx, rbp
0x180016bb9  jz      short loc_180016BD2
0x180016bbb  test    byte ptr [rcx+1Ch], 8
0x180016bbf  jz      short loc_180016BD2
0x180016bc1  mov     edx, 25h ; '%'
0x180016bc6  mov     r8, r14
0x180016bc9  mov     rcx, [rcx+10h]
0x180016bcd  call    WPP_SF_
0x180016bd2  lea     rcx, aRevokeclassobj; "RevokeClassObjects"
0x180016bd9  call    ?ActivateLch@CLchManager@@SAKPEBG@Z; CLchManager::ActivateLch(ushort const *)
0x180016bde  mov     rcx, cs:?g_pContextSwitcher@@3PEAUIContextCallback@@EA; IContextCallback * g_pContextSwitcher
0x180016be5  test    rcx, rcx
0x180016be8  jz      short loc_180016C2B
0x180016bea  mov     rax, [rcx]
0x180016bed  mov     [rsp+48h+var_20], 0
0x180016bf6  mov     [rsp+48h+var_28], 5
0x180016bfe  lea     r9, IID_IContextCallback
0x180016c05  xor     r8d, r8d
0x180016c08  lea     rdx, ?EnterDisconnectCallback@@YAJPEAUtagComCallData@@@Z; EnterDisconnectCallback(tagComCallData *)
0x180016c0f  mov     rax, [rax+18h]
0x180016c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c18  mov     rcx, cs:?g_pContextSwitcher@@3PEAUIContextCallback@@EA; IContextCallback * g_pContextSwitcher
0x180016c1f  mov     rax, [rcx]
0x180016c22  mov     rax, [rax+10h]
0x180016c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c2b  mov     cs:?g_pContextSwitcher@@3PEAUIContextCallback@@EA, 0; IContextCallback * g_pContextSwitcher
0x180016c36  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c3d  cmp     rcx, rbp
0x180016c40  jz      short loc_180016C59
0x180016c42  test    byte ptr [rcx+1Ch], 8
0x180016c46  jz      short loc_180016C59
0x180016c48  mov     edx, 26h ; '&'
0x180016c4d  mov     r8, r14
0x180016c50  mov     rcx, [rcx+10h]
0x180016c54  call    WPP_SF_
0x180016c59  lea     rcx, aReleasesinglet; "ReleaseSingletons"
0x180016c60  call    ?ActivateLch@CLchManager@@SAKPEBG@Z; CLchManager::ActivateLch(ushort const *)
0x180016c65  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c6c  cmp     rcx, rbp
0x180016c6f  jz      short loc_180016C88
0x180016c71  test    byte ptr [rcx+1Ch], 8
0x180016c75  jz      short loc_180016C88
0x180016c77  mov     edx, 27h ; '''
0x180016c7c  mov     r8, r14
0x180016c7f  mov     rcx, [rcx+10h]
0x180016c83  call    WPP_SF_
0x180016c88  call    ?UninitializeEventHandler@@YAJXZ; UninitializeEventHandler(void)
0x180016c8d  mov     ebx, eax
0x180016c8f  test    eax, eax
0x180016c91  js      loc_180016D88
0x180016c97  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c9e  cmp     rcx, rbp
0x180016ca1  jz      short loc_180016CC1
0x180016ca3  test    byte ptr [rcx+1Ch], 8
0x180016ca7  jz      short loc_180016CC1
0x180016ca9  mov     edx, 28h ; '('
0x180016cae  mov     r8, r14
0x180016cb1  mov     rcx, [rcx+10h]
0x180016cb5  call    WPP_SF_
0x180016cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cc1  cmp     cs:?g_bHnetInitialized@@3HA, 0; int g_bHnetInitialized
0x180016cc8  jz      short loc_180016CF4
0x180016cca  mov     rcx, cs:?g_pHNetCfgMgr@@3PEAUIHNetCfgMgr@@EA; struct IUnknown *
0x180016cd1  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180016cd6  lea     rcx, ?g_csHNetCfgMgr@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180016cdd  call    cs:__imp_DeleteCriticalSection
0x180016ce3  mov     cs:?g_bHnetInitialized@@3HA, 0; int g_bHnetInitialized
0x180016ced  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cf4  cmp     rcx, rbp
0x180016cf7  jz      short loc_180016D17
0x180016cf9  test    byte ptr [rcx+1Ch], 8
0x180016cfd  jz      short loc_180016D17
0x180016cff  mov     edx, 29h ; ')'
0x180016d04  mov     r8, r14
0x180016d07  mov     rcx, [rcx+10h]
0x180016d0b  call    WPP_SF_
0x180016d10  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d17  cmp     cs:?ghMsTcpDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ghMsTcpDll
0x180016d1f  jz      short loc_180016D4C
0x180016d21  mov     rax, cs:?gpfnStopWsdpSvc@@3P6AXXZEA; void (*gpfnStopWsdpSvc)(void)
0x180016d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d2d  mov     rcx, cs:?ghMsTcpDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x180016d34  call    cs:__imp_FreeLibrary
0x180016d3a  mov     cs:?ghMsTcpDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ghMsTcpDll
0x180016d45  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d4c  cmp     rcx, rbp
0x180016d4f  jz      short loc_180016D68
0x180016d51  test    byte ptr [rcx+1Ch], 8
0x180016d55  jz      short loc_180016D68
0x180016d57  mov     edx, 2Ah ; '*'
0x180016d5c  mov     r8, r14
0x180016d5f  mov     rcx, [rcx+10h]
0x180016d63  call    WPP_SF_
0x180016d68  mov     edx, 2
0x180016d6d  call    ?ReferenceRasman@ServiceModule@@QEAAXW4RASREFTYPE@@@Z; ServiceModule::ReferenceRasman(RASREFTYPE)
0x180016d72  lea     rcx, aServiceshutdow; "ServiceShutdownFinal"
0x180016d79  call    ?ActivateLch@CLchManager@@SAKPEBG@Z; CLchManager::ActivateLch(ushort const *)
0x180016d7e  mov     edx, 1; unsigned int
0x180016d83  call    ?SetServiceStatus@ServiceModule@@QEAAXK@Z; ServiceModule::SetServiceStatus(ulong)
0x180016d88  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d8f  cmp     rcx, rbp
0x180016d92  jz      short loc_180016DAC
0x180016d94  test    byte ptr [rcx+1Ch], 8
0x180016d98  jz      short loc_180016DAC
0x180016d9a  mov     edx, 2Bh ; '+'
0x180016d9f  mov     r8, r14
0x180016da2  mov     rcx, [rcx+10h]
0x180016da6  call    WPP_SF_
0x180016dab  nop
0x180016dac  call    cs:__imp_CoUninitialize
0x180016db2  test    ebx, ebx
0x180016db4  js      short loc_180016DBA
0x180016db6  xor     eax, eax
0x180016db8  jmp     short loc_180016E03
0x180016dba  mov     edx, 4; unsigned int
0x180016dbf  call    ?SetServiceStatus@ServiceModule@@QEAAXK@Z; ServiceModule::SetServiceStatus(ulong)
0x180016dc4  mov     eax, ebx
0x180016dc6  mov     edx, 1FFF0000h
0x180016dcb  and     eax, edx
0x180016dcd  cmp     eax, 0F0000h
0x180016dd2  jnz     short loc_180016DDF
0x180016dd4  movzx   ebx, bx
0x180016dd7  or      ebx, 0E0000000h
0x180016ddd  jmp     short loc_180016E01
0x180016ddf  mov     eax, ebx
0x180016de1  and     eax, edx
0x180016de3  cmp     eax, 70000h
0x180016de8  jnz     short loc_180016DEF
0x180016dea  movzx   ebx, bx
0x180016ded  jmp     short loc_180016E01
0x180016def  mov     ecx, ebx
0x180016df1  and     ecx, edx
0x180016df3  mov     eax, 1Fh
0x180016df8  cmp     ecx, 40000h
0x180016dfe  cmovz   ebx, eax
0x180016e01  mov     eax, ebx
0x180016e03  mov     rbx, [rsp+48h+arg_8]
0x180016e08  mov     rbp, [rsp+48h+arg_10]
0x180016e0d  add     rsp, 40h
0x180016e11  pop     r14
0x180016e13  retn
```
