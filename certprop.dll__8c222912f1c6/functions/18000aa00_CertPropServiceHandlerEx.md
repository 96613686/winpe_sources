# CertPropServiceHandlerEx

- ea: `0x18000aa00`
- end: `0x18000af7c`
- name: `CertPropServiceHandlerEx`
- size: `1404`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, const wchar_t *lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callees

- `0x180004600`
- `0x18000aa00`
- `0x18000af90`
- `0x1800188a4`
- `0x180018974`
- `0x180018bb4`
- `0x180018c28`
- `0x1800243ec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000ad12`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000ad12`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000ad01`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000ad01`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000acd4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000acd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ad75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ad75`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000adc9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000adc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aa33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ab40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aa33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ab40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adbc`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000adb2`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000adb2`

## pseudocode

```c
__int64 __fastcall CertPropServiceHandlerEx(
        DWORD dwControl,
        DWORD dwEventType,
        const wchar_t *lpEventData,
        LPVOID lpContext)
{
  int v4; // edi
  char v7; // r13
  DWORD CurrentThreadId; // eax
  char *i; // rcx
  size_t v10; // rdx
  int v11; // ebx
  int v13; // ebx
  DWORD RemovalRegisterCallback; // r12d
  DWORD v15; // eax
  size_t j; // rdx
  unsigned __int64 v17; // rcx
  int v18; // edx
  int v19; // r8d
  int v20; // r9d
  unsigned int v21; // r8d
  bool v22; // zf
  int v23; // r10d
  unsigned int v24; // r8d
  bool v25; // zf
  int v26; // r10d
  _DWORD *v27; // rax
  void *v28; // r14
  struct _TP_WORK *ThreadpoolWork; // rax
  __int64 v30; // rcx
  int v31; // [rsp+30h] [rbp-38h]

  v4 = 1;
  v7 = dwControl;
  if ( _InterlockedExchange(&g_fBlockServiceHandler, 1) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v10 = `WppTraceIndent'::`2'::idxCurrentThread;
    v11 = 0;
    if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
    {
      v10 = 0;
      `WppTraceIndent'::`2'::idxCurrentThread = 0;
      LODWORD(`WppTraceIndent'::`2'::ThreadTable) = CurrentThreadId;
      dword_180031404[0] = 0;
    }
    else
    {
      if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
        || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != CurrentThreadId )
      {
        v21 = -1;
        for ( i = 0; ; i = (char *)(unsigned int)((_DWORD)i + 1) )
        {
          v22 = (_DWORD)i == 32;
          if ( (unsigned int)i >= 0x20 )
            break;
          v23 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)i);
          if ( v23 == CurrentThreadId )
          {
            v10 = (unsigned int)i;
            `WppTraceIndent'::`2'::idxCurrentThread = (int)i;
            v22 = (_DWORD)i == 32;
            break;
          }
          if ( v21 == -1 && !v23 )
            v21 = (unsigned int)i;
        }
        if ( v22 )
        {
          if ( v21 == -1 )
          {
            `WppTraceIndent'::`2'::idxCurrentThread = -2;
            goto LABEL_9;
          }
          v10 = v21;
          `WppTraceIndent'::`2'::idxCurrentThread = v21;
          *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)v21) = CurrentThreadId;
          dword_180031404[2 * v21] = 0;
        }
      }
      if ( (v10 & 0x80000000) != 0LL )
      {
LABEL_9:
        `WppTraceIndent'::`2'::szIndentPrefix = 0;
        if ( (WPP_GLOBAL_Control[28] & 2) != 0 && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u && v11 >= 1 )
        {
          do
          {
            if ( StringCbCatA(i, v10, "..") )
              break;
            ++v4;
          }
          while ( v4 <= v11 );
        }
        StringCbCatA(i, v10, " ");
        WPP_pszIndent = (__int64)&`WppTraceIndent'::`2'::szIndentPrefix;
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            74,
            (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
            (unsigned int)&`WppTraceIndent'::`2'::szIndentPrefix,
            v7);
        }
        return 1115;
      }
    }
    v11 = dword_180031404[2 * (int)v10];
    goto LABEL_9;
  }
  v13 = 0;
  RemovalRegisterCallback = 0;
  switch ( dwControl )
  {
    case 1u:
    case 5u:
      *(_QWORD *)&ServiceStatus.dwControlsAccepted = 133;
      ServiceStatus.dwCurrentState = 3;
      ServiceStatus.dwWaitHint = 0;
      if ( !SetServiceStatus(g_hCertPropStatus, &ServiceStatus) )
        GetLastError();
      SetEvent(g_hCertPropStopEvent);
      break;
    case 0xBu:
      if ( dwEventType == 0x8000 )
      {
        if ( lpEventData
          && *((_DWORD *)lpEventData + 1) == 5
          && !memcmp_0(lpEventData + 6, &GUID_DEVINTERFACE_SMARTCARD, 0x10u) )
        {
          ScPnPSmartCardDeviceArrivalRegisterCallback(lpEventData + 14);
        }
      }
      else if ( dwEventType == 32769 || dwEventType == 32770 || dwEventType - 32771 <= 1 )
      {
        if ( lpEventData )
        {
          if ( *((_DWORD *)lpEventData + 1) == 6 )
          {
            RemovalRegisterCallback = ScPnPHandleQueryRemovalRegisterCallback(dwEventType, *((_QWORD *)lpEventData + 3));
            if ( RemovalRegisterCallback )
            {
              WppTraceIndent(v30, 2);
              if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control[28] & 1) != 0
                && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
              {
                WPP_SF_sD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  75,
                  (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
                  WPP_pszIndent,
                  RemovalRegisterCallback);
              }
            }
          }
        }
      }
      break;
    case 0xEu:
      if ( dwEventType == 2 )
      {
LABEL_53:
        RemovalRegisterCallback = 8;
        v31 = *((_DWORD *)lpEventData + 1);
        v27 = HeapAlloc(g_hHeap, 8u, 8u);
        v28 = v27;
        if ( v27 )
        {
          *v27 = dwEventType;
          v27[1] = v31;
          ThreadpoolWork = CreateThreadpoolWork(CertPropSessionHandlerThread, v27, &g_TpEnvironment);
          if ( ThreadpoolWork )
          {
            RemovalRegisterCallback = 0;
            SubmitThreadpoolWork(ThreadpoolWork);
          }
          else
          {
            HeapFree(g_hHeap, 0, v28);
            RemovalRegisterCallback = GetLastError();
          }
        }
      }
      else
      {
        switch ( dwEventType )
        {
          case 1u:
          case 3u:
          case 4u:
          case 5u:
          case 6u:
          case 7u:
          case 8u:
            goto LABEL_53;
          default:
            goto LABEL_17;
        }
      }
      break;
    default:
      RemovalRegisterCallback = 120;
      break;
  }
