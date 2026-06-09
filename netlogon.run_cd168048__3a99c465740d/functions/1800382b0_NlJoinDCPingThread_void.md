# NlJoinDCPingThread(void *)

- ea: `0x1800382b0`
- end: `0x1800386a7`
- name: `?NlJoinDCPingThread@@YAKPEAX@Z`
- size: `1015`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x180003ce0`
- `0x180007518`
- `0x18000d444`
- `0x18000d854`
- `0x1800382b0`
- `0x180038944`
- `0x18003b4b4`
- `0x180083478`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800385c6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800385c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038395`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038395`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003862d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003862d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038368`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800383d1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038441`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038368`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800383d1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038441`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800384da`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800384da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038332`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800384b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038332`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800384b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038502`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038642`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038502`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038642`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180038535`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180038535`

## string_xrefs

- `0x18003831e`: `SYSTEM\CurrentControlSet\Services\Netlogon\JoinDomain`
- `0x1800382ee`: `NlJoinDCPingThread: NlStartNetlogonCall failed\n`
- `0x1800383fb`: `NlJoinDCPingThread: DcName is too short.\n`
- `0x180038461`: `NlJoinDCPingThread:  Join DC: %ws, Flags: 0x%lx\n`
- `0x180038487`: `NlJoinDCPingThread: Join DC is not NT5, deleting it\n`
- `0x1800384ab`: `SYSTEM\CurrentControlSet\Services\Netlogon`
- `0x1800384ed`: `NlJoinDCPingThread: Couldn't delete JoinDomain 0x%lx\n`
- `0x180038513`: `NlJoinDCPingThread: RegOpenKeyEx failed 0x%lx\n`
- `0x180038541`: `NlJoinDCPingThread: Starting ping loop now\n`
- `0x180038555`: `NlJoinDCPingThread: MAX_ELAPSED_TIME_MIN is %d minutes\n`
- `0x180038616`: `NlJoinDCPingThread: join DC pinged, exiting loop\n`
- `0x180038601`: `NlJoinDCPingThread: joinDC unpingable after network up\n`
- `0x1800385f8`: `NlJoinDCPingThread: max time expired so exiting loop now\n`
- `0x18003859c`: `NlJoinDCPingThread: NlVerifyNetworkUp() succeeded\n`
- `0x1800385ad`: `NlJoinDCPingThread: sleeping prior to retry\n`
- `0x1800385e3`: `NlJoinDCPingThread: NlStartNetlogonCall failed after sleep\n`
- `0x180038679`: `NlJoinDCPingThread: exiting with return code=0x%lx\n`

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
0x1800382b0  mov     [rsp-38h+arg_0], rbx
0x1800382b5  push    rbp
0x1800382b6  push    rsi
0x1800382b7  push    rdi
0x1800382b8  push    r12
0x1800382ba  push    r13
0x1800382bc  push    r14
0x1800382be  push    r15
0x1800382c0  mov     rbp, rsp
0x1800382c3  sub     rsp, 50h
0x1800382c7  xor     r13d, r13d
0x1800382ca  mov     [rbp+hKey], r13
0x1800382ce  mov     r12d, r13d
0x1800382d1  mov     [rbp+cbData], r13d
0x1800382d5  mov     dword ptr [rbp+Data], r13d
0x1800382d9  mov     [rbp+Type], r13d
0x1800382dd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r13
0x1800382e1  call    ?NlStartNetlogonCall@@YAHXZ; NlStartNetlogonCall(void)
0x1800382e6  lea     ebx, [r13+1]
0x1800382ea  test    eax, eax
0x1800382ec  jnz     short loc_18003830C
0x1800382ee  lea     rdx, aNljoindcpingth_5; "NlJoinDCPingThread: NlStartNetlogonCall"...
0x1800382f5  mov     ecx, ebx; unsigned int
0x1800382f7  mov     r14d, r13d
0x1800382fa  mov     esi, r13d
0x1800382fd  mov     edi, 0C0000192h
0x180038302  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180038307  jmp     loc_180038639
0x18003830c  lea     rax, [rbp+hKey]
0x180038310  mov     r9d, 2000000h; samDesired
0x180038316  xor     r8d, r8d; ulOptions
0x180038319  mov     [rsp+50h+phkResult], rax; phkResult
0x18003831e  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x180038325  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003832c  mov     edi, r13d
0x18003832f  mov     r14d, ebx
0x180038332  call    cs:__imp_RegOpenKeyExW
0x180038339  nop     dword ptr [rax+rax+00h]
0x18003833e  mov     esi, eax
0x180038340  test    eax, eax
0x180038342  jnz     loc_180038639
0x180038348  mov     rcx, [rbp+hKey]; hKey
0x18003834c  lea     rax, [rbp+cbData]
0x180038350  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180038355  lea     r9, [rbp+Type]; lpType
0x180038359  xor     r8d, r8d; lpReserved
0x18003835c  mov     [rsp+50h+phkResult], r13; lpData
0x180038361  lea     rdx, ValueName; "DomainControllerName"
0x180038368  call    cs:__imp_RegQueryValueExW
0x18003836f  nop     dword ptr [rax+rax+00h]
0x180038374  mov     esi, eax
0x180038376  test    eax, eax
0x180038378  jnz     loc_180038639
0x18003837e  cmp     [rbp+Type], ebx
0x180038381  jz      short loc_18003838D
0x180038383  mov     esi, 65Dh
0x180038388  jmp     loc_180038639
0x18003838d  mov     edx, [rbp+cbData]; uBytes
0x180038390  mov     ecx, 40h ; '@'; uFlags
0x180038395  call    cs:__imp_LocalAlloc
0x18003839c  nop     dword ptr [rax+rax+00h]
0x1800383a1  mov     r15, rax
0x1800383a4  test    rax, rax
0x1800383a7  jnz     short loc_1800383B1
0x1800383a9  lea     esi, [rax+8]
0x1800383ac  jmp     loc_180038639
0x1800383b1  mov     rcx, [rbp+hKey]; hKey
0x1800383b5  lea     rax, [rbp+cbData]
0x1800383b9  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800383be  lea     r9, [rbp+Type]; lpType
0x1800383c2  xor     r8d, r8d; lpReserved
0x1800383c5  mov     [rsp+50h+phkResult], r15; lpData
0x1800383ca  lea     rdx, ValueName; "DomainControllerName"
0x1800383d1  call    cs:__imp_RegQueryValueExW
0x1800383d8  nop     dword ptr [rax+rax+00h]
0x1800383dd  mov     esi, eax
0x1800383df  test    eax, eax
0x1800383e1  jnz     loc_18003862A
0x1800383e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800383eb  inc     rax
0x1800383ee  cmp     [r15+rax*2], r13w
0x1800383f3  jnz     short loc_1800383EB
0x1800383f5  cmp     rax, 3
0x1800383f9  jnb     short loc_180038416
0x1800383fb  lea     rdx, aNljoindcpingth_3; "NlJoinDCPingThread: DcName is too short"...
0x180038402  mov     ecx, 100h; unsigned int
0x180038407  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003840c  mov     esi, 65Dh
0x180038411  jmp     loc_18003862A
0x180038416  mov     rcx, [rbp+hKey]; hKey
0x18003841a  lea     rax, [rbp+cbData]
0x18003841e  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180038423  lea     r9, [rbp+Type]; lpType
0x180038427  lea     rax, [rbp+Data]
0x18003842b  mov     [rbp+cbData], 4
0x180038432  xor     r8d, r8d; lpReserved
0x180038435  mov     [rsp+50h+phkResult], rax; lpData
0x18003843a  lea     rdx, aFlags; "Flags"
0x180038441  call    cs:__imp_RegQueryValueExW
0x180038448  nop     dword ptr [rax+rax+00h]
0x18003844d  mov     esi, eax
0x18003844f  test    eax, eax
0x180038451  jnz     loc_18003862A
0x180038457  cmp     [rbp+Type], 4
0x18003845b  jnz     short loc_18003840C
0x18003845d  mov     r9d, dword ptr [rbp+Data]
0x180038461  lea     rdx, aNljoindcpingth_0; "NlJoinDCPingThread:  Join DC: %ws, Flag"...
0x180038468  mov     r8, r15
0x18003846b  mov     ecx, ebx; unsigned int
0x18003846d  mov     esi, r13d
0x180038470  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180038475  call    ?NetpIncJoinDomainEntryUseCount@@YAXXZ; NetpIncJoinDomainEntryUseCount(void)
0x18003847a  test    [rbp+Data], 10h
0x18003847e  mov     r12d, ebx
0x180038481  jnz     loc_18003852E
0x180038487  lea     rdx, aNljoindcpingth_14; "NlJoinDCPingThread: Join DC is not NT5,"...
0x18003848e  mov     [rbp+arg_18], r13
0x180038492  mov     ecx, ebx; unsigned int
0x180038494  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180038499  lea     rax, [rbp+arg_18]
0x18003849d  mov     r9d, 0F003Fh; samDesired
0x1800384a3  xor     r8d, r8d; ulOptions
0x1800384a6  mov     [rsp+50h+phkResult], rax; phkResult
0x1800384ab  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x1800384b2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800384b9  call    cs:__imp_RegOpenKeyExW
0x1800384c0  nop     dword ptr [rax+rax+00h]
0x1800384c5  test    eax, eax
0x1800384c7  jnz     short loc_180038510
0x1800384c9  mov     rcx, [rbp+arg_18]; hKey
0x1800384cd  lea     rdx, aJoindomain; "JoinDomain"
0x1800384d4  xor     r9d, r9d; Reserved
0x1800384d7  xor     r8d, r8d; samDesired
0x1800384da  call    cs:__imp_RegDeleteKeyExW
0x1800384e1  nop     dword ptr [rax+rax+00h]
0x1800384e6  test    eax, eax
0x1800384e8  jz      short loc_1800384FE
0x1800384ea  mov     r8d, eax
0x1800384ed  lea     rdx, aNljoindcpingth_6; "NlJoinDCPingThread: Couldn't delete Joi"...
0x1800384f4  mov     ecx, 100h; unsigned int
0x1800384f9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800384fe  mov     rcx, [rbp+arg_18]; hKey
0x180038502  call    cs:__imp_RegCloseKey
0x180038509  nop     dword ptr [rax+rax+00h]
0x18003850e  jmp     short loc_180038524
0x180038510  mov     r8d, eax
0x180038513  lea     rdx, aNljoindcpingth_2; "NlJoinDCPingThread: RegOpenKeyEx failed"...
0x18003851a  mov     ecx, 100h; unsigned int
0x18003851f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180038524  mov     edi, 0Dh
0x180038529  jmp     loc_18003862A
0x18003852e  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180038532  mov     r12d, r13d
0x180038535  call    cs:__imp_GetSystemTimeAsFileTime
0x18003853c  nop     dword ptr [rax+rax+00h]
0x180038541  lea     rdx, aNljoindcpingth_13; "NlJoinDCPingThread: Starting ping loop "...
0x180038548  mov     ecx, ebx; unsigned int
0x18003854a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003854f  mov     r8d, 0Fh
0x180038555  lea     rdx, aNljoindcpingth_10; "NlJoinDCPingThread: MAX_ELAPSED_TIME_MI"...
0x18003855c  mov     ecx, ebx; unsigned int
0x18003855e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180038563  lea     rcx, [r15+4]; unsigned __int16 *
0x180038567  call    ?NlPingJoinDC@@YAKPEAG@Z; NlPingJoinDC(ushort *)
0x18003856c  mov     edi, eax
0x18003856e  test    eax, eax
0x180038570  jz      loc_180038616
0x180038576  test    r12d, r12d
0x180038579  jnz     loc_180038601
0x18003857f  mov     rcx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180038583  mov     edx, 0DBBA0h
0x180038588  call    NetpLogonTimeHasElapsed
0x18003858d  test    al, al
0x18003858f  jnz     short loc_1800385F8
0x180038591  call    ?NlVerifyNetworkUp@@YAKXZ; NlVerifyNetworkUp(void)
0x180038596  mov     ecx, ebx; unsigned int
0x180038598  test    eax, eax
0x18003859a  jnz     short loc_1800385AD
0x18003859c  lea     rdx, aNljoindcpingth_1; "NlJoinDCPingThread: NlVerifyNetworkUp()"...
0x1800385a3  mov     r12d, ebx
0x1800385a6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800385ab  jmp     short loc_1800385DB
0x1800385ad  lea     rdx, aNljoindcpingth_17; "NlJoinDCPingThread: sleeping prior to r"...
0x1800385b4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800385b9  call    ?NlEndNetlogonCall@@YAXXZ; NlEndNetlogonCall(void)
0x1800385be  mov     ecx, 1388h; dwMilliseconds
0x1800385c3  xor     r14d, r14d
0x1800385c6  call    cs:__imp_Sleep
0x1800385cd  nop     dword ptr [rax+rax+00h]
0x1800385d2  call    ?NlStartNetlogonCall@@YAHXZ; NlStartNetlogonCall(void)
0x1800385d7  test    eax, eax
0x1800385d9  jz      short loc_1800385E3
0x1800385db  add     cs:?gdwDCLocatorLoopTries@@3KA, ebx; ulong gdwDCLocatorLoopTries
0x1800385e1  jmp     short loc_180038563
0x1800385e3  lea     rdx, aNljoindcpingth_11; "NlJoinDCPingThread: NlStartNetlogonCall"...
0x1800385ea  mov     ecx, ebx; unsigned int
0x1800385ec  mov     edi, 0C0000192h
0x1800385f1  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800385f6  jmp     short loc_180038627
0x1800385f8  lea     rdx, aNljoindcpingth; "NlJoinDCPingThread: max time expired so"...
0x1800385ff  jmp     short loc_18003861D
0x180038601  lea     rdx, aNljoindcpingth_15; "NlJoinDCPingThread: joinDC unpingable a"...
0x180038608  mov     ecx, ebx; unsigned int
0x18003860a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003860f  mov     edi, 54Bh
0x180038614  jmp     short loc_180038624
0x180038616  lea     rdx, aNljoindcpingth_16; "NlJoinDCPingThread: join DC pinged, exi"...
0x18003861d  mov     ecx, ebx; unsigned int
0x18003861f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180038624  mov     r14d, ebx
0x180038627  mov     r12d, ebx
0x18003862a  mov     rcx, r15; hMem
0x18003862d  call    cs:__imp_LocalFree
0x180038634  nop     dword ptr [rax+rax+00h]
0x180038639  mov     rcx, [rbp+hKey]; hKey
0x18003863d  test    rcx, rcx
0x180038640  jz      short loc_18003864E
0x180038642  call    cs:__imp_RegCloseKey
0x180038649  nop     dword ptr [rax+rax+00h]
0x18003864e  test    r12d, r12d
0x180038651  jnz     short loc_180038658
0x180038653  call    ?NetpIncJoinDomainEntryUseCount@@YAXXZ; NetpIncJoinDomainEntryUseCount(void)
0x180038658  test    esi, esi
0x18003865a  jnz     short loc_180038665
0x18003865c  test    edi, edi
0x18003865e  jnz     short loc_18003866B
0x180038660  mov     edi, r13d
0x180038663  jmp     short loc_18003866B
0x180038665  test    edi, edi
0x180038667  jnz     short loc_18003866B
0x180038669  mov     edi, esi
0x18003866b  mov     cs:?NlGlobalJoinLogicDone@@3HA, ebx; int NlGlobalJoinLogicDone
0x180038671  test    r14d, r14d
0x180038674  jz      short loc_18003868C
0x180038676  mov     r8d, edi
0x180038679  lea     rdx, aNljoindcpingth_8; "NlJoinDCPingThread: exiting with return"...
0x180038680  mov     ecx, ebx; unsigned int
0x180038682  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180038687  call    ?NlEndNetlogonCall@@YAXXZ; NlEndNetlogonCall(void)
0x18003868c  mov     rbx, [rsp+50h+arg_0]
0x180038694  mov     eax, edi
0x180038696  add     rsp, 50h
0x18003869a  pop     r15
0x18003869c  pop     r14
0x18003869e  pop     r13
0x1800386a0  pop     r12
0x1800386a2  pop     rdi
0x1800386a3  pop     rsi
0x1800386a4  pop     rbp
0x1800386a5  retn
```
