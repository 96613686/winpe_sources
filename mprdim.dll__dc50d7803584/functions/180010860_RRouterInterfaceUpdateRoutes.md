# RRouterInterfaceUpdateRoutes

- ea: `0x180010860`
- end: `0x180010bb4`
- name: `RRouterInterfaceUpdateRoutes`
- size: `852`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800056c4`
- `0x18000def0`
- `0x180010860`
- `0x180019950`
- `0x180028640`
- `0x180045d40`
- `0x180045d7c`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010940`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010940`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800109e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800109e3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180010a0f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180010a0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010989`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010a29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010a37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010aa7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010af7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010b27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010989`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010a29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010a37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010aa7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010af7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010b27`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001096b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001096b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b1c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010b11`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010b11`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010919`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010919`
- `RPCRT4!RpcRevertToSelf` at `0x180010994`
- `RPCRT4!RpcRevertToSelf` at `0x180010a3f`
- `RPCRT4!RpcRevertToSelf` at `0x180010ab2`
- `RPCRT4!RpcRevertToSelf` at `0x180010994`
- `RPCRT4!RpcRevertToSelf` at `0x180010a3f`
- `RPCRT4!RpcRevertToSelf` at `0x180010ab2`
- `RPCRT4!RpcImpersonateClient` at `0x18001094b`
- `RPCRT4!RpcImpersonateClient` at `0x18001094b`

## string_xrefs

- `0x1800109b1`: `RRouterInterfaceUpdateRoutes: failed to revert to self. Error %d`
- `0x180010a54`: `RRouterInterfaceUpdateRoutes: failed to revert to self. Error %d`
- `0x180010b40`: `InterfaceUpdateRoutes: WaitForSingleObject returned %d`

## pseudocode

```c
DWORD __fastcall RRouterInterfaceUpdateRoutes(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        void *a4,
        DWORD CurrentProcessId)
{
  __int64 v6; // r13
  int v8; // r14d
  int v9; // edi
  HANDLE EventW; // rsi
  DWORD LastError; // ebx
  HANDLE v13; // rbx
  unsigned int v14; // eax
  __int64 *v15; // rdx
  HANDLE CurrentProcess; // rax
  DWORD v17; // r15d
  unsigned int v18; // eax
  CDimInterfaceTable *v19; // rcx
  __int64 v20; // rdx
  unsigned int updated; // eax
  WINBOOL AccessStatus; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v23; // [rsp+44h] [rbp-BCh]
  HANDLE TargetHandle; // [rsp+48h] [rbp-B8h] BYREF
  GUID ActivityId; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v23 = a3;
  v6 = a2;
  AccessStatus = 0;
  TargetHandle = 0;
  ActivityId = 0;
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v8 = 1;
  v9 = SetRasServerActivityId(&ActivityId);
  if ( DimSecObjAccessCheck(1u, &AccessStatus) || AccessStatus )
  {
    if ( v9 )
      ReSetActivityId(&ActivityId);
    return 5;
  }
  if ( a4 )
  {
    LastError = RpcImpersonateClient(0);
    if ( LastError )
    {
LABEL_50:
      if ( v9 )
        ReSetActivityId(&ActivityId);
      return LastError;
    }
    v8 = 0;
    EventW = a4;
  }
  else
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
    {
      if ( v9 )
        ReSetActivityId(&ActivityId);
      return GetLastError();
    }
    CurrentProcessId = GetCurrentProcessId();
  }
  v13 = OpenProcess(0xFFFFFu, 0, CurrentProcessId);
  if ( !v13 )
  {
    LastError = GetLastError();
    if ( v8 )
    {
      CloseHandle(EventW);
      goto LABEL_50;
    }
    v14 = RpcRevertToSelf();
    if ( !v14 )
      goto LABEL_50;
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_50;
    LOWORD(v26) = 0;
    FormatRRASErrorString(&v26, L"RRouterInterfaceUpdateRoutes: failed to revert to self. Error %d", v14);
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_50;
    v15 = RasDimTraceError;
LABEL_49:
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v15, &v26);
    goto LABEL_50;
  }
  CurrentProcess = GetCurrentProcess();
  if ( DuplicateHandle(v13, EventW, CurrentProcess, &TargetHandle, 0, 0, 2u) )
  {
    CloseHandle(v13);
    if ( !v8 )
    {
      LastError = RpcRevertToSelf();
      if ( LastError )
        goto LABEL_50;
    }
    if ( (_DWORD)v6 == -1 )
      v20 = -1;
    else
      v20 = v6;
    updated = CDimInterfaceTable::UpdateRoutes(v19, (void *const)v20, v23, EventW);
    LastError = updated;
    if ( updated && updated != 600 )
      CloseHandle(TargetHandle);
    if ( !a4 )
    {
      if ( (!LastError || LastError == 600) && WaitForSingleObject(EventW, 0xFFFFFFFF) == -1 )
        LastError = GetLastError();
      CloseHandle(EventW);
      if ( LastError == 600 )
        LastError = 0;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 8) == 0 )
      goto LABEL_50;
    LOWORD(v26) = 0;
    FormatRRASErrorString(&v26, L"InterfaceUpdateRoutes: WaitForSingleObject returned %d", LastError);
    if ( (Microsoft_Windows_RRASEnableBits & 8) == 0 )
      goto LABEL_50;
    v15 = RasDimTraceInfo;
    goto LABEL_49;
  }
  v17 = GetLastError();
  CloseHandle(v13);
  if ( v8 )
  {
    CloseHandle(EventW);
  }
  else
  {
    v18 = RpcRevertToSelf();
    if ( v18 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v26) = 0;
        FormatRRASErrorString(&v26, L"RRouterInterfaceUpdateRoutes: failed to revert to self. Error %d", v18);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, &v26);
      }
    }
  }
  if ( v9 )
    ReSetActivityId(&ActivityId);
  return v17;
}

```

