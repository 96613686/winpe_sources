# CObjectAccessTracker<ITSSession,5000>::CObjectAccessTracker<ITSSession,5000>(char const *,ITSSession *,ITSRpcClientTrackerMgr *,long *)

- ea: `0x18000f3bc`
- end: `0x18000f6e0`
- name: `??0?$CObjectAccessTracker@UITSSession@@$0BDII@@@QEAA@PEBDPEAUITSSession@@PEAVITSRpcClientTrackerMgr@@PEAJ@Z`
- size: `804`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000df50`

## callees

- `0x1800077a0`
- `0x18000f3bc`
- `0x180014a10`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x18000f67e`
- `ntdll!RtlCaptureStackBackTrace` at `0x18000f67e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f623`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f623`
- `RPCRT4!RpcImpersonateClient` at `0x18000f4f8`
- `RPCRT4!RpcImpersonateClient` at `0x18000f4f8`
- `RPCRT4!RpcRevertToSelf` at `0x18000f554`
- `RPCRT4!RpcRevertToSelf` at `0x18000f554`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000f4b7`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000f4b7`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000f5a2`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000f5a2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f537`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f537`

## string_xrefs

- `0x18000f699`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18000f5e7`: `CObjectAccessTracker<struct ITSSession,5000>::CObjectAccessTracker`
- `0x18000f642`: `CObjectAccessTracker<struct ITSSession,5000>::GetCallerSessionId`
- `0x18000f68f`: `CObjectAccessTracker<struct ITSSession,5000>::GetCallerSessionId`
- `0x18000f64c`: `GetTokenInformation failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CObjectAccessTracker<ITSSession,5000>::CObjectAccessTracker<ITSSession,5000>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        signed int *a5)
{
  struct _LIST_ENTRY *v8; // rcx
  char v9; // al
  int IsClientLocal; // eax
  RPC_STATUS v11; // eax
  signed int v12; // ebx
  int v13; // eax
  bool v14; // sf
  signed int v15; // edi
  RPC_STATUS v17; // eax
  int v18; // eax
  signed int LastError; // eax
  __int64 BackTraceHash; // [rsp+78h] [rbp+48h] BYREF
  unsigned int ClientLocalFlag; // [rsp+80h] [rbp+50h] BYREF
  int TokenInformation; // [rsp+88h] [rbp+58h] BYREF

  BackTraceHash = a2;
  *(_QWORD *)a1 = &CTSPrivateObject<IUnknown>::`vftable';
  *(_QWORD *)(a1 + 16) = "SESSIONCLIENTTRACKER";
  *(_DWORD *)(a1 + 8) = 0;
  *(_DWORD *)(a1 + 12) = 1;
  v8 = (struct _LIST_ENTRY *)(a1 + 1576);
  v8->Blink = v8;
  v8->Flink = v8;
  AddTrackingObject(v8);
  *(_QWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 32) = 0;
  LODWORD(BackTraceHash) = 0;
  v9 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 32));
  if ( g_bCaptureObjectStackTrace == 1 )
    RtlCaptureStackBackTrace(1u, 6u, (PVOID *)(a1 + 48LL * (v9 & 0x1F) + 40), (PULONG)&BackTraceHash);
  *(_QWORD *)a1 = &CObjectAccessTracker<ITSSession,5000>::`vftable';
  *(_QWORD *)(a1 + 1592) = a3;
  if ( a3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  *(_DWORD *)(a1 + 1600) = -1;
  *(_DWORD *)(a1 + 1604) = -1;
  *(_QWORD *)(a1 + 1608) = a4;
  if ( a4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a4 + 8LL))(a4);
  *(_QWORD *)(a1 + 1616) = 0;
  ClientLocalFlag = 0;
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  if ( IsClientLocal > 0 )
    IsClientLocal = (unsigned __int16)IsClientLocal | 0x80070000;
  if ( IsClientLocal < 0 || !ClientLocalFlag )
    goto LABEL_26;
  LODWORD(BackTraceHash) = 0;
  TokenInformation = 0;
  v11 = RpcImpersonateClient(0);
  v12 = v11;
  LODWORD(BackTraceHash) = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  if ( v12 < 0 )
  {
    _DbgPrintMessage(
      8,
      "RpcImpersonateClient failed: 0x%x in %s",
      v12,
      "CObjectAccessTracker<struct ITSSession,5000>::GetCallerSessionId");
    v15 = v12;
LABEL_33:
    _DbgPrintMessage(
      8,
      "GetCallerSessionId failed: 0x%x in %s",
      (unsigned int)v12,
      "CObjectAccessTracker<struct ITSSession,5000>::CObjectAccessTracker");
    goto LABEL_22;
  }
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenSessionId, &TokenInformation, 4u, (PDWORD)&BackTraceHash) )
    goto LABEL_15;
  LastError = GetLastError();
  v12 = LastError;
  if ( LastError > 0 )
    v12 = (unsigned __int16)LastError | 0x80070000;
  if ( v12 >= 0 )
