# CADMCOMW::GetCallerPIDAndProcessName(ulong *,STRU *,void * *,int)

- ea: `0x180005514`
- end: `0x180005912`
- name: `?GetCallerPIDAndProcessName@CADMCOMW@@AEAAJPEAKPEAVSTRU@@PEAPEAXH@Z`
- size: `1022`
- prototype: `int(CADMCOMW *__hidden this, unsigned int *, struct STRU *, void **, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000238c`
- `0x180006c0c`

## callees

- `0x180005514`
- `0x180006198`
- `0x180010010`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x18000570b`
- `ADVAPI32!OpenThreadToken` at `0x18000570b`
- `ADVAPI32!RevertToSelf` at `0x18000571b`
- `ADVAPI32!RevertToSelf` at `0x18000571b`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180005894`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180005894`
- `ole32!CoGetCallContext` at `0x180005570`
- `ole32!CoGetCallContext` at `0x180005570`
- `KERNEL32!GetCurrentProcess` at `0x1800055ac`
- `KERNEL32!GetCurrentProcess` at `0x1800055ac`
- `KERNEL32!OpenProcess` at `0x180005792`
- `KERNEL32!OpenProcess` at `0x1800057cb`
- `KERNEL32!OpenProcess` at `0x180005792`
- `KERNEL32!OpenProcess` at `0x1800057cb`
- `KERNEL32!GetCurrentThread` at `0x1800056f6`
- `KERNEL32!GetCurrentThread` at `0x1800056f6`
- `KERNEL32!CloseHandle` at `0x180005778`
- `KERNEL32!CloseHandle` at `0x180005885`
- `KERNEL32!CloseHandle` at `0x1800058f1`
- `KERNEL32!CloseHandle` at `0x180005778`
- `KERNEL32!CloseHandle` at `0x180005885`
- `KERNEL32!CloseHandle` at `0x1800058f1`
- `KERNEL32!GetLastError` at `0x180005725`
- `KERNEL32!GetLastError` at `0x1800057a4`
- `KERNEL32!GetLastError` at `0x1800057d9`
- `KERNEL32!GetLastError` at `0x18000589e`
- `KERNEL32!GetLastError` at `0x180005725`
- `KERNEL32!GetLastError` at `0x1800057a4`
- `KERNEL32!GetLastError` at `0x1800057d9`
- `KERNEL32!GetLastError` at `0x18000589e`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180005634`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180005634`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800056a8`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800056a8`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x1800055d7`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x1800055d7`
- `IisRTL!PuDbgPrint` at `0x180005623`
- `IisRTL!PuDbgPrint` at `0x18000576e`
- `IisRTL!PuDbgPrint` at `0x180005822`
- `IisRTL!PuDbgPrint` at `0x1800058e7`
- `IisRTL!PuDbgPrint` at `0x180005623`
- `IisRTL!PuDbgPrint` at `0x18000576e`
- `IisRTL!PuDbgPrint` at `0x180005822`
- `IisRTL!PuDbgPrint` at `0x1800058e7`

## string_xrefs

- `0x18000560a`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180005767`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180005816`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x1800058e0`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x1800055ff`: `CADMCOMW::GetCallerPIDAndProcessName`
- `0x180005755`: `CADMCOMW::GetCallerPIDAndProcessName`
- `0x18000580b`: `CADMCOMW::GetCallerPIDAndProcessName`
- `0x1800058ce`: `CADMCOMW::GetCallerPIDAndProcessName`
- `0x1800057f7`: `OpenProcess() failed hr=0x%08x.\n`
- `0x1800058c3`: `ImpersonateLoggedOnUser() failed in GetCallerPIDAndProcessName hr=0x%08x.\n`

## pseudocode

```c
__int64 __fastcall CADMCOMW::GetCallerPIDAndProcessName(
        CADMCOMW *this,
        unsigned int *a2,
        struct STRU *a3,
        void **a4,
        int a5)
{
  HANDLE v5; // rdi
  HRESULT v9; // eax
  signed int ProcessName; // ebx
  HANDLE CurrentProcess; // rax
  int v12; // eax
  RPC_STATUS IsClientLocal; // eax
  int v14; // r12d
  const char *v15; // rax
  __int64 v16; // r8
  RPC_STATUS v17; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE v20; // rax
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  void *TokenHandle; // [rsp+30h] [rbp-10h] BYREF
  void *ppInterface; // [rsp+38h] [rbp-8h] BYREF
  unsigned int Pid; // [rsp+70h] [rbp+30h] BYREF
  int v28; // [rsp+74h] [rbp+34h]
  unsigned int ClientLocalFlag; // [rsp+78h] [rbp+38h] BYREF

  v28 = HIDWORD(this);
  v5 = 0;
  TokenHandle = 0;
  ppInterface = 0;
  ClientLocalFlag = 0;
  Pid = 0;
  if ( !a2 || !a3 )
  {
    ProcessName = -2147024809;
    goto LABEL_65;
  }
  if ( a4 )
    *a4 = 0;
  v9 = CoGetCallContext(&IID_IServerSecurity, &ppInterface);
  ProcessName = v9;
  if ( v9 < 0 )
  {
    if ( v9 != -2147417833 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
          6835,
          "CADMCOMW::GetCallerPIDAndProcessName",
          "CoGetCallContext() failed hr=0x%08x.\n",
          v9);
      goto LABEL_65;
    }
    ProcessName = 0;
    goto LABEL_8;
  }
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  if ( IsClientLocal != 1725 && IsClientLocal != 1702 )
  {
    v14 = 1;
    if ( IsClientLocal )
    {
      if ( IsClientLocal != 1764 )
      {
        if ( IsClientLocal > 0 )
          ProcessName = (unsigned __int16)IsClientLocal | 0x80070000;
        else
          ProcessName = IsClientLocal;
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          v15 = "I_RpcBindingIsClientLocal() failed hr=0x%08x.\n";
          v16 = 6871;
LABEL_55:
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
            v16,
            "CADMCOMW::GetCallerPIDAndProcessName",
            v15,
            ProcessName);
          goto LABEL_56;
        }
        goto LABEL_56;
      }
    }
    else if ( !ClientLocalFlag )
    {
      *a2 = -1;
      goto LABEL_9;
    }
    v17 = I_RpcBindingInqLocalClientPID(0, &Pid);
    if ( v17 != 1725 && v17 != 1702 )
    {
      if ( !v17 )
      {
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) && TokenHandle && !RevertToSelf() )
        {
          LastError = GetLastError();
          ProcessName = LastError;
          if ( LastError > 0 )
            ProcessName = (unsigned __int16)LastError | 0x80070000;
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
              6916,
              "CADMCOMW::GetCallerPIDAndProcessName",
              "RevertToSelf() failed hr=0x%08x.\n",
              ProcessName);
          CloseHandle(TokenHandle);
          TokenHandle = 0;
          goto LABEL_56;
        }
        v20 = OpenProcess(0x100400u, 0, Pid);
        v5 = v20;
        if ( v20 )
        {
          ProcessName = GetProcessName(v20, a3);
          if ( ProcessName < 0 )
            goto LABEL_65;
        }
        else
        {
          v21 = GetLastError();
          if ( v21 > 0 )
            v21 = (unsigned __int16)v21 | 0x80070000;
          v14 = 0;
          if ( v21 != -2147024891 || (v5 = OpenProcess(0x100000u, 0, Pid)) == 0 )
          {
            v22 = GetLastError();
            ProcessName = v22;
            if ( v22 > 0 )
              ProcessName = (unsigned __int16)v22 | 0x80070000;
            if ( (g_dwDebugFlags & 3) != 0 )
            {
              v15 = "OpenProcess() failed hr=0x%08x.\n";
              v16 = 6946;
              goto LABEL_55;
            }
            goto LABEL_56;
          }
        }
        *a2 = Pid;
        if ( a4 )
        {
          *a4 = v5;
          v5 = 0;
        }
        ProcessName = 0;
        goto LABEL_62;
      }
      if ( v17 > 0 )
        ProcessName = (unsigned __int16)v17 | 0x80070000;
      else
        ProcessName = v17;
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        v15 = "I_RpcBindingInqLocalClientPID() failed hr=0x%08x.\n";
        v16 = 6894;
        goto LABEL_55;
      }
