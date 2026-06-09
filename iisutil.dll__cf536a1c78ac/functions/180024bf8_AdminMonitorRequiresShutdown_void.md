# AdminMonitorRequiresShutdown(void)

- ea: `0x180024bf8`
- end: `0x180024dac`
- name: `?AdminMonitorRequiresShutdown@@YA?AW4MONITOR_ACTION_TO_TAKE@@XZ`
- size: `436`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002566c`

## callees

- `0x180008000`
- `0x180024bf8`
- `0x180024db4`
- `0x180025418`
- `0x18002e560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180024cf6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180024cf6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180024d30`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180024d30`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180024d54`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180024d54`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180024c76`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180024c76`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180024d77`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180024d86`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180024d77`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180024d86`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180024c4d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180024c4d`

## string_xrefs

- `0x180024cdb`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`

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
0x180024bf8  push    rbp
0x180024bfa  push    rbx
0x180024bfb  push    rsi
0x180024bfc  push    rdi
0x180024bfd  push    r14
0x180024bff  mov     rbp, rsp
0x180024c02  sub     rsp, 70h
0x180024c06  mov     rax, cs:__security_cookie
0x180024c0d  xor     rax, rsp
0x180024c10  mov     [rbp+var_8], rax
0x180024c14  lea     r8, [rbp+var_3C]; unsigned int *
0x180024c18  mov     [rbp+dwMilliseconds], 0
0x180024c1f  lea     rdx, [rbp+var_34]; unsigned int *
0x180024c23  mov     [rbp+var_34], 0
0x180024c2a  lea     rcx, [rbp+dwMilliseconds]; unsigned int *
0x180024c2e  mov     [rbp+var_3C], 0
0x180024c35  mov     dword ptr [rbp+var_38], 0
0x180024c3c  call    ?GetRegistryControlsForInetinfoCrash@@YAXPEAK00@Z; GetRegistryControlsForInetinfoCrash(ulong *,ulong *,ulong *)
0x180024c41  mov     ebx, 80000000h
0x180024c46  xor     edx, edx; lpDatabaseName
0x180024c48  mov     r8d, ebx; dwDesiredAccess
0x180024c4b  xor     ecx, ecx; lpMachineName
0x180024c4d  call    cs:__imp_OpenSCManagerW
0x180024c54  nop     dword ptr [rax+rax+00h]
0x180024c59  mov     r14, rax
0x180024c5c  test    rax, rax
0x180024c5f  jnz     short loc_180024C69
0x180024c61  lea     ebx, [rax+2]
0x180024c64  jmp     loc_180024D92
0x180024c69  mov     r8d, ebx; dwDesiredAccess
0x180024c6c  lea     rdx, ServiceName; "IISADMIN"
0x180024c73  mov     rcx, r14; hSCManager
0x180024c76  call    cs:__imp_OpenServiceW
0x180024c7d  nop     dword ptr [rax+rax+00h]
0x180024c82  mov     rsi, rax
0x180024c85  test    rax, rax
0x180024c88  jnz     short loc_180024C92
0x180024c8a  lea     ebx, [rax+2]
0x180024c8d  jmp     loc_180024D83
0x180024c92  lea     rdx, [rbp+var_38]; enum IISRESET_ACTION *
0x180024c96  mov     rcx, rsi; hService
0x180024c99  call    ?DetermineIISResetState@@YAJPEAUSC_HANDLE__@@PEAW4IISRESET_ACTION@@@Z; DetermineIISResetState(SC_HANDLE__ *,IISRESET_ACTION *)
0x180024c9e  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180024ca4  test    al, 3
0x180024ca6  mov     edi, dword ptr [rbp+var_38]
0x180024ca9  setnz   cl
0x180024cac  bt      eax, 1Bh
0x180024cb0  setb    al
0x180024cb3  test    al, cl
0x180024cb5  jz      short loc_180024CE7
0x180024cb7  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180024cbe  lea     rax, aResetActionIsD; "Reset action is %d \n"
0x180024cc5  mov     dword ptr [rsp+70h+var_48], edi; char
0x180024cc9  lea     r9, aAdminmonitorre; "AdminMonitorRequiresShutdown"
0x180024cd0  mov     r8d, 3DBh; unsigned int
0x180024cd6  mov     [rsp+70h+pcbBytesNeeded], rax; char *
0x180024cdb  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180024ce2  call    PuDbgPrint
0x180024ce7  cmp     edi, 1
0x180024cea  jnz     short loc_180024D0A
0x180024cec  mov     edx, [rbp+dwMilliseconds]; dwMilliseconds
0x180024cef  mov     rcx, cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA; hHandle
0x180024cf6  call    cs:__imp_WaitForSingleObject
0x180024cfd  nop     dword ptr [rax+rax+00h]
0x180024d02  test    eax, eax
0x180024d04  jnz     short loc_180024D0A
0x180024d06  xor     ebx, ebx
0x180024d08  jmp     short loc_180024D74
0x180024d0a  mov     ebx, 2
0x180024d0f  cmp     edi, ebx
0x180024d11  jnz     short loc_180024D74
0x180024d13  xor     eax, eax
0x180024d15  xorps   xmm0, xmm0
0x180024d18  movups  xmmword ptr [rbp+Buffer], xmm0
0x180024d1c  mov     [rbp+var_10], eax
0x180024d1f  xor     edi, edi
0x180024d21  movups  [rbp+var_20], xmm0
0x180024d25  mov     [rbp+dwMilliseconds], eax
0x180024d28  cmp     edi, [rbp+var_34]
0x180024d2b  jnb     short loc_180024D74
0x180024d2d  mov     ecx, [rbp+var_3C]; dwMilliseconds
0x180024d30  call    cs:__imp_Sleep
0x180024d37  nop     dword ptr [rax+rax+00h]
0x180024d3c  lea     rax, [rbp+dwMilliseconds]
0x180024d40  mov     r9d, 24h ; '$'; cbBufSize
0x180024d46  lea     r8, [rbp+Buffer]; lpBuffer
0x180024d4a  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180024d4f  xor     edx, edx; InfoLevel
0x180024d51  mov     rcx, rsi; hService
0x180024d54  call    cs:__imp_QueryServiceStatusEx
0x180024d5b  nop     dword ptr [rax+rax+00h]
0x180024d60  test    eax, eax
0x180024d62  jz      short loc_180024D6A
0x180024d64  cmp     dword ptr [rbp+Buffer+4], 4
0x180024d68  jz      short loc_180024D6F
0x180024d6a  add     edi, [rbp+var_3C]
0x180024d6d  jmp     short loc_180024D28
0x180024d6f  mov     ebx, 1
0x180024d74  mov     rcx, rsi; hSCObject
0x180024d77  call    cs:__imp_CloseServiceHandle
0x180024d7e  nop     dword ptr [rax+rax+00h]
0x180024d83  mov     rcx, r14; hSCObject
0x180024d86  call    cs:__imp_CloseServiceHandle
0x180024d8d  nop     dword ptr [rax+rax+00h]
0x180024d92  mov     eax, ebx
0x180024d94  mov     rcx, [rbp+var_8]
0x180024d98  xor     rcx, rsp; StackCookie
0x180024d9b  call    __security_check_cookie
0x180024da0  add     rsp, 70h
0x180024da4  pop     r14
0x180024da6  pop     rdi
0x180024da7  pop     rsi
0x180024da8  pop     rbx
0x180024da9  pop     rbp
0x180024daa  retn
```
