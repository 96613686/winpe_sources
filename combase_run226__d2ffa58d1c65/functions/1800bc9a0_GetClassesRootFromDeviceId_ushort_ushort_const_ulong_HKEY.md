# GetClassesRootFromDeviceId(ushort *,ushort const *,ulong,HKEY__ * *)

- ea: `0x1800bc9a0`
- end: `0x1800bcb20`
- name: `?GetClassesRootFromDeviceId@@YAJPEAGPEBGKPEAPEAUHKEY__@@@Z`
- size: `384`
- prototype: `HRESULT __fastcall(wchar_t *deviceInstanceId, const wchar_t *classesRootSubPath, unsigned int samDesired, HKEY__ **classesRootKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800bc928`

## callees

- `0x18000712c`
- `0x18003c7ec`
- `0x18005cde8`
- `0x18005ce60`
- `0x18006474c`
- `0x1800bc9a0`
- `0x18017101c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bcaf5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bcaf5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bcacc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bcacc`
- `CFGMGR32!CM_Open_DevNode_Key` at `0x1800bca68`
- `CFGMGR32!CM_Open_DevNode_Key` at `0x1800bca68`
- `CFGMGR32!CM_MapCrToWin32Err` at `0x1800bca1c`
- `CFGMGR32!CM_MapCrToWin32Err` at `0x1800bca8f`
- `CFGMGR32!CM_MapCrToWin32Err` at `0x1800bca1c`
- `CFGMGR32!CM_MapCrToWin32Err` at `0x1800bca8f`
- `CFGMGR32!CM_Locate_DevNodeW` at `0x1800bc9ee`
- `CFGMGR32!CM_Locate_DevNodeW` at `0x1800bc9ee`

## string_xrefs

- `0x1800bc9f4`: `onecore\com\combase\catalog\devicecatalog.cpp`

## pseudocode

```c
__int64 __fastcall GetClassesRootFromDeviceId(
        wchar_t *deviceInstanceId,
        const wchar_t *classesRootSubPath,
        REGSAM samDesired,
        HKEY__ **classesRootKey)
{
  __int64 v8; // rcx
  CONFIGRET v9; // eax
  CONFIGRET v10; // ebx
  DWORD v11; // eax
  unsigned int v12; // ebx
  CONFIGRET v13; // eax
  CONFIGRET v14; // ebx
  DWORD v15; // eax
  LSTATUS v16; // eax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (__cdecl*)(HKEY__ *),&RegCloseKey,wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t> > > deviceKey; // [rsp+30h] [rbp-18h] BYREF
  void *impersonationToken; // [rsp+38h] [rbp-10h] BYREF
  void *retaddr; // [rsp+78h] [rbp+30h]
  unsigned int deviceInstanceHandle; // [rsp+98h] [rbp+50h] BYREF

  impersonationToken = 0;
  if ( SuspendImpersonate(&impersonationToken) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8);
  *classesRootKey = 0;
  deviceInstanceHandle = 0;
  v9 = CM_Locate_DevNodeW(&deviceInstanceHandle, deviceInstanceId, 0);
  v10 = v9;
  if ( v9 )
    wil::details::in1diag3::_Log_Win32(retaddr, 0x1Au, "onecore\\com\\combase\\catalog\\devicecatalog.cpp", v9);
  v11 = CM_MapCrToWin32Err(v10, 0x3D0Fu);
  if ( v11 )
  {
    v12 = wil::details::in1diag3::Return_Win32(retaddr, 0x1Bu, "onecore\\com\\combase\\catalog\\devicecatalog.cpp", v11);
  }
  else
  {
    deviceKey.m_ptr = 0;
    v13 = CM_Open_DevNode_Key(deviceInstanceHandle, 0x20019u, 0, 1u, &deviceKey.m_ptr, 1u);
    v14 = v13;
    if ( v13 )
      wil::details::in1diag3::_Log_Win32(retaddr, 0x1Eu, "onecore\\com\\combase\\catalog\\devicecatalog.cpp", v13);
    v15 = CM_MapCrToWin32Err(v14, 0x3D0Fu);
    if ( v15 )
    {
      v12 = wil::details::in1diag3::Return_Win32(
              retaddr,
              0x1Fu,
              "onecore\\com\\combase\\catalog\\devicecatalog.cpp",
              v15);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&deviceKey);
    }
    else
    {
      v16 = RegOpenKeyExW(deviceKey.m_ptr, classesRootSubPath, 0, samDesired, classesRootKey);
      if ( v16 )
      {
        v12 = wil::details::in1diag3::Return_Win32(
                retaddr,
                0x25u,
                "onecore\\com\\combase\\catalog\\devicecatalog.cpp",
                v16);
        if ( deviceKey.m_ptr )
          RegCloseKey(deviceKey.m_ptr);
      }
      else
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&deviceKey);
        v12 = 0;
      }
    }
  }
  ResumeImpersonate(impersonationToken);
  return v12;
}

```

