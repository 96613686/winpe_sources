# CAssociationContext::Init(ushort const *,ushort const *,ulong,ulong,_DAF_ASSOCIATION_PARAMETER const *)

- ea: `0x180055614`
- end: `0x180055e24`
- name: `?Init@CAssociationContext@@QEAAJPEBG0KKPEBU_DAF_ASSOCIATION_PARAMETER@@@Z`
- size: `2064`
- prototype: `__int64 __usercall@<rax>(CAssociationContext *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int, const struct _DAF_ASSOCIATION_PARAMETER *)`
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002eee0`

## callees

- `0x180008a50`
- `0x180009590`
- `0x180019d00`
- `0x18001a268`
- `0x18001a478`
- `0x18001fabc`
- `0x18002482c`
- `0x180026120`
- `0x18002cc94`
- `0x180033470`
- `0x1800337e8`
- `0x1800345f0`
- `0x1800377ec`
- `0x1800452a4`
- `0x180054494`
- `0x180055614`
- `0x180057180`
- `0x180057790`
- `0x180059100`
- `0x180063824`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800559af`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800559af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055873`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055873`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180055881`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180055881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800559c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055a18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055a99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800559c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055a18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055a99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800559e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180055a64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800559e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180055a64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055842`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055842`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180055a0e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180055a8f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180055a0e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180055a8f`

## pseudocode