## disassembly

```asm
0x180010860  mov     [rsp-8+arg_0], rbx
0x180010865  push    rbp
0x180010866  push    rsi
0x180010867  push    rdi
0x180010868  push    r12
0x18001086a  push    r13
0x18001086c  push    r14
0x18001086e  push    r15
0x180010870  lea     rbp, [rsp-770h]
0x180010878  sub     rsp, 870h
0x18001087f  mov     rax, cs:__security_cookie
0x180010886  xor     rax, rsp
0x180010889  mov     [rbp+7A0h+var_40], rax
0x180010890  mov     r12d, [rbp+7A0h+arg_20]
0x180010897  lea     rcx, [rsp+8A0h+var_83C]; void *
0x18001089c  xor     esi, esi
0x18001089e  mov     [rsp+8A0h+var_85C], r8d
0x1800108a3  mov     r13d, edx
0x1800108a6  xorps   xmm0, xmm0
0x1800108a9  xor     edx, edx; Val
0x1800108ab  mov     [rsp+8A0h+AccessStatus], esi
0x1800108af  mov     r8d, 7FCh; Size
0x1800108b5  mov     [rsp+8A0h+TargetHandle], rsi
0x1800108ba  movups  xmmword ptr [rsp+8A0h+ActivityId.Data1], xmm0
0x1800108bf  mov     [rsp+8A0h+var_840], esi
0x1800108c3  mov     r15, r9
0x1800108c6  call    memset_0
0x1800108cb  lea     rcx, [rsp+8A0h+ActivityId]; ActivityId
0x1800108d0  call    SetRasServerActivityId
0x1800108d5  lea     r14d, [rsi+1]
0x1800108d9  mov     edi, eax
0x1800108db  mov     ecx, r14d; DesiredAccess
0x1800108de  lea     rdx, [rsp+8A0h+AccessStatus]; AccessStatus
0x1800108e3  call    ?DimSecObjAccessCheck@@YAKKPEAK@Z; DimSecObjAccessCheck(ulong,ulong *)
0x1800108e8  test    eax, eax
0x1800108ea  jnz     short loc_1800108F2
0x1800108ec  cmp     [rsp+8A0h+AccessStatus], esi
0x1800108f0  jz      short loc_18001090A
0x1800108f2  test    edi, edi
0x1800108f4  jz      short loc_180010900
0x1800108f6  lea     rcx, [rsp+8A0h+ActivityId]; ActivityId
0x1800108fb  call    ReSetActivityId
0x180010900  mov     eax, 5
0x180010905  jmp     loc_180010B8A
0x18001090a  xor     ecx, ecx; BindingHandle
0x18001090c  test    r15, r15
0x18001090f  jnz     short loc_18001094B
0x180010911  xor     r9d, r9d; lpName
0x180010914  xor     r8d, r8d; bInitialState
0x180010917  xor     edx, edx; bManualReset
0x180010919  call    cs:__imp_CreateEventW
0x18001091f  mov     rsi, rax
0x180010922  test    rax, rax
0x180010925  jnz     short loc_180010940
0x180010927  test    edi, edi
0x180010929  jz      short loc_180010935
0x18001092b  lea     rcx, [rsp+8A0h+ActivityId]; ActivityId
0x180010930  call    ReSetActivityId
0x180010935  call    cs:__imp_GetLastError
0x18001093b  jmp     loc_180010B8A
0x180010940  call    cs:__imp_GetCurrentProcessId
0x180010946  mov     r12d, eax
0x180010949  jmp     short loc_180010961
0x18001094b  call    cs:__imp_RpcImpersonateClient
0x180010951  mov     ebx, eax
0x180010953  test    eax, eax
0x180010955  jnz     loc_180010B7A
0x18001095b  mov     r14d, esi
0x18001095e  mov     rsi, r15
0x180010961  mov     r8d, r12d; dwProcessId
0x180010964  xor     edx, edx; bInheritHandle
0x180010966  mov     ecx, 0FFFFFh; dwDesiredAccess
0x18001096b  call    cs:__imp_OpenProcess
0x180010971  mov     rbx, rax
0x180010974  test    rax, rax
0x180010977  jnz     short loc_1800109E3
0x180010979  call    cs:__imp_GetLastError
0x18001097f  mov     ebx, eax
0x180010981  test    r14d, r14d
0x180010984  jz      short loc_180010994
0x180010986  mov     rcx, rsi; hObject
0x180010989  call    cs:__imp_CloseHandle
0x18001098f  jmp     loc_180010B7A
0x180010994  call    cs:__imp_RpcRevertToSelf
0x18001099a  test    eax, eax
0x18001099c  jz      loc_180010B7A
0x1800109a2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800109a9  jz      loc_180010B7A
0x1800109af  xor     ecx, ecx
0x1800109b1  lea     rdx, aRrouterinterfa_6; "RRouterInterfaceUpdateRoutes: failed to"...
0x1800109b8  mov     word ptr [rsp+8A0h+var_840], cx
0x1800109bd  mov     r8d, eax
0x1800109c0  lea     rcx, [rsp+8A0h+var_840]
0x1800109c5  call    FormatRRASErrorString
0x1800109ca  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800109d1  jz      loc_180010B7A
0x1800109d7  lea     rdx, RasDimTraceError
0x1800109de  jmp     loc_180010B69
0x1800109e3  call    cs:__imp_GetCurrentProcess
0x1800109e9  mov     [rsp+8A0h+dwOptions], 2; dwOptions
0x1800109f1  lea     r9, [rsp+8A0h+TargetHandle]; lpTargetHandle
0x1800109f6  mov     r8, rax; hTargetProcessHandle
0x1800109f9  mov     [rsp+8A0h+bInheritHandle], 0; bInheritHandle
0x180010a01  mov     rdx, rsi; hSourceHandle
0x180010a04  mov     [rsp+8A0h+dwDesiredAccess], 0; dwDesiredAccess
0x180010a0c  mov     rcx, rbx; hSourceProcessHandle
0x180010a0f  call    cs:__imp_DuplicateHandle
0x180010a15  test    eax, eax
0x180010a17  jnz     loc_180010AA4
0x180010a1d  call    cs:__imp_GetLastError
0x180010a23  mov     rcx, rbx; hObject
0x180010a26  mov     r15d, eax
0x180010a29  call    cs:__imp_CloseHandle
0x180010a2f  test    r14d, r14d
0x180010a32  jz      short loc_180010A3F
0x180010a34  mov     rcx, rsi; hObject
0x180010a37  call    cs:__imp_CloseHandle
0x180010a3d  jmp     short loc_180010A8E
0x180010a3f  call    cs:__imp_RpcRevertToSelf
0x180010a45  test    eax, eax
0x180010a47  jz      short loc_180010A8E
0x180010a49  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180010a50  jz      short loc_180010A8E
0x180010a52  xor     ecx, ecx
0x180010a54  lea     rdx, aRrouterinterfa_6; "RRouterInterfaceUpdateRoutes: failed to"...
0x180010a5b  mov     word ptr [rsp+8A0h+var_840], cx
0x180010a60  mov     r8d, eax
0x180010a63  lea     rcx, [rsp+8A0h+var_840]
0x180010a68  call    FormatRRASErrorString
0x180010a6d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180010a74  jz      short loc_180010A8E
0x180010a76  lea     r8, [rsp+8A0h+var_840]
0x180010a7b  lea     rdx, RasDimTraceError
0x180010a82  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010a89  call    McTemplateU0z_EventWriteTransfer
0x180010a8e  test    edi, edi
0x180010a90  jz      short loc_180010A9C
0x180010a92  lea     rcx, [rsp+8A0h+ActivityId]; ActivityId
0x180010a97  call    ReSetActivityId
0x180010a9c  mov     eax, r15d
0x180010a9f  jmp     loc_180010B8A
0x180010aa4  mov     rcx, rbx; hObject
0x180010aa7  call    cs:__imp_CloseHandle
0x180010aad  test    r14d, r14d
0x180010ab0  jnz     short loc_180010AC2
0x180010ab2  call    cs:__imp_RpcRevertToSelf
0x180010ab8  mov     ebx, eax
0x180010aba  test    eax, eax
0x180010abc  jnz     loc_180010B7A
0x180010ac2  or      r12d, 0FFFFFFFFh
0x180010ac6  cmp     r13d, r12d
0x180010ac9  jnz     short loc_180010AD1
0x180010acb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180010acf  jmp     short loc_180010AD4
0x180010ad1  mov     rdx, r13; void *
0x180010ad4  mov     r8d, [rsp+8A0h+var_85C]; unsigned int
0x180010ad9  mov     r9, rsi; void *
0x180010adc  call    ?UpdateRoutes@CDimInterfaceTable@@QEAAKQEAXK0@Z; CDimInterfaceTable::UpdateRoutes(void * const,ulong,void * const)
0x180010ae1  mov     ebx, eax
0x180010ae3  mov     r14d, 258h
0x180010ae9  test    eax, eax
0x180010aeb  jz      short loc_180010AFD
0x180010aed  cmp     eax, r14d
0x180010af0  jz      short loc_180010AFD
0x180010af2  mov     rcx, [rsp+8A0h+TargetHandle]; hObject
0x180010af7  call    cs:__imp_CloseHandle
0x180010afd  test    r15, r15
0x180010b00  jnz     short loc_180010B35
0x180010b02  test    ebx, ebx
0x180010b04  jz      short loc_180010B0B
0x180010b06  cmp     ebx, r14d
0x180010b09  jnz     short loc_180010B24
0x180010b0b  mov     edx, r12d; dwMilliseconds
0x180010b0e  mov     rcx, rsi; hHandle
0x180010b11  call    cs:__imp_WaitForSingleObject
0x180010b17  cmp     eax, r12d
0x180010b1a  jnz     short loc_180010B24
0x180010b1c  call    cs:__imp_GetLastError
0x180010b22  mov     ebx, eax
0x180010b24  mov     rcx, rsi; hObject
0x180010b27  call    cs:__imp_CloseHandle
0x180010b2d  xor     eax, eax
0x180010b2f  cmp     ebx, r14d
0x180010b32  cmovz   ebx, eax
0x180010b35  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180010b3c  jz      short loc_180010B7A
0x180010b3e  xor     eax, eax
0x180010b40  lea     rdx, aInterfaceupdat; "InterfaceUpdateRoutes: WaitForSingleObj"...
0x180010b47  mov     r8d, ebx
0x180010b4a  mov     word ptr [rsp+8A0h+var_840], ax
0x180010b4f  lea     rcx, [rsp+8A0h+var_840]
0x180010b54  call    FormatRRASErrorString
0x180010b59  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180010b60  jz      short loc_180010B7A
0x180010b62  lea     rdx, RasDimTraceInfo
0x180010b69  lea     r8, [rsp+8A0h+var_840]
0x180010b6e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010b75  call    McTemplateU0z_EventWriteTransfer
0x180010b7a  test    edi, edi
0x180010b7c  jz      short loc_180010B88
0x180010b7e  lea     rcx, [rsp+8A0h+ActivityId]; ActivityId
0x180010b83  call    ReSetActivityId
0x180010b88  mov     eax, ebx
0x180010b8a  mov     rcx, [rbp+7A0h+var_40]
0x180010b91  xor     rcx, rsp; StackCookie
0x180010b94  call    __security_check_cookie
0x180010b99  mov     rbx, [rsp+8A0h+arg_0]
0x180010ba1  add     rsp, 870h
0x180010ba8  pop     r15
0x180010baa  pop     r14
0x180010bac  pop     r13
0x180010bae  pop     r12
0x180010bb0  pop     rdi
0x180010bb1  pop     rsi
0x180010bb2  pop     rbp
0x180010bb3  retn
```
