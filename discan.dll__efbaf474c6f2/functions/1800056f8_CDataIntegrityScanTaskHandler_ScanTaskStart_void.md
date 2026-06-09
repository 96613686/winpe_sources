# CDataIntegrityScanTaskHandler::ScanTaskStart(void)

- ea: `0x1800056f8`
- end: `0x180005d09`
- name: `?ScanTaskStart@CDataIntegrityScanTaskHandler@@AEAAXXZ`
- size: `1553`
- prototype: `void __fastcall(CDataIntegrityScanTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180005d10`

## callees

- `0x180001b78`
- `0x180002e20`
- `0x180002ff4`
- `0x1800032f8`
- `0x180003a7c`
- `0x1800056f8`
- `0x180006470`
- `0x180006498`
- `0x180006524`
- `0x180006688`
- `0x1800068b4`
- `0x18000beec`
- `0x18001323c`
- `0x1800168dc`
- `0x180039010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005ae7`
- `KERNEL32!GetLastError` at `0x180005ae7`
- `KERNEL32!GetThreadPriority` at `0x1800057d5`
- `KERNEL32!GetThreadPriority` at `0x1800057d5`
- `KERNEL32!GetCurrentThread` at `0x1800057cc`
- `KERNEL32!GetCurrentThread` at `0x1800057cc`
- `KERNEL32!GetPriorityClass` at `0x1800057e6`
- `KERNEL32!GetPriorityClass` at `0x1800057e6`
- `KERNEL32!GetCurrentProcess` at `0x1800057dd`
- `KERNEL32!GetCurrentProcess` at `0x1800057dd`
- `KERNEL32!SetEvent` at `0x180005b0c`
- `KERNEL32!SetEvent` at `0x180005b0c`
- `KERNEL32!WaitForSingleObject` at `0x18000599c`
- `KERNEL32!WaitForSingleObject` at `0x180005b3f`
- `KERNEL32!WaitForSingleObject` at `0x18000599c`
- `KERNEL32!WaitForSingleObject` at `0x180005b3f`
- `KERNEL32!SetThreadpoolWait` at `0x180005a00`
- `KERNEL32!SetThreadpoolWait` at `0x180005a00`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180005814`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180005814`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800058f6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800058f6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180005ce8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180005ce8`

## string_xrefs

- `0x180005729`: `CDataIntegrityScanTaskHandler::ScanTaskStart`
- `0x18000584c`: `Hr = CoInit.Initialize( COINIT_MULTITHREADED )`

## pseudocode

```c
void __fastcall CDataIntegrityScanTaskHandler::ScanTaskStart(CDataIntegrityScanTaskHandler *this)
{
  CDataIntegrityScanTaskHandler *v1; // rsi
  __int64 v2; // r8
  USHORT v3; // dx
  USHORT Length; // cx
  USHORT v5; // ax
  PVOID *v6; // rax
  HANDLE CurrentThread; // rax
  int ThreadPriority; // ebx
  HANDLE CurrentProcess; // rax
  DWORD PriorityClass; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  HRESULT v13; // eax
  int v14; // ecx
  int v15; // eax
  _BYTE *v16; // rbx
  int v17; // eax
  DWORD v18; // eax
  signed int v19; // edi
  void *v20; // rax
  CSystemScanner *v21; // rax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  signed int LastError; // eax
  unsigned int v25; // eax
  PVOID *v26; // rcx
  void *v27; // rax
  CSystemScanner *v28; // rax
  int v29; // [rsp+30h] [rbp-68h] BYREF
  int v30; // [rsp+34h] [rbp-64h] BYREF
  _BYTE v31[8]; // [rsp+38h] [rbp-60h] BYREF
  const char *v32; // [rsp+40h] [rbp-58h] BYREF
  int started; // [rsp+48h] [rbp-50h]
  USHORT v34; // [rsp+50h] [rbp-48h]
  USHORT v35; // [rsp+52h] [rbp-46h]
  int v36; // [rsp+54h] [rbp-44h]
  char *v37; // [rsp+58h] [rbp-40h]
  unsigned int v39; // [rsp+A8h] [rbp+10h]
  _BYTE *v40; // [rsp+B8h] [rbp+20h] BYREF

  v1 = this;
  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v2 + 16) = "CDataIntegrityScanTaskHandler::ScanTaskStart";
  v32 = "CDataIntegrityScanTaskHandler::ScanTaskStart";
  v3 = ++*(_WORD *)(v2 + 8);
  Length = GlobalIndentString.Length;
  v5 = GlobalIndentString.Length;
  if ( v3 < GlobalIndentString.Length )
    v5 = *(_WORD *)(v2 + 8);
  v34 = v5;
  if ( v3 < GlobalIndentString.Length )
    Length = v3;
  v35 = Length;
  v36 = 0;
  v37 = off_180047060;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CDataIntegrityScanTaskHandler::ScanTaskStart");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 4u )
  {
    CurrentThread = GetCurrentThread();
    ThreadPriority = GetThreadPriority(CurrentThread);
    CurrentProcess = GetCurrentProcess();
    PriorityClass = GetPriorityClass(CurrentProcess);
    WPP_SF_LLL(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, *((unsigned int *)v1 + 60), PriorityClass, ThreadPriority);
  }
  v13 = CoInitializeEx(0, 0);
  started = v13;
  if ( v13 >= 0 )
  {
    *((_QWORD *)v1 + 49) = 0;
    *((_QWORD *)v1 + 42) = *((_QWORD *)v1 + 17);
    *((_DWORD *)v1 + 86) = *((_DWORD *)v1 + 73);
    *((_DWORD *)v1 + 87) = *((_DWORD *)v1 + 74);
    *((_DWORD *)v1 + 88) = *((_DWORD *)v1 + 75);
    *((_BYTE *)v1 + 325) = *((_BYTE *)v1 + 284);
    *((_BYTE *)v1 + 326) = *((_BYTE *)v1 + 285);
    *((_DWORD *)v1 + 89) = *((_DWORD *)v1 + 76);
    *((_DWORD *)v1 + 90) = *((_DWORD *)v1 + 77);
    *((_DWORD *)v1 + 91) = *((_DWORD *)v1 + 78);
    *((_DWORD *)v1 + 92) = 3600000 * *((_DWORD *)v1 + 79);
    CoCreateGuid((GUID *)((char *)v1 + 372));
    v14 = *((_DWORD *)v1 + 60);
    v15 = 1;
    if ( v14 != 1 )
      v15 = *((_DWORD *)v1 + 70);
    *((_DWORD *)v1 + 80) = v15;
    *((_DWORD *)v1 + 82) = v14;
    *((_BYTE *)v1 + 324) = *((_BYTE *)v1 + 244);
    EventWriteTaskStart((CDataIntegrityScanTaskHandler *)((char *)v1 + 320));
    wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v31, v1);
    v16 = v31;
    v40 = v31;
    if ( !*((_DWORD *)v1 + 60) )
    {
      v17 = EnableTaskTrigger(1);
      started = v17;
      if ( v17 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
          (unsigned int)v17);
      }
      v18 = WaitForSingleObject(*((HANDLE *)v1 + 28), 0);
      if ( v18 == 258 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
        }
        v19 = -2147023654;