```c
__int64 __fastcall CAssociationContext::Init(
        CAssociationContext *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        const struct _DAF_ASSOCIATION_PARAMETER *a6)
{
  unsigned __int16 *v7; // rax
  wil::details *v9; // r15
  int v10; // r9d
  int ProviderFromAepId; // eax
  int v12; // eax
  int v13; // r8d
  std::_Ref_count_base *v14; // r15
  signed int IsAssociated; // eax
  int v16; // r9d
  void *v17; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v19; // ebx
  _QWORD *v21; // rax
  int v22; // ecx
  char *v23; // r13
  _QWORD *v24; // rax
  HANDLE EventW; // r12
  signed int LastError; // eax
  void *v27; // rbx
  HANDLE CurrentProcess; // rax
  __int64 v29; // rcx
  HANDLE v30; // r15
  void *v31; // rbx
  HANDLE v32; // rax
  __int64 v33; // rcx
  _QWORD *v34; // r12
  const unsigned __int16 *v35; // rdx
  _QWORD *v36; // rbx
  int ProviderAepIdFromAepId; // eax
  int v38; // r8d
  int v39; // r9d
  __int64 v40; // rcx
  __int64 v41; // rcx
  int v42; // r8d
  char v43; // al
  int v44; // r9d
  _QWORD *v45; // rax
  char v46; // [rsp+40h] [rbp-91h]
  wil::details *v47; // [rsp+50h] [rbp-81h] BYREF
  unsigned int v48; // [rsp+58h] [rbp-79h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-71h] BYREF
  HANDLE TargetHandle; // [rsp+68h] [rbp-69h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-61h] BYREF
  std::_Ref_count_base *v52[2]; // [rsp+78h] [rbp-59h] BYREF
  HANDLE v53[2]; // [rsp+88h] [rbp-49h] BYREF
  _QWORD v54[8]; // [rsp+98h] [rbp-39h] BYREF
  _QWORD v55[8]; // [rsp+D8h] [rbp+7h] BYREF
  int RpcClientToken; // [rsp+128h] [rbp+57h] BYREF
  unsigned __int16 *v57; // [rsp+130h] [rbp+5Fh] BYREF
  unsigned int v58; // [rsp+140h] [rbp+6Fh] BYREF

  v58 = a4;
  v57 = a2;
  v7 = a2;
  RpcClientToken = 0;
  v9 = 0;
  v47 = 0;
  *(_OWORD *)v52 = 0;
  hObject = 0;
  v48 = 0;
  lpMem = 0;
  *((_DWORD *)this + 6) = a4;
  if ( *((_DWORD *)this + 7) )
  {
    RpcClientToken = -2140930033;
    if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    {
LABEL_32:
      *((_DWORD *)this + 7) = -1;
      goto LABEL_33;
    }
    v10 = 13;
    v46 = 15;
    goto LABEL_4;
  }
  ProviderFromAepId = DafStringCopy(a2, (char *)this + 8);
  RpcClientToken = ProviderFromAepId;
  if ( ProviderFromAepId < 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v10 = 14;
LABEL_8:
      v46 = ProviderFromAepId;
      v7 = v57;
LABEL_4:
      WPP_RECORDER_SF_SqD(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        (int)a2,
        (int)a3,
        v10,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        (__int64)v7,
        (char)this,
        v46);
      goto LABEL_25;
    }
    goto LABEL_25;
  }
  if ( a3 )
  {
    v12 = DafStringCopy(a3, (char *)this + 16);
    RpcClientToken = v12;
    if ( v12 < 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_SqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (int)a2,
          v13,
          15,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          (__int64)a3,
          (char)this,
          v12);
      goto LABEL_25;
    }
  }
  ProviderFromAepId = DAS::ProviderManagement::ProviderManager::GetProviderFromAepId(g_providerManager, v57, v52);
  RpcClientToken = ProviderFromAepId;
  if ( !ProviderFromAepId )
  {
    v14 = v52[0];
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_SSq(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        (int)a2,
        (int)a3,
        17,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        *(_QWORD *)v52[0],
        (__int64)v57,
        (char)this);
    *((_DWORD *)this + 98) = (*((_DWORD *)v14 + 14) >> 11) & 1;
    if ( *((_DWORD *)v14 + 18) )
      RpcClientToken = GetRpcClientToken(&hObject);
    LOBYTE(IsAssociated) = RpcClientToken;
    if ( RpcClientToken < 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v16 = 18;
LABEL_23:
        WPP_RECORDER_SF_SqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (int)a2,
          (int)a3,
          v16,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          (__int64)v57,
          (char)this,
          IsAssociated);
        goto LABEL_24;
      }
      goto LABEL_24;
    }
    IsAssociated = CAssociationContext::IsAssociated(this, hObject);
    RpcClientToken = IsAssociated;
    if ( IsAssociated )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_24;
      v16 = 19;
      goto LABEL_23;
    }
    RpcClientToken = CAssociationContext::SanitizeExtendedParamters(
                       a3,
                       a5,
                       a6,
                       &v48,
                       (struct _DAF_ASSOCIATION_PARAMETER **)&lpMem);
    if ( RpcClientToken < 0 )
      goto LABEL_24;
    v21 = std::shared_ptr<ProviderContext>::shared_ptr<ProviderContext>(v53, v52);
    RpcClientToken = CAssociationContext::InitSetAssociation((char *)this, v21, a5, (__int64)a6);
    if ( RpcClientToken < 0 )
      goto LABEL_24;
    v22 = *((_DWORD *)v14 + 12);
    *((_DWORD *)this + 8) = v22 != 0;
    TargetHandle = 0;
    if ( v22 )
    {
      v53[0] = 0;
      v23 = (char *)this + 600;
      v24 = std::shared_ptr<ProviderContext>::shared_ptr<ProviderContext>(v55, v52);
      IsAssociated = CHostContext::GetHostContext(v24, (char *)this + 600);
      RpcClientToken = IsAssociated;
      if ( IsAssociated )
      {
        if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_24;
        v16 = 20;
        goto LABEL_23;
      }
      EventW = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 7) = EventW;
      if ( !EventW )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        RpcClientToken = LastError;
        goto LABEL_24;
      }
      v27 = *(void **)(*(_QWORD *)v23 + 8LL);
      CurrentProcess = GetCurrentProcess();
      if ( !DuplicateHandle(CurrentProcess, EventW, v27, &TargetHandle, 0, 0, 2u) )
      {
        IsAssociated = GetLastError();
        if ( IsAssociated > 0 )
          IsAssociated = (unsigned __int16)IsAssociated | 0x80070000;
        RpcClientToken = IsAssociated;
        if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_24;
        v16 = 21;
        goto LABEL_23;
      }
      if ( *((_DWORD *)v14 + 18) )
      {
        if ( *((_DWORD *)v14 + 21) )
        {
          v30 = hObject;
          if ( hObject )
          {
            v31 = *(void **)(*(_QWORD *)v23 + 8LL);
            v32 = GetCurrentProcess();
            if ( !DuplicateHandle(v32, v30, v31, v53, 0, 0, 2u) )
            {
              IsAssociated = GetLastError();
              if ( IsAssociated > 0 )
                IsAssociated = (unsigned __int16)IsAssociated | 0x80070000;
              RpcClientToken = IsAssociated;
              if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
                goto LABEL_24;
              v16 = 22;
              goto LABEL_23;
            }
          }
        }
      }
      if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 0x10) != 0 )
        McTemplateU0p_EventWriteTransfer(v29, CREATE_ASSOC_CTX_PROVIDER_START, this);
      v54[0] = &RpcClientToken;
      v54[1] = this;
      v54[2] = &v57;
      v54[3] = &v58;
      v54[4] = &TargetHandle;
      v54[5] = v53;
      v54[6] = &v48;
      v54[7] = &lpMem;
      RpcClientToken = lambda_dd7b7e83695decf74624e2cfbf9d98ad_::operator()(v54);
      if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 0x10) != 0 )
        McTemplateU0p_EventWriteTransfer(v33, CREATE_ASSOC_CTX_PROVIDER_STOP, this);
      LOBYTE(IsAssociated) = RpcClientToken;
      if ( RpcClientToken )
      {
        if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_24;
        v16 = 24;
        goto LABEL_23;
      }
      v9 = v47;
LABEL_108:
      *((_DWORD *)this + 7) = 1;
      goto LABEL_25;
    }
    IsAssociated = ProviderContext::GetClassFactory(v14, (struct IClassFactory **)&TargetHandle);
    RpcClientToken = IsAssociated;
    if ( IsAssociated )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_24;
      v16 = 25;
      goto LABEL_23;
    }
    v34 = (_QWORD *)((char *)this + 576);
    RpcClientToken = (*(__int64 (__fastcall **)(HANDLE, _QWORD, GUID *, char *))(*(_QWORD *)TargetHandle + 24LL))(
                       TargetHandle,
                       0,
                       &IID_IAepAssociation,
                       (char *)this + 576);
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)TargetHandle + 16LL))(TargetHandle);
    if ( RpcClientToken )
    {
      if ( RpcClientToken == -2147467262 )
      {
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_SqD(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            (int)a2,
            (int)a3,
            26,
            &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
            (__int64)v57,
            (char)this,
            2);
        goto LABEL_24;
      }
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v16 = 27;
        LOBYTE(IsAssociated) = RpcClientToken;
        goto LABEL_23;
      }
LABEL_24:
      v9 = v47;
      goto LABEL_25;
    }
    IsAssociated = DafGetProviderNameFromAepId(v57);
    RpcClientToken = IsAssociated;
    if ( IsAssociated < 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_24;
      v16 = 28;
      goto LABEL_23;
    }
    if ( (*((_DWORD *)v14 + 14) & 0x800) != 0 )
      v35 = (const unsigned __int16 *)*((_QWORD *)this + 2);
    else
      v35 = 0;
    v36 = (_QWORD *)((char *)this + 584);
    ProviderAepIdFromAepId = CAssociationCallback::Create(
                               0,
                               v35,
                               *((_DWORD *)v14 + 19),
                               this,
                               hObject,
                               (struct CAssociationCallback **)this + 73);
    RpcClientToken = ProviderAepIdFromAepId;
    if ( ProviderAepIdFromAepId )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v39 = 29;
LABEL_87:
        WPP_RECORDER_SF_SqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (int)a2,
          v38,
          v39,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          (__int64)v57,
          (char)this,
          ProviderAepIdFromAepId);
      }
    }
    else
    {
      hObject = 0;
      ProviderAepIdFromAepId = DafGetProviderAepIdFromAepId(*((_QWORD *)this + 1), &v47);
      RpcClientToken = ProviderAepIdFromAepId;
      if ( !ProviderAepIdFromAepId )
      {
        if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 0x10) != 0 )
          McTemplateU0p_EventWriteTransfer(v40, CREATE_ASSOC_CTX_PROVIDER_START, this);
        v9 = v47;
        RpcClientToken = (*(__int64 (__fastcall **)(_QWORD, wil::details *, _QWORD, _QWORD, unsigned int, LPVOID))(*(_QWORD *)*v34 + 24LL))(
                           *v34,
                           v47,
                           v58,
                           *v36,
                           v48,
                           lpMem);
        if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 0x10) != 0 )
          McTemplateU0p_EventWriteTransfer(v41, CREATE_ASSOC_CTX_PROVIDER_STOP, this);
        v43 = RpcClientToken;
        if ( RpcClientToken >= 0 )
        {
          v45 = std::shared_ptr<ProviderContext>::shared_ptr<ProviderContext>(v55, v52);
          RpcClientToken = CAssociationContext::SetupProviderCleanup((__int64)this, (__int64)v45);
          if ( !RpcClientToken )
            goto LABEL_108;
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v34 + 96LL))(*v34);
          if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          {
LABEL_89:
            if ( *v34 )
            {
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v34 + 16LL))(*v34);
              *v34 = 0;
            }
            if ( *v36 )
            {
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v36 + 16LL))(*v36);
              *v36 = 0;
            }
            goto LABEL_25;
          }
          v44 = 32;
          v43 = RpcClientToken;
        }
        else
        {
          if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
            goto LABEL_89;
          v44 = 31;
        }
        WPP_RECORDER_SF_SqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (int)a2,
          v42,
          v44,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          (__int64)v57,
          (char)this,
          v43);
        goto LABEL_89;
      }
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v39 = 30;
        goto LABEL_87;
      }
    }
    v9 = v47;
    goto LABEL_89;
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v10 = 16;
    goto LABEL_8;
  }
LABEL_25:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( v9 )
    wil::details::FreeProcessHeap(v9, a2);
  v17 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v17);
  }
  if ( RpcClientToken < 0 )
    goto LABEL_32;
LABEL_33:
  v19 = RpcClientToken;
  if ( v52[1] )
    std::_Ref_count_base::_Decref(v52[1]);
  return v19;
}

```

