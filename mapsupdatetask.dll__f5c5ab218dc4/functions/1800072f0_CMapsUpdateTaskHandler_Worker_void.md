# CMapsUpdateTaskHandler::Worker(void)

- ea: `0x1800072f0`
- end: `0x180007559`
- name: `?Worker@CMapsUpdateTaskHandler@@EEAAJXZ`
- size: `617`
- prototype: `__int64 __fastcall(CMapsUpdateTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001be0`
- `0x180002612`
- `0x1800065c4`
- `0x1800072f0`
- `0x1800075e4`
- `0x180007c04`
- `0x180007ca0`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800074b7`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180007501`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800074b7`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180007501`
- `ZTrace_Maps!ZTraceClose` at `0x180007512`
- `ZTrace_Maps!ZTraceClose` at `0x180007512`
- `ZTrace_Maps!ZTraceInit` at `0x18000732d`
- `ZTrace_Maps!ZTraceInit` at `0x18000732d`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800073f1`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800073f1`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000740d`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000740d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000742f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000742f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007469`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000736f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000743d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000744c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000748a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000736f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000743d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000744c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000748a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007333`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007333`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18000733f`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18000733f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180007365`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800074cc`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180007365`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800074cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007458`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000750c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007458`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000750c`

## string_xrefs

- `0x180007326`: `*** starting ztrace:onecoreuap\windows\maps\moshost\updatetaskcomhandler\mapsupdatetask.cpp***`
- `0x180007404`: `CMapsUpdateTaskHandler::Worker`
- `0x1800074a8`: `CMapsUpdateTaskHandler::Worker`
- `0x1800074f8`: `CMapsUpdateTaskHandler::Worker`

## pseudocode

```c
__int64 __fastcall CMapsUpdateTaskHandler::Worker(CMapsUpdateTaskHandler *this)
{
  HANDLE CurrentThread; // r14
  int ThreadPriority; // eax
  char v4; // r12
  signed int LastError; // eax
  int v6; // r8d
  unsigned int v7; // edi
  __int64 v8; // rcx
  int VolatileRegistryLocation; // eax
  const unsigned __int16 *v10; // rdx
  unsigned int v11; // r8d
  int v12; // r8d
  int v13; // eax
  int v14; // r8d
  unsigned int v15; // eax
  HANDLE Event; // rbp
  void *v17; // rsi
  DWORD v18; // r15d
  unsigned int v19; // r8d
  const char *v20; // r9
  signed int v21; // eax
  unsigned int v23[4]; // [rsp+20h] [rbp-258h] BYREF
  WCHAR SubKey[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v23[0] = 0;
  ZTraceInit("*** starting ztrace:onecoreuap\\windows\\maps\\moshost\\updatetaskcomhandler\\mapsupdatetask.cpp***");
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  if ( ThreadPriority == 0x7FFFFFFF )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v6 = 204;
    goto LABEL_38;
  }
  v4 = 0;
  if ( ThreadPriority != -2 )
  {
    if ( !SetThreadPriority(CurrentThread, 0x10000) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        LastError = -2143748092;
      }
      v6 = 208;
LABEL_38:
      v7 = ZTraceReportOrigination(LastError, "CMapsUpdateTaskHandler::Worker", v6, this);
      goto LABEL_39;
    }
    v4 = 1;
  }
  v7 = 0;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 9, 1, 1) != 1 )
  {
    memset_0(SubKey, 0, 0x208u);
    VolatileRegistryLocation = RegUtils::GetVolatileRegistryLocation(v8, SubKey);
    if ( VolatileRegistryLocation >= 0 )
    {
      VolatileRegistryLocation = RegUtils::GetRegDword(SubKey, v10, v11, v23);
      if ( VolatileRegistryLocation >= 0 )
        goto LABEL_18;
      v12 = 830;
    }
    else
    {
      v12 = 824;
    }
    v13 = ZTraceReportPropagationNoThis(VolatileRegistryLocation, "RegUtils::GetMapsVolatileRegDword", v12);
    if ( v13 < 0 )
    {
      v14 = 219;
      goto LABEL_17;
    }
LABEL_18:
    if ( v23[0] )
      goto LABEL_31;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    if ( !Event )
    {
      v21 = GetLastError();
      if ( v21 )
      {
        if ( v21 > 0 )
          v21 = (unsigned __int16)v21 | 0x80070000;
      }
      else
      {
        v21 = -2143748092;
      }
      v15 = ZTraceReportOrigination(v21, "CMapsUpdateTaskHandler::Worker", 223, this);
      goto LABEL_30;
    }
    GetLastError();
    v17 = (void *)*((_QWORD *)this + 12);
    if ( v17 )
    {
      v18 = GetLastError();
      if ( !CloseHandle(v17) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v19, v20);
      SetLastError(v18);
    }
    *((_QWORD *)this + 12) = Event;
    v13 = CMapsUpdateTaskHandler::StartAutoCheckForUpdate(this);
    if ( v13 >= 0 )
      goto LABEL_31;
    v14 = 224;
LABEL_17:
    v15 = ZTraceReportPropagation(v13, "CMapsUpdateTaskHandler::Worker", v14, this);
LABEL_30:
    v7 = v15;
  }
