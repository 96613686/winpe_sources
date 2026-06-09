# MsiBeginTransactionW

- ea: `0x1801a24f0`
- end: `0x1801a29ab`
- name: `MsiBeginTransactionW`
- size: `1211`
- prototype: `UINT __stdcall(LPCWSTR szName, DWORD dwTransactionAttributes, MSIHANDLE *phTransactionHandle, HANDLE *phChangeOfOwnerEvent)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1801a23b0`

## callees

- `0x180005af8`
- `0x18000c4bc`
- `0x18000ca3c`
- `0x18000d6d8`
- `0x180010ac0`
- `0x1800141e0`
- `0x180018ee0`
- `0x180019cc0`
- `0x18006dc80`
- `0x18012b2c0`
- `0x180148a10`
- `0x1801a24f0`
- `0x1801d6748`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x1801a2656`
- `KERNEL32!OpenEventW` at `0x1801a26eb`
- `KERNEL32!OpenEventW` at `0x1801a2656`
- `KERNEL32!OpenEventW` at `0x1801a26eb`
- `KERNEL32!CreateEventW` at `0x1801a27bb`
- `KERNEL32!CreateEventW` at `0x1801a27d4`
- `KERNEL32!CreateEventW` at `0x1801a27bb`
- `KERNEL32!CreateEventW` at `0x1801a27d4`
- `KERNEL32!CreateThread` at `0x1801a2840`
- `KERNEL32!CreateThread` at `0x1801a2840`

## string_xrefs

- `0x1801a2551`: `Entering MsiBeginTransactionW. szTransactionName: %s, dwTransactionAttributes: %d`
- `0x1801a26bb`: `Error occurred in string function, unable to create end transaction event.`
- `0x1801a2724`: `Error occured opening event: %s`
- `0x1801a290a`: `Error occured opening event: %s`
- `0x1801a2780`: `Error occurred in string function, unable to create ack event.`
- `0x1801a2890`: `Error occurred creating cleanup EEUI on change of owner thread.`

## pseudocode

```c
UINT __stdcall MsiBeginTransactionW(
        LPCWSTR szName,
        DWORD dwTransactionAttributes,
        MSIHANDLE *phTransactionHandle,
        HANDLE *phChangeOfOwnerEvent)
{
  const unsigned __int16 *v8; // rax
  int v9; // eax
  struct IMsiServer *MsiServer; // rax
  UINT v12; // r14d
  HANDLE v13; // r12
  WCHAR *v14; // rax
  const unsigned __int16 *v15; // r9
  HANDLE EventW; // rsi
  HANDLE v17; // rdi
  _QWORD *v18; // rax
  void *v19; // rbx
  HANDLE Thread; // rax
  int v21; // ebx
  bool v22[8]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v23; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v25[264]; // [rsp+280h] [rbp+180h] BYREF

  v23 = 0;
  if ( g_dmDiagnosticMode )
  {
    v8 = szName;
    if ( !szName )
      v8 = L"(null)";
    DebugString(
      9,
      0,
      0,
      L"Entering MsiBeginTransactionW. szTransactionName: %s, dwTransactionAttributes: %d",
      v8,
      (const unsigned __int16 *)dwTransactionAttributes,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  }
  if ( (int)StringCchLengthW(szName, 0x7FFFFFFFu, &v23) < 0
    || !szName
    || !v23
    || !phTransactionHandle
    || !phChangeOfOwnerEvent
    || dwTransactionAttributes > 1 )
  {
    return 87;
  }
  v9 = ((__int64 (__fastcall *)(_QWORD))OLE32::CoInitialize)(0);
  if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147417850 )
    return 1603;
  v22[0] = v9 >= 0;
  MsiServer = CreateMsiServer();
  v23 = (unsigned __int64)MsiServer;
  if ( MsiServer )
  {
    v12 = (*(__int64 (__fastcall **)(struct IMsiServer *, LPCWSTR, _QWORD, MSIHANDLE *, WCHAR *))(*(_QWORD *)MsiServer
                                                                                                + 160LL))(
            MsiServer,
            szName,
            dwTransactionAttributes,
            phTransactionHandle,
            Name);
    v13 = OpenEventW(0x100000u, 0, Name);
    if ( v13 )
    {
      if ( (int)StringCchPrintfW(v25, 0x105u, L"%s%s", Name, L"ET") >= 0 )
      {
        g_hEndTransactionEvent = OpenEventW(0x100000u, 0, v25);
        if ( !g_hEndTransactionEvent && g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"Error occured opening event: %s",
            v25,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        if ( (int)StringCchCatW(Name, 0x105u, L"Reset") < 0 )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              L"Error occurred in string function, unable to create ack event.",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          goto LABEL_40;
        }
        EventW = CreateEventW(0, 0, 0, Name);
        v17 = CreateEventW(0, 0, 0, 0);
        if ( !v17 || !EventW )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              L"Error occured creating event",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          goto LABEL_40;
        }
        if ( LoadServices() )
        {
          *phChangeOfOwnerEvent = v17;
          v18 = operator new(0x18u);
          v19 = v18;
          if ( v18 )
          {
            *v18 = v13;
            v18[2] = v17;
            v18[1] = EventW;
            Thread = CreateThread(0, 0, CleanupEEUIOnChangeOfOwnerThread, v18, 0, 0);
            g_hCleanupEEUIThread = Thread;
          }
          else
          {
            Thread = g_hCleanupEEUIThread;
          }
          if ( Thread )
            goto LABEL_40;
          operator delete(v19);
          FreeServices();
          if ( !g_dmDiagnosticMode )
            goto LABEL_40;
          v14 = (WCHAR *)L"(NULL)";
          v15 = L"Error occurred creating cleanup EEUI on change of owner thread.";
          goto LABEL_39;
        }
        v12 = 14;
      }
      else if ( g_dmDiagnosticMode )
      {
        v14 = (WCHAR *)L"(NULL)";
        v15 = L"Error occurred in string function, unable to create end transaction event.";
LABEL_39:
        DebugString(9, 0, 0, v15, v14, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
      }
    }
    else if ( g_dmDiagnosticMode )
    {
      v15 = L"Error occured opening event: %s";
      v14 = Name;
      goto LABEL_39;
    }
LABEL_40:
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v23);
    CCoUninitialize::~CCoUninitialize((CCoUninitialize *)v22);
    return v12;
  }
  v21 = InSafeMode() ? 0x33 : 0;
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v23);
  CCoUninitialize::~CCoUninitialize((CCoUninitialize *)v22);
  return v21 + 1601;
}