## disassembly

```asm
0x180055614  mov     rax, rsp
0x180055617  mov     [rax+18h], rbx
0x18005561b  mov     [rax+20h], r9d
0x18005561f  mov     [rax+10h], rdx
0x180055623  push    rbp
0x180055624  push    rsi
0x180055625  push    rdi
0x180055626  push    r12
0x180055628  push    r13
0x18005562a  push    r14
0x18005562c  push    r15
0x18005562e  lea     rbp, [rax-4Fh]
0x180055632  sub     rsp, 0E0h
0x180055639  mov     rbx, r8
0x18005563c  mov     rax, rdx
0x18005563f  mov     rdi, rcx
0x180055642  mov     [rbp+47h+arg_0], 0
0x180055649  xor     r14d, r14d
0x18005564c  mov     [rsp+110h+var_D0], r14
0x180055651  xor     r15d, r15d
0x180055654  mov     [rsp+110h+var_C8], r15
0x180055659  xorps   xmm0, xmm0
0x18005565c  movdqu  xmmword ptr [rbp+47h+var_A0], xmm0
0x180055661  mov     [rbp+47h+hObject], r14
0x180055665  mov     [rbp+47h+var_C0], r14d
0x180055669  mov     [rbp+47h+lpMem], r14
0x18005566d  mov     [rcx+18h], r9d
0x180055671  cmp     [rcx+1Ch], r14d
0x180055675  jz      short loc_1800556C9
0x180055677  mov     [rbp+47h+arg_0], 8064000Fh
0x18005567e  lea     rsi, WPP_RECORDER_INITIALIZED
0x180055685  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18005568c  jz      loc_18005588D
0x180055692  lea     r9d, [r14+0Dh]; int
0x180055696  mov     dword ptr [rsp+110h+var_D8], 8064000Fh; char
0x18005569e  mov     qword ptr [rsp+110h+dwOptions], rdi; char
0x1800556a3  mov     qword ptr [rsp+110h+bInheritHandle], rax; __int64
0x1800556a8  lea     r14, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x1800556af  mov     qword ptr [rsp+110h+dwDesiredAccess], r14; MessageGuid
0x1800556b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800556bb  mov     rcx, [rcx+28h]; int
0x1800556bf  call    WPP_RECORDER_SF_SqD
0x1800556c4  jmp     loc_180055834
0x1800556c9  lea     rdx, [rcx+8]
0x1800556cd  mov     rcx, rax
0x1800556d0  call    DafStringCopy
0x1800556d5  mov     [rbp+47h+arg_0], eax
0x1800556d8  test    eax, eax
0x1800556da  jns     short loc_180055700
0x1800556dc  lea     rsi, WPP_RECORDER_INITIALIZED
0x1800556e3  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1800556ea  jz      loc_180055839
0x1800556f0  mov     r9d, 0Eh
0x1800556f6  mov     dword ptr [rsp+110h+var_D8], eax
0x1800556fa  mov     rax, [rbp+47h+arg_8]
0x1800556fe  jmp     short loc_18005569E
0x180055700  test    rbx, rbx
0x180055703  jz      short loc_180055745
0x180055705  lea     rdx, [rdi+10h]
0x180055709  mov     rcx, rbx
0x18005570c  call    DafStringCopy
0x180055711  mov     [rbp+47h+arg_0], eax
0x180055714  test    eax, eax
0x180055716  jns     short loc_180055745
0x180055718  lea     rsi, WPP_RECORDER_INITIALIZED
0x18005571f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180055726  jz      loc_180055839
0x18005572c  mov     r9d, 0Fh
0x180055732  mov     dword ptr [rsp+110h+var_D8], eax
0x180055736  mov     qword ptr [rsp+110h+dwOptions], rdi
0x18005573b  mov     qword ptr [rsp+110h+bInheritHandle], rbx
0x180055740  jmp     loc_1800556A8
0x180055745  lea     r8, [rbp+47h+var_A0]
0x180055749  mov     rdx, [rbp+47h+arg_8]
0x18005574d  mov     rcx, cs:?g_providerManager@@3V?$unique_ptr@VProviderManager@ProviderManagement@DAS@@U?$default_delete@VProviderManager@ProviderManagement@DAS@@@std@@@std@@A; std::unique_ptr<DAS::ProviderManagement::ProviderManager> g_providerManager
0x180055754  call    ?GetProviderFromAepId@ProviderManager@ProviderManagement@DAS@@QEAAJPEBGAEAV?$shared_ptr@VProviderContext@@@std@@@Z; DAS::ProviderManagement::ProviderManager::GetProviderFromAepId(ushort const *,std::shared_ptr<ProviderContext> &)
0x180055759  mov     [rbp+47h+arg_0], eax
0x18005575c  test    eax, eax
0x18005575e  jz      short loc_18005577F
0x180055760  lea     rsi, WPP_RECORDER_INITIALIZED
0x180055767  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18005576e  jz      loc_180055839
0x180055774  mov     r9d, 10h
0x18005577a  jmp     loc_1800556F6
0x18005577f  lea     rsi, WPP_RECORDER_INITIALIZED
0x180055786  lea     r14, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x18005578d  mov     r15, [rbp+47h+var_A0]
0x180055791  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180055798  jz      short loc_1800557CB
0x18005579a  mov     r9d, 11h; int
0x1800557a0  mov     qword ptr [rsp+110h+var_D8], rdi; char
0x1800557a5  mov     rax, [rbp+47h+arg_8]
0x1800557a9  mov     qword ptr [rsp+110h+dwOptions], rax; __int64
0x1800557ae  mov     rax, [r15]
0x1800557b1  mov     qword ptr [rsp+110h+bInheritHandle], rax; __int64
0x1800557b6  mov     qword ptr [rsp+110h+dwDesiredAccess], r14; MessageGuid
0x1800557bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800557c2  mov     rcx, [rcx+28h]; int
0x1800557c6  call    WPP_RECORDER_SF_SSq
0x1800557cb  mov     eax, [r15+38h]
0x1800557cf  shr     eax, 0Bh
0x1800557d2  and     eax, 1
0x1800557d5  mov     [rdi+188h], eax
0x1800557db  cmp     dword ptr [r15+48h], 0
0x1800557e0  jz      short loc_1800557EE
0x1800557e2  lea     rcx, [rbp+47h+hObject]; TokenHandle
0x1800557e6  call    ?GetRpcClientToken@@YAJPEAPEAX@Z; GetRpcClientToken(void * *)
0x1800557eb  mov     [rbp+47h+arg_0], eax
0x1800557ee  mov     eax, [rbp+47h+arg_0]
0x1800557f1  test    eax, eax
0x1800557f3  jns     loc_1800558C2
0x1800557f9  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180055800  jz      short loc_18005582F
0x180055802  mov     r9d, 12h; int
0x180055808  mov     dword ptr [rsp+110h+var_D8], eax; char
0x18005580c  mov     qword ptr [rsp+110h+dwOptions], rdi; char
0x180055811  mov     rax, [rbp+47h+arg_8]
0x180055815  mov     qword ptr [rsp+110h+bInheritHandle], rax; __int64
0x18005581a  mov     qword ptr [rsp+110h+dwDesiredAccess], r14; MessageGuid
0x18005581f  mov     rcx, cs:WPP_GLOBAL_Control
0x180055826  mov     rcx, [rcx+28h]; int
0x18005582a  call    WPP_RECORDER_SF_SqD
0x18005582f  mov     r15, [rsp+110h+var_C8]
0x180055834  mov     r14, [rsp+110h+var_D0]
0x180055839  mov     rcx, [rbp+47h+hObject]; hObject
0x18005583d  test    rcx, rcx
0x180055840  jz      short loc_180055850
0x180055842  call    cs:__imp_CloseHandle
0x180055848  mov     [rbp+47h+hObject], 0
0x180055850  test    r14, r14
0x180055853  jz      short loc_18005585D
0x180055855  mov     rcx, r14; this
0x180055858  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18005585d  test    r15, r15
0x180055860  jz      short loc_18005586A
0x180055862  mov     rcx, r15; this
0x180055865  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18005586a  mov     rbx, [rbp+47h+lpMem]
0x18005586e  test    rbx, rbx
0x180055871  jz      short loc_180055887
0x180055873  call    cs:__imp_GetProcessHeap
0x180055879  mov     r8, rbx; lpMem
0x18005587c  xor     edx, edx; dwFlags
0x18005587e  mov     rcx, rax; hHeap
0x180055881  call    cs:__imp_HeapFree
0x180055887  cmp     [rbp+47h+arg_0], 0
0x18005588b  jge     short loc_180055894
0x18005588d  mov     dword ptr [rdi+1Ch], 0FFFFFFFFh
0x180055894  mov     ebx, [rbp+47h+arg_0]
0x180055897  mov     rcx, [rbp+47h+var_A0+8]; this
0x18005589b  test    rcx, rcx
0x18005589e  jz      short loc_1800558A5
0x1800558a0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800558a5  mov     eax, ebx
0x1800558a7  mov     rbx, [rsp+110h+arg_10]
0x1800558af  add     rsp, 0E0h
0x1800558b6  pop     r15
0x1800558b8  pop     r14
0x1800558ba  pop     r13
0x1800558bc  pop     r12
0x1800558be  pop     rdi
0x1800558bf  pop     rsi
0x1800558c0  pop     rbp
0x1800558c1  retn
0x1800558c2  mov     rdx, [rbp+47h+hObject]; void *
0x1800558c6  mov     rcx, rdi; this
0x1800558c9  call    ?IsAssociated@CAssociationContext@@IEAAJPEAX@Z; CAssociationContext::IsAssociated(void *)
0x1800558ce  mov     [rbp+47h+arg_0], eax
0x1800558d1  test    eax, eax
0x1800558d3  jz      short loc_1800558ED
0x1800558d5  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1800558dc  jz      loc_18005582F
0x1800558e2  mov     r9d, 13h
0x1800558e8  jmp     loc_180055808
0x1800558ed  lea     rax, [rbp+47h+lpMem]
0x1800558f1  mov     qword ptr [rsp+110h+dwDesiredAccess], rax; struct _DAF_ASSOCIATION_PARAMETER **
0x1800558f6  lea     r9, [rbp+47h+var_C0]; unsigned int *
0x1800558fa  mov     r8, [rbp+47h+arg_28]; struct _DAF_ASSOCIATION_PARAMETER *
0x1800558fe  mov     edx, [rbp+47h+arg_20]; unsigned int
0x180055901  mov     rcx, rbx; unsigned __int16 *
0x180055904  call    ?SanitizeExtendedParamters@CAssociationContext@@SAJPEBGKPEBU_DAF_ASSOCIATION_PARAMETER@@PEAKPEAPEAU2@@Z; CAssociationContext::SanitizeExtendedParamters(ushort const *,ulong,_DAF_ASSOCIATION_PARAMETER const *,ulong *,_DAF_ASSOCIATION_PARAMETER * *)
0x180055909  mov     [rbp+47h+arg_0], eax
0x18005590c  test    eax, eax
0x18005590e  js      loc_18005582F
0x180055914  lea     rdx, [rbp+47h+var_A0]
0x180055918  lea     rcx, [rbp+47h+var_90]
0x18005591c  call    ??0?$shared_ptr@VProviderContext@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ProviderContext>::shared_ptr<ProviderContext>(std::shared_ptr<ProviderContext> const &)
0x180055921  mov     rdx, rax
0x180055924  mov     r9, [rbp+47h+arg_28]
0x180055928  mov     r8d, [rbp+47h+arg_20]
0x18005592c  mov     rcx, rdi; pv
0x18005592f  call    ?InitSetAssociation@CAssociationContext@@IEAAJV?$shared_ptr@VProviderContext@@@std@@KPEBU_DAF_ASSOCIATION_PARAMETER@@@Z; CAssociationContext::InitSetAssociation(std::shared_ptr<ProviderContext>,ulong,_DAF_ASSOCIATION_PARAMETER const *)
0x180055934  mov     [rbp+47h+arg_0], eax
0x180055937  test    eax, eax
0x180055939  js      loc_18005582F
0x18005593f  mov     ecx, [r15+30h]
0x180055943  xor     eax, eax
0x180055945  test    ecx, ecx
0x180055947  setnz   al
0x18005594a  mov     [rdi+20h], eax
0x18005594d  mov     [rbp+47h+TargetHandle], 0
0x180055955  test    ecx, ecx
0x180055957  jz      loc_180055B61
0x18005595d  mov     [rbp+47h+var_90], 0
0x180055965  lea     r13, [rdi+258h]
0x18005596c  lea     rdx, [rbp+47h+var_A0]
0x180055970  lea     rcx, [rbp+47h+var_40]
0x180055974  call    ??0?$shared_ptr@VProviderContext@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ProviderContext>::shared_ptr<ProviderContext>(std::shared_ptr<ProviderContext> const &)
0x180055979  mov     rcx, rax
0x18005597c  mov     rdx, r13
0x18005597f  call    ?GetHostContext@CHostContext@@SAJV?$shared_ptr@VProviderContext@@@std@@PEAPEAV1@@Z; CHostContext::GetHostContext(std::shared_ptr<ProviderContext>,CHostContext * *)
0x180055984  mov     [rbp+47h+arg_0], eax
0x180055987  test    eax, eax
0x180055989  jz      short loc_1800559A3
0x18005598b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180055992  jz      loc_18005582F
0x180055998  mov     r9d, 14h
0x18005599e  jmp     loc_180055808
0x1800559a3  xor     r9d, r9d; lpName
0x1800559a6  xor     r8d, r8d; bInitialState
0x1800559a9  lea     edx, [r9+1]; bManualReset
0x1800559ad  xor     ecx, ecx; lpEventAttributes
0x1800559af  call    cs:__imp_CreateEventW
0x1800559b5  mov     r12, rax
0x1800559b8  mov     [rdi+38h], rax
0x1800559bc  test    rax, rax
0x1800559bf  jnz     short loc_1800559DB
0x1800559c1  call    cs:__imp_GetLastError
0x1800559c7  test    eax, eax
0x1800559c9  jle     short loc_1800559D3
0x1800559cb  movzx   eax, ax
0x1800559ce  or      eax, 80070000h
0x1800559d3  mov     [rbp+47h+arg_0], eax
0x1800559d6  jmp     loc_18005582F
0x1800559db  mov     rax, [r13+0]
0x1800559df  mov     rbx, [rax+8]
0x1800559e3  call    cs:__imp_GetCurrentProcess
0x1800559e9  mov     [rsp+110h+dwOptions], 2; dwOptions
0x1800559f1  mov     [rsp+110h+bInheritHandle], 0; bInheritHandle
0x1800559f9  mov     [rsp+110h+dwDesiredAccess], 0; dwDesiredAccess
0x180055a01  lea     r9, [rbp+47h+TargetHandle]; lpTargetHandle
0x180055a05  mov     r8, rbx; hTargetProcessHandle
0x180055a08  mov     rdx, r12; hSourceHandle
0x180055a0b  mov     rcx, rax; hSourceProcessHandle
0x180055a0e  call    cs:__imp_DuplicateHandle
0x180055a14  test    eax, eax
0x180055a16  jnz     short loc_180055A45
0x180055a18  call    cs:__imp_GetLastError
0x180055a1e  test    eax, eax
0x180055a20  jle     short loc_180055A2A
0x180055a22  movzx   eax, ax
0x180055a25  or      eax, 80070000h
0x180055a2a  mov     [rbp+47h+arg_0], eax
0x180055a2d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180055a34  jz      loc_18005582F
0x180055a3a  mov     r9d, 15h
0x180055a40  jmp     loc_180055808
0x180055a45  cmp     dword ptr [r15+48h], 0
0x180055a4a  jz      short loc_180055AC6
0x180055a4c  cmp     dword ptr [r15+54h], 0
0x180055a51  jz      short loc_180055AC6
0x180055a53  mov     r15, [rbp+47h+hObject]
0x180055a57  test    r15, r15
0x180055a5a  jz      short loc_180055AC6
0x180055a5c  mov     rax, [r13+0]
0x180055a60  mov     rbx, [rax+8]
0x180055a64  call    cs:__imp_GetCurrentProcess
0x180055a6a  mov     [rsp+110h+dwOptions], 2; dwOptions
0x180055a72  mov     [rsp+110h+bInheritHandle], 0; bInheritHandle
0x180055a7a  mov     [rsp+110h+dwDesiredAccess], 0; dwDesiredAccess
0x180055a82  lea     r9, [rbp+47h+var_90]; lpTargetHandle
0x180055a86  mov     r8, rbx; hTargetProcessHandle
0x180055a89  mov     rdx, r15; hSourceHandle
0x180055a8c  mov     rcx, rax; hSourceProcessHandle
0x180055a8f  call    cs:__imp_DuplicateHandle
0x180055a95  test    eax, eax
0x180055a97  jnz     short loc_180055AC6
0x180055a99  call    cs:__imp_GetLastError
0x180055a9f  test    eax, eax
0x180055aa1  jle     short loc_180055AAB
0x180055aa3  movzx   eax, ax
0x180055aa6  or      eax, 80070000h
0x180055aab  mov     [rbp+47h+arg_0], eax
0x180055aae  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180055ab5  jz      loc_18005582F
0x180055abb  mov     r9d, 16h
0x180055ac1  jmp     loc_180055808
0x180055ac6  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 10h
0x180055acd  jz      short loc_180055ADE
0x180055acf  mov     r8, rdi
0x180055ad2  lea     rdx, CREATE_ASSOC_CTX_PROVIDER_START
0x180055ad9  call    McTemplateU0p_EventWriteTransfer
0x180055ade  lea     rax, [rbp+47h+arg_0]
0x180055ae2  mov     [rbp+47h+var_80], rax
0x180055ae6  mov     [rbp+47h+var_78], rdi
0x180055aea  lea     rax, [rbp+47h+arg_8]
0x180055aee  mov     [rbp+47h+var_70], rax
0x180055af2  lea     rax, [rbp+47h+arg_18]
0x180055af6  mov     [rbp+47h+var_68], rax
0x180055afa  lea     rax, [rbp+47h+TargetHandle]
  ... truncated ...
```
