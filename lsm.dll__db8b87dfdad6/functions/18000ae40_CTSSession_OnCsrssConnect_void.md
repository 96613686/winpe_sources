# CTSSession::OnCsrssConnect(void)

- ea: `0x18000ae40`
- end: `0x18000b188`
- name: `?OnCsrssConnect@CTSSession@@AEAAJXZ`
- size: `840`
- prototype: `__int64 __fastcall(CTSSession *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ae30`

## callees

- `0x1800074c0`
- `0x180008f04`
- `0x1800092a4`
- `0x1800093d0`
- `0x1800093f8`
- `0x180009420`
- `0x180009810`
- `0x180009a68`
- `0x18000aad4`
- `0x18000ae40`
- `0x18001ce00`
- `0x180025c30`
- `0x180028784`
- `0x18004b460`
- `0x180097010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18000b120`
- `ntdll!RtlReleaseResource` at `0x18000b120`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000aef4`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000aef4`
- `ntdll!EtwEventActivityIdControl` at `0x18000aeab`
- `ntdll!EtwEventActivityIdControl` at `0x18000b140`
- `ntdll!EtwEventActivityIdControl` at `0x18000aeab`
- `ntdll!EtwEventActivityIdControl` at `0x18000b140`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000ae7c`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000ae7c`

## string_xrefs

