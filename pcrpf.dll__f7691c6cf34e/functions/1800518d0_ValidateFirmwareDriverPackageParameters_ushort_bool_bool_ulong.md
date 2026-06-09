# ValidateFirmwareDriverPackageParameters(ushort *,bool *,bool *,ulong *)

- ea: `0x1800518d0`
- end: `0x180051c98`
- name: `?ValidateFirmwareDriverPackageParameters@@YAJPEAGPEA_N1PEAK@Z`
- size: `968`
- prototype: `int __fastcall(DEVINSTID_W pDeviceID, bool *, bool *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18004fe98`

## callees

- `0x180009c64`
- `0x18000c9a4`
- `0x18000dfe0`
- `0x180013e6c`
- `0x18002d5ec`
- `0x180033924`
- `0x1800518d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051a1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051a92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051abc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051bed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051c17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051a1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051a92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051abc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051bed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051c17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051a2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051aa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051ad0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051c01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051c2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051a2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051aa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051ad0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051c01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051c2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800519ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051ae6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051c41`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800519ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051ae6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051c41`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051b74`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051b74`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18005190b`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18005190b`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x180051977`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x180051977`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180051920`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180051987`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180051920`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180051987`

## string_xrefs

- `0x180051937`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x18005199e`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x180051a00`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x180051a77`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x180051b28`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x180051ba2`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x180051bd2`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x180051c7f`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
int __fastcall ValidateFirmwareDriverPackageParameters(DEVINSTID_W pDeviceID, bool *a2, bool *a3, unsigned int *a4)
{
  CONFIGRET v7; // eax
  DWORD v8; // eax
  CONFIGRET v10; // eax
  DWORD v11; // eax
  int v12; // ebx
  unsigned __int16 **v13; // rax
  int RegString; // eax
  void *v15; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 **v17; // rax
  int v18; // eax
  int v19; // edi
  void *v20; // rbx
  HANDLE v21; // rax
  void *v22; // rbx
  HANDLE v23; // rax
  unsigned int ValueW; // eax
  unsigned int v25; // eax
  void *v26; // rbx
  HANDLE v27; // rax
  void *v28; // rbx
  HANDLE v29; // rax
  unsigned int phkDevice; // [rsp+20h] [rbp-40h]
  unsigned int phkDevicea; // [rsp+20h] [rbp-40h]
  unsigned int phkDeviceb; // [rsp+20h] [rbp-40h]
  const char *ulFlags; // [rsp+28h] [rbp-38h]
  HKEY hKey; // [rsp+40h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-18h] BYREF
  LPVOID v36[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  unsigned int pvData; // [rsp+98h] [rbp+38h] BYREF
  DEVNODE pdnDevInst; // [rsp+A0h] [rbp+40h] BYREF
  DWORD pcbData; // [rsp+A8h] [rbp+48h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  pdnDevInst = 0;
  v7 = CM_Locate_DevNodeW(&pdnDevInst, pDeviceID, 0);
  v8 = CM_MapCrToWin32Err(v7, 0xDu);
  if ( v8 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x8D,
             (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
             (const char *)v8,
             phkDevice);
  hKey = 0;
  v10 = CM_Open_DevNode_Key(pdnDevInst, 0x20019u, 0, 1u, &hKey, 0);
  v11 = CM_MapCrToWin32Err(v10, 0xDu);
  if ( v11 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x90,
            (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
            (const char *)v11,
            phkDevicea);
LABEL_5:
    if ( hKey )
      RegCloseKey(hKey);
    return v12;
  }
  lpMem = 0;
  v13 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&(&lpMem);
  RegString = PpfhReadRegString(hKey, 0, L"FirmwareCapsuleFilename", v13);
  v12 = RegString;
  if ( RegString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
      (const char *)(unsigned int)RegString,
      phkDevicea);
    v15 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v15);
    }
    goto LABEL_5;
  }
  v36[0] = 0;
  v17 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&(v36);
  v18 = PpfhReadRegString(hKey, 0, L"FirmwareMeasurementsFilename", v17);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
      (const char *)(unsigned int)v18,
      phkDevicea);
