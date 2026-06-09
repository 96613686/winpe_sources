# RpcCreateWorkerSession

- ea: `0x1800575f0`
- end: `0x18005790e`
- name: `RpcCreateWorkerSession`
- size: `798`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x1800074c0`
- `0x180008f64`
- `0x180014c00`
- `0x180014f40`
- `0x180014ff0`
- `0x18004b460`
- `0x1800575f0`
- `0x180079354`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800576b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057705`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057742`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800576b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057705`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057742`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800576f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800576f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800578a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800578a1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800576a7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180057734`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800576a7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180057734`

## string_xrefs

- `0x180057642`: `RpcCreateWorkerSession`
- `0x180057668`: `RpcCreateWorkerSession`
- `0x1800576d6`: `RpcCreateWorkerSession`
- `0x18005769e`: `%SYSTEMROOT%\System32\WinLogon.exe -type Debug`
- `0x18005772a`: `%SYSTEMROOT%\System32\WinLogon.exe -type Debug`

## pseudocode

```c
__int64 __fastcall RpcCreateWorkerSession(
        __int64 a1,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int uBytes,
        unsigned int a6,
        struct _LUID a7,
        __int64 a8,
        unsigned int *a9)
{
  WCHAR *v9; // rsi
  signed int v12; // ebx
  DWORD v13; // eax
  __int64 v14; // rdi
  signed int LastError; // eax
  const char *v16; // rdx
  signed int v17; // eax
  DWORD v18; // eax
  signed int v19; // eax
  struct ISessionManagerInternal *v20; // rdi
  int InstanceOfWorkerTerminal; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  unsigned int v26; // [rsp+40h] [rbp-C0h] BYREF
  struct ISessionManagerInternal *v27; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  struct ITerminal *v29; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 *v31; // [rsp+68h] [rbp-98h]
  __int64 v32; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v33[592]; // [rsp+80h] [rbp-80h] BYREF

  v9 = 0;
  v31 = a4;
  v27 = 0;
  v30 = 0;
  v29 = 0;
  v32 = 0;
  v28 = 0;
  v26 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v33, 0, "RpcCreateWorkerSession");
  if ( !a9 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "pSessionId", "RpcCreateWorkerSession");
LABEL_3:
    v12 = -2147024809;
    goto LABEL_32;
  }
  if ( !a6 )
    goto LABEL_3;
  v13 = ExpandEnvironmentStringsW(L"%SYSTEMROOT%\\System32\\WinLogon.exe -type Debug", 0, 0);
  v14 = v13;
  if ( !v13 )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( v12 < 0 )
      goto LABEL_9;
  }
  v9 = (WCHAR *)LocalAlloc(0x40u, 2 * v14);
  if ( !v9 )
  {
    v17 = GetLastError();
    v12 = v17;
    if ( v17 > 0 )
      v12 = (unsigned __int16)v17 | 0x80070000;
    if ( v12 < 0 )
    {
      v16 = "LocalAlloc failed: 0x%x in %s";
      goto LABEL_10;
    }
  }
  v18 = ExpandEnvironmentStringsW(L"%SYSTEMROOT%\\System32\\WinLogon.exe -type Debug", v9, v14);
  if ( !v18 )
  {
    v19 = GetLastError();
    v12 = v19;
    if ( v19 > 0 )
      v12 = (unsigned __int16)v19 | 0x80070000;
    if ( v12 >= 0 )
      goto LABEL_21;
LABEL_9:
    v16 = "ExpandEnvironmentStrings failed: 0x%x in %s";
LABEL_10:
    _DbgPrintMessage(8, v16, (unsigned int)v12, "RpcCreateWorkerSession");
    goto LABEL_32;
  }
  if ( v18 > (unsigned int)v14 )
  {
    v12 = -2147024774;
    goto LABEL_9;
  }
