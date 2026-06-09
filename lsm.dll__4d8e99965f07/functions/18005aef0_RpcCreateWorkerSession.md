# RpcCreateWorkerSession

- ea: `0x18005aef0`
- end: `0x18005b239`
- name: `RpcCreateWorkerSession`
- size: `841`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x1800077a0`
- `0x18000c684`
- `0x18000e8b0`
- `0x18000f260`
- `0x18000f320`
- `0x18004e850`
- `0x18005aef0`
- `0x18007dab4`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005afb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b017`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b060`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005afb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b017`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b060`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005b003`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005b003`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b1c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b1c5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005afa7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005b04c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005afa7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005b04c`

## string_xrefs

- `0x18005af42`: `RpcCreateWorkerSession`
- `0x18005af68`: `RpcCreateWorkerSession`
- `0x18005afe2`: `RpcCreateWorkerSession`
- `0x18005af9e`: `%SYSTEMROOT%\System32\WinLogon.exe -type Debug`
- `0x18005b042`: `%SYSTEMROOT%\System32\WinLogon.exe -type Debug`

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
0x18005aef0  mov     [rsp-8+arg_0], rbx
0x18005aef5  push    rbp
0x18005aef6  push    rsi
0x18005aef7  push    rdi
0x18005aef8  push    r12
0x18005aefa  push    r13
0x18005aefc  push    r14
0x18005aefe  push    r15
0x18005af00  lea     rbp, [rsp-1E0h]
0x18005af08  sub     rsp, 2E0h
0x18005af0f  mov     rax, cs:__security_cookie
0x18005af16  xor     rax, rsp
0x18005af19  mov     [rbp+210h+var_40], rax
0x18005af20  mov     r15, [rbp+210h+arg_40]
0x18005af27  lea     rcx, [rbp+210h+var_290]; this
0x18005af2b  xor     esi, esi
0x18005af2d  mov     [rsp+310h+var_2A8], r9
0x18005af32  mov     r13d, r8d
0x18005af35  mov     [rsp+310h+var_2C8], rsi
0x18005af3a  mov     r12, rdx
0x18005af3d  mov     [rsp+310h+var_2B0], rsi
0x18005af42  lea     r8, aRpccreateworke; "RpcCreateWorkerSession"
0x18005af49  mov     [rsp+310h+var_2B8], rsi
0x18005af4e  xor     edx, edx; int
0x18005af50  mov     [rsp+310h+var_2A0], rsi
0x18005af55  mov     [rsp+310h+var_2C0], rsi
0x18005af5a  mov     [rsp+310h+var_2D0], esi
0x18005af5e  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18005af63  test    r15, r15
0x18005af66  jnz     short loc_18005AF8F
0x18005af68  lea     r9, aRpccreateworke; "RpcCreateWorkerSession"
0x18005af6f  lea     r8, aPsessionid; "pSessionId"
0x18005af76  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18005af7d  lea     ecx, [rsi+8]; int
0x18005af80  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005af85  mov     ebx, 80070057h
0x18005af8a  jmp     loc_18005B1C2
0x18005af8f  mov     r14d, [rbp+210h+arg_28]
0x18005af96  test    r14d, r14d
0x18005af99  jz      short loc_18005AF85
0x18005af9b  xor     r8d, r8d; nSize
0x18005af9e  lea     rcx, aSystemrootSyst; "%SYSTEMROOT%\\System32\\WinLogon.exe -t"...
0x18005afa5  xor     edx, edx; lpDst
0x18005afa7  call    cs:__imp_ExpandEnvironmentStringsW
0x18005afae  nop     dword ptr [rax+rax+00h]
0x18005afb3  mov     edi, eax
0x18005afb5  test    eax, eax
0x18005afb7  jnz     short loc_18005AFF8
0x18005afb9  call    cs:__imp_GetLastError
0x18005afc0  nop     dword ptr [rax+rax+00h]
0x18005afc5  mov     ebx, eax
0x18005afc7  test    eax, eax
0x18005afc9  jle     short loc_18005AFD4
0x18005afcb  movzx   ebx, ax
0x18005afce  or      ebx, 80070000h
0x18005afd4  test    ebx, ebx
0x18005afd6  jns     short loc_18005AFF8
0x18005afd8  lea     rdx, aExpandenvironm; "ExpandEnvironmentStrings failed: 0x%x i"...
0x18005afdf  mov     r8d, ebx
0x18005afe2  lea     r9, aRpccreateworke; "RpcCreateWorkerSession"
0x18005afe9  mov     ecx, 8; int
0x18005afee  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005aff3  jmp     loc_18005B1C2
0x18005aff8  mov     rdx, rdi
0x18005affb  mov     ecx, 40h ; '@'; uFlags
0x18005b000  add     rdx, rdx; uBytes
0x18005b003  call    cs:__imp_LocalAlloc
0x18005b00a  nop     dword ptr [rax+rax+00h]
0x18005b00f  mov     rsi, rax
0x18005b012  test    rax, rax
0x18005b015  jnz     short loc_18005B03F
0x18005b017  call    cs:__imp_GetLastError
0x18005b01e  nop     dword ptr [rax+rax+00h]
0x18005b023  mov     ebx, eax
0x18005b025  test    eax, eax
0x18005b027  jle     short loc_18005B032
0x18005b029  movzx   ebx, ax
0x18005b02c  or      ebx, 80070000h
0x18005b032  test    ebx, ebx
0x18005b034  jns     short loc_18005B03F
0x18005b036  lea     rdx, aLocalallocFail; "LocalAlloc failed: 0x%x in %s"
0x18005b03d  jmp     short loc_18005AFDF
0x18005b03f  mov     r8d, edi; nSize
0x18005b042  lea     rcx, aSystemrootSyst; "%SYSTEMROOT%\\System32\\WinLogon.exe -t"...
0x18005b049  mov     rdx, rsi; lpDst
0x18005b04c  call    cs:__imp_ExpandEnvironmentStringsW
0x18005b053  nop     dword ptr [rax+rax+00h]
0x18005b058  test    eax, eax
0x18005b05a  jnz     loc_18005B0E7
0x18005b060  call    cs:__imp_GetLastError
0x18005b067  nop     dword ptr [rax+rax+00h]
0x18005b06c  mov     ebx, eax
0x18005b06e  test    eax, eax
0x18005b070  jle     short loc_18005B07B
0x18005b072  movzx   ebx, ax
0x18005b075  or      ebx, 80070000h
0x18005b07b  test    ebx, ebx
0x18005b07d  js      loc_18005AFD8
0x18005b083  lea     rcx, [rsp+310h+var_2C8]; struct ISessionManagerInternal **
0x18005b088  mov     [rsp+310h+var_2C8], 0
0x18005b091  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x18005b096  mov     rdi, [rsp+310h+var_2C8]
0x18005b09b  lea     rax, [rsp+310h+var_2B8]
0x18005b0a0  mov     r9d, dword ptr [rbp+210h+uBytes]; uBytes
0x18005b0a7  mov     edx, r13d; unsigned int
0x18005b0aa  mov     r8, [rsp+310h+var_2A8]; unsigned __int8 *
0x18005b0af  mov     rcx, r12; unsigned __int8 *
0x18005b0b2  mov     [rsp+310h+var_2E0], rax; struct ITerminal **
0x18005b0b7  mov     rax, qword ptr [rbp+210h+arg_30.LowPart]
0x18005b0be  mov     qword ptr [rsp+310h+var_2E8.LowPart], rax; struct _LUID
0x18005b0c3  mov     [rsp+310h+var_2F0], r14d; unsigned int
0x18005b0c8  mov     [rsp+310h+var_2C8], rdi
0x18005b0cd  call    ?GetInstanceOfWorkerTerminal@CWorkerTerminal@@SAJPEAEK0KKU_LUID@@PEAPEAUITerminal@@@Z; CWorkerTerminal::GetInstanceOfWorkerTerminal(uchar *,ulong,uchar *,ulong,ulong,_LUID,ITerminal * *)
0x18005b0d2  mov     ebx, eax
0x18005b0d4  test    eax, eax
0x18005b0d6  jns     short loc_18005B0F5
0x18005b0d8  mov     r8d, eax
0x18005b0db  lea     rdx, aGetinstanceofg; "GetInstanceOfGlassTerminal failed: 0x%x"...
0x18005b0e2  jmp     loc_18005AFE2
0x18005b0e7  cmp     eax, edi
0x18005b0e9  jbe     short loc_18005B083
0x18005b0eb  mov     ebx, 8007007Ah
0x18005b0f0  jmp     loc_18005AFD8
0x18005b0f5  mov     rax, [rdi]
0x18005b0f8  lea     rdx, [rsp+310h+var_2C0]
0x18005b0fd  mov     r8, [rsp+310h+var_2B8]
0x18005b102  mov     rcx, rdi
0x18005b105  mov     rax, [rax+28h]
0x18005b109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b10e  mov     ebx, eax
0x18005b110  test    eax, eax
0x18005b112  jns     short loc_18005B123
0x18005b114  mov     r8d, eax
0x18005b117  lea     rdx, aGetinstanceofs_8; "GetInstanceOfSession failed: 0x%x in %s"
0x18005b11e  jmp     loc_18005AFE2
0x18005b123  mov     rcx, [rsp+310h+var_2C0]
0x18005b128  xor     r9d, r9d
0x18005b12b  mov     r8, rsi
0x18005b12e  mov     qword ptr [rsp+310h+var_2F0], 0
0x18005b137  or      edx, 0FFFFFFFFh
0x18005b13a  mov     rax, [rcx]
0x18005b13d  mov     rax, [rax+20h]
0x18005b141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b146  mov     ebx, eax
0x18005b148  test    eax, eax
0x18005b14a  jns     short loc_18005B15B
0x18005b14c  mov     r8d, eax
0x18005b14f  lea     rdx, aPtrsessionStar; "ptrSession->Start failed: 0x%x in %s"
0x18005b156  jmp     loc_18005AFE2
0x18005b15b  mov     rax, [rdi]
0x18005b15e  lea     rdx, [rsp+310h+var_2B0]
0x18005b163  mov     rcx, rdi
0x18005b166  mov     rax, [rax+20h]
0x18005b16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b16f  mov     rcx, [rsp+310h+var_2C0]
0x18005b174  lea     rdx, [rsp+310h+var_2D0]
0x18005b179  mov     rax, [rcx]
0x18005b17c  mov     rax, [rax+50h]
0x18005b180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b185  mov     rcx, [rsp+310h+var_2B0]
0x18005b18a  mov     r9d, 493E0h
0x18005b190  mov     r8d, [rsp+310h+var_2D0]
0x18005b195  mov     edx, 5
0x18005b19a  mov     rax, [rcx]
0x18005b19d  mov     rax, [rax+20h]
0x18005b1a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b1a6  mov     ebx, eax
0x18005b1a8  test    eax, eax
0x18005b1aa  jns     short loc_18005B1BB
0x18005b1ac  mov     r8d, eax
0x18005b1af  lea     rdx, aWaitforsession_3; "WaitForSessionState failed: 0x%x in %s"
0x18005b1b6  jmp     loc_18005AFE2
0x18005b1bb  mov     eax, [rsp+310h+var_2D0]
0x18005b1bf  mov     [r15], eax
0x18005b1c2  mov     rcx, rsi; hMem
0x18005b1c5  call    cs:__imp_LocalFree
0x18005b1cc  nop     dword ptr [rax+rax+00h]
0x18005b1d1  lea     rcx, [rbp+210h+var_290]; this
0x18005b1d5  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18005b1da  lea     rcx, [rsp+310h+var_2C0]
0x18005b1df  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005b1e4  lea     rcx, [rsp+310h+var_2A0]
0x18005b1e9  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005b1ee  lea     rcx, [rsp+310h+var_2B8]
0x18005b1f3  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005b1f8  lea     rcx, [rsp+310h+var_2B0]
0x18005b1fd  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005b202  lea     rcx, [rsp+310h+var_2C8]
0x18005b207  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005b20c  mov     eax, ebx
0x18005b20e  mov     rcx, [rbp+210h+var_40]
0x18005b215  xor     rcx, rsp; StackCookie
0x18005b218  call    __security_check_cookie
0x18005b21d  mov     rbx, [rsp+310h+arg_0]
0x18005b225  add     rsp, 2E0h
0x18005b22c  pop     r15
0x18005b22e  pop     r14
0x18005b230  pop     r13
0x18005b232  pop     r12
0x18005b234  pop     rdi
0x18005b235  pop     rsi
0x18005b236  pop     rbp
0x18005b237  retn
```