LABEL_13:
    v20 = v36[0];
    if ( v36[0] )
    {
      v21 = GetProcessHeap();
      HeapFree(v21, 0, v20);
    }
    v22 = lpMem;
    if ( lpMem )
    {
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v22);
    }
    if ( hKey )
      RegCloseKey(hKey);
    return v19;
  }
  if ( lpMem && v36[0] )
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
      0x9Fu,
      "ValidateFirmwareDriverPackageParameters",
      "FirmwareCapsuleFileName = %ws, FirmwareMeasurementsFileName = %ws",
      lpMem,
      v36[0]);
    *a2 = 1;
  }
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(hKey, 0, L"FirmwarePcrChangeMask", 0x20000010u, 0, &pvData, &pcbData);
  if ( ValueW )
  {
    if ( ValueW != 2 )
    {
      v19 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xB9,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
              (const char *)ValueW,
              phkDeviceb);
      goto LABEL_13;
    }
  }
  else
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
      0xABu,
      "ValidateFirmwareDriverPackageParameters",
      "firmwarePcrChangeMask: 0x%x",
      pvData);
    v25 = pvData;
    if ( (pvData & 0xFFFFFFEA) != 0 )
    {
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xAF,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
        (const char *)0x80070057LL,
        (int)"Unsupported PCRs in FirmwarePcrChangeMask",
        ulFlags);
    }
    else
    {
      *a3 = 1;
      *a4 = v25;
    }
  }
  v26 = v36[0];
  if ( v36[0] )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v26);
  }
  v28 = lpMem;
  if ( lpMem )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v28);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800518d0  mov     [rsp-28h+arg_0], rbx
