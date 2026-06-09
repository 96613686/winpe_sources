# DpspLaunchCommunicationServer

- ea: `0x180011274`
- end: `0x1800114ef`
- name: `DpspLaunchCommunicationServer`
- size: `635`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b0a0`

## callees

- `0x1800013a0`
- `0x180009090`
- `0x180009fb0`
- `0x180010374`
- `0x180010fbc`
- `0x180011020`
- `0x180011274`

## import_xrefs

- `ntdll!TpAllocAlpcCompletion` at `0x180011484`
- `ntdll!TpAllocAlpcCompletion` at `0x180011484`
- `ntdll!RtlNtStatusToDosError` at `0x180011494`
- `ntdll!RtlNtStatusToDosError` at `0x180011494`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18001128f`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18001128f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011451`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011451`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011334`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011334`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011407`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011407`

## string_xrefs

- `0x180011326`: `System\CurrentControlSet\Control\WDI\Config`
- `0x1800114c1`: `DpspLaunchCommunicationServer`

## pseudocode

```c
__int64 __fastcall DpspLaunchCommunicationServer(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  unsigned int v4; // edx
  signed int v5; // ebx
  int ServerPortName; // eax
  void **v7; // rdx
  int ServerPort; // eax
  int v9; // r8d
  LSTATUS v10; // eax
  unsigned __int64 v11; // rdx
  int v12; // r8d
  int v13; // eax
  HKEY v14; // r11
  LSTATUS v15; // eax
  NTSTATUS v16; // eax
  signed int v17; // eax
  HKEY hKey; // [rsp+30h] [rbp-128h] BYREF
  unsigned __int64 v20; // [rsp+38h] [rbp-120h] BYREF
  WCHAR Data[128]; // [rsp+40h] [rbp-118h] BYREF

  v3 = AlpcMaxAllowedMessageLength(a1, a2, a3);
  g_PreAllocatedBuffer = WdipAlloc(v3);
  if ( !g_PreAllocatedBuffer )
  {
    v5 = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpssrv.cpp",
      (int)L"DpspLaunchCommunicationServer",
      1418,
      (int)L"Error = %d",
      14);
    return (unsigned int)v5;
  }
  ServerPortName = WdipCreateServerPortName(Data, v4);
  v5 = ServerPortName;
  if ( ServerPortName < 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpssrv.cpp",
      (int)L"DpspLaunchCommunicationServer",
      1421,
      (int)L"Error = %d",
      ServerPortName);
    return (unsigned int)v5;
  }
  ServerPort = DpspCreateServerPort(Data, v7);
  v5 = ServerPort;
  if ( ServerPort < 0 )
  {
    v9 = 1424;
LABEL_36:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpssrv.cpp",
      (int)L"DpspLaunchCommunicationServer",
      v9,
      (int)L"Error = %d",
      ServerPort);
    return (unsigned int)v5;
  }
  hKey = 0;
  v20 = 0;
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\WDI\\Config", 0, 2u, &hKey);
  v5 = v10;
  if ( v10 > 0 )
    v5 = (unsigned __int16)v10 | 0x80070000;
  if ( v5 < 0 )
  {
    v12 = 1354;
LABEL_23:
    LOBYTE(v13) = v5;
    goto LABEL_24;
  }
  if ( !hKey )
  {
    v5 = -2147467259;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpssrv.cpp",
      (int)L"WdipSetServerPortName",
      1356,
      (int)L"Error = %d",
      5);
    goto LABEL_25;
  }
  v13 = StringCchLengthW(Data, v11, &v20);
  v5 = v13;
  if ( v13 < 0 )
  {
    v12 = 1362;
LABEL_24:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpssrv.cpp",
      (int)L"WdipSetServerPortName",
      v12,
      (int)L"Error = %d",
      v13);
    goto LABEL_25;
  }
  if ( v20 + 1 < v20 )
  {
    v5 = -2147024362;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpssrv.cpp",
      (int)L"WdipSetServerPortName",
      1366,
      (int)L"Error = %d",
      22);
    goto LABEL_25;
  }
  if ( v20 + 1 != (unsigned __int64)(unsigned int)(2 * v20 + 2) >> 1 )
  {
    v5 = -2147024362;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpssrv.cpp",
      (int)L"WdipSetServerPortName",
      1373,
      (int)L"Error = %d",
      22);
    goto LABEL_25;
  }
  v15 = RegSetValueExW(v14, L"ServerName", 0, 1u, (const BYTE *)Data, 2 * v20 + 2);
  v5 = v15;
  if ( v15 > 0 )
    v5 = (unsigned __int16)v15 | 0x80070000;
  if ( v5 < 0 )
  {
    v12 = 1384;
    goto LABEL_23;
  }
LABEL_25:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 < 0 )
  {
    v9 = 1427;
LABEL_35:
    LOBYTE(ServerPort) = v5;
    goto LABEL_36;
  }
  v16 = TpAllocAlpcCompletion(&g_pAlpcCompletion, g_hServerPort, DpspServerListener, 0, 0);
  if ( v16 < 0 )
  {
    v17 = RtlNtStatusToDosError(v16);
    v5 = v17;
    if ( v17 > 0 )
      v5 = (unsigned __int16)v17 | 0x80070000;
  }
  else
  {
    v5 = 0;
  }
  if ( v5 < 0 )
  {
    v9 = 1438;
    goto LABEL_35;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180011274  push    rbx
0x180011276  sub     rsp, 150h
0x18001127d  mov     rax, cs:__security_cookie
0x180011284  xor     rax, rsp
0x180011287  mov     [rsp+158h+var_18], rax
0x18001128f  call    cs:__imp_AlpcMaxAllowedMessageLength
0x180011295  mov     rcx, rax
0x180011298  call    WdipAlloc
0x18001129d  mov     cs:g_PreAllocatedBuffer, rax
0x1800112a4  test    rax, rax
0x1800112a7  jnz     short loc_1800112C1
0x1800112a9  mov     ebx, 8007000Eh
0x1800112ae  mov     dword ptr [rsp+158h+phkResult], 0Eh
0x1800112b6  mov     r8d, 58Ah
0x1800112bc  jmp     loc_1800114BA
0x1800112c1  lea     rcx, [rsp+158h+Data]; unsigned __int16 *
0x1800112c6  call    ?WdipCreateServerPortName@@YAJPEAGK@Z; WdipCreateServerPortName(ushort *,ulong)
0x1800112cb  mov     ebx, eax
0x1800112cd  test    eax, eax
0x1800112cf  jns     short loc_1800112E3
0x1800112d1  movzx   ecx, ax
0x1800112d4  mov     r8d, 58Dh
0x1800112da  mov     dword ptr [rsp+158h+phkResult], ecx
0x1800112de  jmp     loc_1800114BA
0x1800112e3  lea     rcx, [rsp+158h+Data]; SourceString
0x1800112e8  call    ?DpspCreateServerPort@@YAJPEAGPEAPEAX@Z; DpspCreateServerPort(ushort *,void * *)
0x1800112ed  mov     ebx, eax
0x1800112ef  test    eax, eax
0x1800112f1  jns     short loc_180011301
0x1800112f3  movzx   eax, ax
0x1800112f6  mov     r8d, 590h
0x1800112fc  jmp     loc_1800114B6
0x180011301  lea     rax, [rsp+158h+hKey]
0x180011306  mov     [rsp+158h+hKey], 0
0x18001130f  mov     r9d, 2; samDesired
0x180011315  mov     [rsp+158h+phkResult], rax; phkResult
0x18001131a  xor     r8d, r8d; ulOptions
0x18001131d  mov     [rsp+158h+var_120], 0
0x180011326  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\WDI"...
0x18001132d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011334  call    cs:__imp_RegOpenKeyExW
0x18001133a  mov     ebx, eax
0x18001133c  test    eax, eax
0x18001133e  jle     short loc_180011349
0x180011340  movzx   ebx, ax
0x180011343  or      ebx, 80070000h
0x180011349  test    ebx, ebx
0x18001134b  jns     short loc_180011358
0x18001134d  mov     r8d, 54Ah
0x180011353  jmp     loc_180011426
0x180011358  mov     r11, [rsp+158h+hKey]
0x18001135d  test    r11, r11
0x180011360  jnz     short loc_18001137A
0x180011362  mov     ebx, 80004005h
0x180011367  mov     dword ptr [rsp+158h+phkResult], 4005h
0x18001136f  mov     r8d, 54Ch
0x180011375  jmp     loc_18001142D
0x18001137a  lea     r8, [rsp+158h+var_120]; unsigned __int64 *
0x18001137f  lea     rcx, [rsp+158h+Data]; unsigned __int16 *
0x180011384  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180011389  mov     ebx, eax
0x18001138b  test    eax, eax
0x18001138d  jns     short loc_18001139D
0x18001138f  movzx   eax, ax
0x180011392  mov     r8d, 552h
0x180011398  jmp     loc_180011429
0x18001139d  mov     rax, [rsp+158h+var_120]
0x1800113a2  lea     rcx, [rax+1]
0x1800113a6  cmp     rcx, rax
0x1800113a9  jnb     short loc_1800113C0
0x1800113ab  mov     ebx, 80070216h
0x1800113b0  mov     dword ptr [rsp+158h+phkResult], 216h
0x1800113b8  mov     r8d, 556h
0x1800113be  jmp     short loc_18001142D
0x1800113c0  lea     edx, ds:2[rax*2]
0x1800113c7  mov     eax, edx
0x1800113c9  shr     rax, 1
0x1800113cc  cmp     rcx, rax
0x1800113cf  jz      short loc_1800113E6
0x1800113d1  mov     ebx, 80070216h
0x1800113d6  mov     dword ptr [rsp+158h+phkResult], 216h
0x1800113de  mov     r8d, 55Dh
0x1800113e4  jmp     short loc_18001142D
0x1800113e6  mov     [rsp+158h+cbData], edx; cbData
0x1800113ea  lea     rax, [rsp+158h+Data]
0x1800113ef  lea     rdx, aServername; "ServerName"
0x1800113f6  mov     [rsp+158h+phkResult], rax; lpData
0x1800113fb  mov     r9d, 1; dwType
0x180011401  xor     r8d, r8d; Reserved
0x180011404  mov     rcx, r11; hKey
0x180011407  call    cs:__imp_RegSetValueExW
0x18001140d  mov     ebx, eax
0x18001140f  test    eax, eax
0x180011411  jle     short loc_18001141C
0x180011413  movzx   ebx, ax
0x180011416  or      ebx, 80070000h
0x18001141c  test    ebx, ebx
0x18001141e  jns     short loc_180011447
0x180011420  mov     r8d, 568h; int
0x180011426  movzx   eax, bx
0x180011429  mov     dword ptr [rsp+158h+phkResult], eax; Args
0x18001142d  lea     r9, aErrorD; "Error = %d"
0x180011434  lea     rdx, aWdipsetserverp; "WdipSetServerPortName"
0x18001143b  lea     rcx, aClientcoreBase_5; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180011442  call    WdipTraceError
0x180011447  mov     rcx, [rsp+158h+hKey]; hKey
0x18001144c  test    rcx, rcx
0x18001144f  jz      short loc_180011457
0x180011451  call    cs:__imp_RegCloseKey
0x180011457  test    ebx, ebx
0x180011459  jns     short loc_180011463
0x18001145b  mov     r8d, 593h
0x180011461  jmp     short loc_1800114B3
0x180011463  mov     rdx, cs:g_hServerPort
0x18001146a  lea     r8, ?DpspServerListener@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_ALPC@@@Z; DpspServerListener(_TP_CALLBACK_INSTANCE *,void *,_TP_ALPC *)
0x180011471  xor     r9d, r9d
0x180011474  mov     [rsp+158h+phkResult], 0
0x18001147d  lea     rcx, g_pAlpcCompletion
0x180011484  call    cs:__imp_TpAllocAlpcCompletion
0x18001148a  test    eax, eax
0x18001148c  js      short loc_180011492
0x18001148e  xor     ebx, ebx
0x180011490  jmp     short loc_1800114A9
0x180011492  mov     ecx, eax; Status
0x180011494  call    cs:__imp_RtlNtStatusToDosError
0x18001149a  mov     ebx, eax
0x18001149c  test    eax, eax
0x18001149e  jle     short loc_1800114A9
0x1800114a0  movzx   ebx, ax
0x1800114a3  or      ebx, 80070000h
0x1800114a9  test    ebx, ebx
0x1800114ab  jns     short loc_1800114D4
0x1800114ad  mov     r8d, 59Eh; int
0x1800114b3  movzx   eax, bx
0x1800114b6  mov     dword ptr [rsp+158h+phkResult], eax; Args
0x1800114ba  lea     r9, aErrorD; "Error = %d"
0x1800114c1  lea     rdx, aDpsplaunchcomm; "DpspLaunchCommunicationServer"
0x1800114c8  lea     rcx, aClientcoreBase_5; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800114cf  call    WdipTraceError
0x1800114d4  mov     eax, ebx
0x1800114d6  mov     rcx, [rsp+158h+var_18]
0x1800114de  xor     rcx, rsp; StackCookie
0x1800114e1  call    __security_check_cookie
0x1800114e6  add     rsp, 150h
0x1800114ed  pop     rbx
0x1800114ee  retn
```
