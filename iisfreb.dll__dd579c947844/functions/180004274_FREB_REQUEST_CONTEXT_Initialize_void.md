# FREB_REQUEST_CONTEXT::Initialize(void)

- ea: `0x180004274`
- end: `0x180004438`
- name: `?Initialize@FREB_REQUEST_CONTEXT@@SAJXZ`
- size: `452`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003130`

## callees

- `0x180001008`
- `0x180004274`
- `0x1800054e8`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800043d7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800043d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800042ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800042ea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004379`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043e1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180004345`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180004345`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x1800042a5`
- `iisutil!??0LANG_STRING@@QEAA@XZ` at `0x18000439d`
- `iisutil!??0LANG_STRING@@QEAA@XZ` at `0x18000439d`
- `iisutil!?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z` at `0x1800043bf`
- `iisutil!?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z` at `0x1800043bf`

## string_xrefs

- `0x180004370`: `iisres.dll`

## pseudocode

```c
__int64 FREB_REQUEST_CONTEXT::Initialize(void)
{
  char *v0; // rax
  char *v1; // rbx
  char *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rcx
  __int64 v5; // rdx
  char *v6; // rax
  DWORD TickCount; // eax
  signed int LastError; // eax
  signed int v9; // ebx
  LANG_STRING *v10; // rax
  LANG_STRING *v11; // rax
  signed int v12; // eax

  v0 = (char *)operator new(0x1C30u);
  v1 = v0;
  if ( !v0 )
  {
    FREB_REQUEST_CONTEXT::sm_pTimeoutMonitor = 0;
    goto LABEL_22;
  }
  v2 = v0 + 4800;
  v3 = 300;
  do
  {
    ((void (__fastcall *)(char *))CReaderWriterLock3::CReaderWriterLock3)(v2);
    v2 += 8;
    --v3;
  }
  while ( v3 );
  v4 = 0;
  *((_DWORD *)v1 + 1801) = 0;
  v5 = 0;
  *((_QWORD *)v1 + 901) = 0;
  do
  {
    v6 = &v1[v5];
    ++v4;
    *((_QWORD *)v6 + 1) = v6;
    v5 += 16;
    *(_QWORD *)v6 = v6;
  }
  while ( v4 != 300 );
  TickCount = GetTickCount();
  FREB_REQUEST_CONTEXT::sm_pTimeoutMonitor = (FREB_TIMEOUT_MONITOR_LIST *)v1;
  *((_DWORD *)v1 + 1800) = TickCount / 0x3E8 % 0x12C;
  if ( !CreateTimerQueueTimer(
          (PHANDLE)v1 + 901,
          0,
          FREB_TIMEOUT_MONITOR_LIST::DoExpirationCheck,
          v1,
          0x3E8u,
          0x3E8u,
          0x10u) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_23;
  }
  FREB_REQUEST_CONTEXT::sm_hResourceDll = LoadLibraryExW(L"iisres.dll", 0, 0);
  if ( !FREB_REQUEST_CONTEXT::sm_hResourceDll )
    goto LABEL_15;
  v10 = (LANG_STRING *)operator new(0x58u);
  if ( !v10 )
  {
    FREB_REQUEST_CONTEXT::sm_pLangString = 0;
    goto LABEL_22;
  }
  v11 = LANG_STRING::LANG_STRING(v10);
  FREB_REQUEST_CONTEXT::sm_pLangString = v11;
  if ( !v11 )
  {
LABEL_22:
    v9 = -2147024888;
    goto LABEL_23;
  }
  v9 = LANG_STRING::Initialize(v11, FREB_REQUEST_CONTEXT::sm_hResourceDll, 5u);
  if ( v9 < 0 )
  {
LABEL_23:
    FREB_REQUEST_CONTEXT::Terminate();
    return (unsigned int)v9;
  }
  if ( InitializeCriticalSectionAndSpinCount(&FREB_REQUEST_CONTEXT::sm_csCustomActionSerializer, 0x64u) )
  {
    FREB_REQUEST_CONTEXT::sm_fCustomActionLockInited = 1;
    return (unsigned int)v9;
  }
LABEL_15:
  v12 = GetLastError();
  v9 = v12;
  if ( v12 > 0 )
    v9 = (unsigned __int16)v12 | 0x80070000;
  if ( v9 < 0 )
    goto LABEL_23;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180004274  mov     [rsp+arg_0], rbx
0x180004279  mov     [rsp+arg_8], rsi
0x18000427e  push    rdi
0x18000427f  sub     rsp, 40h
0x180004283  mov     ecx, 1C30h; Size
0x180004288  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000428d  mov     rbx, rax
0x180004290  test    rax, rax
0x180004293  jz      loc_180004411
0x180004299  lea     rdi, [rax+12C0h]
0x1800042a0  mov     esi, 12Ch
0x1800042a5  mov     rax, cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x1800042ac  mov     rcx, rdi
0x1800042af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042b4  add     rdi, 8
0x1800042b8  sub     rsi, 1
0x1800042bc  jnz     short loc_1800042A5
0x1800042be  xor     ecx, ecx
0x1800042c0  mov     [rbx+1C24h], esi
0x1800042c6  xor     edx, edx
0x1800042c8  mov     [rbx+1C28h], rsi
0x1800042cf  lea     rax, [rdx+rbx]
0x1800042d3  inc     rcx
0x1800042d6  mov     [rax+8], rax
0x1800042da  lea     rdx, [rdx+10h]
0x1800042de  mov     [rax], rax
0x1800042e1  cmp     rcx, 12Ch
0x1800042e8  jnz     short loc_1800042CF
0x1800042ea  call    cs:__imp_GetTickCount
0x1800042f0  mov     [rsp+48h+Flags], 10h; Flags
0x1800042f8  lea     r8, ?DoExpirationCheck@FREB_TIMEOUT_MONITOR_LIST@@SAXPEAXE@Z; Callback
0x1800042ff  mov     ecx, eax
0x180004301  mov     cs:?sm_pTimeoutMonitor@FREB_REQUEST_CONTEXT@@0PEAVFREB_TIMEOUT_MONITOR_LIST@@EA, rbx; FREB_TIMEOUT_MONITOR_LIST * FREB_REQUEST_CONTEXT::sm_pTimeoutMonitor
0x180004308  mov     eax, 10624DD3h
0x18000430d  mov     r9, rbx; Parameter
0x180004310  mul     ecx
0x180004312  mov     eax, 1B4E81B5h
0x180004317  mov     ecx, edx
0x180004319  shr     ecx, 6
0x18000431c  mul     ecx
0x18000431e  shr     edx, 5
0x180004321  imul    eax, edx, 12Ch
0x180004327  xor     edx, edx; TimerQueue
0x180004329  sub     ecx, eax
0x18000432b  mov     eax, 3E8h
0x180004330  mov     [rbx+1C20h], ecx
0x180004336  lea     rcx, [rbx+1C28h]; phNewTimer
0x18000433d  mov     [rsp+48h+Period], eax; Period
0x180004341  mov     [rsp+48h+DueTime], eax; DueTime
0x180004345  call    cs:__imp_CreateTimerQueueTimer
0x18000434b  mov     edi, 80070000h
0x180004350  test    eax, eax
0x180004352  jnz     short loc_18000436D
0x180004354  call    cs:__imp_GetLastError
0x18000435a  mov     ebx, eax
0x18000435c  test    eax, eax
0x18000435e  jle     short loc_180004365
0x180004360  movzx   ebx, ax
0x180004363  or      ebx, edi
0x180004365  test    ebx, ebx
0x180004367  js      loc_180004421
0x18000436d  xor     r8d, r8d; dwFlags
0x180004370  lea     rcx, LibFileName; "iisres.dll"
0x180004377  xor     edx, edx; hFile
0x180004379  call    cs:__imp_LoadLibraryExW
0x18000437f  mov     cs:?sm_hResourceDll@FREB_REQUEST_CONTEXT@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * FREB_REQUEST_CONTEXT::sm_hResourceDll
0x180004386  test    rax, rax
0x180004389  jz      short loc_1800043E1
0x18000438b  mov     ecx, 58h ; 'X'; Size
0x180004390  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004395  test    rax, rax
0x180004398  jz      short loc_180004404
0x18000439a  mov     rcx, rax
0x18000439d  call    cs:__imp_??0LANG_STRING@@QEAA@XZ; LANG_STRING::LANG_STRING(void)
0x1800043a3  mov     cs:?sm_pLangString@FREB_REQUEST_CONTEXT@@0PEAVLANG_STRING@@EA, rax; LANG_STRING * FREB_REQUEST_CONTEXT::sm_pLangString
0x1800043aa  test    rax, rax
0x1800043ad  jz      short loc_18000441C
0x1800043af  mov     rdx, cs:?sm_hResourceDll@FREB_REQUEST_CONTEXT@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * FREB_REQUEST_CONTEXT::sm_hResourceDll
0x1800043b6  mov     r8d, 5
0x1800043bc  mov     rcx, rax
0x1800043bf  call    cs:__imp_?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z; LANG_STRING::Initialize(HINSTANCE__ *,ulong)
0x1800043c5  mov     ebx, eax
0x1800043c7  test    eax, eax
0x1800043c9  js      short loc_180004421
0x1800043cb  mov     edx, 64h ; 'd'; dwSpinCount
0x1800043d0  lea     rcx, ?sm_csCustomActionSerializer@FREB_REQUEST_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800043d7  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800043dd  test    eax, eax
0x1800043df  jnz     short loc_1800043F8
0x1800043e1  call    cs:__imp_GetLastError
0x1800043e7  mov     ebx, eax
0x1800043e9  test    eax, eax
0x1800043eb  jle     short loc_1800043F2
0x1800043ed  movzx   ebx, ax
0x1800043f0  or      ebx, edi
0x1800043f2  test    ebx, ebx
0x1800043f4  jns     short loc_180004426
0x1800043f6  jmp     short loc_180004421
0x1800043f8  mov     cs:?sm_fCustomActionLockInited@FREB_REQUEST_CONTEXT@@0HA, 1; int FREB_REQUEST_CONTEXT::sm_fCustomActionLockInited
0x180004402  jmp     short loc_180004426
0x180004404  mov     cs:?sm_pLangString@FREB_REQUEST_CONTEXT@@0PEAVLANG_STRING@@EA, 0; LANG_STRING * FREB_REQUEST_CONTEXT::sm_pLangString
0x18000440f  jmp     short loc_18000441C
0x180004411  mov     cs:?sm_pTimeoutMonitor@FREB_REQUEST_CONTEXT@@0PEAVFREB_TIMEOUT_MONITOR_LIST@@EA, 0; FREB_TIMEOUT_MONITOR_LIST * FREB_REQUEST_CONTEXT::sm_pTimeoutMonitor
0x18000441c  mov     ebx, 80070008h
0x180004421  call    ?Terminate@FREB_REQUEST_CONTEXT@@SAXXZ; FREB_REQUEST_CONTEXT::Terminate(void)
0x180004426  mov     rsi, [rsp+48h+arg_8]
0x18000442b  mov     eax, ebx
0x18000442d  mov     rbx, [rsp+48h+arg_0]
0x180004432  add     rsp, 40h
0x180004436  pop     rdi
0x180004437  retn
```
