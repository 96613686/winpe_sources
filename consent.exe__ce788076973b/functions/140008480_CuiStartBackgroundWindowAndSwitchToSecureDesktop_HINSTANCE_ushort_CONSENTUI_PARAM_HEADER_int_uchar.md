# CuiStartBackgroundWindowAndSwitchToSecureDesktop(HINSTANCE__ *,ushort *,_CONSENTUI_PARAM_HEADER *,int *,uchar *)

- ea: `0x140008480`
- end: `0x14000897a`
- name: `?CuiStartBackgroundWindowAndSwitchToSecureDesktop@@YAKPEAUHINSTANCE__@@PEAGPEAU_CONSENTUI_PARAM_HEADER@@PEAHPEAE@Z`
- size: `1274`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned __int16 *, HANDLE *, int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14001a080`

## callees

- `0x140008480`
- `0x14000f8c0`
- `0x14000fbec`
- `0x140013928`
- `0x14001bb44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000852b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000852b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000855e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400085d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000855e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400085d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008666`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400085fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400085fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400084e2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400084e2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400085ac`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400085ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140008854`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140008854`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x140008617`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x140008617`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1400086e6`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1400086e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008604`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000868e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400086cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000872e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400087ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008923`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008604`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000868e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400086cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000872e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400087ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008923`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140008637`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140008637`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400084b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140008734`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000890c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400084b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140008734`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000890c`
- `WMsgAPI!WmsgSendMessage` at `0x140008875`
- `WMsgAPI!WmsgSendMessage` at `0x140008875`
- `ntdll!EtwEventWrite` at `0x14000884e`
- `ntdll!EtwEventWrite` at `0x140008906`
- `ntdll!EtwEventWrite` at `0x14000884e`
- `ntdll!EtwEventWrite` at `0x140008906`
- `ntdll!RtlNtStatusToDosError` at `0x1400088bf`
- `ntdll!RtlNtStatusToDosError` at `0x1400088bf`

## pseudocode

```c
__int64 __fastcall CuiStartBackgroundWindowAndSwitchToSecureDesktop(
        HINSTANCE a1,
        unsigned __int16 *a2,
        HANDLE *a3,
        int *a4,
        unsigned __int8 *a5)
{
  void *v5; // rsi
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  HANDLE EventW; // rax
  void *v12; // r14
  DWORD v13; // eax
  HANDLE v14; // rax
  DWORD v15; // eax
  DWORD v16; // eax
  DWORD LastError; // eax
  DWORD v18; // ebx
  __int64 v19; // r8
  unsigned int v20; // eax
  DWORD CurrentProcessId; // eax
  ULONG v22; // eax
  __int64 result; // rax
  NTSTATUS Status; // [rsp+30h] [rbp-20h] BYREF
  DWORD ThreadId; // [rsp+34h] [rbp-1Ch] BYREF
  DWORD TickCount; // [rsp+38h] [rbp-18h]
  HANDLE Handles[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD ExitCode; // [rsp+A0h] [rbp+50h] BYREF

  ExitCode = 87;
  v5 = 0;
  Status = 0;
  ThreadId = 0;
  TickCount = GetTickCount();
  Handles[0] = a3[2];
  hMutex = a3[5];
  a3[2] = 0;
  v9 = LocalAlloc(0x40u, 0x50u);
  v10 = v9;
  if ( v9 )
  {
    *v9 = a1;
    v9[1] = Handles[0];
    v9[8] = a5;
    v9[2] = a3 + 2;
    v9[6] = a2;
    v9[7] = a4;
    *((_DWORD *)v9 + 18) = *((_DWORD *)a3 + 12);
    EventW = CreateEventW(0, 1, 0, 0);
    v10[3] = EventW;
    v12 = EventW;
    if ( EventW )
    {
      v14 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CuipWindowThread, v10, 4u, &ThreadId);
      v5 = v14;
      if ( v14 )
      {
        ResumeThread(v14);
        Handles[0] = v5;
        Handles[1] = v12;
        v16 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
        ExitCode = v16;
        if ( !v16 )
        {
          GetExitCodeThread(v5, &ExitCode);
          if ( ExitCode == -1 )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 101, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids);
            }
            ExitCode = 50;
          }
          else
          {
            if ( ExitCode != 1223 )
            {
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
              {
                WPP_SF_D(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  103,
                  WPP_2ce5143529803a6454f2e220154fca2e_Traceguids,
                  ExitCode);
              }
              CloseHandle(v12);
              ExitCode = 0;
              v20 = CuipAcquireSessionMutex(0);
              ExitCode = v20;
              if ( v20 )
              {
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
                {
                  WPP_SF_D(
                    *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                    106,
                    WPP_2ce5143529803a6454f2e220154fca2e_Traceguids,
                    v20);
                  v20 = ExitCode;
                }
              }
              else
              {
                dword_140029BBC = 1;
              }
              if ( v20 )
                goto LABEL_53;
              goto LABEL_41;
            }
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 102, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids);
            }
          }
          CloseHandle(v12);
          v18 = GetTickCount();
          goto LABEL_54;
        }
        if ( v16 == 1 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 104, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids);
        }
        else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_D(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            105,
            WPP_2ce5143529803a6454f2e220154fca2e_Traceguids,
            LastError);
          CloseHandle(v12);
          ExitCode = 0;
          goto LABEL_41;
        }
      }
      else
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        {
          v15 = GetLastError();
          WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 100, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, v15);
        }
        LocalFree(v10);
      }
      CloseHandle(v12);
      ExitCode = 0;
      goto LABEL_41;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      v13 = GetLastError();
      WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 99, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, v13);
      ExitCode = 0;
      goto LABEL_41;
    }
  }
  ExitCode = 0;
LABEL_41:
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 107, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids);
  EtwEventWrite(g_ConsentPerfRegHandle, ConsentUI_SwitchDesktop_Start, 0, 0);
  CurrentProcessId = GetCurrentProcessId();
  v22 = WmsgSendMessage(NtCurrentPeb()->SessionId, 1280, CurrentProcessId, &Status);
  ExitCode = v22;
  if ( !v22 )
  {
    if ( Status >= 0 )
    {
      dword_140029BE4 = 1;
      ExitCode = 0;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 109, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids);
      goto LABEL_53;
    }
    v22 = RtlNtStatusToDosError(Status);
    ExitCode = v22;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 108, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, v22);
LABEL_53:
  EtwEventWrite(g_ConsentPerfRegHandle, ConsentUI_SwitchDesktop_Stop, 0, 0);
  v18 = GetTickCount();
  if ( !v5 )
    goto LABEL_56;
LABEL_54:
  result = ExitCode;
  if ( ExitCode )
  {
    CloseHandle(v5);
LABEL_56:
    result = ExitCode;
    if ( ExitCode )
      return result;
    goto LABEL_57;
  }
  hObject = v5;
LABEL_57:
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 110, v19, v18 - TickCount);
    return ExitCode;
  }
  return result;
}

```

