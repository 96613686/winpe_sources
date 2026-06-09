# CPipeVC::CreateVirtualChannel(IRDPCoreChannelManager *,char *,ulong,void * *)

- ea: `0x1800097d0`
- end: `0x180009e55`
- name: `?CreateVirtualChannel@CPipeVC@@UEAAJPEAUIRDPCoreChannelManager@@PEADKPEAPEAX@Z`
- size: `1669`
- prototype: `__int64 __fastcall(CPipeVC *__hidden this, struct IRDPCoreChannelManager *, char *, unsigned int, void **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800071c0`
- `0x1800071f0`
- `0x1800091a8`
- `0x1800097d0`
- `0x18000a8e0`
- `0x180012200`
- `0x180016684`
- `0x18002e600`
- `0x1800598d0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180009cc7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180009cc7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009b1a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009d1d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009b1a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009d1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d9f`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180009870`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180009870`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18000991e`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18000991e`
- `RDPBASE!RDPAPI_GetGlobalObject` at `0x18000993e`
- `RDPBASE!RDPAPI_GetGlobalObject` at `0x18000993e`

## string_xrefs

- `0x180009a98`: `Failed to create Virtual Channel on Stack`
- `0x180009b69`: `Wait for open event timed out: vc not bound`
- `0x180009b02`: `Failed to Open Virtual Channel on Stack`
- `0x180009c5d`: `Client side of VC binding not done.`
- `0x180009bca`: `Wait for open event failed: vc not bound`
- `0x180009d0d`: `IssueFirstReadOnPipeThreadSync failed`
- `0x180009d67`: `Failed WaitForSingleObject Call waiting for IssueFirstReadOnPipeThreadSync`

## pseudocode

