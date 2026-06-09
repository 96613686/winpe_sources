# NlJoinDCPingThread(void *)

- ea: `0x180036230`
- end: `0x1800365da`
- name: `?NlJoinDCPingThread@@YAKPEAX@Z`
- size: `938`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x180003ac0`
- `0x180007278`
- `0x18000ccf0`
- `0x18000d094`
- `0x180036230`
- `0x18003682c`
- `0x180039204`
- `0x18007d7c8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003650c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003650c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036309`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036309`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003656d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003656d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800362e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003633f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800363a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800362e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003633f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800363a9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180036436`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180036436`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800362b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003641b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800362b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003641b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036458`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003657c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036458`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003657c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180036485`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180036485`

## string_xrefs

- `0x18003629e`: `SYSTEM\CurrentControlSet\Services\Netlogon\JoinDomain`
- `0x18003626e`: `NlJoinDCPingThread: NlStartNetlogonCall failed\n`
- `0x180036363`: `NlJoinDCPingThread: DcName is too short.\n`
- `0x1800363c3`: `NlJoinDCPingThread:  Join DC: %ws, Flags: 0x%lx\n`
- `0x1800363e9`: `NlJoinDCPingThread: Join DC is not NT5, deleting it\n`
- `0x18003640d`: `SYSTEM\CurrentControlSet\Services\Netlogon`
- `0x180036443`: `NlJoinDCPingThread: Couldn't delete JoinDomain 0x%lx\n`
- `0x180036463`: `NlJoinDCPingThread: RegOpenKeyEx failed 0x%lx\n`
- `0x18003648b`: `NlJoinDCPingThread: Starting ping loop now\n`
- `0x18003649f`: `NlJoinDCPingThread: MAX_ELAPSED_TIME_MIN is %d minutes\n`
- `0x180036556`: `NlJoinDCPingThread: join DC pinged, exiting loop\n`
- `0x180036541`: `NlJoinDCPingThread: joinDC unpingable after network up\n`
- `0x180036538`: `NlJoinDCPingThread: max time expired so exiting loop now\n`
- `0x1800364e2`: `NlJoinDCPingThread: NlVerifyNetworkUp() succeeded\n`
- `0x1800364f3`: `NlJoinDCPingThread: sleeping prior to retry\n`
- `0x180036523`: `NlJoinDCPingThread: NlStartNetlogonCall failed after sleep\n`
- `0x1800365ad`: `NlJoinDCPingThread: exiting with return code=0x%lx\n`

## pseudocode

