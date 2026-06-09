# PpfhRegisterEventLogProvider

- ea: `0x18003639c`
- end: `0x1800368e5`
- name: `PpfhRegisterEventLogProvider`
- size: `1353`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x1800351d0`

## callees

- `0x180003270`
- `0x180003cf0`
- `0x180009c64`
- `0x18000a66c`
- `0x18000c9a4`
- `0x18000dfe0`
- `0x18002d5ec`
- `0x180030944`
- `0x180033670`
- `0x18003639c`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x1800363e8`
- `ntdll!EtwEventRegister` at `0x1800363e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036684`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036684`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800364a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003666d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036800`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036866`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800368b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800364a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003666d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036800`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036866`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800368b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800364ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036814`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003687a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800368c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800364ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036814`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003687a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800368c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036564`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180036554`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180036554`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18003678f`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18003678f`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x1800367c9`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x1800367c9`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180036749`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180036749`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 PpfhRegisterEventLogProvider()
{
  unsigned int v0; // eax
  int IsOSWinPEBased; // eax
  signed int AssociatedOSPathInWinPEBasedOS; // ebx
  unsigned __int16 **v4; // rax
  __int64 v5; // rdx
  void *v6; // rdi
  HANDLE v7; // rax
  signed int LastError; // eax
  __int64 v9; // rcx
  unsigned __int16 *v10; // rax
  unsigned int v11; // edi
  unsigned __int64 v12; // rsi
  __int64 v13; // r14
  HANDLE v14; // rax
  _DWORD *v15; // rax
  struct _EVENT_TRACE_PROPERTIES *v16; // rbx
  unsigned __int16 *v17; // rdx
  unsigned __int64 v18; // rsi
  __int64 v19; // rax
  unsigned __int16 *v20; // rcx
  unsigned __int16 v21; // r8
  unsigned __int16 *v22; // rcx
  ULONG started; // eax
  __int64 v24; // rdx
  void *v25; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v27; // rax
  void *v28; // rbx
  HANDLE v29; // rax
  bool v30; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h] BYREF
  ULONG64 TraceHandle; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v33; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v34[22]; // [rsp+68h] [rbp-98h]
  WCHAR InstanceName[32]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v36[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR PathName[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  if ( g_eventProvider )
    return 0;
  v0 = EtwEventRegister(&PCRPF_Provider, 0, 0, &g_eventProvider);
  if ( v0 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x18,
             (int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
             (const char *)v0);
  v30 = 0;
  IsOSWinPEBased = PpfhIsOSWinPEBased(&v30);
  AssociatedOSPathInWinPEBasedOS = IsOSWinPEBased;
  if ( IsOSWinPEBased < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
      (const char *)(unsigned int)IsOSWinPEBased);
    return (unsigned int)AssociatedOSPathInWinPEBasedOS;
  }
  if ( !v30 )
    return 0;
  v30 = 0;
  lpMem = 0;
  v4 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&(&lpMem);
  AssociatedOSPathInWinPEBasedOS = PpfhGetAssociatedOSPathInWinPEBasedOS(&v30, v4);
  if ( AssociatedOSPathInWinPEBasedOS < 0 )
  {
    v5 = 33;
    goto LABEL_10;
  }
  if ( !v30 )
  {
LABEL_45:
    v25 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v25);
    }
    return 0;
  }
  v33 = *(_OWORD *)L"Windows\\Logs\\PCRPF";
  *(_OWORD *)v34 = *(_OWORD *)L"Logs\\PCRPF";
  *(_QWORD *)&v34[14] = *(_QWORD *)L"RPF";
  memset_0(PathName, 0, 0x208u);
  AssociatedOSPathInWinPEBasedOS = StringCchPrintfW(PathName, 0x104u, L"%s\\%s", lpMem, &v33);
  if ( AssociatedOSPathInWinPEBasedOS < 0 )
  {
    v5 = 38;
    goto LABEL_10;
  }
  if ( !CreateDirectoryW(PathName, 0) )
  {
    LastError = GetLastError();
    AssociatedOSPathInWinPEBasedOS = LastError;
    if ( LastError != 183 )
    {
      if ( LastError > 0 )
        AssociatedOSPathInWinPEBasedOS = (unsigned __int16)LastError | 0x80070000;
      if ( AssociatedOSPathInWinPEBasedOS >= 0 )
        goto LABEL_11;
      v5 = 42;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
        (const char *)(unsigned int)AssociatedOSPathInWinPEBasedOS);
LABEL_11:
      v6 = lpMem;
      if ( lpMem )
      {
        v7 = GetProcessHeap();
        HeapFree(v7, 0, v6);
      }
      return (unsigned int)AssociatedOSPathInWinPEBasedOS;
    }
  }
  memset_0(v36, 0, 0x208u);
  AssociatedOSPathInWinPEBasedOS = StringCchPrintfW(v36, 0x104u, L"%s\\PcrpfWinREEventLog.etl", PathName);
  if ( AssociatedOSPathInWinPEBasedOS < 0 )
  {
    v5 = 46;
    goto LABEL_10;
  }
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
    0x2Fu,
    "PpfhRegisterEventLogProvider",
    "Setting up event logs into %ws",
    v36);
  v9 = 260;
  v10 = v36;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  v11 = -2147024809;
  AssociatedOSPathInWinPEBasedOS = v9 == 0 ? 0x80070057 : 0;
  if ( !v9 )
  {
    v5 = 50;
    goto LABEL_10;
  }
  v12 = (-(__int64)(v9 != 0) & (2 * (260 - v9))) + 2;
  wcscpy(InstanceName, L"PcrpfWinREEventLogSession");
  v13 = (-(__int64)(v9 != 0) & (2 * (260 - v9))) + 174;
  v14 = GetProcessHeap();
  v15 = HeapAlloc(v14, 8u, v12 + 172);
  v16 = (struct _EVENT_TRACE_PROPERTIES *)v15;
  if ( !v15 )
  {
    v11 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
      (const char *)0x8007000ELL);
    goto LABEL_53;
  }
  *v15 = v13;
  v15[10] = 2;
  v15[11] = 0x20000;
  v15[16] = 4;
  v15[15] = 5;
  v15[29] = 120;
  v15[28] = 172;
  v17 = (unsigned __int16 *)(v15 + 43);
  v18 = v12 >> 1;
  if ( v18 )
  {
    if ( v18 > 0x7FFFFFFF )
    {
      *v17 = 0;
    }
    else
    {
      v19 = 2147483646;
      v20 = v36;
      do
      {
        if ( !v19 )
          break;
        v21 = *v20;
        if ( !*v20 )
          break;
        ++v20;
        *v17++ = v21;
        --v19;
        --v18;
      }
      while ( v18 );
      v11 = v18 == 0 ? 0x8007007A : 0;
      v22 = v17 - 1;
      if ( v18 )
        v22 = v17;
      *v22 = 0;
      if ( v18 )
      {
        TraceHandle = 0;
        started = StartTraceW(&TraceHandle, InstanceName, v16);
        if ( started )
        {
          v24 = 80;
          goto LABEL_40;
        }
        started = EnableTraceEx2(TraceHandle, &PCRPF_Provider, 1u, 4u, 0, 0, 0, 0);
        if ( started )
        {
          v24 = 82;
LABEL_40:
          v11 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)v24,
                  (int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
                  (const char *)started);
          if ( TraceHandle )
            ControlTraceW(TraceHandle, 0, v16, 1u);
          goto LABEL_51;
        }
        g_winreLogSessionHandle = TraceHandle;
        g_winreEventTraceProperties = v16;
        goto LABEL_45;
      }
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x45,
    (int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
    (const char *)v11);
LABEL_51:
  v27 = GetProcessHeap();
  HeapFree(v27, 0, v16);
LABEL_53:
  v28 = lpMem;
  if ( lpMem )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v28);
  }
  return v11;
}

