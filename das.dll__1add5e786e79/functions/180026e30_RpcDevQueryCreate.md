# RpcDevQueryCreate

- ea: `0x180026e30`
- end: `0x1800272e6`
- name: `RpcDevQueryCreate`
- size: `1206`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, struct _DEV_QUERY_DATA *@<rdx>, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180005a70`
- `0x180009590`
- `0x180015458`
- `0x18001bf50`
- `0x180021fe4`
- `0x180024510`
- `0x180026c20`
- `0x180026e30`
- `0x180033ad0`
- `0x1800345f0`
- `0x1800363b0`
- `0x18003c79c`
- `0x180044c70`
- `0x1800536d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002716b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002716b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002715b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002715b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180026edd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180026edd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180026ef8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180026ef8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027051`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002720a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027051`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002720a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027218`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027218`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027060`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027060`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270a9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180027178`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180027178`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180027079`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800270dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800270e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180027079`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800270dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800270e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002728b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027299`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002728b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027299`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002709f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002710e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180027249`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002727d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002709f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002710e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180027249`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002727d`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180027152`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180027152`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026e9e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026e9e`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180026fb3`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180026fb3`

## pseudocode

```c
__int64 __fastcall RpcDevQueryCreate(void *a1, GUID *a2, HANDLE *a3, HANDLE *a4, PSRWLOCK *a5)
{
  GUID *v6; // r14
  signed int Data; // ebx
  unsigned __int64 v8; // r15
  HANDLE v9; // rsi
  void *v10; // r12
  struct _SLIST_ENTRY *v11; // r13
  __int64 v12; // rcx
  __int64 v13; // rcx
  int RpcClientInfo; // eax
  int v15; // eax
  unsigned __int16 *v16; // rdx
  int v17; // eax
  PSRWLOCK v18; // rdi
  HANDLE ProcessHeap; // rax
  PVOID Ptr; // rbx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  HANDLE v23; // rdx
  HANDLE *v24; // rcx
  HANDLE v25; // rbx
  HANDLE v26; // rax
  union _SLIST_HEADER *v27; // rcx
  HANDLE v28; // rax
  unsigned int v30; // [rsp+50h] [rbp-C8h] BYREF
  unsigned int v31; // [rsp+54h] [rbp-C4h] BYREF
  WINBOOL Wow64Process; // [rsp+58h] [rbp-C0h] BYREF
  unsigned int v33; // [rsp+5Ch] [rbp-BCh] BYREF
  HANDLE hProcess; // [rsp+60h] [rbp-B8h] BYREF
  void *v35; // [rsp+68h] [rbp-B0h] BYREF
  unsigned __int16 *v36; // [rsp+70h] [rbp-A8h] BYREF
  HANDLE TargetHandle; // [rsp+78h] [rbp-A0h] BYREF
  HANDLE hSourceHandle; // [rsp+80h] [rbp-98h] BYREF
  unsigned __int16 *v39; // [rsp+88h] [rbp-90h] BYREF
  PSRWLOCK SRWLock; // [rsp+90h] [rbp-88h] BYREF
  _BYTE v41[16]; // [rsp+A0h] [rbp-78h] BYREF
  int v42; // [rsp+B0h] [rbp-68h]
  int v43; // [rsp+128h] [rbp+10h] BYREF
  HANDLE *v44; // [rsp+130h] [rbp+18h]
  HANDLE *v45; // [rsp+138h] [rbp+20h]

  v45 = a4;
  v44 = a3;
  v6 = a2;
  v31 = 0;
  Data = 0;
  v39 = 0;
  v8 = 0;
  v36 = 0;
  v30 = 0;
  v9 = 0;
  hProcess = 0;
  v10 = 0;
  v35 = 0;
  TargetHandle = 0;
  v11 = 0;
  v33 = 0;
  hSourceHandle = 0;
  SRWLock = 0;
  v43 = 0;
  EventActivityIdControl(2u, a2);
  if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 8) != 0 )
  {
    McTemplateU0p_EventWriteTransfer(v12, RPC_CREATE_QUERY_START, v6);
    if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 8) != 0 )
      McTemplateU0p_EventWriteTransfer(v13, CREATE_QUERY_INCL_PROVIDERS_START, v6);
  }
  AcquireSRWLockShared(&g_srwQueryServicesStopping);
  if ( g_bQueryServicesStopping )
    Data = -2147467260;
  ReleaseSRWLockShared(&g_srwQueryServicesStopping);
  if ( Data < 0 )
    goto LABEL_31;
  Data = ValidateQueryData((struct _DEV_QUERY_DATA *)v6);
  if ( Data < 0 )
    goto LABEL_31;
  GetPerUserParams(v6[6].Data1, *(const struct _DEV_QUERY_PARAMETER **)v6[6].Data4, &v31, &v39);
  RpcClientInfo = GetRpcClientInfo(a1, &v31, v39, &v30, &hProcess, &v35, &v33, 0, &v36);
  v8 = (unsigned __int64)v36;
  Data = RpcClientInfo;
  if ( RpcClientInfo >= 0 )
  {
    Data = IsServiceSid(v36, &v43);
    if ( Data >= 0 )
    {
      Wow64Process = 0;
      v9 = hProcess;
      v15 = IsWow64Process(hProcess, &Wow64Process);
      if ( v15 )
        v15 = Wow64Process == 0;
      v10 = v35;
      v16 = 0;
      if ( !v43 )
        v16 = (unsigned __int16 *)v8;
      v17 = CQueryContext::Create(
              (struct _DEV_QUERY_DATA *)v6,
              v16,
              v30,
              v35,
              v33,
              v15,
              (struct CQueryContext **)&SRWLock);
      v18 = SRWLock;
      Data = v17;
      if ( v17 < 0 )
        goto LABEL_22;
      v6 = 0;
      v10 = 0;
      v8 &= -(__int64)(v43 != 0);
      TraceProcessName(SRWLock, v30, v9, L"QueryContext");
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl'::`2'::impl) )
      {
        ProcessHeap = GetProcessHeap();
        v11 = (struct _SLIST_ENTRY *)HeapAlloc(ProcessHeap, 0, 0x40u);
        if ( !v11 )
        {
          Data = -2147024882;
          goto LABEL_22;
        }
      }
      Ptr = v18[7].Ptr;
      CurrentProcess = GetCurrentProcess();
      if ( DuplicateHandle(CurrentProcess, Ptr, v9, &TargetHandle, 0x100000u, 0, 0)
        && (v25 = GetCurrentProcess(),
            v26 = GetCurrentProcess(),
            DuplicateHandle(v26, v25, v9, &hSourceHandle, 0x100000u, 0, 0)) )
      {
        Data = DAS::Dispatcher::Dispatch::AddActiveQuery((struct CQueryContext *)v18);
        if ( !Data )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl'::`2'::impl) )
          {
            memset_0(v41, 0, 0x40u);
            v42 = 1;
            Data = CQueryContext::SubmitWorkItem(v18, (const struct _QUERY_WORK_ITEM *)v41);
            if ( Data < 0 )
            {
LABEL_22:
              if ( v18 )
                CQueryContext::Release((CQueryContext *)v18);
              goto LABEL_31;
            }
          }
          else
          {
            _InterlockedAdd((volatile signed __int32 *)&v18[56].Ptr + 1, 1u);
            v27 = g_QueryWorkItemList;
            *((_QWORD *)&v11[1].Next + 1) = v18;
            LODWORD(v11[1].Next) = 1;
            InterlockedPushEntrySList(v27, v11);
            AcquireSRWLockExclusive(v18);
            LODWORD(v18[1].Ptr) = 1;
            ReleaseSRWLockExclusive(v18);
            SubmitThreadpoolWork(g_QueryThreadpoolWork);
          }
          *v44 = TargetHandle;
          v24 = v45;
          *v45 = hSourceHandle;
          *a5 = v18;
          goto LABEL_38;
        }
      }
      else
      {
        LastError = GetLastError();
        Data = LastError;
        if ( LastError > 0 )
          Data = (unsigned __int16)LastError | 0x80070000;
      }
      if ( Data >= 0 )
        goto LABEL_38;
      goto LABEL_22;
    }
  }
  v10 = v35;
  v9 = hProcess;