```c
__int64 __fastcall NlJoinDCPingThread(PVOID Parameter)
{
  int v1; // r12d
  int v2; // r14d
  LSTATUS v3; // esi
  unsigned int v4; // edi
  HLOCAL v5; // r15
  unsigned __int64 v6; // rax
  unsigned int v7; // eax
  unsigned int v8; // eax
  int v9; // r12d
  BYTE Data[4]; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+48h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+50h] BYREF
  HKEY phkResult; // [rsp+A8h] [rbp+58h] BYREF

  hKey = 0;
  v1 = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  SystemTimeAsFileTime = 0;
  if ( !(unsigned int)NlStartNetlogonCall() )
  {
    v2 = 0;
    v3 = 0;
    v4 = -1073741422;
    NlPrintRoutine(1u, L"NlJoinDCPingThread: NlStartNetlogonCall failed\n");
    goto LABEL_39;
  }
  v4 = 0;
  v2 = 1;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\Netlogon\\JoinDomain",
         0,
         0x2000000u,
         &hKey);
  if ( !v3 )
  {
    v3 = RegQueryValueExW(hKey, L"DomainControllerName", 0, &Type, 0, &cbData);
    if ( !v3 )
    {
      if ( Type != 1 )
      {
        v3 = 1629;
        goto LABEL_39;
      }
      v5 = LocalAlloc(0x40u, cbData);
      if ( !v5 )
      {
        v3 = 8;
        goto LABEL_39;
      }
      v3 = RegQueryValueExW(hKey, L"DomainControllerName", 0, &Type, (LPBYTE)v5, &cbData);
      if ( v3 )
        goto LABEL_38;
      v6 = -1;
      do
        ++v6;
      while ( *((_WORD *)v5 + v6) );
      if ( v6 >= 3 )
      {
        cbData = 4;
        v3 = RegQueryValueExW(hKey, L"Flags", 0, &Type, Data, &cbData);
        if ( v3 )
          goto LABEL_38;
        if ( Type == 4 )
        {
          v3 = 0;
          NlPrintRoutine(1u, L"NlJoinDCPingThread:  Join DC: %ws, Flags: 0x%lx\n", v5, *(unsigned int *)Data);
          NetpIncJoinDomainEntryUseCount();
          v1 = 1;
          if ( (Data[0] & 0x10) != 0 )
          {
            v9 = 0;
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            NlPrintRoutine(1u, L"NlJoinDCPingThread: Starting ping loop now\n");
            NlPrintRoutine(1u, L"NlJoinDCPingThread: MAX_ELAPSED_TIME_MIN is %d minutes\n", 15);
            while ( 1 )
            {
              v4 = NlPingJoinDC((unsigned __int16 *)v5 + 2);
              if ( !v4 )
                break;
              if ( v9 )
              {
                NlPrintRoutine(1u, L"NlJoinDCPingThread: joinDC unpingable after network up\n");
                v4 = 1355;
                goto LABEL_36;
              }
              if ( (unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD))NetpLogonTimeHasElapsed)(
                                      SystemTimeAsFileTime,
                                      900000) )
              {
                NlPrintRoutine(1u, L"NlJoinDCPingThread: max time expired so exiting loop now\n");
                goto LABEL_36;
              }
              if ( NlVerifyNetworkUp() )
              {
                NlPrintRoutine(1u, L"NlJoinDCPingThread: sleeping prior to retry\n");
                NlEndNetlogonCall();
                v2 = 0;
                Sleep(0x1388u);
                if ( !(unsigned int)NlStartNetlogonCall() )
                {
                  v4 = -1073741422;
                  NlPrintRoutine(1u, L"NlJoinDCPingThread: NlStartNetlogonCall failed after sleep\n");
                  goto LABEL_37;
                }
              }
              else
              {
                v9 = 1;
                NlPrintRoutine(1u, L"NlJoinDCPingThread: NlVerifyNetworkUp() succeeded\n");
              }
              ++gdwDCLocatorLoopTries;
            }
            NlPrintRoutine(1u, L"NlJoinDCPingThread: join DC pinged, exiting loop\n");
LABEL_36:
            v2 = 1;
LABEL_37:
            v1 = 1;
          }
          else
          {
            phkResult = 0;
            NlPrintRoutine(1u, L"NlJoinDCPingThread: Join DC is not NT5, deleting it\n");
            v7 = RegOpenKeyExW(
                   HKEY_LOCAL_MACHINE,
                   L"SYSTEM\\CurrentControlSet\\Services\\Netlogon",
                   0,
                   0xF003Fu,
                   &phkResult);
            if ( v7 )
            {
              NlPrintRoutine(0x100u, L"NlJoinDCPingThread: RegOpenKeyEx failed 0x%lx\n", v7);
            }
            else
            {
              v8 = RegDeleteKeyExW(phkResult, L"JoinDomain", 0, 0);
              if ( v8 )
                NlPrintRoutine(0x100u, L"NlJoinDCPingThread: Couldn't delete JoinDomain 0x%lx\n", v8);
              RegCloseKey(phkResult);
            }
            v4 = 13;
          }
          goto LABEL_38;
        }
      }
      else
      {
        NlPrintRoutine(0x100u, L"NlJoinDCPingThread: DcName is too short.\n");
      }
      v3 = 1629;
LABEL_38:
      LocalFree(v5);
    }
  }
LABEL_39:
  if ( hKey )
    RegCloseKey(hKey);
  if ( !v1 )
    NetpIncJoinDomainEntryUseCount();
  if ( v3 )
  {
    if ( !v4 )
      v4 = v3;
  }
  else if ( !v4 )
  {
    v4 = 0;
  }
  NlGlobalJoinLogicDone = 1;
  if ( v2 )
  {
    NlPrintRoutine(1u, L"NlJoinDCPingThread: exiting with return code=0x%lx\n", v4);
    NlEndNetlogonCall();
  }
  return v4;
}

```

## disassembly

