# HcsClient::OperationTracker::CompleteOperationSynchronously(std::shared_ptr<ClientOperation> const &,long,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ProcessInformation *)

- ea: `0x180049b6c`
- end: `0x180049f1c`
- name: `?CompleteOperationSynchronously@OperationTracker@HcsClient@@QEAAXAEBV?$shared_ptr@VClientOperation@@@std@@JV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUProcessInformation@@@Z`
- size: `944`
- prototype: ``
- caller_count: `20`
- callee_count: `22`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180016e50`
- `0x18002c594`
- `0x18002c93c`
- `0x18002cb38`
- `0x18002d304`
- `0x180036164`
- `0x1800363cc`
- `0x180036c50`
- `0x180036eac`
- `0x18003727c`
- `0x1800374d8`
- `0x180037c7c`
- `0x180037ed4`
- `0x18003812c`
- `0x180038384`
- `0x1800385ec`
- `0x180038824`
- `0x180038a80`
- `0x180038cdc`
- `0x180038f60`

## callees

- `0x1800067c0`
- `0x180006c3c`
- `0x180006d0c`
- `0x180007438`
- `0x18001fea4`
- `0x180020494`
- `0x1800216cc`
- `0x180026224`
- `0x18002a03c`
- `0x18002a0b4`
- `0x18002a610`
- `0x18002a700`
- `0x18004771c`
- `0x180047cb8`
- `0x180048344`
- `0x180048b10`
- `0x1800498b4`
- `0x180049940`
- `0x1800499cc`
- `0x180049b6c`
- `0x18004b00c`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049eb3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049eb3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049e8e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049e8e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180049ea5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180049ea5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049ef3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049ef3`

## string_xrefs