LABEL_31:
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl'::`2'::impl)
    && v11 )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v11);
  }
  if ( TargetHandle )
    DuplicateHandle(v9, TargetHandle, 0, 0, 0x100000u, 0, 1u);
  v23 = hSourceHandle;
  if ( hSourceHandle )
    DuplicateHandle(v9, hSourceHandle, 0, 0, 0x100000u, 0, 1u);
LABEL_38:
  if ( v9 )
    CloseHandle(v9);
  if ( v10 )
    CloseHandle(v10);
  if ( v6 )
    wil::details::FreeProcessHeap((wil::details *)v6, v23);
  if ( v8 )
    wil::details::FreeProcessHeap((wil::details *)v8, v23);
  if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 8) != 0 )
    McTemplateU0p_EventWriteTransfer(v24, RPC_CREATE_QUERY_STOP, v6);
  return (unsigned int)Data;
}

```

## disassembly

```asm
0x180026e30  mov     r11, rsp
0x180026e33  mov     [r11+20h], r9
0x180026e37  mov     [r11+18h], r8
0x180026e3b  push    rbx
0x180026e3c  push    rsi
0x180026e3d  push    rdi
0x180026e3e  push    r12
0x180026e40  push    r13
0x180026e42  push    r14
0x180026e44  push    r15
0x180026e46  sub     rsp, 0E0h
0x180026e4d  xor     eax, eax
0x180026e4f  mov     rdi, rcx
0x180026e52  mov     r14, rdx
0x180026e55  mov     [rsp+118h+var_C4], eax
0x180026e59  mov     ebx, eax
0x180026e5b  mov     [r11-90h], rax
0x180026e62  mov     r15d, eax
0x180026e65  mov     [rsp+118h+var_A8], rax
0x180026e6a  lea     ecx, [rax+2]; ControlCode
0x180026e6d  mov     [rsp+118h+var_C8], eax
0x180026e71  mov     esi, eax
0x180026e73  mov     [rsp+118h+hProcess], rax
0x180026e78  mov     r12d, eax
0x180026e7b  mov     [rsp+118h+var_B0], rax
0x180026e80  mov     [rsp+118h+TargetHandle], rax
0x180026e85  mov     r13d, eax
0x180026e88  mov     [rsp+118h+var_BC], eax
0x180026e8c  mov     [r11-98h], rax
0x180026e93  mov     [r11-88h], rax
0x180026e9a  mov     [r11+10h], eax
0x180026e9e  call    cs:__imp_EventActivityIdControl
0x180026ea4  mov     eax, cs:Microsoft_Windows_DeviceAssociationServiceEnableBits
0x180026eaa  test    al, 8
0x180026eac  jz      short loc_180026ED6
0x180026eae  mov     r8, r14
0x180026eb1  lea     rdx, RPC_CREATE_QUERY_START
0x180026eb8  call    McTemplateU0p_EventWriteTransfer
0x180026ebd  mov     eax, cs:Microsoft_Windows_DeviceAssociationServiceEnableBits
0x180026ec3  test    al, 8
0x180026ec5  jz      short loc_180026ED6
0x180026ec7  mov     r8, r14
0x180026eca  lea     rdx, CREATE_QUERY_INCL_PROVIDERS_START
0x180026ed1  call    McTemplateU0p_EventWriteTransfer
0x180026ed6  lea     rcx, ?g_srwQueryServicesStopping@@3U_RTL_SRWLOCK@@A; SRWLock
0x180026edd  call    cs:__imp_AcquireSRWLockShared
0x180026ee3  cmp     cs:?g_bQueryServicesStopping@@3HA, ebx; int g_bQueryServicesStopping
0x180026ee9  lea     rcx, ?g_srwQueryServicesStopping@@3U_RTL_SRWLOCK@@A; SRWLock
0x180026ef0  mov     eax, 80004004h
0x180026ef5  cmovnz  ebx, eax
0x180026ef8  call    cs:__imp_ReleaseSRWLockShared
0x180026efe  test    ebx, ebx
0x180026f00  js      loc_1800271F5
0x180026f06  mov     rcx, r14; struct _DEV_QUERY_DATA *
0x180026f09  call    ?ValidateQueryData@@YAJPEAU_DEV_QUERY_DATA@@@Z; ValidateQueryData(_DEV_QUERY_DATA *)
0x180026f0e  mov     ebx, eax
0x180026f10  test    eax, eax
0x180026f12  js      loc_1800271F5
0x180026f18  mov     rdx, [r14+68h]; struct _DEV_QUERY_PARAMETER *
0x180026f1c  lea     r9, [rsp+118h+var_90]; unsigned __int16 **
0x180026f24  mov     ecx, [r14+60h]; unsigned int
0x180026f28  lea     r8, [rsp+118h+var_C4]; unsigned int *
0x180026f2d  call    ?GetPerUserParams@@YAXKPEBU_DEV_QUERY_PARAMETER@@PEAKPEAPEAG@Z; GetPerUserParams(ulong,_DEV_QUERY_PARAMETER const *,ulong *,ushort * *)
0x180026f32  mov     r8, [rsp+118h+var_90]; unsigned __int16 *
0x180026f3a  lea     rdx, [rsp+118h+var_A8]
0x180026f3f  mov     [rsp+118h+var_D8], rdx; unsigned __int16 **
0x180026f44  lea     rax, [rsp+118h+var_BC]
0x180026f49  mov     [rsp+118h+var_E0], rsi; unsigned __int16 **
0x180026f4e  lea     r9, [rsp+118h+var_C8]; unsigned int *
0x180026f53  mov     qword ptr [rsp+118h+dwOptions], rax; unsigned int *
0x180026f58  lea     rdx, [rsp+118h+var_C4]; unsigned int *
0x180026f5d  lea     rax, [rsp+118h+var_B0]
0x180026f62  mov     rcx, rdi; void *
0x180026f65  mov     qword ptr [rsp+118h+bInheritHandle], rax; void **
0x180026f6a  lea     rax, [rsp+118h+hProcess]
0x180026f6f  mov     qword ptr [rsp+118h+dwDesiredAccess], rax; void **
0x180026f74  call    ?GetRpcClientInfo@@YAJPEAXPEAKPEAG1PEAPEAX31PEAPEAG4@Z; GetRpcClientInfo(void *,ulong *,ushort *,ulong *,void * *,void * *,ulong *,ushort * *,ushort * *)
0x180026f79  mov     r15, [rsp+118h+var_A8]
0x180026f7e  mov     ebx, eax
0x180026f80  test    eax, eax
0x180026f82  js      loc_1800271EB
0x180026f88  lea     rdx, [rsp+118h+arg_8]; int *
0x180026f90  mov     rcx, r15; unsigned __int16 *
0x180026f93  call    ?IsServiceSid@@YAJPEBGPEAH@Z; IsServiceSid(ushort const *,int *)
0x180026f98  mov     ebx, eax
0x180026f9a  test    eax, eax
0x180026f9c  js      loc_1800271EB
0x180026fa2  mov     [rsp+118h+Wow64Process], esi
0x180026fa6  lea     rdx, [rsp+118h+Wow64Process]; Wow64Process
0x180026fab  mov     rsi, [rsp+118h+hProcess]
0x180026fb0  mov     rcx, rsi; hProcess
0x180026fb3  call    cs:__imp_IsWow64Process
0x180026fb9  test    eax, eax
0x180026fbb  jz      short loc_180026FC9
0x180026fbd  xor     eax, eax
0x180026fbf  cmp     [rsp+118h+Wow64Process], eax
0x180026fc3  lea     ecx, [rax+1]
0x180026fc6  cmovz   eax, ecx
0x180026fc9  mov     r12, [rsp+118h+var_B0]
0x180026fce  lea     rcx, [rsp+118h+SRWLock]
0x180026fd6  mov     r8d, [rsp+118h+var_C8]; unsigned int
0x180026fdb  xor     edx, edx
0x180026fdd  cmp     [rsp+118h+arg_8], edx
0x180026fe4  mov     r9, r12; void *
0x180026fe7  mov     qword ptr [rsp+118h+dwOptions], rcx; struct CQueryContext **
0x180026fec  mov     rcx, r14; struct _DEV_QUERY_DATA *
0x180026fef  mov     [rsp+118h+bInheritHandle], eax; int
0x180026ff3  cmovz   rdx, r15; unsigned __int16 *
0x180026ff7  mov     eax, [rsp+118h+var_BC]
0x180026ffb  mov     [rsp+118h+dwDesiredAccess], eax; int
0x180026fff  call    ?Create@CQueryContext@@SAJPEAU_DEV_QUERY_DATA@@PEAGKPEAXHHPEAPEAV1@@Z; CQueryContext::Create(_DEV_QUERY_DATA *,ushort *,ulong,void *,int,int,CQueryContext * *)
0x180027004  mov     rdi, [rsp+118h+SRWLock]
0x18002700c  mov     ebx, eax
0x18002700e  test    eax, eax
0x180027010  js      loc_1800270C6
0x180027016  mov     eax, [rsp+118h+arg_8]
0x18002701d  lea     r9, aQuerycontext; "QueryContext"
0x180027024  mov     edx, [rsp+118h+var_C8]; unsigned int
0x180027028  xor     r14d, r14d
0x18002702b  xor     r12d, r12d
0x18002702e  mov     r8, rsi; void *
0x180027031  neg     eax
0x180027033  mov     rcx, rdi; void *
0x180027036  sbb     rax, rax
0x180027039  and     r15, rax
0x18002703c  call    ?TraceProcessName@@YAXPEAXK0PEBG@Z; TraceProcessName(void *,ulong,void *,ushort const *)
0x180027041  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher> `wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl(void)'::`2'::impl
0x180027048  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(void)
0x18002704d  test    al, al
0x18002704f  jnz     short loc_180027075
0x180027051  call    cs:__imp_GetProcessHeap
0x180027057  xor     edx, edx; dwFlags
0x180027059  lea     r8d, [r14+40h]; dwBytes
0x18002705d  mov     rcx, rax; hHeap
0x180027060  call    cs:__imp_HeapAlloc
0x180027066  mov     r13, rax
0x180027069  test    rax, rax
0x18002706c  jnz     short loc_180027075
0x18002706e  mov     ebx, 8007000Eh
0x180027073  jmp     short loc_1800270C6
0x180027075  mov     rbx, [rdi+38h]
0x180027079  call    cs:__imp_GetCurrentProcess
0x18002707f  mov     [rsp+118h+dwOptions], r12d; dwOptions
0x180027084  lea     r9, [rsp+118h+TargetHandle]; lpTargetHandle
0x180027089  mov     rcx, rax; hSourceProcessHandle
0x18002708c  mov     [rsp+118h+bInheritHandle], r12d; bInheritHandle
0x180027091  mov     r8, rsi; hTargetProcessHandle
0x180027094  mov     [rsp+118h+dwDesiredAccess], 100000h; dwDesiredAccess
0x18002709c  mov     rdx, rbx; hSourceHandle
0x18002709f  call    cs:__imp_DuplicateHandle
0x1800270a5  test    eax, eax
0x1800270a7  jnz     short loc_1800270DC
0x1800270a9  call    cs:__imp_GetLastError
0x1800270af  mov     ebx, eax
0x1800270b1  test    eax, eax
0x1800270b3  jle     short loc_1800270BE
0x1800270b5  movzx   ebx, ax
0x1800270b8  or      ebx, 80070000h
0x1800270be  test    ebx, ebx
0x1800270c0  jns     loc_180027283
0x1800270c6  test    rdi, rdi
0x1800270c9  jz      loc_1800271F5
0x1800270cf  mov     rcx, rdi; this
0x1800270d2  call    ?Release@CQueryContext@@QEAAKXZ; CQueryContext::Release(void)
0x1800270d7  jmp     loc_1800271F5
0x1800270dc  call    cs:__imp_GetCurrentProcess
0x1800270e2  mov     rbx, rax
0x1800270e5  call    cs:__imp_GetCurrentProcess
0x1800270eb  mov     [rsp+118h+dwOptions], r12d; dwOptions
0x1800270f0  lea     r9, [rsp+118h+hSourceHandle]; lpTargetHandle
0x1800270f8  mov     rcx, rax; hSourceProcessHandle
0x1800270fb  mov     [rsp+118h+bInheritHandle], r12d; bInheritHandle
0x180027100  mov     r8, rsi; hTargetProcessHandle
0x180027103  mov     [rsp+118h+dwDesiredAccess], 100000h; dwDesiredAccess
0x18002710b  mov     rdx, rbx; hSourceHandle
0x18002710e  call    cs:__imp_DuplicateHandle
0x180027114  test    eax, eax
0x180027116  jz      short loc_1800270A9
0x180027118  mov     rcx, rdi; struct CQueryContext *
0x18002711b  call    ?AddActiveQuery@Dispatch@Dispatcher@DAS@@SAJPEAVCQueryContext@@@Z; DAS::Dispatcher::Dispatch::AddActiveQuery(CQueryContext *)
0x180027120  mov     ebx, eax
0x180027122  test    eax, eax
0x180027124  jnz     short loc_1800270BE
0x180027126  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher> `wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl(void)'::`2'::impl
0x18002712d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(void)
0x180027132  test    al, al
0x180027134  jnz     short loc_180027180
0x180027136  lea     eax, [rbx+1]
0x180027139  lock add [rdi+1C4h], eax
0x180027140  mov     rcx, cs:?g_QueryWorkItemList@@3PEAT_SLIST_HEADER@@EA; ListHead
0x180027147  mov     rdx, r13; ListEntry
0x18002714a  mov     [r13+18h], rdi
0x18002714e  mov     [r13+10h], eax
0x180027152  call    cs:__imp_InterlockedPushEntrySList
0x180027158  mov     rcx, rdi; SRWLock
0x18002715b  call    cs:__imp_AcquireSRWLockExclusive
0x180027161  mov     rcx, rdi; SRWLock
0x180027164  mov     dword ptr [rdi+8], 1
0x18002716b  call    cs:__imp_ReleaseSRWLockExclusive
0x180027171  mov     rcx, cs:?g_QueryThreadpoolWork@@3PEAU_TP_WORK@@EA; pwk
0x180027178  call    cs:__imp_SubmitThreadpoolWork
0x18002717e  jmp     short loc_1800271B8
0x180027180  xor     edx, edx; Val
0x180027182  lea     rcx, [rsp+118h+var_78]; void *
0x18002718a  lea     r8d, [rdx+40h]; Size
0x18002718e  call    memset_0
0x180027193  lea     rdx, [rsp+118h+var_78]; struct _QUERY_WORK_ITEM *
0x18002719b  mov     [rsp+118h+var_68], 1
0x1800271a6  mov     rcx, rdi; SRWLock
0x1800271a9  call    ?SubmitWorkItem@CQueryContext@@IEAAJAEBU_QUERY_WORK_ITEM@@@Z; CQueryContext::SubmitWorkItem(_QUERY_WORK_ITEM const &)
0x1800271ae  mov     ebx, eax
0x1800271b0  test    eax, eax
0x1800271b2  js      loc_1800270C6
0x1800271b8  mov     rcx, [rsp+118h+arg_10]
0x1800271c0  mov     rax, [rsp+118h+TargetHandle]
0x1800271c5  mov     [rcx], rax
0x1800271c8  mov     rax, [rsp+118h+hSourceHandle]
0x1800271d0  mov     rcx, [rsp+118h+arg_18]
0x1800271d8  mov     [rcx], rax
0x1800271db  mov     rax, [rsp+118h+arg_20]
0x1800271e3  mov     [rax], rdi
0x1800271e6  jmp     loc_180027283
0x1800271eb  mov     r12, [rsp+118h+var_B0]
0x1800271f0  mov     rsi, [rsp+118h+hProcess]
0x1800271f5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher> `wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl(void)'::`2'::impl
0x1800271fc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(void)
0x180027201  test    al, al
0x180027203  jnz     short loc_18002721E
0x180027205  test    r13, r13
0x180027208  jz      short loc_18002721E
0x18002720a  call    cs:__imp_GetProcessHeap
0x180027210  mov     r8, r13; lpMem
0x180027213  xor     edx, edx; dwFlags
0x180027215  mov     rcx, rax; hHeap
0x180027218  call    cs:__imp_HeapFree
0x18002721e  mov     rdx, [rsp+118h+TargetHandle]; hSourceHandle
0x180027223  test    rdx, rdx
0x180027226  jz      short loc_18002724F
0x180027228  mov     [rsp+118h+dwOptions], 1; dwOptions
0x180027230  xor     r9d, r9d; lpTargetHandle
0x180027233  mov     [rsp+118h+bInheritHandle], 0; bInheritHandle
0x18002723b  xor     r8d, r8d; hTargetProcessHandle
0x18002723e  mov     rcx, rsi; hSourceProcessHandle
0x180027241  mov     [rsp+118h+dwDesiredAccess], 100000h; dwDesiredAccess
0x180027249  call    cs:__imp_DuplicateHandle
0x18002724f  mov     rdx, [rsp+118h+hSourceHandle]; hSourceHandle
0x180027257  test    rdx, rdx
0x18002725a  jz      short loc_180027283
0x18002725c  mov     [rsp+118h+dwOptions], 1; dwOptions
0x180027264  xor     r9d, r9d; lpTargetHandle
0x180027267  mov     [rsp+118h+bInheritHandle], 0; bInheritHandle
0x18002726f  xor     r8d, r8d; hTargetProcessHandle
0x180027272  mov     rcx, rsi; hSourceProcessHandle
0x180027275  mov     [rsp+118h+dwDesiredAccess], 100000h; dwDesiredAccess
0x18002727d  call    cs:__imp_DuplicateHandle
0x180027283  test    rsi, rsi
0x180027286  jz      short loc_180027291
0x180027288  mov     rcx, rsi; hObject
0x18002728b  call    cs:__imp_CloseHandle
0x180027291  test    r12, r12
0x180027294  jz      short loc_18002729F
0x180027296  mov     rcx, r12; hObject
0x180027299  call    cs:__imp_CloseHandle
0x18002729f  test    r14, r14
0x1800272a2  jz      short loc_1800272AC
0x1800272a4  mov     rcx, r14; this
0x1800272a7  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800272ac  test    r15, r15
0x1800272af  jz      short loc_1800272B9
0x1800272b1  mov     rcx, r15; this
0x1800272b4  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800272b9  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 8
0x1800272c0  jz      short loc_1800272D1
0x1800272c2  mov     r8, r14
0x1800272c5  lea     rdx, RPC_CREATE_QUERY_STOP
0x1800272cc  call    McTemplateU0p_EventWriteTransfer
0x1800272d1  mov     eax, ebx
0x1800272d3  add     rsp, 0E0h
0x1800272da  pop     r15
0x1800272dc  pop     r14
0x1800272de  pop     r13
0x1800272e0  pop     r12
0x1800272e2  pop     rdi
0x1800272e3  pop     rsi
0x1800272e4  pop     rbx
0x1800272e5  retn
```
