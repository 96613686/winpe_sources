# ToBeRunJobThreadProc(void *)

- ea: `0x180005460`
- end: `0x1800056f8`
- name: `?ToBeRunJobThreadProc@@YAKPEAX@Z`
- size: `664`
- prototype: `void __fastcall __noreturn(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180001868`
- `0x180001ca0`
- `0x180003c90`
- `0x1800041bc`
- `0x180005460`
- `0x180005700`
- `0x180006aa0`
- `0x18000d134`
- `0x18000fdac`
- `0x1800110b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800054d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005581`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800055e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800054d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005581`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800055e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005477`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800055a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005616`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005477`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800055a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005616`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005593`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005593`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180005654`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180005654`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054bd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800054e5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800054e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800054fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800054fa`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180005509`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180005537`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000554a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180005509`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180005537`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000554a`

## pseudocode

```c
void __fastcall __noreturn ToBeRunJobThreadProc(PVOID Parameter)
{
  HMODULE v1; // rsi
  FILETIME *v2; // rbx
  DWORD v3; // ebx
  _QWORD *v4; // rax
  int v5; // edi
  bool v6; // zf
  DWORD dwLowDateTime; // eax
  DWORD dwHighDateTime; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp+10h] BYREF
  FILETIME FileTime2; // [rsp+60h] [rbp+18h] BYREF

  EnterCriticalSection(&JobsCriticalSection);
  v1 = hToBeRunJobModule;
  hToBeRunJobModule = 0;
  while ( 1 )
  {
    SystemTimeAsFileTime = 0;
    while ( 1 )
    {
      v2 = (FILETIME *)pToBeRunJobHead;
      if ( !pToBeRunJobHead )
      {
        if ( hToBeRunJobEvent )
        {
          CloseHandle(hToBeRunJobEvent);
          hToBeRunJobEvent = 0;
        }
        LeaveCriticalSection(&JobsCriticalSection);
LABEL_7:
        if ( v1 )
          FreeLibraryAndExitThread(v1, 0);
        ExitThread(0);
      }
      if ( !*((_DWORD *)pToBeRunJobHead + 4) && !*((_DWORD *)pToBeRunJobHead + 5) )
      {
        SystemTimeAsFileTime = 0;
        goto LABEL_18;
      }
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( CompareFileTime(&SystemTimeAsFileTime, v2 + 2) < 0 )
      {
        FileTime2 = (FILETIME)(*(_QWORD *)&SystemTimeAsFileTime + 10000000LL * (unsigned int)dword_1800202A8);
        if ( CompareFileTime(v2 + 2, &FileTime2) <= 0 )
          break;
      }
LABEL_18:
      v4 = (_QWORD *)*v2;
      v5 = 0;
      pToBeRunJobHead = v4;
      if ( v4 )
        v4[1] = 0;
      v6 = v2[3].dwLowDateTime == 5;
      *v2 = 0;
      if ( v6 )
        v5 = 1;
      LeaveCriticalSection(&JobsCriticalSection);
      dwLowDateTime = v2[3].dwLowDateTime;
      if ( dwLowDateTime == 1 )
      {
        ProcessToBeRunTriggerJob(v2);
      }
      else if ( dwLowDateTime == 2 )
      {
        ProcessToBeRunScanJob(v2);
      }
      else
      {
        switch ( dwLowDateTime )
        {
          case 3u:
            dwHighDateTime = v2[14].dwHighDateTime;
            if ( dwHighDateTime == 4 )
              goto LABEL_31;
            if ( dwHighDateTime == 5 )
            {
              AddRetrievalPreFetchJob(v2);
            }
            else
            {
              v2[15].dwLowDateTime = -2147418113;
              v2[14].dwHighDateTime = 4;
LABEL_31:
              CompletePreFetchJob((struct _CUCS_PRE_FETCH_JOB_ENTRY *)v2);
            }
            break;
          case 4u:
            ProcessToBeRunLogoffExitJob(v2);
            break;
          case 5u:
            ProcessToBeRunServiceStopJob(v2);
            break;
          case 6u:
            ProcessToBeRunDeleteDirJob(v2);
            break;
          case 7u:
            ProcessToBeRunAddHpkpJob(v2);
            break;
          case 8u:
            ProcessToBeRunUpdateHpkpJob(v2);
            break;
          default:
            break;
        }
      }
      if ( v5 )
        goto LABEL_7;
      EnterCriticalSection(&JobsCriticalSection);
    }
    if ( CompareFileTime(v2 + 2, &SystemTimeAsFileTime) <= 0
      || (v3 = 1000 * ((*(_QWORD *)&v2[2] - *(_QWORD *)&SystemTimeAsFileTime) / 0x989680uLL), v3 < 0x3E8) )
    {
      v3 = 1000;
    }
    LeaveCriticalSection(&JobsCriticalSection);
    WaitForSingleObjectEx(hToBeRunJobEvent, v3, 0);
    EnterCriticalSection(&JobsCriticalSection);
  }
}