LABEL_17:
  _InterlockedExchange(&g_fBlockServiceHandler, 0);
  v15 = GetCurrentThreadId();
  v17 = `WppTraceIndent'::`2'::idxCurrentThread;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v17 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = v15;
    dword_180031404[0] = 0;
    goto LABEL_23;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
    || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != v15 )
  {
    v24 = -1;
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      v25 = (_DWORD)j == 32;
      if ( (unsigned int)j >= 0x20 )
        break;
      v26 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)j);
      if ( v26 == v15 )
      {
        v17 = (unsigned int)j;
        `WppTraceIndent'::`2'::idxCurrentThread = j;
        v25 = (_DWORD)j == 32;
        break;
      }
      if ( v24 == -1 && !v26 )
        v24 = j;
    }
    if ( v25 )
    {
      if ( v24 == -1 )
      {
        `WppTraceIndent'::`2'::idxCurrentThread = -2;
        goto LABEL_24;
      }
      v17 = v24;
      `WppTraceIndent'::`2'::idxCurrentThread = v24;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)v24) = v15;
      dword_180031404[2 * v24] = 0;
    }
  }
  if ( (v17 & 0x80000000) == 0LL )
LABEL_23:
    v13 = dword_180031404[2 * (int)v17];
LABEL_24:
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (WPP_GLOBAL_Control[28] & 2) != 0 && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u && v13 >= 1 )
  {
    do
    {
      if ( StringCbCatA((STRSAFE_LPSTR)v17, j, "..") )
        break;
      ++v4;
    }
    while ( v4 <= v13 );
  }
  StringCbCatA((STRSAFE_LPSTR)v17, j, " ");
  WPP_pszIndent = (__int64)&`WppTraceIndent'::`2'::szIndentPrefix;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, v20, v7, RemovalRegisterCallback);
  }
  return RemovalRegisterCallback;
}