## disassembly

```asm
0x1800bc9a0  push    rbp
0x1800bc9a2  push    rbx
0x1800bc9a3  push    rsi
0x1800bc9a4  push    rdi
0x1800bc9a5  push    r12
0x1800bc9a7  push    r14
0x1800bc9a9  mov     rbp, rsp
0x1800bc9ac  sub     rsp, 48h
0x1800bc9b0  mov     rbx, deviceInstanceId
0x1800bc9b3  mov     [rbp+impersonationToken], 0
0x1800bc9bb  lea     deviceInstanceId, [rbp+impersonationToken]; pHandle
0x1800bc9bf  mov     rdi, classesRootKey
0x1800bc9c2  mov     esi, samDesired
0x1800bc9c5  mov     r14, classesRootSubPath
0x1800bc9c8  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x1800bc9cd  test    eax, eax
0x1800bc9cf  jns     short loc_1800BC9D6
0x1800bc9d1  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(SuspendImpersonate(&impersonationToken))")
0x1800bc9d6  xor     samDesired, samDesired; ulFlags
0x1800bc9d9  mov     qword ptr [rdi], 0
0x1800bc9e0  mov     classesRootSubPath, rbx; pDeviceID
0x1800bc9e3  mov     [rbp+deviceInstanceHandle], 0
0x1800bc9ea  lea     deviceInstanceId, [rbp+deviceInstanceHandle]; pdnDevInst
0x1800bc9ee  call    cs:__imp_CM_Locate_DevNodeW
0x1800bc9f4  lea     r12, aOnecoreComComb_140; "onecore\\com\\combase\\catalog\\devicec"...
0x1800bc9fb  mov     ebx, eax
0x1800bc9fd  test    eax, eax
0x1800bc9ff  jz      short loc_1800BCA15
0x1800bca01  mov     deviceInstanceId, [rbp+30h]; callerReturnAddress
0x1800bca05  mov     r9d, eax; err
0x1800bca08  mov     r8, r12; fileName
0x1800bca0b  mov     edx, 1Ah; lineNumber
0x1800bca10  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800bca15  mov     edx, 3D0Fh; DefaultErr
0x1800bca1a  mov     ecx, ebx; CmReturnCode
0x1800bca1c  call    cs:__imp_CM_MapCrToWin32Err
0x1800bca22  test    eax, eax
0x1800bca24  jz      short loc_1800BCA41
0x1800bca26  mov     deviceInstanceId, [rbp+30h]; callerReturnAddress
0x1800bca2a  mov     r9d, eax; err
0x1800bca2d  mov     r8, r12; fileName
0x1800bca30  mov     edx, 1Bh; lineNumber
0x1800bca35  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800bca3a  mov     ebx, eax
0x1800bca3c  jmp     loc_1800BCB08
0x1800bca41  mov     ecx, [rbp+deviceInstanceHandle]; dnDevNode
0x1800bca44  lea     rax, [rbp+deviceKey]
0x1800bca48  mov     r9d, 1; Disposition
0x1800bca4e  mov     [rbp+deviceKey.m_ptr], 0
0x1800bca56  mov     [rsp+48h+ulFlags], r9d; ulFlags
0x1800bca5b  xor     samDesired, samDesired; ulHardwareProfile
0x1800bca5e  mov     edx, 20019h; samDesired
0x1800bca63  mov     [rsp+48h+phkDevice], rax; phkDevice
0x1800bca68  call    cs:__imp_CM_Open_DevNode_Key
0x1800bca6e  mov     ebx, eax
0x1800bca70  test    eax, eax
0x1800bca72  jz      short loc_1800BCA88
0x1800bca74  mov     deviceInstanceId, [rbp+30h]; callerReturnAddress
0x1800bca78  mov     r9d, eax; err
0x1800bca7b  mov     r8, r12; fileName
0x1800bca7e  mov     edx, 1Eh; lineNumber
0x1800bca83  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800bca88  mov     edx, 3D0Fh; DefaultErr
0x1800bca8d  mov     ecx, ebx; CmReturnCode
0x1800bca8f  call    cs:__imp_CM_MapCrToWin32Err
0x1800bca95  test    eax, eax
0x1800bca97  jz      short loc_1800BCABA
0x1800bca99  mov     deviceInstanceId, [rbp+30h]; callerReturnAddress
0x1800bca9d  mov     r9d, eax; err
0x1800bcaa0  mov     r8, r12; fileName
0x1800bcaa3  mov     edx, 1Fh; lineNumber
0x1800bcaa8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800bcaad  lea     deviceInstanceId, [rbp+deviceKey]; this
0x1800bcab1  mov     ebx, eax
0x1800bcab3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800bcab8  jmp     short loc_1800BCB08
0x1800bcaba  mov     deviceInstanceId, [rbp+deviceKey.m_ptr]; hKey
0x1800bcabe  mov     r9d, esi; samDesired
0x1800bcac1  xor     samDesired, samDesired; ulOptions
0x1800bcac4  mov     [rsp+48h+phkDevice], rdi; phkResult
0x1800bcac9  mov     classesRootSubPath, r14; lpSubKey
0x1800bcacc  call    cs:__imp_RegOpenKeyExW
0x1800bcad2  test    eax, eax
0x1800bcad4  jz      short loc_1800BCAFD
0x1800bcad6  mov     deviceInstanceId, [rbp+30h]; callerReturnAddress
0x1800bcada  mov     r9d, eax; err
0x1800bcadd  mov     r8, r12; fileName
0x1800bcae0  mov     edx, 25h ; '%'; lineNumber
0x1800bcae5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800bcaea  mov     deviceInstanceId, [rbp+deviceKey.m_ptr]; hKey
0x1800bcaee  mov     ebx, eax
0x1800bcaf0  test    deviceInstanceId, deviceInstanceId
0x1800bcaf3  jz      short loc_1800BCB08
0x1800bcaf5  call    cs:__imp_RegCloseKey
0x1800bcafb  jmp     short loc_1800BCB08
0x1800bcafd  lea     deviceInstanceId, [rbp+deviceKey]; this
0x1800bcb01  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800bcb06  xor     ebx, ebx
0x1800bcb08  mov     deviceInstanceId, [rbp+impersonationToken]; hToken
0x1800bcb0c  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x1800bcb11  mov     eax, ebx
0x1800bcb13  add     rsp, 48h
0x1800bcb17  pop     r14
0x1800bcb19  pop     r12
0x1800bcb1b  pop     rdi
0x1800bcb1c  pop     rsi
0x1800bcb1d  pop     rbx
0x1800bcb1e  pop     rbp
0x1800bcb1f  retn
```
