# CObjectAccessTracker<ITSSession,5000>::CObjectAccessTracker<ITSSession,5000>(char const *,ITSSession *,ITSRpcClientTrackerMgr *,long *)

- ea: `0x180015a24`
- end: `0x180015d1d`
- name: `??0?$CObjectAccessTracker@UITSSession@@$0BDII@@@QEAA@PEBDPEAUITSSession@@PEAVITSRpcClientTrackerMgr@@PEAJ@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014300`

## callees

- `0x1800074c0`
- `0x180010eb0`
- `0x180015a24`
- `0x180097010`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x180015cc1`
- `ntdll!RtlCaptureStackBackTrace` at `0x180015cc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c6c`
- `RPCRT4!RpcImpersonateClient` at `0x180015b5a`
- `RPCRT4!RpcImpersonateClient` at `0x180015b5a`
- `RPCRT4!RpcRevertToSelf` at `0x180015baa`
- `RPCRT4!RpcRevertToSelf` at `0x180015baa`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180015b1f`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180015b1f`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180015bf1`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180015bf1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015b93`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015b93`

## string_xrefs

- `0x180015cd6`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x180015c30`: `CObjectAccessTracker<struct ITSSession,5000>::CObjectAccessTracker`
- `0x180015c85`: `CObjectAccessTracker<struct ITSSession,5000>::GetCallerSessionId`
- `0x180015ccc`: `CObjectAccessTracker<struct ITSSession,5000>::GetCallerSessionId`
- `0x180015c8f`: `GetTokenInformation failed: 0x%x in %s`

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
0x180015a24  mov     [rsp-38h+BackTraceHash], rdx
0x180015a29  mov     [rsp-38h+arg_0], rcx
0x180015a2e  push    rbp
0x180015a2f  push    rbx
0x180015a30  push    rsi
0x180015a31  push    rdi
0x180015a32  push    r13
0x180015a34  push    r14
0x180015a36  push    r15
0x180015a38  mov     rbp, rsp
0x180015a3b  sub     rsp, 30h
0x180015a3f  mov     rdi, r9
0x180015a42  mov     rbx, r8
0x180015a45  mov     rsi, rcx
0x180015a48  lea     rax, ??_7?$CTSPrivateObject@UIUnknown@@@@6B@; const CTSPrivateObject<IUnknown>::`vftable'
0x180015a4f  mov     [rcx], rax
0x180015a52  lea     rax, aSessionclientt_0; "SESSIONCLIENTTRACKER"
0x180015a59  mov     [rcx+10h], rax
0x180015a5d  mov     dword ptr [rcx+8], 0
0x180015a64  mov     r14d, 1
0x180015a6a  mov     [rcx+0Ch], r14d
0x180015a6e  add     rcx, 628h; struct _LIST_ENTRY *
0x180015a75  mov     [rcx+8], rcx
0x180015a79  mov     [rcx], rcx
0x180015a7c  call    ?AddTrackingObject@@YAXPEAU_LIST_ENTRY@@@Z; AddTrackingObject(_LIST_ENTRY *)
0x180015a81  mov     qword ptr [rsi+18h], 0
0x180015a89  mov     dword ptr [rsi+20h], 0
0x180015a90  mov     dword ptr [rbp+BackTraceHash], 0
0x180015a97  mov     eax, r14d
0x180015a9a  lock xadd [rsi+20h], eax
0x180015a9f  add     eax, r14d
0x180015aa2  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, r14d; int g_bCaptureObjectStackTrace
0x180015aa9  jz      loc_180015CA3
0x180015aaf  lea     rax, ??_7?$CObjectAccessTracker@UITSSession@@$0BDII@@@6B@; const CObjectAccessTracker<ITSSession,5000>::`vftable'
0x180015ab6  mov     [rsi], rax
0x180015ab9  mov     [rsi+638h], rbx
0x180015ac0  test    rbx, rbx
0x180015ac3  jz      short loc_180015AD5
0x180015ac5  mov     rax, [rbx]
0x180015ac8  mov     rcx, rbx
0x180015acb  mov     rax, [rax+8]
0x180015acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ad4  nop
0x180015ad5  lea     r14, [rsi+640h]
0x180015adc  or      eax, 0FFFFFFFFh
0x180015adf  mov     [r14], eax
0x180015ae2  mov     [rsi+644h], eax
0x180015ae8  mov     [rsi+648h], rdi
0x180015aef  test    rdi, rdi
0x180015af2  jz      short loc_180015B04
0x180015af4  mov     rax, [rdi]
0x180015af7  mov     rcx, rdi
0x180015afa  mov     rax, [rax+8]
0x180015afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b03  nop
0x180015b04  lea     r15, [rsi+650h]
0x180015b0b  mov     qword ptr [r15], 0
0x180015b12  mov     [rbp+ClientLocalFlag], 0
0x180015b19  lea     rdx, [rbp+ClientLocalFlag]; ClientLocalFlag
0x180015b1d  xor     ecx, ecx; BindingHandle
0x180015b1f  call    cs:__imp_I_RpcBindingIsClientLocal
0x180015b25  mov     edi, 80070000h
0x180015b2a  test    eax, eax
0x180015b2c  jg      loc_180015C41
0x180015b32  mov     r13d, 8
0x180015b38  test    eax, eax
0x180015b3a  js      loc_180015C05
0x180015b40  cmp     [rbp+ClientLocalFlag], 0
0x180015b44  jz      loc_180015C05
0x180015b4a  mov     dword ptr [rbp+BackTraceHash], 0
0x180015b51  mov     [rbp+TokenInformation], 0
0x180015b58  xor     ecx, ecx; BindingHandle
0x180015b5a  call    cs:__imp_RpcImpersonateClient
0x180015b60  mov     ebx, eax
0x180015b62  mov     dword ptr [rbp+BackTraceHash], eax
0x180015b65  test    eax, eax
0x180015b67  jg      loc_180015C4B
0x180015b6d  test    ebx, ebx
0x180015b6f  js      loc_180015CCC
0x180015b75  lea     rax, [rbp+BackTraceHash]
0x180015b79  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180015b7e  mov     r9d, 4; TokenInformationLength
0x180015b84  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180015b88  lea     edx, [r9+8]; TokenInformationClass
0x180015b8c  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x180015b93  call    cs:__imp_GetTokenInformation
0x180015b99  test    eax, eax
0x180015b9b  jz      loc_180015C6C
0x180015ba1  mov     eax, [rbp+TokenInformation]
0x180015ba4  mov     [rsi+644h], eax
0x180015baa  call    cs:__imp_RpcRevertToSelf
0x180015bb0  mov     dword ptr [rbp+BackTraceHash], eax
0x180015bb3  test    eax, eax
0x180015bb5  jg      loc_180015C55
0x180015bbb  js      loc_180015CF6
0x180015bc1  mov     edi, ebx
0x180015bc3  test    ebx, ebx
0x180015bc5  js      loc_180015CE7
0x180015bcb  cmp     dword ptr [rsi+644h], 0
0x180015bd2  jnz     short loc_180015BEC
0x180015bd4  mov     rcx, [rbp+arg_20]
0x180015bd8  mov     [rcx], edi
0x180015bda  mov     rax, rsi
0x180015bdd  add     rsp, 30h
0x180015be1  pop     r15
0x180015be3  pop     r14
0x180015be5  pop     r13
0x180015be7  pop     rdi
0x180015be8  pop     rsi
0x180015be9  pop     rbx
0x180015bea  pop     rbp
0x180015beb  retn
0x180015bec  mov     rdx, r14; Pid
0x180015bef  xor     ecx, ecx; Binding
0x180015bf1  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180015bf7  mov     edi, eax
0x180015bf9  test    eax, eax
0x180015bfb  jg      short loc_180015C61
0x180015bfd  test    edi, edi
0x180015bff  js      loc_180015D0D
0x180015c05  mov     rcx, [rsi+648h]
0x180015c0c  mov     rax, [rcx]
0x180015c0f  mov     r8, r15
0x180015c12  mov     edx, 1388h
0x180015c17  mov     rax, [rax+18h]
0x180015c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c20  mov     edi, eax
0x180015c22  test    eax, eax
0x180015c24  jns     short loc_180015BD4
0x180015c26  mov     r8d, eax
0x180015c29  lea     rdx, aMPcienttracker; "m_pCientTracker->TrackCaller failed: 0x"...
0x180015c30  lea     r9, aCobjectaccesst; "CObjectAccessTracker<struct ITSSession,"...
0x180015c37  mov     ecx, r13d; int
0x180015c3a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015c3f  jmp     short loc_180015BD4
0x180015c41  movzx   eax, ax
0x180015c44  or      eax, edi
0x180015c46  jmp     loc_180015B32
0x180015c4b  movzx   ebx, ax
0x180015c4e  or      ebx, edi
0x180015c50  jmp     loc_180015B6D
0x180015c55  movzx   eax, ax
0x180015c58  or      eax, edi
0x180015c5a  test    eax, eax
0x180015c5c  jmp     loc_180015BBB
0x180015c61  movzx   edi, ax
0x180015c64  or      edi, 80070000h
0x180015c6a  jmp     short loc_180015BFD
0x180015c6c  call    cs:__imp_GetLastError
0x180015c72  mov     ebx, eax
0x180015c74  test    eax, eax
0x180015c76  jle     short loc_180015C7D
0x180015c78  movzx   ebx, ax
0x180015c7b  or      ebx, edi
0x180015c7d  test    ebx, ebx
0x180015c7f  jns     loc_180015BA1
0x180015c85  lea     r9, aCobjectaccesst_1; "CObjectAccessTracker<struct ITSSession,"...
0x180015c8c  mov     r8d, ebx
0x180015c8f  lea     rdx, aGettokeninform_2; "GetTokenInformation failed: 0x%x in %s"
0x180015c96  mov     ecx, r13d; int
0x180015c99  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015c9e  jmp     loc_180015BAA
0x180015ca3  and     eax, 1Fh
0x180015ca6  lea     r8, [rax+rax*2]
0x180015caa  shl     r8, 4
0x180015cae  add     r8, 28h ; '('
0x180015cb2  add     r8, rsi; BackTrace
0x180015cb5  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x180015cb9  mov     edx, 6; FramesToCapture
0x180015cbe  mov     ecx, r14d; FramesToSkip
0x180015cc1  call    cs:__imp_RtlCaptureStackBackTrace
0x180015cc7  jmp     loc_180015AAF
0x180015ccc  lea     r9, aCobjectaccesst_1; "CObjectAccessTracker<struct ITSSession,"...
0x180015cd3  mov     r8d, ebx
0x180015cd6  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x180015cdd  mov     ecx, r13d; int
0x180015ce0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015ce5  mov     edi, ebx
0x180015ce7  mov     r8d, ebx
0x180015cea  lea     rdx, aGetcallersessi; "GetCallerSessionId failed: 0x%x in %s"
0x180015cf1  jmp     loc_180015C30
0x180015cf6  mov     r8d, eax
0x180015cf9  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed 0x%08x"
0x180015d00  mov     ecx, r13d; int
0x180015d03  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015d08  jmp     loc_180015BC1
0x180015d0d  mov     r8d, edi
0x180015d10  lea     rdx, aIRpcbindinginq_1; "I_RpcBindingInqLocalClientPID failed: 0"...
0x180015d17  jmp     loc_180015C30
```
