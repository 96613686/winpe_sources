# InitializeIISUtil

- ea: `0x18001fbd0`
- end: `0x18001fd8f`
- name: `InitializeIISUtil`
- size: `447`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008000`
- `0x1800166dc`
- `0x18001fbd0`
- `0x180020f90`
- `0x180021470`
- `0x180023c24`
- `0x1800262b4`
- `0x180027968`
- `0x1800280f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fd07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fd56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fd07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fd56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd31`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001fd21`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001fd21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fd7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fd7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fbe2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fbe2`

## string_xrefs

- `0x18001fc29`: `servercommon\inetsrv\iis\iisrearc\core\common\util\init_iisutil.cxx`
- `0x18001fc9c`: `servercommon\inetsrv\iis\iisrearc\core\common\util\init_iisutil.cxx`
- `0x18001fcde`: `servercommon\inetsrv\iis\iisrearc\core\common\util\init_iisutil.cxx`

## pseudocode

```c
__int64 InitializeIISUtil()
{
  unsigned int v0; // ebx
  bool v2; // zf
  char v3; // al
  int v4; // eax
  DWORD v5; // eax
  signed int LastError; // eax
  bool v7; // sf
  DWORD v8; // eax
  char v10; // [rsp+28h] [rbp-20h]

  v0 = 1;
  EnterCriticalSection(&CriticalSection);
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 4) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\init_iisutil.cxx",
      0x113u,
      "InitializeIISUtil",
      "InitializeIISUtil, %d %s\n",
      dword_180050504[0]);
  if ( !(*(_DWORD *)dword_180050504)++ )
  {
    v2 = (unsigned int)SchedulerInitialize() == 0;
    v3 = g_dwDebugFlagsIISUtil;
    if ( v2 )
    {
      if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      {
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\init_iisutil.cxx",
          0x11Cu,
          "InitializeIISUtil",
          "Initializing Scheduler Failed\n",
          v10);
        v3 = g_dwDebugFlagsIISUtil;
      }
      v0 = 0;
    }
    if ( (v3 & 3) != 0 && (v3 & 4) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\init_iisutil.cxx",
        0x121u,
        "InitializeIISUtil",
        "Scheduler Initialized\n",
        v10);
    v0 &= -ALLOC_CACHE_HANDLER::SetLookasideCleanupInterval();
    v4 = InitializeTokenAcl();
    if ( v4 < 0 )
    {
      v5 = WIN32_FROM_HRESULT(v4);
      SetLastError(v5);
      v0 = 0;
    }
    if ( !InitializeCriticalSectionAndSpinCount(&g_csLocalizedResourceDll, 0x3E8u) )
    {
      LastError = GetLastError();
      v7 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v7 = LastError < 0;
      }
      if ( v7 )
      {
        v8 = WIN32_FROM_HRESULT(LastError);
        SetLastError(v8);
        v0 = 0;
      }
    }
    InitializeDateTime();
    UlInitializeParsing();
    InitializeNormalizeUrl();
  }
  LeaveCriticalSection(&CriticalSection);
  return v0;
}