## disassembly

```asm
0x140008480  mov     [rsp-38h+arg_8], rbx
0x140008485  mov     [rsp-38h+arg_0], rcx
0x14000848a  push    rbp
0x14000848b  push    rsi
0x14000848c  push    rdi
0x14000848d  push    r12
0x14000848f  push    r13
0x140008491  push    r14
0x140008493  push    r15
0x140008495  mov     rbp, rsp
0x140008498  sub     rsp, 50h
0x14000849c  xor     edi, edi
0x14000849e  mov     [rbp+ExitCode], 57h ; 'W'
0x1400084a5  mov     esi, edi
0x1400084a7  mov     [rbp+Status], edi
0x1400084aa  mov     [rbp+ThreadId], edi
0x1400084ad  mov     r12, r9
0x1400084b0  mov     r14, r8
0x1400084b3  mov     r13, rdx
0x1400084b6  call    cs:__imp_GetTickCount
0x1400084bc  mov     [rbp+var_18], eax
0x1400084bf  lea     r15, [r14+10h]
0x1400084c3  mov     rax, [r15]
0x1400084c6  mov     edx, 50h ; 'P'; uBytes
0x1400084cb  mov     [rbp+Handles], rax
0x1400084cf  mov     ecx, 40h ; '@'; uFlags
0x1400084d4  mov     rax, [r14+28h]
0x1400084d8  mov     cs:hMutex, rax
0x1400084df  mov     [r15], rdi
0x1400084e2  call    cs:__imp_LocalAlloc
0x1400084e8  mov     rdi, rax
0x1400084eb  test    rax, rax
0x1400084ee  jz      loc_1400087F3
0x1400084f4  mov     rax, [rbp+arg_0]
0x1400084f8  xor     r9d, r9d; lpName
0x1400084fb  mov     [rdi], rax
0x1400084fe  xor     r8d, r8d; bInitialState
0x140008501  mov     rax, [rbp+Handles]
0x140008505  mov     edx, 1; bManualReset
0x14000850a  mov     [rdi+8], rax
0x14000850e  xor     ecx, ecx; lpEventAttributes
0x140008510  mov     rax, [rbp+arg_20]
0x140008514  mov     [rdi+40h], rax
0x140008518  mov     [rdi+10h], r15
0x14000851c  mov     [rdi+30h], r13
0x140008520  mov     [rdi+38h], r12
0x140008524  mov     eax, [r14+30h]
0x140008528  mov     [rdi+48h], eax
0x14000852b  call    cs:__imp_CreateEventW
0x140008531  mov     [rdi+18h], rax
0x140008535  mov     r14, rax
0x140008538  test    rax, rax
0x14000853b  jnz     short loc_14000858D
0x14000853d  mov     rcx, cs:WPP_GLOBAL_Control
0x140008544  lea     r15, WPP_GLOBAL_Control
0x14000854b  cmp     rcx, r15
0x14000854e  jz      loc_1400087FA
0x140008554  test    byte ptr [rcx+1Ch], 4
0x140008558  jz      loc_1400087FA
0x14000855e  call    cs:__imp_GetLastError
0x140008564  mov     rcx, cs:WPP_GLOBAL_Control
0x14000856b  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x140008572  mov     edx, 63h ; 'c'
0x140008577  mov     r9d, eax
0x14000857a  mov     rcx, [rcx+10h]
0x14000857e  call    WPP_SF_D
0x140008583  xor     edi, edi
0x140008585  mov     [rbp+ExitCode], edi
0x140008588  jmp     loc_140008813
0x14000858d  lea     rax, [rbp+ThreadId]
0x140008591  mov     r9, rdi; lpParameter
0x140008594  mov     [rsp+50h+lpThreadId], rax; lpThreadId
0x140008599  lea     r8, ?CuipWindowThread@@YAKPEAX@Z; lpStartAddress
0x1400085a0  xor     edx, edx; dwStackSize
0x1400085a2  mov     [rsp+50h+dwCreationFlags], 4; dwCreationFlags
0x1400085aa  xor     ecx, ecx; lpThreadAttributes
0x1400085ac  call    cs:__imp_CreateThread
0x1400085b2  mov     rsi, rax
0x1400085b5  test    rax, rax
0x1400085b8  jnz     short loc_140008614
0x1400085ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400085c1  lea     r15, WPP_GLOBAL_Control
0x1400085c8  cmp     rcx, r15
0x1400085cb  jz      short loc_1400085F8
0x1400085cd  test    byte ptr [rcx+1Ch], 4
0x1400085d1  jz      short loc_1400085F8
0x1400085d3  call    cs:__imp_GetLastError
0x1400085d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400085e0  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x1400085e7  mov     edx, 64h ; 'd'
0x1400085ec  mov     r9d, eax
0x1400085ef  mov     rcx, [rcx+10h]
0x1400085f3  call    WPP_SF_D
0x1400085f8  mov     rcx, rdi; hMem
0x1400085fb  call    cs:__imp_LocalFree
0x140008601  mov     rcx, r14; hObject
0x140008604  call    cs:__imp_CloseHandle
0x14000860a  xor     edi, edi
0x14000860c  mov     [rbp+ExitCode], edi
0x14000860f  jmp     loc_140008813
0x140008614  mov     rcx, rsi; hThread
0x140008617  call    cs:__imp_ResumeThread
0x14000861d  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x140008623  mov     [rbp+Handles], rsi
0x140008627  xor     r8d, r8d; bWaitAll
0x14000862a  mov     [rbp+var_8], r14
0x14000862e  lea     rdx, [rbp+Handles]; lpHandles
0x140008632  mov     ecx, 2; nCount
0x140008637  call    cs:__imp_WaitForMultipleObjects
0x14000863d  mov     [rbp+ExitCode], eax
0x140008640  test    eax, eax
0x140008642  jz      loc_1400086DF
0x140008648  cmp     eax, 1
0x14000864b  jz      short loc_14000869E
0x14000864d  mov     rax, cs:WPP_GLOBAL_Control
0x140008654  lea     r15, WPP_GLOBAL_Control
0x14000865b  cmp     rax, r15
0x14000865e  jz      short loc_140008601
0x140008660  test    byte ptr [rax+1Ch], 4
0x140008664  jz      short loc_140008601
0x140008666  call    cs:__imp_GetLastError
0x14000866c  mov     rcx, cs:WPP_GLOBAL_Control
0x140008673  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x14000867a  mov     edx, 69h ; 'i'
0x14000867f  mov     r9d, eax
0x140008682  mov     rcx, [rcx+10h]
0x140008686  call    WPP_SF_D
0x14000868b  mov     rcx, r14; hObject
0x14000868e  call    cs:__imp_CloseHandle
0x140008694  xor     edi, edi
0x140008696  mov     [rbp+ExitCode], edi
0x140008699  jmp     loc_140008813
0x14000869e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400086a5  lea     r15, WPP_GLOBAL_Control
0x1400086ac  cmp     rcx, r15
0x1400086af  jz      short loc_1400086CC
0x1400086b1  test    byte ptr [rcx+1Ch], 4
0x1400086b5  jz      short loc_1400086CC
0x1400086b7  mov     rcx, [rcx+10h]
0x1400086bb  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x1400086c2  mov     edx, 68h ; 'h'
0x1400086c7  call    WPP_SF_
0x1400086cc  mov     rcx, r14; hObject
0x1400086cf  call    cs:__imp_CloseHandle
0x1400086d5  xor     edi, edi
0x1400086d7  mov     [rbp+ExitCode], edi
0x1400086da  jmp     loc_140008813
0x1400086df  lea     rdx, [rbp+ExitCode]; lpExitCode
0x1400086e3  mov     rcx, rsi; hThread
0x1400086e6  call    cs:__imp_GetExitCodeThread
0x1400086ec  mov     r9d, [rbp+ExitCode]
0x1400086f0  cmp     r9d, 0FFFFFFFFh
0x1400086f4  jnz     short loc_140008741
0x1400086f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400086fd  lea     r15, WPP_GLOBAL_Control
0x140008704  cmp     rcx, r15
0x140008707  jz      short loc_140008724
0x140008709  test    byte ptr [rcx+1Ch], 4
0x14000870d  jz      short loc_140008724
0x14000870f  mov     rcx, [rcx+10h]
0x140008713  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x14000871a  mov     edx, 65h ; 'e'
0x14000871f  call    WPP_SF_
0x140008724  mov     [rbp+ExitCode], 32h ; '2'
0x14000872b  mov     rcx, r14; hObject
0x14000872e  call    cs:__imp_CloseHandle
0x140008734  call    cs:__imp_GetTickCount
0x14000873a  mov     ebx, eax
0x14000873c  jmp     loc_140008919
0x140008741  cmp     r9d, 4C7h
0x140008748  jnz     short loc_14000877A
0x14000874a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008751  lea     r15, WPP_GLOBAL_Control
0x140008758  cmp     rcx, r15
0x14000875b  jz      short loc_14000872B
0x14000875d  test    byte ptr [rcx+1Ch], 4
0x140008761  jz      short loc_14000872B
0x140008763  mov     rcx, [rcx+10h]
0x140008767  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x14000876e  mov     edx, 66h ; 'f'
0x140008773  call    WPP_SF_
0x140008778  jmp     short loc_14000872B
0x14000877a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008781  lea     r15, WPP_GLOBAL_Control
0x140008788  cmp     rcx, r15
0x14000878b  jz      short loc_1400087A8
0x14000878d  test    byte ptr [rcx+1Ch], 4
0x140008791  jz      short loc_1400087A8
0x140008793  mov     rcx, [rcx+10h]
0x140008797  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x14000879e  mov     edx, 67h ; 'g'
0x1400087a3  call    WPP_SF_D
0x1400087a8  mov     rcx, r14; hObject
0x1400087ab  call    cs:__imp_CloseHandle
0x1400087b1  xor     edi, edi
0x1400087b3  xor     ecx, ecx; int *
0x1400087b5  mov     [rbp+ExitCode], edi
0x1400087b8  call    ?CuipAcquireSessionMutex@@YAKPEAH@Z; CuipAcquireSessionMutex(int *)
0x1400087bd  mov     [rbp+ExitCode], eax
0x1400087c0  test    eax, eax
0x1400087c2  jz      short loc_140008801
0x1400087c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400087cb  cmp     rcx, r15
0x1400087ce  jz      short loc_14000880B
0x1400087d0  test    byte ptr [rcx+1Ch], 4
0x1400087d4  jz      short loc_14000880B
0x1400087d6  mov     rcx, [rcx+10h]
0x1400087da  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x1400087e1  mov     edx, 6Ah ; 'j'
0x1400087e6  mov     r9d, eax
0x1400087e9  call    WPP_SF_D
0x1400087ee  mov     eax, [rbp+ExitCode]
0x1400087f1  jmp     short loc_14000880B
0x1400087f3  lea     r15, WPP_GLOBAL_Control
0x1400087fa  xor     edi, edi
0x1400087fc  mov     [rbp+ExitCode], edi
0x1400087ff  jmp     short loc_140008813
0x140008801  mov     cs:dword_140029BBC, 1
0x14000880b  test    eax, eax
0x14000880d  jnz     loc_1400088F2
0x140008813  mov     rcx, cs:WPP_GLOBAL_Control
0x14000881a  cmp     rcx, r15
0x14000881d  jz      short loc_14000883A
0x14000881f  test    byte ptr [rcx+1Ch], 4
0x140008823  jz      short loc_14000883A
0x140008825  mov     rcx, [rcx+10h]
0x140008829  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x140008830  mov     edx, 6Bh ; 'k'
0x140008835  call    WPP_SF_
0x14000883a  mov     rcx, cs:?g_ConsentPerfRegHandle@@3_KA; unsigned __int64 g_ConsentPerfRegHandle
0x140008841  lea     rdx, ConsentUI_SwitchDesktop_Start
0x140008848  xor     r9d, r9d
0x14000884b  xor     r8d, r8d
0x14000884e  call    cs:__imp_EtwEventWrite
0x140008854  call    cs:__imp_GetCurrentProcessId
0x14000885a  mov     rcx, gs:60h
0x140008863  lea     r9, [rbp+Status]
0x140008867  mov     r8d, eax
0x14000886a  mov     edx, 500h
0x14000886f  mov     ecx, [rcx+2C0h]
0x140008875  call    cs:__imp_WmsgSendMessage
0x14000887b  mov     [rbp+ExitCode], eax
0x14000887e  test    eax, eax
0x140008880  jnz     short loc_1400088C8
0x140008882  mov     ecx, [rbp+Status]; Status
0x140008885  test    ecx, ecx
0x140008887  js      short loc_1400088BF
0x140008889  mov     cs:dword_140029BE4, 1
0x140008893  mov     [rbp+ExitCode], edi
0x140008896  mov     rcx, cs:WPP_GLOBAL_Control
0x14000889d  cmp     rcx, r15
0x1400088a0  jz      short loc_1400088F2
0x1400088a2  test    byte ptr [rcx+1Ch], 4
0x1400088a6  jz      short loc_1400088F2
0x1400088a8  mov     rcx, [rcx+10h]
0x1400088ac  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x1400088b3  mov     edx, 6Dh ; 'm'
0x1400088b8  call    WPP_SF_
0x1400088bd  jmp     short loc_1400088F2
0x1400088bf  call    cs:__imp_RtlNtStatusToDosError
0x1400088c5  mov     [rbp+ExitCode], eax
0x1400088c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400088cf  cmp     rcx, r15
0x1400088d2  jz      short loc_1400088F2
0x1400088d4  test    byte ptr [rcx+1Ch], 4
0x1400088d8  jz      short loc_1400088F2
0x1400088da  mov     rcx, [rcx+10h]
0x1400088de  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x1400088e5  mov     edx, 6Ch ; 'l'
0x1400088ea  mov     r9d, eax
0x1400088ed  call    WPP_SF_D
0x1400088f2  mov     rcx, cs:?g_ConsentPerfRegHandle@@3_KA; unsigned __int64 g_ConsentPerfRegHandle
0x1400088f9  lea     rdx, ConsentUI_SwitchDesktop_Stop
0x140008900  xor     r9d, r9d
0x140008903  xor     r8d, r8d
0x140008906  call    cs:__imp_EtwEventWrite
0x14000890c  call    cs:__imp_GetTickCount
0x140008912  mov     ebx, eax
0x140008914  test    rsi, rsi
0x140008917  jz      short loc_140008929
0x140008919  mov     eax, [rbp+ExitCode]
0x14000891c  test    eax, eax
0x14000891e  jz      short loc_140008971
0x140008920  mov     rcx, rsi; hObject
0x140008923  call    cs:__imp_CloseHandle
0x140008929  mov     eax, [rbp+ExitCode]
0x14000892c  test    eax, eax
0x14000892e  jnz     short loc_140008959
0x140008930  mov     rcx, cs:WPP_GLOBAL_Control
0x140008937  cmp     rcx, r15
0x14000893a  jz      short loc_140008959
0x14000893c  test    byte ptr [rcx+1Ch], 4
0x140008940  jz      short loc_140008959
0x140008942  sub     ebx, [rbp+var_18]
0x140008945  mov     edx, 6Eh ; 'n'
0x14000894a  mov     rcx, [rcx+10h]
0x14000894e  mov     r9d, ebx
0x140008951  call    WPP_SF_l
0x140008956  mov     eax, [rbp+ExitCode]
0x140008959  mov     rbx, [rsp+50h+arg_8]
  ... truncated ...
```