- `0x18000af1d`: `OpenNtSessionHandle failed: 0x%x in %s`
- `0x18000af31`: `OpenNtSessionHandle failed: 0x%x in %s`
- `0x18000af13`: `CTSSession::OpenNtSessionHandle`

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
0x18000ae40  mov     [rsp-8+arg_8], rbx
0x18000ae45  mov     [rsp-8+arg_10], rsi
0x18000ae4a  push    rbp
0x18000ae4b  push    rdi
0x18000ae4c  push    r12
0x18000ae4e  push    r14
0x18000ae50  push    r15
0x18000ae52  lea     rbp, [rsp-70h]
0x18000ae57  sub     rsp, 170h
0x18000ae5e  mov     rax, cs:__security_cookie
0x18000ae65  xor     rax, rsp
0x18000ae68  mov     [rbp+90h+var_30], rax
0x18000ae6c  mov     rsi, rcx
0x18000ae6f  mov     [rsp+190h+var_160], 0
0x18000ae78  or      r15d, 0FFFFFFFFh
0x18000ae7c  call    cs:__imp_WTSGetServiceSessionId
0x18000ae82  mov     r12d, eax
0x18000ae85  lea     rcx, [rsi+0C88h]
0x18000ae8c  mov     [rbp+90h+var_100], 80004005h
0x18000ae93  lea     r14d, [r15+5]
0x18000ae97  test    rcx, rcx
0x18000ae9a  jz      short loc_18000AEBA
0x18000ae9c  movups  xmm0, xmmword ptr [rcx]
0x18000ae9f  movdqu  [rbp+90h+var_110], xmm0
0x18000aea4  lea     rdx, [rbp+90h+var_110]
0x18000aea8  mov     ecx, r14d
0x18000aeab  call    cs:__imp_EtwEventActivityIdControl
0x18000aeb1  test    eax, eax
0x18000aeb3  jnz     short loc_18000AEBA
0x18000aeb5  mov     [rbp+90h+var_100], eax
0x18000aeb8  jmp     short loc_18000AEC1
0x18000aeba  xorps   xmm0, xmm0
0x18000aebd  movups  [rbp+90h+var_110], xmm0
0x18000aec1  mov     r8, rsi; struct ITSSession *
0x18000aec4  lea     rbx, aCtssessionOncs_0; "CTSSession::OnCsrssConnect"
0x18000aecb  mov     rdx, rbx; char *
0x18000aece  lea     rcx, [rbp+90h+var_F0]; this
0x18000aed2  call    ??0CTSSessionTrace@@QEAA@PEBDPEAUITSSession@@@Z; CTSSessionTrace::CTSSessionTrace(char const *,ITSSession *)
0x18000aed7  nop
0x18000aed8  lea     rcx, [rsi+740h]; Resource
0x18000aedf  mov     [rsp+190h+Resource], rcx
0x18000aee4  mov     [rsp+190h+var_150], 1
0x18000aeec  cmp     dword ptr [rcx+60h], 0
0x18000aef0  jz      short loc_18000AEFB
0x18000aef2  mov     dl, 1; Wait
0x18000aef4  call    cs:__imp_RtlAcquireResourceExclusive
0x18000aefa  nop
0x18000aefb  lea     rdx, [rsi+1940h]; void **
0x18000af02  mov     ecx, [rsi+6D0h]; int
0x18000af08  call    ?OpenNtSessionHandle@ISessionManagerInternal@@SAJJPEAPEAX@Z; ISessionManagerInternal::OpenNtSessionHandle(long,void * *)
0x18000af0d  mov     edi, eax
0x18000af0f  test    eax, eax
0x18000af11  jns     short loc_18000AF4A
0x18000af13  lea     r9, aCtssessionOpen; "CTSSession::OpenNtSessionHandle"
0x18000af1a  mov     r8d, eax
0x18000af1d  lea     rdx, aOpenntsessionh; "OpenNtSessionHandle failed: 0x%x in %s"
0x18000af24  mov     ecx, 8; int
0x18000af29  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000af2e  mov     r8d, edi
0x18000af31  lea     rdx, aOpenntsessionh; "OpenNtSessionHandle failed: 0x%x in %s"
0x18000af38  mov     r9, rbx
0x18000af3b  mov     ecx, 8; int
0x18000af40  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000af45  jmp     loc_18000B0EF
0x18000af4a  mov     rcx, [rsi+638h]
0x18000af51  mov     rax, [rcx]
0x18000af54  lea     r8, [rsp+190h+var_160]
0x18000af59  lea     rdx, IID_ITSSession
0x18000af60  mov     rax, [rax+18h]
0x18000af64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af69  mov     edi, eax
0x18000af6b  test    eax, eax
0x18000af6d  jns     short loc_18000AF7B
0x18000af6f  mov     r8d, eax
0x18000af72  lea     rdx, aQiItssessionFa; "QI( ITSSession ) failed: 0x%x in %s"
0x18000af79  jmp     short loc_18000AF38
0x18000af7b  lea     rbx, [rsi+0CB8h]
0x18000af82  mov     edx, 9
0x18000af87  mov     rcx, rbx
0x18000af8a  call    ?CheckState@CState@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@@Z; CTSSession::CState::CheckState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002)
0x18000af8f  mov     edi, eax
0x18000af91  mov     r14d, [rbx]
0x18000af94  test    eax, eax
0x18000af96  jns     short loc_18000AFB9
0x18000af98  mov     ecx, r14d
0x18000af9b  call    ?GetStateName@CUtils@@SAPEBDW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@@Z; CUtils::GetStateName(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)
0x18000afa0  mov     r8, rax
0x18000afa3  lea     rdx, aInvalidStateFo; "invalid state for EvCsrConnected, state"...
0x18000afaa  mov     ecx, 8; int
0x18000afaf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000afb4  jmp     loc_18000B0E9
0x18000afb9  cmp     eax, 1
0x18000afbc  jnz     short loc_18000B006
0x18000afbe  mov     ecx, r14d; int
0x18000afc1  call    ?GetLsmStateName@@YAPEBGH@Z; GetLsmStateName(int)
0x18000afc6  mov     r9, rax
0x18000afc9  mov     ecx, 9; int
0x18000afce  call    ?GetLsmEventName@@YAPEBGH@Z; GetLsmEventName(int)
0x18000afd3  mov     ecx, 4
0x18000afd8  test    byte ptr cs:?g_DebugTraceComponent@@3KA, cl; ulong g_DebugTraceComponent
0x18000afde  jz      loc_18000B10E
0x18000afe4  mov     [rsp+190h+var_170], rax
0x18000afe9  mov     r8d, [rsi+6D0h]
0x18000aff0  lea     rdx, aNoChangeToSess; "No change to session %d state %ws with "...
0x18000aff7  mov     ecx, 2; int
0x18000affc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b001  jmp     loc_18000B10E
0x18000b006  mov     r15d, [rsi+6D0h]
0x18000b00d  xorps   xmm0, xmm0
0x18000b010  xor     eax, eax
0x18000b012  movups  [rsp+190h+var_148], xmm0
0x18000b017  movups  [rsp+190h+var_138], xmm0
0x18000b01c  movups  [rsp+190h+var_128], xmm0
0x18000b021  mov     [rsp+190h+var_118], rax
0x18000b026  lea     rdx, [rsp+190h+var_148]; struct __PTSSessInfo *
0x18000b02b  mov     rcx, rsi; this
0x18000b02e  call    ?InitializeNotifyInfo@CTSSession@@AEAAJPEAU__PTSSessInfo@@@Z; CTSSession::InitializeNotifyInfo(__PTSSessInfo *)
0x18000b033  mov     edi, eax
0x18000b035  mov     eax, 14CBh
0x18000b03a  lea     ecx, [rax+8]
0x18000b03d  cmp     r15d, r12d
0x18000b040  cmovz   eax, ecx
0x18000b043  mov     edx, 9
0x18000b048  lea     ecx, [rdx-5]
0x18000b04b  cmovz   edx, ecx
0x18000b04e  mov     dword ptr [rsp+190h+var_170], eax
0x18000b052  lea     r9, [rsp+190h+var_118]
0x18000b057  lea     r8, [rsp+190h+var_128+8]
0x18000b05c  mov     rcx, rbx
0x18000b05f  call    ?ChangeState@CState@CTSSession@@QEAA?AW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@W4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@PEAKPEAT_LARGE_INTEGER@@K@Z; CTSSession::CState::ChangeState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002,ulong *,_LARGE_INTEGER *,ulong)
0x18000b064  test    edi, edi
0x18000b066  js      short loc_18000B0D7
0x18000b068  mov     ebx, [rbx]
0x18000b06a  lea     rcx, [rsp+190h+Resource]; this
0x18000b06f  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18000b074  mov     rcx, [rsi+720h]
0x18000b07b  add     rcx, 728h
0x18000b082  mov     rax, [rcx]
0x18000b085  mov     r9d, r14d
0x18000b088  mov     r8d, ebx
0x18000b08b  lea     rdx, [rsp+190h+var_148]
0x18000b090  mov     rax, [rax+68h]
0x18000b094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b099  mov     rcx, qword ptr [rsp+190h+var_148]
0x18000b09e  test    rcx, rcx
0x18000b0a1  jz      short loc_18000B0B8
0x18000b0a3  mov     rax, [rcx]
0x18000b0a6  mov     rax, [rax+10h]
0x18000b0aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0af  mov     qword ptr [rsp+190h+var_148], 0
0x18000b0b8  mov     rcx, qword ptr [rsp+190h+var_128]
0x18000b0bd  test    rcx, rcx
0x18000b0c0  jz      short loc_18000B0D7
0x18000b0c2  mov     rax, [rcx]
0x18000b0c5  mov     rax, [rax+10h]
0x18000b0c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0ce  mov     qword ptr [rsp+190h+var_128], 0
0x18000b0d7  cmp     qword ptr [rsi+718h], 0
0x18000b0df  jnz     short loc_18000B0E5
0x18000b0e1  xor     edi, edi
0x18000b0e3  jmp     short loc_18000B10E
0x18000b0e5  test    edi, edi
0x18000b0e7  jns     short loc_18000B10E
0x18000b0e9  mov     r14d, 4
0x18000b0ef  cmp     r15d, r12d
0x18000b0f2  jz      short loc_18000B0FF
0x18000b0f4  cmp     r15d, 0FFFFFFFFh
0x18000b0f8  mov     edx, 9
0x18000b0fd  jnz     short loc_18000B102
0x18000b0ff  mov     edx, r14d
0x18000b102  mov     r8d, edi
0x18000b105  mov     rcx, rsi
0x18000b108  call    ?LogFailedTransition@CTSSession@@AEAAXW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@J@Z; CTSSession::LogFailedTransition(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002,long)
0x18000b10d  nop
0x18000b10e  cmp     [rsp+190h+var_150], 0
0x18000b113  jz      short loc_18000B127
0x18000b115  mov     rcx, [rsp+190h+Resource]; Resource
0x18000b11a  cmp     dword ptr [rcx+60h], 0
0x18000b11e  jz      short loc_18000B127
0x18000b120  call    cs:__imp_RtlReleaseResource
0x18000b126  nop
0x18000b127  lea     rcx, [rbp+90h+var_F0]; this
0x18000b12b  call    ??1CTSSessionTrace@@UEAA@XZ; CTSSessionTrace::~CTSSessionTrace(void)
0x18000b130  nop
0x18000b131  cmp     [rbp+90h+var_100], 0
0x18000b135  jl      short loc_18000B147
0x18000b137  lea     rdx, [rbp+90h+var_110]
0x18000b13b  mov     ecx, 2
0x18000b140  call    cs:__imp_EtwEventActivityIdControl
0x18000b146  nop
0x18000b147  mov     rcx, [rsp+190h+var_160]
0x18000b14c  test    rcx, rcx
0x18000b14f  jz      short loc_18000B15E
0x18000b151  mov     rax, [rcx]
0x18000b154  mov     rax, [rax+10h]
0x18000b158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b15d  nop
0x18000b15e  mov     eax, edi
0x18000b160  mov     rcx, [rbp+90h+var_30]
0x18000b164  xor     rcx, rsp; StackCookie
0x18000b167  call    __security_check_cookie
0x18000b16c  lea     r11, [rsp+190h+var_20]
0x18000b174  mov     rbx, [r11+38h]
0x18000b178  mov     rsi, [r11+40h]
0x18000b17c  mov     rsp, r11
0x18000b17f  pop     r15
0x18000b181  pop     r14
0x18000b183  pop     r12
0x18000b185  pop     rdi
0x18000b186  pop     rbp
0x18000b187  retn
```
