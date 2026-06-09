# DpspBackgroundControl(void *)

- ea: `0x180016200`
- end: `0x1800166a4`
- name: `?DpspBackgroundControl@@YAKPEAX@Z`
- size: `1188`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task`

## callees

- `0x1800064e8`
- `0x180007248`
- `0x180007800`
- `0x1800086e8`
- `0x180009090`
- `0x180009fb0`
- `0x180015b84`
- `0x180016200`
- `0x1800166ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800163d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800163d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016492`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800163c1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180016688`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800163c1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180016688`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016370`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016370`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001627f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001627f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016311`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016354`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016311`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016354`

## string_xrefs

- `0x180016227`: `System\CurrentControlSet\Control\WDI\Config`
- `0x1800162c0`: `DpspGetBackgroundWorkerConfigInformation`

## pseudocode

```c
__int64 __fastcall DpspBackgroundControl(PVOID Parameter)
{
  LSTATUS v1; // eax
  signed int v2; // ebx
  DWORD v3; // eax
  signed int v4; // eax
  int v5; // r8d
  int refreshed; // eax
  int started; // eax
  unsigned int SystemTimeInMinutes; // r14d
  unsigned int i; // r15d
  signed int LastError; // eax
  int v12; // eax
  int v13; // eax
  int v14; // r8d
  int v15; // eax
  int v16; // eax
  int v17; // eax
  DWORD v18; // esi
  unsigned int v19; // edi
  BYTE v20[4]; // [rsp+30h] [rbp-40h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-3Ch] BYREF
  DWORD cbData; // [rsp+38h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-30h] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-28h] BYREF

  Handles[0] = g_hWorkerShutdown;
  Handles[1] = g_hGroupPolicyControl;
  Handles[2] = g_hDataRetentionControl;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v20 = 0;
  hKey = 0;
  cbData = 4;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\WDI\\Config", 0, 0x20019u, &hKey);
  v2 = v1;
  if ( v1 > 0 )
    v2 = (unsigned __int16)v1 | 0x80070000;
  if ( v2 >= 0 )
  {
    if ( hKey )
    {
      if ( RegQueryValueExW(hKey, L"InitWait", 0, 0, Data, &cbData) )
      {
        *(_DWORD *)Data = 10;
      }
      else if ( *(_DWORD *)Data < 2u )
      {
        *(_DWORD *)Data = 2;
      }
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"WorkerInterval", 0, 0, v20, &cbData) || !*(_DWORD *)v20 )
        *(_DWORD *)v20 = 15;
    }
    else
    {
      v2 = -2147467259;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsbgctrl.cpp",
        (int)L"DpspGetBackgroundWorkerConfigInformation",
        183,
        (int)L"Error = %d",
        5);
    }
  }
  else
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsbgctrl.cpp",
      (int)L"DpspGetBackgroundWorkerConfigInformation",
      181,
      (int)L"Error = %d",
      v2);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v2 < 0 )
  {
    *(_DWORD *)Data = 10;
    *(_DWORD *)v20 = 15;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsbgctrl.cpp",
      (int)L"DpspBackgroundControl",
      297,
      (int)L"Error = %d",
      v2);
    LOWORD(v2) = 0;
  }
  v3 = WaitForMultipleObjectsEx(2u, Handles, 0, 60000 * *(_DWORD *)Data, 0);
  if ( !v3 )
    return (unsigned __int16)v2;
  if ( v3 == 1 )
  {
    DpspLoadGroupPolicy();
    refreshed = DpspRaiseGroupPolicyRefreshEvent();
    if ( refreshed < 0 )
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsbgctrl.cpp",
        (int)L"DpspBackgroundControl",
        339,
        (int)L"Error = %d",
        refreshed);
    goto LABEL_27;
  }
  if ( v3 != -1 )
  {
LABEL_27:
    started = DpspRaiseServiceStartEvent(&WDI_DPS_EVENT_LAZY_INIT);
    LOWORD(v2) = started;
    if ( started < 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsbgctrl.cpp",
        (int)L"DpspBackgroundControl",
        358,
        (int)L"Error = %d",
        started);
      LOWORD(v2) = 0;
    }
    SystemTimeInMinutes = WdipGetSystemTimeInMinutes();
    for ( i = SystemTimeInMinutes; ; i = v19 )
    {
      do
      {
        while ( 1 )
        {
          v18 = WaitForMultipleObjectsEx(3u, Handles, 0, 60000 * *(_DWORD *)v20, 0);
          v19 = WdipGetSystemTimeInMinutes();
          if ( !v18 )
            return (unsigned __int16)v2;
          if ( v18 == 1 )
            break;
          switch ( v18 )
          {
            case 2u:
              v15 = DpspDeleteOldDirectories();
              LOWORD(v2) = v15;
              if ( v15 < 0 )
              {
                WdipTraceError(
                  (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsbgctrl.cpp",
                  (int)L"DpspBackgroundControl",
                  456,
                  (int)L"Error = %d",
                  v15);
                LOWORD(v2) = 0;
              }
              else
              {
                i = v19;
              }
              if ( v19 > SystemTimeInMinutes && v19 - SystemTimeInMinutes > *(_DWORD *)v20 )
              {
                v13 = DpspUnloadAfterIdle();
                LOWORD(v2) = v13;
                if ( v13 >= 0 )
                  goto LABEL_46;
                v14 = 472;
LABEL_67:
                WdipTraceError(
                  (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsbgctrl.cpp",
                  (int)L"DpspBackgroundControl",
                  v14,
                  (int)L"Error = %d",
                  v13);
                LOWORD(v2) = 0;
              }
              break;
            case 0x102u:
              if ( v19 > i && v19 - i > 0x5A0 )
              {
                v12 = DpspDeleteOldDirectories();
                if ( v12 < 0 )
                  WdipTraceError(
                    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsbgctrl.cpp",
                    (int)L"DpspBackgroundControl",
                    493,
                    (int)L"Error = %d",
                    v12);
                else
                  i = v19;
              }
              v13 = DpspUnloadAfterIdle();
              LOWORD(v2) = v13;
              if ( v13 < 0 )
              {
                v14 = 503;
                goto LABEL_67;
              }
LABEL_46:
              SystemTimeInMinutes = v19;
              break;
            case 0xFFFFFFFF:
              LastError = GetLastError();
              v2 = LastError;
              if ( LastError > 0 )
                v2 = (unsigned __int16)LastError | 0x80070000;
              if ( v2 < 0 )
              {
                v5 = 387;
                goto LABEL_38;
              }
              return (unsigned __int16)v2;
          }
        }
        DpspLoadGroupPolicy();
        v16 = DpspRaiseGroupPolicyRefreshEvent();
        LOWORD(v2) = v16;
        if ( v16 < 0 )
        {
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsbgctrl.cpp",
            (int)L"DpspBackgroundControl",
            406,
            (int)L"Error = %d",
            v16);
          LOWORD(v2) = 0;
        }
        if ( v19 > SystemTimeInMinutes && v19 - SystemTimeInMinutes > *(_DWORD *)v20 )
        {
          v17 = DpspUnloadAfterIdle();
          LOWORD(v2) = v17;
          if ( v17 < 0 )
          {
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsbgctrl.cpp",
              (int)L"DpspBackgroundControl",
              421,
              (int)L"Error = %d",
              v17);
            LOWORD(v2) = 0;
          }
          else
          {
            SystemTimeInMinutes = v19;
          }
        }
      }
      while ( v19 <= i || v19 - i <= 0x5A0 );
      v13 = DpspDeleteOldDirectories();
      LOWORD(v2) = v13;
      if ( v13 < 0 )
      {
        v14 = 438;
        goto LABEL_67;
      }
    }
  }
  v4 = GetLastError();
  v2 = v4;
  if ( v4 > 0 )
    v2 = (unsigned __int16)v4 | 0x80070000;
  if ( v2 < 0 )
  {
    v5 = 320;
LABEL_38:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsbgctrl.cpp",
      (int)L"DpspBackgroundControl",
      v5,
      (int)L"Error = %d",
      v2);
  }
  return (unsigned __int16)v2;
}