```

## disassembly

```asm
0x18003639c  push    rbp
0x18003639e  push    rbx
0x18003639f  push    rsi
0x1800363a0  push    rdi
0x1800363a1  push    r14
0x1800363a3  push    r15
0x1800363a5  lea     rbp, [rsp-3F8h]
0x1800363ad  sub     rsp, 4F8h
0x1800363b4  mov     rax, cs:__security_cookie
0x1800363bb  xor     rax, rsp
0x1800363be  mov     [rbp+420h+var_40], rax
0x1800363c5  xor     r15d, r15d
0x1800363c8  cmp     cs:?g_eventProvider@@3_KA, r15; unsigned __int64 g_eventProvider
0x1800363cf  jnz     loc_180036820
0x1800363d5  lea     r9, ?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x1800363dc  xor     r8d, r8d
0x1800363df  xor     edx, edx
0x1800363e1  lea     rcx, PCRPF_Provider
0x1800363e8  call    cs:__imp_EtwEventRegister
0x1800363ef  nop     dword ptr [rax+rax+00h]
0x1800363f4  test    eax, eax
0x1800363f6  jz      short loc_180036417
0x1800363f8  mov     rcx, [rbp+428h]; this
0x1800363ff  mov     r9d, eax; char *
0x180036402  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180036409  lea     edx, [r15+18h]; void *
0x18003640d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180036412  jmp     loc_180036822
0x180036417  mov     [rsp+520h+var_4E0], r15b
0x18003641c  lea     rcx, [rsp+520h+var_4E0]; bool *
0x180036421  call    ?PpfhIsOSWinPEBased@@YAJPEA_N@Z; PpfhIsOSWinPEBased(bool *)
0x180036426  mov     ebx, eax
0x180036428  test    eax, eax
0x18003642a  jns     short loc_18003644E
0x18003642c  mov     rcx, [rbp+428h]; this
0x180036433  mov     r9d, eax; char *
0x180036436  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003643d  mov     edx, 1Bh; void *
0x180036442  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036447  mov     eax, ebx
0x180036449  jmp     loc_180036822
0x18003644e  cmp     [rsp+520h+var_4E0], r15b
0x180036453  jz      loc_180036820
0x180036459  mov     [rsp+520h+var_4E0], r15b
0x18003645e  mov     [rsp+520h+lpMem], r15
0x180036463  lea     rcx, [rsp+520h+lpMem]
0x180036468  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator&(void)
0x18003646d  mov     rdx, rax; unsigned __int16 **
0x180036470  lea     rcx, [rsp+520h+var_4E0]; bool *
0x180036475  call    ?PpfhGetAssociatedOSPathInWinPEBasedOS@@YAJPEA_NPEAPEAG@Z; PpfhGetAssociatedOSPathInWinPEBasedOS(bool *,ushort * *)
0x18003647a  mov     ebx, eax
0x18003647c  test    eax, eax
0x18003647e  jns     short loc_1800364CB
0x180036480  mov     edx, 21h ; '!'; void *
0x180036485  mov     rcx, [rbp+428h]; this
0x18003648c  mov     r9d, ebx; char *
0x18003648f  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180036496  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003649b  nop
0x18003649c  mov     rdi, [rsp+520h+lpMem]
0x1800364a1  test    rdi, rdi
0x1800364a4  jz      short loc_180036447
0x1800364a6  call    cs:__imp_GetProcessHeap
0x1800364ad  nop     dword ptr [rax+rax+00h]
0x1800364b2  mov     rcx, rax; hHeap
0x1800364b5  mov     r8, rdi; lpMem
0x1800364b8  xor     edx, edx; dwFlags
0x1800364ba  call    cs:__imp_HeapFree
0x1800364c1  nop     dword ptr [rax+rax+00h]
0x1800364c6  jmp     loc_180036447
0x1800364cb  cmp     [rsp+520h+var_4E0], r15b
0x1800364d0  jz      loc_1800367F6
0x1800364d6  movups  xmm0, xmmword ptr cs:aWindowsLogsPcr; "Windows\\Logs\\PCRPF"
0x1800364dd  movups  [rsp+520h+var_4C8], xmm0
0x1800364e2  movups  xmm1, xmmword ptr cs:aWindowsLogsPcr+10h; "Logs\\PCRPF"
0x1800364e9  movups  xmmword ptr [rsp+520h+var_4B8], xmm1
0x1800364ee  movsd   xmm0, qword ptr cs:aWindowsLogsPcr+1Eh; "RPF"
0x1800364f6  movsd   qword ptr [rsp+520h+var_4B8+0Eh], xmm0
0x1800364fc  mov     edi, 208h
0x180036501  mov     r8d, edi; Size
0x180036504  xor     edx, edx; Val
0x180036506  lea     rcx, [rbp+420h+PathName]; void *
0x18003650d  call    memset_0
0x180036512  lea     rax, [rsp+520h+var_4C8]
0x180036517  mov     [rsp+520h+MatchAnyKeyword], rax
0x18003651c  mov     r9, [rsp+520h+lpMem]
0x180036521  lea     r8, aSS; "%s\\%s"
0x180036528  mov     esi, 104h
0x18003652d  mov     edx, esi; unsigned __int64
0x18003652f  lea     rcx, [rbp+420h+PathName]; unsigned __int16 *
0x180036536  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003653b  mov     ebx, eax
0x18003653d  test    eax, eax
0x18003653f  jns     short loc_18003654B
0x180036541  mov     edx, 26h ; '&'
0x180036546  jmp     loc_180036485
0x18003654b  xor     edx, edx; lpSecurityAttributes
0x18003654d  lea     rcx, [rbp+420h+PathName]; lpPathName
0x180036554  call    cs:__imp_CreateDirectoryW
0x18003655b  nop     dword ptr [rax+rax+00h]
0x180036560  test    eax, eax
0x180036562  jnz     short loc_180036598
0x180036564  call    cs:__imp_GetLastError
0x18003656b  nop     dword ptr [rax+rax+00h]
0x180036570  mov     ebx, eax
0x180036572  cmp     eax, 0B7h
0x180036577  jz      short loc_180036598
0x180036579  test    eax, eax
0x18003657b  jle     short loc_180036586
0x18003657d  movzx   ebx, ax
0x180036580  or      ebx, 80070000h
0x180036586  test    ebx, ebx
0x180036588  jns     loc_18003649C
0x18003658e  mov     edx, 2Ah ; '*'
0x180036593  jmp     loc_180036485
0x180036598  mov     r8, rdi; Size
0x18003659b  xor     edx, edx; Val
0x18003659d  lea     rcx, [rbp+420h+var_460]; void *
0x1800365a1  call    memset_0
0x1800365a6  lea     r9, [rbp+420h+PathName]
0x1800365ad  lea     r8, aSPcrpfwinreeve; "%s\\PcrpfWinREEventLog.etl"
0x1800365b4  mov     rdx, rsi; unsigned __int64
0x1800365b7  lea     rcx, [rbp+420h+var_460]; unsigned __int16 *
0x1800365bb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800365c0  mov     ebx, eax
0x1800365c2  test    eax, eax
0x1800365c4  jns     short loc_1800365D0
0x1800365c6  mov     edx, 2Eh ; '.'
0x1800365cb  jmp     loc_180036485
0x1800365d0  lea     rax, [rbp+420h+var_460]
0x1800365d4  mov     [rsp+520h+MatchAnyKeyword], rax; int
0x1800365d9  lea     r9, aSettingUpEvent; "Setting up event logs into %ws"
0x1800365e0  lea     r8, aPpfhregisterev; "PpfhRegisterEventLogProvider"
0x1800365e7  mov     edx, 2Fh ; '/'; unsigned int
0x1800365ec  lea     rcx, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800365f3  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800365f8  mov     rcx, rsi
0x1800365fb  lea     rax, [rbp+420h+var_460]
0x1800365ff  cmp     [rax], r15w
0x180036603  jz      short loc_18003660F
0x180036605  add     rax, 2
0x180036609  sub     rcx, 1
0x18003660d  jnz     short loc_1800365FF
0x18003660f  mov     rax, rcx
0x180036612  neg     rax
0x180036615  sbb     ebx, ebx
0x180036617  not     ebx
0x180036619  mov     edi, 80070057h
0x18003661e  and     ebx, edi
0x180036620  test    rcx, rcx
0x180036623  jz      loc_1800368DA
0x180036629  sub     rsi, rcx
0x18003662c  add     rsi, rsi
0x18003662f  neg     rcx
0x180036632  sbb     rax, rax
0x180036635  and     rsi, rax
0x180036638  add     rsi, 2
0x18003663c  movups  xmm0, xmmword ptr cs:aPcrpfwinreeven; "PcrpfWinREEventLogSession"
0x180036643  movups  xmmword ptr [rbp+420h+InstanceName], xmm0
0x180036647  movups  xmm1, xmmword ptr cs:aPcrpfwinreeven+10h; "REEventLogSession"
0x18003664e  movups  [rbp+420h+var_490], xmm1
0x180036652  movups  xmm0, xmmword ptr cs:aPcrpfwinreeven+20h; "ogSession"
0x180036659  movups  [rbp+420h+var_480], xmm0
0x18003665d  mov     eax, dword ptr cs:aPcrpfwinreeven+30h; "n"
0x180036663  mov     [rbp+420h+var_470], eax
0x180036666  lea     r14, [rsi+0ACh]
0x18003666d  call    cs:__imp_GetProcessHeap
0x180036674  nop     dword ptr [rax+rax+00h]
0x180036679  mov     rcx, rax; hHeap
0x18003667c  mov     r8, r14; dwBytes
0x18003667f  mov     edx, 8; dwFlags
0x180036684  call    cs:__imp_HeapAlloc
0x18003668b  nop     dword ptr [rax+rax+00h]
0x180036690  mov     rbx, rax
0x180036693  test    rax, rax
0x180036696  jz      loc_180036888
0x18003669c  mov     [rax], r14d
0x18003669f  mov     dword ptr [rax+28h], 2
0x1800366a6  mov     dword ptr [rax+2Ch], 20000h
0x1800366ad  mov     dword ptr [rax+40h], 4
0x1800366b4  mov     dword ptr [rax+3Ch], 5
0x1800366bb  mov     dword ptr [rax+74h], 78h ; 'x'
0x1800366c2  mov     dword ptr [rax+70h], 0ACh
0x1800366c9  lea     rdx, [rax+0ACh]
0x1800366d0  shr     rsi, 1
0x1800366d3  jz      loc_180036842
0x1800366d9  cmp     rsi, 7FFFFFFFh
0x1800366e0  ja      loc_180036847
0x1800366e6  mov     eax, 7FFFFFFEh
0x1800366eb  lea     rcx, [rbp+420h+var_460]
0x1800366ef  test    rax, rax
0x1800366f2  jz      short loc_180036713
0x1800366f4  movzx   r8d, word ptr [rcx]
0x1800366f8  test    r8w, r8w
0x1800366fc  jz      short loc_180036713
0x1800366fe  add     rcx, 2
0x180036702  mov     [rdx], r8w
0x180036706  add     rdx, 2
0x18003670a  dec     rax
0x18003670d  sub     rsi, 1
0x180036711  jnz     short loc_1800366EF
0x180036713  mov     rax, rsi
0x180036716  neg     rax
0x180036719  sbb     edi, edi
0x18003671b  not     edi
0x18003671d  and     edi, 8007007Ah
0x180036723  lea     rcx, [rdx-2]
0x180036727  test    rsi, rsi
0x18003672a  cmovnz  rcx, rdx
0x18003672e  mov     [rcx], r15w
0x180036732  jz      loc_18003684B
0x180036738  mov     [rsp+520h+TraceHandle], r15
0x18003673d  mov     r8, rbx; Properties
0x180036740  lea     rdx, [rbp+420h+InstanceName]; InstanceName
0x180036744  lea     rcx, [rsp+520h+TraceHandle]; TraceHandle
0x180036749  call    cs:__imp_StartTraceW
0x180036750  nop     dword ptr [rax+rax+00h]
0x180036755  test    eax, eax
0x180036757  jz      short loc_1800367A0
0x180036759  mov     edx, 50h ; 'P'; void *
0x18003675e  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180036765  mov     r9d, eax; char *
0x180036768  mov     rcx, [rbp+428h]; this
0x18003676f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180036774  mov     edi, eax
0x180036776  mov     rcx, [rsp+520h+TraceHandle]; TraceHandle
0x18003677b  test    rcx, rcx
0x18003677e  jz      loc_180036866
0x180036784  mov     r9d, 1; ControlCode
0x18003678a  mov     r8, rbx; Properties
0x18003678d  xor     edx, edx; InstanceName
0x18003678f  call    cs:__imp_ControlTraceW
0x180036796  nop     dword ptr [rax+rax+00h]
0x18003679b  jmp     loc_180036866
0x1800367a0  mov     [rsp+520h+EnableParameters], r15; EnableParameters
0x1800367a5  mov     [rsp+520h+Timeout], r15d; Timeout
0x1800367aa  mov     [rsp+520h+MatchAllKeyword], r15; MatchAllKeyword
0x1800367af  mov     [rsp+520h+MatchAnyKeyword], r15; MatchAnyKeyword
0x1800367b4  mov     r9b, 4; Level
0x1800367b7  mov     r8d, 1; ControlCode
0x1800367bd  lea     rdx, PCRPF_Provider; ProviderId
0x1800367c4  mov     rcx, [rsp+520h+TraceHandle]; TraceHandle
0x1800367c9  call    cs:__imp_EnableTraceEx2
0x1800367d0  nop     dword ptr [rax+rax+00h]
0x1800367d5  test    eax, eax
0x1800367d7  jz      short loc_1800367E3
0x1800367d9  mov     edx, 52h ; 'R'
0x1800367de  jmp     loc_18003675E
0x1800367e3  mov     rax, [rsp+520h+TraceHandle]
0x1800367e8  mov     cs:?g_winreLogSessionHandle@@3_KA, rax; unsigned __int64 g_winreLogSessionHandle
0x1800367ef  mov     cs:?g_winreEventTraceProperties@@3PEAU_EVENT_TRACE_PROPERTIES@@EA, rbx; _EVENT_TRACE_PROPERTIES * g_winreEventTraceProperties
0x1800367f6  mov     rbx, [rsp+520h+lpMem]
0x1800367fb  test    rbx, rbx
0x1800367fe  jz      short loc_180036820
0x180036800  call    cs:__imp_GetProcessHeap
0x180036807  nop     dword ptr [rax+rax+00h]
0x18003680c  mov     rcx, rax; hHeap
0x18003680f  mov     r8, rbx; lpMem
0x180036812  xor     edx, edx; dwFlags
0x180036814  call    cs:__imp_HeapFree
0x18003681b  nop     dword ptr [rax+rax+00h]
0x180036820  xor     eax, eax
0x180036822  mov     rcx, [rbp+420h+var_40]
0x180036829  xor     rcx, rsp; StackCookie
0x18003682c  call    __security_check_cookie
0x180036831  add     rsp, 4F8h
0x180036838  pop     r15
0x18003683a  pop     r14
0x18003683c  pop     rdi
0x18003683d  pop     rsi
0x18003683e  pop     rbx
0x18003683f  pop     rbp
0x180036840  retn
0x180036842  test    rsi, rsi
0x180036845  jz      short loc_18003684B
0x180036847  mov     [rdx], r15w
0x18003684b  mov     rcx, [rbp+428h]; this
0x180036852  mov     r9d, edi; char *
0x180036855  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003685c  mov     edx, 45h ; 'E'; void *
0x180036861  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036866  call    cs:__imp_GetProcessHeap
0x18003686d  nop     dword ptr [rax+rax+00h]
0x180036872  mov     rcx, rax; hHeap
0x180036875  mov     r8, rbx; lpMem
0x180036878  xor     edx, edx; dwFlags
0x18003687a  call    cs:__imp_HeapFree
0x180036881  nop     dword ptr [rax+rax+00h]
0x180036886  jmp     short loc_1800368A9
0x180036888  mov     rcx, [rbp+428h]; this
0x18003688f  mov     edi, 8007000Eh
0x180036894  mov     r9d, edi; char *
0x180036897  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003689e  mov     edx, 3Ah ; ':'; void *
0x1800368a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800368a8  nop
0x1800368a9  mov     rbx, [rsp+520h+lpMem]
0x1800368ae  test    rbx, rbx
0x1800368b1  jz      short loc_1800368D3
0x1800368b3  call    cs:__imp_GetProcessHeap
  ... truncated ...
```
