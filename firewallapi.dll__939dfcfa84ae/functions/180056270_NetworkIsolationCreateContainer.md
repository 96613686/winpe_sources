# NetworkIsolationCreateContainer

- ea: `0x180056270`
- end: `0x18005669a`
- name: `NetworkIsolationCreateContainer`
- size: `1066`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005e0c`
- `0x18000ea10`
- `0x180026798`
- `0x1800294b0`
- `0x18003336c`
- `0x180056270`
- `0x180058a34`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180056566`
- `RPCRT4!NdrClientCall3` at `0x180056566`
- `RPCRT4!RpcBindingFree` at `0x180056628`
- `RPCRT4!RpcBindingFree` at `0x180056628`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800563ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005648d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800563ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005648d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005647d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005647d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800565e1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800565e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180056380`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180056380`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800563d4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800563d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800563ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800563ba`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800563a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800563a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180056317`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180056317`
- `fwbase!FwBaseFree` at `0x180056609`
- `fwbase!FwBaseFree` at `0x180056609`
- `fwbase!FwCloseHandle` at `0x1800565f5`
- `fwbase!FwCloseHandle` at `0x1800565f5`
- `fwbase!FwHResultToWindowsError` at `0x180056445`
- `fwbase!FwHResultToWindowsError` at `0x180056445`
- `fwbase!FwGetTokenInformation` at `0x180056437`
- `fwbase!FwGetTokenInformation` at `0x180056437`

## pseudocode

```c
__int64 __fastcall NetworkIsolationCreateContainer(
        int a1,
        const wchar_t *a2,
        const wchar_t *a3,
        int a4,
        __int64 a5,
        int a6)
{
  char v6; // r15
  int v10; // r12d
  const wchar_t *v11; // r8
  const wchar_t *v12; // rdx
  HANDLE CurrentThread; // rax
  BOOL v14; // eax
  int v15; // r15d
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  DWORD v18; // ebx
  FwPolicy2 *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  unsigned int TokenInformation; // eax
  unsigned int Pointer; // eax
  unsigned int v24; // eax
  __int64 v25; // rcx
  __int64 v27; // [rsp+20h] [rbp-C8h]
  __int64 v28; // [rsp+40h] [rbp-A8h]
  void *TokenHandle; // [rsp+90h] [rbp-58h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp-50h] BYREF
  _QWORD *v34; // [rsp+A0h] [rbp-48h] BYREF

  v6 = a4;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 594, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  Binding = 0;
  v34 = 0;
  TokenHandle = 0;
  v10 = 0;
  GetTickCount64();
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v11 = a3;
    if ( !a3 )
      v11 = L"<null>";
    v12 = a2;
    if ( !a2 )
      v12 = L"<null>";
    WPP_SF_DSSDqD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v12,
      (_DWORD)v11,
      a1,
      (__int64)v12,
      (__int64)v11,
      v6,
      a5,
      a6);
  }
  CurrentThread = GetCurrentThread();
  v14 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
  if ( v14 )
  {
    v15 = 1;
  }
  else
  {
    v15 = 0;
    CurrentProcess = GetCurrentProcess();
    v14 = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  }
  if ( v14 )
  {
    TokenInformation = FwGetTokenInformation(TokenHandle, 1, &v34, 0);
    LastError = FwHResultToWindowsError(TokenInformation);
    v18 = LastError;
    if ( !LastError )
    {
      if ( v15 == 1 )
      {
        if ( !RevertToSelf() )
        {
          LastError = GetLastError();
          v18 = LastError;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v20 = 598;
            goto LABEL_18;
          }
          goto LABEL_38;
        }
        v10 = 1;
      }
      LastError = Int_FWLocalRpcBindingCreate(&Binding);
      v18 = LastError;
      if ( LastError )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v20 = 599;
          goto LABEL_18;
        }
      }
      else
      {
        LODWORD(v28) = a4;
        LODWORD(v27) = a1;
        Pointer = (unsigned int)NdrClientCall3(
                                  (MIDL_STUBLESS_PROXY_INFO *)&FW_NET_ISO_DIAG_ProxyInfo,
                                  2u,
                                  0,
                                  Binding,
                                  v27,
                                  *v34,
                                  a2,
                                  a3,
                                  v28,
                                  a5,
                                  a6).Pointer;
        v18 = Pointer;
        if ( Pointer )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v20 = 600;
            v21 = Pointer;
            goto LABEL_37;
          }
        }
      }
      goto LABEL_38;
    }
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v20 = 597;
      goto LABEL_18;
    }
  }
  else
  {
    LastError = GetLastError();
    v18 = LastError;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v20 = 596;
LABEL_18:
      v21 = LastError;
LABEL_37:
      WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v21);
    }
  }
