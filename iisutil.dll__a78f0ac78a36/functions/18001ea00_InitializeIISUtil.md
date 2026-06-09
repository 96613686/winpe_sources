# InitializeIISUtil

- ea: `0x18001ea00`
- end: `0x18001eb9a`
- name: `InitializeIISUtil`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007300`
- `0x180015b4c`
- `0x18001ea00`
- `0x18001fc60`
- `0x1800200e0`
- `0x1800224a8`
- `0x180024848`
- `0x180025dc0`
- `0x1800264fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001eb31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001eb6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001eb31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001eb6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb4f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001eb45`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001eb45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001eb8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001eb8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ea12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ea12`

## string_xrefs

- `0x18001ea53`: `servercommon\inetsrv\iis\iisrearc\core\common\util\init_iisutil.cxx`
- `0x18001eac6`: `servercommon\inetsrv\iis\iisrearc\core\common\util\init_iisutil.cxx`
- `0x18001eb08`: `servercommon\inetsrv\iis\iisrearc\core\common\util\init_iisutil.cxx`

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
      dword_18004E50C[0]);
  if ( !(*(_DWORD *)dword_18004E50C)++ )
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
0x18001ea00  push    rbx
0x18001ea02  sub     rsp, 40h
0x18001ea06  lea     rcx, CriticalSection; lpCriticalSection
0x18001ea0d  mov     ebx, 1
0x18001ea12  call    cs:__imp_EnterCriticalSection
0x18001ea18  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18001ea1e  test    al, 3
0x18001ea20  setnz   cl
0x18001ea23  test    al, 4
0x18001ea25  setnz   al
0x18001ea28  test    al, cl
0x18001ea2a  jz      short loc_18001EA7B
0x18001ea2c  mov     eax, cs:dword_18004E50C
0x18001ea32  lea     rdx, byte_180031FA9
0x18001ea39  test    eax, eax
0x18001ea3b  lea     rcx, aInitializing; "initializing"
0x18001ea42  lea     r9, aInitializeiisu_2; "InitializeIISUtil"
0x18001ea49  mov     r8d, 113h; unsigned int
0x18001ea4f  cmovnz  rcx, rdx
0x18001ea53  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001ea5a  mov     [rsp+48h+var_18], rcx
0x18001ea5f  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001ea66  mov     dword ptr [rsp+48h+var_20], eax; char
0x18001ea6a  lea     rax, aInitializeiisu_3; "InitializeIISUtil, %d %s\n"
0x18001ea71  mov     [rsp+48h+var_28], rax; char *
0x18001ea76  call    PuDbgPrint
0x18001ea7b  mov     eax, cs:dword_18004E50C
0x18001ea81  mov     ecx, eax
0x18001ea83  add     eax, ebx
0x18001ea85  mov     cs:dword_18004E50C, eax
0x18001ea8b  test    ecx, ecx
0x18001ea8d  jnz     loc_18001EB85
0x18001ea93  call    ?SchedulerInitialize@@YAHXZ; SchedulerInitialize(void)
0x18001ea98  test    eax, eax
0x18001ea9a  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18001eaa0  jnz     short loc_18001EADA
0x18001eaa2  test    al, 3
0x18001eaa4  jz      short loc_18001EAD8
0x18001eaa6  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001eaad  lea     rax, aInitializingSc; "Initializing Scheduler Failed\n"
0x18001eab4  lea     r9, aInitializeiisu_2; "InitializeIISUtil"
0x18001eabb  mov     [rsp+48h+var_28], rax; char *
0x18001eac0  mov     r8d, 11Ch; unsigned int
0x18001eac6  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001eacd  call    PuDbgPrint
0x18001ead2  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18001ead8  xor     ebx, ebx
0x18001eada  test    al, 3
0x18001eadc  setnz   cl
0x18001eadf  test    al, 4
0x18001eae1  setnz   al
0x18001eae4  test    al, cl
0x18001eae6  jz      short loc_18001EB14
0x18001eae8  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001eaef  lea     rax, aSchedulerIniti; "Scheduler Initialized\n"
0x18001eaf6  lea     r9, aInitializeiisu_2; "InitializeIISUtil"
0x18001eafd  mov     [rsp+48h+var_28], rax; char *
0x18001eb02  mov     r8d, 121h; unsigned int
0x18001eb08  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001eb0f  call    PuDbgPrint
0x18001eb14  call    ?SetLookasideCleanupInterval@ALLOC_CACHE_HANDLER@@SAHXZ; ALLOC_CACHE_HANDLER::SetLookasideCleanupInterval(void)
0x18001eb19  neg     eax
0x18001eb1b  sbb     ecx, ecx
0x18001eb1d  and     ebx, ecx
0x18001eb1f  call    ?InitializeTokenAcl@@YAJXZ; InitializeTokenAcl(void)
0x18001eb24  test    eax, eax
0x18001eb26  jns     short loc_18001EB39
0x18001eb28  mov     ecx, eax; int
0x18001eb2a  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18001eb2f  mov     ecx, eax; dwErrCode
0x18001eb31  call    cs:__imp_SetLastError
0x18001eb37  xor     ebx, ebx
0x18001eb39  mov     edx, 3E8h; dwSpinCount
0x18001eb3e  lea     rcx, ?g_csLocalizedResourceDll@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001eb45  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18001eb4b  test    eax, eax
0x18001eb4d  jnz     short loc_18001EB76
0x18001eb4f  call    cs:__imp_GetLastError
0x18001eb55  test    eax, eax
0x18001eb57  jle     short loc_18001EB63
0x18001eb59  movzx   eax, ax
0x18001eb5c  or      eax, 80070000h
0x18001eb61  test    eax, eax
0x18001eb63  jns     short loc_18001EB76
0x18001eb65  mov     ecx, eax; int
0x18001eb67  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18001eb6c  mov     ecx, eax; dwErrCode
0x18001eb6e  call    cs:__imp_SetLastError
0x18001eb74  xor     ebx, ebx
0x18001eb76  call    ?InitializeDateTime@@YAXXZ; InitializeDateTime(void)
0x18001eb7b  call    ?UlInitializeParsing@@YAJXZ; UlInitializeParsing(void)
0x18001eb80  call    ?InitializeNormalizeUrl@@YAJXZ; InitializeNormalizeUrl(void)
0x18001eb85  lea     rcx, CriticalSection; lpCriticalSection
0x18001eb8c  call    cs:__imp_LeaveCriticalSection
0x18001eb92  mov     eax, ebx
0x18001eb94  add     rsp, 40h
0x18001eb98  pop     rbx
0x18001eb99  retn
```