```c
__int64 __fastcall CPipeVC::CreateVirtualChannel(
        CPipeVC *this,
        struct IRDPCoreChannelManager *a2,
        char *a3,
        unsigned int a4,
        void **a5)
{
  __int64 v9; // r13
  unsigned int CurrentThreadActivityIdPrefix; // eax
  _QWORD *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  signed int GlobalObject; // ebx
  unsigned int v15; // eax
  unsigned int v16; // eax
  int v17; // edx
  const char *v18; // rcx
  DWORD v19; // eax
  unsigned int v20; // eax
  signed int LastError; // eax
  PVOID *v22; // rax
  int v23; // ebx
  unsigned int v24; // eax
  signed int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  HANDLE hObject; // [rsp+30h] [rbp-38h] BYREF
  __int64 v31; // [rsp+38h] [rbp-30h] BYREF
  __int64 v32; // [rsp+40h] [rbp-28h] BYREF
  __int64 v33; // [rsp+48h] [rbp-20h] BYREF
  char *v34; // [rsp+50h] [rbp-18h] BYREF
  __int64 v35; // [rsp+B0h] [rbp+48h] BYREF

  v35 = 0;
  v33 = 0;
  v32 = 0;
  *a5 = (void *)-1LL;
  v9 = 0;
  v31 = 0;
  hObject = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      80,
      (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)a3);
  }
  v11 = (_QWORD *)((char *)this + 40);
  v34 = (char *)this + 40;
  if ( *((_DWORD *)this + 12) )
    PAL_System_CritSecEnter(*v11, a2, a3);
  if ( !(unsigned int)CPipeVC::IsValidObjectState((CPipeVC *)((char *)this - 48)) )
  {
    GlobalObject = -2147024884;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        81,
        (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
        v15,
        (__int64)"!IsValidObjectState()",
        12);
    }
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v34);
    goto LABEL_85;
  }
  if ( *((_QWORD *)this + 7) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v33, v12, v13);
    v9 = *((_QWORD *)this + 7);
    v33 = v9;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v33);
  }
  if ( this != (CPipeVC *)-40LL && *((_DWORD *)this + 12) )
    PAL_System_CritSecLeave(*v11);
  *((_DWORD *)this + 16) = a4 & 3;
  GlobalObject = RDPAPI_GetGlobalObject(&CLSID_GlobalPipeMgr, &IID_IGlobalPipeMgr, &v32);
  if ( GlobalObject < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_85;
    }
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 82;
    goto LABEL_23;
  }
  GlobalObject = (*(__int64 (__fastcall **)(__int64, char *, HANDLE *, char *))(*(_QWORD *)v32 + 24LL))(
                   v32,
                   (char *)this + 80,
                   &hObject,
                   a3);
  if ( GlobalObject < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_85;
    }
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 83;
LABEL_23:
    v18 = "Failed to get Global Pipe Mgr";
LABEL_84:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
      v16,
      (__int64)v18,
      GlobalObject);
    goto LABEL_85;
  }
  GlobalObject = (**(__int64 (__fastcall ***)(struct IRDPCoreChannelManager *, GUID *, __int64 *))a2)(
                   a2,
                   &IID_IRDPCoreChannelManagerEx,
                   &v31);
  if ( GlobalObject < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_85;
    }
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 84;
    v18 = "Failed to QI for the channel manager ex interface";
    goto LABEL_84;
  }
  GlobalObject = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, __int64 *))(*(_QWORD *)v31 + 24LL))(
                   v31,
                   a3,
                   a4,
                   &v35);
  if ( GlobalObject < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_85;
    }
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 85;
    v18 = "Failed to create Virtual Channel on Stack";
    goto LABEL_84;
  }
  GlobalObject = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v35 + 40LL))(
                   v35,
                   ((unsigned __int64)this + 8) & ((unsigned __int128)-(__int128)((unsigned __int64)this - 48) >> 64),
                   0);
  if ( GlobalObject < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_85;
    }
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 86;
    v18 = "Failed to Open Virtual Channel on Stack";
    goto LABEL_84;
  }
  v19 = WaitForSingleObject(*((HANDLE *)this + 47), 0x2710u);
  if ( v19 == 258 )
  {
    GlobalObject = -2147023436;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        87,
        (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
        v20,
        (__int64)"Wait for open event timed out: vc not bound",
        180);
    }
    goto LABEL_85;
  }
  if ( v19 )
  {
    LastError = GetLastError();
    GlobalObject = LastError;
    if ( LastError > 0 )
      GlobalObject = (unsigned __int16)LastError | 0x80070000;
    if ( GlobalObject < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_85;
      }
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 88;
      v18 = "Wait for open event failed: vc not bound";
      goto LABEL_84;
    }
  }
  v22 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v23 = *((_DWORD *)this + 24);
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      89,
      (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
      v24,
      (__int64)a3,
      v23);
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
  GlobalObject = *((_DWORD *)this + 24);
  if ( GlobalObject < 0 )
  {
    if ( v22 == &WPP_GLOBAL_Control || (*((_BYTE *)v22 + 28) & 8) == 0 || *((_BYTE *)v22 + 25) < 2u )
      goto LABEL_85;
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 90;
    v18 = "Client side of VC binding not done.";
    goto LABEL_84;
  }
  GlobalObject = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v35)(
                   v35,
                   &IID_IRDPCoreVirtualChannelEx,
                   (char *)this + 72);
  if ( GlobalObject < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_85;
    }
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 91;
    v18 = "Failed to QI the VCEx interface";
    goto LABEL_84;
  }
  ResetEvent(*((HANDLE *)this + 11));
  GlobalObject = CPipeVCMgr::IssueFirstReadWorkItem(*((CPipeVCMgr **)this + 4), (CPipeVC *)((char *)this - 48));
  if ( GlobalObject < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_85;
    }
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 92;
    v18 = "IssueFirstReadOnPipeThreadSync failed";
    goto LABEL_84;
  }
  if ( !WaitForSingleObject(*((HANDLE *)this + 11), 0xFFFFFFFF) )
    goto LABEL_89;
  v25 = GetLastError();
  GlobalObject = v25;
  if ( v25 > 0 )
    GlobalObject = (unsigned __int16)v25 | 0x80070000;
  if ( GlobalObject >= 0 )
  {
LABEL_89:
    *a5 = hObject;
    goto LABEL_90;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 93;
    v18 = "Failed WaitForSingleObject Call waiting for IssueFirstReadOnPipeThreadSync";
    goto LABEL_84;
  }
LABEL_85:
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
    *a5 = (void *)-1LL;
  }
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 32LL))(v35);
LABEL_90:
  v26 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v27 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v28 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  return (unsigned int)GlobalObject;
}

```

