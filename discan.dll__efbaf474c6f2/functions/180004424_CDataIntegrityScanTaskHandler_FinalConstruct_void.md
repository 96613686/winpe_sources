# CDataIntegrityScanTaskHandler::FinalConstruct(void)

- ea: `0x180004424`
- end: `0x1800048a6`
- name: `?FinalConstruct@CDataIntegrityScanTaskHandler@@QEAAJXZ`
- size: `1154`
- prototype: `__int64 __fastcall(char *pv)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800036b4`
- `0x1800037e8`

## callees

- `0x1800032f8`
- `0x180004424`
- `0x180006688`
- `0x1800068b4`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1800044d9`
- `KERNEL32!CreateEventW` at `0x180004545`
- `KERNEL32!CreateEventW` at `0x1800045c8`
- `KERNEL32!CreateEventW` at `0x180004637`
- `KERNEL32!CreateEventW` at `0x1800044d9`
- `KERNEL32!CreateEventW` at `0x180004545`
- `KERNEL32!CreateEventW` at `0x1800045c8`
- `KERNEL32!CreateEventW` at `0x180004637`
- `KERNEL32!GetLastError` at `0x1800044e8`
- `KERNEL32!GetLastError` at `0x180004554`
- `KERNEL32!GetLastError` at `0x1800045d7`
- `KERNEL32!GetLastError` at `0x180004646`
- `KERNEL32!GetLastError` at `0x1800046bb`
- `KERNEL32!GetLastError` at `0x180004730`
- `KERNEL32!GetLastError` at `0x1800047aa`
- `KERNEL32!GetLastError` at `0x180004830`
- `KERNEL32!GetLastError` at `0x1800044e8`
- `KERNEL32!GetLastError` at `0x180004554`
- `KERNEL32!GetLastError` at `0x1800045d7`
- `KERNEL32!GetLastError` at `0x180004646`
- `KERNEL32!GetLastError` at `0x1800046bb`
- `KERNEL32!GetLastError` at `0x180004730`
- `KERNEL32!GetLastError` at `0x1800047aa`
- `KERNEL32!GetLastError` at `0x180004830`
- `KERNEL32!CreateThreadpoolWork` at `0x1800046a9`
- `KERNEL32!CreateThreadpoolWork` at `0x18000471e`
- `KERNEL32!CreateThreadpoolWork` at `0x1800046a9`
- `KERNEL32!CreateThreadpoolWork` at `0x18000471e`
- `KERNEL32!CreateEventExW` at `0x180004798`
- `KERNEL32!CreateEventExW` at `0x180004798`
- `KERNEL32!CreateSemaphoreExW` at `0x18000481e`
- `KERNEL32!CreateSemaphoreExW` at `0x18000481e`

## string_xrefs

- `0x180004808`: `Global\discan_{9FEF8AB5-7238-44F3-A974-53D78F0844EA}_tasksem`
- `0x180004436`: `CDataIntegrityScanTaskHandler::FinalConstruct`
- `0x180004532`: `Hr = BOOL_HR( m_StopEvent.AttachEx( CreateEvent( NULL, TRUE, FALSE, NULL ) ) )`
- `0x18000459e`: `Hr = BOOL_HR( m_PauseEvent.AttachEx( CreateEvent( NULL, TRUE, FALSE, NULL ) ) )`
- `0x180004621`: `Hr = BOOL_HR( m_ScannerRundownCompleteEvent.AttachEx( CreateEvent( nullptr, TRUE, FALSE, nullptr ) ) )`
- `0x180004690`: `Hr = BOOL_HR( m_TaskCompletionEvent.AttachEx( CreateEvent( NULL, TRUE, FALSE, NULL ) ) )`
- `0x180004705`: `Hr = BOOL_HR( m_TaskStartWork.AttachEx( CreateThreadpoolWork( ScanTaskStartCallback, this, NULL ) ) )`
- `0x18000477a`: `Hr = BOOL_HR( m_TaskCompletedWork.AttachEx( CreateThreadpoolWork( ScanTaskCompletedCallback, this, NULL ) ) )`
- `0x1800047f4`: `Hr = BOOL_HR( m_RegularTaskHaltEvent.AttachEx( CreateEventEx( NULL, DiscanRegularTaskHaltEventName, CREATE_EVENT_MANUAL_RESET, EVENT_ALL_ACCESS ) ) )`
- `0x18000486e`: `Hr = BOOL_HR( m_TaskSemaphore.AttachEx( CreateSemaphoreEx( NULL, 1, 1, DiscanTaskSemaphoreName, 0, SEMAPHORE_ALL_ACCESS ) ) )`

## pseudocode

```c
__int64 __fastcall CDataIntegrityScanTaskHandler::FinalConstruct(char *pv)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  USHORT Length; // cx
  __int64 v4; // r8
  USHORT v5; // ax
  HANDLE EventW; // rax
  signed int v7; // eax
  signed int v8; // ebx
  _QWORD *v9; // rcx
  int v10; // edx
  const char *v11; // r9
  HANDLE v12; // rax
  signed int v13; // eax
  HANDLE v14; // rax
  signed int v15; // eax
  HANDLE v16; // rax
  signed int v17; // eax
  PTP_WORK ThreadpoolWork; // rax
  signed int v19; // eax
  PTP_WORK v20; // rax
  signed int v21; // eax
  HANDLE Event; // rax
  signed int v23; // eax
  HANDLE Semaphore; // rax
  signed int LastError; // eax
  const char *v27; // [rsp+30h] [rbp-28h] BYREF
  signed int v28; // [rsp+38h] [rbp-20h]
  USHORT v29; // [rsp+40h] [rbp-18h]
  USHORT v30; // [rsp+42h] [rbp-16h]
  int v31; // [rsp+44h] [rbp-14h]
  char *v32; // [rsp+48h] [rbp-10h]

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  Length = GlobalIndentString.Length;
  v27 = "CDataIntegrityScanTaskHandler::FinalConstruct";
  v4 = ThreadLocalStoragePointer[tls_index];
  *(_QWORD *)(v4 + 16) = "CDataIntegrityScanTaskHandler::FinalConstruct";
  v5 = Length;
  if ( ++*(_WORD *)(v4 + 8) < Length )
  {
    v5 = *(_WORD *)(v4 + 8);
    Length = v5;
  }
  v29 = v5;
  v31 = 0;
  v32 = off_180047060;
  v30 = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CDataIntegrityScanTaskHandler::FinalConstruct");
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)pv + 9) = EventW;
  if ( EventW )
  {
    v12 = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)pv + 11) = v12;
    if ( v12 )
    {
      v14 = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)pv + 15) = v14;
      if ( v14 )
      {
        v16 = CreateEventW(0, 1, 0, 0);
        *((_QWORD *)pv + 13) = v16;
        if ( v16 )
        {
          ThreadpoolWork = CreateThreadpoolWork(CDataIntegrityScanTaskHandler::ScanTaskStartCallback, pv, 0);
          *((_QWORD *)pv + 31) = ThreadpoolWork;
          if ( ThreadpoolWork )
          {
            v20 = CreateThreadpoolWork(CDataIntegrityScanTaskHandler::ScanTaskCompletedCallback, pv, 0);
            *((_QWORD *)pv + 33) = v20;
            if ( v20 )
            {
              Event = CreateEventExW(0, L"Global\\discan_{9FEF8AB5-7238-44F3-A974-53D78F0844EA}_halt", 1u, 0x1F0003u);
              *((_QWORD *)pv + 19) = Event;
              if ( Event )
              {
                Semaphore = CreateSemaphoreExW(
                              0,
                              1,
                              1,
                              L"Global\\discan_{9FEF8AB5-7238-44F3-A974-53D78F0844EA}_tasksem",
                              0,
                              0x1F0003u);
                *((_QWORD *)pv + 28) = Semaphore;
                if ( Semaphore )
                {
                  *(_OWORD *)(pv + 408) = 0;
                  *((_QWORD *)pv + 53) = 0;
                  v8 = 0;
                  v28 = 0;
                  goto LABEL_81;
                }
                LastError = GetLastError();
                v8 = LastError;
                if ( LastError > 0 )
                  v8 = (unsigned __int16)LastError | 0x80070000;
                if ( v8 >= 0 )
                  v8 = -2147467259;
                v28 = v8;
                v9 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v10 = 17;
                  v11 = "Hr = BOOL_HR( m_TaskSemaphore.AttachEx( CreateSemaphoreEx( NULL, 1, 1, DiscanTaskSemaphoreName, "
                        "0, SEMAPHORE_ALL_ACCESS ) ) )";
                  goto LABEL_25;
                }
              }
              else
              {
                v23 = GetLastError();
                v8 = v23;
                if ( v23 > 0 )
                  v8 = (unsigned __int16)v23 | 0x80070000;
                if ( v8 >= 0 )
                  v8 = -2147467259;
                v28 = v8;
                v9 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v10 = 16;
                  v11 = "Hr = BOOL_HR( m_RegularTaskHaltEvent.AttachEx( CreateEventEx( NULL, DiscanRegularTaskHaltEventNa"
                        "me, CREATE_EVENT_MANUAL_RESET, EVENT_ALL_ACCESS ) ) )";
                  goto LABEL_25;
                }
              }
            }
            else
            {
              v21 = GetLastError();
              v8 = v21;
              if ( v21 > 0 )
                v8 = (unsigned __int16)v21 | 0x80070000;
              if ( v8 >= 0 )
                v8 = -2147467259;
              v28 = v8;
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v10 = 15;
                v11 = "Hr = BOOL_HR( m_TaskCompletedWork.AttachEx( CreateThreadpoolWork( ScanTaskCompletedCallback, this, NULL ) ) )";
                goto LABEL_25;
              }
            }
          }
          else
          {
            v19 = GetLastError();
            v8 = v19;
            if ( v19 > 0 )
              v8 = (unsigned __int16)v19 | 0x80070000;
            if ( v8 >= 0 )
              v8 = -2147467259;
            v28 = v8;
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v10 = 14;
              v11 = "Hr = BOOL_HR( m_TaskStartWork.AttachEx( CreateThreadpoolWork( ScanTaskStartCallback, this, NULL ) ) )";
              goto LABEL_25;
            }
          }
        }
        else
        {
          v17 = GetLastError();
          v8 = v17;
          if ( v17 > 0 )
            v8 = (unsigned __int16)v17 | 0x80070000;
          if ( v8 >= 0 )
            v8 = -2147467259;
          v28 = v8;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v10 = 13;
            v11 = "Hr = BOOL_HR( m_TaskCompletionEvent.AttachEx( CreateEvent( NULL, TRUE, FALSE, NULL ) ) )";
            goto LABEL_25;
          }
        }
      }
      else
      {
        v15 = GetLastError();
        v8 = v15;
        if ( v15 > 0 )
          v8 = (unsigned __int16)v15 | 0x80070000;
        if ( v8 >= 0 )
          v8 = -2147467259;
        v28 = v8;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = 12;
          v11 = "Hr = BOOL_HR( m_ScannerRundownCompleteEvent.AttachEx( CreateEvent( nullptr, TRUE, FALSE, nullptr ) ) )";
          goto LABEL_25;
        }
      }
    }
    else
    {
      v13 = GetLastError();
      v8 = v13;
      if ( v13 > 0 )
        v8 = (unsigned __int16)v13 | 0x80070000;
      if ( v8 >= 0 )
        v8 = -2147467259;
      v28 = v8;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 11;
        v11 = "Hr = BOOL_HR( m_PauseEvent.AttachEx( CreateEvent( NULL, TRUE, FALSE, NULL ) ) )";
        goto LABEL_25;
      }
    }
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    v28 = v8;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 10;
      v11 = "Hr = BOOL_HR( m_StopEvent.AttachEx( CreateEvent( NULL, TRUE, FALSE, NULL ) ) )";