```

## disassembly

```asm
0x180016200  push    rbp
0x180016202  push    rbx
0x180016203  push    rsi
0x180016204  push    rdi
0x180016205  push    r13
0x180016207  push    r14
0x180016209  push    r15
0x18001620b  mov     rbp, rsp
0x18001620e  sub     rsp, 70h
0x180016212  mov     rax, cs:__security_cookie
0x180016219  xor     rax, rsp
0x18001621c  mov     [rbp+var_10], rax
0x180016220  mov     rax, cs:g_hWorkerShutdown
0x180016227  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\WDI"...
0x18001622e  mov     [rbp+Handles], rax
0x180016232  mov     esi, 4
0x180016237  mov     rax, cs:g_hGroupPolicyControl
0x18001623e  mov     r9d, 20019h; samDesired
0x180016244  mov     [rbp+var_20], rax
0x180016248  xor     r8d, r8d; ulOptions
0x18001624b  mov     rax, cs:g_hDataRetentionControl
0x180016252  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016259  mov     [rbp+var_18], rax
0x18001625d  lea     rax, [rbp+hKey]
0x180016261  mov     [rsp+70h+phkResult], rax; phkResult
0x180016266  mov     dword ptr [rbp+Data], 0
0x18001626d  mov     dword ptr [rbp+var_40], 0
0x180016274  mov     [rbp+hKey], 0
0x18001627c  mov     [rbp+cbData], esi
0x18001627f  call    cs:__imp_RegOpenKeyExW
0x180016285  mov     ebx, eax
0x180016287  test    eax, eax
0x180016289  jle     short loc_180016294
0x18001628b  movzx   ebx, ax
0x18001628e  or      ebx, 80070000h
0x180016294  lea     r13, aErrorD; "Error = %d"
0x18001629b  mov     r15d, 0Ah
0x1800162a1  lea     rdi, aClientcoreBase_10; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800162a8  lea     r14d, [r15+5]
0x1800162ac  test    ebx, ebx
0x1800162ae  jns     short loc_1800162D4
0x1800162b0  movzx   eax, bx
0x1800162b3  mov     r8d, 0B5h; int
0x1800162b9  mov     dword ptr [rsp+70h+phkResult], eax; Args
0x1800162bd  mov     r9, r13; int
0x1800162c0  lea     rdx, aDpspgetbackgro; "DpspGetBackgroundWorkerConfigInformatio"...
0x1800162c7  mov     rcx, rdi; int
0x1800162ca  call    WdipTraceError
0x1800162cf  jmp     loc_180016367
0x1800162d4  mov     rcx, [rbp+hKey]; hKey
0x1800162d8  test    rcx, rcx
0x1800162db  jnz     short loc_1800162F2
0x1800162dd  mov     ebx, 80004005h
0x1800162e2  mov     dword ptr [rsp+70h+phkResult], 4005h
0x1800162ea  mov     r8d, 0B7h
0x1800162f0  jmp     short loc_1800162BD
0x1800162f2  lea     rax, [rbp+cbData]
0x1800162f6  xor     r9d, r9d; lpType
0x1800162f9  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800162fe  lea     rdx, aInitwait; "InitWait"
0x180016305  lea     rax, [rbp+Data]
0x180016309  xor     r8d, r8d; lpReserved
0x18001630c  mov     [rsp+70h+phkResult], rax; lpData
0x180016311  call    cs:__imp_RegQueryValueExW
0x180016317  test    eax, eax
0x180016319  jz      short loc_180016321
0x18001631b  mov     dword ptr [rbp+Data], r15d
0x18001631f  jmp     short loc_18001632E
0x180016321  cmp     dword ptr [rbp+Data], 2
0x180016325  jnb     short loc_18001632E
0x180016327  mov     dword ptr [rbp+Data], 2
0x18001632e  mov     rcx, [rbp+hKey]; hKey
0x180016332  lea     rax, [rbp+cbData]
0x180016336  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18001633b  lea     rdx, aWorkerinterval; "WorkerInterval"
0x180016342  lea     rax, [rbp+var_40]
0x180016346  mov     [rbp+cbData], esi
0x180016349  xor     r9d, r9d; lpType
0x18001634c  mov     [rsp+70h+phkResult], rax; lpData
0x180016351  xor     r8d, r8d; lpReserved
0x180016354  call    cs:__imp_RegQueryValueExW
0x18001635a  test    eax, eax
0x18001635c  jnz     short loc_180016363
0x18001635e  cmp     dword ptr [rbp+var_40], eax
0x180016361  jnz     short loc_180016367
0x180016363  mov     dword ptr [rbp+var_40], r14d
0x180016367  mov     rcx, [rbp+hKey]; hKey
0x18001636b  test    rcx, rcx
0x18001636e  jz      short loc_180016376
0x180016370  call    cs:__imp_RegCloseKey
0x180016376  lea     rsi, aDpspbackground; "DpspBackgroundControl"
0x18001637d  test    ebx, ebx
0x18001637f  jns     short loc_1800163A6
0x180016381  movzx   eax, bx
0x180016384  mov     r9, r13; int
0x180016387  mov     r8d, 129h; int
0x18001638d  mov     dword ptr [rsp+70h+phkResult], eax; Args
0x180016391  mov     rdx, rsi; int
0x180016394  mov     dword ptr [rbp+Data], r15d
0x180016398  mov     rcx, rdi; int
0x18001639b  mov     dword ptr [rbp+var_40], r14d
0x18001639f  call    WdipTraceError
0x1800163a4  xor     ebx, ebx
0x1800163a6  imul    r9d, dword ptr [rbp+Data], 0EA60h; dwMilliseconds
0x1800163ae  lea     rdx, [rbp+Handles]; lpHandles
0x1800163b2  xor     r8d, r8d; bWaitAll
0x1800163b5  mov     dword ptr [rsp+70h+phkResult], 0; bAlertable
0x1800163bd  lea     ecx, [r8+2]; nCount
0x1800163c1  call    cs:__imp_WaitForMultipleObjectsEx
0x1800163c7  test    eax, eax
0x1800163c9  jz      loc_1800164CE
0x1800163cf  cmp     eax, 1
0x1800163d2  jz      short loc_180016407
0x1800163d4  cmp     eax, 0FFFFFFFFh
0x1800163d7  jnz     short loc_180016430
0x1800163d9  call    cs:__imp_GetLastError
0x1800163df  mov     ebx, eax
0x1800163e1  test    eax, eax
0x1800163e3  jle     short loc_1800163EE
0x1800163e5  movzx   ebx, ax
0x1800163e8  or      ebx, 80070000h
0x1800163ee  test    ebx, ebx
0x1800163f0  jns     loc_1800164CE
0x1800163f6  mov     r8d, 140h
0x1800163fc  mov     rdx, rsi
0x1800163ff  mov     rcx, rdi
0x180016402  jmp     loc_1800164BF
0x180016407  call    DpspLoadGroupPolicy
0x18001640c  call    DpspRaiseGroupPolicyRefreshEvent
0x180016411  test    eax, eax
0x180016413  jns     short loc_180016430
0x180016415  movzx   eax, ax
0x180016418  mov     r9, r13; int
0x18001641b  mov     r8d, 153h; int
0x180016421  mov     dword ptr [rsp+70h+phkResult], eax; Args
0x180016425  mov     rdx, rsi; int
0x180016428  mov     rcx, rdi; int
0x18001642b  call    WdipTraceError
0x180016430  lea     rcx, WDI_DPS_EVENT_LAZY_INIT; EventDescriptor
0x180016437  call    DpspRaiseServiceStartEvent
0x18001643c  mov     ebx, eax
0x18001643e  test    eax, eax
0x180016440  jns     short loc_18001645F
0x180016442  movzx   eax, ax
0x180016445  mov     r9, r13; int
0x180016448  mov     r8d, 166h; int
0x18001644e  mov     dword ptr [rsp+70h+phkResult], eax; Args
0x180016452  mov     rdx, rsi; int
0x180016455  mov     rcx, rdi; int
0x180016458  call    WdipTraceError
0x18001645d  xor     ebx, ebx
0x18001645f  call    ?WdipGetSystemTimeInMinutes@@YAKXZ; WdipGetSystemTimeInMinutes(void)
0x180016464  mov     r14d, eax
0x180016467  mov     r15d, eax
0x18001646a  jmp     loc_18001666D
0x18001646f  cmp     esi, 1
0x180016472  jz      loc_1800165AE
0x180016478  cmp     esi, 2
0x18001647b  jz      loc_18001654C
0x180016481  cmp     esi, 102h
0x180016487  jz      short loc_1800164EC
0x180016489  cmp     esi, 0FFFFFFFFh
0x18001648c  jnz     loc_18001666D
0x180016492  call    cs:__imp_GetLastError
0x180016498  mov     ebx, eax
0x18001649a  test    eax, eax
0x18001649c  jle     short loc_1800164A7
0x18001649e  movzx   ebx, ax
0x1800164a1  or      ebx, 80070000h
0x1800164a7  test    ebx, ebx
0x1800164a9  jns     short loc_1800164CE
0x1800164ab  mov     r8d, 183h; int
0x1800164b1  lea     rdx, aDpspbackground; "DpspBackgroundControl"
0x1800164b8  lea     rcx, aClientcoreBase_10; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800164bf  movzx   eax, bx
0x1800164c2  mov     r9, r13; int
0x1800164c5  mov     dword ptr [rsp+70h+phkResult], eax; Args
0x1800164c9  call    WdipTraceError
0x1800164ce  movzx   eax, bx
0x1800164d1  mov     rcx, [rbp+var_10]
0x1800164d5  xor     rcx, rsp; StackCookie
0x1800164d8  call    __security_check_cookie
0x1800164dd  add     rsp, 70h
0x1800164e1  pop     r15
0x1800164e3  pop     r14
0x1800164e5  pop     r13
0x1800164e7  pop     rdi
0x1800164e8  pop     rsi
0x1800164e9  pop     rbx
0x1800164ea  pop     rbp
0x1800164eb  retn
0x1800164ec  cmp     edi, r15d
0x1800164ef  jbe     short loc_18001652E
0x1800164f1  mov     eax, edi
0x1800164f3  sub     eax, r15d
0x1800164f6  cmp     eax, 5A0h
0x1800164fb  jbe     short loc_18001652E
0x1800164fd  call    DpspDeleteOldDirectories
0x180016502  test    eax, eax
0x180016504  js      short loc_18001650B
0x180016506  mov     r15d, edi
0x180016509  jmp     short loc_18001652E
0x18001650b  movzx   eax, ax
0x18001650e  lea     rdx, aDpspbackground; "DpspBackgroundControl"
0x180016515  mov     r9, r13; int
0x180016518  mov     dword ptr [rsp+70h+phkResult], eax; Args
0x18001651c  mov     r8d, 1EDh; int
0x180016522  lea     rcx, aClientcoreBase_10; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180016529  call    WdipTraceError
0x18001652e  call    DpspUnloadAfterIdle
0x180016533  mov     ebx, eax
0x180016535  test    eax, eax
0x180016537  js      short loc_180016541
0x180016539  mov     r14d, edi
0x18001653c  jmp     loc_18001666D
0x180016541  mov     r8d, 1F7h
0x180016547  jmp     loc_18001664E
0x18001654c  call    DpspDeleteOldDirectories
0x180016551  mov     ebx, eax
0x180016553  test    eax, eax
0x180016555  js      short loc_18001655C
0x180016557  mov     r15d, edi
0x18001655a  jmp     short loc_180016581
0x18001655c  movzx   eax, ax
0x18001655f  lea     rdx, aDpspbackground; "DpspBackgroundControl"
0x180016566  mov     r9, r13; int
0x180016569  mov     dword ptr [rsp+70h+phkResult], eax; Args
0x18001656d  mov     r8d, 1C8h; int
0x180016573  lea     rcx, aClientcoreBase_10; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18001657a  call    WdipTraceError
0x18001657f  xor     ebx, ebx
0x180016581  cmp     edi, r14d
0x180016584  jbe     loc_18001666D
0x18001658a  mov     eax, edi
0x18001658c  sub     eax, r14d
0x18001658f  cmp     eax, dword ptr [rbp+var_40]
0x180016592  jbe     loc_18001666D
0x180016598  call    DpspUnloadAfterIdle
0x18001659d  mov     ebx, eax
0x18001659f  test    eax, eax
0x1800165a1  jns     short loc_180016539
0x1800165a3  mov     r8d, 1D8h
0x1800165a9  jmp     loc_18001664E
0x1800165ae  call    DpspLoadGroupPolicy
0x1800165b3  call    DpspRaiseGroupPolicyRefreshEvent
0x1800165b8  mov     ebx, eax
0x1800165ba  test    eax, eax
0x1800165bc  jns     short loc_1800165E3
0x1800165be  movzx   eax, ax
0x1800165c1  lea     rdx, aDpspbackground; "DpspBackgroundControl"
0x1800165c8  mov     r9, r13; int
0x1800165cb  mov     dword ptr [rsp+70h+phkResult], eax; Args
0x1800165cf  mov     r8d, 196h; int
0x1800165d5  lea     rcx, aClientcoreBase_10; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800165dc  call    WdipTraceError
0x1800165e1  xor     ebx, ebx
0x1800165e3  cmp     edi, r14d
0x1800165e6  jbe     short loc_180016627
0x1800165e8  mov     eax, edi
0x1800165ea  sub     eax, r14d
0x1800165ed  cmp     eax, dword ptr [rbp+var_40]
0x1800165f0  jbe     short loc_180016627
0x1800165f2  call    DpspUnloadAfterIdle
0x1800165f7  mov     ebx, eax
0x1800165f9  test    eax, eax
0x1800165fb  js      short loc_180016602
0x1800165fd  mov     r14d, edi
0x180016600  jmp     short loc_180016627
0x180016602  movzx   eax, ax
0x180016605  lea     rdx, aDpspbackground; "DpspBackgroundControl"
0x18001660c  mov     r9, r13; int
0x18001660f  mov     dword ptr [rsp+70h+phkResult], eax; Args
0x180016613  mov     r8d, 1A5h; int
0x180016619  lea     rcx, aClientcoreBase_10; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180016620  call    WdipTraceError
0x180016625  xor     ebx, ebx
0x180016627  cmp     edi, r15d
0x18001662a  jbe     short loc_18001666D
0x18001662c  mov     eax, edi
0x18001662e  sub     eax, r15d
0x180016631  cmp     eax, 5A0h
0x180016636  jbe     short loc_18001666D
0x180016638  call    DpspDeleteOldDirectories
0x18001663d  mov     ebx, eax
0x18001663f  test    eax, eax
0x180016641  js      short loc_180016648
0x180016643  mov     r15d, edi
0x180016646  jmp     short loc_18001666D
0x180016648  mov     r8d, 1B6h; int
0x18001664e  movzx   eax, ax
0x180016651  lea     rdx, aDpspbackground; "DpspBackgroundControl"
0x180016658  mov     r9, r13; int
0x18001665b  mov     dword ptr [rsp+70h+phkResult], eax; Args
0x18001665f  lea     rcx, aClientcoreBase_10; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180016666  call    WdipTraceError
0x18001666b  xor     ebx, ebx
0x18001666d  imul    r9d, dword ptr [rbp+var_40], 0EA60h; dwMilliseconds
0x180016675  lea     rdx, [rbp+Handles]; lpHandles
0x180016679  xor     r8d, r8d; bWaitAll
0x18001667c  mov     dword ptr [rsp+70h+phkResult], 0; bAlertable
  ... truncated ...
```