LABEL_51:
        started = v19;
        goto LABEL_82;
      }
      if ( v18 )
      {
        LastError = GetLastError();
        v19 = LastError;
        if ( LastError > 0 )
          v19 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_51;
      }
      *((_BYTE *)v1 + 216) = 1;
      SetThreadpoolWait(*((PTP_WAIT *)v1 + 21), *((HANDLE *)v1 + 19), 0);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
      }
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        v20 = operator new(0x210u);
        if ( v20 )
          v21 = CSystemScanner::CSystemScanner(
                  v20,
                  (CDataIntegrityScanTaskHandler *)((char *)v1 + 320),
                  (struct ISystemScanNotify *)(((unsigned __int64)v1 + 8) & -(__int64)(v1 != 0)));
        else
          v21 = 0;
        *((_QWORD *)v1 + 50) = v21;
        started = CSystemScanner::StartSystemScan(v21, *((void **)v1 + 9), *((void **)v1 + 15));
        if ( started >= 0 )
          v16 = 0;
        v40 = v16;
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          started = -2147024882;
          v1 = this;
          __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180005A96);
          goto LABEL_44;
        }
        if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v29) )
        {
          started = v29;
          v1 = this;
          __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180005A98);
        }
      }
LABEL_44:
      v19 = started;
      if ( started >= 0 )
        goto LABEL_84;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_82:
        if ( v19 < 0 )
