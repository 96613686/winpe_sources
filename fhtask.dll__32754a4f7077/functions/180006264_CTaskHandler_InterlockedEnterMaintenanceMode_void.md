# CTaskHandler::InterlockedEnterMaintenanceMode(void)

- ea: `0x180006264`
- end: `0x1800064cd`
- name: `?InterlockedEnterMaintenanceMode@CTaskHandler@@AEAAXXZ`
- size: `617`
- prototype: `void __fastcall(CTaskHandler *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1800065d0`
- `0x180006620`

## callees

- `0x180005ea4`
- `0x180006070`
- `0x180006264`
- `0x180006728`
- `0x1800067a0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800064a5`
- `KERNEL32!LocalFree` at `0x1800064a5`
- `KERNEL32!SetThreadpoolWait` at `0x180006390`
- `KERNEL32!SetThreadpoolWait` at `0x180006390`
- `KERNEL32!CreateThreadpoolWait` at `0x18000636d`
- `KERNEL32!CreateThreadpoolWait` at `0x18000636d`
- `KERNEL32!EnterCriticalSection` at `0x180006279`
- `KERNEL32!EnterCriticalSection` at `0x180006279`
- `KERNEL32!LeaveCriticalSection` at `0x1800064b8`
- `KERNEL32!LeaveCriticalSection` at `0x1800064b8`
- `KERNEL32!GetLastError` at `0x180006318`
- `KERNEL32!GetLastError` at `0x18000641a`
- `KERNEL32!GetLastError` at `0x18000646a`
- `KERNEL32!GetLastError` at `0x180006318`
- `KERNEL32!GetLastError` at `0x18000641a`
- `KERNEL32!GetLastError` at `0x18000646a`
- `KERNEL32!OpenEventW` at `0x1800063f6`
- `KERNEL32!OpenEventW` at `0x1800063f6`
- `KERNEL32!CreateEventW` at `0x1800062f4`
- `KERNEL32!CreateEventW` at `0x1800062f4`
- `fhsvcctl!FhServiceEnterMaintenanceMode` at `0x1800063a0`
- `fhsvcctl!FhServiceEnterMaintenanceMode` at `0x1800063a0`

## pseudocode

```c
void __fastcall CTaskHandler::InterlockedEnterMaintenanceMode(CTaskHandler *this)
{
  __int64 v2; // rcx
  struct _FILETIME *p_pftTimeout; // rbp
  HANDLE EventW; // rax
  signed int LastError; // eax
  struct _TP_WAIT *ThreadpoolWait; // rax
  int v7; // eax
  HANDLE v8; // rax
  char v9; // al
  signed int v10; // eax
  LPCWSTR lpName; // [rsp+50h] [rbp+8h] BYREF
  struct _FILETIME pftTimeout; // [rsp+58h] [rbp+10h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
  lpName = 0;
  pftTimeout = 0;
  CTaskHandler::ExitMaintenanceMode(this, 0);
  v2 = *((_QWORD *)this + 9);
  if ( !v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids);
LABEL_5:
    p_pftTimeout = &pftTimeout;
    EventW = CreateEventW(0, 1, 1, 0);
    *((_QWORD *)this + 16) = EventW;
    if ( !EventW
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids,
        (unsigned int)LastError);
    }
    pftTimeout = (struct _FILETIME)-10000000LL;
    goto LABEL_12;
  }
  v7 = FhServiceEnterMaintenanceMode(v2, &lpName);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids,
        (unsigned int)v7);
    goto LABEL_5;
  }
  *((_DWORD *)this + 30) = 1;
  v8 = OpenEventW(0x100000u, 0, lpName);
  *((_QWORD *)this + 16) = v8;
  if ( !v8 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = GetLastError();
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids,
      (_DWORD)lpName,
      v9);
  }
  p_pftTimeout = 0;
LABEL_12:
  if ( *((_QWORD *)this + 16) )
  {
    ThreadpoolWait = CreateThreadpoolWait(CTaskHandler::MaintenanceModeWaitCallback, this, 0);
    *((_QWORD *)this + 17) = ThreadpoolWait;
    if ( ThreadpoolWait )
    {
      SetThreadpoolWait(ThreadpoolWait, *((HANDLE *)this + 16), p_pftTimeout);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = GetLastError();
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids,
        (unsigned int)v10);
    }
  }
  if ( lpName )
  {
    LocalFree((HLOCAL)lpName);
    lpName = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
}

```