## disassembly

```asm
0x1800097d0  push    rbp
0x1800097d2  push    rbx
0x1800097d3  push    rsi
0x1800097d4  push    rdi
0x1800097d5  push    r12
0x1800097d7  push    r13
0x1800097d9  push    r14
0x1800097db  push    r15
0x1800097dd  mov     rbp, rsp
0x1800097e0  sub     rsp, 68h
0x1800097e4  mov     rax, [rbp+arg_20]
0x1800097e8  xor     r14d, r14d
0x1800097eb  mov     esi, r9d
0x1800097ee  mov     [rbp+arg_0], r14
0x1800097f2  mov     r12, r8
0x1800097f5  mov     [rbp+var_20], r14
0x1800097f9  mov     r15, rdx
0x1800097fc  mov     [rbp+var_28], r14
0x180009800  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x180009807  mov     rdi, rcx
0x18000980a  mov     r13d, r14d
0x18000980d  mov     [rbp+var_30], r14
0x180009811  mov     [rbp+hObject], r14
0x180009815  mov     rax, cs:WPP_GLOBAL_Control
0x18000981c  lea     rcx, WPP_GLOBAL_Control
0x180009823  cmp     rax, rcx
0x180009826  jz      short loc_18000985F
0x180009828  test    dword ptr [rax+1Ch], 800h
0x18000982f  jz      short loc_18000985F
0x180009831  cmp     byte ptr [rax+19h], 4
0x180009835  jb      short loc_18000985F
0x180009837  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000983c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009843  lea     edx, [r14+50h]
0x180009847  mov     r9d, eax
0x18000984a  mov     [rsp+68h+var_48], r12
0x18000984f  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x180009856  mov     rcx, [rcx+10h]
0x18000985a  call    WPP_SF_Ds
0x18000985f  lea     rbx, [rdi+28h]
0x180009863  mov     [rbp+var_18], rbx
0x180009867  cmp     [rbx+8], r14d
0x18000986b  jz      short loc_180009876
0x18000986d  mov     rcx, [rbx]
0x180009870  call    cs:__imp_PAL_System_CritSecEnter
0x180009876  lea     r14, [rdi-30h]
0x18000987a  mov     rcx, r14; this
0x18000987d  call    ?IsValidObjectState@CPipeVC@@IEAAHXZ; CPipeVC::IsValidObjectState(void)
0x180009882  test    eax, eax
0x180009884  jnz     short loc_1800098F0
0x180009886  mov     ebx, 8007000Ch
0x18000988b  mov     rax, cs:WPP_GLOBAL_Control
0x180009892  lea     rcx, WPP_GLOBAL_Control
0x180009899  cmp     rax, rcx
0x18000989c  jz      short loc_1800098E2
0x18000989e  test    byte ptr [rax+1Ch], 8
0x1800098a2  jz      short loc_1800098E2
0x1800098a4  cmp     byte ptr [rax+19h], 2
0x1800098a8  jb      short loc_1800098E2
0x1800098aa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800098af  lea     rcx, aIsvalidobjects; "!IsValidObjectState()"
0x1800098b6  mov     [rsp+68h+var_40], 8007000Ch
0x1800098be  mov     [rsp+68h+var_48], rcx
0x1800098c3  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x1800098ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098d1  mov     edx, 51h ; 'Q'
0x1800098d6  mov     r9d, eax
0x1800098d9  mov     rcx, [rcx+10h]
0x1800098dd  call    WPP_SF_DsD
0x1800098e2  lea     rcx, [rbp+var_18]; this
0x1800098e6  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800098eb  jmp     loc_180009D91
0x1800098f0  cmp     [rdi+38h], r13
0x1800098f4  jz      short loc_180009910
0x1800098f6  lea     rcx, [rbp+var_20]
0x1800098fa  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800098ff  mov     r13, [rdi+38h]
0x180009903  lea     rcx, [rbp+var_20]
0x180009907  mov     [rbp+var_20], r13
0x18000990b  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180009910  test    rbx, rbx
0x180009913  jz      short loc_180009924
0x180009915  cmp     dword ptr [rbx+8], 0
0x180009919  jz      short loc_180009924
0x18000991b  mov     rcx, [rbx]
0x18000991e  call    cs:__imp_PAL_System_CritSecLeave
0x180009924  mov     eax, esi
0x180009926  lea     r8, [rbp+var_28]
0x18000992a  and     eax, 3
0x18000992d  lea     rdx, IID_IGlobalPipeMgr
0x180009934  lea     rcx, CLSID_GlobalPipeMgr
0x18000993b  mov     [rdi+40h], eax
0x18000993e  call    cs:__imp_RDPAPI_GetGlobalObject
0x180009944  mov     ebx, eax
0x180009946  test    eax, eax
0x180009948  jns     short loc_18000998B
0x18000994a  mov     rax, cs:WPP_GLOBAL_Control
0x180009951  lea     rcx, WPP_GLOBAL_Control
0x180009958  cmp     rax, rcx
0x18000995b  jz      loc_180009D91
0x180009961  test    byte ptr [rax+1Ch], 8
0x180009965  jz      loc_180009D91
0x18000996b  cmp     byte ptr [rax+19h], 2
0x18000996f  jb      loc_180009D91
0x180009975  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000997a  mov     edx, 52h ; 'R'
0x18000997f  lea     rcx, aFailedToGetGlo; "Failed to get Global Pipe Mgr"
0x180009986  jmp     loc_180009D6E
0x18000998b  mov     rcx, [rbp+var_28]
0x18000998f  lea     rdx, [rdi+50h]
0x180009993  mov     r9, r12
0x180009996  lea     r8, [rbp+hObject]
0x18000999a  mov     rax, [rcx]
0x18000999d  mov     rax, [rax+18h]
0x1800099a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099a6  mov     ebx, eax
0x1800099a8  test    eax, eax
0x1800099aa  jns     short loc_1800099E3
0x1800099ac  mov     rax, cs:WPP_GLOBAL_Control
0x1800099b3  lea     rcx, WPP_GLOBAL_Control
0x1800099ba  cmp     rax, rcx
0x1800099bd  jz      loc_180009D91
0x1800099c3  test    byte ptr [rax+1Ch], 8
0x1800099c7  jz      loc_180009D91
0x1800099cd  cmp     byte ptr [rax+19h], 2
0x1800099d1  jb      loc_180009D91
0x1800099d7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800099dc  mov     edx, 53h ; 'S'
0x1800099e1  jmp     short loc_18000997F
0x1800099e3  mov     rax, [r15]
0x1800099e6  lea     r8, [rbp+var_30]
0x1800099ea  lea     rdx, IID_IRDPCoreChannelManagerEx
0x1800099f1  mov     rcx, r15
0x1800099f4  mov     rax, [rax]
0x1800099f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099fc  mov     ebx, eax
0x1800099fe  test    eax, eax
0x180009a00  jns     short loc_180009A43
0x180009a02  mov     rax, cs:WPP_GLOBAL_Control
0x180009a09  lea     rcx, WPP_GLOBAL_Control
0x180009a10  cmp     rax, rcx
0x180009a13  jz      loc_180009D91
0x180009a19  test    byte ptr [rax+1Ch], 8
0x180009a1d  jz      loc_180009D91
0x180009a23  cmp     byte ptr [rax+19h], 2
0x180009a27  jb      loc_180009D91
0x180009a2d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009a32  mov     edx, 54h ; 'T'
0x180009a37  lea     rcx, aFailedToQiForT_0; "Failed to QI for the channel manager ex"...
0x180009a3e  jmp     loc_180009D6E
0x180009a43  mov     rcx, [rbp+var_30]
0x180009a47  lea     r9, [rbp+arg_0]
0x180009a4b  mov     r8d, esi
0x180009a4e  mov     rdx, r12
0x180009a51  mov     rax, [rcx]
0x180009a54  mov     rax, [rax+18h]
0x180009a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a5d  mov     ebx, eax
0x180009a5f  test    eax, eax
0x180009a61  jns     short loc_180009AA4
0x180009a63  mov     rax, cs:WPP_GLOBAL_Control
0x180009a6a  lea     rcx, WPP_GLOBAL_Control
0x180009a71  cmp     rax, rcx
0x180009a74  jz      loc_180009D91
0x180009a7a  test    byte ptr [rax+1Ch], 8
0x180009a7e  jz      loc_180009D91
0x180009a84  cmp     byte ptr [rax+19h], 2
0x180009a88  jb      loc_180009D91
0x180009a8e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009a93  mov     edx, 55h ; 'U'
0x180009a98  lea     rcx, aFailedToCreate_31; "Failed to create Virtual Channel on Sta"...
0x180009a9f  jmp     loc_180009D6E
0x180009aa4  mov     rcx, [rbp+arg_0]
0x180009aa8  lea     r8, [rdi+8]
0x180009aac  mov     rax, r14
0x180009aaf  neg     rax
0x180009ab2  mov     r9, [rcx]
0x180009ab5  sbb     rdx, rdx
0x180009ab8  and     rdx, r8
0x180009abb  xor     r8d, r8d
0x180009abe  mov     rax, [r9+28h]
0x180009ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ac7  mov     ebx, eax
0x180009ac9  test    eax, eax
0x180009acb  jns     short loc_180009B0E
0x180009acd  mov     rax, cs:WPP_GLOBAL_Control
0x180009ad4  lea     rcx, WPP_GLOBAL_Control
0x180009adb  cmp     rax, rcx
0x180009ade  jz      loc_180009D91
0x180009ae4  test    byte ptr [rax+1Ch], 8
0x180009ae8  jz      loc_180009D91
0x180009aee  cmp     byte ptr [rax+19h], 2
0x180009af2  jb      loc_180009D91
0x180009af8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009afd  mov     edx, 56h ; 'V'
0x180009b02  lea     rcx, aFailedToOpenVi; "Failed to Open Virtual Channel on Stack"
0x180009b09  jmp     loc_180009D6E
0x180009b0e  mov     rcx, [rdi+178h]; hHandle
0x180009b15  mov     edx, 2710h; dwMilliseconds
0x180009b1a  call    cs:__imp_WaitForSingleObject
0x180009b20  cmp     eax, 102h
0x180009b25  jnz     short loc_180009B75
0x180009b27  mov     ebx, 800705B4h
0x180009b2c  mov     rax, cs:WPP_GLOBAL_Control
0x180009b33  lea     rcx, WPP_GLOBAL_Control
0x180009b3a  cmp     rax, rcx
0x180009b3d  jz      loc_180009D91
0x180009b43  test    byte ptr [rax+1Ch], 8
0x180009b47  jz      loc_180009D91
0x180009b4d  cmp     byte ptr [rax+19h], 2
0x180009b51  jb      loc_180009D91
0x180009b57  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009b5c  mov     edx, 57h ; 'W'
0x180009b61  mov     [rsp+68h+var_40], 800705B4h
0x180009b69  lea     rcx, aWaitForOpenEve; "Wait for open event timed out: vc not b"...
0x180009b70  jmp     loc_180009D72
0x180009b75  mov     r15d, 80070000h
0x180009b7b  test    eax, eax
0x180009b7d  jz      short loc_180009BD6
0x180009b7f  call    cs:__imp_GetLastError
0x180009b85  mov     ebx, eax
0x180009b87  test    eax, eax
0x180009b89  jle     short loc_180009B91
0x180009b8b  movzx   ebx, ax
0x180009b8e  or      ebx, r15d
0x180009b91  test    ebx, ebx
0x180009b93  jns     short loc_180009BD6
0x180009b95  mov     rax, cs:WPP_GLOBAL_Control
0x180009b9c  lea     rcx, WPP_GLOBAL_Control
0x180009ba3  cmp     rax, rcx
0x180009ba6  jz      loc_180009D91
0x180009bac  test    byte ptr [rax+1Ch], 8
0x180009bb0  jz      loc_180009D91
0x180009bb6  cmp     byte ptr [rax+19h], 2
0x180009bba  jb      loc_180009D91
0x180009bc0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009bc5  mov     edx, 58h ; 'X'
0x180009bca  lea     rcx, aWaitForOpenEve_0; "Wait for open event failed: vc not boun"...
0x180009bd1  jmp     loc_180009D6E
0x180009bd6  mov     rax, cs:WPP_GLOBAL_Control
0x180009bdd  lea     rsi, WPP_GLOBAL_Control
0x180009be4  cmp     rax, rsi
0x180009be7  jz      short loc_180009C2F
0x180009be9  test    dword ptr [rax+1Ch], 800h
0x180009bf0  jz      short loc_180009C2F
0x180009bf2  cmp     byte ptr [rax+19h], 4
0x180009bf6  jb      short loc_180009C2F
0x180009bf8  mov     ebx, [rdi+60h]
0x180009bfb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009c00  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c07  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x180009c0e  mov     edx, 59h ; 'Y'
0x180009c13  mov     [rsp+68h+var_40], ebx
0x180009c17  mov     r9d, eax
0x180009c1a  mov     [rsp+68h+var_48], r12
0x180009c1f  mov     rcx, [rcx+10h]
0x180009c23  call    WPP_SF_DsD
0x180009c28  mov     rax, cs:WPP_GLOBAL_Control
0x180009c2f  mov     ebx, [rdi+60h]
0x180009c32  test    ebx, ebx
0x180009c34  jns     short loc_180009C69
0x180009c36  cmp     rax, rsi
0x180009c39  jz      loc_180009D91
0x180009c3f  test    byte ptr [rax+1Ch], 8
0x180009c43  jz      loc_180009D91
0x180009c49  cmp     byte ptr [rax+19h], 2
0x180009c4d  jb      loc_180009D91
0x180009c53  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009c58  mov     edx, 5Ah ; 'Z'
0x180009c5d  lea     rcx, aClientSideOfVc; "Client side of VC binding not done."
0x180009c64  jmp     loc_180009D6E
0x180009c69  mov     rcx, [rbp+arg_0]
0x180009c6d  lea     r8, [rdi+48h]
0x180009c71  lea     rdx, IID_IRDPCoreVirtualChannelEx
0x180009c78  mov     rax, [rcx]
0x180009c7b  mov     rax, [rax]
0x180009c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c83  mov     ebx, eax
0x180009c85  test    eax, eax
0x180009c87  jns     short loc_180009CC3
0x180009c89  mov     rax, cs:WPP_GLOBAL_Control
0x180009c90  cmp     rax, rsi
0x180009c93  jz      loc_180009D91
0x180009c99  test    byte ptr [rax+1Ch], 8
0x180009c9d  jz      loc_180009D91
0x180009ca3  cmp     byte ptr [rax+19h], 2
0x180009ca7  jb      loc_180009D91
0x180009cad  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009cb2  mov     edx, 5Bh ; '['
0x180009cb7  lea     rcx, aFailedToQiTheV; "Failed to QI the VCEx interface"
0x180009cbe  jmp     loc_180009D6E
0x180009cc3  mov     rcx, [rdi+58h]; hEvent
0x180009cc7  call    cs:__imp_ResetEvent
0x180009ccd  mov     rcx, [rdi+20h]; this
0x180009cd1  mov     rdx, r14; struct CPipeVC *
0x180009cd4  call    ?IssueFirstReadWorkItem@CPipeVCMgr@@QEAAJPEAVCPipeVC@@@Z; CPipeVCMgr::IssueFirstReadWorkItem(CPipeVC *)
0x180009cd9  mov     ebx, eax
0x180009cdb  test    eax, eax
0x180009cdd  jns     short loc_180009D16
0x180009cdf  mov     rax, cs:WPP_GLOBAL_Control
  ... truncated ...
```
