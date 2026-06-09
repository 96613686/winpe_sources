# HandleCompletedSendJob(_JOB_ENTRY *)

- ea: `0x1400314a8`
- end: `0x140031b65`
- name: `?HandleCompletedSendJob@@YAHPEAU_JOB_ENTRY@@@Z`
- size: `1725`
- prototype: `__int64 __fastcall(struct _JOB_ENTRY *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14002f9f0`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004e68`
- `0x140022a4c`
- `0x14002b8c0`
- `0x14002cfcc`
- `0x14002efb8`
- `0x14002f32c`
- `0x1400314a8`
- `0x1400330ec`
- `0x140034564`
- `0x140034ae4`
- `0x140037b14`
- `0x14003909c`
- `0x14003a3d8`
- `0x14003e7ac`
- `0x14004efe0`
- `0x140055acc`
- `0x140065df8`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003158a`
- `KERNEL32!GetLastError` at `0x140031797`
- `KERNEL32!GetLastError` at `0x140031891`
- `KERNEL32!GetLastError` at `0x140031a21`
- `KERNEL32!GetLastError` at `0x140031a84`
- `KERNEL32!GetLastError` at `0x140031ae0`
- `KERNEL32!GetLastError` at `0x14003158a`
- `KERNEL32!GetLastError` at `0x140031797`
- `KERNEL32!GetLastError` at `0x140031891`
- `KERNEL32!GetLastError` at `0x140031a21`
- `KERNEL32!GetLastError` at `0x140031a84`
- `KERNEL32!GetLastError` at `0x140031ae0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140031520`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140031520`
- `KERNEL32!EnterCriticalSection` at `0x14003150f`
- `KERNEL32!EnterCriticalSection` at `0x140031634`
- `KERNEL32!EnterCriticalSection` at `0x1400316ab`
- `KERNEL32!EnterCriticalSection` at `0x1400317ce`
- `KERNEL32!EnterCriticalSection` at `0x1400318c2`
- `KERNEL32!EnterCriticalSection` at `0x140031b1e`
- `KERNEL32!EnterCriticalSection` at `0x14003150f`
- `KERNEL32!EnterCriticalSection` at `0x140031634`
- `KERNEL32!EnterCriticalSection` at `0x1400316ab`
- `KERNEL32!EnterCriticalSection` at `0x1400317ce`
- `KERNEL32!EnterCriticalSection` at `0x1400318c2`
- `KERNEL32!EnterCriticalSection` at `0x140031b1e`
- `KERNEL32!LeaveCriticalSection` at `0x14003164b`
- `KERNEL32!LeaveCriticalSection` at `0x1400316fe`
- `KERNEL32!LeaveCriticalSection` at `0x140031854`
- `KERNEL32!LeaveCriticalSection` at `0x140031aba`
- `KERNEL32!LeaveCriticalSection` at `0x140031ac7`
- `KERNEL32!LeaveCriticalSection` at `0x140031b38`
- `KERNEL32!LeaveCriticalSection` at `0x14003164b`
- `KERNEL32!LeaveCriticalSection` at `0x1400316fe`
- `KERNEL32!LeaveCriticalSection` at `0x140031854`
- `KERNEL32!LeaveCriticalSection` at `0x140031aba`
- `KERNEL32!LeaveCriticalSection` at `0x140031ac7`
- `KERNEL32!LeaveCriticalSection` at `0x140031b38`
- `KERNEL32!SetEvent` at `0x140031a62`
- `KERNEL32!SetEvent` at `0x140031a62`
- `ole32!CoUninitialize` at `0x1400317c1`
- `ole32!CoUninitialize` at `0x1400317c1`
- `ole32!CoInitializeEx` at `0x14003165d`
- `ole32!CoInitializeEx` at `0x14003165d`

## pseudocode

```c
__int64 __fastcall HandleCompletedSendJob(struct _JOB_ENTRY *a1)
{
  __int64 v2; // rdi
  DWORD LastError; // eax
  DWORD v4; // ebx
  __int64 v5; // rbp
  int v6; // ebx
  HRESULT v7; // eax
  unsigned int v8; // esi
  __int64 v9; // rdx
  __int64 v10; // rbx
  _WORD *v11; // r8
  char *v12; // rax
  char *v13; // r8
  DWORD v14; // eax
  CMapDeviceId *v15; // rcx
  __int64 v16; // rdx
  DWORD v17; // eax
  __int64 v18; // rbx
  __int64 v19; // rcx
  int v20; // eax
  _WORD *v21; // rcx
  _WORD *v22; // rax
  _WORD *v23; // rcx
  int QueueEvent; // eax
  _QWORD *v25; // rcx
  int v26; // r9d
  DWORD v27; // eax
  DWORD v28; // eax
  DWORD v29; // eax
  __int64 v31; // [rsp+20h] [rbp-2A8h]
  unsigned __int16 v32[14]; // [rsp+44h] [rbp-284h] BYREF
  char v33; // [rsp+60h] [rbp-268h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  EnterCriticalSection(&g_CsJob);
  v2 = *((_QWORD *)a1 + 138);
  GetSystemTimeAsFileTime((LPFILETIME)a1 + 6);
  *((_QWORD *)a1 + 7) = *((_QWORD *)a1 + 6) - *((_QWORD *)a1 + 5);
  if ( !*(_QWORD *)(v2 + 72) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        173,
        &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *(unsigned int *)(v2 + 32));
    }
    if ( !(unsigned int)CreateTiffFileForJob((struct _JOB_QUEUE *)v2) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          174,
          &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
          *(unsigned int *)(v2 + 32),
          LastError);
      }
      v32[0] = 0;
      StringCchPrintfW(v32, 0xCu, L"%ld", v4);
      v31 = *((_QWORD *)g_pFaxConfig + 12);
      FaxLog(2, 1, 1, 3221257548LL);
    }
  }
  v5 = 2147483646;
  if ( *(_QWORD *)(v2 + 72) )
  {
    EnterCriticalSection(&g_CsConfig);
    v6 = *((_DWORD *)g_pFaxConfig + 11);
    LeaveCriticalSection(&g_CsConfig);
    if ( v6 )
    {
      v7 = CoInitializeEx(0, 0);
      v8 = v7;
      if ( v7 >= 0 )
      {
        if ( !ArchiveOutboundJob((const struct _JOB_QUEUE *)v2)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = GetLastError();
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            176,
            &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
            *(unsigned int *)(v2 + 32),
            v14);
        }
        CoUninitialize();
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            175,
            &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
            (unsigned int)v7);
        }
        EnterCriticalSection(&g_CsConfig);
        v9 = 2147483646;
        v10 = 260;
        v11 = (_WORD *)*((_QWORD *)g_pFaxConfig + 6);
        v12 = &v33;
        do
        {
          if ( !v9 )
            break;
          if ( !*v11 )
            break;
          *(_WORD *)v12 = *v11++;
          v12 += 2;
          --v9;
          --v10;
        }
        while ( v10 );
        v13 = v12 - 2;
        if ( v10 )
          v13 = v12;
        *(_WORD *)v13 = 0;
        LeaveCriticalSection(&g_CsConfig);
        if ( v10 )
        {
          v32[0] = 0;
          StringCchPrintfW(v32, 0xCu, L"%ld", v8);
          v31 = *(_QWORD *)(v2 + 72);
          FaxLog(2, 1, 3, 3221257492LL);
        }
      }
    }
  }
  EnterCriticalSection(&g_CsOutboundActivityLogging);
  if ( g_hOutboxActivityLogFile == (HANDLE)-1LL )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 177;