```

## disassembly

```asm
0x180005460  mov     [rsp+arg_0], rbx
0x180005465  push    rbp
0x180005466  push    rsi
0x180005467  push    rdi
0x180005468  push    r14
0x18000546a  push    r15
0x18000546c  sub     rsp, 20h
0x180005470  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180005477  call    cs:__imp_EnterCriticalSection
0x18000547d  mov     rsi, cs:?hToBeRunJobModule@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hToBeRunJobModule
0x180005484  lea     r14, __ImageBase
0x18000548b  xor     ebp, ebp
0x18000548d  mov     r15, 0D6BF94D5E57A42BDh
0x180005497  mov     cs:?hToBeRunJobModule@@3PEAUHINSTANCE__@@EA, rbp; HINSTANCE__ * hToBeRunJobModule
0x18000549e  xchg    ax, ax
0x1800054a0  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], rbp
0x1800054a5  mov     rbx, cs:?pToBeRunJobHead@@3PEAU_CUCS_JOB_HEADER@@EA; _CUCS_JOB_HEADER * pToBeRunJobHead
0x1800054ac  test    rbx, rbx
0x1800054af  jnz     short loc_1800054EC
0x1800054b1  mov     rcx, cs:?hToBeRunJobEvent@@3PEAXEA; hObject
0x1800054b8  test    rcx, rcx
0x1800054bb  jz      short loc_1800054CA
0x1800054bd  call    cs:__imp_CloseHandle
0x1800054c3  mov     cs:?hToBeRunJobEvent@@3PEAXEA, rbp; void * hToBeRunJobEvent
0x1800054ca  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800054d1  call    cs:__imp_LeaveCriticalSection
0x1800054d7  test    rsi, rsi
0x1800054da  jz      loc_180005652
0x1800054e0  xor     edx, edx; dwExitCode
0x1800054e2  mov     rcx, rsi; hLibModule
0x1800054e5  call    cs:__imp_FreeLibraryAndExitThread
0x1800054eb  int     3; Trap to Debugger
0x1800054ec  cmp     [rbx+10h], ebp
0x1800054ef  jz      loc_1800055AB
0x1800054f5  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800054fa  call    cs:__imp_GetSystemTimeAsFileTime
0x180005500  lea     rdx, [rbx+10h]; lpFileTime2
0x180005504  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpFileTime1
0x180005509  call    cs:__imp_CompareFileTime
0x18000550f  test    eax, eax
0x180005511  jns     loc_1800055B9
0x180005517  mov     eax, cs:dword_1800202A8
0x18000551d  lea     rdx, [rsp+48h+FileTime2]; lpFileTime2
0x180005522  imul    rcx, rax, 989680h
0x180005529  add     rcx, qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime]
0x18000552e  mov     qword ptr [rsp+48h+FileTime2.dwLowDateTime], rcx
0x180005533  lea     rcx, [rbx+10h]; lpFileTime1
0x180005537  call    cs:__imp_CompareFileTime
0x18000553d  test    eax, eax
0x18000553f  jg      short loc_1800055B9
0x180005541  lea     rdx, [rsp+48h+SystemTimeAsFileTime]; lpFileTime2
0x180005546  lea     rcx, [rbx+10h]; lpFileTime1
0x18000554a  call    cs:__imp_CompareFileTime
0x180005550  test    eax, eax
0x180005552  jle     short loc_180005575
0x180005554  mov     rcx, [rbx+10h]
0x180005558  mov     rax, r15
0x18000555b  sub     rcx, qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime]
0x180005560  mul     rcx
0x180005563  shr     rdx, 17h
0x180005567  imul    ebx, edx, 3E8h
0x18000556d  cmp     ebx, 3E8h
0x180005573  jnb     short loc_18000557A
0x180005575  mov     ebx, 3E8h
0x18000557a  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180005581  call    cs:__imp_LeaveCriticalSection
0x180005587  mov     rcx, cs:?hToBeRunJobEvent@@3PEAXEA; hHandle
0x18000558e  xor     r8d, r8d; bAlertable
0x180005591  mov     edx, ebx; dwMilliseconds
0x180005593  call    cs:__imp_WaitForSingleObjectEx
0x180005599  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800055a0  call    cs:__imp_EnterCriticalSection
0x1800055a6  jmp     loc_1800054A0
0x1800055ab  cmp     [rbx+14h], ebp
0x1800055ae  jnz     loc_1800054F5
0x1800055b4  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], rbp
0x1800055b9  mov     rax, [rbx]
0x1800055bc  mov     edi, ebp
0x1800055be  mov     cs:?pToBeRunJobHead@@3PEAU_CUCS_JOB_HEADER@@EA, rax; _CUCS_JOB_HEADER * pToBeRunJobHead
0x1800055c5  test    rax, rax
0x1800055c8  jz      short loc_1800055CE
0x1800055ca  mov     [rax+8], rbp
0x1800055ce  cmp     dword ptr [rbx+18h], 5
0x1800055d2  mov     [rbx], rbp
0x1800055d5  jz      loc_18000566F
0x1800055db  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800055e2  call    cs:__imp_LeaveCriticalSection
0x1800055e8  mov     eax, [rbx+18h]
0x1800055eb  cmp     eax, 1
0x1800055ee  jz      short loc_1800055FF
0x1800055f0  cmp     eax, 2
0x1800055f3  jnz     short loc_180005621
0x1800055f5  mov     rcx, rbx; hMem
0x1800055f8  call    ProcessToBeRunScanJob
0x1800055fd  jmp     short def_180005634; jumptable 0000000180005634 default case
0x1800055ff  mov     rcx, rbx; hMem
0x180005602  call    ProcessToBeRunTriggerJob
0x180005607  test    edi, edi; jumptable 0000000180005634 default case
0x180005609  jnz     loc_1800054D7
0x18000560f  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180005616  call    cs:__imp_EnterCriticalSection
0x18000561c  jmp     loc_1800054A5
0x180005621  add     eax, 0FFFFFFFDh; switch 6 cases
0x180005624  cmp     eax, 5
0x180005627  ja      short def_180005634; jumptable 0000000180005634 default case
0x180005629  mov     eax, ds:(jpt_180005634 - 180000000h)[r14+rax*4]
0x180005631  add     rax, r14
0x180005634  jmp     rax; switch jump
0x180005636  mov     rcx, rbx; jumptable 0000000180005634 case 4
0x180005639  call    ProcessToBeRunLogoffExitJob
0x18000563e  jmp     short def_180005634; jumptable 0000000180005634 default case
0x180005640  mov     eax, [rbx+74h]; jumptable 0000000180005634 case 3
0x180005643  cmp     eax, 4
0x180005646  jnz     short loc_180005679
0x180005648  mov     rcx, rbx; struct _CUCS_PRE_FETCH_JOB_ENTRY *
0x18000564b  call    ?CompletePreFetchJob@@YAXPEAU_CUCS_PRE_FETCH_JOB_ENTRY@@@Z; CompletePreFetchJob(_CUCS_PRE_FETCH_JOB_ENTRY *)
0x180005650  jmp     short def_180005634; jumptable 0000000180005634 default case
0x180005652  xor     ecx, ecx; dwExitCode
0x180005654  call    cs:__imp_ExitThread
0x18000565b  mov     rcx, rbx; jumptable 0000000180005634 case 8
0x18000565e  call    ProcessToBeRunUpdateHpkpJob
0x180005663  jmp     short def_180005634; jumptable 0000000180005634 default case
0x180005665  mov     rcx, rbx; jumptable 0000000180005634 case 5
0x180005668  call    ProcessToBeRunServiceStopJob
0x18000566d  jmp     short def_180005634; jumptable 0000000180005634 default case
0x18000566f  mov     edi, 1
0x180005674  jmp     loc_1800055DB
0x180005679  cmp     eax, 6; switch 7 cases
0x18000567c  ja      short def_180005689; jumptable 0000000180005689 default case, cases 0-4,6
0x18000567e  mov     eax, ds:(jpt_180005689 - 180000000h)[r14+rax*4]
0x180005686  add     rax, r14
0x180005689  jmp     rax; switch jump
0x18000568b  mov     rcx, rbx; jumptable 0000000180005689 case 5
0x18000568e  call    AddRetrievalPreFetchJob
0x180005693  jmp     def_180005634; jumptable 0000000180005634 default case
0x180005698  mov     dword ptr [rbx+78h], 8000FFFFh; jumptable 0000000180005689 default case, cases 0-4,6
0x18000569f  mov     dword ptr [rbx+74h], 4
0x1800056a6  jmp     short loc_180005648
0x1800056a8  mov     rcx, rbx; jumptable 0000000180005634 case 6
0x1800056ab  call    ProcessToBeRunDeleteDirJob
0x1800056b0  jmp     def_180005634; jumptable 0000000180005634 default case
0x1800056b5  mov     rcx, rbx; jumptable 0000000180005634 case 7
0x1800056b8  call    ProcessToBeRunAddHpkpJob
0x1800056bd  jmp     def_180005634; jumptable 0000000180005634 default case
```