LABEL_15:
    *(_DWORD *)(a1 + 1604) = TokenInformation;
  else
    _DbgPrintMessage(
      8,
      "GetTokenInformation failed: 0x%x in %s",
      v12,
      "CObjectAccessTracker<struct ITSSession,5000>::GetCallerSessionId");
  v13 = RpcRevertToSelf();
  LODWORD(BackTraceHash) = v13;
  v14 = v13 < 0;
  if ( v13 > 0 )
  {
    v13 = (unsigned __int16)v13 | 0x80070000;
    v14 = v13 < 0;
  }
  if ( v14 )
    _DbgPrintMessage(8, "RpcRevertToSelf failed 0x%08x", v13);
  v15 = v12;
  if ( v12 < 0 )
    goto LABEL_33;
  if ( !*(_DWORD *)(a1 + 1604) )
    goto LABEL_22;
  v17 = I_RpcBindingInqLocalClientPID(0, (unsigned int *)(a1 + 1600));
  v15 = v17;
  if ( v17 > 0 )
    v15 = (unsigned __int16)v17 | 0x80070000;
  if ( v15 < 0 )
  {
    _DbgPrintMessage(
      8,
      "I_RpcBindingInqLocalClientPID failed: 0x%x in %s",
      (unsigned int)v15,
      "CObjectAccessTracker<struct ITSSession,5000>::CObjectAccessTracker");
    goto LABEL_22;
  }
LABEL_26:
  v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(a1 + 1608) + 24LL))(
          *(_QWORD *)(a1 + 1608),
          5000,
          a1 + 1616);
  v15 = v18;
  if ( v18 < 0 )
    _DbgPrintMessage(
      8,
      "m_pCientTracker->TrackCaller failed: 0x%x in %s",
      (unsigned int)v18,
      "CObjectAccessTracker<struct ITSSession,5000>::CObjectAccessTracker");
LABEL_22:
  *a5 = v15;
  return a1;
}