LABEL_56:
      if ( ProcessName < 0 )
        goto LABEL_65;
LABEL_62:
      if ( !v14 )
        goto LABEL_65;
      goto LABEL_9;
    }
  }
LABEL_8:
  *a2 = CADMCOMW::sm_dwProcessIdThis;
LABEL_9:
  if ( !*((_DWORD *)a3 + 12) && *a2 == CADMCOMW::sm_dwProcessIdThis )
  {
    CurrentProcess = GetCurrentProcess();
    v12 = GetProcessName(CurrentProcess, a3);
    ProcessName = v12;
    if ( a5 )
    {
      if ( v12 < 0 )
        goto LABEL_65;
      ProcessName = STRU::Append(a3, L" - EWR");
    }
    if ( ProcessName >= 0 )
      ProcessName = 0;
  }
LABEL_65:
  if ( ppInterface )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
    ppInterface = 0;
  }
  if ( v5 )
    CloseHandle(v5);
  if ( TokenHandle )
  {
    if ( !ImpersonateLoggedOnUser(TokenHandle) )
    {
      v23 = GetLastError();
      ProcessName = v23;
      if ( v23 > 0 )
        ProcessName = (unsigned __int16)v23 | 0x80070000;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
          7018,
          "CADMCOMW::GetCallerPIDAndProcessName",
          "ImpersonateLoggedOnUser() failed in GetCallerPIDAndProcessName hr=0x%08x.\n",
          ProcessName);
    }
    CloseHandle(TokenHandle);
  }
  return (unsigned int)ProcessName;
}

