# CManagerThread::Start(void *)

- ea: `0x1800026a0`
- end: `0x1800029d7`
- name: `?Start@CManagerThread@@QEAAJPEAX@Z`
- size: `823`
- prototype: `__int64 __fastcall(CManagerThread *this, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180001950`

## callees

- `0x1800026a0`
- `0x1800029e0`
- `0x180003190`
- `0x180003390`
- `0x18000ca14`
- `0x18000d840`
- `0x18000daf0`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180002725`
- `ADVAPI32!RegCreateKeyExW` at `0x180002725`
- `KERNEL32!CreateEventW` at `0x18000286b`
- `KERNEL32!CreateEventW` at `0x18000286b`
- `KERNEL32!GetLastError` at `0x18000279e`
- `KERNEL32!GetLastError` at `0x1800027ee`
- `KERNEL32!GetLastError` at `0x18000287d`
- `KERNEL32!GetLastError` at `0x1800028c8`
- `KERNEL32!GetLastError` at `0x180002974`
- `KERNEL32!GetLastError` at `0x18000279e`
- `KERNEL32!GetLastError` at `0x1800027ee`
- `KERNEL32!GetLastError` at `0x18000287d`
- `KERNEL32!GetLastError` at `0x1800028c8`
- `KERNEL32!GetLastError` at `0x180002974`
- `KERNEL32!LoadLibraryExW` at `0x18000278c`
- `KERNEL32!LoadLibraryExW` at `0x18000278c`
- `KERNEL32!GetProcAddress` at `0x1800027dc`
- `KERNEL32!GetProcAddress` at `0x1800027dc`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x1800028b6`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x1800028b6`
- `KERNEL32!CreateThreadpoolWait` at `0x180002962`
- `KERNEL32!CreateThreadpoolWait` at `0x180002962`
- `KERNEL32!SetThreadpoolWait` at `0x1800029c1`
- `KERNEL32!SetThreadpoolWait` at `0x1800029c1`

## string_xrefs

- `0x1800026f9`: `System\CurrentControlSet\Services\fhsvc\Parameters\Configs`
- `0x180002783`: `msidle.dll`

## pseudocode

```c
__int64 __fastcall CManagerThread::Start(CManagerThread *this, __int64 a2)
{
  LSTATUS Key; // eax
  CManagerThread *v4; // rcx
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  HMODULE Library; // rax
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  CManagerThread *v13; // rcx
  signed int v14; // eax
  struct _TP_WAIT *ThreadpoolWait; // rax
  signed int LastError; // eax
  CManagerThread *v17; // rcx
  _FILETIME pftTimeout; // [rsp+80h] [rbp+8h] BYREF

  pftTimeout = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids);
  qword_1800199E0 = a2;
  Key = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\fhsvc\\Parameters\\Configs",
          0,
          0,
          0,
          0x2001Fu,
          0,
          &g_ManagerThread,
          0);
  v5 = Key;
  if ( Key )
  {
    if ( Key > 0 )
      v5 = (unsigned __int16)Key | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 33;
LABEL_10:
      WPP_SF_d(v6[2], v7, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, v5);
      return v5;
    }
    return v5;
  }
  if ( (_QWORD)xmmword_180019A80 )
  {
LABEL_24:
    if ( (int)CManagerThread::CreateMaintenanceModeEvent(v4) < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
        "SUCCEEDED(hr)");
    }
    hEvent = CreateEventW(0, 1, 0, 0);
    if ( hEvent )
    {
      ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
      qword_180019960 = (__int64)ThreadpoolCleanupGroup;
      if ( ThreadpoolCleanupGroup )
      {
        dword_180019968 = 3;
        xmmword_180019990 = 0;
        qword_180019970 = 0;
        qword_180019988 = 0;
        dword_1800199A4 = 1;
        dword_1800199A8 = 72;
        qword_180019978 = (__int64)ThreadpoolCleanupGroup;
        qword_180019980 = 0;
        dword_1800199A0 = 1;
        CManagerThread::UpdatePowerState(v13);
        ThreadpoolWait = CreateThreadpoolWait(CManagerThread::WaitCallback, &g_ManagerThread, 0);
        pwa = ThreadpoolWait;
        if ( ThreadpoolWait )
        {
          pftTimeout = 0;
          v5 = 0;
          SetThreadpoolWait(ThreadpoolWait, hEvent, &pftTimeout);
          CManagerThread::ValidateAndCountRegisteredConfigs(v17);
          return v5;
        }
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 39;
          goto LABEL_10;
        }
      }
      else
      {
        v14 = GetLastError();
        v5 = v14;
        if ( v14 > 0 )
          v5 = (unsigned __int16)v14 | 0x80070000;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 38;
          goto LABEL_10;
        }
      }
    }
    else
    {
      v11 = GetLastError();
      v5 = v11;
      if ( v11 > 0 )
        v5 = (unsigned __int16)v11 | 0x80070000;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 37;
        goto LABEL_10;
      }
    }
    return v5;
  }
  Library = LoadLibraryExW(L"msidle.dll", 0, 0);
  *(_QWORD *)&xmmword_180019A80 = Library;
  if ( Library )
  {
    *((_QWORD *)&xmmword_180019A80 + 1) = GetProcAddress(Library, (LPCSTR)8);
    if ( !*((_QWORD *)&xmmword_180019A80 + 1) )
    {
      v10 = GetLastError();
      v5 = v10;
      if ( v10 > 0 )
        v5 = (unsigned __int16)v10 | 0x80070000;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 35;
        goto LABEL_10;
      }
      return v5;
    }
    goto LABEL_24;
  }
  v9 = GetLastError();
  v5 = v9;
  if ( v9 > 0 )
    v5 = (unsigned __int16)v9 | 0x80070000;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 34;
    goto LABEL_10;
  }
  return v5;
}