LABEL_83:
          (**((void (__fastcall ***)(char *, _QWORD, _QWORD))v1 + 1))((char *)v1 + 8, (unsigned int)v19, 0);
LABEL_84:
        CAutoTearDown__lambda_0f0e5c37d1ef12747dd41e8920bec683___::_CAutoTearDown__lambda_0f0e5c37d1ef12747dd41e8920bec683___(&v40);
        CoUninitialize();
        goto LABEL_85;
      }
      v23 = 43;
LABEL_81:
      WPP_SF_d(v22[2], v23, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids, (unsigned int)v19);
      goto LABEL_82;
    }
    SetEvent(*((HANDLE *)v1 + 19));
    v19 = -805305301;
    started = -805305301;
    v25 = 0;
    v26 = (PVOID *)WPP_GLOBAL_Control;
    while ( 1 )
    {
      v39 = v25;
      if ( v25 >= 0x258 )
        break;
      if ( !WaitForSingleObject(*((HANDLE *)v1 + 28), 0x3E8u) )
      {
        *((_BYTE *)v1 + 216) = 1;
        v19 = 0;
        started = 0;
        v26 = (PVOID *)WPP_GLOBAL_Control;
        break;
      }
      v26 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids, v39);
        v26 = (PVOID *)WPP_GLOBAL_Control;
      }
      v25 = v39 + 1;
    }
    if ( v19 < 0 )
    {
      if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 1) != 0 && *((_BYTE *)v26 + 25) >= 2u )
        WPP_SF_d(v26[2], 45, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids, (unsigned int)v19);
      goto LABEL_83;
    }
    if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 1) != 0 && *((_BYTE *)v26 + 25) >= 4u )
      WPP_SF_(v26[2], 46, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
    if ( __eh34_try(-1, 2) )
    {
      __eh34_scope_strut(2);
      v27 = operator new(0x210u);
      if ( v27 )
        v28 = CSystemScanner::CSystemScanner(
                v27,
                (CDataIntegrityScanTaskHandler *)((char *)v1 + 320),
                (struct ISystemScanNotify *)(((unsigned __int64)v1 + 8) & -(__int64)(v1 != 0)));
      else
        v28 = 0;
      *((_QWORD *)v1 + 50) = v28;
      started = CSystemScanner::StartSystemScan(v28, *((void **)v1 + 9), *((void **)v1 + 15));
      if ( started >= 0 )
        v16 = 0;
      v40 = v16;
    }
    if ( __eh34_catch(2) )
    {
      if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        started = -2147024882;
        v1 = this;
        __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_180005C72);
        goto LABEL_76;
      }
      if ( __eh34_catch_type(2, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v30) )
      {
        started = v30;
        v1 = this;
        __eh34_try_continuation(2, &ATL::CAtlException `RTTI Type Descriptor', &loc_180005C74);
      }
    }
LABEL_76:
    v19 = started;
    if ( started >= 0 )
      goto LABEL_84;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_82;
    }
    v23 = 47;
    goto LABEL_81;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (int)&WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids,
      (int)"Hr = CoInit.Initialize( COINIT_MULTITHREADED )",
      v13);
  }
LABEL_85:
  CHResultImp::~CHResultImp((CHResultImp *)&v32);
}

```

## disassembly

```asm
0x1800056f8  mov     r11, rsp
0x1800056fb  mov     [r11+8], rcx
0x1800056ff  push    rbx
0x180005700  push    rsi
0x180005701  push    rdi
0x180005702  push    r12
0x180005704  push    r13
0x180005706  push    r14
0x180005708  push    r15
0x18000570a  sub     rsp, 60h
0x18000570e  mov     rsi, rcx
0x180005711  mov     edx, cs:_tls_index
0x180005717  mov     rax, gs:58h
0x180005720  mov     r8, [rax+rdx*8]
0x180005724  mov     eax, 10h
0x180005729  lea     r9, aCdataintegrity_5; "CDataIntegrityScanTaskHandler::ScanTask"...
0x180005730  mov     [rax+r8], r9
0x180005734  mov     [r11-58h], r9
0x180005738  mov     edx, 8
0x18000573d  mov     r15d, 1
0x180005743  add     [rdx+r8], r15w
0x180005748  movzx   edx, word ptr [rdx+r8]
0x18000574d  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180005754  movzx   eax, cx
0x180005757  cmp     dx, cx
0x18000575a  cmovb   ax, dx
0x18000575e  mov     [rsp+98h+var_48], ax
0x180005763  cmovb   cx, dx
0x180005767  mov     [rsp+98h+var_46], cx
0x18000576c  xor     eax, eax
0x18000576e  mov     [rsp+98h+var_44], eax
0x180005772  mov     rax, cs:off_180047060; "                                       "...
0x180005779  mov     [r11-40h], rax
0x18000577d  lea     r12, WPP_GLOBAL_Control
0x180005784  mov     rax, cs:WPP_GLOBAL_Control
0x18000578b  cmp     rax, r12
0x18000578e  jz      short loc_1800057B8
0x180005790  test    [rax+1Ch], r15b
0x180005794  jz      short loc_1800057B8
0x180005796  cmp     byte ptr [rax+19h], 5
0x18000579a  jb      short loc_1800057B8
0x18000579c  lea     edx, [r15+0Ch]
0x1800057a0  mov     [r11-78h], r9
0x1800057a4  lea     r9, [r11-48h]
0x1800057a8  mov     rcx, [rax+10h]; LoggerHandle
0x1800057ac  call    WPP_SF_aZs
0x1800057b1  mov     rax, cs:WPP_GLOBAL_Control
0x1800057b8  cmp     rax, r12
0x1800057bb  jz      short loc_18000580D
0x1800057bd  test    [rax+1Ch], r15b
0x1800057c1  jz      short loc_18000580D
0x1800057c3  mov     r13b, 4
0x1800057c6  cmp     [rax+19h], r13b
0x1800057ca  jb      short loc_180005810
0x1800057cc  call    cs:__imp_GetCurrentThread
0x1800057d2  mov     rcx, rax; hThread
0x1800057d5  call    cs:__imp_GetThreadPriority
0x1800057db  mov     ebx, eax
0x1800057dd  call    cs:__imp_GetCurrentProcess
0x1800057e3  mov     rcx, rax; hProcess
0x1800057e6  call    cs:__imp_GetPriorityClass
0x1800057ec  mov     [rsp+98h+var_70], ebx
0x1800057f0  mov     [rsp+98h+var_78], eax
0x1800057f4  mov     r9d, [rsi+0F0h]
0x1800057fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180005802  mov     rcx, [rcx+10h]
0x180005806  call    WPP_SF_LLL
0x18000580b  jmp     short loc_180005810
0x18000580d  mov     r13b, 4
0x180005810  xor     edx, edx; dwCoInit
0x180005812  xor     ecx, ecx; pvReserved
0x180005814  call    cs:__imp_CoInitializeEx
0x18000581a  mov     [rsp+98h+arg_10], eax
0x180005821  mov     [rsp+98h+var_50], eax
0x180005825  xor     r14d, r14d
0x180005828  test    eax, eax
0x18000582a  jns     short loc_180005869
0x18000582c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005833  cmp     rcx, r12
0x180005836  jz      short loc_180005864
0x180005838  test    [rcx+1Ch], r15b
0x18000583c  jz      short loc_180005864
0x18000583e  cmp     byte ptr [rcx+19h], 2
0x180005842  jb      short loc_180005864
0x180005844  lea     edx, [r14+27h]
0x180005848  mov     [rsp+98h+var_78], eax
0x18000584c  lea     r9, aHrCoinitInitia; "Hr = CoInit.Initialize( COINIT_MULTITHR"...
0x180005853  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x18000585a  mov     rcx, [rcx+10h]
0x18000585e  call    WPP_SF_sd
0x180005863  nop
0x180005864  jmp     loc_180005CEF
0x180005869  lea     rdi, [rsi+140h]
0x180005870  mov     [rdi+48h], r14
0x180005874  mov     rax, [rsi+88h]
0x18000587b  mov     [rsi+150h], rax
0x180005882  mov     eax, [rsi+124h]
0x180005888  mov     [rsi+158h], eax
0x18000588e  mov     eax, [rsi+128h]
0x180005894  mov     [rsi+15Ch], eax
0x18000589a  mov     eax, [rsi+12Ch]
0x1800058a0  mov     [rsi+160h], eax
0x1800058a6  mov     al, [rsi+11Ch]
0x1800058ac  mov     [rsi+145h], al
0x1800058b2  mov     al, [rsi+11Dh]
0x1800058b8  mov     [rsi+146h], al
0x1800058be  mov     eax, [rsi+130h]
0x1800058c4  mov     [rsi+164h], eax
0x1800058ca  mov     eax, [rsi+134h]
0x1800058d0  mov     [rsi+168h], eax
0x1800058d6  mov     eax, [rsi+138h]
0x1800058dc  mov     [rsi+16Ch], eax
0x1800058e2  imul    eax, [rsi+13Ch], 36EE80h
0x1800058ec  mov     [rsi+170h], eax
0x1800058f2  lea     rcx, [rdi+34h]; pguid
0x1800058f6  call    cs:__imp_CoCreateGuid
0x1800058fc  mov     ecx, [rsi+0F0h]
0x180005902  cmp     ecx, r15d
0x180005905  mov     eax, r15d
0x180005908  jz      short loc_180005910
0x18000590a  mov     eax, [rsi+118h]
0x180005910  mov     [rdi], eax
0x180005912  mov     [rsi+148h], ecx
0x180005918  mov     al, [rsi+0F4h]
0x18000591e  mov     [rsi+144h], al
0x180005924  mov     rcx, rdi; struct _SCRUB_ENVIRONMENT *
0x180005927  call    ?EventWriteTaskStart@@YAXPEAU_SCRUB_ENVIRONMENT@@@Z; EventWriteTaskStart(_SCRUB_ENVIRONMENT *)
0x18000592c  mov     rdx, rsi
0x18000592f  lea     rcx, [rsp+98h+var_60]
0x180005934  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180005939  lea     rbx, [rsp+98h+var_60]
0x18000593e  mov     [rsp+98h+arg_18], rbx
0x180005946  cmp     [rsi+0F0h], r14d
0x18000594d  jnz     loc_180005B05
0x180005953  mov     ecx, r15d
0x180005956  call    ?EnableTaskTrigger@@YAJW4TaskTriggerOption@@PEBG@Z; EnableTaskTrigger(TaskTriggerOption,ushort const *)
0x18000595b  mov     [rsp+98h+var_50], eax
0x18000595f  test    eax, eax
0x180005961  jns     short loc_180005993
0x180005963  mov     rcx, cs:WPP_GLOBAL_Control
0x18000596a  cmp     rcx, r12
0x18000596d  jz      short loc_180005993
0x18000596f  test    [rcx+1Ch], r15b
0x180005973  jz      short loc_180005993
0x180005975  cmp     byte ptr [rcx+19h], 2
0x180005979  jb      short loc_180005993
0x18000597b  mov     edx, 28h ; '('
0x180005980  mov     r9d, eax
0x180005983  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x18000598a  mov     rcx, [rcx+10h]
0x18000598e  call    WPP_SF_d
0x180005993  xor     edx, edx; dwMilliseconds
0x180005995  mov     rcx, [rsi+0E0h]; hHandle
0x18000599c  call    cs:__imp_WaitForSingleObject
0x1800059a2  cmp     eax, 102h
0x1800059a7  jnz     short loc_1800059E0
0x1800059a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059b0  cmp     rcx, r12
0x1800059b3  jz      short loc_1800059D6
0x1800059b5  test    [rcx+1Ch], r15b
0x1800059b9  jz      short loc_1800059D6
0x1800059bb  cmp     [rcx+19h], r13b
0x1800059bf  jb      short loc_1800059D6
0x1800059c1  mov     edx, 29h ; ')'
0x1800059c6  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x1800059cd  mov     rcx, [rcx+10h]
0x1800059d1  call    WPP_SF_
0x1800059d6  mov     edi, 800704DAh
0x1800059db  jmp     loc_180005AFC
0x1800059e0  test    eax, eax
0x1800059e2  jnz     loc_180005AE7
0x1800059e8  mov     [rsi+0D8h], r15b
0x1800059ef  xor     r8d, r8d; pftTimeout
0x1800059f2  mov     rdx, [rsi+98h]; h
0x1800059f9  mov     rcx, [rsi+0A8h]; pwa
0x180005a00  call    cs:__imp_SetThreadpoolWait
0x180005a06  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a0d  cmp     rcx, r12
0x180005a10  jz      short loc_180005A34
0x180005a12  test    [rcx+1Ch], r15b
0x180005a16  jz      short loc_180005A34
0x180005a18  cmp     [rcx+19h], r13b
0x180005a1c  jb      short loc_180005A34
0x180005a1e  mov     edx, 2Ah ; '*'
0x180005a23  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180005a2a  mov     rcx, [rcx+10h]
0x180005a2e  call    WPP_SF_
0x180005a33  nop
0x180005a34  mov     ecx, 210h; Size
0x180005a39  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005a3e  mov     [rsp+98h+arg_8], rax
0x180005a46  test    rax, rax
0x180005a49  jz      short loc_180005A68
0x180005a4b  mov     rcx, rsi
0x180005a4e  lea     r9, [rsi+8]
0x180005a52  neg     rcx
0x180005a55  sbb     r8, r8
0x180005a58  and     r8, r9; struct ISystemScanNotify *
0x180005a5b  mov     rdx, rdi; struct _SCRUB_ENVIRONMENT *
0x180005a5e  mov     rcx, rax; pv
0x180005a61  call    ??0CSystemScanner@@QEAA@PEAU_SCRUB_ENVIRONMENT@@PEAUISystemScanNotify@@@Z; CSystemScanner::CSystemScanner(_SCRUB_ENVIRONMENT *,ISystemScanNotify *)
0x180005a66  jmp     short loc_180005A6B
0x180005a68  mov     rax, r14
0x180005a6b  mov     [rsi+190h], rax
0x180005a72  mov     r8, [rsi+78h]; void *
0x180005a76  mov     rdx, [rsi+48h]; void *
0x180005a7a  mov     rcx, rax; this
0x180005a7d  call    ?StartSystemScan@CSystemScanner@@QEAAJPEAX0@Z; CSystemScanner::StartSystemScan(void *,void *)
0x180005a82  mov     [rsp+98h+var_50], eax
0x180005a86  test    eax, eax
0x180005a88  cmovns  rbx, r14
0x180005a8c  mov     [rsp+98h+arg_18], rbx
0x180005a94  jmp     short loc_180005AAD
0x180005a96  jmp     short $+2
0x180005a98  mov     rsi, [rsp+98h+arg_0]
0x180005aa0  lea     r12, WPP_GLOBAL_Control
0x180005aa7  mov     r15d, 1
0x180005aad  mov     edi, [rsp+98h+var_50]
0x180005ab1  test    edi, edi
0x180005ab3  jns     loc_180005CDA
0x180005ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ac0  cmp     rcx, r12
0x180005ac3  jz      loc_180005CC1
0x180005ac9  test    [rcx+1Ch], r15b
0x180005acd  jz      loc_180005CC1
0x180005ad3  cmp     byte ptr [rcx+19h], 2
0x180005ad7  jb      loc_180005CC1
0x180005add  mov     edx, 2Bh ; '+'
0x180005ae2  jmp     loc_180005CAE
0x180005ae7  call    cs:__imp_GetLastError
0x180005aed  mov     edi, eax
0x180005aef  test    eax, eax
0x180005af1  jle     short loc_180005AFC
0x180005af3  movzx   edi, ax
0x180005af6  or      edi, 80070000h
0x180005afc  mov     [rsp+98h+var_50], edi
0x180005b00  jmp     loc_180005CC1
0x180005b05  mov     rcx, [rsi+98h]; hEvent
0x180005b0c  call    cs:__imp_SetEvent
0x180005b12  mov     edi, 0D000042Bh
0x180005b17  mov     [rsp+98h+var_50], edi
0x180005b1b  mov     eax, r14d
0x180005b1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b25  mov     dword ptr [rsp+98h+arg_8], eax
0x180005b2c  cmp     eax, 258h
0x180005b31  jnb     short loc_180005BA7
0x180005b33  mov     edx, 3E8h; dwMilliseconds
0x180005b38  mov     rcx, [rsi+0E0h]; hHandle
0x180005b3f  call    cs:__imp_WaitForSingleObject
0x180005b45  test    eax, eax
0x180005b47  jz      short loc_180005B91
0x180005b49  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b50  cmp     rcx, r12
0x180005b53  jz      short loc_180005B85
0x180005b55  test    [rcx+1Ch], r15b
0x180005b59  jz      short loc_180005B85
0x180005b5b  cmp     [rcx+19h], r13b
0x180005b5f  jb      short loc_180005B85
0x180005b61  mov     edx, 2Ch ; ','
0x180005b66  mov     r9d, dword ptr [rsp+98h+arg_8]
0x180005b6e  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180005b75  mov     rcx, [rcx+10h]
0x180005b79  call    WPP_SF_d
0x180005b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b85  mov     eax, dword ptr [rsp+98h+arg_8]
0x180005b8c  add     eax, r15d
0x180005b8f  jmp     short loc_180005B25
0x180005b91  mov     [rsi+0D8h], r15b
0x180005b98  mov     edi, r14d
0x180005b9b  mov     [rsp+98h+var_50], r14d
0x180005ba0  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ba7  test    edi, edi
0x180005ba9  jns     short loc_180005BE5
0x180005bab  cmp     rcx, r12
0x180005bae  jz      loc_180005CC5
0x180005bb4  test    [rcx+1Ch], r15b
0x180005bb8  jz      loc_180005CC5
0x180005bbe  cmp     byte ptr [rcx+19h], 2
0x180005bc2  jb      loc_180005CC5
0x180005bc8  mov     edx, 2Dh ; '-'
0x180005bcd  mov     r9d, edi
0x180005bd0  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180005bd7  mov     rcx, [rcx+10h]
0x180005bdb  call    WPP_SF_d
0x180005be0  jmp     loc_180005CC5
0x180005be5  cmp     rcx, r12
0x180005be8  jz      short loc_180005C0C
0x180005bea  test    [rcx+1Ch], r15b
0x180005bee  jz      short loc_180005C0C
0x180005bf0  cmp     [rcx+19h], r13b
0x180005bf4  jb      short loc_180005C0C
0x180005bf6  mov     edx, 2Eh ; '.'
0x180005bfb  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180005c02  mov     rcx, [rcx+10h]
0x180005c06  call    WPP_SF_
0x180005c0b  nop
0x180005c0c  mov     ecx, 210h; Size
0x180005c11  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005c16  mov     [rsp+98h+arg_8], rax
0x180005c1e  test    rax, rax
  ... truncated ...
```
