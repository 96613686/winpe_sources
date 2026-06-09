# ComponentOnDemandp_InstallLaunchThreadProc(void *)

- ea: `0x1800a76f0`
- end: `0x1800a798a`
- name: `?ComponentOnDemandp_InstallLaunchThreadProc@@YAKPEAX@Z`
- size: `666`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000dc08`
- `0x180012920`
- `0x18001b320`
- `0x180034434`
- `0x180052618`
- `0x18007a9cf`
- `0x1800a76f0`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800a781b`
- `msvcrt!wcsrchr` at `0x1800a781b`
- `ntdll!RtlAllocateHeap` at `0x1800a77ad`
- `ntdll!RtlAllocateHeap` at `0x1800a77ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a77fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a78aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a78fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a77fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a78aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a78fc`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800a78a0`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800a78a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a793b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a794b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a793b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a794b`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x1800a77f1`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x1800a77f1`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800a78ef`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800a78ef`

## string_xrefs

- `0x1800a77c8`: `ComponentOnDemandp_InstallLaunchThreadProc`
- `0x1800a78bd`: `ComponentOnDemandp_InstallLaunchThreadProc`
- `0x1800a7920`: `ComponentOnDemand`
- `0x1800a7911`: `Complete,Component,%S`

## pseudocode

```c
__int64 __fastcall ComponentOnDemandp_InstallLaunchThreadProc(PVOID Parameter)
{
  __int64 v2; // rax
  unsigned __int64 v3; // r15
  unsigned int v4; // ebx
  DWORD v5; // esi
  unsigned __int16 *Heap; // r14
  const char *v7; // r9
  int v8; // r8d
  DWORD LastError; // eax
  wchar_t *v10; // rax
  WCHAR *v11; // rax
  DWORD v12; // eax
  const char *v13; // r9
  int v14; // r8d
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE Handles[3]; // [rsp+78h] [rbp-88h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Filename[264]; // [rsp+100h] [rbp+0h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  *(_OWORD *)Handles = 0;
  PcaSetCurrentThreadQosLow();
  v2 = -1;
  do
    ++v2;
  while ( *((_WORD *)Parameter + v2) );
  v3 = v2 + 331;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  v4 = 8;
  Handles[0] = *((HANDLE *)Parameter + 70);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v5 = -1;
  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v3);
  if ( !Heap )
  {
    v7 = "Out of memory";
    v8 = 516;
LABEL_5:
    AslLogCallPrintf(1, (unsigned int)"ComponentOnDemandp_InstallLaunchThreadProc", v8, (_DWORD)v7);
    goto LABEL_19;
  }
  if ( !K32GetModuleFileNameExW(*((HANDLE *)Parameter + 67), 0, Filename, 0x104u) )
  {
    LastError = GetLastError();
    v7 = "Could not get caller name";
    v8 = 530;
    v4 = LastError;
    goto LABEL_5;
  }
  v10 = wcsrchr(Filename, 0x5Cu);
  if ( v10 )
    v11 = v10 + 1;
  else
    v11 = Filename;
  if ( StringCchPrintfW(
         Heap,
         v3,
         L"Fondue.exe /enable-feature:%s /show-caller /top-most /caller-name:\"%s\"",
         Parameter,
         v11) < 0 )
  {
    v4 = 111;
    v7 = "Request file name too long";
    v8 = 552;
    goto LABEL_5;
  }
  if ( !CreateProcessAsUserW(*((HANDLE *)Parameter + 69), 0, Heap, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    v12 = GetLastError();
    v13 = "Could not launch process %d";
    v14 = 572;
LABEL_15:
    v4 = v12;
    AslLogCallPrintf(1, (unsigned int)"ComponentOnDemandp_InstallLaunchThreadProc", v14, (_DWORD)v13);
    goto LABEL_19;
  }
  Handles[1] = ProcessInformation.hProcess;
  v5 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
  if ( v5 == -1 )
  {
    v12 = GetLastError();
    v13 = "Wait failed [%d]";
    v14 = 588;
    goto LABEL_15;
  }
  PcaTracePrintf("ComponentOnDemand", 0, 0, "Complete,Component,%S", (const wchar_t *)Parameter);
  v4 = 0;
LABEL_19:
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  if ( v5 )
    ComponentOnDemandp_ResumePendingProcesses((unsigned __int16 *)Parameter);
  return v4;
}

```

## disassembly