LABEL_21:
  v27 = 0;
  ISessionManagerInternal::GetInstanceOfSessionManagerInternal(&v27);
  v20 = v27;
  InstanceOfWorkerTerminal = CWorkerTerminal::GetInstanceOfWorkerTerminal(a2, a3, v31, uBytes, a6, a7, &v29);
  v12 = InstanceOfWorkerTerminal;
  if ( InstanceOfWorkerTerminal >= 0 )
  {
    v22 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *, struct ITerminal *))(*(_QWORD *)v20 + 40LL))(
            v20,
            &v28,
            v29);
    v12 = v22;
    if ( v22 >= 0 )
    {
      v23 = (*(__int64 (__fastcall **)(__int64, __int64, WCHAR *, _QWORD, _QWORD))(*(_QWORD *)v28 + 32LL))(
              v28,
              0xFFFFFFFFLL,
              v9,
              0,
              0);
      v12 = v23;
      if ( v23 >= 0 )
      {
        (*(void (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)v20 + 32LL))(v20, &v30);
        (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v28 + 80LL))(v28, &v26);
        v24 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v30 + 32LL))(
                v30,
                5,
                v26,
                300000);
        v12 = v24;
        if ( v24 >= 0 )
          *a9 = v26;
        else
          _DbgPrintMessage(8, "WaitForSessionState failed: 0x%x in %s", (unsigned int)v24, "RpcCreateWorkerSession");
      }
      else
      {
        _DbgPrintMessage(8, "ptrSession->Start failed: 0x%x in %s", (unsigned int)v23, "RpcCreateWorkerSession");
      }
    }
    else
    {
      _DbgPrintMessage(8, "GetInstanceOfSession failed: 0x%x in %s", (unsigned int)v22, "RpcCreateWorkerSession");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "GetInstanceOfGlassTerminal failed: 0x%x in %s",
      (unsigned int)InstanceOfWorkerTerminal,
      "RpcCreateWorkerSession");
  }
