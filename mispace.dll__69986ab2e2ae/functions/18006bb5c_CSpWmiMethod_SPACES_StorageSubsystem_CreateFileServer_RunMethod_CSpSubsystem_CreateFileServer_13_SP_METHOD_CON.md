# CSpWmiMethod<_SPACES_StorageSubsystem_CreateFileServer>::RunMethod<CSpSubsystem::CreateFileServer,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006bb5c`
- end: `0x18006bed9`
- name: `??$RunMethod@VCreateFileServer@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_SPACES_StorageSubsystem_CreateFileServer@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800743e0`

## callees

- `0x180001504`
- `0x180001994`
- `0x180006350`
- `0x1800063a0`
- `0x1800063ac`
- `0x18000c644`
- `0x180013b4c`
- `0x1800142e8`
- `0x180014a54`
- `0x1800257fc`
- `0x18005f41c`
- `0x18006bb5c`
- `0x18006e014`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bd3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bd3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006bd0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006bd0f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006bd2a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006bd2a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006bcef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006bcef`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006bde4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006bde4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006bea3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006bea3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006be8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006be8f`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageSubsystem_CreateFileServer>::RunMethod<CSpSubsystem::CreateFileServer,13>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 FileServer; // rax
  __int64 v8; // rdi
  unsigned int v9; // ebx
  __int64 *v10; // r15
  int v11; // r8d
  int v12; // r9d
  bool v13; // zf
  __int64 v14; // rcx
  enum _MI_Result v15; // eax
  HANDLE CurrentThread; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v21; // [rsp+40h] [rbp-40h] BYREF
  BOOL v22; // [rsp+44h] [rbp-3Ch] BYREF
  int v23; // [rsp+48h] [rbp-38h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-30h] BYREF
  CSpSubsystem::CreateFileServer *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::CreateFileServer *)operator new(0x178u);
  FileServer = CSpSubsystem::CreateFileServer::CreateFileServer(v25);
  v8 = FileServer;
  if ( FileServer )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)FileServer + 8LL))(FileServer, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpSubsystem::CreateFileServer *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_180318E20,
        v11,
        v12,
        (__int64)&v25,
        (__int64)&v23,
        (__int64)&v21,
        (__int64)&v22);
    }
    v14 = *a1;
    if ( *a1 && *(_QWORD *)v14 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v14 + 24LL))(
             v14,
             &MSFT_StorageExtendedStatus_rtti,
             v8 + 32);
      if ( v9 )
        goto LABEL_30;
      if ( *((_DWORD *)a1 + 4) )
      {
        CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(v8 + 328);
        if ( !(unsigned int)CSpJobMgr::GetInstance((struct CSpJobMgr **)(v8 + 328)) )
        {
          v9 = 28;
          goto LABEL_30;
        }
        v10 = (__int64 *)operator new(0x10u);
        *v10 = v8;
        ThreadpoolWork = CreateThreadpoolWork(
                           CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::ResumeMethodWorker,
                           v10,
                           0);
        if ( ThreadpoolWork )
        {
          CurrentThread = GetCurrentThread();
          if ( OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle) || GetLastError() == 1008 )
          {
            v10[1] = (__int64)TokenHandle;
            (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 24LL))(v8, a1[1], a2);
            v17 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
            v9 = v17;
            if ( !v17 || v17 == 7 )
            {
              v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
              if ( !v9
                && (*(_QWORD *)(v8 + 336) != *(_QWORD *)&GUID_NULL.Data1
                 || *(_QWORD *)(v8 + 344) != *(_QWORD *)GUID_NULL.Data4) )
              {
                v9 = CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(v8, a3);
                if ( !v9 )
                {
                  SubmitThreadpoolWork(ThreadpoolWork);
                  return v9;
                }
              }
            }
            goto LABEL_30;
          }
        }
        v15 = GleToMiResult();
        goto LABEL_14;
      }
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 16LL))(v8, a1[1], a2);
      v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 48LL))(v8, a3);
      v9 = v18;
      if ( !v18 || v18 == 7 )
      {
        v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
        v9 = v19;
        if ( !v19 || v19 == 7 )
        {
          v15 = (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
LABEL_14:
          v9 = v15;
        }
      }
    }
    else
    {
      v9 = 4;
    }