```asm
0x1800a76f0  mov     [rsp-8+arg_8], rbx
0x1800a76f5  mov     [rsp-8+arg_10], rsi
0x1800a76fa  push    rbp
0x1800a76fb  push    rdi
0x1800a76fc  push    r12
0x1800a76fe  push    r14
0x1800a7700  push    r15
0x1800a7702  lea     rbp, [rsp-220h]
0x1800a770a  sub     rsp, 320h
0x1800a7711  mov     rax, cs:__security_cookie
0x1800a7718  xor     rax, rsp
0x1800a771b  mov     [rbp+240h+var_30], rax
0x1800a7722  mov     rdi, rcx
0x1800a7725  mov     ebx, 68h ; 'h'
0x1800a772a  mov     r8d, ebx; Size
0x1800a772d  lea     rcx, [rbp+240h+StartupInfo]; void *
0x1800a7731  xor     edx, edx; Val
0x1800a7733  call    memset_0
0x1800a7738  xorps   xmm0, xmm0
0x1800a773b  xor     eax, eax
0x1800a773d  movups  xmmword ptr [rsp+340h+ProcessInformation.hProcess], xmm0
0x1800a7742  mov     qword ptr [rsp+340h+ProcessInformation.dwProcessId], rax
0x1800a7747  movups  xmmword ptr [rsp+340h+Handles], xmm0
0x1800a774c  call    ?PcaSetCurrentThreadQosLow@@YAXXZ; PcaSetCurrentThreadQosLow(void)
0x1800a7751  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a7755  xor     r12d, r12d
0x1800a7758  inc     rax
0x1800a775b  cmp     [rdi+rax*2], r12w
0x1800a7760  jnz     short loc_1800A7758
0x1800a7762  mov     r8, rbx; Size
0x1800a7765  lea     rcx, [rbp+240h+StartupInfo]; void *
0x1800a7769  xor     edx, edx; Val
0x1800a776b  lea     r15, [rax+14Bh]
0x1800a7772  call    memset_0
0x1800a7777  xor     eax, eax
0x1800a7779  lea     r8, [r15+r15]; Size
0x1800a777d  mov     qword ptr [rsp+340h+ProcessInformation.dwProcessId], rax
0x1800a7782  xorps   xmm0, xmm0
0x1800a7785  mov     rax, [rdi+230h]
0x1800a778c  mov     ebx, 8
0x1800a7791  mov     [rsp+340h+Handles], rax
0x1800a7796  mov     edx, ebx; Flags
0x1800a7798  movups  xmmword ptr [rsp+340h+ProcessInformation.hProcess], xmm0
0x1800a779d  mov     rcx, gs:60h
0x1800a77a6  or      esi, 0FFFFFFFFh
0x1800a77a9  mov     rcx, [rcx+30h]; HeapHandle
0x1800a77ad  call    cs:__imp_RtlAllocateHeap
0x1800a77b3  mov     r14, rax
0x1800a77b6  test    rax, rax
0x1800a77b9  jnz     short loc_1800A77DE
0x1800a77bb  lea     r9, aOutOfMemory; "Out of memory"
0x1800a77c2  mov     r8d, 204h
0x1800a77c8  lea     rdx, aComponentondem_5; "ComponentOnDemandp_InstallLaunchThreadP"...
0x1800a77cf  mov     ecx, 1
0x1800a77d4  call    AslLogCallPrintf
0x1800a77d9  jmp     loc_1800A7931
0x1800a77de  mov     rcx, [rdi+218h]; hProcess
0x1800a77e5  lea     r8, [rbp+240h+Filename]; lpFilename
0x1800a77e9  mov     r9d, 104h; nSize
0x1800a77ef  xor     edx, edx; hModule
0x1800a77f1  call    cs:__imp_K32GetModuleFileNameExW
0x1800a77f7  test    eax, eax
0x1800a77f9  jnz     short loc_1800A7812
0x1800a77fb  call    cs:__imp_GetLastError
0x1800a7801  lea     r9, aCouldNotGetCal; "Could not get caller name"
0x1800a7808  mov     r8d, 212h
0x1800a780e  mov     ebx, eax
0x1800a7810  jmp     short loc_1800A77C8
0x1800a7812  mov     edx, 5Ch ; '\'; Ch
0x1800a7817  lea     rcx, [rbp+240h+Filename]; Str
0x1800a781b  call    cs:__imp_wcsrchr
0x1800a7821  test    rax, rax
0x1800a7824  jnz     short loc_1800A782C
0x1800a7826  lea     rax, [rbp+240h+Filename]
0x1800a782a  jmp     short loc_1800A7830
0x1800a782c  add     rax, 2
0x1800a7830  mov     r9, rdi
0x1800a7833  mov     [rsp+340h+lpThreadAttributes], rax
0x1800a7838  lea     r8, aFondueExeEnabl; "Fondue.exe /enable-feature:%s /show-cal"...
0x1800a783f  mov     rdx, r15; unsigned __int64
0x1800a7842  mov     rcx, r14; unsigned __int16 *
0x1800a7845  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a784a  test    eax, eax
0x1800a784c  jns     short loc_1800A7865
0x1800a784e  mov     ebx, 6Fh ; 'o'
0x1800a7853  lea     r9, aRequestFileNam; "Request file name too long"
0x1800a785a  mov     r8d, 228h
0x1800a7860  jmp     loc_1800A77C8
0x1800a7865  mov     rcx, [rdi+228h]; hToken
0x1800a786c  lea     rax, [rsp+340h+ProcessInformation]
0x1800a7871  mov     [rsp+340h+lpProcessInformation], rax; lpProcessInformation
0x1800a7876  xor     r9d, r9d; lpProcessAttributes
0x1800a7879  lea     rax, [rbp+240h+StartupInfo]
0x1800a787d  mov     r8, r14; lpCommandLine
0x1800a7880  mov     [rsp+340h+lpStartupInfo], rax; lpStartupInfo
0x1800a7885  xor     edx, edx; lpApplicationName
0x1800a7887  mov     [rsp+340h+lpCurrentDirectory], r12; lpCurrentDirectory
0x1800a788c  mov     [rsp+340h+lpEnvironment], r12; lpEnvironment
0x1800a7891  mov     [rsp+340h+dwCreationFlags], r12d; dwCreationFlags
0x1800a7896  mov     [rsp+340h+bInheritHandles], r12d; bInheritHandles
0x1800a789b  mov     [rsp+340h+lpThreadAttributes], r12; lpThreadAttributes
0x1800a78a0  call    cs:__imp_CreateProcessAsUserW
0x1800a78a6  test    eax, eax
0x1800a78a8  jnz     short loc_1800A78D6
0x1800a78aa  call    cs:__imp_GetLastError
0x1800a78b0  lea     r9, aCouldNotLaunch; "Could not launch process %d"
0x1800a78b7  mov     r8d, 23Ch
0x1800a78bd  lea     rdx, aComponentondem_5; "ComponentOnDemandp_InstallLaunchThreadP"...
0x1800a78c4  mov     dword ptr [rsp+340h+lpThreadAttributes], eax
0x1800a78c8  mov     ecx, 1
0x1800a78cd  mov     ebx, eax
0x1800a78cf  call    AslLogCallPrintf
0x1800a78d4  jmp     short loc_1800A7931
0x1800a78d6  mov     rax, [rsp+340h+ProcessInformation.hProcess]
0x1800a78db  lea     rdx, [rsp+340h+Handles]; lpHandles
0x1800a78e0  xor     r8d, r8d; bWaitAll
0x1800a78e3  mov     [rbp+240h+Handles+8], rax
0x1800a78e7  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800a78eb  lea     ecx, [r8+2]; nCount
0x1800a78ef  call    cs:__imp_WaitForMultipleObjects
0x1800a78f5  mov     esi, eax
0x1800a78f7  cmp     eax, 0FFFFFFFFh
0x1800a78fa  jnz     short loc_1800A7911
0x1800a78fc  call    cs:__imp_GetLastError
0x1800a7902  lea     r9, aWaitFailedD; "Wait failed [%d]"
0x1800a7909  mov     r8d, 24Ch
0x1800a790f  jmp     short loc_1800A78BD
0x1800a7911  lea     r9, aCompleteCompon; "Complete,Component,%S"
0x1800a7918  mov     [rsp+340h+lpThreadAttributes], rdi
0x1800a791d  xor     r8d, r8d; unsigned int
0x1800a7920  lea     rcx, aComponentondem_1; "ComponentOnDemand"
0x1800a7927  xor     edx, edx; unsigned int
0x1800a7929  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800a792e  mov     ebx, r12d
0x1800a7931  mov     rcx, [rsp+340h+ProcessInformation.hProcess]; hObject
0x1800a7936  test    rcx, rcx
0x1800a7939  jz      short loc_1800A7941
0x1800a793b  call    cs:__imp_CloseHandle
0x1800a7941  mov     rcx, [rsp+340h+ProcessInformation.hThread]; hObject
0x1800a7946  test    rcx, rcx
0x1800a7949  jz      short loc_1800A7951
0x1800a794b  call    cs:__imp_CloseHandle
0x1800a7951  test    esi, esi
0x1800a7953  jz      short loc_1800A795D
0x1800a7955  mov     rcx, rdi; unsigned __int16 *
0x1800a7958  call    ?ComponentOnDemandp_ResumePendingProcesses@@YAXPEAG@Z; ComponentOnDemandp_ResumePendingProcesses(ushort *)
0x1800a795d  mov     eax, ebx
0x1800a795f  mov     rcx, [rbp+240h+var_30]
0x1800a7966  xor     rcx, rsp; StackCookie
0x1800a7969  call    __security_check_cookie
0x1800a796e  lea     r11, [rsp+340h+var_20]
0x1800a7976  mov     rbx, [r11+38h]
0x1800a797a  mov     rsi, [r11+40h]
0x1800a797e  mov     rsp, r11
0x1800a7981  pop     r15
0x1800a7983  pop     r14
0x1800a7985  pop     r12
0x1800a7987  pop     rdi
0x1800a7988  pop     rbp
0x1800a7989  retn
```