LABEL_38:
  if ( v15 == 1 && v10 == 1 )
    SetThreadToken(0, TokenHandle);
  FwCloseHandle(TokenHandle);
  FwBaseFree(v34);
  if ( Binding )
  {
    v24 = RpcBindingFree(&Binding);
    if ( v24 )
      MicrosoftTelemetryAssertTriggeredArgs(v25, v24);
    Binding = 0;
  }
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 601, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v18);
  return v18;
}

```

## disassembly

```asm
0x180056270  push    rbx
0x180056272  push    rsi
0x180056273  push    r12
0x180056275  push    r13
0x180056277  push    r14
0x180056279  push    r15
0x18005627b  sub     rsp, 0B8h
0x180056282  mov     rax, cs:__security_cookie
0x180056289  xor     rax, rsp
0x18005628c  mov     [rsp+0E8h+var_40], rax
0x180056294  mov     r15d, r9d
0x180056297  mov     [rsp+0E8h+var_80], r9d
0x18005629c  mov     rbx, r8
0x18005629f  mov     [rsp+0E8h+var_68], rbx
0x1800562a7  mov     r13, rdx
0x1800562aa  mov     esi, ecx
0x1800562ac  mov     [rsp+0E8h+var_7C], ecx
0x1800562b0  mov     rax, [rsp+0E8h+arg_20]
0x1800562b8  mov     [rsp+0E8h+var_70], rax
0x1800562bd  lea     r14, WPP_GLOBAL_Control
0x1800562c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800562cb  cmp     rcx, r14
0x1800562ce  jz      short loc_1800562EB
0x1800562d0  test    byte ptr [rcx+1Ch], 8
0x1800562d4  jz      short loc_1800562EB
0x1800562d6  mov     edx, 252h
0x1800562db  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800562e2  mov     rcx, [rcx+10h]
0x1800562e6  call    WPP_SF_
0x1800562eb  mov     [rsp+0E8h+Binding], 0
0x1800562f7  mov     [rsp+0E8h+var_48], 0
0x180056303  mov     [rsp+0E8h+TokenHandle], 0
0x18005630f  xor     r12d, r12d
0x180056312  mov     [rsp+0E8h+var_84], r12d
0x180056317  call    cs:__imp_GetTickCount64
0x18005631e  nop     dword ptr [rax+rax+00h]
0x180056323  mov     rcx, cs:WPP_GLOBAL_Control
0x18005632a  cmp     rcx, r14
0x18005632d  jz      short loc_180056380
0x18005632f  test    byte ptr [rcx+1Ch], 4
0x180056333  jz      short loc_180056380
0x180056335  lea     rax, aNull; "<null>"
0x18005633c  mov     r8, rbx
0x18005633f  test    rbx, rbx
0x180056342  cmovz   r8, rax
0x180056346  mov     rdx, r13
0x180056349  test    r13, r13
0x18005634c  cmovz   rdx, rax
0x180056350  mov     eax, [rsp+0E8h+arg_28]
0x180056357  mov     dword ptr [rsp+0E8h+var_A8], eax
0x18005635b  mov     rax, [rsp+0E8h+var_70]
0x180056360  mov     [rsp+0E8h+var_B0], rax
0x180056365  mov     dword ptr [rsp+0E8h+var_B8], r15d
0x18005636a  mov     [rsp+0E8h+var_C0], r8
0x18005636f  mov     [rsp+0E8h+var_C8], rdx
0x180056374  mov     r9d, esi
0x180056377  mov     rcx, [rcx+10h]
0x18005637b  call    WPP_SF_DSSDqD
0x180056380  call    cs:__imp_GetCurrentThread
0x180056387  nop     dword ptr [rax+rax+00h]
0x18005638c  mov     rcx, rax; ThreadHandle
0x18005638f  lea     r9, [rsp+0E8h+TokenHandle]; TokenHandle
0x180056397  mov     esi, 1
0x18005639c  mov     r8d, esi; OpenAsSelf
0x18005639f  lea     edx, [rsi+0Bh]; DesiredAccess
0x1800563a2  call    cs:__imp_OpenThreadToken
0x1800563a9  nop     dword ptr [rax+rax+00h]
0x1800563ae  test    eax, eax
0x1800563b0  jnz     short loc_1800563E2
0x1800563b2  xor     r15d, r15d
0x1800563b5  mov     [rsp+0E8h+var_88], r15d
0x1800563ba  call    cs:__imp_GetCurrentProcess
0x1800563c1  nop     dword ptr [rax+rax+00h]
0x1800563c6  mov     rcx, rax; ProcessHandle
0x1800563c9  lea     r8, [rsp+0E8h+TokenHandle]; TokenHandle
0x1800563d1  lea     edx, [rsi+7]; DesiredAccess
0x1800563d4  call    cs:__imp_OpenProcessToken
0x1800563db  nop     dword ptr [rax+rax+00h]
0x1800563e0  jmp     short loc_1800563E9
0x1800563e2  mov     r15d, esi
0x1800563e5  mov     [rsp+0E8h+var_88], esi
0x1800563e9  test    eax, eax
0x1800563eb  jnz     short loc_180056422
0x1800563ed  call    cs:__imp_GetLastError
0x1800563f4  nop     dword ptr [rax+rax+00h]
0x1800563f9  mov     ebx, eax
0x1800563fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180056402  cmp     rcx, r14
0x180056405  jz      loc_1800565CD
0x18005640b  test    [rcx+1Ch], sil
0x18005640f  jz      loc_1800565CD
0x180056415  mov     edx, 254h
0x18005641a  mov     r9d, eax
0x18005641d  jmp     loc_1800565BD
0x180056422  xor     r9d, r9d
0x180056425  lea     r8, [rsp+0E8h+var_48]
0x18005642d  mov     edx, esi
0x18005642f  mov     rcx, [rsp+0E8h+TokenHandle]
0x180056437  call    cs:__imp_FwGetTokenInformation
0x18005643e  nop     dword ptr [rax+rax+00h]
0x180056443  mov     ecx, eax
0x180056445  call    cs:__imp_FwHResultToWindowsError
0x18005644c  nop     dword ptr [rax+rax+00h]
0x180056451  mov     ebx, eax
0x180056453  test    eax, eax
0x180056455  jz      short loc_180056478
0x180056457  mov     rcx, cs:WPP_GLOBAL_Control
0x18005645e  cmp     rcx, r14
0x180056461  jz      loc_1800565CD
0x180056467  test    [rcx+1Ch], sil
0x18005646b  jz      loc_1800565CD
0x180056471  mov     edx, 255h
0x180056476  jmp     short loc_18005641A
0x180056478  cmp     r15d, esi
0x18005647b  jnz     short loc_1800564C6
0x18005647d  call    cs:__imp_RevertToSelf
0x180056484  nop     dword ptr [rax+rax+00h]
0x180056489  test    eax, eax
0x18005648b  jnz     short loc_1800564BF
0x18005648d  call    cs:__imp_GetLastError
0x180056494  nop     dword ptr [rax+rax+00h]
0x180056499  mov     ebx, eax
0x18005649b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800564a2  cmp     rcx, r14
0x1800564a5  jz      loc_1800565CD
0x1800564ab  test    [rcx+1Ch], sil
0x1800564af  jz      loc_1800565CD
0x1800564b5  mov     edx, 256h
0x1800564ba  jmp     loc_18005641A
0x1800564bf  mov     r12d, esi
0x1800564c2  mov     [rsp+0E8h+var_84], esi
0x1800564c6  lea     rcx, [rsp+0E8h+Binding]
0x1800564ce  call    Int_FWLocalRpcBindingCreate
0x1800564d3  mov     ebx, eax
0x1800564d5  test    eax, eax
0x1800564d7  jz      short loc_1800564FD
0x1800564d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800564e0  cmp     rcx, r14
0x1800564e3  jz      loc_1800565CD
0x1800564e9  test    [rcx+1Ch], sil
0x1800564ed  jz      loc_1800565CD
0x1800564f3  mov     edx, 257h
0x1800564f8  jmp     loc_18005641A
0x1800564fd  mov     rax, [rsp+0E8h+var_48]
0x180056505  mov     rcx, [rax]
0x180056508  mov     [rsp+0E8h+var_60], 0
0x180056514  mov     eax, [rsp+0E8h+arg_28]
0x18005651b  mov     [rsp+0E8h+var_98], eax
0x18005651f  mov     rax, [rsp+0E8h+var_70]
0x180056524  mov     [rsp+0E8h+var_A0], rax
0x180056529  mov     eax, [rsp+0E8h+var_80]
0x18005652d  mov     dword ptr [rsp+0E8h+var_A8], eax
0x180056531  mov     rax, [rsp+0E8h+var_68]
0x180056539  mov     [rsp+0E8h+var_B0], rax
0x18005653e  mov     [rsp+0E8h+var_B8], r13
0x180056543  mov     [rsp+0E8h+var_C0], rcx
0x180056548  mov     eax, [rsp+0E8h+var_7C]
0x18005654c  mov     dword ptr [rsp+0E8h+var_C8], eax
0x180056550  mov     r9, [rsp+0E8h+Binding]
0x180056558  xor     r8d, r8d; pReturnValue
0x18005655b  lea     edx, [r8+2]; nProcNum
0x18005655f  lea     rcx, ?FW_NET_ISO_DIAG_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180056566  call    cs:__imp_NdrClientCall3
0x18005656d  nop     dword ptr [rax+rax+00h]
0x180056572  mov     rbx, rax
0x180056575  mov     [rsp+0E8h+var_60], rax
0x18005657d  mov     [rsp+0E8h+var_78], eax
0x180056581  jmp     short loc_18005659F
0x180056583  mov     ebx, eax
0x180056585  mov     [rsp+0E8h+var_78], eax
0x180056589  lea     r14, WPP_GLOBAL_Control
0x180056590  mov     esi, 1
0x180056595  mov     r15d, [rsp+0E8h+var_88]
0x18005659a  mov     r12d, [rsp+0E8h+var_84]
0x18005659f  test    ebx, ebx
0x1800565a1  jz      short loc_1800565CD
0x1800565a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800565aa  cmp     rcx, r14
0x1800565ad  jz      short loc_1800565CD
0x1800565af  test    [rcx+1Ch], sil
0x1800565b3  jz      short loc_1800565CD
0x1800565b5  mov     edx, 258h
0x1800565ba  mov     r9d, ebx
0x1800565bd  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800565c4  mov     rcx, [rcx+10h]
0x1800565c8  call    WPP_SF_d
0x1800565cd  cmp     r15d, esi
0x1800565d0  jnz     short loc_1800565ED
0x1800565d2  cmp     r12d, esi
0x1800565d5  jnz     short loc_1800565ED
0x1800565d7  mov     rdx, [rsp+0E8h+TokenHandle]; Token
0x1800565df  xor     ecx, ecx; Thread
0x1800565e1  call    cs:__imp_SetThreadToken
0x1800565e8  nop     dword ptr [rax+rax+00h]
0x1800565ed  mov     rcx, [rsp+0E8h+TokenHandle]
0x1800565f5  call    cs:__imp_FwCloseHandle
0x1800565fc  nop     dword ptr [rax+rax+00h]
0x180056601  mov     rcx, [rsp+0E8h+var_48]
0x180056609  call    cs:__imp_FwBaseFree
0x180056610  nop     dword ptr [rax+rax+00h]
0x180056615  cmp     [rsp+0E8h+Binding], 0
0x18005661e  jz      short loc_18005664B
0x180056620  lea     rcx, [rsp+0E8h+Binding]; Binding
0x180056628  call    cs:__imp_RpcBindingFree
0x18005662f  nop     dword ptr [rax+rax+00h]
0x180056634  test    eax, eax
0x180056636  jz      short loc_18005663F
0x180056638  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcBindingFree")
0x18005663a  call    MicrosoftTelemetryAssertTriggeredArgs
0x18005663f  mov     [rsp+0E8h+Binding], 0
0x18005664b  mov     rcx, cs:WPP_GLOBAL_Control
0x180056652  cmp     rcx, r14
0x180056655  jz      short loc_180056675
0x180056657  test    byte ptr [rcx+1Ch], 8
0x18005665b  jz      short loc_180056675
0x18005665d  mov     edx, 259h
0x180056662  mov     r9d, ebx
0x180056665  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18005666c  mov     rcx, [rcx+10h]
0x180056670  call    WPP_SF_d
0x180056675  mov     eax, ebx
0x180056677  mov     rcx, [rsp+0E8h+var_40]
0x18005667f  xor     rcx, rsp; StackCookie
0x180056682  call    __security_check_cookie
0x180056687  add     rsp, 0B8h
0x18005668e  pop     r15
0x180056690  pop     r14
0x180056692  pop     r13
0x180056694  pop     r12
0x180056696  pop     rsi
0x180056697  pop     rbx
0x180056698  retn
0x180060408  push    rbp
0x18006040a  sub     rsp, 60h
0x18006040e  mov     rbp, rdx
0x180060411  mov     rcx, [rcx]
0x180060414  mov     ecx, [rcx]; ExceptionCode
0x180060416  call    cs:__imp_RpcExceptionFilter
0x18006041d  nop     dword ptr [rax+rax+00h]
0x180060422  nop
0x180060423  add     rsp, 60h
0x180060427  pop     rbp
0x180060428  retn
```