```

## disassembly

```asm
0x18001fbd0  push    rbx
0x18001fbd2  sub     rsp, 40h
0x18001fbd6  lea     rcx, CriticalSection; lpCriticalSection
0x18001fbdd  mov     ebx, 1
0x18001fbe2  call    cs:__imp_EnterCriticalSection
0x18001fbe9  nop     dword ptr [rax+rax+00h]
0x18001fbee  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18001fbf4  test    al, 3
0x18001fbf6  setnz   cl
0x18001fbf9  test    al, 4
0x18001fbfb  setnz   al
0x18001fbfe  test    al, cl
0x18001fc00  jz      short loc_18001FC51
0x18001fc02  mov     eax, cs:dword_180050504
0x18001fc08  lea     rdx, byte_180033FA9
0x18001fc0f  test    eax, eax
0x18001fc11  lea     rcx, aInitializing; "initializing"
0x18001fc18  lea     r9, aInitializeiisu_2; "InitializeIISUtil"
0x18001fc1f  mov     r8d, 113h; unsigned int
0x18001fc25  cmovnz  rcx, rdx
0x18001fc29  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001fc30  mov     [rsp+48h+var_18], rcx
0x18001fc35  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001fc3c  mov     dword ptr [rsp+48h+var_20], eax; char
0x18001fc40  lea     rax, aInitializeiisu_3; "InitializeIISUtil, %d %s\n"
0x18001fc47  mov     [rsp+48h+var_28], rax; char *
0x18001fc4c  call    PuDbgPrint
0x18001fc51  mov     eax, cs:dword_180050504
0x18001fc57  mov     ecx, eax
0x18001fc59  add     eax, ebx
0x18001fc5b  mov     cs:dword_180050504, eax
0x18001fc61  test    ecx, ecx
0x18001fc63  jnz     loc_18001FD73
0x18001fc69  call    ?SchedulerInitialize@@YAHXZ; SchedulerInitialize(void)
0x18001fc6e  test    eax, eax
0x18001fc70  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18001fc76  jnz     short loc_18001FCB0
0x18001fc78  test    al, 3
0x18001fc7a  jz      short loc_18001FCAE
0x18001fc7c  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001fc83  lea     rax, aInitializingSc; "Initializing Scheduler Failed\n"
0x18001fc8a  lea     r9, aInitializeiisu_2; "InitializeIISUtil"
0x18001fc91  mov     [rsp+48h+var_28], rax; char *
0x18001fc96  mov     r8d, 11Ch; unsigned int
0x18001fc9c  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001fca3  call    PuDbgPrint
0x18001fca8  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18001fcae  xor     ebx, ebx
0x18001fcb0  test    al, 3
0x18001fcb2  setnz   cl
0x18001fcb5  test    al, 4
0x18001fcb7  setnz   al
0x18001fcba  test    al, cl
0x18001fcbc  jz      short loc_18001FCEA
0x18001fcbe  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001fcc5  lea     rax, aSchedulerIniti; "Scheduler Initialized\n"
0x18001fccc  lea     r9, aInitializeiisu_2; "InitializeIISUtil"
0x18001fcd3  mov     [rsp+48h+var_28], rax; char *
0x18001fcd8  mov     r8d, 121h; unsigned int
0x18001fcde  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001fce5  call    PuDbgPrint
0x18001fcea  call    ?SetLookasideCleanupInterval@ALLOC_CACHE_HANDLER@@SAHXZ; ALLOC_CACHE_HANDLER::SetLookasideCleanupInterval(void)
0x18001fcef  neg     eax
0x18001fcf1  sbb     ecx, ecx
0x18001fcf3  and     ebx, ecx
0x18001fcf5  call    ?InitializeTokenAcl@@YAJXZ; InitializeTokenAcl(void)
0x18001fcfa  test    eax, eax
0x18001fcfc  jns     short loc_18001FD15
0x18001fcfe  mov     ecx, eax; int
0x18001fd00  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18001fd05  mov     ecx, eax; dwErrCode
0x18001fd07  call    cs:__imp_SetLastError
0x18001fd0e  nop     dword ptr [rax+rax+00h]
0x18001fd13  xor     ebx, ebx
0x18001fd15  mov     edx, 3E8h; dwSpinCount
0x18001fd1a  lea     rcx, ?g_csLocalizedResourceDll@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001fd21  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18001fd28  nop     dword ptr [rax+rax+00h]
0x18001fd2d  test    eax, eax
0x18001fd2f  jnz     short loc_18001FD64
0x18001fd31  call    cs:__imp_GetLastError
0x18001fd38  nop     dword ptr [rax+rax+00h]
0x18001fd3d  test    eax, eax
0x18001fd3f  jle     short loc_18001FD4B
0x18001fd41  movzx   eax, ax
0x18001fd44  or      eax, 80070000h
0x18001fd49  test    eax, eax
0x18001fd4b  jns     short loc_18001FD64
0x18001fd4d  mov     ecx, eax; int
0x18001fd4f  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18001fd54  mov     ecx, eax; dwErrCode
0x18001fd56  call    cs:__imp_SetLastError
0x18001fd5d  nop     dword ptr [rax+rax+00h]
0x18001fd62  xor     ebx, ebx
0x18001fd64  call    ?InitializeDateTime@@YAXXZ; InitializeDateTime(void)
0x18001fd69  call    ?UlInitializeParsing@@YAJXZ; UlInitializeParsing(void)
0x18001fd6e  call    ?InitializeNormalizeUrl@@YAJXZ; InitializeNormalizeUrl(void)
0x18001fd73  lea     rcx, CriticalSection; lpCriticalSection
0x18001fd7a  call    cs:__imp_LeaveCriticalSection
0x18001fd81  nop     dword ptr [rax+rax+00h]
0x18001fd86  mov     eax, ebx
0x18001fd88  add     rsp, 40h
0x18001fd8c  pop     rbx
0x18001fd8d  retn
```