```

## disassembly

```asm
0x1800026a0  mov     qword ptr [rsp+pftTimeout.dwLowDateTime], rcx
0x1800026a5  push    rbx
0x1800026a6  push    rbp
0x1800026a7  push    rsi
0x1800026a8  push    rdi
0x1800026a9  sub     rsp, 58h
0x1800026ad  xor     edi, edi
0x1800026af  mov     rbx, rdx
0x1800026b2  mov     qword ptr [rsp+78h+pftTimeout.dwLowDateTime], rdi
0x1800026ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026c1  lea     rsi, WPP_GLOBAL_Control
0x1800026c8  cmp     rcx, rsi
0x1800026cb  jz      short loc_1800026E8
0x1800026cd  test    byte ptr [rcx+1Ch], 8
0x1800026d1  jz      short loc_1800026E8
0x1800026d3  mov     rcx, [rcx+10h]
0x1800026d7  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x1800026de  mov     edx, 20h ; ' '
0x1800026e3  call    WPP_SF_
0x1800026e8  mov     [rsp+78h+lpdwDisposition], rdi; lpdwDisposition
0x1800026ed  lea     rbp, ?g_ManagerThread@@3VCManagerThread@@A; CManagerThread g_ManagerThread
0x1800026f4  mov     [rsp+78h+phkResult], rbp; phkResult
0x1800026f9  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\fh"...
0x180002700  mov     [rsp+78h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180002705  xor     r9d, r9d; lpClass
0x180002708  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x180002710  xor     r8d, r8d; Reserved
0x180002713  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000271a  mov     [rsp+78h+dwOptions], edi; dwOptions
0x18000271e  mov     cs:qword_1800199E0, rbx
0x180002725  call    cs:__imp_RegCreateKeyExW
0x18000272b  mov     ebx, eax
0x18000272d  test    eax, eax
0x18000272f  jz      short loc_180002773
0x180002731  jle     short loc_18000273C
0x180002733  movzx   ebx, ax
0x180002736  or      ebx, 80070000h
0x18000273c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002743  cmp     rcx, rsi
0x180002746  jz      loc_1800029CC
0x18000274c  test    byte ptr [rcx+1Ch], 1
0x180002750  jz      loc_1800029CC
0x180002756  mov     edx, 21h ; '!'
0x18000275b  mov     rcx, [rcx+10h]
0x18000275f  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180002766  mov     r9d, ebx
0x180002769  call    WPP_SF_d
0x18000276e  jmp     loc_1800029CC
0x180002773  cmp     qword ptr cs:xmmword_180019A80, rdi
0x18000277a  jnz     loc_180002827
0x180002780  xor     r8d, r8d; dwFlags
0x180002783  lea     rcx, LibFileName; "msidle.dll"
0x18000278a  xor     edx, edx; hFile
0x18000278c  call    cs:__imp_LoadLibraryExW
0x180002792  mov     qword ptr cs:xmmword_180019A80, rax
0x180002799  test    rax, rax
0x18000279c  jnz     short loc_1800027D4
0x18000279e  call    cs:__imp_GetLastError
0x1800027a4  mov     ebx, eax
0x1800027a6  test    eax, eax
0x1800027a8  jle     short loc_1800027B3
0x1800027aa  movzx   ebx, ax
0x1800027ad  or      ebx, 80070000h
0x1800027b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027ba  cmp     rcx, rsi
0x1800027bd  jz      loc_1800029CC
0x1800027c3  test    byte ptr [rcx+1Ch], 1
0x1800027c7  jz      loc_1800029CC
0x1800027cd  mov     edx, 22h ; '"'
0x1800027d2  jmp     short loc_18000275B
0x1800027d4  mov     edx, 8; lpProcName
0x1800027d9  mov     rcx, rax; hModule
0x1800027dc  call    cs:__imp_GetProcAddress
0x1800027e2  mov     qword ptr cs:xmmword_180019A80+8, rax
0x1800027e9  test    rax, rax
0x1800027ec  jnz     short loc_180002827
0x1800027ee  call    cs:__imp_GetLastError
0x1800027f4  mov     ebx, eax
0x1800027f6  test    eax, eax
0x1800027f8  jle     short loc_180002803
0x1800027fa  movzx   ebx, ax
0x1800027fd  or      ebx, 80070000h
0x180002803  mov     rcx, cs:WPP_GLOBAL_Control
0x18000280a  cmp     rcx, rsi
0x18000280d  jz      loc_1800029CC
0x180002813  test    byte ptr [rcx+1Ch], 1
0x180002817  jz      loc_1800029CC
0x18000281d  mov     edx, 23h ; '#'
0x180002822  jmp     loc_18000275B
0x180002827  call    ?CreateMaintenanceModeEvent@CManagerThread@@QEAAJXZ; CManagerThread::CreateMaintenanceModeEvent(void)
0x18000282c  test    eax, eax
0x18000282e  jns     short loc_18000285E
0x180002830  mov     rcx, cs:WPP_GLOBAL_Control
0x180002837  cmp     rcx, rsi
0x18000283a  jz      short loc_18000285E
0x18000283c  test    byte ptr [rcx+1Ch], 4
0x180002840  jz      short loc_18000285E
0x180002842  mov     rcx, [rcx+10h]
0x180002846  lea     r9, aSucceededHr; "SUCCEEDED(hr)"
0x18000284d  mov     edx, 24h ; '$'
0x180002852  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180002859  call    WPP_SF_s
0x18000285e  xor     r9d, r9d; lpName
0x180002861  xor     r8d, r8d; bInitialState
0x180002864  mov     edx, 1; bManualReset
0x180002869  xor     ecx, ecx; lpEventAttributes
0x18000286b  call    cs:__imp_CreateEventW
0x180002871  mov     cs:hEvent, rax
0x180002878  test    rax, rax
0x18000287b  jnz     short loc_1800028B6
0x18000287d  call    cs:__imp_GetLastError
0x180002883  mov     ebx, eax
0x180002885  test    eax, eax
0x180002887  jle     short loc_180002892
0x180002889  movzx   ebx, ax
0x18000288c  or      ebx, 80070000h
0x180002892  mov     rcx, cs:WPP_GLOBAL_Control
0x180002899  cmp     rcx, rsi
0x18000289c  jz      loc_1800029CC
0x1800028a2  test    byte ptr [rcx+1Ch], 1
0x1800028a6  jz      loc_1800029CC
0x1800028ac  mov     edx, 25h ; '%'
0x1800028b1  jmp     loc_18000275B
0x1800028b6  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1800028bc  mov     cs:qword_180019960, rax
0x1800028c3  test    rax, rax
0x1800028c6  jnz     short loc_180002901
0x1800028c8  call    cs:__imp_GetLastError
0x1800028ce  mov     ebx, eax
0x1800028d0  test    eax, eax
0x1800028d2  jle     short loc_1800028DD
0x1800028d4  movzx   ebx, ax
0x1800028d7  or      ebx, 80070000h
0x1800028dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028e4  cmp     rcx, rsi
0x1800028e7  jz      loc_1800029CC
0x1800028ed  test    byte ptr [rcx+1Ch], 1
0x1800028f1  jz      loc_1800029CC
0x1800028f7  mov     edx, 26h ; '&'
0x1800028fc  jmp     loc_18000275B
0x180002901  xorps   xmm0, xmm0
0x180002904  mov     cs:dword_180019968, 3
0x18000290e  movdqa  cs:xmmword_180019990, xmm0
0x180002916  mov     cs:qword_180019970, rdi
0x18000291d  mov     cs:qword_180019988, rdi
0x180002924  mov     cs:dword_1800199A4, 1
0x18000292e  mov     cs:dword_1800199A8, 48h ; 'H'
0x180002938  mov     cs:qword_180019978, rax
0x18000293f  mov     cs:qword_180019980, rdi
0x180002946  mov     cs:dword_1800199A0, 1
0x180002950  call    ?UpdatePowerState@CManagerThread@@QEAAXXZ; CManagerThread::UpdatePowerState(void)
0x180002955  xor     r8d, r8d; pcbe
0x180002958  lea     rcx, ?WaitCallback@CManagerThread@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x18000295f  mov     rdx, rbp; pv
0x180002962  call    cs:__imp_CreateThreadpoolWait
0x180002968  mov     cs:pwa, rax
0x18000296f  test    rax, rax
0x180002972  jnz     short loc_1800029A5
0x180002974  call    cs:__imp_GetLastError
0x18000297a  mov     ebx, eax
0x18000297c  test    eax, eax
0x18000297e  jle     short loc_180002989
0x180002980  movzx   ebx, ax
0x180002983  or      ebx, 80070000h
0x180002989  mov     rcx, cs:WPP_GLOBAL_Control
0x180002990  cmp     rcx, rsi
0x180002993  jz      short loc_1800029CC
0x180002995  test    byte ptr [rcx+1Ch], 1
0x180002999  jz      short loc_1800029CC
0x18000299b  mov     edx, 27h ; '''
0x1800029a0  jmp     loc_18000275B
0x1800029a5  mov     rdx, cs:hEvent; h
0x1800029ac  lea     r8, [rsp+78h+pftTimeout]; pftTimeout
0x1800029b4  mov     rcx, rax; pwa
0x1800029b7  mov     qword ptr [rsp+78h+pftTimeout.dwLowDateTime], rdi
0x1800029bf  mov     ebx, edi
0x1800029c1  call    cs:__imp_SetThreadpoolWait
0x1800029c7  call    ?ValidateAndCountRegisteredConfigs@CManagerThread@@AEAAXXZ; CManagerThread::ValidateAndCountRegisteredConfigs(void)
0x1800029cc  mov     eax, ebx
0x1800029ce  add     rsp, 58h
0x1800029d2  pop     rdi
0x1800029d3  pop     rsi
0x1800029d4  pop     rbp
0x1800029d5  pop     rbx
0x1800029d6  retn
```