0x1800518d5  push    rbp
0x1800518d6  push    rsi
0x1800518d7  push    rdi
0x1800518d8  push    r14
0x1800518da  push    r15
0x1800518dc  mov     rbp, rsp
0x1800518df  sub     rsp, 60h
0x1800518e3  mov     rsi, r9
0x1800518e6  mov     r14, r8
0x1800518e9  mov     r15, rdx
0x1800518ec  mov     byte ptr [rdx], 0
0x1800518ef  mov     byte ptr [r8], 0
0x1800518f3  mov     dword ptr [r9], 0
0x1800518fa  mov     [rbp+pdnDevInst], 0
0x180051901  xor     r8d, r8d; ulFlags
0x180051904  mov     rdx, rcx; pDeviceID
0x180051907  lea     rcx, [rbp+pdnDevInst]; pdnDevInst
0x18005190b  call    cs:__imp_CM_Locate_DevNodeW
0x180051912  nop     dword ptr [rax+rax+00h]
0x180051917  mov     ecx, eax; CmReturnCode
0x180051919  mov     ebx, 0Dh
0x18005191e  mov     edx, ebx; DefaultErr
0x180051920  call    cs:__imp_CM_MapCrToWin32Err
0x180051927  nop     dword ptr [rax+rax+00h]
0x18005192c  test    eax, eax
0x18005192e  jz      short loc_18005194D
0x180051930  mov     rcx, [rbp+28h]; this
0x180051934  mov     r9d, eax; char *
0x180051937  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18005193e  mov     edx, 8Dh; void *
0x180051943  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180051948  jmp     loc_180051C4F
0x18005194d  mov     [rbp+hKey], 0
0x180051955  mov     [rsp+60h+ulFlags], 0; ulFlags
0x18005195d  lea     rax, [rbp+hKey]
0x180051961  mov     [rsp+60h+phkDevice], rax; int
0x180051966  mov     r9d, 1; Disposition
0x18005196c  xor     r8d, r8d; ulHardwareProfile
0x18005196f  mov     edx, 20019h; samDesired
0x180051974  mov     ecx, [rbp+pdnDevInst]; dnDevNode
0x180051977  call    cs:__imp_CM_Open_DevNode_Key
0x18005197e  nop     dword ptr [rax+rax+00h]
0x180051983  mov     ecx, eax; CmReturnCode
0x180051985  mov     edx, ebx; DefaultErr
0x180051987  call    cs:__imp_CM_MapCrToWin32Err
0x18005198e  nop     dword ptr [rax+rax+00h]
0x180051993  test    eax, eax
0x180051995  jz      short loc_1800519CD
0x180051997  mov     rcx, [rbp+28h]; this
0x18005199b  mov     r9d, eax; char *
0x18005199e  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x1800519a5  mov     edx, 90h; void *
0x1800519aa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800519af  mov     ebx, eax
0x1800519b1  mov     rcx, [rbp+hKey]; hKey
0x1800519b5  test    rcx, rcx
0x1800519b8  jz      short loc_1800519C6
0x1800519ba  call    cs:__imp_RegCloseKey
0x1800519c1  nop     dword ptr [rax+rax+00h]
0x1800519c6  mov     eax, ebx
0x1800519c8  jmp     loc_180051C4F
0x1800519cd  mov     [rbp+lpMem], 0
0x1800519d5  lea     rcx, [rbp+lpMem]
0x1800519d9  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator&(void)
0x1800519de  mov     r9, rax; unsigned __int16 **
0x1800519e1  lea     r8, aFirmwarecapsul; "FirmwareCapsuleFilename"
0x1800519e8  xor     edx, edx; lpSubKey
0x1800519ea  mov     rcx, [rbp+hKey]; hkey
0x1800519ee  call    ?PpfhReadRegString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; PpfhReadRegString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800519f3  mov     ebx, eax
0x1800519f5  test    eax, eax
0x1800519f7  jns     short loc_180051A40
0x1800519f9  mov     rcx, [rbp+28h]; this
0x1800519fd  mov     r9d, eax; char *
0x180051a00  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180051a07  mov     edx, 99h; void *
0x180051a0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051a11  nop
0x180051a12  mov     rdi, [rbp+lpMem]
0x180051a16  test    rdi, rdi
0x180051a19  jz      short loc_1800519B1
0x180051a1b  call    cs:__imp_GetProcessHeap
0x180051a22  nop     dword ptr [rax+rax+00h]
0x180051a27  mov     rcx, rax; hHeap
0x180051a2a  mov     r8, rdi; lpMem
0x180051a2d  xor     edx, edx; dwFlags
0x180051a2f  call    cs:__imp_HeapFree
0x180051a36  nop     dword ptr [rax+rax+00h]
0x180051a3b  jmp     loc_1800519B1
0x180051a40  mov     [rbp+var_10], 0
0x180051a48  lea     rcx, [rbp+var_10]
0x180051a4c  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator&(void)
0x180051a51  mov     r9, rax; unsigned __int16 **
0x180051a54  lea     r8, aFirmwaremeasur; "FirmwareMeasurementsFilename"
0x180051a5b  xor     edx, edx; lpSubKey
0x180051a5d  mov     rcx, [rbp+hKey]; hkey
0x180051a61  call    ?PpfhReadRegString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; PpfhReadRegString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180051a66  mov     edi, eax
0x180051a68  test    eax, eax
0x180051a6a  jns     loc_180051AF9
0x180051a70  mov     rcx, [rbp+28h]; this
0x180051a74  mov     r9d, eax; char *
0x180051a77  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180051a7e  mov     edx, 9Ch; void *
0x180051a83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051a88  nop
0x180051a89  mov     rbx, [rbp+var_10]
0x180051a8d  test    rbx, rbx
0x180051a90  jz      short loc_180051AB3
0x180051a92  call    cs:__imp_GetProcessHeap
0x180051a99  nop     dword ptr [rax+rax+00h]
0x180051a9e  mov     r8, rbx; lpMem
0x180051aa1  xor     edx, edx; dwFlags
0x180051aa3  mov     rcx, rax; hHeap
0x180051aa6  call    cs:__imp_HeapFree
0x180051aad  nop     dword ptr [rax+rax+00h]
0x180051ab2  nop
0x180051ab3  mov     rbx, [rbp+lpMem]
0x180051ab7  test    rbx, rbx
0x180051aba  jz      short loc_180051ADD
0x180051abc  call    cs:__imp_GetProcessHeap
0x180051ac3  nop     dword ptr [rax+rax+00h]
0x180051ac8  mov     rcx, rax; hHeap
0x180051acb  mov     r8, rbx; lpMem
0x180051ace  xor     edx, edx; dwFlags
0x180051ad0  call    cs:__imp_HeapFree
0x180051ad7  nop     dword ptr [rax+rax+00h]
0x180051adc  nop
0x180051add  mov     rcx, [rbp+hKey]; hKey
0x180051ae1  test    rcx, rcx
0x180051ae4  jz      short loc_180051AF2
0x180051ae6  call    cs:__imp_RegCloseKey
0x180051aed  nop     dword ptr [rax+rax+00h]
0x180051af2  mov     eax, edi
0x180051af4  jmp     loc_180051C4F
0x180051af9  mov     rax, [rbp+lpMem]
0x180051afd  test    rax, rax
0x180051b00  jz      short loc_180051B38
0x180051b02  mov     rcx, [rbp+var_10]
0x180051b06  test    rcx, rcx
0x180051b09  jz      short loc_180051B38
0x180051b0b  mov     qword ptr [rsp+60h+ulFlags], rcx
0x180051b10  mov     [rsp+60h+phkDevice], rax
0x180051b15  lea     r9, aFirmwarecapsul_0; "FirmwareCapsuleFileName = %ws, Firmware"...
0x180051b1c  lea     r8, aValidatefirmwa; "ValidateFirmwareDriverPackageParameters"
0x180051b23  mov     edx, 9Fh; unsigned int
0x180051b28  lea     rcx, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180051b2f  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180051b34  mov     byte ptr [r15], 1
0x180051b38  mov     [rbp+pvData], 0
0x180051b3f  mov     [rbp+arg_18], 4
0x180051b46  lea     rax, [rbp+arg_18]
0x180051b4a  mov     [rsp+60h+pcbData], rax; pcbData
0x180051b4f  lea     rax, [rbp+pvData]
0x180051b53  mov     qword ptr [rsp+60h+ulFlags], rax; char *
0x180051b58  mov     [rsp+60h+phkDevice], 0; unsigned int
0x180051b61  mov     r9d, 20000010h; dwFlags
0x180051b67  lea     r8, aFirmwarepcrcha; "FirmwarePcrChangeMask"
0x180051b6e  xor     edx, edx; lpSubKey
0x180051b70  mov     rcx, [rbp+hKey]; hkey
0x180051b74  call    cs:__imp_RegGetValueW
0x180051b7b  nop     dword ptr [rax+rax+00h]
0x180051b80  test    eax, eax
0x180051b82  jnz     loc_180051C6F
0x180051b88  mov     eax, [rbp+pvData]
0x180051b8b  mov     dword ptr [rsp+60h+phkDevice], eax
0x180051b8f  lea     r9, aFirmwarepcrcha_0; "firmwarePcrChangeMask: 0x%x"
0x180051b96  lea     r8, aValidatefirmwa; "ValidateFirmwareDriverPackageParameters"
0x180051b9d  mov     edx, 0ABh; unsigned int
0x180051ba2  lea     rcx, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180051ba9  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180051bae  mov     eax, [rbp+pvData]
0x180051bb1  test    eax, 0FFFFFFEAh
0x180051bb6  jz      loc_180051C64
0x180051bbc  mov     rcx, [rbp+28h]; this
0x180051bc0  lea     rax, aUnsupportedPcr; "Unsupported PCRs in FirmwarePcrChangeMa"...
0x180051bc7  mov     [rsp+60h+phkDevice], rax; int
0x180051bcc  mov     r9d, 80070057h; char *
0x180051bd2  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180051bd9  mov     edx, 0AFh; void *
0x180051bde  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180051be3  nop
0x180051be4  mov     rbx, [rbp+var_10]
0x180051be8  test    rbx, rbx
0x180051beb  jz      short loc_180051C0E
0x180051bed  call    cs:__imp_GetProcessHeap
0x180051bf4  nop     dword ptr [rax+rax+00h]
0x180051bf9  mov     rcx, rax; hHeap
0x180051bfc  mov     r8, rbx; lpMem
0x180051bff  xor     edx, edx; dwFlags
0x180051c01  call    cs:__imp_HeapFree
0x180051c08  nop     dword ptr [rax+rax+00h]
0x180051c0d  nop
0x180051c0e  mov     rbx, [rbp+lpMem]
0x180051c12  test    rbx, rbx
0x180051c15  jz      short loc_180051C38
0x180051c17  call    cs:__imp_GetProcessHeap
0x180051c1e  nop     dword ptr [rax+rax+00h]
0x180051c23  mov     rcx, rax; hHeap
0x180051c26  mov     r8, rbx; lpMem
0x180051c29  xor     edx, edx; dwFlags
0x180051c2b  call    cs:__imp_HeapFree
0x180051c32  nop     dword ptr [rax+rax+00h]
0x180051c37  nop
0x180051c38  mov     rcx, [rbp+hKey]; hKey
0x180051c3c  test    rcx, rcx
0x180051c3f  jz      short loc_180051C4D
0x180051c41  call    cs:__imp_RegCloseKey
0x180051c48  nop     dword ptr [rax+rax+00h]
0x180051c4d  xor     eax, eax
0x180051c4f  mov     rbx, [rsp+60h+arg_0]
0x180051c57  add     rsp, 60h
0x180051c5b  pop     r15
0x180051c5d  pop     r14
0x180051c5f  pop     rdi
0x180051c60  pop     rsi
0x180051c61  pop     rbp
0x180051c62  retn
0x180051c64  mov     byte ptr [r14], 1
0x180051c68  mov     [rsi], eax
0x180051c6a  jmp     loc_180051BE4
0x180051c6f  cmp     eax, 2
0x180051c72  jz      loc_180051BE4
0x180051c78  mov     rcx, [rbp+28h]; this
0x180051c7c  mov     r9d, eax; char *
0x180051c7f  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180051c86  mov     edx, 0B9h; void *
0x180051c8b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180051c90  mov     edi, eax
0x180051c92  jmp     loc_180051A89
```