LABEL_32:
  LocalFree(v9);
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v33);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v28);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v32);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v29);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v30);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v27);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800575f0  mov     [rsp-8+arg_0], rbx
0x1800575f5  push    rbp
0x1800575f6  push    rsi
0x1800575f7  push    rdi
0x1800575f8  push    r12
0x1800575fa  push    r13
0x1800575fc  push    r14
0x1800575fe  push    r15
0x180057600  lea     rbp, [rsp-1E0h]
0x180057608  sub     rsp, 2E0h
0x18005760f  mov     rax, cs:__security_cookie
0x180057616  xor     rax, rsp
0x180057619  mov     [rbp+210h+var_40], rax
0x180057620  mov     r15, [rbp+210h+arg_40]
0x180057627  lea     rcx, [rbp+210h+var_290]; this
0x18005762b  xor     esi, esi
0x18005762d  mov     [rsp+310h+var_2A8], r9
0x180057632  mov     r13d, r8d
0x180057635  mov     [rsp+310h+var_2C8], rsi
0x18005763a  mov     r12, rdx
0x18005763d  mov     [rsp+310h+var_2B0], rsi
0x180057642  lea     r8, aRpccreateworke; "RpcCreateWorkerSession"
0x180057649  mov     [rsp+310h+var_2B8], rsi
0x18005764e  xor     edx, edx; int
0x180057650  mov     [rsp+310h+var_2A0], rsi
0x180057655  mov     [rsp+310h+var_2C0], rsi
0x18005765a  mov     [rsp+310h+var_2D0], esi
0x18005765e  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x180057663  test    r15, r15
0x180057666  jnz     short loc_18005768F
0x180057668  lea     r9, aRpccreateworke; "RpcCreateWorkerSession"
0x18005766f  lea     r8, aPsessionid; "pSessionId"
0x180057676  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18005767d  lea     ecx, [rsi+8]; int
0x180057680  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180057685  mov     ebx, 80070057h
0x18005768a  jmp     loc_18005789E
0x18005768f  mov     r14d, [rbp+210h+arg_28]
0x180057696  test    r14d, r14d
0x180057699  jz      short loc_180057685
0x18005769b  xor     r8d, r8d; nSize
0x18005769e  lea     rcx, aSystemrootSyst; "%SYSTEMROOT%\\System32\\WinLogon.exe -t"...
0x1800576a5  xor     edx, edx; lpDst
0x1800576a7  call    cs:__imp_ExpandEnvironmentStringsW
0x1800576ad  mov     edi, eax
0x1800576af  test    eax, eax
0x1800576b1  jnz     short loc_1800576EC
0x1800576b3  call    cs:__imp_GetLastError
0x1800576b9  mov     ebx, eax
0x1800576bb  test    eax, eax
0x1800576bd  jle     short loc_1800576C8
0x1800576bf  movzx   ebx, ax
0x1800576c2  or      ebx, 80070000h
0x1800576c8  test    ebx, ebx
0x1800576ca  jns     short loc_1800576EC
0x1800576cc  lea     rdx, aExpandenvironm; "ExpandEnvironmentStrings failed: 0x%x i"...
0x1800576d3  mov     r8d, ebx
0x1800576d6  lea     r9, aRpccreateworke; "RpcCreateWorkerSession"
0x1800576dd  mov     ecx, 8; int
0x1800576e2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800576e7  jmp     loc_18005789E
0x1800576ec  mov     rdx, rdi
0x1800576ef  mov     ecx, 40h ; '@'; uFlags
0x1800576f4  add     rdx, rdx; uBytes
0x1800576f7  call    cs:__imp_LocalAlloc
0x1800576fd  mov     rsi, rax
0x180057700  test    rax, rax
0x180057703  jnz     short loc_180057727
0x180057705  call    cs:__imp_GetLastError
0x18005770b  mov     ebx, eax
0x18005770d  test    eax, eax
0x18005770f  jle     short loc_18005771A
0x180057711  movzx   ebx, ax
0x180057714  or      ebx, 80070000h
0x18005771a  test    ebx, ebx
0x18005771c  jns     short loc_180057727
0x18005771e  lea     rdx, aLocalallocFail; "LocalAlloc failed: 0x%x in %s"
0x180057725  jmp     short loc_1800576D3
0x180057727  mov     r8d, edi; nSize
0x18005772a  lea     rcx, aSystemrootSyst; "%SYSTEMROOT%\\System32\\WinLogon.exe -t"...
0x180057731  mov     rdx, rsi; lpDst
0x180057734  call    cs:__imp_ExpandEnvironmentStringsW
0x18005773a  test    eax, eax
0x18005773c  jnz     loc_1800577C3
0x180057742  call    cs:__imp_GetLastError
0x180057748  mov     ebx, eax
0x18005774a  test    eax, eax
0x18005774c  jle     short loc_180057757
0x18005774e  movzx   ebx, ax
0x180057751  or      ebx, 80070000h
0x180057757  test    ebx, ebx
0x180057759  js      loc_1800576CC
0x18005775f  lea     rcx, [rsp+310h+var_2C8]; struct ISessionManagerInternal **
0x180057764  mov     [rsp+310h+var_2C8], 0
0x18005776d  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x180057772  mov     rdi, [rsp+310h+var_2C8]
0x180057777  lea     rax, [rsp+310h+var_2B8]
0x18005777c  mov     r9d, dword ptr [rbp+210h+uBytes]; uBytes
0x180057783  mov     edx, r13d; unsigned int
0x180057786  mov     r8, [rsp+310h+var_2A8]; unsigned __int8 *
0x18005778b  mov     rcx, r12; unsigned __int8 *
0x18005778e  mov     [rsp+310h+var_2E0], rax; struct ITerminal **
0x180057793  mov     rax, qword ptr [rbp+210h+arg_30.LowPart]
0x18005779a  mov     qword ptr [rsp+310h+var_2E8.LowPart], rax; struct _LUID
0x18005779f  mov     [rsp+310h+var_2F0], r14d; unsigned int
0x1800577a4  mov     [rsp+310h+var_2C8], rdi
0x1800577a9  call    ?GetInstanceOfWorkerTerminal@CWorkerTerminal@@SAJPEAEK0KKU_LUID@@PEAPEAUITerminal@@@Z; CWorkerTerminal::GetInstanceOfWorkerTerminal(uchar *,ulong,uchar *,ulong,ulong,_LUID,ITerminal * *)
0x1800577ae  mov     ebx, eax
0x1800577b0  test    eax, eax
0x1800577b2  jns     short loc_1800577D1
0x1800577b4  mov     r8d, eax
0x1800577b7  lea     rdx, aGetinstanceofg; "GetInstanceOfGlassTerminal failed: 0x%x"...
0x1800577be  jmp     loc_1800576D6
0x1800577c3  cmp     eax, edi
0x1800577c5  jbe     short loc_18005775F
0x1800577c7  mov     ebx, 8007007Ah
0x1800577cc  jmp     loc_1800576CC
0x1800577d1  mov     rax, [rdi]
0x1800577d4  lea     rdx, [rsp+310h+var_2C0]
0x1800577d9  mov     r8, [rsp+310h+var_2B8]
0x1800577de  mov     rcx, rdi
0x1800577e1  mov     rax, [rax+28h]
0x1800577e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800577ea  mov     ebx, eax
0x1800577ec  test    eax, eax
0x1800577ee  jns     short loc_1800577FF
0x1800577f0  mov     r8d, eax
0x1800577f3  lea     rdx, aGetinstanceofs_8; "GetInstanceOfSession failed: 0x%x in %s"
0x1800577fa  jmp     loc_1800576D6
0x1800577ff  mov     rcx, [rsp+310h+var_2C0]
0x180057804  xor     r9d, r9d
0x180057807  mov     r8, rsi
0x18005780a  mov     qword ptr [rsp+310h+var_2F0], 0
0x180057813  or      edx, 0FFFFFFFFh
0x180057816  mov     rax, [rcx]
0x180057819  mov     rax, [rax+20h]
0x18005781d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057822  mov     ebx, eax
0x180057824  test    eax, eax
0x180057826  jns     short loc_180057837
0x180057828  mov     r8d, eax
0x18005782b  lea     rdx, aPtrsessionStar; "ptrSession->Start failed: 0x%x in %s"
0x180057832  jmp     loc_1800576D6
0x180057837  mov     rax, [rdi]
0x18005783a  lea     rdx, [rsp+310h+var_2B0]
0x18005783f  mov     rcx, rdi
0x180057842  mov     rax, [rax+20h]
0x180057846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005784b  mov     rcx, [rsp+310h+var_2C0]
0x180057850  lea     rdx, [rsp+310h+var_2D0]
0x180057855  mov     rax, [rcx]
0x180057858  mov     rax, [rax+50h]
0x18005785c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057861  mov     rcx, [rsp+310h+var_2B0]
0x180057866  mov     r9d, 493E0h
0x18005786c  mov     r8d, [rsp+310h+var_2D0]
0x180057871  mov     edx, 5
0x180057876  mov     rax, [rcx]
0x180057879  mov     rax, [rax+20h]
0x18005787d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057882  mov     ebx, eax
0x180057884  test    eax, eax
0x180057886  jns     short loc_180057897
0x180057888  mov     r8d, eax
0x18005788b  lea     rdx, aWaitforsession_3; "WaitForSessionState failed: 0x%x in %s"
0x180057892  jmp     loc_1800576D6
0x180057897  mov     eax, [rsp+310h+var_2D0]
0x18005789b  mov     [r15], eax
0x18005789e  mov     rcx, rsi; hMem
0x1800578a1  call    cs:__imp_LocalFree
0x1800578a7  lea     rcx, [rbp+210h+var_290]; this
0x1800578ab  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x1800578b0  lea     rcx, [rsp+310h+var_2C0]
0x1800578b5  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800578ba  lea     rcx, [rsp+310h+var_2A0]
0x1800578bf  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800578c4  lea     rcx, [rsp+310h+var_2B8]
0x1800578c9  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800578ce  lea     rcx, [rsp+310h+var_2B0]
0x1800578d3  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800578d8  lea     rcx, [rsp+310h+var_2C8]
0x1800578dd  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800578e2  mov     eax, ebx
0x1800578e4  mov     rcx, [rbp+210h+var_40]
0x1800578eb  xor     rcx, rsp; StackCookie
0x1800578ee  call    __security_check_cookie
0x1800578f3  mov     rbx, [rsp+310h+arg_0]
0x1800578fb  add     rsp, 2E0h
0x180057902  pop     r15
0x180057904  pop     r14
0x180057906  pop     r13
0x180057908  pop     r12
0x18005790a  pop     rdi
0x18005790b  pop     rsi
0x18005790c  pop     rbp
0x18005790d  retn
```
