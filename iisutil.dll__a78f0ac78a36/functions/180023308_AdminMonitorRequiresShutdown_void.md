# AdminMonitorRequiresShutdown(void)

- ea: `0x180023308`
- end: `0x180023491`
- name: `?AdminMonitorRequiresShutdown@@YA?AW4MONITOR_ACTION_TO_TAKE@@XZ`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180023c98`

## callees

- `0x180007300`
- `0x180023308`
- `0x180023498`
- `0x180023a74`
- `0x18002c4c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800233fa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800233fa`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002342e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002342e`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18002344c`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18002344c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180023380`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180023380`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180023469`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180023472`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180023469`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180023472`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002335d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002335d`

## string_xrefs

- `0x1800233df`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`

## pseudocode

```c
__int64 AdminMonitorRequiresShutdown()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // r14
  unsigned int v2; // ebx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  int v5; // edi
  unsigned int v6; // edi
  DWORD dwMilliseconds; // [rsp+30h] [rbp-40h] BYREF
  DWORD v9; // [rsp+34h] [rbp-3Ch] BYREF
  char v10[4]; // [rsp+38h] [rbp-38h] BYREF
  unsigned int v11; // [rsp+3Ch] [rbp-34h] BYREF
  BYTE Buffer[16]; // [rsp+40h] [rbp-30h] BYREF
  __int128 v13; // [rsp+50h] [rbp-20h]
  int v14; // [rsp+60h] [rbp-10h]

  dwMilliseconds = 0;
  v11 = 0;
  v9 = 0;
  *(_DWORD *)v10 = 0;
  GetRegistryControlsForInetinfoCrash(&dwMilliseconds, &v11, &v9);
  v0 = OpenSCManagerW(0, 0, 0x80000000);
  v1 = v0;
  if ( v0 )
  {
    v3 = OpenServiceW(v0, L"IISADMIN", 0x80000000);
    v4 = v3;
    if ( v3 )
    {
      DetermineIISResetState(v3, (enum IISRESET_ACTION *)v10);
      v5 = *(_DWORD *)v10;
      if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x8000000) != 0 )
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\adminmonitor.cxx",
          0x3DBu,
          "AdminMonitorRequiresShutdown",
          "Reset action is %d \n",
          v10[0]);
      if ( v5 != 1 || WaitForSingleObject(g_IISAdminMonitorShutdownEvent, dwMilliseconds) )
      {
        v2 = 2;
        if ( v5 == 2 )
        {
          *(_OWORD *)Buffer = 0;
          v14 = 0;
          v6 = 0;
          v13 = 0;
          dwMilliseconds = 0;
          while ( v6 < v11 )
          {
            Sleep(v9);
            if ( QueryServiceStatusEx(v4, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &dwMilliseconds)
              && *(_DWORD *)&Buffer[4] == 4 )
            {
              v2 = 1;
              break;
            }
            v6 += v9;
          }
        }
      }
      else
      {
        v2 = 0;
      }
      CloseServiceHandle(v4);
    }
    else
    {
      v2 = 2;
    }
    CloseServiceHandle(v1);
  }
  else
  {
    return 2;
  }
  return v2;
}