## disassembly

```asm
0x180006264  mov     [rsp+arg_10], rbx
0x180006269  push    rbp
0x18000626a  push    r13
0x18000626c  push    r14
0x18000626e  sub     rsp, 30h
0x180006272  mov     rbx, rcx
0x180006275  add     rcx, 50h ; 'P'; lpCriticalSection
0x180006279  call    cs:__imp_EnterCriticalSection
0x18000627f  xor     edx, edx; int
0x180006281  mov     [rsp+48h+lpName], 0
0x18000628a  mov     rcx, rbx; this
0x18000628d  mov     qword ptr [rsp+48h+pftTimeout.dwLowDateTime], 0
0x180006296  call    ?ExitMaintenanceMode@CTaskHandler@@AEAAXH@Z; CTaskHandler::ExitMaintenanceMode(int)
0x18000629b  mov     rcx, [rbx+48h]
0x18000629f  lea     r13, WPP_GLOBAL_Control
0x1800062a6  test    rcx, rcx
0x1800062a9  jnz     loc_18000639B
0x1800062af  mov     eax, 80070426h
0x1800062b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062bb  cmp     rcx, r13
0x1800062be  jz      loc_1800063E2
0x1800062c4  test    byte ptr [rcx+1Ch], 1
0x1800062c8  jz      loc_1800063E2
0x1800062ce  mov     rcx, [rcx+10h]
0x1800062d2  lea     r8, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids
0x1800062d9  mov     edx, 11h
0x1800062de  call    WPP_SF_
0x1800062e3  xor     r9d, r9d; lpName
0x1800062e6  lea     rbp, [rsp+48h+pftTimeout]
0x1800062eb  xor     ecx, ecx; lpEventAttributes
0x1800062ed  lea     edx, [r9+1]; bManualReset
0x1800062f1  mov     r8d, edx; bInitialState
0x1800062f4  call    cs:__imp_CreateEventW
0x1800062fa  mov     [rbx+80h], rax
0x180006301  test    rax, rax
0x180006304  jnz     short loc_180006349
0x180006306  mov     rax, cs:WPP_GLOBAL_Control
0x18000630d  cmp     rax, r13
0x180006310  jz      short loc_180006349
0x180006312  test    byte ptr [rax+1Ch], 1
0x180006316  jz      short loc_180006349
0x180006318  call    cs:__imp_GetLastError
0x18000631e  test    eax, eax
0x180006320  jle     short loc_18000632A
0x180006322  movzx   eax, ax
0x180006325  or      eax, 80070000h
0x18000632a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006331  lea     r8, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids
0x180006338  mov     edx, 14h
0x18000633d  mov     r9d, eax
0x180006340  mov     rcx, [rcx+10h]
0x180006344  call    WPP_SF_d
0x180006349  mov     qword ptr [rsp+48h+pftTimeout.dwLowDateTime], 0FFFFFFFFFF676980h
0x180006352  cmp     qword ptr [rbx+80h], 0
0x18000635a  jz      loc_18000649B
0x180006360  xor     r8d, r8d; pcbe
0x180006363  lea     rcx, ?MaintenanceModeWaitCallback@CTaskHandler@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x18000636a  mov     rdx, rbx; pv
0x18000636d  call    cs:__imp_CreateThreadpoolWait
0x180006373  mov     [rbx+88h], rax
0x18000637a  test    rax, rax
0x18000637d  jz      loc_180006458
0x180006383  mov     rdx, [rbx+80h]; h
0x18000638a  mov     r8, rbp; pftTimeout
0x18000638d  mov     rcx, rax; pwa
0x180006390  call    cs:__imp_SetThreadpoolWait
0x180006396  jmp     loc_18000649B
0x18000639b  lea     rdx, [rsp+48h+lpName]
0x1800063a0  call    cs:__imp_FhServiceEnterMaintenanceMode
0x1800063a6  test    eax, eax
0x1800063a8  js      short loc_1800063B3
0x1800063aa  mov     dword ptr [rbx+78h], 1
0x1800063b1  jmp     short loc_1800063EA
0x1800063b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063ba  cmp     rcx, r13
0x1800063bd  jz      short loc_1800063E2
0x1800063bf  test    byte ptr [rcx+1Ch], 1
0x1800063c3  jz      short loc_1800063E2
0x1800063c5  mov     rcx, [rcx+10h]
0x1800063c9  lea     r8, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids
0x1800063d0  mov     edx, 12h
0x1800063d5  mov     r9d, eax
0x1800063d8  call    WPP_SF_d
0x1800063dd  jmp     loc_1800062E3
0x1800063e2  test    eax, eax
0x1800063e4  js      loc_1800062E3
0x1800063ea  mov     r8, [rsp+48h+lpName]; lpName
0x1800063ef  xor     edx, edx; bInheritHandle
0x1800063f1  mov     ecx, 100000h; dwDesiredAccess
0x1800063f6  call    cs:__imp_OpenEventW
0x1800063fc  mov     [rbx+80h], rax
0x180006403  test    rax, rax
0x180006406  jnz     short loc_180006451
0x180006408  mov     rax, cs:WPP_GLOBAL_Control
0x18000640f  cmp     rax, r13
0x180006412  jz      short loc_180006451
0x180006414  test    byte ptr [rax+1Ch], 1
0x180006418  jz      short loc_180006451
0x18000641a  call    cs:__imp_GetLastError
0x180006420  test    eax, eax
0x180006422  jle     short loc_18000642C
0x180006424  movzx   eax, ax
0x180006427  or      eax, 80070000h
0x18000642c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006433  lea     r8, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids
0x18000643a  mov     r9, [rsp+48h+lpName]
0x18000643f  mov     edx, 13h
0x180006444  mov     [rsp+48h+var_28], eax
0x180006448  mov     rcx, [rcx+10h]
0x18000644c  call    WPP_SF_Sd
0x180006451  xor     ebp, ebp
0x180006453  jmp     loc_180006352
0x180006458  mov     rax, cs:WPP_GLOBAL_Control
0x18000645f  cmp     rax, r13
0x180006462  jz      short loc_18000649B
0x180006464  test    byte ptr [rax+1Ch], 1
0x180006468  jz      short loc_18000649B
0x18000646a  call    cs:__imp_GetLastError
0x180006470  test    eax, eax
0x180006472  jle     short loc_18000647C
0x180006474  movzx   eax, ax
0x180006477  or      eax, 80070000h
0x18000647c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006483  lea     r8, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids
0x18000648a  mov     edx, 15h
0x18000648f  mov     r9d, eax
0x180006492  mov     rcx, [rcx+10h]
0x180006496  call    WPP_SF_d
0x18000649b  mov     rcx, [rsp+48h+lpName]; hMem
0x1800064a0  test    rcx, rcx
0x1800064a3  jz      short loc_1800064B4
0x1800064a5  call    cs:__imp_LocalFree
0x1800064ab  mov     [rsp+48h+lpName], 0
0x1800064b4  lea     rcx, [rbx+50h]; lpCriticalSection
0x1800064b8  call    cs:__imp_LeaveCriticalSection
0x1800064be  mov     rbx, [rsp+48h+arg_10]
0x1800064c3  add     rsp, 30h
0x1800064c7  pop     r14
0x1800064c9  pop     r13
0x1800064cb  pop     rbp
0x1800064cc  retn
```