LABEL_42:
      WPP_SF_(*((_QWORD *)v15 + 2), v16, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
    }
  }
  else if ( !(unsigned int)LogOutboundActivity((struct _JOB_QUEUE *)v2) )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 178;
      goto LABEL_42;
    }
  }
  LeaveCriticalSection(&g_CsOutboundActivityLogging);
  FaxLogSend((const struct _JOB_QUEUE *)v2, 0);
  if ( g_pFaxPerfCounters
    && !(unsigned int)UpdatePerfCounters(v2)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = GetLastError();
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      179,
      &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
      *(unsigned int *)(v2 + 32),
      v17);
  }
  EnterCriticalSection(&g_CsQueue);
  v18 = 256;
  _JOB_QUEUE::PutStatus((_JOB_QUEUE *)v2, 0x100u);
  v19 = *(_QWORD *)(v2 + 40);
  v20 = *(_DWORD *)(v19 + 1132);
  v21 = (_WORD *)(v19 + 1216);
  *(_DWORD *)(v2 + 1688) = v20;
  v22 = (_WORD *)(v2 + 1176);
  do
  {
    if ( !v5 )
      break;
    if ( !*v21 )
      break;
    *v22++ = *v21++;
    --v5;
    --v18;
  }
  while ( v18 );
  v23 = v22 - 1;
  if ( v18 )
    v23 = v22;
  *v23 = 0;
  if ( !(unsigned int)UpdatePersistentJobStatus((struct _JOB_QUEUE *const)v2)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      180,
      &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
      *(unsigned int *)(v2 + 1844));
  }
  ++*(_DWORD *)(*(_QWORD *)(v2 + 584) + 376LL);
  QueueEvent = CreateQueueEvent(2, v2);
  if ( QueueEvent
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LOWORD(v31) = QueueEvent;
    WPP_SF_lh(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      181,
      &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
      *(unsigned int *)(v2 + 16),
      v31);
  }
  IncreaseJobRefCount((struct _JOB_QUEUE *)v2, 1);
  v25 = *(_QWORD **)(v2 + 40);
  *(_QWORD *)(v2 + 1160) = v25[5];
  *(_QWORD *)(v2 + 1168) = v25[6];
  *(_DWORD *)(v25[2] + 72LL) = 537919488;
  UpdateDeviceJobsCounter(*(struct _LINE_INFO **)(*(_QWORD *)(v2 + 40) + 16LL), 1, -1, v26);
  if ( !(unsigned int)EndJob(*(struct _JOB_ENTRY **)(v2 + 40), 1)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v27 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v27);
  }
  *(_QWORD *)(v2 + 40) = 0;
  DecreaseJobRefCount((struct _JOB_QUEUE *)v2, 1, 1, 0);
  if ( !SetEvent(g_hJobQueueEvent) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v28 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v28);
    }
    g_ScanQueueAfterTimeout = 1;
  }
  LeaveCriticalSection(&g_CsQueue);
  LeaveCriticalSection(&g_CsJob);
  if ( !(unsigned int)SendJobReceipt(1, (struct _JOB_QUEUE *)v2, *(unsigned __int16 **)(v2 + 72)) )
  {
    v29 = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        184,
        &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *(unsigned int *)(v2 + 32),
        v29);
    }
  }
  EnterCriticalSection(&g_CsQueue);
  DecreaseJobRefCount((struct _JOB_QUEUE *)v2, 1, 1, 1);
  LeaveCriticalSection(&g_CsQueue);
  return 1;
}

