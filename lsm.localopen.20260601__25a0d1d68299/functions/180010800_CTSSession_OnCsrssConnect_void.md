# CTSSession::OnCsrssConnect(void)

- ea: `0x180010800`
- end: `0x180010b67`
- name: `?OnCsrssConnect@CTSSession@@AEAAJXZ`
- size: `871`
- prototype: `__int64 __fastcall(CTSSession *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800107f0`

## callees

- `0x1800077a0`
- `0x180010800`
- `0x1800118f4`
- `0x180011a28`
- `0x180011a50`
- `0x180011a78`
- `0x180011e6c`
- `0x1800120d0`
- `0x180012194`
- `0x18001266c`
- `0x1800129d0`
- `0x180027cc8`
- `0x180029f3c`
- `0x18004e850`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180010af2`
- `ntdll!RtlReleaseResource` at `0x180010af2`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800108c0`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800108c0`
- `ntdll!EtwEventActivityIdControl` at `0x180010871`
- `ntdll!EtwEventActivityIdControl` at `0x180010b18`
- `ntdll!EtwEventActivityIdControl` at `0x180010871`
- `ntdll!EtwEventActivityIdControl` at `0x180010b18`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18001083c`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18001083c`

## string_xrefs

- `0x1800108ef`: `OpenNtSessionHandle failed: 0x%x in %s`
- `0x180010903`: `OpenNtSessionHandle failed: 0x%x in %s`
- `0x1800108e5`: `CTSSession::OpenNtSessionHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CTSSession::OnCsrssConnect(CTSSession *this)
{
  int v2; // r15d
  int v3; // r12d
  int v4; // eax
  int v5; // edi
  int v6; // eax
  int v7; // eax
  unsigned int v8; // r14d
  const char *StateName; // rax
  int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // ebx
  __int64 v13; // rdx
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  PRTL_RESOURCE Resource; // [rsp+38h] [rbp-C8h] BYREF
  int v17; // [rsp+40h] [rbp-C0h]
  _OWORD v18[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v19; // [rsp+68h] [rbp-98h] BYREF
  __int64 v20; // [rsp+78h] [rbp-88h] BYREF
  __int128 v21; // [rsp+80h] [rbp-80h] BYREF
  int v22; // [rsp+90h] [rbp-70h]
  _BYTE v23[192]; // [rsp+A0h] [rbp-60h] BYREF

  v15 = 0;
  v2 = -1;
  v3 = WTSGetServiceSessionId();
  v22 = -2147467259;
  if ( this == (CTSSession *)-3208LL
    || (v21 = *(_OWORD *)((char *)this + 3208), (unsigned int)EtwEventActivityIdControl(4, &v21)) )
  {
    v21 = 0;
  }
  else
  {
    v22 = 0;
  }
  CTSSessionTrace::CTSSessionTrace((CTSSessionTrace *)v23, "CTSSession::OnCsrssConnect", this);
  Resource = (PRTL_RESOURCE)((char *)this + 1856);
  v17 = 1;
  if ( *((_DWORD *)this + 488) )
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 1856), 1u);
  v4 = ISessionManagerInternal::OpenNtSessionHandle(*((_DWORD *)this + 436), (void **)this + 808);
  v5 = v4;
  if ( v4 < 0 )
  {
    _DbgPrintMessage(8, "OpenNtSessionHandle failed: 0x%x in %s", v4, "CTSSession::OpenNtSessionHandle");
    _DbgPrintMessage(8, "OpenNtSessionHandle failed: 0x%x in %s", (unsigned int)v5, "CTSSession::OnCsrssConnect");
    goto LABEL_28;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(**((_QWORD **)this + 199) + 24LL))(
         *((_QWORD *)this + 199),
         &IID_ITSSession,
         &v15);
  v5 = v6;
  if ( v6 < 0 )
  {
    _DbgPrintMessage(8, "QI( ITSSession ) failed: 0x%x in %s", (unsigned int)v6, "CTSSession::OnCsrssConnect");
    goto LABEL_28;
  }
  v7 = CTSSession::CState::CheckState((char *)this + 3256, 9);
  v5 = v7;
  v8 = *((_DWORD *)this + 814);
  if ( v7 < 0 )
  {
    StateName = (const char *)CUtils::GetStateName(v8);
    _DbgPrintMessage(8, "invalid state for EvCsrConnected, state is: \"%s\"", StateName);
LABEL_28:
    if ( v2 == v3 || (v13 = 9, v2 == -1) )
      v13 = 4;
    CTSSession::LogFailedTransition(this, v13, (unsigned int)v5);
    goto LABEL_32;
  }
  if ( v7 != 1 )
  {
    v2 = *((_DWORD *)this + 436);
    memset(v18, 0, sizeof(v18));
    v19 = 0;
    v20 = 0;
    v5 = CTSSession::InitializeNotifyInfo(this, (struct __PTSSessInfo *)v18);
    v10 = 5323;
    if ( v2 == v3 )
      v10 = 5331;
    v11 = 9;
    if ( v2 == v3 )
      v11 = 4;
    CTSSession::CState::ChangeState((char *)this + 3256, v11, (char *)&v19 + 8, &v20, v10);
    if ( v5 >= 0 )
    {
      v12 = *((_DWORD *)this + 814);
      CAutoLock::Unlock((CAutoLock *)&Resource);
      (*(void (__fastcall **)(__int64, _OWORD *, _QWORD, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 228) + 1832LL) + 104LL))(
        *((_QWORD *)this + 228) + 1832LL,
        v18,
        v12,
        v8);
      if ( *(_QWORD *)&v18[0] )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v18[0] + 16LL))(*(_QWORD *)&v18[0]);
        *(_QWORD *)&v18[0] = 0;
      }
      if ( (_QWORD)v19 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v19 + 16LL))(v19);
        *(_QWORD *)&v19 = 0;
      }
    }
    if ( !*((_QWORD *)this + 227) )
    {
      v5 = 0;
      goto LABEL_32;
    }
    if ( v5 >= 0 )
      goto LABEL_32;
    goto LABEL_28;
  }
  GetLsmStateName(v8);
  GetLsmEventName(9);
  if ( (g_DebugTraceComponent & 4) != 0 )
    _DbgPrintMessage(2, "No change to session %d state %ws with event %ws", *((unsigned int *)this + 436));