```asm
0x180036230  mov     [rsp-38h+arg_0], rbx
0x180036235  push    rbp
0x180036236  push    rsi
0x180036237  push    rdi
0x180036238  push    r12
0x18003623a  push    r13
0x18003623c  push    r14
0x18003623e  push    r15
0x180036240  mov     rbp, rsp
0x180036243  sub     rsp, 50h
0x180036247  xor     r13d, r13d
0x18003624a  mov     [rbp+hKey], r13
0x18003624e  mov     r12d, r13d
0x180036251  mov     [rbp+cbData], r13d
0x180036255  mov     dword ptr [rbp+Data], r13d
0x180036259  mov     [rbp+Type], r13d
0x18003625d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r13
0x180036261  call    ?NlStartNetlogonCall@@YAHXZ; NlStartNetlogonCall(void)
0x180036266  lea     ebx, [r13+1]
0x18003626a  test    eax, eax
0x18003626c  jnz     short loc_18003628C
0x18003626e  lea     rdx, aNljoindcpingth_5; "NlJoinDCPingThread: NlStartNetlogonCall"...
0x180036275  mov     ecx, ebx; unsigned int
0x180036277  mov     r14d, r13d
0x18003627a  mov     esi, r13d
0x18003627d  mov     edi, 0C0000192h
0x180036282  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180036287  jmp     loc_180036573
0x18003628c  lea     rax, [rbp+hKey]
0x180036290  mov     r9d, 2000000h; samDesired
0x180036296  xor     r8d, r8d; ulOptions
0x180036299  mov     [rsp+50h+phkResult], rax; phkResult
0x18003629e  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x1800362a5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800362ac  mov     edi, r13d
0x1800362af  mov     r14d, ebx
0x1800362b2  call    cs:__imp_RegOpenKeyExW
0x1800362b8  mov     esi, eax
0x1800362ba  test    eax, eax
0x1800362bc  jnz     loc_180036573
0x1800362c2  mov     rcx, [rbp+hKey]; hKey
0x1800362c6  lea     rax, [rbp+cbData]
0x1800362ca  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800362cf  lea     r9, [rbp+Type]; lpType
0x1800362d3  xor     r8d, r8d; lpReserved
0x1800362d6  mov     [rsp+50h+phkResult], r13; lpData
0x1800362db  lea     rdx, ValueName; "DomainControllerName"
0x1800362e2  call    cs:__imp_RegQueryValueExW
0x1800362e8  mov     esi, eax
0x1800362ea  test    eax, eax
0x1800362ec  jnz     loc_180036573
0x1800362f2  cmp     [rbp+Type], ebx
0x1800362f5  jz      short loc_180036301
0x1800362f7  mov     esi, 65Dh
0x1800362fc  jmp     loc_180036573
0x180036301  mov     edx, [rbp+cbData]; uBytes
0x180036304  mov     ecx, 40h ; '@'; uFlags
0x180036309  call    cs:__imp_LocalAlloc
0x18003630f  mov     r15, rax
0x180036312  test    rax, rax
0x180036315  jnz     short loc_18003631F
0x180036317  lea     esi, [rax+8]
0x18003631a  jmp     loc_180036573
0x18003631f  mov     rcx, [rbp+hKey]; hKey
0x180036323  lea     rax, [rbp+cbData]
0x180036327  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18003632c  lea     r9, [rbp+Type]; lpType
0x180036330  xor     r8d, r8d; lpReserved
0x180036333  mov     [rsp+50h+phkResult], r15; lpData
0x180036338  lea     rdx, ValueName; "DomainControllerName"
0x18003633f  call    cs:__imp_RegQueryValueExW
0x180036345  mov     esi, eax
0x180036347  test    eax, eax
0x180036349  jnz     loc_18003656A
0x18003634f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036353  inc     rax
0x180036356  cmp     [r15+rax*2], r13w
0x18003635b  jnz     short loc_180036353
0x18003635d  cmp     rax, 3
0x180036361  jnb     short loc_18003637E
0x180036363  lea     rdx, aNljoindcpingth_3; "NlJoinDCPingThread: DcName is too short"...
0x18003636a  mov     ecx, 100h; unsigned int
0x18003636f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180036374  mov     esi, 65Dh
0x180036379  jmp     loc_18003656A
0x18003637e  mov     rcx, [rbp+hKey]; hKey
0x180036382  lea     rax, [rbp+cbData]
0x180036386  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18003638b  lea     r9, [rbp+Type]; lpType
0x18003638f  lea     rax, [rbp+Data]
0x180036393  mov     [rbp+cbData], 4
0x18003639a  xor     r8d, r8d; lpReserved
0x18003639d  mov     [rsp+50h+phkResult], rax; lpData
0x1800363a2  lea     rdx, aFlags; "Flags"
0x1800363a9  call    cs:__imp_RegQueryValueExW
0x1800363af  mov     esi, eax
0x1800363b1  test    eax, eax
0x1800363b3  jnz     loc_18003656A
0x1800363b9  cmp     [rbp+Type], 4
0x1800363bd  jnz     short loc_180036374
0x1800363bf  mov     r9d, dword ptr [rbp+Data]
0x1800363c3  lea     rdx, aNljoindcpingth_0; "NlJoinDCPingThread:  Join DC: %ws, Flag"...
0x1800363ca  mov     r8, r15
0x1800363cd  mov     ecx, ebx; unsigned int
0x1800363cf  mov     esi, r13d
0x1800363d2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800363d7  call    ?NetpIncJoinDomainEntryUseCount@@YAXXZ; NetpIncJoinDomainEntryUseCount(void)
0x1800363dc  test    [rbp+Data], 10h
0x1800363e0  mov     r12d, ebx
0x1800363e3  jnz     loc_18003647E
0x1800363e9  lea     rdx, aNljoindcpingth_14; "NlJoinDCPingThread: Join DC is not NT5,"...
0x1800363f0  mov     [rbp+arg_18], r13
0x1800363f4  mov     ecx, ebx; unsigned int
0x1800363f6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800363fb  lea     rax, [rbp+arg_18]
0x1800363ff  mov     r9d, 0F003Fh; samDesired
0x180036405  xor     r8d, r8d; ulOptions
0x180036408  mov     [rsp+50h+phkResult], rax; phkResult
0x18003640d  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x180036414  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003641b  call    cs:__imp_RegOpenKeyExW
0x180036421  test    eax, eax
0x180036423  jnz     short loc_180036460
0x180036425  mov     rcx, [rbp+arg_18]; hKey
0x180036429  lea     rdx, aJoindomain; "JoinDomain"
0x180036430  xor     r9d, r9d; Reserved
0x180036433  xor     r8d, r8d; samDesired
0x180036436  call    cs:__imp_RegDeleteKeyExW
0x18003643c  test    eax, eax
0x18003643e  jz      short loc_180036454
0x180036440  mov     r8d, eax
0x180036443  lea     rdx, aNljoindcpingth_6; "NlJoinDCPingThread: Couldn't delete Joi"...
0x18003644a  mov     ecx, 100h; unsigned int
0x18003644f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180036454  mov     rcx, [rbp+arg_18]; hKey
0x180036458  call    cs:__imp_RegCloseKey
0x18003645e  jmp     short loc_180036474
0x180036460  mov     r8d, eax
0x180036463  lea     rdx, aNljoindcpingth_2; "NlJoinDCPingThread: RegOpenKeyEx failed"...
0x18003646a  mov     ecx, 100h; unsigned int
0x18003646f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180036474  mov     edi, 0Dh
0x180036479  jmp     loc_18003656A
0x18003647e  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180036482  mov     r12d, r13d
0x180036485  call    cs:__imp_GetSystemTimeAsFileTime
0x18003648b  lea     rdx, aNljoindcpingth_13; "NlJoinDCPingThread: Starting ping loop "...
0x180036492  mov     ecx, ebx; unsigned int
0x180036494  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180036499  mov     r8d, 0Fh
0x18003649f  lea     rdx, aNljoindcpingth_10; "NlJoinDCPingThread: MAX_ELAPSED_TIME_MI"...
0x1800364a6  mov     ecx, ebx; unsigned int
0x1800364a8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800364ad  lea     rcx, [r15+4]; unsigned __int16 *
0x1800364b1  call    ?NlPingJoinDC@@YAKPEAG@Z; NlPingJoinDC(ushort *)
0x1800364b6  mov     edi, eax
0x1800364b8  test    eax, eax
0x1800364ba  jz      loc_180036556
0x1800364c0  test    r12d, r12d
0x1800364c3  jnz     short loc_180036541
0x1800364c5  mov     rcx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800364c9  mov     edx, 0DBBA0h
0x1800364ce  call    NetpLogonTimeHasElapsed
0x1800364d3  test    al, al
0x1800364d5  jnz     short loc_180036538
0x1800364d7  call    ?NlVerifyNetworkUp@@YAKXZ; NlVerifyNetworkUp(void)
0x1800364dc  mov     ecx, ebx; unsigned int
0x1800364de  test    eax, eax
0x1800364e0  jnz     short loc_1800364F3
0x1800364e2  lea     rdx, aNljoindcpingth_1; "NlJoinDCPingThread: NlVerifyNetworkUp()"...
0x1800364e9  mov     r12d, ebx
0x1800364ec  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800364f1  jmp     short loc_18003651B
0x1800364f3  lea     rdx, aNljoindcpingth_17; "NlJoinDCPingThread: sleeping prior to r"...
0x1800364fa  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800364ff  call    ?NlEndNetlogonCall@@YAXXZ; NlEndNetlogonCall(void)
0x180036504  mov     ecx, 1388h; dwMilliseconds
0x180036509  xor     r14d, r14d
0x18003650c  call    cs:__imp_Sleep
0x180036512  call    ?NlStartNetlogonCall@@YAHXZ; NlStartNetlogonCall(void)
0x180036517  test    eax, eax
0x180036519  jz      short loc_180036523
0x18003651b  add     cs:?gdwDCLocatorLoopTries@@3KA, ebx; ulong gdwDCLocatorLoopTries
0x180036521  jmp     short loc_1800364AD
0x180036523  lea     rdx, aNljoindcpingth_11; "NlJoinDCPingThread: NlStartNetlogonCall"...
0x18003652a  mov     ecx, ebx; unsigned int
0x18003652c  mov     edi, 0C0000192h
0x180036531  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180036536  jmp     short loc_180036567
0x180036538  lea     rdx, aNljoindcpingth; "NlJoinDCPingThread: max time expired so"...
0x18003653f  jmp     short loc_18003655D
0x180036541  lea     rdx, aNljoindcpingth_15; "NlJoinDCPingThread: joinDC unpingable a"...
0x180036548  mov     ecx, ebx; unsigned int
0x18003654a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003654f  mov     edi, 54Bh
0x180036554  jmp     short loc_180036564
0x180036556  lea     rdx, aNljoindcpingth_16; "NlJoinDCPingThread: join DC pinged, exi"...
0x18003655d  mov     ecx, ebx; unsigned int
0x18003655f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180036564  mov     r14d, ebx
0x180036567  mov     r12d, ebx
0x18003656a  mov     rcx, r15; hMem
0x18003656d  call    cs:__imp_LocalFree
0x180036573  mov     rcx, [rbp+hKey]; hKey
0x180036577  test    rcx, rcx
0x18003657a  jz      short loc_180036582
0x18003657c  call    cs:__imp_RegCloseKey
0x180036582  test    r12d, r12d
0x180036585  jnz     short loc_18003658C
0x180036587  call    ?NetpIncJoinDomainEntryUseCount@@YAXXZ; NetpIncJoinDomainEntryUseCount(void)
0x18003658c  test    esi, esi
0x18003658e  jnz     short loc_180036599
0x180036590  test    edi, edi
0x180036592  jnz     short loc_18003659F
0x180036594  mov     edi, r13d
0x180036597  jmp     short loc_18003659F
0x180036599  test    edi, edi
0x18003659b  jnz     short loc_18003659F
0x18003659d  mov     edi, esi
0x18003659f  mov     cs:?NlGlobalJoinLogicDone@@3HA, ebx; int NlGlobalJoinLogicDone
0x1800365a5  test    r14d, r14d
0x1800365a8  jz      short loc_1800365C0
0x1800365aa  mov     r8d, edi
0x1800365ad  lea     rdx, aNljoindcpingth_8; "NlJoinDCPingThread: exiting with return"...
0x1800365b4  mov     ecx, ebx; unsigned int
0x1800365b6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800365bb  call    ?NlEndNetlogonCall@@YAXXZ; NlEndNetlogonCall(void)
0x1800365c0  mov     rbx, [rsp+50h+arg_0]
0x1800365c8  mov     eax, edi
0x1800365ca  add     rsp, 50h
0x1800365ce  pop     r15
0x1800365d0  pop     r14
0x1800365d2  pop     r13
0x1800365d4  pop     r12
0x1800365d6  pop     rdi
0x1800365d7  pop     rsi
0x1800365d8  pop     rbp
0x1800365d9  retn
```