```

## disassembly

```asm
0x1400314a8  push    rbx
0x1400314aa  push    rbp
0x1400314ab  push    rsi
0x1400314ac  push    rdi
0x1400314ad  push    r12
0x1400314af  push    r13
0x1400314b1  push    r14
0x1400314b3  push    r15
0x1400314b5  sub     rsp, 288h
0x1400314bc  mov     rax, cs:__security_cookie
0x1400314c3  xor     rax, rsp
0x1400314c6  mov     [rsp+2C8h+var_58], rax
0x1400314ce  mov     rsi, rcx
0x1400314d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400314d8  lea     rbp, WPP_GLOBAL_Control
0x1400314df  mov     r13b, 4
0x1400314e2  cmp     rcx, rbp
0x1400314e5  jz      short loc_140031508
0x1400314e7  test    [rcx+1Ch], r13b
0x1400314eb  jz      short loc_140031508
0x1400314ed  cmp     byte ptr [rcx+19h], 5
0x1400314f1  jb      short loc_140031508
0x1400314f3  mov     rcx, [rcx+10h]
0x1400314f7  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400314fe  mov     edx, 0ACh
0x140031503  call    WPP_SF_
0x140031508  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003150f  call    cs:__imp_EnterCriticalSection
0x140031515  mov     rdi, [rsi+450h]
0x14003151c  lea     rcx, [rsi+30h]; lpSystemTimeAsFileTime
0x140031520  call    cs:__imp_GetSystemTimeAsFileTime
0x140031526  mov     rax, [rsi+30h]
0x14003152a  mov     r15d, 2
0x140031530  sub     rax, [rsi+28h]
0x140031534  xor     r14d, r14d
0x140031537  mov     [rsi+38h], rax
0x14003153b  lea     r12d, [r15-1]
0x14003153f  cmp     [rdi+48h], r14
0x140031543  jnz     loc_14003161E
0x140031549  mov     rcx, cs:WPP_GLOBAL_Control
0x140031550  cmp     rcx, rbp
0x140031553  jz      short loc_14003157A
0x140031555  test    [rcx+1Ch], r13b
0x140031559  jz      short loc_14003157A
0x14003155b  cmp     byte ptr [rcx+19h], 5
0x14003155f  jb      short loc_14003157A
0x140031561  mov     r9d, [rdi+20h]
0x140031565  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14003156c  mov     rcx, [rcx+10h]
0x140031570  mov     edx, 0ADh
0x140031575  call    WPP_SF_d
0x14003157a  mov     rcx, rdi; struct _JOB_QUEUE *
0x14003157d  call    ?CreateTiffFileForJob@@YAHPEAU_JOB_QUEUE@@@Z; CreateTiffFileForJob(_JOB_QUEUE *)
0x140031582  test    eax, eax
0x140031584  jnz     loc_14003161E
0x14003158a  call    cs:__imp_GetLastError
0x140031590  mov     ebx, eax
0x140031592  mov     rcx, cs:WPP_GLOBAL_Control
0x140031599  cmp     rcx, rbp
0x14003159c  jz      short loc_1400315C7
0x14003159e  test    [rcx+1Ch], r13b
0x1400315a2  jz      short loc_1400315C7
0x1400315a4  cmp     [rcx+19h], r15b
0x1400315a8  jb      short loc_1400315C7
0x1400315aa  mov     r9d, [rdi+20h]
0x1400315ae  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400315b5  mov     rcx, [rcx+10h]
0x1400315b9  mov     edx, 0AEh
0x1400315be  mov     dword ptr [rsp+2C8h+var_2A8], eax
0x1400315c2  call    WPP_SF_dd
0x1400315c7  mov     r9d, ebx
0x1400315ca  mov     [rsp+2C8h+var_288], ebx
0x1400315ce  lea     r8, aLd; "%ld"
0x1400315d5  mov     [rsp+2C8h+var_284], r14w
0x1400315db  mov     edx, 0Ch; unsigned __int64
0x1400315e0  lea     rcx, [rsp+2C8h+var_284]; unsigned __int16 *
0x1400315e5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400315ea  test    eax, eax
0x1400315ec  lea     rdx, [rsp+2C8h+var_284]
0x1400315f1  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x1400315f8  mov     r9d, 0C0007D4Ch
0x1400315fe  cmovs   rdx, r14
0x140031602  mov     r8d, r12d
0x140031605  mov     [rsp+2C8h+var_2A0], rdx
0x14003160a  mov     edx, r12d
0x14003160d  mov     rcx, [rax+60h]
0x140031611  mov     [rsp+2C8h+var_2A8], rcx
0x140031616  mov     ecx, r15d
0x140031619  call    FaxLog
0x14003161e  mov     ebp, 7FFFFFFEh
0x140031623  cmp     [rdi+48h], r14
0x140031627  jz      loc_1400317C7
0x14003162d  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140031634  call    cs:__imp_EnterCriticalSection
0x14003163a  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140031641  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140031648  mov     ebx, [rax+2Ch]
0x14003164b  call    cs:__imp_LeaveCriticalSection
0x140031651  test    ebx, ebx
0x140031653  jz      loc_1400317C7
0x140031659  xor     edx, edx; dwCoInit
0x14003165b  xor     ecx, ecx; pvReserved
0x14003165d  call    cs:__imp_CoInitializeEx
0x140031663  mov     esi, eax
0x140031665  test    eax, eax
0x140031667  jns     loc_14003176C
0x14003166d  mov     rcx, cs:WPP_GLOBAL_Control
0x140031674  lea     rdx, WPP_GLOBAL_Control
0x14003167b  cmp     rcx, rdx
0x14003167e  jz      short loc_1400316A4
0x140031680  test    [rcx+1Ch], r13b
0x140031684  jz      short loc_1400316A4
0x140031686  cmp     [rcx+19h], r15b
0x14003168a  jb      short loc_1400316A4
0x14003168c  mov     rcx, [rcx+10h]
0x140031690  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140031697  mov     edx, 0AFh
0x14003169c  mov     r9d, eax
0x14003169f  call    WPP_SF_d
0x1400316a4  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400316ab  call    cs:__imp_EnterCriticalSection
0x1400316b1  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x1400316b8  mov     rdx, rbp
0x1400316bb  mov     ebx, 104h
0x1400316c0  mov     r8, [rax+30h]
0x1400316c4  lea     rax, [rsp+2C8h+var_268]
0x1400316c9  test    rdx, rdx
0x1400316cc  jz      short loc_1400316E8
0x1400316ce  movzx   ecx, word ptr [r8]
0x1400316d2  test    cx, cx
0x1400316d5  jz      short loc_1400316E8
0x1400316d7  mov     [rax], cx
0x1400316da  add     r8, r15
0x1400316dd  add     rax, r15
0x1400316e0  sub     rdx, r12
0x1400316e3  sub     rbx, r12
0x1400316e6  jnz     short loc_1400316C9
0x1400316e8  lea     r8, [rax-2]
0x1400316ec  test    rbx, rbx
0x1400316ef  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400316f6  cmovnz  r8, rax
0x1400316fa  mov     [r8], r14w
0x1400316fe  call    cs:__imp_LeaveCriticalSection
0x140031704  test    rbx, rbx
0x140031707  jz      loc_1400317C7
0x14003170d  mov     r9d, esi
0x140031710  mov     [rsp+2C8h+var_288], esi
0x140031714  lea     r8, aLd; "%ld"
0x14003171b  mov     [rsp+2C8h+var_284], r14w
0x140031721  mov     edx, 0Ch; unsigned __int64
0x140031726  lea     rcx, [rsp+2C8h+var_284]; unsigned __int16 *
0x14003172b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140031730  test    eax, eax
0x140031732  lea     rdx, [rsp+2C8h+var_284]
0x140031737  lea     rax, [rsp+2C8h+var_268]
0x14003173c  mov     r9d, 0C0007D14h
0x140031742  cmovs   rdx, r14
0x140031746  mov     r8d, 3
0x14003174c  mov     [rsp+2C8h+var_298], rdx
0x140031751  mov     ecx, r15d
0x140031754  mov     [rsp+2C8h+var_2A0], rax
0x140031759  mov     edx, r12d
0x14003175c  mov     rax, [rdi+48h]
0x140031760  mov     [rsp+2C8h+var_2A8], rax
0x140031765  call    FaxLog
0x14003176a  jmp     short loc_1400317C7
0x14003176c  mov     rcx, rdi; struct _JOB_QUEUE *
0x14003176f  call    ?ArchiveOutboundJob@@YAHPEBU_JOB_QUEUE@@@Z; ArchiveOutboundJob(_JOB_QUEUE const *)
0x140031774  test    eax, eax
0x140031776  jnz     short loc_1400317C1
0x140031778  mov     rax, cs:WPP_GLOBAL_Control
0x14003177f  lea     rdx, WPP_GLOBAL_Control
0x140031786  cmp     rax, rdx
0x140031789  jz      short loc_1400317C1
0x14003178b  test    [rax+1Ch], r13b
0x14003178f  jz      short loc_1400317C1
0x140031791  cmp     [rax+19h], r15b
0x140031795  jb      short loc_1400317C1
0x140031797  call    cs:__imp_GetLastError
0x14003179d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400317a4  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400317ab  mov     r9d, [rdi+20h]
0x1400317af  mov     edx, 0B0h
0x1400317b4  mov     dword ptr [rsp+2C8h+var_2A8], eax
0x1400317b8  mov     rcx, [rcx+10h]
0x1400317bc  call    WPP_SF_dd
0x1400317c1  call    cs:__imp_CoUninitialize
0x1400317c7  lea     rcx, ?g_CsOutboundActivityLogging@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400317ce  call    cs:__imp_EnterCriticalSection
0x1400317d4  cmp     cs:?g_hOutboxActivityLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * g_hOutboxActivityLogFile
0x1400317dc  jnz     short loc_140031814
0x1400317de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400317e5  lea     rsi, WPP_GLOBAL_Control
0x1400317ec  cmp     rcx, rsi
0x1400317ef  jz      short loc_14003184D
0x1400317f1  test    [rcx+1Ch], r13b
0x1400317f5  jz      short loc_14003184D
0x1400317f7  cmp     [rcx+19h], r15b
0x1400317fb  jb      short loc_14003184D
0x1400317fd  mov     edx, 0B1h
0x140031802  mov     rcx, [rcx+10h]
0x140031806  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14003180d  call    WPP_SF_
0x140031812  jmp     short loc_14003184D
0x140031814  mov     rcx, rdi; struct _JOB_QUEUE *
0x140031817  call    ?LogOutboundActivity@@YAHPEAU_JOB_QUEUE@@@Z; LogOutboundActivity(_JOB_QUEUE *)
0x14003181c  test    eax, eax
0x14003181e  jnz     short loc_140031846
0x140031820  mov     rcx, cs:WPP_GLOBAL_Control
0x140031827  lea     rsi, WPP_GLOBAL_Control
0x14003182e  cmp     rcx, rsi
0x140031831  jz      short loc_14003184D
0x140031833  test    [rcx+1Ch], r13b
0x140031837  jz      short loc_14003184D
0x140031839  cmp     [rcx+19h], r15b
0x14003183d  jb      short loc_14003184D
0x14003183f  mov     edx, 0B2h
0x140031844  jmp     short loc_140031802
0x140031846  lea     rsi, WPP_GLOBAL_Control
0x14003184d  lea     rcx, ?g_CsOutboundActivityLogging@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140031854  call    cs:__imp_LeaveCriticalSection
0x14003185a  xor     edx, edx; int
0x14003185c  mov     rcx, rdi; struct _JOB_QUEUE *
0x14003185f  call    ?FaxLogSend@@YAXPEBU_JOB_QUEUE@@H@Z; FaxLogSend(_JOB_QUEUE const *,int)
0x140031864  cmp     cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA, r14; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x14003186b  jz      short loc_1400318BB
0x14003186d  mov     rcx, rdi
0x140031870  call    UpdatePerfCounters
0x140031875  test    eax, eax
0x140031877  jnz     short loc_1400318BB
0x140031879  mov     rax, cs:WPP_GLOBAL_Control
0x140031880  cmp     rax, rsi
0x140031883  jz      short loc_1400318BB
0x140031885  test    [rax+1Ch], r13b
0x140031889  jz      short loc_1400318BB
0x14003188b  cmp     [rax+19h], r15b
0x14003188f  jb      short loc_1400318BB
0x140031891  call    cs:__imp_GetLastError
0x140031897  mov     rcx, cs:WPP_GLOBAL_Control
0x14003189e  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400318a5  mov     r9d, [rdi+20h]
0x1400318a9  mov     edx, 0B3h
0x1400318ae  mov     dword ptr [rsp+2C8h+var_2A8], eax
0x1400318b2  mov     rcx, [rcx+10h]
0x1400318b6  call    WPP_SF_dd
0x1400318bb  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400318c2  call    cs:__imp_EnterCriticalSection
0x1400318c8  mov     ebx, 100h
0x1400318cd  mov     rcx, rdi; this
0x1400318d0  mov     edx, ebx; unsigned int
0x1400318d2  call    ?PutStatus@_JOB_QUEUE@@QEAAXK@Z; _JOB_QUEUE::PutStatus(ulong)
0x1400318d7  mov     rcx, [rdi+28h]
0x1400318db  mov     eax, [rcx+46Ch]
0x1400318e1  add     rcx, 4C0h
0x1400318e8  mov     [rdi+698h], eax
0x1400318ee  lea     rax, [rdi+498h]
0x1400318f5  test    rbp, rbp
0x1400318f8  jz      short loc_140031913
0x1400318fa  movzx   edx, word ptr [rcx]
0x1400318fd  test    dx, dx
0x140031900  jz      short loc_140031913
0x140031902  mov     [rax], dx
0x140031905  add     rcx, r15
0x140031908  add     rax, r15
0x14003190b  sub     rbp, r12
0x14003190e  sub     rbx, r12
0x140031911  jnz     short loc_1400318F5
0x140031913  lea     rcx, [rax-2]
0x140031917  test    rbx, rbx
0x14003191a  cmovnz  rcx, rax
0x14003191e  mov     [rcx], r14w
0x140031922  mov     rcx, rdi; struct _JOB_QUEUE *
0x140031925  call    ?UpdatePersistentJobStatus@@YAHQEAU_JOB_QUEUE@@@Z; UpdatePersistentJobStatus(_JOB_QUEUE * const)
0x14003192a  test    eax, eax
0x14003192c  jnz     short loc_140031962
0x14003192e  mov     rcx, cs:WPP_GLOBAL_Control
0x140031935  cmp     rcx, rsi
0x140031938  jz      short loc_140031962
0x14003193a  test    [rcx+1Ch], r13b
0x14003193e  jz      short loc_140031962
0x140031940  cmp     [rcx+19h], r15b
0x140031944  jb      short loc_140031962
0x140031946  mov     r9d, [rdi+734h]
0x14003194d  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140031954  mov     rcx, [rcx+10h]
0x140031958  mov     edx, 0B4h
0x14003195d  call    WPP_SF_d
0x140031962  mov     rax, [rdi+248h]
0x140031969  mov     rdx, rdi
0x14003196c  mov     ecx, r15d
0x14003196f  add     [rax+178h], r12d
0x140031976  call    ?CreateQueueEvent@@YAKW4FAX_ENUM_JOB_EVENT_TYPE@@QEAU_JOB_QUEUE@@@Z; CreateQueueEvent(FAX_ENUM_JOB_EVENT_TYPE,_JOB_QUEUE * const)
0x14003197b  test    eax, eax
0x14003197d  jz      short loc_1400319B5
0x14003197f  mov     rcx, cs:WPP_GLOBAL_Control
0x140031986  cmp     rcx, rsi
0x140031989  jz      short loc_1400319B5
0x14003198b  test    [rcx+1Ch], r13b
0x14003198f  jz      short loc_1400319B5
0x140031991  cmp     [rcx+19h], r15b
  ... truncated ...
```