```

## disassembly

```asm
0x180005514  mov     [rsp-28h+arg_10], rbx
0x180005519  mov     [rsp-28h+arg_18], rsi
0x18000551e  mov     qword ptr [rsp-28h+Pid], rcx
0x180005523  push    rbp
0x180005524  push    rdi
0x180005525  push    r12
0x180005527  push    r14
0x180005529  push    r15
0x18000552b  mov     rbp, rsp
0x18000552e  sub     rsp, 40h
0x180005532  xor     edi, edi
0x180005534  mov     rsi, r9
0x180005537  mov     [rbp+TokenHandle], rdi
0x18000553b  mov     r15, r8
0x18000553e  mov     [rbp+ppInterface], rdi
0x180005542  mov     r14, rdx
0x180005545  mov     [rbp+ClientLocalFlag], edi
0x180005548  mov     [rbp+Pid], edi
0x18000554b  test    rdx, rdx
0x18000554e  jz      loc_18000585B
0x180005554  test    r8, r8
0x180005557  jz      loc_18000585B
0x18000555d  test    r9, r9
0x180005560  jz      short loc_180005565
0x180005562  mov     [r9], rdi
0x180005565  lea     rdx, [rbp+ppInterface]; ppInterface
0x180005569  lea     rcx, IID_IServerSecurity; riid
0x180005570  call    cs:__imp_CoGetCallContext
0x180005576  mov     ebx, eax
0x180005578  test    eax, eax
0x18000557a  jns     loc_18000562E
0x180005580  cmp     eax, 80010117h
0x180005585  jnz     short loc_1800055EB
0x180005587  xor     ebx, ebx
0x180005589  mov     eax, cs:?sm_dwProcessIdThis@CADMCOMW@@2KA; ulong CADMCOMW::sm_dwProcessIdThis
0x18000558f  mov     [r14], eax
0x180005592  cmp     dword ptr [r15+30h], 0
0x180005597  jnz     loc_180005860
0x18000559d  mov     eax, cs:?sm_dwProcessIdThis@CADMCOMW@@2KA; ulong CADMCOMW::sm_dwProcessIdThis
0x1800055a3  cmp     [r14], eax
0x1800055a6  jnz     loc_180005860
0x1800055ac  call    cs:__imp_GetCurrentProcess
0x1800055b2  mov     rcx, rax; hProcess
0x1800055b5  mov     rdx, r15; struct STRU *
0x1800055b8  call    ?GetProcessName@@YAJPEAXPEAVSTRU@@@Z; GetProcessName(void *,STRU *)
0x1800055bd  cmp     [rbp+arg_20], 0
0x1800055c1  mov     ebx, eax
0x1800055c3  jz      short loc_1800055DF
0x1800055c5  test    eax, eax
0x1800055c7  js      loc_180005860
0x1800055cd  lea     rdx, aEwr; " - EWR"
0x1800055d4  mov     rcx, r15
0x1800055d7  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800055dd  mov     ebx, eax
0x1800055df  xor     eax, eax
0x1800055e1  test    ebx, ebx
0x1800055e3  cmovns  ebx, eax
0x1800055e6  jmp     loc_180005860
0x1800055eb  test    byte ptr cs:g_dwDebugFlags, 3
0x1800055f2  jz      loc_180005860
0x1800055f8  mov     rcx, cs:g_pDebug
0x1800055ff  lea     r9, aCadmcomwGetcal; "CADMCOMW::GetCallerPIDAndProcessName"
0x180005606  mov     [rsp+40h+var_18], eax
0x18000560a  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180005611  lea     rax, aCogetcallconte; "CoGetCallContext() failed hr=0x%08x.\n"
0x180005618  mov     r8d, 1AB3h
0x18000561e  mov     [rsp+40h+var_20], rax
0x180005623  call    cs:__imp_PuDbgPrint
0x180005629  jmp     loc_180005860
0x18000562e  lea     rdx, [rbp+ClientLocalFlag]; ClientLocalFlag
0x180005632  xor     ecx, ecx; BindingHandle
0x180005634  call    cs:__imp_I_RpcBindingIsClientLocal
0x18000563a  cmp     eax, 6BDh
0x18000563f  jz      loc_180005589
0x180005645  cmp     eax, 6A6h
0x18000564a  jz      loc_180005589
0x180005650  mov     r12d, 1
0x180005656  test    eax, eax
0x180005658  jnz     short loc_18000566B
0x18000565a  cmp     [rbp+ClientLocalFlag], edi
0x18000565d  jnz     short loc_1800056A2
0x18000565f  mov     dword ptr [r14], 0FFFFFFFFh
0x180005666  jmp     loc_180005592
0x18000566b  cmp     eax, 6E4h
0x180005670  jz      short loc_1800056A2
0x180005672  test    eax, eax
0x180005674  jg      short loc_18000567A
0x180005676  mov     ebx, eax
0x180005678  jmp     short loc_180005683
0x18000567a  movzx   ebx, ax
0x18000567d  or      ebx, 80070000h
0x180005683  test    byte ptr cs:g_dwDebugFlags, 3
0x18000568a  jz      loc_180005828
0x180005690  lea     rax, aIRpcbindingisc; "I_RpcBindingIsClientLocal() failed hr=0"...
0x180005697  mov     r8d, 1AD7h
0x18000569d  jmp     loc_180005804
0x1800056a2  lea     rdx, [rbp+Pid]; Pid
0x1800056a6  xor     ecx, ecx; Binding
0x1800056a8  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800056ae  cmp     eax, 6BDh
0x1800056b3  jz      loc_180005589
0x1800056b9  cmp     eax, 6A6h
0x1800056be  jz      loc_180005589
0x1800056c4  test    eax, eax
0x1800056c6  jz      short loc_1800056F6
0x1800056c8  jg      short loc_1800056CE
0x1800056ca  mov     ebx, eax
0x1800056cc  jmp     short loc_1800056D7
0x1800056ce  movzx   ebx, ax
0x1800056d1  or      ebx, 80070000h
0x1800056d7  test    byte ptr cs:g_dwDebugFlags, 3
0x1800056de  jz      loc_180005828
0x1800056e4  lea     rax, aIRpcbindinginq; "I_RpcBindingInqLocalClientPID() failed "...
0x1800056eb  mov     r8d, 1AEEh
0x1800056f1  jmp     loc_180005804
0x1800056f6  call    cs:__imp_GetCurrentThread
0x1800056fc  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180005700  mov     r8d, r12d; OpenAsSelf
0x180005703  mov     rcx, rax; ThreadHandle
0x180005706  mov     edx, 0Ch; DesiredAccess
0x18000570b  call    cs:__imp_OpenThreadToken
0x180005711  test    eax, eax
0x180005713  jz      short loc_180005787
0x180005715  cmp     [rbp+TokenHandle], rdi
0x180005719  jz      short loc_180005787
0x18000571b  call    cs:__imp_RevertToSelf
0x180005721  test    eax, eax
0x180005723  jnz     short loc_180005787
0x180005725  call    cs:__imp_GetLastError
0x18000572b  mov     ebx, eax
0x18000572d  test    eax, eax
0x18000572f  jle     short loc_18000573A
0x180005731  movzx   ebx, ax
0x180005734  or      ebx, 80070000h
0x18000573a  test    byte ptr cs:g_dwDebugFlags, 3
0x180005741  jz      short loc_180005774
0x180005743  mov     rcx, cs:g_pDebug
0x18000574a  lea     rax, aReverttoselfFa; "RevertToSelf() failed hr=0x%08x.\n"
0x180005751  mov     [rsp+40h+var_18], ebx
0x180005755  lea     r9, aCadmcomwGetcal; "CADMCOMW::GetCallerPIDAndProcessName"
0x18000575c  mov     r8d, 1B04h
0x180005762  mov     [rsp+40h+var_20], rax
0x180005767  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x18000576e  call    cs:__imp_PuDbgPrint
0x180005774  mov     rcx, [rbp+TokenHandle]; hObject
0x180005778  call    cs:__imp_CloseHandle
0x18000577e  mov     [rbp+TokenHandle], rdi
0x180005782  jmp     loc_180005828
0x180005787  mov     r8d, [rbp+Pid]; dwProcessId
0x18000578b  xor     edx, edx; bInheritHandle
0x18000578d  mov     ecx, 100400h; dwDesiredAccess
0x180005792  call    cs:__imp_OpenProcess
0x180005798  mov     rdi, rax
0x18000579b  test    rax, rax
0x18000579e  jnz     loc_18000582E
0x1800057a4  call    cs:__imp_GetLastError
0x1800057aa  test    eax, eax
0x1800057ac  jle     short loc_1800057B6
0x1800057ae  movzx   eax, ax
0x1800057b1  or      eax, 80070000h
0x1800057b6  xor     r12d, r12d
0x1800057b9  cmp     eax, 80070005h
0x1800057be  jnz     short loc_1800057D9
0x1800057c0  mov     r8d, [rbp+Pid]; dwProcessId
0x1800057c4  xor     edx, edx; bInheritHandle
0x1800057c6  mov     ecx, 100000h; dwDesiredAccess
0x1800057cb  call    cs:__imp_OpenProcess
0x1800057d1  mov     rdi, rax
0x1800057d4  test    rax, rax
0x1800057d7  jnz     short loc_18000583F
0x1800057d9  call    cs:__imp_GetLastError
0x1800057df  mov     ebx, eax
0x1800057e1  test    eax, eax
0x1800057e3  jle     short loc_1800057EE
0x1800057e5  movzx   ebx, ax
0x1800057e8  or      ebx, 80070000h
0x1800057ee  test    byte ptr cs:g_dwDebugFlags, 3
0x1800057f5  jz      short loc_180005828
0x1800057f7  lea     rax, aOpenprocessFai; "OpenProcess() failed hr=0x%08x.\n"
0x1800057fe  mov     r8d, 1B22h
0x180005804  mov     rcx, cs:g_pDebug
0x18000580b  lea     r9, aCadmcomwGetcal; "CADMCOMW::GetCallerPIDAndProcessName"
0x180005812  mov     [rsp+40h+var_18], ebx
0x180005816  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x18000581d  mov     [rsp+40h+var_20], rax
0x180005822  call    cs:__imp_PuDbgPrint
0x180005828  test    ebx, ebx
0x18000582a  js      short loc_180005860
0x18000582c  jmp     short loc_180005851
0x18000582e  mov     rdx, r15; struct STRU *
0x180005831  mov     rcx, rax; hProcess
0x180005834  call    ?GetProcessName@@YAJPEAXPEAVSTRU@@@Z; GetProcessName(void *,STRU *)
0x180005839  mov     ebx, eax
0x18000583b  test    eax, eax
0x18000583d  js      short loc_180005860
0x18000583f  mov     eax, [rbp+Pid]
0x180005842  mov     [r14], eax
0x180005845  test    rsi, rsi
0x180005848  jz      short loc_18000584F
0x18000584a  mov     [rsi], rdi
0x18000584d  xor     edi, edi
0x18000584f  xor     ebx, ebx
0x180005851  test    r12d, r12d
0x180005854  jz      short loc_180005860
0x180005856  jmp     loc_180005592
0x18000585b  mov     ebx, 80070057h
0x180005860  mov     rcx, [rbp+ppInterface]
0x180005864  test    rcx, rcx
0x180005867  jz      short loc_18000587D
0x180005869  mov     rax, [rcx]
0x18000586c  mov     rax, [rax+10h]
0x180005870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005875  mov     [rbp+ppInterface], 0
0x18000587d  test    rdi, rdi
0x180005880  jz      short loc_18000588B
0x180005882  mov     rcx, rdi; hObject
0x180005885  call    cs:__imp_CloseHandle
0x18000588b  mov     rcx, [rbp+TokenHandle]; hToken
0x18000588f  test    rcx, rcx
0x180005892  jz      short loc_1800058F7
0x180005894  call    cs:__imp_ImpersonateLoggedOnUser
0x18000589a  test    eax, eax
0x18000589c  jnz     short loc_1800058ED
0x18000589e  call    cs:__imp_GetLastError
0x1800058a4  mov     ebx, eax
0x1800058a6  test    eax, eax
0x1800058a8  jle     short loc_1800058B3
0x1800058aa  movzx   ebx, ax
0x1800058ad  or      ebx, 80070000h
0x1800058b3  test    byte ptr cs:g_dwDebugFlags, 3
0x1800058ba  jz      short loc_1800058ED
0x1800058bc  mov     rcx, cs:g_pDebug
0x1800058c3  lea     rax, aImpersonatelog; "ImpersonateLoggedOnUser() failed in Get"...
0x1800058ca  mov     [rsp+40h+var_18], ebx
0x1800058ce  lea     r9, aCadmcomwGetcal; "CADMCOMW::GetCallerPIDAndProcessName"
0x1800058d5  mov     r8d, 1B6Ah
0x1800058db  mov     [rsp+40h+var_20], rax
0x1800058e0  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x1800058e7  call    cs:__imp_PuDbgPrint
0x1800058ed  mov     rcx, [rbp+TokenHandle]; hObject
0x1800058f1  call    cs:__imp_CloseHandle
0x1800058f7  lea     r11, [rsp+40h+var_s0]
0x1800058fc  mov     eax, ebx
0x1800058fe  mov     rbx, [r11+40h]
0x180005902  mov     rsi, [r11+48h]
0x180005906  mov     rsp, r11
0x180005909  pop     r15
0x18000590b  pop     r14
0x18000590d  pop     r12
0x18000590f  pop     rdi
0x180005910  pop     rbp
0x180005911  retn
```