```

## disassembly

```asm
0x1801a24f0  push    rbp
0x1801a24f2  push    rbx
0x1801a24f3  push    rsi
0x1801a24f4  push    rdi
0x1801a24f5  push    r12
0x1801a24f7  push    r13
0x1801a24f9  push    r14
0x1801a24fb  push    r15
0x1801a24fd  lea     rbp, [rsp-3A8h]
0x1801a2505  sub     rsp, 4A8h
0x1801a250c  mov     rax, cs:__security_cookie
0x1801a2513  xor     rax, rsp
0x1801a2516  mov     [rbp+3E0h+var_50], rax
0x1801a251d  xor     r13d, r13d
0x1801a2520  mov     edi, edx
0x1801a2522  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801a2529  mov     rsi, r8
0x1801a252c  mov     r15, r9
0x1801a252f  mov     [rsp+4E0h+var_478], r13
0x1801a2534  mov     rbx, rcx
0x1801a2537  lea     r8, aNull; "(NULL)"
0x1801a253e  jz      short loc_1801A258D
0x1801a2540  mov     [rsp+4E0h+var_488], r13; void *
0x1801a2545  lea     rdx, aNull_4; "(null)"
0x1801a254c  mov     [rsp+4E0h+var_490], r13d; unsigned int
0x1801a2551  lea     r9, aEnteringMsibeg_0; "Entering MsiBeginTransactionW. szTransa"...
0x1801a2558  mov     [rsp+4E0h+var_498], r8; unsigned __int16 *
0x1801a255d  test    rcx, rcx
0x1801a2560  mov     [rsp+4E0h+var_4A0], r8; unsigned __int16 *
0x1801a2565  mov     rax, rcx
0x1801a2568  mov     [rsp+4E0h+var_4A8], r8; unsigned __int16 *
0x1801a256d  cmovz   rax, rdx
0x1801a2571  mov     [rsp+4E0h+var_4B0], r8; unsigned __int16 *
0x1801a2576  xor     edx, edx; unsigned __int16
0x1801a2578  mov     [rsp+4E0h+lpThreadId], rdi; unsigned __int16 *
0x1801a257d  xor     r8d, r8d; int
0x1801a2580  mov     qword ptr [rsp+4E0h+dwCreationFlags], rax; unsigned __int16 *
0x1801a2585  lea     ecx, [rdx+9]; int
0x1801a2588  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801a258d  lea     r8, [rsp+4E0h+var_478]; unsigned __int64 *
0x1801a2592  mov     edx, 7FFFFFFFh; unsigned __int64
0x1801a2597  mov     rcx, rbx; unsigned __int16 *
0x1801a259a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1801a259f  test    eax, eax
0x1801a25a1  js      loc_1801A2982
0x1801a25a7  test    rbx, rbx
0x1801a25aa  jz      loc_1801A2982
0x1801a25b0  cmp     [rsp+4E0h+var_478], r13
0x1801a25b5  jz      loc_1801A2982
0x1801a25bb  test    rsi, rsi
0x1801a25be  jz      loc_1801A2982
0x1801a25c4  test    r15, r15
0x1801a25c7  jz      loc_1801A2982
0x1801a25cd  cmp     edi, 1
0x1801a25d0  ja      loc_1801A2982
0x1801a25d6  mov     rax, cs:?CoInitialize@OLE32@@3P6AJPEAX@ZEA; long (*OLE32::CoInitialize)(void *)
0x1801a25dd  xor     ecx, ecx
0x1801a25df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a25e4  mov     edx, 80000000h
0x1801a25e9  lea     ecx, [rax+rdx]
0x1801a25ec  test    edx, ecx
0x1801a25ee  jnz     short loc_1801A2601
0x1801a25f0  cmp     eax, 80010106h
0x1801a25f5  jz      short loc_1801A2601
0x1801a25f7  mov     eax, 643h
0x1801a25fc  jmp     loc_1801A2987
0x1801a2601  shr     eax, 1Fh
0x1801a2604  xor     al, 1
0x1801a2606  mov     [rsp+4E0h+var_480], al
0x1801a260a  call    ?CreateMsiServer@@YAPEAUIMsiServer@@XZ; CreateMsiServer(void)
0x1801a260f  mov     [rsp+4E0h+var_478], rax
0x1801a2614  mov     r10, rax
0x1801a2617  test    rax, rax
0x1801a261a  jz      loc_1801A295A
0x1801a2620  mov     rcx, [rax]
0x1801a2623  mov     r9, rsi
0x1801a2626  mov     r8d, edi
0x1801a2629  mov     rdx, rbx
0x1801a262c  mov     rax, [rcx+0A0h]
0x1801a2633  lea     rcx, [rsp+4E0h+Name]
0x1801a2638  mov     qword ptr [rsp+4E0h+dwCreationFlags], rcx
0x1801a263d  mov     rcx, r10
0x1801a2640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a2645  mov     ebx, 100000h
0x1801a264a  lea     r8, [rsp+4E0h+Name]; lpName
0x1801a264f  mov     ecx, ebx; dwDesiredAccess
0x1801a2651  xor     edx, edx; bInheritHandle
0x1801a2653  mov     r14d, eax
0x1801a2656  call    cs:__imp_OpenEventW
0x1801a265d  nop     dword ptr [rax+rax+00h]
0x1801a2662  mov     r12, rax
0x1801a2665  test    rax, rax
0x1801a2668  jz      loc_1801A28F0
0x1801a266e  lea     rax, aEt; "ET"
0x1801a2675  mov     edi, 105h
0x1801a267a  mov     edx, edi; unsigned __int64
0x1801a267c  mov     qword ptr [rsp+4E0h+dwCreationFlags], rax
0x1801a2681  lea     r9, [rsp+4E0h+Name]
0x1801a2686  lea     r8, aSS_1; "%s%s"
0x1801a268d  lea     rcx, [rbp+3E0h+var_260]; unsigned __int16 *
0x1801a2694  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801a2699  test    eax, eax
0x1801a269b  jns     short loc_1801A26E0
0x1801a269d  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801a26a4  jz      loc_1801A2941
0x1801a26aa  mov     [rsp+4E0h+var_488], r13
0x1801a26af  lea     rax, aNull; "(NULL)"
0x1801a26b6  mov     [rsp+4E0h+var_490], r13d
0x1801a26bb  lea     r9, aErrorOccurredI; "Error occurred in string function, unab"...
0x1801a26c2  mov     [rsp+4E0h+var_498], rax
0x1801a26c7  mov     [rsp+4E0h+var_4A0], rax
0x1801a26cc  mov     [rsp+4E0h+var_4A8], rax
0x1801a26d1  mov     [rsp+4E0h+var_4B0], rax
0x1801a26d6  mov     [rsp+4E0h+lpThreadId], rax
0x1801a26db  jmp     loc_1801A292F
0x1801a26e0  lea     r8, [rbp+3E0h+var_260]; lpName
0x1801a26e7  xor     edx, edx; bInheritHandle
0x1801a26e9  mov     ecx, ebx; dwDesiredAccess
0x1801a26eb  call    cs:__imp_OpenEventW
0x1801a26f2  nop     dword ptr [rax+rax+00h]
0x1801a26f7  mov     cs:?g_hEndTransactionEvent@@3PEAXEA, rax; void * g_hEndTransactionEvent
0x1801a26fe  lea     rbx, aNull; "(NULL)"
0x1801a2705  test    rax, rax
0x1801a2708  jnz     short loc_1801A2756
0x1801a270a  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801a2711  jz      short loc_1801A2756
0x1801a2713  mov     [rsp+4E0h+var_488], r13; void *
0x1801a2718  lea     rax, [rbp+3E0h+var_260]
0x1801a271f  mov     [rsp+4E0h+var_490], r13d; unsigned int
0x1801a2724  lea     r9, aErrorOccuredOp; "Error occured opening event: %s"
0x1801a272b  mov     [rsp+4E0h+var_498], rbx; unsigned __int16 *
0x1801a2730  xor     edx, edx; unsigned __int16
0x1801a2732  mov     [rsp+4E0h+var_4A0], rbx; unsigned __int16 *
0x1801a2737  xor     r8d, r8d; int
0x1801a273a  mov     [rsp+4E0h+var_4A8], rbx; unsigned __int16 *
0x1801a273f  mov     [rsp+4E0h+var_4B0], rbx; unsigned __int16 *
0x1801a2744  mov     [rsp+4E0h+lpThreadId], rbx; unsigned __int16 *
0x1801a2749  lea     ecx, [rdx+9]; int
0x1801a274c  mov     qword ptr [rsp+4E0h+dwCreationFlags], rax; unsigned __int16 *
0x1801a2751  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801a2756  lea     r8, aReset; "Reset"
0x1801a275d  mov     rdx, rdi; unsigned __int64
0x1801a2760  lea     rcx, [rsp+4E0h+Name]; unsigned __int16 *
0x1801a2765  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801a276a  test    eax, eax
0x1801a276c  jns     short loc_1801A27AF
0x1801a276e  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801a2775  jz      loc_1801A2941
0x1801a277b  mov     [rsp+4E0h+var_488], r13
0x1801a2780  lea     r9, aErrorOccurredI_0; "Error occurred in string function, unab"...
0x1801a2787  mov     [rsp+4E0h+var_490], r13d
0x1801a278c  mov     [rsp+4E0h+var_498], rbx
0x1801a2791  mov     [rsp+4E0h+var_4A0], rbx
0x1801a2796  mov     [rsp+4E0h+var_4A8], rbx
0x1801a279b  mov     [rsp+4E0h+var_4B0], rbx
0x1801a27a0  mov     [rsp+4E0h+lpThreadId], rbx
0x1801a27a5  mov     qword ptr [rsp+4E0h+dwCreationFlags], rbx
0x1801a27aa  jmp     loc_1801A2934
0x1801a27af  lea     r9, [rsp+4E0h+Name]; lpName
0x1801a27b4  xor     r8d, r8d; bInitialState
0x1801a27b7  xor     edx, edx; bManualReset
0x1801a27b9  xor     ecx, ecx; lpEventAttributes
0x1801a27bb  call    cs:__imp_CreateEventW
0x1801a27c2  nop     dword ptr [rax+rax+00h]
0x1801a27c7  xor     r9d, r9d; lpName
0x1801a27ca  xor     r8d, r8d; bInitialState
0x1801a27cd  xor     edx, edx; bManualReset
0x1801a27cf  xor     ecx, ecx; lpEventAttributes
0x1801a27d1  mov     rsi, rax
0x1801a27d4  call    cs:__imp_CreateEventW
0x1801a27db  nop     dword ptr [rax+rax+00h]
0x1801a27e0  mov     rdi, rax
0x1801a27e3  test    rax, rax
0x1801a27e6  jz      loc_1801A28B2
0x1801a27ec  test    rsi, rsi
0x1801a27ef  jz      loc_1801A28B2
0x1801a27f5  call    ?LoadServices@@YAPEAVIMsiServices@@XZ; LoadServices(void)
0x1801a27fa  test    rax, rax
0x1801a27fd  jnz     short loc_1801A2808
0x1801a27ff  lea     r14d, [rax+0Eh]
0x1801a2803  jmp     loc_1801A2941
0x1801a2808  mov     ecx, 18h; unsigned __int64
0x1801a280d  mov     [r15], rdi
0x1801a2810  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801a2815  mov     rbx, rax
0x1801a2818  test    rax, rax
0x1801a281b  jz      short loc_1801A2855
0x1801a281d  mov     [rsp+4E0h+lpThreadId], r13; lpThreadId
0x1801a2822  lea     r8, ?CleanupEEUIOnChangeOfOwnerThread@@YAKPEAX@Z; lpStartAddress
0x1801a2829  mov     r9, rax; lpParameter
0x1801a282c  mov     [rsp+4E0h+dwCreationFlags], r13d; dwCreationFlags
0x1801a2831  xor     edx, edx; dwStackSize
0x1801a2833  mov     [rax], r12
0x1801a2836  xor     ecx, ecx; lpThreadAttributes
0x1801a2838  mov     [rax+10h], rdi
0x1801a283c  mov     [rax+8], rsi
0x1801a2840  call    cs:__imp_CreateThread
0x1801a2847  nop     dword ptr [rax+rax+00h]
0x1801a284c  mov     cs:?g_hCleanupEEUIThread@@3PEAXEA, rax; void * g_hCleanupEEUIThread
0x1801a2853  jmp     short loc_1801A285C
0x1801a2855  mov     rax, cs:?g_hCleanupEEUIThread@@3PEAXEA; void * g_hCleanupEEUIThread
0x1801a285c  test    rax, rax
0x1801a285f  jnz     loc_1801A2941
0x1801a2865  mov     rcx, rbx; void *
0x1801a2868  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801a286d  call    ?FreeServices@@YAHXZ; FreeServices(void)
0x1801a2872  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801a2879  jz      loc_1801A2941
0x1801a287f  mov     [rsp+4E0h+var_488], r13
0x1801a2884  lea     rax, aNull; "(NULL)"
0x1801a288b  mov     [rsp+4E0h+var_490], r13d
0x1801a2890  lea     r9, aErrorOccurredC; "Error occurred creating cleanup EEUI on"...
0x1801a2897  mov     [rsp+4E0h+var_498], rax
0x1801a289c  mov     [rsp+4E0h+var_4A0], rax
0x1801a28a1  mov     [rsp+4E0h+var_4A8], rax
0x1801a28a6  mov     [rsp+4E0h+var_4B0], rax
0x1801a28ab  mov     [rsp+4E0h+lpThreadId], rax
0x1801a28b0  jmp     short loc_1801A292F
0x1801a28b2  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801a28b9  jz      loc_1801A2941
0x1801a28bf  mov     [rsp+4E0h+var_488], r13
0x1801a28c4  lea     r9, aErrorOccuredCr_1; "Error occured creating event"
0x1801a28cb  mov     [rsp+4E0h+var_490], r13d
0x1801a28d0  mov     [rsp+4E0h+var_498], rbx
0x1801a28d5  mov     [rsp+4E0h+var_4A0], rbx
0x1801a28da  mov     [rsp+4E0h+var_4A8], rbx
0x1801a28df  mov     [rsp+4E0h+var_4B0], rbx
0x1801a28e4  mov     [rsp+4E0h+lpThreadId], rbx
0x1801a28e9  mov     qword ptr [rsp+4E0h+dwCreationFlags], rbx
0x1801a28ee  jmp     short loc_1801A2934
0x1801a28f0  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801a28f7  jz      short loc_1801A2941
0x1801a28f9  mov     [rsp+4E0h+var_488], r13; void *
0x1801a28fe  lea     rax, aNull; "(NULL)"
0x1801a2905  mov     [rsp+4E0h+var_490], r13d; unsigned int
0x1801a290a  lea     r9, aErrorOccuredOp; "Error occured opening event: %s"
0x1801a2911  mov     [rsp+4E0h+var_498], rax; unsigned __int16 *
0x1801a2916  mov     [rsp+4E0h+var_4A0], rax; unsigned __int16 *
0x1801a291b  mov     [rsp+4E0h+var_4A8], rax; unsigned __int16 *
0x1801a2920  mov     [rsp+4E0h+var_4B0], rax; unsigned __int16 *
0x1801a2925  mov     [rsp+4E0h+lpThreadId], rax; unsigned __int16 *
0x1801a292a  lea     rax, [rsp+4E0h+Name]
0x1801a292f  mov     qword ptr [rsp+4E0h+dwCreationFlags], rax; unsigned __int16 *
0x1801a2934  xor     edx, edx; unsigned __int16
0x1801a2936  xor     r8d, r8d; int
0x1801a2939  lea     ecx, [rdx+9]; int
0x1801a293c  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801a2941  lea     rcx, [rsp+4E0h+var_478]
0x1801a2946  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801a294b  lea     rcx, [rsp+4E0h+var_480]; this
0x1801a2950  call    ??1CCoUninitialize@@QEAA@XZ; CCoUninitialize::~CCoUninitialize(void)
0x1801a2955  mov     eax, r14d
0x1801a2958  jmp     short loc_1801A2987
0x1801a295a  call    ?InSafeMode@@YA_NXZ; InSafeMode(void)
0x1801a295f  neg     al
0x1801a2961  lea     rcx, [rsp+4E0h+var_478]
0x1801a2966  sbb     ebx, ebx
0x1801a2968  and     ebx, 33h
0x1801a296b  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801a2970  lea     rcx, [rsp+4E0h+var_480]; this
0x1801a2975  call    ??1CCoUninitialize@@QEAA@XZ; CCoUninitialize::~CCoUninitialize(void)
0x1801a297a  lea     eax, [rbx+641h]
0x1801a2980  jmp     short loc_1801A2987
0x1801a2982  mov     eax, 57h ; 'W'
0x1801a2987  mov     rcx, [rbp+3E0h+var_50]
0x1801a298e  xor     rcx, rsp; StackCookie
0x1801a2991  call    __security_check_cookie
0x1801a2996  add     rsp, 4A8h
0x1801a299d  pop     r15
0x1801a299f  pop     r14
0x1801a29a1  pop     r13
0x1801a29a3  pop     r12
0x1801a29a5  pop     rdi
0x1801a29a6  pop     rsi
0x1801a29a7  pop     rbx
0x1801a29a8  pop     rbp
0x1801a29a9  retn
```