LABEL_31:
  if ( v4 )
    SetThreadPriority(CurrentThread, 0x20000);
LABEL_39:
  CloseHandle(CurrentThread);
  ZTraceClose();
  return v7;
}

```

## disassembly

```asm
0x1800072f0  mov     [rsp+arg_8], rbx
0x1800072f5  mov     [rsp+arg_10], rbp
0x1800072fa  push    rsi
0x1800072fb  push    rdi
0x1800072fc  push    r12
0x1800072fe  push    r14
0x180007300  push    r15
0x180007302  sub     rsp, 250h
0x180007309  mov     rax, cs:__security_cookie
0x180007310  xor     rax, rsp
0x180007313  mov     [rsp+278h+var_38], rax
0x18000731b  mov     rbx, rcx
0x18000731e  mov     [rsp+278h+var_258], 0
0x180007326  lea     rcx, aStartingZtrace; "*** starting ztrace:onecoreuap\\windows"...
0x18000732d  call    cs:__imp_?ZTraceInit@@YAXPEBD@Z; ZTraceInit(char const *)
0x180007333  call    cs:__imp_GetCurrentThread
0x180007339  mov     rcx, rax; hThread
0x18000733c  mov     r14, rax
0x18000733f  call    cs:__imp_GetThreadPriority
0x180007345  cmp     eax, 7FFFFFFFh
0x18000734a  jz      loc_1800074D4
0x180007350  xor     r12b, r12b
0x180007353  mov     esi, 1
0x180007358  cmp     eax, 0FFFFFFFEh
0x18000735b  jz      short loc_180007398
0x18000735d  mov     edx, 10000h; nPriority
0x180007362  mov     rcx, r14; hThread
0x180007365  call    cs:__imp_SetThreadPriority
0x18000736b  test    eax, eax
0x18000736d  jnz     short loc_180007395
0x18000736f  call    cs:__imp_GetLastError
0x180007375  test    eax, eax
0x180007377  jz      short loc_180007385
0x180007379  jle     short loc_18000738A
0x18000737b  movzx   eax, ax
0x18000737e  or      eax, 80070000h
0x180007383  jmp     short loc_18000738A
0x180007385  mov     eax, 80390004h
0x18000738a  mov     r8d, 0D0h
0x180007390  jmp     loc_1800074F5
0x180007395  mov     r12b, sil
0x180007398  xor     edi, edi
0x18000739a  mov     eax, esi
0x18000739c  lock cmpxchg [rbx+24h], esi
0x1800073a1  jz      loc_1800074BF
0x1800073a7  xor     edx, edx; Val
0x1800073a9  lea     rcx, [rsp+278h+SubKey]; void *
0x1800073ae  mov     r8d, 208h; Size
0x1800073b4  call    memset_0
0x1800073b9  lea     rdx, [rsp+278h+SubKey]
0x1800073be  call    ?GetVolatileRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetVolatileRegistryLocation(MapsRegKeys,ushort *,ulong)
0x1800073c3  test    eax, eax
0x1800073c5  jns     short loc_1800073CF
0x1800073c7  mov     r8d, 338h
0x1800073cd  jmp     short loc_1800073E8
0x1800073cf  lea     r9, [rsp+278h+var_258]; unsigned int *
0x1800073d4  lea     rcx, [rsp+278h+SubKey]; lpSubKey
0x1800073d9  call    ?GetRegDword@RegUtils@@SAJPEBG0KPEAK@Z; RegUtils::GetRegDword(ushort const *,ushort const *,ulong,ulong *)
0x1800073de  test    eax, eax
0x1800073e0  jns     short loc_180007418
0x1800073e2  mov     r8d, 33Eh
0x1800073e8  lea     rdx, aRegutilsGetmap; "RegUtils::GetMapsVolatileRegDword"
0x1800073ef  mov     ecx, eax
0x1800073f1  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800073f7  test    eax, eax
0x1800073f9  jns     short loc_180007418
0x1800073fb  mov     r8d, 0DBh
0x180007401  mov     r9, rbx
0x180007404  lea     rdx, aCmapsupdatetas; "CMapsUpdateTaskHandler::Worker"
0x18000740b  mov     ecx, eax
0x18000740d  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180007413  jmp     loc_1800074BD
0x180007418  cmp     [rsp+278h+var_258], edi
0x18000741c  jnz     loc_1800074BF
0x180007422  mov     r9d, 1F0003h; dwDesiredAccess
0x180007428  xor     r8d, r8d; dwFlags
0x18000742b  xor     edx, edx; lpName
0x18000742d  xor     ecx, ecx; lpEventAttributes
0x18000742f  call    cs:__imp_CreateEventExW
0x180007435  mov     rbp, rax
0x180007438  test    rax, rax
0x18000743b  jz      short loc_18000748A
0x18000743d  call    cs:__imp_GetLastError
0x180007443  mov     rsi, [rbx+60h]
0x180007447  test    rsi, rsi
0x18000744a  jz      short loc_18000746F
0x18000744c  call    cs:__imp_GetLastError
0x180007452  mov     rcx, rsi; hObject
0x180007455  mov     r15d, eax
0x180007458  call    cs:__imp_CloseHandle
0x18000745e  test    eax, eax
0x180007460  jz      loc_180007546
0x180007466  mov     ecx, r15d; dwErrCode
0x180007469  call    cs:__imp_SetLastError
0x18000746f  mov     rcx, rbx; this
0x180007472  mov     [rbx+60h], rbp
0x180007476  call    ?StartAutoCheckForUpdate@CMapsUpdateTaskHandler@@AEAAJXZ; CMapsUpdateTaskHandler::StartAutoCheckForUpdate(void)
0x18000747b  test    eax, eax
0x18000747d  jns     short loc_1800074BF
0x18000747f  mov     r8d, 0E0h
0x180007485  jmp     loc_180007401
0x18000748a  call    cs:__imp_GetLastError
0x180007490  test    eax, eax
0x180007492  jz      short loc_1800074A0
0x180007494  jle     short loc_1800074A5
0x180007496  movzx   eax, ax
0x180007499  or      eax, 80070000h
0x18000749e  jmp     short loc_1800074A5
0x1800074a0  mov     eax, 80390004h
0x1800074a5  mov     r9, rbx
0x1800074a8  lea     rdx, aCmapsupdatetas; "CMapsUpdateTaskHandler::Worker"
0x1800074af  mov     r8d, 0DFh
0x1800074b5  mov     ecx, eax
0x1800074b7  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x1800074bd  mov     edi, eax
0x1800074bf  test    r12b, r12b
0x1800074c2  jz      short loc_180007509
0x1800074c4  mov     edx, 20000h; nPriority
0x1800074c9  mov     rcx, r14; hThread
0x1800074cc  call    cs:__imp_SetThreadPriority
0x1800074d2  jmp     short loc_180007509
0x1800074d4  call    cs:__imp_GetLastError
0x1800074da  test    eax, eax
0x1800074dc  jz      short loc_1800074EA
0x1800074de  jle     short loc_1800074EF
0x1800074e0  movzx   eax, ax
0x1800074e3  or      eax, 80070000h
0x1800074e8  jmp     short loc_1800074EF
0x1800074ea  mov     eax, 80390004h
0x1800074ef  mov     r8d, 0CCh
0x1800074f5  mov     r9, rbx
0x1800074f8  lea     rdx, aCmapsupdatetas; "CMapsUpdateTaskHandler::Worker"
0x1800074ff  mov     ecx, eax
0x180007501  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180007507  mov     edi, eax
0x180007509  mov     rcx, r14; hObject
0x18000750c  call    cs:__imp_CloseHandle
0x180007512  call    cs:__imp_?ZTraceClose@@YAXXZ; ZTraceClose(void)
0x180007518  mov     eax, edi
0x18000751a  mov     rcx, [rsp+278h+var_38]
0x180007522  xor     rcx, rsp; StackCookie
0x180007525  call    __security_check_cookie
0x18000752a  lea     r11, [rsp+278h+var_28]
0x180007532  mov     rbx, [r11+38h]
0x180007536  mov     rbp, [r11+40h]
0x18000753a  mov     rsp, r11
0x18000753d  pop     r15
0x18000753f  pop     r14
0x180007541  pop     r12
0x180007543  pop     rdi
0x180007544  pop     rsi
0x180007545  retn
0x180007546  mov     rcx, [rsp+278h]; this
0x18000754e  mov     edx, 0A0Bh; void *
0x180007553  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