- `0x180049beb`: `ClientLib_SyncOperationCompletion`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
HLOCAL __fastcall HcsClient::OperationTracker::CompleteOperationSynchronously(
        __int64 a1,
        PSRWLOCK *a2,
        int a3,
        HLOCAL *a4,
        int *a5)
{
  _QWORD *v9; // rax
  PSRWLOCK v10; // r8
  __int64 v11; // rsi
  volatile signed __int32 *v12; // rbx
  RTL_SRWLOCK *v13; // rcx
  PSRWLOCK v14; // rcx
  void (*v15)(void *); // r8
  void (*v16)(void *, void *); // r9
  int v17; // ebx
  int v18; // ecx
  _BYTE *v19; // rdx
  char v20; // al
  __int64 v21; // rbx
  HLOCAL result; // rax
  PVOID Ptr; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL *v25; // [rsp+40h] [rbp-C0h] BYREF
  volatile signed __int32 *v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+5Ch] [rbp-A4h]
  HLOCAL v30; // [rsp+60h] [rbp-A0h]
  __int128 v31; // [rsp+68h] [rbp-98h]
  PVOID v32; // [rsp+78h] [rbp-88h]
  int v33; // [rsp+80h] [rbp-80h]
  _BYTE v34[24]; // [rsp+88h] [rbp-78h] BYREF
  char v35; // [rsp+A0h] [rbp-60h]
  int v36; // [rsp+A8h] [rbp-58h]
  _BYTE v37[24]; // [rsp+B0h] [rbp-50h] BYREF
  char v38; // [rsp+C8h] [rbp-38h]
  int v39; // [rsp+D0h] [rbp-30h]
  _BYTE v40[24]; // [rsp+D8h] [rbp-28h] BYREF
  char v41; // [rsp+F0h] [rbp-10h]
  HLOCAL v42; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v43[16]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v44[42]; // [rsp+110h] [rbp+10h] BYREF

  LODWORD(v42) = a3;
  v25 = a4;
  LODWORD(Ptr) = 0;
  memset_0(v44, 0, sizeof(v44));
  Ptr = (*a2)[10].Ptr;
  v9 = (_QWORD *)(a1 + 112);
  if ( *(_QWORD *)(a1 + 136) > 7u )
    v9 = (_QWORD *)*v9;
  v24 = v9;
  wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v44,
    "ClientLib_SyncOperationCompletion");
  v44[0] = &ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::`vftable';
  ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::StartActivity<unsigned short const *,unsigned __int64,long &>(
    v44,
    &v24,
    &Ptr,
    &v42);
  CallbackManager::Enter(*(PSRWLOCK *)(a1 + 104));
  if ( v43[8] )
  {
    if ( ClientOperation::HasCompletionCallback(*a2)
      || *(_QWORD *)(a1 + 16) && (*(_BYTE *)(a1 + 32) & 1) != 0
      || (v10 = *a2) != 0 && (HIDWORD(v10[12].Ptr) == 1 || HIDWORD(v10[12].Ptr) == 10) )
    {
      ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::ClientLib_SyncOperationCompletion_Queue((ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion *)v44);
      v27 = 0;
      v28 = a3;
      v29 = 0;
      v30 = *a4;
      *a4 = 0;
      v31 = 0;
      v14 = a2[1];
      if ( v14 )
      {
        *(_QWORD *)&v31 = *a2;
        *((_QWORD *)&v31 + 1) = v14;
        _InterlockedIncrement((volatile signed __int32 *)&v14[1].Ptr + 1);
      }
      v32 = (*a2)[10].Ptr;
      v15 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>;
      v16 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>;
      if ( a5 )
      {
        v36 = *a5;
        `eh vector copy constructor iterator'(
          v37,
          a5 + 2,
          8u,
          3u,
          wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,
          wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
        v38 = 1;
        v17 = 1;
        v18 = v36;
        v19 = v37;
        v20 = 1;
        v15 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>;
        v16 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>;
      }
      else
      {
        v41 = 0;
        v17 = 2;
        v18 = v39;
        v19 = v40;
        v20 = 0;
      }
      LODWORD(Ptr) = v17;
      v35 = 0;
      if ( v20 )
      {
        v33 = v18;
        `eh vector copy constructor iterator'(
          v34,
          v19,
          8u,
          3u,
          wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,
          wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
        v35 = 1;
      }
      if ( *(_QWORD *)(a1 + 80) == *(_QWORD *)(a1 + 88) )
      {
        std::vector<HcsClient::OperationTracker::WorkItem>::_Emplace_reallocate<HcsClient::OperationTracker::WorkItem>(
          a1 + 72,
          *(_QWORD *)(a1 + 80),
          &v27,
          v16);
      }
      else
      {
        HcsClient::OperationTracker::WorkItem::WorkItem(*(_QWORD *)(a1 + 80), &v27, v15, v16);
        *(_QWORD *)(a1 + 80) += 88LL;
      }
      HcsClient::OperationTracker::WorkItem::~WorkItem((HcsClient::OperationTracker::WorkItem *)&v27);
      if ( (v17 & 2) != 0 )
      {
        v17 &= ~2u;
        LODWORD(Ptr) = v17;
        if ( v41 )
          `eh vector destructor iterator'(
            v40,
            8u,
            3u,
            wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
      }
      if ( (v17 & 1) != 0 && v38 )
        `eh vector destructor iterator'(
          v37,
          8u,
          3u,
          wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
      v21 = *(_QWORD *)(a1 + 104);
      AcquireSRWLockExclusive((PSRWLOCK)(v21 + 40));
      if ( !*(_DWORD *)(v21 + 56) )
      {
        *(_DWORD *)(v21 + 56) = 1;
        SubmitThreadpoolWork(*(PTP_WORK *)(v21 + 32));
      }
      if ( v21 != -40 )
        ReleaseSRWLockExclusive((PSRWLOCK)(v21 + 40));
    }
    else
    {
      v11 = *(_QWORD *)HcsClient::OperationTracker::RemoveOperationById(a1, &v25, v10[10].Ptr);
      v12 = v26;
      if ( v26 )
      {
        if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
      if ( v11 )
      {
        ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::ClientLib_SyncOperationCompletion_Complete((ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion *)v44);
        v13 = *a2;
        v42 = *a4;
        *a4 = 0;
        ClientOperation::Complete(v13);
      }
      else
      {
        ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::ClientLib_SyncOperationCompletion_Drop((ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion *)v44);
      }
    }
  }
  wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v44);
  std::_Optional_destruct_base<CallbackReference,0>::~_Optional_destruct_base<CallbackReference,0>(v43);
  v44[0] = &ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::`vftable';
  wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v44);
  result = (HLOCAL)wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>(v44);
  if ( *a4 )
    return LocalFree(*a4);
  return result;
}