LABEL_32:
  if ( v17 && LODWORD(Resource[1].Lock.DebugInfo) )
    RtlReleaseResource(Resource);
  CTSSessionTrace::~CTSSessionTrace((CTSSessionTrace *)v23);
  if ( v22 >= 0 )
    EtwEventActivityIdControl(2, &v21);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180010800  mov     [rsp-8+arg_8], rbx
0x180010805  mov     [rsp-8+arg_10], rsi
0x18001080a  push    rbp
0x18001080b  push    rdi
0x18001080c  push    r12
0x18001080e  push    r14
0x180010810  push    r15
0x180010812  lea     rbp, [rsp-70h]
0x180010817  sub     rsp, 170h
0x18001081e  mov     rax, cs:__security_cookie
0x180010825  xor     rax, rsp
0x180010828  mov     [rbp+90h+var_30], rax
0x18001082c  mov     rsi, rcx
0x18001082f  mov     [rsp+190h+var_160], 0
0x180010838  or      r15d, 0FFFFFFFFh
0x18001083c  call    cs:__imp_WTSGetServiceSessionId
0x180010843  nop     dword ptr [rax+rax+00h]
0x180010848  mov     r12d, eax
0x18001084b  lea     rcx, [rsi+0C88h]
0x180010852  mov     [rbp+90h+var_100], 80004005h
0x180010859  lea     r14d, [r15+5]
0x18001085d  test    rcx, rcx
0x180010860  jz      short loc_180010886
0x180010862  movups  xmm0, xmmword ptr [rcx]
0x180010865  movdqu  [rbp+90h+var_110], xmm0
0x18001086a  lea     rdx, [rbp+90h+var_110]
0x18001086e  mov     ecx, r14d
0x180010871  call    cs:__imp_EtwEventActivityIdControl
0x180010878  nop     dword ptr [rax+rax+00h]
0x18001087d  test    eax, eax
0x18001087f  jnz     short loc_180010886
0x180010881  mov     [rbp+90h+var_100], eax
0x180010884  jmp     short loc_18001088D
0x180010886  xorps   xmm0, xmm0
0x180010889  movups  [rbp+90h+var_110], xmm0
0x18001088d  mov     r8, rsi; struct ITSSession *
0x180010890  lea     rbx, aCtssessionOncs_0; "CTSSession::OnCsrssConnect"
0x180010897  mov     rdx, rbx; char *
0x18001089a  lea     rcx, [rbp+90h+var_F0]; this
0x18001089e  call    ??0CTSSessionTrace@@QEAA@PEBDPEAUITSSession@@@Z; CTSSessionTrace::CTSSessionTrace(char const *,ITSSession *)
0x1800108a3  nop
0x1800108a4  lea     rcx, [rsi+740h]; Resource
0x1800108ab  mov     [rsp+190h+Resource], rcx
0x1800108b0  mov     [rsp+190h+var_150], 1
0x1800108b8  cmp     dword ptr [rcx+60h], 0
0x1800108bc  jz      short loc_1800108CD
0x1800108be  mov     dl, 1; Wait
0x1800108c0  call    cs:__imp_RtlAcquireResourceExclusive
0x1800108c7  nop     dword ptr [rax+rax+00h]
0x1800108cc  nop
0x1800108cd  lea     rdx, [rsi+1940h]; void **
0x1800108d4  mov     ecx, [rsi+6D0h]; int
0x1800108da  call    ?OpenNtSessionHandle@ISessionManagerInternal@@SAJJPEAPEAX@Z; ISessionManagerInternal::OpenNtSessionHandle(long,void * *)
0x1800108df  mov     edi, eax
0x1800108e1  test    eax, eax
0x1800108e3  jns     short loc_18001091C
0x1800108e5  lea     r9, aCtssessionOpen; "CTSSession::OpenNtSessionHandle"
0x1800108ec  mov     r8d, eax
0x1800108ef  lea     rdx, aOpenntsessionh; "OpenNtSessionHandle failed: 0x%x in %s"
0x1800108f6  mov     ecx, 8; int
0x1800108fb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180010900  mov     r8d, edi
0x180010903  lea     rdx, aOpenntsessionh; "OpenNtSessionHandle failed: 0x%x in %s"
0x18001090a  mov     r9, rbx
0x18001090d  mov     ecx, 8; int
0x180010912  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180010917  jmp     loc_180010AC1
0x18001091c  mov     rcx, [rsi+638h]
0x180010923  mov     rax, [rcx]
0x180010926  lea     r8, [rsp+190h+var_160]
0x18001092b  lea     rdx, IID_ITSSession
0x180010932  mov     rax, [rax+18h]
0x180010936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001093b  mov     edi, eax
0x18001093d  test    eax, eax
0x18001093f  jns     short loc_18001094D
0x180010941  mov     r8d, eax
0x180010944  lea     rdx, aQiItssessionFa; "QI( ITSSession ) failed: 0x%x in %s"
0x18001094b  jmp     short loc_18001090A
0x18001094d  lea     rbx, [rsi+0CB8h]
0x180010954  mov     edx, 9
0x180010959  mov     rcx, rbx
0x18001095c  call    ?CheckState@CState@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@@Z; CTSSession::CState::CheckState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002)
0x180010961  mov     edi, eax
0x180010963  mov     r14d, [rbx]
0x180010966  test    eax, eax
0x180010968  jns     short loc_18001098B
0x18001096a  mov     ecx, r14d
0x18001096d  call    ?GetStateName@CUtils@@SAPEBDW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@@Z; CUtils::GetStateName(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)
0x180010972  mov     r8, rax
0x180010975  lea     rdx, aInvalidStateFo; "invalid state for EvCsrConnected, state"...
0x18001097c  mov     ecx, 8; int
0x180010981  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180010986  jmp     loc_180010ABB
0x18001098b  cmp     eax, 1
0x18001098e  jnz     short loc_1800109D8
0x180010990  mov     ecx, r14d; int
0x180010993  call    ?GetLsmStateName@@YAPEBGH@Z; GetLsmStateName(int)
0x180010998  mov     r9, rax
0x18001099b  mov     ecx, 9; int
0x1800109a0  call    ?GetLsmEventName@@YAPEBGH@Z; GetLsmEventName(int)
0x1800109a5  mov     ecx, 4
0x1800109aa  test    byte ptr cs:?g_DebugTraceComponent@@3KA, cl; ulong g_DebugTraceComponent
0x1800109b0  jz      loc_180010AE0
0x1800109b6  mov     [rsp+190h+var_170], rax
0x1800109bb  mov     r8d, [rsi+6D0h]
0x1800109c2  lea     rdx, aNoChangeToSess; "No change to session %d state %ws with "...
0x1800109c9  mov     ecx, 2; int
0x1800109ce  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800109d3  jmp     loc_180010AE0
0x1800109d8  mov     r15d, [rsi+6D0h]
0x1800109df  xorps   xmm0, xmm0
0x1800109e2  xor     eax, eax
0x1800109e4  movups  [rsp+190h+var_148], xmm0
0x1800109e9  movups  [rsp+190h+var_138], xmm0
0x1800109ee  movups  [rsp+190h+var_128], xmm0
0x1800109f3  mov     [rsp+190h+var_118], rax
0x1800109f8  lea     rdx, [rsp+190h+var_148]; struct __PTSSessInfo *
0x1800109fd  mov     rcx, rsi; this
0x180010a00  call    ?InitializeNotifyInfo@CTSSession@@AEAAJPEAU__PTSSessInfo@@@Z; CTSSession::InitializeNotifyInfo(__PTSSessInfo *)
0x180010a05  mov     edi, eax
0x180010a07  mov     eax, 14CBh
0x180010a0c  lea     ecx, [rax+8]
0x180010a0f  cmp     r15d, r12d
0x180010a12  cmovz   eax, ecx
0x180010a15  mov     edx, 9
0x180010a1a  lea     ecx, [rdx-5]
0x180010a1d  cmovz   edx, ecx
0x180010a20  mov     dword ptr [rsp+190h+var_170], eax
0x180010a24  lea     r9, [rsp+190h+var_118]
0x180010a29  lea     r8, [rsp+190h+var_128+8]
0x180010a2e  mov     rcx, rbx
0x180010a31  call    ?ChangeState@CState@CTSSession@@QEAA?AW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@W4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@PEAKPEAT_LARGE_INTEGER@@K@Z; CTSSession::CState::ChangeState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002,ulong *,_LARGE_INTEGER *,ulong)
0x180010a36  test    edi, edi
0x180010a38  js      short loc_180010AA9
0x180010a3a  mov     ebx, [rbx]
0x180010a3c  lea     rcx, [rsp+190h+Resource]; this
0x180010a41  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180010a46  mov     rcx, [rsi+720h]
0x180010a4d  add     rcx, 728h
0x180010a54  mov     rax, [rcx]
0x180010a57  mov     r9d, r14d
0x180010a5a  mov     r8d, ebx
0x180010a5d  lea     rdx, [rsp+190h+var_148]
0x180010a62  mov     rax, [rax+68h]
0x180010a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a6b  mov     rcx, qword ptr [rsp+190h+var_148]
0x180010a70  test    rcx, rcx
0x180010a73  jz      short loc_180010A8A
0x180010a75  mov     rax, [rcx]
0x180010a78  mov     rax, [rax+10h]
0x180010a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a81  mov     qword ptr [rsp+190h+var_148], 0
0x180010a8a  mov     rcx, qword ptr [rsp+190h+var_128]
0x180010a8f  test    rcx, rcx
0x180010a92  jz      short loc_180010AA9
0x180010a94  mov     rax, [rcx]
0x180010a97  mov     rax, [rax+10h]
0x180010a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010aa0  mov     qword ptr [rsp+190h+var_128], 0
0x180010aa9  cmp     qword ptr [rsi+718h], 0
0x180010ab1  jnz     short loc_180010AB7
0x180010ab3  xor     edi, edi
0x180010ab5  jmp     short loc_180010AE0
0x180010ab7  test    edi, edi
0x180010ab9  jns     short loc_180010AE0
0x180010abb  mov     r14d, 4
0x180010ac1  cmp     r15d, r12d
0x180010ac4  jz      short loc_180010AD1
0x180010ac6  cmp     r15d, 0FFFFFFFFh
0x180010aca  mov     edx, 9
0x180010acf  jnz     short loc_180010AD4
0x180010ad1  mov     edx, r14d
0x180010ad4  mov     r8d, edi
0x180010ad7  mov     rcx, rsi
0x180010ada  call    ?LogFailedTransition@CTSSession@@AEAAXW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@J@Z; CTSSession::LogFailedTransition(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002,long)
0x180010adf  nop
0x180010ae0  cmp     [rsp+190h+var_150], 0
0x180010ae5  jz      short loc_180010AFF
0x180010ae7  mov     rcx, [rsp+190h+Resource]; Resource
0x180010aec  cmp     dword ptr [rcx+60h], 0
0x180010af0  jz      short loc_180010AFF
0x180010af2  call    cs:__imp_RtlReleaseResource
0x180010af9  nop     dword ptr [rax+rax+00h]
0x180010afe  nop
0x180010aff  lea     rcx, [rbp+90h+var_F0]; this
0x180010b03  call    ??1CTSSessionTrace@@UEAA@XZ; CTSSessionTrace::~CTSSessionTrace(void)
0x180010b08  nop
0x180010b09  cmp     [rbp+90h+var_100], 0
0x180010b0d  jl      short loc_180010B25
0x180010b0f  lea     rdx, [rbp+90h+var_110]
0x180010b13  mov     ecx, 2
0x180010b18  call    cs:__imp_EtwEventActivityIdControl
0x180010b1f  nop     dword ptr [rax+rax+00h]
0x180010b24  nop
0x180010b25  mov     rcx, [rsp+190h+var_160]
0x180010b2a  test    rcx, rcx
0x180010b2d  jz      short loc_180010B3C
0x180010b2f  mov     rax, [rcx]
0x180010b32  mov     rax, [rax+10h]
0x180010b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b3b  nop
0x180010b3c  mov     eax, edi
0x180010b3e  mov     rcx, [rbp+90h+var_30]
0x180010b42  xor     rcx, rsp; StackCookie
0x180010b45  call    __security_check_cookie
0x180010b4a  lea     r11, [rsp+190h+var_20]
0x180010b52  mov     rbx, [r11+38h]
0x180010b56  mov     rsi, [r11+40h]
0x180010b5a  mov     rsp, r11
0x180010b5d  pop     r15
0x180010b5f  pop     r14
0x180010b61  pop     r12
0x180010b63  pop     rdi
0x180010b64  pop     rbp
0x180010b65  retn
```
