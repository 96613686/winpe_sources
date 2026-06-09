# ServiceStart

- ea: `0x18000f6c4`
- end: `0x18000f912`
- name: `ServiceStart`
- size: `590`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000f2b0`

## callees

- `0x180009e50`
- `0x18000b324`
- `0x18000e2f0`
- `0x18000f3e4`
- `0x18000f6c4`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f793`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7a5`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18000f827`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18000f827`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f7b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f905`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f7b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f905`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18000f8d0`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18000f8d0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000f805`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000f805`

## pseudocode

```c
__int64 ServiceStart()
{
  WCHAR *v0; // rax
  __int64 v1; // rdx
  const wchar_t *v2; // rcx
  __int128 v3; // xmm1
  __int128 v4; // xmm0
  __int128 v5; // xmm1
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  DWORD LastError; // ebx
  RPC_STATUS v18; // eax
  HLOCAL hMem; // [rsp+40h] [rbp-1A8h] BYREF
  __int128 v20; // [rsp+48h] [rbp-1A0h] BYREF
  WCHAR StringSecurityDescriptor[184]; // [rsp+60h] [rbp-188h] BYREF

  hMem = 0;
  v0 = StringSecurityDescriptor;
  v1 = 2;
  v2 = L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)(A;;GR;;;S-1-15-3-1024-3203351429-212044378"
        "4-2872670797-1918958302-2829055647-4275794519-765664414-2751773334)";
  do
  {
    v3 = *((_OWORD *)v2 + 1);
    *(_OWORD *)v0 = *(_OWORD *)v2;
    v4 = *((_OWORD *)v2 + 2);
    *((_OWORD *)v0 + 1) = v3;
    v5 = *((_OWORD *)v2 + 3);
    *((_OWORD *)v0 + 2) = v4;
    v6 = *((_OWORD *)v2 + 4);
    *((_OWORD *)v0 + 3) = v5;
    v7 = *((_OWORD *)v2 + 5);
    *((_OWORD *)v0 + 4) = v6;
    v8 = *((_OWORD *)v2 + 6);
    *((_OWORD *)v0 + 5) = v7;
    v9 = *((_OWORD *)v2 + 7);
    v2 += 64;
    *((_OWORD *)v0 + 6) = v8;
    *((_OWORD *)v0 + 7) = v9;
    v0 += 64;
    --v1;
  }
  while ( v1 );
  v10 = *((_OWORD *)v2 + 1);
  *(_OWORD *)v0 = *(_OWORD *)v2;
  v11 = *((_OWORD *)v2 + 2);
  *((_OWORD *)v0 + 1) = v10;
  v12 = *((_OWORD *)v2 + 3);
  *((_OWORD *)v0 + 2) = v11;
  v13 = *((_OWORD *)v2 + 4);
  *((_OWORD *)v0 + 3) = v12;
  v14 = *((_OWORD *)v2 + 5);
  *((_OWORD *)v0 + 4) = v13;
  v15 = *(_OWORD *)(v2 + 45);
  *((_OWORD *)v0 + 5) = v14;
  *(_OWORD *)(v0 + 45) = v15;
  v20 = 0;
  hServerStopEvent = CreateEventW(0, 1, 0, 0);
  if ( !hServerStopEvent
    || !(unsigned int)ReportStatusToSCMgr(2, 0, 3000)
    || !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &hMem, 0) )
  {
    goto LABEL_4;
  }
  v18 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, (RPC_WSTR)L"keysvc", hMem);
  LastError = 0;
  if ( v18 != 1740 )
    LastError = v18;
  if ( LastError )
    goto LABEL_5;
  *((_QWORD *)&v20 + 1) = sshStatusHandle;
  LODWORD(v20) = 16;
  LastError = CryptsvcCtrl(1, 0, 0, &v20);
  if ( LastError )
    goto LABEL_5;
  if ( (!g_pCryptsvcSvcsGlobals
     || (*((unsigned int (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))g_pCryptsvcSvcsGlobals
         + 24))(
          &hRegisteredWait,
          L"CryptSvc",
          hServerStopEvent,
          TerminationNotify,
          0,
          24))
    && (hRegisteredWait = (HANDLE)RegisterWaitForSingleObjectEx(
                                    hServerStopEvent,
                                    TerminationNotify,
                                    0,
                                    0xFFFFFFFFLL,
                                    24)) == 0
    || !(unsigned int)ReportStatusToSCMgr(4, 0, 0) )
  {
LABEL_4:
    LastError = GetLastError();
LABEL_5:
    if ( hMem )
      LocalFree(hMem);
    TeardownServer(LastError, 0);
    return LastError;
  }
  if ( hMem )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x18000f6c4  push    rbx
0x18000f6c6  sub     rsp, 1E0h
0x18000f6cd  mov     rax, cs:__security_cookie
0x18000f6d4  xor     rax, rsp
0x18000f6d7  mov     [rsp+1E8h+var_18], rax
0x18000f6df  mov     ebx, 2
0x18000f6e4  mov     [rsp+1E8h+hMem], 0
0x18000f6ed  lea     rax, [rsp+1E8h+StringSecurityDescriptor]
0x18000f6f2  mov     edx, ebx
0x18000f6f4  lea     rcx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18000f6fb  lea     r8d, [rbx+7Eh]
0x18000f6ff  movups  xmm0, xmmword ptr [rcx]
0x18000f702  movups  xmm1, xmmword ptr [rcx+10h]
0x18000f706  movups  xmmword ptr [rax], xmm0
0x18000f709  movups  xmm0, xmmword ptr [rcx+20h]
0x18000f70d  movups  xmmword ptr [rax+10h], xmm1
0x18000f711  movups  xmm1, xmmword ptr [rcx+30h]
0x18000f715  movups  xmmword ptr [rax+20h], xmm0
0x18000f719  movups  xmm0, xmmword ptr [rcx+40h]
0x18000f71d  movups  xmmword ptr [rax+30h], xmm1
0x18000f721  movups  xmm1, xmmword ptr [rcx+50h]
0x18000f725  movups  xmmword ptr [rax+40h], xmm0
0x18000f729  movups  xmm0, xmmword ptr [rcx+60h]
0x18000f72d  movups  xmmword ptr [rax+50h], xmm1
0x18000f731  movups  xmm1, xmmword ptr [rcx+70h]
0x18000f735  add     rcx, r8
0x18000f738  movups  xmmword ptr [rax+60h], xmm0
0x18000f73c  movups  xmmword ptr [rax+70h], xmm1
0x18000f740  add     rax, r8
0x18000f743  sub     rdx, 1
0x18000f747  jnz     short loc_18000F6FF
0x18000f749  movups  xmm0, xmmword ptr [rcx]
0x18000f74c  xor     r9d, r9d; lpName
0x18000f74f  xor     r8d, r8d; bInitialState
0x18000f752  movups  xmm1, xmmword ptr [rcx+10h]
0x18000f756  movups  xmmword ptr [rax], xmm0
0x18000f759  lea     edx, [r9+1]; bManualReset
0x18000f75d  movups  xmm0, xmmword ptr [rcx+20h]
0x18000f761  movups  xmmword ptr [rax+10h], xmm1
0x18000f765  movups  xmm1, xmmword ptr [rcx+30h]
0x18000f769  movups  xmmword ptr [rax+20h], xmm0
0x18000f76d  movups  xmm0, xmmword ptr [rcx+40h]
0x18000f771  movups  xmmword ptr [rax+30h], xmm1
0x18000f775  movups  xmm1, xmmword ptr [rcx+50h]
0x18000f779  movups  xmmword ptr [rax+40h], xmm0
0x18000f77d  movups  xmm0, xmmword ptr [rcx+5Ah]
0x18000f781  xor     ecx, ecx; lpEventAttributes
0x18000f783  movups  xmmword ptr [rax+50h], xmm1
0x18000f787  xorps   xmm1, xmm1
0x18000f78a  movups  xmmword ptr [rax+5Ah], xmm0
0x18000f78e  movups  [rsp+1E8h+var_1A0], xmm1
0x18000f793  call    cs:__imp_CreateEventW
0x18000f799  mov     cs:?hServerStopEvent@@3PEAXEA, rax; void * hServerStopEvent
0x18000f7a0  test    rax, rax
0x18000f7a3  jnz     short loc_18000F7E1
0x18000f7a5  call    cs:__imp_GetLastError
0x18000f7ab  mov     ebx, eax
0x18000f7ad  mov     rcx, [rsp+1E8h+hMem]; hMem
0x18000f7b2  test    rcx, rcx
0x18000f7b5  jz      short loc_18000F7BD
0x18000f7b7  call    cs:__imp_LocalFree
0x18000f7bd  xor     edx, edx; int
0x18000f7bf  mov     ecx, ebx; unsigned int
0x18000f7c1  call    ?TeardownServer@@YAXKH@Z; TeardownServer(ulong,int)
0x18000f7c6  mov     eax, ebx
0x18000f7c8  mov     rcx, [rsp+1E8h+var_18]
0x18000f7d0  xor     rcx, rsp; StackCookie
0x18000f7d3  call    __security_check_cookie
0x18000f7d8  add     rsp, 1E0h
0x18000f7df  pop     rbx
0x18000f7e0  retn
0x18000f7e1  xor     edx, edx
0x18000f7e3  mov     r8d, 0BB8h
0x18000f7e9  mov     ecx, ebx
0x18000f7eb  call    ReportStatusToSCMgr
0x18000f7f0  test    eax, eax
0x18000f7f2  jz      short loc_18000F7A5
0x18000f7f4  xor     r9d, r9d; SecurityDescriptorSize
0x18000f7f7  lea     r8, [rsp+1E8h+hMem]; SecurityDescriptor
0x18000f7fc  lea     rcx, [rsp+1E8h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18000f801  lea     edx, [r9+1]; StringSDRevision
0x18000f805  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000f80b  test    eax, eax
0x18000f80d  jz      short loc_18000F7A5
0x18000f80f  mov     r9, [rsp+1E8h+hMem]; SecurityDescriptor
0x18000f814  lea     r8, Endpoint; "keysvc"
0x18000f81b  mov     edx, 0Ah; MaxCalls
0x18000f820  lea     rcx, Protseq; "ncalrpc"
0x18000f827  call    cs:__imp_RpcServerUseProtseqEpW
0x18000f82d  xor     ebx, ebx
0x18000f82f  cmp     eax, 6CCh
0x18000f834  cmovnz  ebx, eax
0x18000f837  test    ebx, ebx
0x18000f839  jnz     loc_18000F7AD
0x18000f83f  mov     rax, cs:?sshStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * sshStatusHandle
0x18000f846  lea     r9, [rsp+1E8h+var_1A0]
0x18000f84b  xor     r8d, r8d
0x18000f84e  mov     qword ptr [rsp+1E8h+var_1A0+8], rax
0x18000f853  xor     edx, edx
0x18000f855  mov     dword ptr [rsp+1E8h+var_1A0], 10h
0x18000f85d  lea     ecx, [rbx+1]
0x18000f860  call    CryptsvcCtrl
0x18000f865  mov     ebx, eax
0x18000f867  test    eax, eax
0x18000f869  jnz     loc_18000F7AD
0x18000f86f  lea     ebx, [rax+18h]
0x18000f872  mov     rax, cs:?g_pCryptsvcSvcsGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pCryptsvcSvcsGlobals
0x18000f879  test    rax, rax
0x18000f87c  jz      short loc_18000F8B7
0x18000f87e  mov     r8, cs:?hServerStopEvent@@3PEAXEA; void * hServerStopEvent
0x18000f885  lea     r9, ?TerminationNotify@@YAXPEAXE@Z; TerminationNotify(void *,uchar)
0x18000f88c  mov     rax, [rax+0C0h]
0x18000f893  lea     rdx, ServiceName; "CryptSvc"
0x18000f89a  mov     [rsp+1E8h+var_1C0], ebx
0x18000f89e  lea     rcx, ?hRegisteredWait@@3PEAXEA; void * hRegisteredWait
0x18000f8a5  mov     [rsp+1E8h+var_1C8], 0
0x18000f8ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8b3  test    eax, eax
0x18000f8b5  jz      short loc_18000F8E6
0x18000f8b7  mov     rcx, cs:?hServerStopEvent@@3PEAXEA; void * hServerStopEvent
0x18000f8be  lea     rdx, ?TerminationNotify@@YAXPEAXE@Z; TerminationNotify(void *,uchar)
0x18000f8c5  or      r9d, 0FFFFFFFFh
0x18000f8c9  mov     dword ptr [rsp+1E8h+var_1C8], ebx
0x18000f8cd  xor     r8d, r8d
0x18000f8d0  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18000f8d6  mov     cs:?hRegisteredWait@@3PEAXEA, rax; void * hRegisteredWait
0x18000f8dd  test    rax, rax
0x18000f8e0  jz      loc_18000F7A5
0x18000f8e6  xor     edx, edx
0x18000f8e8  xor     r8d, r8d
0x18000f8eb  lea     ecx, [rdx+4]
0x18000f8ee  call    ReportStatusToSCMgr
0x18000f8f3  test    eax, eax
0x18000f8f5  jz      loc_18000F7A5
0x18000f8fb  mov     rcx, [rsp+1E8h+hMem]; hMem
0x18000f900  test    rcx, rcx
0x18000f903  jz      short loc_18000F90B
0x18000f905  call    cs:__imp_LocalFree
0x18000f90b  xor     eax, eax
0x18000f90d  jmp     loc_18000F7C8
```
