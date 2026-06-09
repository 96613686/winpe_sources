# CDataIntegrityScanTaskHandler::Start(IUnknown *,ushort *)

- ea: `0x180005d20`
- end: `0x18000617e`
- name: `?Start@CDataIntegrityScanTaskHandler@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `1118`
- prototype: `__int64 __fastcall(char *pv, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002e30`
- `0x180003134`
- `0x1800032f8`
- `0x1800034f8`
- `0x180005d20`
- `0x180006364`
- `0x180006498`
- `0x1800064d8`
- `0x180006584`
- `0x180006688`
- `0x1800068b4`
- `0x180007f18`
- `0x180039010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180005f2b`
- `msvcrt!_wcsicmp` at `0x180005f48`
- `msvcrt!_wcsicmp` at `0x180005f2b`
- `msvcrt!_wcsicmp` at `0x180005f48`
- `msvcrt!wcstok_s` at `0x180005f66`
- `msvcrt!wcstok_s` at `0x180005f66`
- `msvcrt!free` at `0x180005ef7`
- `msvcrt!free` at `0x180005f77`
- `msvcrt!free` at `0x180005ef7`
- `msvcrt!free` at `0x180005f77`
- `OLEAUT32!__imp_SysStringLen` at `0x180005ed1`
- `OLEAUT32!__imp_SysStringLen` at `0x180005ed1`
- `KERNEL32!GetLastError` at `0x180005faa`
- `KERNEL32!GetLastError` at `0x180006002`
- `KERNEL32!GetLastError` at `0x180005faa`
- `KERNEL32!GetLastError` at `0x180006002`
- `KERNEL32!CreateSemaphoreExW` at `0x180005ff0`
- `KERNEL32!CreateSemaphoreExW` at `0x180005ff0`
- `KERNEL32!GetThreadPriority` at `0x180005e42`
- `KERNEL32!GetThreadPriority` at `0x180005e42`
- `KERNEL32!GetCurrentThread` at `0x180005e39`
- `KERNEL32!GetCurrentThread` at `0x180005e39`
- `KERNEL32!GetPriorityClass` at `0x180005e53`
- `KERNEL32!GetPriorityClass` at `0x180005e53`
- `KERNEL32!GetCurrentProcess` at `0x180005e4a`
- `KERNEL32!GetCurrentProcess` at `0x180005e4a`
- `KERNEL32!CreateThreadpoolWait` at `0x180005f9f`
- `KERNEL32!CreateThreadpoolWait` at `0x180005f9f`
- `KERNEL32!SubmitThreadpoolWork` at `0x18000614e`
- `KERNEL32!SubmitThreadpoolWork` at `0x18000614e`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18000609a`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18000609a`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000606d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000606d`

## string_xrefs

- `0x180005d5b`: `CDataIntegrityScanTaskHandler::Start`
- `0x1800060ea`: `Hr = AtlMarshalPtrInProc( TaskHandlerStatus, IID_ITaskHandlerStatus, &m_TaskCompletedWorkContext.TaskHandlerStatusMarshal )`

## pseudocode

```c
__int64 __fastcall CDataIntegrityScanTaskHandler::Start(char *pv, struct IUnknown *a2, unsigned __int16 *a3)
{
  USHORT Length; // cx
  __int64 v7; // r10
  USHORT v8; // dx
  USHORT v9; // ax
  int StreamOnHGlobal; // ebx
  PVOID *v11; // rcx
  __int64 v12; // rdx
  PVOID *v13; // rcx
  HANDLE CurrentThread; // rax
  int ThreadPriority; // ebx
  HANDLE CurrentProcess; // rax
  DWORD PriorityClass; // eax
  unsigned __int64 v18; // rbx
  unsigned __int64 v19; // rdx
  wchar_t *v20; // rbx
  wchar_t *v21; // rcx
  wchar_t *v22; // rax
  const wchar_t *v23; // rsi
  PTP_WAIT ThreadpoolWait; // rax
  signed int LastError; // eax
  LONG v26; // edx
  HANDLE Semaphore; // rax
  signed int v28; // eax
  LPSTREAM *v29; // rsi
  IUnknown *v30; // r15
  LPUNKNOWN pUnk; // [rsp+30h] [rbp-38h] BYREF
  wchar_t *Context[2]; // [rsp+38h] [rbp-30h] BYREF
  const char *v34; // [rsp+48h] [rbp-20h] BYREF
  int v35; // [rsp+50h] [rbp-18h]
  void *Block; // [rsp+B8h] [rbp+50h] BYREF

  Length = GlobalIndentString.Length;
  v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v34 = "CDataIntegrityScanTaskHandler::Start";
  v8 = ++*(_WORD *)(v7 + 8);
  *(_QWORD *)(v7 + 16) = "CDataIntegrityScanTaskHandler::Start";
  v9 = Length;
  if ( v8 < Length )
  {
    v9 = v8;
    Length = v8;
  }
  LOWORD(Context[0]) = v9;
  HIDWORD(Context[0]) = 0;
  Context[1] = (wchar_t *)off_180047060;
  WORD1(Context[0]) = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CDataIntegrityScanTaskHandler::Start");
  }
  ATL::CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>::CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>(
    &pUnk,
    a2);
  if ( !pUnk )
  {
    StreamOnHGlobal = -2147467262;
    v35 = -2147467262;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 25;
LABEL_61:
      WPP_SF_d(v11[2], v12, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids, (unsigned int)StreamOnHGlobal);
      goto LABEL_63;
    }
    goto LABEL_63;
  }
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      CurrentThread = GetCurrentThread();
      ThreadPriority = GetThreadPriority(CurrentThread);
      CurrentProcess = GetCurrentProcess();
      PriorityClass = GetPriorityClass(CurrentProcess);
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
        PriorityClass,
        ThreadPriority);
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 4u )
      WPP_SF_S(v13[2], 27, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids, a3);
  }
  *((_DWORD *)pv + 60) = 0;
  pv[244] = 0;
  if ( a3 )
  {
    Block = 0;
    v18 = SysStringLen(a3) + 1;
    if ( !(unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Block, v18) )
    {
      StreamOnHGlobal = -2147024882;
      v35 = -2147024882;
      free(Block);
      goto LABEL_63;
    }
    v19 = v18;
    v20 = (wchar_t *)Block;
    StringCchCopyW((unsigned __int16 *)Block, v19, a3);
    v21 = v20;
    Context[0] = 0;
    while ( 1 )
    {
      v22 = wcstok_s(v21, L" \t\n", Context);
      v23 = v22;
      if ( !v22 )
        break;
      if ( _wcsicmp(L"-CrashRecovery", v22) )
      {
        if ( !_wcsicmp(L"-Manual", v23) )
          pv[244] = 1;
      }
      else
      {
        *((_DWORD *)pv + 60) = 1;
      }
      v21 = 0;
    }
    free(v20);
  }
  QueryDataIntegrityScanConfiguration((struct _DISCAN_TASK_CONFIGURATION *)(pv + 280));
  if ( !*((_DWORD *)pv + 60) )
  {
    ThreadpoolWait = CreateThreadpoolWait(CDataIntegrityScanTaskHandler::RegularTaskHaltCallback, pv, 0);
    if ( !ThreadpoolWait )
    {
      LastError = GetLastError();
      StreamOnHGlobal = LastError;
      if ( LastError > 0 )
        StreamOnHGlobal = (unsigned __int16)LastError | 0x80070000;
      v35 = StreamOnHGlobal;
      goto LABEL_63;
    }
    *((_QWORD *)pv + 21) = ThreadpoolWait;
  }
  v26 = *((_DWORD *)pv + 72);
  if ( !v26 )
    goto LABEL_45;
  Semaphore = CreateSemaphoreExW(0, v26, v26, 0, 0, 0x1F0003u);
  *((_QWORD *)pv + 17) = Semaphore;
  if ( Semaphore )
    goto LABEL_45;
  v28 = GetLastError();
  if ( v28 > 0 )
    v28 = (unsigned __int16)v28 | 0x80070000;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
      (unsigned int)v28);
LABEL_45:
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  v29 = (LPSTREAM *)(pv + 424);
  if ( pv == (char *)-424LL )
  {
    StreamOnHGlobal = -2147467261;
    v35 = -2147467261;
  }
  else
  {
    v30 = pUnk;
    StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, (LPSTREAM *)pv + 53);
    if ( StreamOnHGlobal >= 0 )
    {
      StreamOnHGlobal = CoMarshalInterface(*v29, &IID_ITaskHandlerStatus, v30, 3u, 0, 1u);
      if ( StreamOnHGlobal < 0 )
      {
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)*v29 + 16LL))(*v29);
        *v29 = 0;
      }
    }
    v35 = StreamOnHGlobal;
    if ( StreamOnHGlobal >= 0 )
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)pv + 8LL))(pv);
      SubmitThreadpoolWork(*((PTP_WORK *)pv + 31));
      StreamOnHGlobal = 0;
      v35 = 0;
      goto LABEL_63;
    }
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 2u )
    {
      WPP_SF_sd(
        (unsigned int)v11[2],
        29,
        (unsigned int)&WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
        (unsigned int)"Hr = AtlMarshalPtrInProc( TaskHandlerStatus, IID_ITaskHandlerStatus, &m_TaskCompletedWorkContext.T"
                      "askHandlerStatusMarshal )",
        StreamOnHGlobal);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 2u )
    {
      v12 = 30;
      goto LABEL_61;
    }
  }
LABEL_63:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pUnk);
  CHResultImp::~CHResultImp((CHResultImp *)&v34);
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x180005d20  push    rbp
0x180005d22  push    rbx
0x180005d23  push    rsi
0x180005d24  push    rdi
0x180005d25  push    r13
0x180005d27  push    r15
0x180005d29  mov     rbp, rsp
0x180005d2c  sub     rsp, 68h
0x180005d30  mov     rax, gs:58h
0x180005d39  mov     rbx, rdx
0x180005d3c  mov     r9d, cs:_tls_index
0x180005d43  mov     rdi, rcx
0x180005d46  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180005d4d  mov     r13d, 1
0x180005d53  mov     edx, 8
0x180005d58  mov     rsi, r8
0x180005d5b  lea     r8, aCdataintegrity_1; "CDataIntegrityScanTaskHandler::Start"
0x180005d62  mov     r10, [rax+r9*8]
0x180005d66  mov     eax, 10h
0x180005d6b  mov     [rbp+var_20], r8
0x180005d6f  add     [rdx+r10], r13w
0x180005d74  movzx   edx, word ptr [rdx+r10]
0x180005d79  mov     [rax+r10], r8
0x180005d7d  cmp     dx, cx
0x180005d80  movzx   eax, cx
0x180005d83  cmovb   ax, dx
0x180005d87  cmovb   cx, dx
0x180005d8b  mov     word ptr [rbp+Context], ax
0x180005d8f  xor     eax, eax
0x180005d91  mov     dword ptr [rbp+Context+4], eax
0x180005d94  mov     rax, cs:off_180047060; "                                       "...
0x180005d9b  mov     [rbp+var_28], rax
0x180005d9f  mov     word ptr [rbp+Context+2], cx
0x180005da3  mov     rcx, cs:WPP_GLOBAL_Control
0x180005daa  lea     r15, WPP_GLOBAL_Control
0x180005db1  cmp     rcx, r15
0x180005db4  jz      short loc_180005DD8
0x180005db6  test    [rcx+1Ch], r13b
0x180005dba  jz      short loc_180005DD8
0x180005dbc  cmp     byte ptr [rcx+19h], 5
0x180005dc0  jb      short loc_180005DD8
0x180005dc2  mov     rcx, [rcx+10h]; LoggerHandle
0x180005dc6  lea     edx, [r13+0Ch]
0x180005dca  lea     r9, [rbp+Context]
0x180005dce  mov     qword ptr [rsp+68h+dwFlags], r8; __int64
0x180005dd3  call    WPP_SF_aZs
0x180005dd8  mov     rdx, rbx
0x180005ddb  lea     rcx, [rbp+pUnk]
0x180005ddf  call    ??0?$CComQIPtr@UITaskHandlerStatus@@$1?_GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>::CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>(IUnknown *)
0x180005de4  cmp     [rbp+pUnk], 0
0x180005de9  jnz     short loc_180005E21
0x180005deb  mov     ebx, 80004002h
0x180005df0  mov     [rbp+var_18], ebx
0x180005df3  mov     rcx, cs:WPP_GLOBAL_Control
0x180005dfa  cmp     rcx, r15
0x180005dfd  jz      loc_18000615D
0x180005e03  test    [rcx+1Ch], r13b
0x180005e07  jz      loc_18000615D
0x180005e0d  cmp     byte ptr [rcx+19h], 2
0x180005e11  jb      loc_18000615D
0x180005e17  mov     edx, 19h
0x180005e1c  jmp     loc_180006123
0x180005e21  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e28  cmp     rcx, r15
0x180005e2b  jz      short loc_180005EAC
0x180005e2d  test    [rcx+1Ch], r13b
0x180005e31  jz      short loc_180005E83
0x180005e33  cmp     byte ptr [rcx+19h], 4
0x180005e37  jb      short loc_180005E83
0x180005e39  call    cs:__imp_GetCurrentThread
0x180005e3f  mov     rcx, rax; hThread
0x180005e42  call    cs:__imp_GetThreadPriority
0x180005e48  mov     ebx, eax
0x180005e4a  call    cs:__imp_GetCurrentProcess
0x180005e50  mov     rcx, rax; hProcess
0x180005e53  call    cs:__imp_GetPriorityClass
0x180005e59  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e60  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180005e67  mov     edx, 1Ah
0x180005e6c  mov     [rsp+68h+dwFlags], ebx
0x180005e70  mov     r9d, eax
0x180005e73  mov     rcx, [rcx+10h]
0x180005e77  call    WPP_SF_Dd
0x180005e7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e83  cmp     rcx, r15
0x180005e86  jz      short loc_180005EAC
0x180005e88  test    [rcx+1Ch], r13b
0x180005e8c  jz      short loc_180005EAC
0x180005e8e  cmp     byte ptr [rcx+19h], 4
0x180005e92  jb      short loc_180005EAC
0x180005e94  mov     rcx, [rcx+10h]
0x180005e98  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180005e9f  mov     edx, 1Bh
0x180005ea4  mov     r9, rsi
0x180005ea7  call    WPP_SF_S
0x180005eac  mov     dword ptr [rdi+0F0h], 0
0x180005eb6  mov     byte ptr [rdi+0F4h], 0
0x180005ebd  test    rsi, rsi
0x180005ec0  jz      loc_180005F7D
0x180005ec6  mov     rcx, rsi; pbstr
0x180005ec9  mov     [rbp+Block], 0
0x180005ed1  call    cs:__imp_SysStringLen
0x180005ed7  add     eax, r13d
0x180005eda  lea     rcx, [rbp+Block]
0x180005ede  mov     edx, eax
0x180005ee0  mov     ebx, eax
0x180005ee2  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x180005ee7  test    al, al
0x180005ee9  jnz     short loc_180005F02
0x180005eeb  mov     rcx, [rbp+Block]; Block
0x180005eef  mov     ebx, 8007000Eh
0x180005ef4  mov     [rbp+var_18], ebx
0x180005ef7  call    cs:__imp_free
0x180005efd  jmp     loc_18000615D
0x180005f02  mov     rdx, rbx; unsigned __int64
0x180005f05  mov     r8, rsi; unsigned __int16 *
0x180005f08  mov     rbx, [rbp+Block]
0x180005f0c  mov     rcx, rbx; unsigned __int16 *
0x180005f0f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005f14  mov     rcx, rbx
0x180005f17  mov     [rbp+Context], 0
0x180005f1f  jmp     short loc_180005F5B
0x180005f21  mov     rdx, rsi; String2
0x180005f24  lea     rcx, aCrashrecovery; "-CrashRecovery"
0x180005f2b  call    cs:__imp__wcsicmp
0x180005f31  test    eax, eax
0x180005f33  jnz     short loc_180005F3E
0x180005f35  mov     [rdi+0F0h], r13d
0x180005f3c  jmp     short loc_180005F59
0x180005f3e  mov     rdx, rsi; String2
0x180005f41  lea     rcx, aManual; "-Manual"
0x180005f48  call    cs:__imp__wcsicmp
0x180005f4e  test    eax, eax
0x180005f50  jnz     short loc_180005F59
0x180005f52  mov     [rdi+0F4h], r13b
0x180005f59  xor     ecx, ecx; String
0x180005f5b  lea     r8, [rbp+Context]; Context
0x180005f5f  lea     rdx, Delimiter; " \t\n"
0x180005f66  call    cs:__imp_wcstok_s
0x180005f6c  mov     rsi, rax
0x180005f6f  test    rax, rax
0x180005f72  jnz     short loc_180005F21
0x180005f74  mov     rcx, rbx; Block
0x180005f77  call    cs:__imp_free
0x180005f7d  lea     rcx, [rdi+118h]; struct _DISCAN_TASK_CONFIGURATION *
0x180005f84  call    ?QueryDataIntegrityScanConfiguration@@YAXPEAU_DISCAN_TASK_CONFIGURATION@@@Z; QueryDataIntegrityScanConfiguration(_DISCAN_TASK_CONFIGURATION *)
0x180005f89  cmp     dword ptr [rdi+0F0h], 0
0x180005f90  jnz     short loc_180005FCE
0x180005f92  xor     r8d, r8d; pcbe
0x180005f95  lea     rcx, ?RegularTaskHaltCallback@CDataIntegrityScanTaskHandler@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180005f9c  mov     rdx, rdi; pv
0x180005f9f  call    cs:__imp_CreateThreadpoolWait
0x180005fa5  test    rax, rax
0x180005fa8  jnz     short loc_180005FC7
0x180005faa  call    cs:__imp_GetLastError
0x180005fb0  mov     ebx, eax
0x180005fb2  test    eax, eax
0x180005fb4  jle     short loc_180005FBF
0x180005fb6  movzx   ebx, ax
0x180005fb9  or      ebx, 80070000h
0x180005fbf  mov     [rbp+var_18], ebx
0x180005fc2  jmp     loc_18000615D
0x180005fc7  mov     [rdi+0A8h], rax
0x180005fce  mov     edx, [rdi+120h]; lInitialCount
0x180005fd4  test    edx, edx
0x180005fd6  jz      short loc_180006044
0x180005fd8  mov     [rsp+68h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005fe0  xor     r9d, r9d; lpName
0x180005fe3  mov     r8d, edx; lMaximumCount
0x180005fe6  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180005fee  xor     ecx, ecx; lpSemaphoreAttributes
0x180005ff0  call    cs:__imp_CreateSemaphoreExW
0x180005ff6  mov     [rdi+88h], rax
0x180005ffd  test    rax, rax
0x180006000  jnz     short loc_180006044
0x180006002  call    cs:__imp_GetLastError
0x180006008  test    eax, eax
0x18000600a  jle     short loc_180006014
0x18000600c  movzx   eax, ax
0x18000600f  or      eax, 80070000h
0x180006014  mov     rcx, cs:WPP_GLOBAL_Control
0x18000601b  cmp     rcx, r15
0x18000601e  jz      short loc_18000604B
0x180006020  test    [rcx+1Ch], r13b
0x180006024  jz      short loc_18000604B
0x180006026  cmp     byte ptr [rcx+19h], 2
0x18000602a  jb      short loc_18000604B
0x18000602c  mov     rcx, [rcx+10h]
0x180006030  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180006037  mov     edx, 1Ch
0x18000603c  mov     r9d, eax
0x18000603f  call    WPP_SF_d
0x180006044  mov     rcx, cs:WPP_GLOBAL_Control
0x18000604b  lea     rsi, [rdi+1A8h]
0x180006052  test    rsi, rsi
0x180006055  jnz     short loc_180006061
0x180006057  mov     ebx, 80004003h
0x18000605c  mov     [rbp+var_18], ebx
0x18000605f  jmp     short loc_1800060D1
0x180006061  mov     r15, [rbp+pUnk]
0x180006065  mov     r8, rsi; ppstm
0x180006068  mov     edx, r13d; fDeleteOnRelease
0x18000606b  xor     ecx, ecx; hGlobal
0x18000606d  call    cs:__imp_CreateStreamOnHGlobal
0x180006073  mov     ebx, eax
0x180006075  test    eax, eax
0x180006077  js      short loc_1800060BC
0x180006079  mov     rcx, [rsi]; pStm
0x18000607c  lea     rdx, IID_ITaskHandlerStatus; riid
0x180006083  mov     [rsp+68h+dwDesiredAccess], r13d; mshlflags
0x180006088  mov     r9d, 3; dwDestContext
0x18000608e  mov     r8, r15; pUnk
0x180006091  mov     qword ptr [rsp+68h+dwFlags], 0; pvDestContext
0x18000609a  call    cs:__imp_CoMarshalInterface
0x1800060a0  mov     ebx, eax
0x1800060a2  test    eax, eax
0x1800060a4  jns     short loc_1800060BC
0x1800060a6  mov     rcx, [rsi]
0x1800060a9  mov     rax, [rcx]
0x1800060ac  mov     rax, [rax+10h]
0x1800060b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060b5  mov     qword ptr [rsi], 0
0x1800060bc  mov     [rbp+var_18], ebx
0x1800060bf  test    ebx, ebx
0x1800060c1  jns     short loc_180006138
0x1800060c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060ca  lea     r15, WPP_GLOBAL_Control
0x1800060d1  cmp     rcx, r15
0x1800060d4  jz      loc_18000615D
0x1800060da  test    [rcx+1Ch], r13b
0x1800060de  jz      short loc_18000610D
0x1800060e0  cmp     byte ptr [rcx+19h], 2
0x1800060e4  jb      short loc_18000610D
0x1800060e6  mov     rcx, [rcx+10h]
0x1800060ea  lea     r9, aHrAtlmarshalpt; "Hr = AtlMarshalPtrInProc( TaskHandlerSt"...
0x1800060f1  mov     edx, 1Dh
0x1800060f6  mov     [rsp+68h+dwFlags], ebx
0x1800060fa  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180006101  call    WPP_SF_sd
0x180006106  mov     rcx, cs:WPP_GLOBAL_Control
0x18000610d  cmp     rcx, r15
0x180006110  jz      short loc_18000615D
0x180006112  test    [rcx+1Ch], r13b
0x180006116  jz      short loc_18000615D
0x180006118  cmp     byte ptr [rcx+19h], 2
0x18000611c  jb      short loc_18000615D
0x18000611e  mov     edx, 1Eh
0x180006123  mov     rcx, [rcx+10h]
0x180006127  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x18000612e  mov     r9d, ebx
0x180006131  call    WPP_SF_d
0x180006136  jmp     short loc_18000615D
0x180006138  mov     rax, [rdi]
0x18000613b  mov     rcx, rdi
0x18000613e  mov     rax, [rax+8]
0x180006142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006147  mov     rcx, [rdi+0F8h]; pwk
0x18000614e  call    cs:__imp_SubmitThreadpoolWork
0x180006154  xor     ebx, ebx
0x180006156  mov     [rbp+var_18], 0
0x18000615d  lea     rcx, [rbp+pUnk]
0x180006161  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006166  lea     rcx, [rbp+var_20]; this
0x18000616a  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18000616f  mov     eax, ebx
0x180006171  add     rsp, 68h
0x180006175  pop     r15
0x180006177  pop     r13
0x180006179  pop     rdi
0x18000617a  pop     rsi
0x18000617b  pop     rbx
0x18000617c  pop     rbp
0x18000617d  retn
```