```

## disassembly

```asm
0x18000f3bc  mov     [rsp-38h+BackTraceHash], rdx
0x18000f3c1  mov     [rsp-38h+arg_0], rcx
0x18000f3c6  push    rbp
0x18000f3c7  push    rbx
0x18000f3c8  push    rsi
0x18000f3c9  push    rdi
0x18000f3ca  push    r13
0x18000f3cc  push    r14
0x18000f3ce  push    r15
0x18000f3d0  mov     rbp, rsp
0x18000f3d3  sub     rsp, 30h
0x18000f3d7  mov     rdi, r9
0x18000f3da  mov     rbx, r8
0x18000f3dd  mov     rsi, rcx
0x18000f3e0  lea     rax, ??_7?$CTSPrivateObject@UIUnknown@@@@6B@; const CTSPrivateObject<IUnknown>::`vftable'
0x18000f3e7  mov     [rcx], rax
0x18000f3ea  lea     rax, aSessionclientt_0; "SESSIONCLIENTTRACKER"
0x18000f3f1  mov     [rcx+10h], rax
0x18000f3f5  mov     dword ptr [rcx+8], 0
0x18000f3fc  mov     r14d, 1
0x18000f402  mov     [rcx+0Ch], r14d
0x18000f406  add     rcx, 628h; struct _LIST_ENTRY *
0x18000f40d  mov     [rcx+8], rcx
0x18000f411  mov     [rcx], rcx
0x18000f414  call    ?AddTrackingObject@@YAXPEAU_LIST_ENTRY@@@Z; AddTrackingObject(_LIST_ENTRY *)
0x18000f419  mov     qword ptr [rsi+18h], 0
0x18000f421  mov     dword ptr [rsi+20h], 0
0x18000f428  mov     dword ptr [rbp+BackTraceHash], 0
0x18000f42f  mov     eax, r14d
0x18000f432  lock xadd [rsi+20h], eax
0x18000f437  add     eax, r14d
0x18000f43a  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, r14d; int g_bCaptureObjectStackTrace
0x18000f441  jz      loc_18000F660
0x18000f447  lea     rax, ??_7?$CObjectAccessTracker@UITSSession@@$0BDII@@@6B@; const CObjectAccessTracker<ITSSession,5000>::`vftable'
0x18000f44e  mov     [rsi], rax
0x18000f451  mov     [rsi+638h], rbx
0x18000f458  test    rbx, rbx
0x18000f45b  jz      short loc_18000F46D
0x18000f45d  mov     rax, [rbx]
0x18000f460  mov     rcx, rbx
0x18000f463  mov     rax, [rax+8]
0x18000f467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f46c  nop
0x18000f46d  lea     r14, [rsi+640h]
0x18000f474  or      eax, 0FFFFFFFFh
0x18000f477  mov     [r14], eax
0x18000f47a  mov     [rsi+644h], eax
0x18000f480  mov     [rsi+648h], rdi
0x18000f487  test    rdi, rdi
0x18000f48a  jz      short loc_18000F49C
0x18000f48c  mov     rax, [rdi]
0x18000f48f  mov     rcx, rdi
0x18000f492  mov     rax, [rax+8]
0x18000f496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f49b  nop
0x18000f49c  lea     r15, [rsi+650h]
0x18000f4a3  mov     qword ptr [r15], 0
0x18000f4aa  mov     [rbp+ClientLocalFlag], 0
0x18000f4b1  lea     rdx, [rbp+ClientLocalFlag]; ClientLocalFlag
0x18000f4b5  xor     ecx, ecx; BindingHandle
0x18000f4b7  call    cs:__imp_I_RpcBindingIsClientLocal
0x18000f4be  nop     dword ptr [rax+rax+00h]
0x18000f4c3  mov     edi, 80070000h
0x18000f4c8  test    eax, eax
0x18000f4ca  jg      loc_18000F5F8
0x18000f4d0  mov     r13d, 8
0x18000f4d6  test    eax, eax
0x18000f4d8  js      loc_18000F5BC
0x18000f4de  cmp     [rbp+ClientLocalFlag], 0
0x18000f4e2  jz      loc_18000F5BC
0x18000f4e8  mov     dword ptr [rbp+BackTraceHash], 0
0x18000f4ef  mov     [rbp+TokenInformation], 0
0x18000f4f6  xor     ecx, ecx; BindingHandle
0x18000f4f8  call    cs:__imp_RpcImpersonateClient
0x18000f4ff  nop     dword ptr [rax+rax+00h]
0x18000f504  mov     ebx, eax
0x18000f506  mov     dword ptr [rbp+BackTraceHash], eax
0x18000f509  test    eax, eax
0x18000f50b  jg      loc_18000F602
0x18000f511  test    ebx, ebx
0x18000f513  js      loc_18000F68F
0x18000f519  lea     rax, [rbp+BackTraceHash]
0x18000f51d  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18000f522  mov     r9d, 4; TokenInformationLength
0x18000f528  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18000f52c  lea     edx, [r9+8]; TokenInformationClass
0x18000f530  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x18000f537  call    cs:__imp_GetTokenInformation
0x18000f53e  nop     dword ptr [rax+rax+00h]
0x18000f543  test    eax, eax
0x18000f545  jz      loc_18000F623
0x18000f54b  mov     eax, [rbp+TokenInformation]
0x18000f54e  mov     [rsi+644h], eax
0x18000f554  call    cs:__imp_RpcRevertToSelf
0x18000f55b  nop     dword ptr [rax+rax+00h]
0x18000f560  mov     dword ptr [rbp+BackTraceHash], eax
0x18000f563  test    eax, eax
0x18000f565  jg      loc_18000F60C
0x18000f56b  js      loc_18000F6B9
0x18000f571  mov     edi, ebx
0x18000f573  test    ebx, ebx
0x18000f575  js      loc_18000F6AA
0x18000f57b  cmp     dword ptr [rsi+644h], 0
0x18000f582  jnz     short loc_18000F59D
0x18000f584  mov     rcx, [rbp+arg_20]
0x18000f588  mov     [rcx], edi
0x18000f58a  mov     rax, rsi
0x18000f58d  add     rsp, 30h
0x18000f591  pop     r15
0x18000f593  pop     r14
0x18000f595  pop     r13
0x18000f597  pop     rdi
0x18000f598  pop     rsi
0x18000f599  pop     rbx
0x18000f59a  pop     rbp
0x18000f59b  retn
0x18000f59d  mov     rdx, r14; Pid
0x18000f5a0  xor     ecx, ecx; Binding
0x18000f5a2  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000f5a9  nop     dword ptr [rax+rax+00h]
0x18000f5ae  mov     edi, eax
0x18000f5b0  test    eax, eax
0x18000f5b2  jg      short loc_18000F618
0x18000f5b4  test    edi, edi
0x18000f5b6  js      loc_18000F6D0
0x18000f5bc  mov     rcx, [rsi+648h]
0x18000f5c3  mov     rax, [rcx]
0x18000f5c6  mov     r8, r15
0x18000f5c9  mov     edx, 1388h
0x18000f5ce  mov     rax, [rax+18h]
0x18000f5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5d7  mov     edi, eax
0x18000f5d9  test    eax, eax
0x18000f5db  jns     short loc_18000F584
0x18000f5dd  mov     r8d, eax
0x18000f5e0  lea     rdx, aMPcienttracker; "m_pCientTracker->TrackCaller failed: 0x"...
0x18000f5e7  lea     r9, aCobjectaccesst; "CObjectAccessTracker<struct ITSSession,"...
0x18000f5ee  mov     ecx, r13d; int
0x18000f5f1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f5f6  jmp     short loc_18000F584
0x18000f5f8  movzx   eax, ax
0x18000f5fb  or      eax, edi
0x18000f5fd  jmp     loc_18000F4D0
0x18000f602  movzx   ebx, ax
0x18000f605  or      ebx, edi
0x18000f607  jmp     loc_18000F511
0x18000f60c  movzx   eax, ax
0x18000f60f  or      eax, edi
0x18000f611  test    eax, eax
0x18000f613  jmp     loc_18000F56B
0x18000f618  movzx   edi, ax
0x18000f61b  or      edi, 80070000h
0x18000f621  jmp     short loc_18000F5B4
0x18000f623  call    cs:__imp_GetLastError
0x18000f62a  nop     dword ptr [rax+rax+00h]
0x18000f62f  mov     ebx, eax
0x18000f631  test    eax, eax
0x18000f633  jle     short loc_18000F63A
0x18000f635  movzx   ebx, ax
0x18000f638  or      ebx, edi
0x18000f63a  test    ebx, ebx
0x18000f63c  jns     loc_18000F54B
0x18000f642  lea     r9, aCobjectaccesst_1; "CObjectAccessTracker<struct ITSSession,"...
0x18000f649  mov     r8d, ebx
0x18000f64c  lea     rdx, aGettokeninform_2; "GetTokenInformation failed: 0x%x in %s"
0x18000f653  mov     ecx, r13d; int
0x18000f656  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f65b  jmp     loc_18000F554
0x18000f660  and     eax, 1Fh
0x18000f663  lea     r8, [rax+rax*2]
0x18000f667  shl     r8, 4
0x18000f66b  add     r8, 28h ; '('
0x18000f66f  add     r8, rsi; BackTrace
0x18000f672  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x18000f676  mov     edx, 6; FramesToCapture
0x18000f67b  mov     ecx, r14d; FramesToSkip
0x18000f67e  call    cs:__imp_RtlCaptureStackBackTrace
0x18000f685  nop     dword ptr [rax+rax+00h]
0x18000f68a  jmp     loc_18000F447
0x18000f68f  lea     r9, aCobjectaccesst_1; "CObjectAccessTracker<struct ITSSession,"...
0x18000f696  mov     r8d, ebx
0x18000f699  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18000f6a0  mov     ecx, r13d; int
0x18000f6a3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f6a8  mov     edi, ebx
0x18000f6aa  mov     r8d, ebx
0x18000f6ad  lea     rdx, aGetcallersessi; "GetCallerSessionId failed: 0x%x in %s"
0x18000f6b4  jmp     loc_18000F5E7
0x18000f6b9  mov     r8d, eax
0x18000f6bc  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed 0x%08x"
0x18000f6c3  mov     ecx, r13d; int
0x18000f6c6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f6cb  jmp     loc_18000F571
0x18000f6d0  mov     r8d, edi
0x18000f6d3  lea     rdx, aIRpcbindinginq_1; "I_RpcBindingInqLocalClientPID failed: 0"...
0x18000f6da  jmp     loc_18000F5E7
```