```

## disassembly

```asm
0x18000aa00  mov     [rsp+arg_8], rbx
0x18000aa05  mov     [rsp+arg_10], rbp
0x18000aa0a  push    rsi
0x18000aa0b  push    rdi
0x18000aa0c  push    r13
0x18000aa0e  push    r14
0x18000aa10  push    r15
0x18000aa12  sub     rsp, 40h
0x18000aa16  mov     edi, 1
0x18000aa1b  mov     r14, r8
0x18000aa1e  mov     eax, edi
0x18000aa20  mov     ebp, edx
0x18000aa22  xchg    eax, cs:g_fBlockServiceHandler
0x18000aa28  mov     r13d, ecx
0x18000aa2b  test    eax, eax
0x18000aa2d  jz      loc_18000AAF4
0x18000aa33  call    cs:__imp_GetCurrentThreadId
0x18000aa39  movsxd  rdx, cs:?idxCurrentThread@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::idxCurrentThread
0x18000aa40  lea     rsi, __ImageBase
0x18000aa47  xor     ebx, ebx
0x18000aa49  mov     r9d, eax
0x18000aa4c  cmp     edx, 0FFFFFFFFh
0x18000aa4f  jz      short loc_18000AA6D
0x18000aa51  cmp     edx, 0FFFFFFFEh
0x18000aa54  jz      loc_18000ABDB
0x18000aa5a  cmp     rva ?ThreadTable@?1??WppTraceIndent@@9@9[rsi+rdx*8], eax; `WppTraceIndent'::`2'::ThreadTable ...
0x18000aa61  jnz     loc_18000ABDB
0x18000aa67  test    edx, edx
0x18000aa69  jns     short loc_18000AA82
0x18000aa6b  jmp     short loc_18000AA8C
0x18000aa6d  mov     edx, ebx; cbDest
0x18000aa6f  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ebx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000aa75  mov     cs:?ThreadTable@?1??WppTraceIndent@@9@9, r9d; `WppTraceIndent'::`2'::ThreadTable
0x18000aa7c  mov     cs:dword_180031404, ebx
0x18000aa82  movsxd  rax, edx
0x18000aa85  mov     ebx, rva dword_180031404[rsi+rax*8]
0x18000aa8c  mov     rax, cs:WPP_GLOBAL_Control
0x18000aa93  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@9@9, 0; `WppTraceIndent'::`2'::szIndentPrefix
0x18000aa9a  test    byte ptr [rax+1Ch], 2
0x18000aa9e  jnz     loc_18000AE14
0x18000aaa4  lea     r8, asc_180027F18; " "
0x18000aaab  call    StringCbCatA
0x18000aab0  lea     r10, ?szIndentPrefix@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::szIndentPrefix
0x18000aab7  mov     cs:WPP_pszIndent, r10
0x18000aabe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aac5  lea     r15, WPP_GLOBAL_Control
0x18000aacc  cmp     rcx, r15
0x18000aacf  jnz     loc_18000AE45
0x18000aad5  mov     eax, 45Bh
0x18000aada  mov     rbx, [rsp+68h+arg_8]
0x18000aadf  mov     rbp, [rsp+68h+arg_10]
0x18000aae7  add     rsp, 40h
0x18000aaeb  pop     r15
0x18000aaed  pop     r14
0x18000aaef  pop     r13
0x18000aaf1  pop     rdi
0x18000aaf2  pop     rsi
0x18000aaf3  retn
0x18000aaf4  xor     ebx, ebx
0x18000aaf6  mov     [rsp+68h+arg_0], r12
0x18000aafb  mov     eax, r13d
0x18000aafe  lea     rsi, __ImageBase
0x18000ab05  lea     r15, WPP_GLOBAL_Control
0x18000ab0c  mov     r12d, ebx
0x18000ab0f  sub     eax, edi
0x18000ab11  jz      loc_18000AD89
0x18000ab17  sub     eax, 4
0x18000ab1a  jz      loc_18000AD89
0x18000ab20  sub     eax, 6
0x18000ab23  jz      loc_18000AD1D
0x18000ab29  cmp     eax, 3
0x18000ab2c  jz      loc_18000ACB0
0x18000ab32  mov     r12d, 78h ; 'x'
0x18000ab38  mov     eax, ebx; jumptable 000000018000AE91 default case, case 2
0x18000ab3a  xchg    eax, cs:g_fBlockServiceHandler
0x18000ab40  call    cs:__imp_GetCurrentThreadId
0x18000ab46  movsxd  rcx, cs:?idxCurrentThread@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::idxCurrentThread
0x18000ab4d  mov     r9d, eax
0x18000ab50  cmp     ecx, 0FFFFFFFFh
0x18000ab53  jz      short loc_18000AB71
0x18000ab55  cmp     ecx, 0FFFFFFFEh
0x18000ab58  jz      loc_18000AC57
0x18000ab5e  cmp     rva ?ThreadTable@?1??WppTraceIndent@@9@9[rsi+rcx*8], eax; `WppTraceIndent'::`2'::ThreadTable ...
0x18000ab65  jnz     loc_18000AC57
0x18000ab6b  test    ecx, ecx
0x18000ab6d  jns     short loc_18000AB86
0x18000ab6f  jmp     short loc_18000AB90
0x18000ab71  mov     ecx, ebx; pszDest
0x18000ab73  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ebx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000ab79  mov     cs:?ThreadTable@?1??WppTraceIndent@@9@9, r9d; `WppTraceIndent'::`2'::ThreadTable
0x18000ab80  mov     cs:dword_180031404, ebx
0x18000ab86  movsxd  rax, ecx
0x18000ab89  mov     ebx, rva dword_180031404[rsi+rax*8]
0x18000ab90  mov     rax, cs:WPP_GLOBAL_Control
0x18000ab97  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@9@9, 0; `WppTraceIndent'::`2'::szIndentPrefix
0x18000ab9e  test    byte ptr [rax+1Ch], 2
0x18000aba2  jnz     loc_18000AF2A
0x18000aba8  lea     r8, asc_180027F18; " "
0x18000abaf  call    StringCbCatA
0x18000abb4  lea     r10, ?szIndentPrefix@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::szIndentPrefix
0x18000abbb  mov     cs:WPP_pszIndent, r10
0x18000abc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abc9  cmp     rcx, r15
0x18000abcc  jnz     short loc_18000AC33
0x18000abce  mov     eax, r12d
0x18000abd1  mov     r12, [rsp+68h+arg_0]
0x18000abd6  jmp     loc_18000AADA
0x18000abdb  mov     r8d, 0FFFFFFFFh
0x18000abe1  mov     ecx, ebx
0x18000abe3  cmp     ecx, 20h ; ' '
0x18000abe6  jnb     short loc_18000AC14
0x18000abe8  movsxd  rax, ecx
0x18000abeb  mov     r10d, rva ?ThreadTable@?1??WppTraceIndent@@9@9[rsi+rax*8]; `WppTraceIndent'::`2'::ThreadTable ...
0x18000abf3  cmp     r10d, r9d
0x18000abf6  jz      short loc_18000AC09
0x18000abf8  cmp     r8d, 0FFFFFFFFh
0x18000abfc  jnz     short loc_18000AC05
0x18000abfe  test    r10d, r10d
0x18000ac01  cmovz   r8d, ecx
0x18000ac05  inc     ecx
0x18000ac07  jmp     short loc_18000ABE3
0x18000ac09  mov     edx, ecx
0x18000ac0b  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ecx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000ac11  cmp     ecx, 20h ; ' '
0x18000ac14  jnz     loc_18000AA67
0x18000ac1a  cmp     r8d, 0FFFFFFFFh
0x18000ac1e  jnz     loc_18000ADD4
0x18000ac24  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, 0FFFFFFFEh; `WppTraceIndent'::`2'::idxCurrentThread
0x18000ac2e  jmp     loc_18000AA8C
0x18000ac33  test    byte ptr [rcx+1Ch], 1
0x18000ac37  jz      short loc_18000ABCE
0x18000ac39  cmp     byte ptr [rcx+19h], 4
0x18000ac3d  jb      short loc_18000ABCE
0x18000ac3f  mov     rcx, [rcx+10h]
0x18000ac43  mov     [rsp+68h+var_40], r12d
0x18000ac48  mov     [rsp+68h+var_48], r13d
0x18000ac4d  call    WPP_SF_sDD
0x18000ac52  jmp     loc_18000ABCE
0x18000ac57  mov     r8d, 0FFFFFFFFh
0x18000ac5d  mov     edx, ebx
0x18000ac5f  nop
0x18000ac60  cmp     edx, 20h ; ' '
0x18000ac63  jnb     short loc_18000AC91
0x18000ac65  movsxd  rax, edx
0x18000ac68  mov     r10d, rva ?ThreadTable@?1??WppTraceIndent@@9@9[rsi+rax*8]; `WppTraceIndent'::`2'::ThreadTable ...
0x18000ac70  cmp     r10d, r9d
0x18000ac73  jz      short loc_18000AC86
0x18000ac75  cmp     r8d, 0FFFFFFFFh
0x18000ac79  jnz     short loc_18000AC82
0x18000ac7b  test    r10d, r10d
0x18000ac7e  cmovz   r8d, edx
0x18000ac82  inc     edx
0x18000ac84  jmp     short loc_18000AC60
0x18000ac86  mov     ecx, edx
0x18000ac88  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, edx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000ac8e  cmp     edx, 20h ; ' '
0x18000ac91  jnz     loc_18000AB6B
0x18000ac97  cmp     r8d, 0FFFFFFFFh
0x18000ac9b  jnz     loc_18000ADF4
0x18000aca1  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, 0FFFFFFFEh; `WppTraceIndent'::`2'::idxCurrentThread
0x18000acab  jmp     loc_18000AB90
0x18000acb0  cmp     ebp, 2
0x18000acb3  jnz     loc_18000AE7B
0x18000acb9  mov     eax, [r8+4]; jumptable 000000018000AE91 cases 1,3-8
0x18000acbd  mov     r12d, 8
0x18000acc3  mov     rcx, cs:g_hHeap; hHeap
0x18000acca  mov     r8d, r12d; dwBytes
0x18000accd  mov     edx, r12d; dwFlags
0x18000acd0  mov     [rsp+68h+var_38], eax
0x18000acd4  call    cs:__imp_HeapAlloc
0x18000acda  mov     r14, rax
0x18000acdd  test    rax, rax
0x18000ace0  jz      def_18000AE91; jumptable 000000018000AE91 default case, case 2
0x18000ace6  mov     [rax], ebp
0x18000ace8  lea     r8, g_TpEnvironment; pcbe
0x18000acef  mov     eax, [rsp+68h+var_38]
0x18000acf3  lea     rcx, CertPropSessionHandlerThread; pfnwk
0x18000acfa  mov     rdx, r14; pv
0x18000acfd  mov     [r14+4], eax
0x18000ad01  call    cs:__imp_CreateThreadpoolWork
0x18000ad07  test    rax, rax
0x18000ad0a  jz      short loc_18000AD69
0x18000ad0c  mov     rcx, rax; pwk
0x18000ad0f  mov     r12d, ebx
0x18000ad12  call    cs:__imp_SubmitThreadpoolWork
0x18000ad18  jmp     def_18000AE91; jumptable 000000018000AE91 default case, case 2
0x18000ad1d  cmp     ebp, 8000h
0x18000ad23  jnz     loc_18000AE93
0x18000ad29  test    r14, r14
0x18000ad2c  jz      def_18000AE91; jumptable 000000018000AE91 default case, case 2
0x18000ad32  cmp     dword ptr [r8+4], 5
0x18000ad37  jnz     def_18000AE91; jumptable 000000018000AE91 default case, case 2
0x18000ad3d  lea     rcx, [r8+0Ch]; Buf1
0x18000ad41  mov     r8d, 10h; Size
0x18000ad47  lea     rdx, GUID_DEVINTERFACE_SMARTCARD; Buf2
0x18000ad4e  call    memcmp_0
0x18000ad53  test    eax, eax
0x18000ad55  jnz     def_18000AE91; jumptable 000000018000AE91 default case, case 2
0x18000ad5b  lea     rcx, [r14+1Ch]; pszSrc
0x18000ad5f  call    ScPnPSmartCardDeviceArrivalRegisterCallback
0x18000ad64  jmp     def_18000AE91; jumptable 000000018000AE91 default case, case 2
0x18000ad69  mov     rcx, cs:g_hHeap; hHeap
0x18000ad70  mov     r8, r14; lpMem
0x18000ad73  xor     edx, edx; dwFlags
0x18000ad75  call    cs:__imp_HeapFree
0x18000ad7b  call    cs:__imp_GetLastError
0x18000ad81  mov     r12d, eax
0x18000ad84  jmp     def_18000AE91; jumptable 000000018000AE91 default case, case 2
0x18000ad89  mov     rcx, cs:g_hCertPropStatus; hServiceStatus
0x18000ad90  lea     rdx, ServiceStatus; lpServiceStatus
0x18000ad97  mov     qword ptr cs:ServiceStatus.dwControlsAccepted, 85h
0x18000ada2  mov     cs:ServiceStatus.dwCurrentState, 3
0x18000adac  mov     cs:ServiceStatus.dwWaitHint, ebx
0x18000adb2  call    cs:__imp_SetServiceStatus
0x18000adb8  test    eax, eax
0x18000adba  jnz     short loc_18000ADC2
0x18000adbc  call    cs:__imp_GetLastError
0x18000adc2  mov     rcx, cs:g_hCertPropStopEvent; hEvent
0x18000adc9  call    cs:__imp_SetEvent
0x18000adcf  jmp     def_18000AE91; jumptable 000000018000AE91 default case, case 2
0x18000add4  movsxd  rax, r8d
0x18000add7  mov     edx, r8d
0x18000adda  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, edx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000ade0  mov     rva ?ThreadTable@?1??WppTraceIndent@@9@9[rsi+rax*8], r9d; `WppTraceIndent'::`2'::ThreadTable ...
0x18000ade8  mov     rva dword_180031404[rsi+rax*8], ebx
0x18000adef  jmp     loc_18000AA67
0x18000adf4  movsxd  rax, r8d
0x18000adf7  mov     ecx, r8d
0x18000adfa  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ecx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000ae00  mov     rva ?ThreadTable@?1??WppTraceIndent@@9@9[rsi+rax*8], r9d; `WppTraceIndent'::`2'::ThreadTable ...
0x18000ae08  mov     rva dword_180031404[rsi+rax*8], ebx
0x18000ae0f  jmp     loc_18000AB6B
0x18000ae14  cmp     byte ptr [rax+19h], 5
0x18000ae18  jb      loc_18000AAA4
0x18000ae1e  cmp     ebx, edi
0x18000ae20  jl      loc_18000AAA4
0x18000ae26  lea     r8, pszSrc; ".."
0x18000ae2d  call    StringCbCatA
0x18000ae32  test    eax, eax
0x18000ae34  jnz     loc_18000AAA4
0x18000ae3a  inc     edi
0x18000ae3c  cmp     edi, ebx
0x18000ae3e  jle     short loc_18000AE26
0x18000ae40  jmp     loc_18000AAA4
0x18000ae45  test    byte ptr [rcx+1Ch], 1
0x18000ae49  jz      loc_18000AAD5
0x18000ae4f  cmp     byte ptr [rcx+19h], 4
0x18000ae53  jb      loc_18000AAD5
0x18000ae59  mov     rcx, [rcx+10h]
0x18000ae5d  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18000ae64  mov     edx, 4Ah ; 'J'
0x18000ae69  mov     [rsp+68h+var_48], r13d
0x18000ae6e  mov     r9, r10
0x18000ae71  call    WPP_SF_sD
0x18000ae76  jmp     loc_18000AAD5
0x18000ae7b  lea     eax, [rdx-1]; switch 8 cases
0x18000ae7e  cmp     eax, 7
0x18000ae81  ja      def_18000AE91; jumptable 000000018000AE91 default case, case 2
0x18000ae87  mov     eax, ds:(jpt_18000AE91 - 180000000h)[rsi+rax*4]
0x18000ae8e  add     rax, rsi
0x18000ae91  jmp     rax; switch jump
0x18000ae93  mov     eax, ebp
0x18000ae95  sub     eax, 8001h
0x18000ae9a  jz      short loc_18000AEAC
0x18000ae9c  sub     eax, edi
0x18000ae9e  jz      short loc_18000AEAC
0x18000aea0  sub     eax, edi
0x18000aea2  jz      short loc_18000AEAC
0x18000aea4  cmp     eax, edi
0x18000aea6  jnz     def_18000AE91; jumptable 000000018000AE91 default case, case 2
0x18000aeac  test    r14, r14
0x18000aeaf  jz      def_18000AE91; jumptable 000000018000AE91 default case, case 2
0x18000aeb5  cmp     dword ptr [r8+4], 6
0x18000aeba  jnz     def_18000AE91; jumptable 000000018000AE91 default case, case 2
0x18000aec0  mov     rdx, [r8+18h]
0x18000aec4  mov     ecx, ebp
0x18000aec6  call    ScPnPHandleQueryRemovalRegisterCallback
0x18000aecb  mov     r12d, eax
0x18000aece  test    eax, eax
0x18000aed0  jz      def_18000AE91; jumptable 000000018000AE91 default case, case 2
0x18000aed6  mov     edx, 2
0x18000aedb  call    WppTraceIndent
0x18000aee0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aee7  cmp     rcx, r15
0x18000aeea  jz      def_18000AE91; jumptable 000000018000AE91 default case, case 2
0x18000aef0  test    [rcx+1Ch], dil
0x18000aef4  jz      def_18000AE91; jumptable 000000018000AE91 default case, case 2
0x18000aefa  cmp     byte ptr [rcx+19h], 2
0x18000aefe  jb      def_18000AE91; jumptable 000000018000AE91 default case, case 2
0x18000af04  mov     r9, cs:WPP_pszIndent
0x18000af0b  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18000af12  mov     rcx, [rcx+10h]
0x18000af16  mov     edx, 4Bh ; 'K'
0x18000af1b  mov     [rsp+68h+var_48], r12d
0x18000af20  call    WPP_SF_sD
0x18000af25  jmp     def_18000AE91; jumptable 000000018000AE91 default case, case 2
0x18000af2a  cmp     byte ptr [rax+19h], 5
0x18000af2e  jb      loc_18000ABA8
0x18000af34  cmp     ebx, edi
0x18000af36  jl      loc_18000ABA8
  ... truncated ...
```