LABEL_25:
      WPP_SF_sd(v9[2], v10, (unsigned int)&WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids, (_DWORD)v11, v8);
    }
  }
LABEL_81:
  CHResultImp::~CHResultImp((CHResultImp *)&v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180004424  push    rbp
0x180004426  push    rbx
0x180004427  push    rsi
0x180004428  push    rdi
0x180004429  mov     rbp, rsp
0x18000442c  sub     rsp, 58h
0x180004430  mov     edx, cs:_tls_index
0x180004436  lea     r9, aCdataintegrity_4; "CDataIntegrityScanTaskHandler::FinalCon"...
0x18000443d  mov     rax, gs:58h
0x180004446  mov     rbx, rcx
0x180004449  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180004450  mov     edi, 1
0x180004455  mov     [rbp+var_28], r9
0x180004459  mov     r8, [rax+rdx*8]
0x18000445d  mov     eax, 10h
0x180004462  mov     edx, 8
0x180004467  mov     [rax+r8], r9
0x18000446b  movzx   eax, cx
0x18000446e  add     [rdx+r8], di
0x180004473  movzx   edx, word ptr [rdx+r8]
0x180004478  cmp     dx, cx
0x18000447b  cmovb   ax, dx
0x18000447f  cmovb   cx, dx
0x180004483  mov     [rbp+var_18], ax
0x180004487  xor     eax, eax
0x180004489  mov     [rbp+var_14], eax
0x18000448c  mov     rax, cs:off_180047060; "                                       "...
0x180004493  mov     [rbp+var_10], rax
0x180004497  mov     [rbp+var_16], cx
0x18000449b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044a2  lea     rsi, WPP_GLOBAL_Control
0x1800044a9  cmp     rcx, rsi
0x1800044ac  jz      short loc_1800044CF
0x1800044ae  test    [rcx+1Ch], dil
0x1800044b2  jz      short loc_1800044CF
0x1800044b4  cmp     byte ptr [rcx+19h], 5
0x1800044b8  jb      short loc_1800044CF
0x1800044ba  mov     rcx, [rcx+10h]; LoggerHandle
0x1800044be  lea     edx, [rdi+0Ch]
0x1800044c1  mov     qword ptr [rsp+58h+dwFlags], r9; __int64
0x1800044c6  lea     r9, [rbp+var_18]
0x1800044ca  call    WPP_SF_aZs
0x1800044cf  xor     r9d, r9d; lpName
0x1800044d2  xor     r8d, r8d; bInitialState
0x1800044d5  mov     edx, edi; bManualReset
0x1800044d7  xor     ecx, ecx; lpEventAttributes
0x1800044d9  call    cs:__imp_CreateEventW
0x1800044df  mov     [rbx+48h], rax
0x1800044e3  test    rax, rax
0x1800044e6  jnz     short loc_18000453B
0x1800044e8  call    cs:__imp_GetLastError
0x1800044ee  mov     ebx, eax
0x1800044f0  test    eax, eax
0x1800044f2  jle     short loc_1800044FD
0x1800044f4  movzx   ebx, ax
0x1800044f7  or      ebx, 80070000h
0x1800044fd  test    ebx, ebx
0x1800044ff  js      short loc_180004506
0x180004501  mov     ebx, 80004005h
0x180004506  mov     [rbp+var_20], ebx
0x180004509  mov     rcx, cs:WPP_GLOBAL_Control
0x180004510  cmp     rcx, rsi
0x180004513  jz      loc_180004892
0x180004519  test    [rcx+1Ch], dil
0x18000451d  jz      loc_180004892
0x180004523  cmp     byte ptr [rcx+19h], 2
0x180004527  jb      loc_180004892
0x18000452d  mov     edx, 0Ah
0x180004532  lea     r9, aHrBoolHrMStope; "Hr = BOOL_HR( m_StopEvent.AttachEx( Cre"...
0x180004539  jmp     short loc_1800045A5
0x18000453b  xor     r9d, r9d; lpName
0x18000453e  xor     r8d, r8d; bInitialState
0x180004541  mov     edx, edi; bManualReset
0x180004543  xor     ecx, ecx; lpEventAttributes
0x180004545  call    cs:__imp_CreateEventW
0x18000454b  mov     [rbx+58h], rax
0x18000454f  test    rax, rax
0x180004552  jnz     short loc_1800045BE
0x180004554  call    cs:__imp_GetLastError
0x18000455a  mov     ebx, eax
0x18000455c  test    eax, eax
0x18000455e  jle     short loc_180004569
0x180004560  movzx   ebx, ax
0x180004563  or      ebx, 80070000h
0x180004569  test    ebx, ebx
0x18000456b  js      short loc_180004572
0x18000456d  mov     ebx, 80004005h
0x180004572  mov     [rbp+var_20], ebx
0x180004575  mov     rcx, cs:WPP_GLOBAL_Control
0x18000457c  cmp     rcx, rsi
0x18000457f  jz      loc_180004892
0x180004585  test    [rcx+1Ch], dil
0x180004589  jz      loc_180004892
0x18000458f  cmp     byte ptr [rcx+19h], 2
0x180004593  jb      loc_180004892
0x180004599  mov     edx, 0Bh
0x18000459e  lea     r9, aHrBoolHrMPause; "Hr = BOOL_HR( m_PauseEvent.AttachEx( Cr"...
0x1800045a5  mov     rcx, [rcx+10h]
0x1800045a9  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x1800045b0  mov     [rsp+58h+dwFlags], ebx
0x1800045b4  call    WPP_SF_sd
0x1800045b9  jmp     loc_180004892
0x1800045be  xor     r9d, r9d; lpName
0x1800045c1  xor     r8d, r8d; bInitialState
0x1800045c4  mov     edx, edi; bManualReset
0x1800045c6  xor     ecx, ecx; lpEventAttributes
0x1800045c8  call    cs:__imp_CreateEventW
0x1800045ce  mov     [rbx+78h], rax
0x1800045d2  test    rax, rax
0x1800045d5  jnz     short loc_18000462D
0x1800045d7  call    cs:__imp_GetLastError
0x1800045dd  mov     ebx, eax
0x1800045df  test    eax, eax
0x1800045e1  jle     short loc_1800045EC
0x1800045e3  movzx   ebx, ax
0x1800045e6  or      ebx, 80070000h
0x1800045ec  test    ebx, ebx
0x1800045ee  js      short loc_1800045F5
0x1800045f0  mov     ebx, 80004005h
0x1800045f5  mov     [rbp+var_20], ebx
0x1800045f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045ff  cmp     rcx, rsi
0x180004602  jz      loc_180004892
0x180004608  test    [rcx+1Ch], dil
0x18000460c  jz      loc_180004892
0x180004612  cmp     byte ptr [rcx+19h], 2
0x180004616  jb      loc_180004892
0x18000461c  mov     edx, 0Ch
0x180004621  lea     r9, aHrBoolHrMScann; "Hr = BOOL_HR( m_ScannerRundownCompleteE"...
0x180004628  jmp     loc_1800045A5
0x18000462d  xor     r9d, r9d; lpName
0x180004630  xor     r8d, r8d; bInitialState
0x180004633  mov     edx, edi; bManualReset
0x180004635  xor     ecx, ecx; lpEventAttributes
0x180004637  call    cs:__imp_CreateEventW
0x18000463d  mov     [rbx+68h], rax
0x180004641  test    rax, rax
0x180004644  jnz     short loc_18000469C
0x180004646  call    cs:__imp_GetLastError
0x18000464c  mov     ebx, eax
0x18000464e  test    eax, eax
0x180004650  jle     short loc_18000465B
0x180004652  movzx   ebx, ax
0x180004655  or      ebx, 80070000h
0x18000465b  test    ebx, ebx
0x18000465d  js      short loc_180004664
0x18000465f  mov     ebx, 80004005h
0x180004664  mov     [rbp+var_20], ebx
0x180004667  mov     rcx, cs:WPP_GLOBAL_Control
0x18000466e  cmp     rcx, rsi
0x180004671  jz      loc_180004892
0x180004677  test    [rcx+1Ch], dil
0x18000467b  jz      loc_180004892
0x180004681  cmp     byte ptr [rcx+19h], 2
0x180004685  jb      loc_180004892
0x18000468b  mov     edx, 0Dh
0x180004690  lea     r9, aHrBoolHrMTaskc; "Hr = BOOL_HR( m_TaskCompletionEvent.Att"...
0x180004697  jmp     loc_1800045A5
0x18000469c  xor     r8d, r8d; pcbe
0x18000469f  lea     rcx, ?ScanTaskStartCallback@CDataIntegrityScanTaskHandler@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800046a6  mov     rdx, rbx; pv
0x1800046a9  call    cs:__imp_CreateThreadpoolWork
0x1800046af  mov     [rbx+0F8h], rax
0x1800046b6  test    rax, rax
0x1800046b9  jnz     short loc_180004711
0x1800046bb  call    cs:__imp_GetLastError
0x1800046c1  mov     ebx, eax
0x1800046c3  test    eax, eax
0x1800046c5  jle     short loc_1800046D0
0x1800046c7  movzx   ebx, ax
0x1800046ca  or      ebx, 80070000h
0x1800046d0  test    ebx, ebx
0x1800046d2  js      short loc_1800046D9
0x1800046d4  mov     ebx, 80004005h
0x1800046d9  mov     [rbp+var_20], ebx
0x1800046dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046e3  cmp     rcx, rsi
0x1800046e6  jz      loc_180004892
0x1800046ec  test    [rcx+1Ch], dil
0x1800046f0  jz      loc_180004892
0x1800046f6  cmp     byte ptr [rcx+19h], 2
0x1800046fa  jb      loc_180004892
0x180004700  mov     edx, 0Eh
0x180004705  lea     r9, aHrBoolHrMTasks_0; "Hr = BOOL_HR( m_TaskStartWork.AttachEx("...
0x18000470c  jmp     loc_1800045A5
0x180004711  xor     r8d, r8d; pcbe
0x180004714  lea     rcx, ?ScanTaskCompletedCallback@CDataIntegrityScanTaskHandler@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000471b  mov     rdx, rbx; pv
0x18000471e  call    cs:__imp_CreateThreadpoolWork
0x180004724  mov     [rbx+108h], rax
0x18000472b  test    rax, rax
0x18000472e  jnz     short loc_180004786
0x180004730  call    cs:__imp_GetLastError
0x180004736  mov     ebx, eax
0x180004738  test    eax, eax
0x18000473a  jle     short loc_180004745
0x18000473c  movzx   ebx, ax
0x18000473f  or      ebx, 80070000h
0x180004745  test    ebx, ebx
0x180004747  js      short loc_18000474E
0x180004749  mov     ebx, 80004005h
0x18000474e  mov     [rbp+var_20], ebx
0x180004751  mov     rcx, cs:WPP_GLOBAL_Control
0x180004758  cmp     rcx, rsi
0x18000475b  jz      loc_180004892
0x180004761  test    [rcx+1Ch], dil
0x180004765  jz      loc_180004892
0x18000476b  cmp     byte ptr [rcx+19h], 2
0x18000476f  jb      loc_180004892
0x180004775  mov     edx, 0Fh
0x18000477a  lea     r9, aHrBoolHrMTaskc_0; "Hr = BOOL_HR( m_TaskCompletedWork.Attac"...
0x180004781  jmp     loc_1800045A5
0x180004786  mov     r9d, 1F0003h; dwDesiredAccess
0x18000478c  lea     rdx, Name; "Global\\discan_{9FEF8AB5-7238-44F3-A974"...
0x180004793  mov     r8d, edi; dwFlags
0x180004796  xor     ecx, ecx; lpEventAttributes
0x180004798  call    cs:__imp_CreateEventExW
0x18000479e  mov     [rbx+98h], rax
0x1800047a5  test    rax, rax
0x1800047a8  jnz     short loc_180004800
0x1800047aa  call    cs:__imp_GetLastError
0x1800047b0  mov     ebx, eax
0x1800047b2  test    eax, eax
0x1800047b4  jle     short loc_1800047BF
0x1800047b6  movzx   ebx, ax
0x1800047b9  or      ebx, 80070000h
0x1800047bf  test    ebx, ebx
0x1800047c1  js      short loc_1800047C8
0x1800047c3  mov     ebx, 80004005h
0x1800047c8  mov     [rbp+var_20], ebx
0x1800047cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047d2  cmp     rcx, rsi
0x1800047d5  jz      loc_180004892
0x1800047db  test    [rcx+1Ch], dil
0x1800047df  jz      loc_180004892
0x1800047e5  cmp     byte ptr [rcx+19h], 2
0x1800047e9  jb      loc_180004892
0x1800047ef  mov     edx, 10h
0x1800047f4  lea     r9, aHrBoolHrMRegul; "Hr = BOOL_HR( m_RegularTaskHaltEvent.At"...
0x1800047fb  jmp     loc_1800045A5
0x180004800  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004808  lea     r9, aGlobalDiscan9f; "Global\\discan_{9FEF8AB5-7238-44F3-A974"...
0x18000480f  mov     r8d, edi; lMaximumCount
0x180004812  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18000481a  mov     edx, edi; lInitialCount
0x18000481c  xor     ecx, ecx; lpSemaphoreAttributes
0x18000481e  call    cs:__imp_CreateSemaphoreExW
0x180004824  mov     [rbx+0E0h], rax
0x18000482b  test    rax, rax
0x18000482e  jnz     short loc_18000487A
0x180004830  call    cs:__imp_GetLastError
0x180004836  mov     ebx, eax
0x180004838  test    eax, eax
0x18000483a  jle     short loc_180004845
0x18000483c  movzx   ebx, ax
0x18000483f  or      ebx, 80070000h
0x180004845  test    ebx, ebx
0x180004847  js      short loc_18000484E
0x180004849  mov     ebx, 80004005h
0x18000484e  mov     [rbp+var_20], ebx
0x180004851  mov     rcx, cs:WPP_GLOBAL_Control
0x180004858  cmp     rcx, rsi
0x18000485b  jz      short loc_180004892
0x18000485d  test    [rcx+1Ch], dil
0x180004861  jz      short loc_180004892
0x180004863  cmp     byte ptr [rcx+19h], 2
0x180004867  jb      short loc_180004892
0x180004869  mov     edx, 11h
0x18000486e  lea     r9, aHrBoolHrMTasks; "Hr = BOOL_HR( m_TaskSemaphore.AttachEx("...
0x180004875  jmp     loc_1800045A5
0x18000487a  xor     eax, eax
0x18000487c  xorps   xmm0, xmm0
0x18000487f  movups  xmmword ptr [rbx+198h], xmm0
0x180004886  mov     [rbx+1A8h], rax
0x18000488d  xor     ebx, ebx
0x18000488f  mov     [rbp+var_20], eax
0x180004892  lea     rcx, [rbp+var_28]; this
0x180004896  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18000489b  mov     eax, ebx
0x18000489d  add     rsp, 58h
0x1800048a1  pop     rdi
0x1800048a2  pop     rsi
0x1800048a3  pop     rbx
0x1800048a4  pop     rbp
0x1800048a5  retn
```