```

## disassembly

```asm
0x180023308  push    rbp
0x18002330a  push    rbx
0x18002330b  push    rsi
0x18002330c  push    rdi
0x18002330d  push    r14
0x18002330f  mov     rbp, rsp
0x180023312  sub     rsp, 70h
0x180023316  mov     rax, cs:__security_cookie
0x18002331d  xor     rax, rsp
0x180023320  mov     [rbp+var_8], rax
0x180023324  lea     r8, [rbp+var_3C]; unsigned int *
0x180023328  mov     [rbp+dwMilliseconds], 0
0x18002332f  lea     rdx, [rbp+var_34]; unsigned int *
0x180023333  mov     [rbp+var_34], 0
0x18002333a  lea     rcx, [rbp+dwMilliseconds]; unsigned int *
0x18002333e  mov     [rbp+var_3C], 0
0x180023345  mov     dword ptr [rbp+var_38], 0
0x18002334c  call    ?GetRegistryControlsForInetinfoCrash@@YAXPEAK00@Z; GetRegistryControlsForInetinfoCrash(ulong *,ulong *,ulong *)
0x180023351  mov     ebx, 80000000h
0x180023356  xor     edx, edx; lpDatabaseName
0x180023358  mov     r8d, ebx; dwDesiredAccess
0x18002335b  xor     ecx, ecx; lpMachineName
0x18002335d  call    cs:__imp_OpenSCManagerW
0x180023363  mov     r14, rax
0x180023366  test    rax, rax
0x180023369  jnz     short loc_180023373
0x18002336b  lea     ebx, [rax+2]
0x18002336e  jmp     loc_180023478
0x180023373  mov     r8d, ebx; dwDesiredAccess
0x180023376  lea     rdx, ServiceName; "IISADMIN"
0x18002337d  mov     rcx, r14; hSCManager
0x180023380  call    cs:__imp_OpenServiceW
0x180023386  mov     rsi, rax
0x180023389  test    rax, rax
0x18002338c  jnz     short loc_180023396
0x18002338e  lea     ebx, [rax+2]
0x180023391  jmp     loc_18002346F
0x180023396  lea     rdx, [rbp+var_38]; enum IISRESET_ACTION *
0x18002339a  mov     rcx, rsi; hService
0x18002339d  call    ?DetermineIISResetState@@YAJPEAUSC_HANDLE__@@PEAW4IISRESET_ACTION@@@Z; DetermineIISResetState(SC_HANDLE__ *,IISRESET_ACTION *)
0x1800233a2  mov     eax, cs:g_dwDebugFlagsIISUtil
0x1800233a8  test    al, 3
0x1800233aa  mov     edi, dword ptr [rbp+var_38]
0x1800233ad  setnz   cl
0x1800233b0  bt      eax, 1Bh
0x1800233b4  setb    al
0x1800233b7  test    al, cl
0x1800233b9  jz      short loc_1800233EB
0x1800233bb  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800233c2  lea     rax, aResetActionIsD; "Reset action is %d \n"
0x1800233c9  mov     dword ptr [rsp+70h+var_48], edi; char
0x1800233cd  lea     r9, aAdminmonitorre; "AdminMonitorRequiresShutdown"
0x1800233d4  mov     r8d, 3DBh; unsigned int
0x1800233da  mov     [rsp+70h+pcbBytesNeeded], rax; char *
0x1800233df  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800233e6  call    PuDbgPrint
0x1800233eb  cmp     edi, 1
0x1800233ee  jnz     short loc_180023408
0x1800233f0  mov     edx, [rbp+dwMilliseconds]; dwMilliseconds
0x1800233f3  mov     rcx, cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA; hHandle
0x1800233fa  call    cs:__imp_WaitForSingleObject
0x180023400  test    eax, eax
0x180023402  jnz     short loc_180023408
0x180023404  xor     ebx, ebx
0x180023406  jmp     short loc_180023466
0x180023408  mov     ebx, 2
0x18002340d  cmp     edi, ebx
0x18002340f  jnz     short loc_180023466
0x180023411  xor     eax, eax
0x180023413  xorps   xmm0, xmm0
0x180023416  movups  xmmword ptr [rbp+Buffer], xmm0
0x18002341a  mov     [rbp+var_10], eax
0x18002341d  xor     edi, edi
0x18002341f  movups  [rbp+var_20], xmm0
0x180023423  mov     [rbp+dwMilliseconds], eax
0x180023426  cmp     edi, [rbp+var_34]
0x180023429  jnb     short loc_180023466
0x18002342b  mov     ecx, [rbp+var_3C]; dwMilliseconds
0x18002342e  call    cs:__imp_Sleep
0x180023434  lea     rax, [rbp+dwMilliseconds]
0x180023438  mov     r9d, 24h ; '$'; cbBufSize
0x18002343e  lea     r8, [rbp+Buffer]; lpBuffer
0x180023442  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180023447  xor     edx, edx; InfoLevel
0x180023449  mov     rcx, rsi; hService
0x18002344c  call    cs:__imp_QueryServiceStatusEx
0x180023452  test    eax, eax
0x180023454  jz      short loc_18002345C
0x180023456  cmp     dword ptr [rbp+Buffer+4], 4
0x18002345a  jz      short loc_180023461
0x18002345c  add     edi, [rbp+var_3C]
0x18002345f  jmp     short loc_180023426
0x180023461  mov     ebx, 1
0x180023466  mov     rcx, rsi; hSCObject
0x180023469  call    cs:__imp_CloseServiceHandle
0x18002346f  mov     rcx, r14; hSCObject
0x180023472  call    cs:__imp_CloseServiceHandle
0x180023478  mov     eax, ebx
0x18002347a  mov     rcx, [rbp+var_8]
0x18002347e  xor     rcx, rsp; StackCookie
0x180023481  call    __security_check_cookie
0x180023486  add     rsp, 70h
0x18002348a  pop     r14
0x18002348c  pop     rdi
0x18002348d  pop     rsi
0x18002348e  pop     rbx
0x18002348f  pop     rbp
0x180023490  retn
```