LABEL_30:
    (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
    if ( v10 )
      operator delete(v10);
    goto LABEL_32;
  }
  v9 = 27;
LABEL_32:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  return v9;
}

```

## disassembly

```asm
0x18006bb5c  mov     [rsp-38h+arg_18], rbx
0x18006bb61  push    rbp
0x18006bb62  push    rsi
0x18006bb63  push    rdi
0x18006bb64  push    r12
0x18006bb66  push    r13
0x18006bb68  push    r14
0x18006bb6a  push    r15
0x18006bb6c  mov     rbp, rsp
0x18006bb6f  sub     rsp, 80h
0x18006bb76  mov     rax, cs:__security_cookie
0x18006bb7d  xor     rax, rsp
0x18006bb80  mov     [rbp+var_8], rax
0x18006bb84  xor     eax, eax
0x18006bb86  mov     rsi, rcx
0x18006bb89  xorps   xmm0, xmm0
0x18006bb8c  mov     [rbp+var_10], eax
0x18006bb8f  mov     ecx, 178h; Size
0x18006bb94  mov     [rbp+var_40], eax
0x18006bb97  movups  [rbp+var_20], xmm0
0x18006bb9b  mov     [rbp+TokenHandle], rax
0x18006bb9f  mov     r12, r8
0x18006bba2  mov     r13, rdx
0x18006bba5  xor     r14d, r14d
0x18006bba8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006bbad  mov     rcx, rax; this
0x18006bbb0  mov     [rbp+var_28], rax
0x18006bbb4  call    ??0CreateFileServer@CSpSubsystem@@QEAA@XZ; CSpSubsystem::CreateFileServer::CreateFileServer(void)
0x18006bbb9  mov     rdi, rax
0x18006bbbc  test    rax, rax
0x18006bbbf  jnz     short loc_18006BBC9
0x18006bbc1  lea     ebx, [rax+1Bh]
0x18006bbc4  jmp     loc_18006BE86
0x18006bbc9  mov     rax, [rax]
0x18006bbcc  mov     rdx, rsi
0x18006bbcf  mov     rcx, rdi
0x18006bbd2  xor     r15d, r15d
0x18006bbd5  mov     rax, [rax+8]
0x18006bbd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bbde  lea     rcx, [rbp+var_40]
0x18006bbe2  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006bbe7  mov     [rdi+1Ch], eax
0x18006bbea  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006bbee  mov     ecx, [rsi+14h]; unsigned int
0x18006bbf1  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006bbf6  mov     eax, cs:dword_18039EB68
0x18006bbfc  cmp     eax, 5
0x18006bbff  jbe     short loc_18006BC6F
0x18006bc01  mov     rdx, 400000000000h
0x18006bc0b  lea     rcx, dword_18039EB68
0x18006bc12  call    _tlgKeywordOn
0x18006bc17  test    al, al
0x18006bc19  jz      short loc_18006BC6F
0x18006bc1b  mov     eax, [rbp+var_40]
0x18006bc1e  lea     rdx, unk_180318E20
0x18006bc25  xor     ecx, ecx
0x18006bc27  cmp     [rdi+1Ch], eax
0x18006bc2a  movzx   eax, word ptr [rbp+var_10]
0x18006bc2e  mov     word ptr [rbp+var_40], ax
0x18006bc32  setnz   cl
0x18006bc35  mov     eax, [rsi+14h]
0x18006bc38  mov     [rbp+var_38], eax
0x18006bc3b  lea     rax, [rbp+var_20]
0x18006bc3f  mov     [rbp+var_28], rax
0x18006bc43  lea     rax, [rbp+var_3C]
0x18006bc47  mov     [rsp+80h+var_48], rax
0x18006bc4c  lea     rax, [rbp+var_40]
0x18006bc50  mov     [rsp+80h+var_50], rax
0x18006bc55  lea     rax, [rbp+var_38]
0x18006bc59  mov     [rsp+80h+var_58], rax
0x18006bc5e  lea     rax, [rbp+var_28]
0x18006bc62  mov     [rsp+80h+var_60], rax
0x18006bc67  mov     [rbp+var_3C], ecx
0x18006bc6a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006bc6f  mov     rcx, [rsi]
0x18006bc72  test    rcx, rcx
0x18006bc75  jz      loc_18006BE5C
0x18006bc7b  mov     rax, [rcx]
0x18006bc7e  test    rax, rax
0x18006bc81  jz      loc_18006BE5C
0x18006bc87  mov     rax, [rax+18h]
0x18006bc8b  lea     r8, [rdi+20h]
0x18006bc8f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006bc96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bc9b  mov     ebx, eax
0x18006bc9d  test    eax, eax
0x18006bc9f  jnz     loc_18006BE61
0x18006bca5  cmp     [rsi+10h], r14d
0x18006bca9  jz      loc_18006BDF5
0x18006bcaf  lea     rbx, [rdi+148h]
0x18006bcb6  mov     rcx, rbx
0x18006bcb9  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006bcbe  mov     rcx, rbx; struct CSpJobMgr **
0x18006bcc1  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006bcc6  test    eax, eax
0x18006bcc8  jnz     short loc_18006BCD2
0x18006bcca  lea     ebx, [rax+1Ch]
0x18006bccd  jmp     loc_18006BE61
0x18006bcd2  mov     ecx, 10h; Size
0x18006bcd7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006bcdc  xor     r8d, r8d; pcbe
0x18006bcdf  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006bce6  mov     rdx, rax; pv
0x18006bce9  mov     r15, rax
0x18006bcec  mov     [rax], rdi
0x18006bcef  call    cs:__imp_CreateThreadpoolWork
0x18006bcf6  nop     dword ptr [rax+rax+00h]
0x18006bcfb  mov     r14, rax
0x18006bcfe  test    rax, rax
0x18006bd01  jnz     short loc_18006BD0F
0x18006bd03  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006bd08  mov     ebx, eax
0x18006bd0a  jmp     loc_18006BE61
0x18006bd0f  call    cs:__imp_GetCurrentThread
0x18006bd16  nop     dword ptr [rax+rax+00h]
0x18006bd1b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006bd1f  xor     r8d, r8d; OpenAsSelf
0x18006bd22  mov     rcx, rax; ThreadHandle
0x18006bd25  mov     edx, 2000Ch; DesiredAccess
0x18006bd2a  call    cs:__imp_OpenThreadToken
0x18006bd31  nop     dword ptr [rax+rax+00h]
0x18006bd36  test    eax, eax
0x18006bd38  jnz     short loc_18006BD4D
0x18006bd3a  call    cs:__imp_GetLastError
0x18006bd41  nop     dword ptr [rax+rax+00h]
0x18006bd46  cmp     eax, 3F0h
0x18006bd4b  jnz     short loc_18006BD03
0x18006bd4d  mov     rax, [rbp+TokenHandle]
0x18006bd51  mov     r8, r13
0x18006bd54  mov     [r15+8], rax
0x18006bd58  mov     rcx, rdi
0x18006bd5b  mov     rax, [rdi]
0x18006bd5e  mov     rdx, [rsi+8]
0x18006bd62  mov     rax, [rax+18h]
0x18006bd66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bd6b  mov     rax, [rdi]
0x18006bd6e  mov     rdx, r12
0x18006bd71  mov     rcx, rdi
0x18006bd74  mov     rax, [rax+28h]
0x18006bd78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bd7d  mov     ebx, eax
0x18006bd7f  test    eax, eax
0x18006bd81  jz      short loc_18006BD8C
0x18006bd83  cmp     eax, 7
0x18006bd86  jnz     loc_18006BE61
0x18006bd8c  mov     rax, [rdi]
0x18006bd8f  mov     rdx, r12
0x18006bd92  mov     rcx, rdi
0x18006bd95  mov     rax, [rax+38h]
0x18006bd99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bd9e  mov     ebx, eax
0x18006bda0  test    eax, eax
0x18006bda2  jnz     loc_18006BE61
0x18006bda8  mov     rax, [rdi+150h]
0x18006bdaf  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006bdb6  jnz     short loc_18006BDCC
0x18006bdb8  mov     rax, [rdi+158h]
0x18006bdbf  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006bdc6  jz      loc_18006BE61
0x18006bdcc  mov     rdx, r12
0x18006bdcf  mov     rcx, rdi
0x18006bdd2  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006bdd7  mov     ebx, eax
0x18006bdd9  test    eax, eax
0x18006bddb  jnz     loc_18006BE61
0x18006bde1  mov     rcx, r14; pwk
0x18006bde4  call    cs:__imp_SubmitThreadpoolWork
0x18006bdeb  nop     dword ptr [rax+rax+00h]
0x18006bdf0  jmp     loc_18006BEAF
0x18006bdf5  mov     rax, [rdi]
0x18006bdf8  mov     r8, r13
0x18006bdfb  mov     rdx, [rsi+8]
0x18006bdff  mov     rcx, rdi
0x18006be02  mov     rax, [rax+10h]
0x18006be06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006be0b  mov     rax, [rdi]
0x18006be0e  mov     rdx, r12
0x18006be11  mov     rcx, rdi
0x18006be14  mov     rax, [rax+30h]
0x18006be18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006be1d  mov     ebx, eax
0x18006be1f  test    eax, eax
0x18006be21  jz      short loc_18006BE28
0x18006be23  cmp     eax, 7
0x18006be26  jnz     short loc_18006BE61
0x18006be28  mov     rax, [rdi]
0x18006be2b  mov     rdx, r12
0x18006be2e  mov     rcx, rdi
0x18006be31  mov     rax, [rax+28h]
0x18006be35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006be3a  mov     ebx, eax
0x18006be3c  test    eax, eax
0x18006be3e  jz      short loc_18006BE45
0x18006be40  cmp     eax, 7
0x18006be43  jnz     short loc_18006BE61
0x18006be45  mov     rax, [rdi]
0x18006be48  mov     rdx, r12
0x18006be4b  mov     rcx, rdi
0x18006be4e  mov     rax, [rax+38h]
0x18006be52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006be57  jmp     loc_18006BD08
0x18006be5c  mov     ebx, 4
0x18006be61  mov     rax, [rdi]
0x18006be64  mov     edx, 1
0x18006be69  mov     rcx, rdi
0x18006be6c  mov     rax, [rax]
0x18006be6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006be74  test    r15, r15
0x18006be77  jz      short loc_18006BE86
0x18006be79  mov     edx, 10h
0x18006be7e  mov     rcx, r15; Block
0x18006be81  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006be86  mov     rcx, [rbp+TokenHandle]; hObject
0x18006be8a  test    rcx, rcx
0x18006be8d  jz      short loc_18006BE9B
0x18006be8f  call    cs:__imp_CloseHandle
0x18006be96  nop     dword ptr [rax+rax+00h]
0x18006be9b  test    r14, r14
0x18006be9e  jz      short loc_18006BEAF
0x18006bea0  mov     rcx, r14; pwk
0x18006bea3  call    cs:__imp_CloseThreadpoolWork
0x18006beaa  nop     dword ptr [rax+rax+00h]
0x18006beaf  mov     eax, ebx
0x18006beb1  mov     rcx, [rbp+var_8]
0x18006beb5  xor     rcx, rsp; StackCookie
0x18006beb8  call    __security_check_cookie
0x18006bebd  mov     rbx, [rsp+80h+arg_18]
0x18006bec5  add     rsp, 80h
0x18006becc  pop     r15
0x18006bece  pop     r14
0x18006bed0  pop     r13
0x18006bed2  pop     r12
0x18006bed4  pop     rdi
0x18006bed5  pop     rsi
0x18006bed6  pop     rbp
0x18006bed7  retn
```