```

## disassembly

```asm
0x180049b6c  push    rbp
0x180049b6e  push    rbx
0x180049b6f  push    rsi
0x180049b70  push    rdi
0x180049b71  push    r12
0x180049b73  push    r13
0x180049b75  push    r14
0x180049b77  push    r15
0x180049b79  lea     rbp, [rsp-178h]
0x180049b81  sub     rsp, 278h
0x180049b88  mov     rax, cs:__security_cookie
0x180049b8f  xor     rax, rsp
0x180049b92  mov     [rbp+1B0h+var_50], rax
0x180049b99  mov     r15, r9
0x180049b9c  mov     r13d, r8d
0x180049b9f  mov     rdi, rdx
0x180049ba2  mov     r14, rcx
0x180049ba5  mov     r12, [rbp+1B0h+arg_20]
0x180049bac  mov     dword ptr [rbp+1B0h+var_1B8], r8d
0x180049bb0  mov     [rsp+2B0h+var_270], r9
0x180049bb5  xor     ebx, ebx
0x180049bb7  mov     dword ptr [rsp+2B0h+var_280], ebx
0x180049bbb  xor     edx, edx; Val
0x180049bbd  mov     r8d, 150h; Size
0x180049bc3  lea     rcx, [rbp+1B0h+var_1A0]; void *
0x180049bc7  call    memset_0
0x180049bcc  mov     rax, [rdi]
0x180049bcf  mov     rcx, [rax+50h]
0x180049bd3  mov     [rsp+2B0h+var_280], rcx
0x180049bd8  lea     rax, [r14+70h]
0x180049bdc  cmp     qword ptr [rax+18h], 7
0x180049be1  jbe     short loc_180049BE6
0x180049be3  mov     rax, [rax]
0x180049be6  mov     [rsp+2B0h+var_278], rax
0x180049beb  lea     rdx, aClientlibSynco; "ClientLib_SyncOperationCompletion"
0x180049bf2  lea     rcx, [rbp+1B0h+var_1A0]
0x180049bf6  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeLib@@$0A@$0BAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180049bfb  lea     rax, ??_7ClientLib_SyncOperationCompletion@TraceProvider@Diagnostics@ComputeLib@@6B@; const ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::`vftable'
0x180049c02  mov     [rbp+1B0h+var_1A0], rax
0x180049c06  lea     r9, [rbp+1B0h+var_1B8]
0x180049c0a  lea     r8, [rsp+2B0h+var_280]
0x180049c0f  lea     rdx, [rsp+2B0h+var_278]
0x180049c14  lea     rcx, [rbp+1B0h+var_1A0]
0x180049c18  call    ??$StartActivity@PEBG_KAEAJ@ClientLib_SyncOperationCompletion@TraceProvider@Diagnostics@ComputeLib@@QEAAX$$QEAPEBG$$QEA_KAEAJ@Z; ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::StartActivity<ushort const *,unsigned __int64,long &>(ushort const * &&,unsigned __int64 &&,long &)
0x180049c1d  nop
0x180049c1e  lea     rdx, [rbp+1B0h+var_1B0]
0x180049c22  mov     rcx, [r14+68h]; SRWLock
0x180049c26  call    ?Enter@CallbackManager@@QEAA?AV?$optional@VCallbackReference@@@std@@XZ; CallbackManager::Enter(void)
0x180049c2b  nop
0x180049c2c  cmp     [rbp+1B0h+var_1A8], bl
0x180049c2f  jz      loc_180049EB9
0x180049c35  mov     rcx, [rdi]; SRWLock
0x180049c38  call    ?HasCompletionCallback@ClientOperation@@QEAA_NXZ; ClientOperation::HasCompletionCallback(void)
0x180049c3d  test    al, al
0x180049c3f  jnz     loc_180049D0A
0x180049c45  cmp     [r14+10h], rbx
0x180049c49  jz      short loc_180049C56
0x180049c4b  test    byte ptr [r14+20h], 1
0x180049c50  jnz     loc_180049D0A
0x180049c56  mov     r8, [rdi]
0x180049c59  test    r8, r8
0x180049c5c  jz      short loc_180049C74
0x180049c5e  cmp     dword ptr [r8+64h], 1
0x180049c63  jz      loc_180049D0A
0x180049c69  cmp     dword ptr [r8+64h], 0Ah
0x180049c6e  jz      loc_180049D0A
0x180049c74  mov     r8, [r8+50h]
0x180049c78  lea     rdx, [rsp+2B0h+var_270]
0x180049c7d  mov     rcx, r14
0x180049c80  call    ?RemoveOperationById@OperationTracker@HcsClient@@QEAA?AV?$shared_ptr@VClientOperation@@@std@@_K@Z; HcsClient::OperationTracker::RemoveOperationById(unsigned __int64)
0x180049c85  mov     rsi, [rax]
0x180049c88  mov     rbx, [rsp+2B0h+var_268]
0x180049c8d  test    rbx, rbx
0x180049c90  jz      short loc_180049CCD
0x180049c92  or      r14d, 0FFFFFFFFh
0x180049c96  mov     eax, r14d
0x180049c99  lock xadd [rbx+8], eax
0x180049c9e  add     eax, r14d
0x180049ca1  jnz     short loc_180049CCD
0x180049ca3  mov     rax, [rbx]
0x180049ca6  mov     rcx, rbx
0x180049ca9  mov     rax, [rax]
0x180049cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049cb1  mov     eax, r14d
0x180049cb4  lock xadd [rbx+0Ch], eax
0x180049cb9  add     eax, r14d
0x180049cbc  jnz     short loc_180049CCD
0x180049cbe  mov     rax, [rbx]
0x180049cc1  mov     rcx, rbx
0x180049cc4  mov     rax, [rax+8]
0x180049cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ccd  lea     rcx, [rbp+1B0h+var_1A0]; this
0x180049cd1  test    rsi, rsi
0x180049cd4  jz      short loc_180049D00
0x180049cd6  call    ?ClientLib_SyncOperationCompletion_Complete@ClientLib_SyncOperationCompletion@TraceProvider@Diagnostics@ComputeLib@@QEAAXXZ; ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::ClientLib_SyncOperationCompletion_Complete(void)
0x180049cdb  mov     rcx, [rdi]; SRWLock
0x180049cde  mov     rax, [r15]
0x180049ce1  mov     [rbp+1B0h+var_1B8], rax
0x180049ce5  mov     qword ptr [r15], 0
0x180049cec  mov     r9, r12
0x180049cef  lea     r8, [rbp+1B0h+var_1B8]
0x180049cf3  mov     edx, r13d
0x180049cf6  call    ?Complete@ClientOperation@@QEAA_NJV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUProcessInformation@@@Z; ClientOperation::Complete(long,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ProcessInformation *)
0x180049cfb  jmp     loc_180049EB9
0x180049d00  call    ?ClientLib_SyncOperationCompletion_Drop@ClientLib_SyncOperationCompletion@TraceProvider@Diagnostics@ComputeLib@@QEAAXXZ; ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::ClientLib_SyncOperationCompletion_Drop(void)
0x180049d05  jmp     loc_180049EB9
0x180049d0a  lea     rcx, [rbp+1B0h+var_1A0]; this
0x180049d0e  call    ?ClientLib_SyncOperationCompletion_Queue@ClientLib_SyncOperationCompletion@TraceProvider@Diagnostics@ComputeLib@@QEAAXXZ; ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::ClientLib_SyncOperationCompletion_Queue(void)
0x180049d13  mov     [rsp+2B0h+var_260], rbx
0x180049d18  mov     [rsp+2B0h+var_258], r13d
0x180049d1d  xor     eax, eax
0x180049d1f  mov     [rsp+2B0h+var_254], eax
0x180049d23  mov     rax, [r15]
0x180049d26  mov     [rsp+2B0h+var_250], rax
0x180049d2b  mov     [r15], rbx
0x180049d2e  xorps   xmm0, xmm0
0x180049d31  movdqu  [rsp+2B0h+var_248], xmm0
0x180049d37  mov     rcx, [rdi+8]
0x180049d3b  test    rcx, rcx
0x180049d3e  jz      short loc_180049D51
0x180049d40  mov     rax, [rdi]
0x180049d43  mov     qword ptr [rsp+2B0h+var_248], rax
0x180049d48  mov     qword ptr [rsp+2B0h+var_248+8], rcx
0x180049d4d  lock inc dword ptr [rcx+0Ch]
0x180049d51  mov     rax, [rdi]
0x180049d54  mov     rcx, [rax+50h]
0x180049d58  mov     [rsp+2B0h+var_238], rcx
0x180049d5d  lea     r8, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x180049d64  lea     r9, ??0?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180049d6b  mov     edi, 3
0x180049d70  lea     r13d, [rdi+5]
0x180049d74  test    r12, r12
0x180049d77  jz      short loc_180049DBF
0x180049d79  mov     eax, [r12]
0x180049d7d  mov     [rbp+1B0h+var_208], eax
0x180049d80  lea     rdx, [r12+8]; void *
0x180049d85  mov     [rsp+2B0h+var_288], r8; void (*)(void *)
0x180049d8a  mov     [rsp+2B0h+var_290], r9; void (*)(void *, void *)
0x180049d8f  mov     r9d, edi; unsigned __int64
0x180049d92  mov     r8d, r13d; unsigned __int64
0x180049d95  lea     rcx, [rbp+1B0h+var_200]; void *
0x180049d99  call    ??__C@YAXPEAX0_K1P6AX00@ZP6AX0@Z@Z; `eh vector copy constructor iterator'(void *,void *,unsigned __int64,unsigned __int64,void (*)(void *,void *),void (*)(void *))
0x180049d9e  nop
0x180049d9f  mov     [rbp+1B0h+var_1E8], 1
0x180049da3  lea     ebx, [rdi-2]
0x180049da6  mov     ecx, [rbp+1B0h+var_208]
0x180049da9  lea     rdx, [rbp+1B0h+var_200]
0x180049dad  mov     al, bl
0x180049daf  lea     r8, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x180049db6  lea     r9, ??0?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180049dbd  jmp     short loc_180049DD0
0x180049dbf  mov     [rbp+1B0h+var_1C0], bl
0x180049dc2  mov     ebx, 2
0x180049dc7  mov     ecx, [rbp+1B0h+var_1E0]
0x180049dca  lea     rdx, [rbp+1B0h+var_1D8]; void *
0x180049dce  xor     al, al
0x180049dd0  mov     dword ptr [rsp+2B0h+var_280], ebx
0x180049dd4  mov     [rbp+1B0h+var_210], 0
0x180049dd8  test    al, al
0x180049dda  jz      short loc_180049DFD
0x180049ddc  mov     [rbp+1B0h+var_230], ecx
0x180049ddf  mov     [rsp+2B0h+var_288], r8; void (*)(void *)
0x180049de4  mov     [rsp+2B0h+var_290], r9; void (*)(void *, void *)
0x180049de9  mov     r9, rdi; unsigned __int64
0x180049dec  mov     r8, r13; unsigned __int64
0x180049def  lea     rcx, [rbp+1B0h+var_228]; void *
0x180049df3  call    ??__C@YAXPEAX0_K1P6AX00@ZP6AX0@Z@Z; `eh vector copy constructor iterator'(void *,void *,unsigned __int64,unsigned __int64,void (*)(void *,void *),void (*)(void *))
0x180049df8  nop
0x180049df9  mov     [rbp+1B0h+var_210], 1
0x180049dfd  mov     rax, [r14+50h]
0x180049e01  cmp     rax, [r14+58h]
0x180049e05  jz      short loc_180049E1B
0x180049e07  lea     rdx, [rsp+2B0h+var_260]
0x180049e0c  mov     rcx, rax
0x180049e0f  call    ??0WorkItem@OperationTracker@HcsClient@@QEAA@$$QEAU012@@Z; HcsClient::OperationTracker::WorkItem::WorkItem(HcsClient::OperationTracker::WorkItem &&)
0x180049e14  add     qword ptr [r14+50h], 58h ; 'X'
0x180049e19  jmp     short loc_180049E2D
0x180049e1b  lea     r8, [rsp+2B0h+var_260]
0x180049e20  mov     rdx, rax
0x180049e23  lea     rcx, [r14+48h]
0x180049e27  call    ??$_Emplace_reallocate@UWorkItem@OperationTracker@HcsClient@@@?$vector@UWorkItem@OperationTracker@HcsClient@@V?$allocator@UWorkItem@OperationTracker@HcsClient@@@std@@@std@@AEAAPEAUWorkItem@OperationTracker@HcsClient@@QEAU234@$$QEAU234@@Z; std::vector<HcsClient::OperationTracker::WorkItem>::_Emplace_reallocate<HcsClient::OperationTracker::WorkItem>(HcsClient::OperationTracker::WorkItem * const,HcsClient::OperationTracker::WorkItem &&)
0x180049e2c  nop
0x180049e2d  lea     rcx, [rsp+2B0h+var_260]; this
0x180049e32  call    ??1WorkItem@OperationTracker@HcsClient@@QEAA@XZ; HcsClient::OperationTracker::WorkItem::~WorkItem(void)
0x180049e37  nop
0x180049e38  test    bl, 2
0x180049e3b  jz      short loc_180049E61
0x180049e3d  and     ebx, 0FFFFFFFDh
0x180049e40  mov     dword ptr [rsp+2B0h+var_280], ebx
0x180049e44  cmp     [rbp+1B0h+var_1C0], 0
0x180049e48  jz      short loc_180049E61
0x180049e4a  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x180049e51  mov     r8, rdi; unsigned __int64
0x180049e54  mov     rdx, r13; unsigned __int64
0x180049e57  lea     rcx, [rbp+1B0h+var_1D8]; void *
0x180049e5b  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180049e60  nop
0x180049e61  test    bl, 1
0x180049e64  jz      short loc_180049E83
0x180049e66  cmp     [rbp+1B0h+var_1E8], 0
0x180049e6a  jz      short loc_180049E83
0x180049e6c  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x180049e73  mov     r8, rdi; unsigned __int64
0x180049e76  mov     rdx, r13; unsigned __int64
0x180049e79  lea     rcx, [rbp+1B0h+var_200]; void *
0x180049e7d  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180049e82  nop
0x180049e83  mov     rbx, [r14+68h]
0x180049e87  lea     rdi, [rbx+28h]
0x180049e8b  mov     rcx, rdi; SRWLock
0x180049e8e  call    cs:__imp_AcquireSRWLockExclusive
0x180049e94  cmp     dword ptr [rbx+38h], 0
0x180049e98  jnz     short loc_180049EAB
0x180049e9a  mov     dword ptr [rbx+38h], 1
0x180049ea1  mov     rcx, [rbx+20h]; pwk
0x180049ea5  call    cs:__imp_SubmitThreadpoolWork
0x180049eab  test    rdi, rdi
0x180049eae  jz      short loc_180049EB9
0x180049eb0  mov     rcx, rdi; SRWLock
0x180049eb3  call    cs:__imp_ReleaseSRWLockExclusive
0x180049eb9  lea     rcx, [rbp+1B0h+var_1A0]
0x180049ebd  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLib@@$0A@$0BAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180049ec2  nop
0x180049ec3  lea     rcx, [rbp+1B0h+var_1B0]
0x180049ec7  call    ??1?$_Optional_destruct_base@VCallbackReference@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<CallbackReference,0>::~_Optional_destruct_base<CallbackReference,0>(void)
0x180049ecc  nop
0x180049ecd  lea     rax, ??_7ClientLib_SyncOperationCompletion@TraceProvider@Diagnostics@ComputeLib@@6B@; const ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::`vftable'
0x180049ed4  mov     [rbp+1B0h+var_1A0], rax
0x180049ed8  lea     rcx, [rbp+1B0h+var_1A0]
0x180049edc  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLib@@$0A@$0BAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180049ee1  lea     rcx, [rbp+1B0h+var_1A0]
0x180049ee5  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeLib@@$0A@$0BAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180049eea  nop
0x180049eeb  mov     rcx, [r15]; hMem
0x180049eee  test    rcx, rcx
0x180049ef1  jz      short loc_180049EF9
0x180049ef3  call    cs:__imp_LocalFree
0x180049ef9  mov     rcx, [rbp+1B0h+var_50]
0x180049f00  xor     rcx, rsp; StackCookie
0x180049f03  call    __security_check_cookie
0x180049f08  add     rsp, 278h
0x180049f0f  pop     r15
0x180049f11  pop     r14
0x180049f13  pop     r13
0x180049f15  pop     r12
0x180049f17  pop     rdi
0x180049f18  pop     rsi
0x180049f19  pop     rbx
0x180049f1a  pop     rbp
0x180049f1b  retn
```
