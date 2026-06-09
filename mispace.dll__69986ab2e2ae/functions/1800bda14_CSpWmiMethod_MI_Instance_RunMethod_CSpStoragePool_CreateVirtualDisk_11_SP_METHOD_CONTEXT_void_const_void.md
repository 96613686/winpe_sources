# CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::CreateVirtualDisk,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bda14`
- end: `0x1800bdd91`
- name: `??$RunMethod@VCreateVirtualDisk@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800c5060`
- `0x1800ccda4`

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
- `0x1800bda14`
- `0x1800c0d84`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdbf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdbf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bdbc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bdbc7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bdbe2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bdbe2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bdba7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bdba7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bdc9c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bdc9c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bdd5b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bdd5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bdd47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bdd47`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::CreateVirtualDisk,11>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 VirtualDisk; // rax
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
  CSpStoragePool::CreateVirtualDisk *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::CreateVirtualDisk *)operator new(0x260u);
  VirtualDisk = CSpStoragePool::CreateVirtualDisk::CreateVirtualDisk(v25);
  v8 = VirtualDisk;
  if ( VirtualDisk )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)VirtualDisk + 8LL))(VirtualDisk, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStoragePool::CreateVirtualDisk *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_18032F154,
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
0x1800bda14  mov     [rsp-38h+arg_18], rbx
0x1800bda19  push    rbp
0x1800bda1a  push    rsi
0x1800bda1b  push    rdi
0x1800bda1c  push    r12
0x1800bda1e  push    r13
0x1800bda20  push    r14
0x1800bda22  push    r15
0x1800bda24  mov     rbp, rsp
0x1800bda27  sub     rsp, 80h
0x1800bda2e  mov     rax, cs:__security_cookie
0x1800bda35  xor     rax, rsp
0x1800bda38  mov     [rbp+var_8], rax
0x1800bda3c  xor     eax, eax
0x1800bda3e  mov     rsi, rcx
0x1800bda41  xorps   xmm0, xmm0
0x1800bda44  mov     [rbp+var_10], eax
0x1800bda47  mov     ecx, 260h; Size
0x1800bda4c  mov     [rbp+var_40], eax
0x1800bda4f  movups  [rbp+var_20], xmm0
0x1800bda53  mov     [rbp+TokenHandle], rax
0x1800bda57  mov     r12, r8
0x1800bda5a  mov     r13, rdx
0x1800bda5d  xor     r14d, r14d
0x1800bda60  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bda65  mov     rcx, rax; this
0x1800bda68  mov     [rbp+var_28], rax
0x1800bda6c  call    ??0CreateVirtualDisk@CSpStoragePool@@QEAA@XZ; CSpStoragePool::CreateVirtualDisk::CreateVirtualDisk(void)
0x1800bda71  mov     rdi, rax
0x1800bda74  test    rax, rax
0x1800bda77  jnz     short loc_1800BDA81
0x1800bda79  lea     ebx, [rax+1Bh]
0x1800bda7c  jmp     loc_1800BDD3E
0x1800bda81  mov     rax, [rax]
0x1800bda84  mov     rdx, rsi
0x1800bda87  mov     rcx, rdi
0x1800bda8a  xor     r15d, r15d
0x1800bda8d  mov     rax, [rax+8]
0x1800bda91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bda96  lea     rcx, [rbp+var_40]
0x1800bda9a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bda9f  mov     [rdi+1Ch], eax
0x1800bdaa2  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bdaa6  mov     ecx, [rsi+14h]; unsigned int
0x1800bdaa9  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bdaae  mov     eax, cs:dword_18039EB68
0x1800bdab4  cmp     eax, 5
0x1800bdab7  jbe     short loc_1800BDB27
0x1800bdab9  mov     rdx, 400000000000h
0x1800bdac3  lea     rcx, dword_18039EB68
0x1800bdaca  call    _tlgKeywordOn
0x1800bdacf  test    al, al
0x1800bdad1  jz      short loc_1800BDB27
0x1800bdad3  mov     eax, [rbp+var_40]
0x1800bdad6  lea     rdx, dword_18032F154
0x1800bdadd  xor     ecx, ecx
0x1800bdadf  cmp     [rdi+1Ch], eax
0x1800bdae2  movzx   eax, word ptr [rbp+var_10]
0x1800bdae6  mov     word ptr [rbp+var_40], ax
0x1800bdaea  setnz   cl
0x1800bdaed  mov     eax, [rsi+14h]
0x1800bdaf0  mov     [rbp+var_38], eax
0x1800bdaf3  lea     rax, [rbp+var_20]
0x1800bdaf7  mov     [rbp+var_28], rax
0x1800bdafb  lea     rax, [rbp+var_3C]
0x1800bdaff  mov     [rsp+80h+var_48], rax
0x1800bdb04  lea     rax, [rbp+var_40]
0x1800bdb08  mov     [rsp+80h+var_50], rax
0x1800bdb0d  lea     rax, [rbp+var_38]
0x1800bdb11  mov     [rsp+80h+var_58], rax
0x1800bdb16  lea     rax, [rbp+var_28]
0x1800bdb1a  mov     [rsp+80h+var_60], rax
0x1800bdb1f  mov     [rbp+var_3C], ecx
0x1800bdb22  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bdb27  mov     rcx, [rsi]
0x1800bdb2a  test    rcx, rcx
0x1800bdb2d  jz      loc_1800BDD14
0x1800bdb33  mov     rax, [rcx]
0x1800bdb36  test    rax, rax
0x1800bdb39  jz      loc_1800BDD14
0x1800bdb3f  mov     rax, [rax+18h]
0x1800bdb43  lea     r8, [rdi+20h]
0x1800bdb47  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bdb4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdb53  mov     ebx, eax
0x1800bdb55  test    eax, eax
0x1800bdb57  jnz     loc_1800BDD19
0x1800bdb5d  cmp     [rsi+10h], r14d
0x1800bdb61  jz      loc_1800BDCAD
0x1800bdb67  lea     rbx, [rdi+148h]
0x1800bdb6e  mov     rcx, rbx
0x1800bdb71  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bdb76  mov     rcx, rbx; struct CSpJobMgr **
0x1800bdb79  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bdb7e  test    eax, eax
0x1800bdb80  jnz     short loc_1800BDB8A
0x1800bdb82  lea     ebx, [rax+1Ch]
0x1800bdb85  jmp     loc_1800BDD19
0x1800bdb8a  mov     ecx, 10h; Size
0x1800bdb8f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bdb94  xor     r8d, r8d; pcbe
0x1800bdb97  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bdb9e  mov     rdx, rax; pv
0x1800bdba1  mov     r15, rax
0x1800bdba4  mov     [rax], rdi
0x1800bdba7  call    cs:__imp_CreateThreadpoolWork
0x1800bdbae  nop     dword ptr [rax+rax+00h]
0x1800bdbb3  mov     r14, rax
0x1800bdbb6  test    rax, rax
0x1800bdbb9  jnz     short loc_1800BDBC7
0x1800bdbbb  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bdbc0  mov     ebx, eax
0x1800bdbc2  jmp     loc_1800BDD19
0x1800bdbc7  call    cs:__imp_GetCurrentThread
0x1800bdbce  nop     dword ptr [rax+rax+00h]
0x1800bdbd3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bdbd7  xor     r8d, r8d; OpenAsSelf
0x1800bdbda  mov     rcx, rax; ThreadHandle
0x1800bdbdd  mov     edx, 2000Ch; DesiredAccess
0x1800bdbe2  call    cs:__imp_OpenThreadToken
0x1800bdbe9  nop     dword ptr [rax+rax+00h]
0x1800bdbee  test    eax, eax
0x1800bdbf0  jnz     short loc_1800BDC05
0x1800bdbf2  call    cs:__imp_GetLastError
0x1800bdbf9  nop     dword ptr [rax+rax+00h]
0x1800bdbfe  cmp     eax, 3F0h
0x1800bdc03  jnz     short loc_1800BDBBB
0x1800bdc05  mov     rax, [rbp+TokenHandle]
0x1800bdc09  mov     r8, r13
0x1800bdc0c  mov     [r15+8], rax
0x1800bdc10  mov     rcx, rdi
0x1800bdc13  mov     rax, [rdi]
0x1800bdc16  mov     rdx, [rsi+8]
0x1800bdc1a  mov     rax, [rax+18h]
0x1800bdc1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdc23  mov     rax, [rdi]
0x1800bdc26  mov     rdx, r12
0x1800bdc29  mov     rcx, rdi
0x1800bdc2c  mov     rax, [rax+28h]
0x1800bdc30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdc35  mov     ebx, eax
0x1800bdc37  test    eax, eax
0x1800bdc39  jz      short loc_1800BDC44
0x1800bdc3b  cmp     eax, 7
0x1800bdc3e  jnz     loc_1800BDD19
0x1800bdc44  mov     rax, [rdi]
0x1800bdc47  mov     rdx, r12
0x1800bdc4a  mov     rcx, rdi
0x1800bdc4d  mov     rax, [rax+38h]
0x1800bdc51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdc56  mov     ebx, eax
0x1800bdc58  test    eax, eax
0x1800bdc5a  jnz     loc_1800BDD19
0x1800bdc60  mov     rax, [rdi+150h]
0x1800bdc67  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bdc6e  jnz     short loc_1800BDC84
0x1800bdc70  mov     rax, [rdi+158h]
0x1800bdc77  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bdc7e  jz      loc_1800BDD19
0x1800bdc84  mov     rdx, r12
0x1800bdc87  mov     rcx, rdi
0x1800bdc8a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bdc8f  mov     ebx, eax
0x1800bdc91  test    eax, eax
0x1800bdc93  jnz     loc_1800BDD19
0x1800bdc99  mov     rcx, r14; pwk
0x1800bdc9c  call    cs:__imp_SubmitThreadpoolWork
0x1800bdca3  nop     dword ptr [rax+rax+00h]
0x1800bdca8  jmp     loc_1800BDD67
0x1800bdcad  mov     rax, [rdi]
0x1800bdcb0  mov     r8, r13
0x1800bdcb3  mov     rdx, [rsi+8]
0x1800bdcb7  mov     rcx, rdi
0x1800bdcba  mov     rax, [rax+10h]
0x1800bdcbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdcc3  mov     rax, [rdi]
0x1800bdcc6  mov     rdx, r12
0x1800bdcc9  mov     rcx, rdi
0x1800bdccc  mov     rax, [rax+30h]
0x1800bdcd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdcd5  mov     ebx, eax
0x1800bdcd7  test    eax, eax
0x1800bdcd9  jz      short loc_1800BDCE0
0x1800bdcdb  cmp     eax, 7
0x1800bdcde  jnz     short loc_1800BDD19
0x1800bdce0  mov     rax, [rdi]
0x1800bdce3  mov     rdx, r12
0x1800bdce6  mov     rcx, rdi
0x1800bdce9  mov     rax, [rax+28h]
0x1800bdced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdcf2  mov     ebx, eax
0x1800bdcf4  test    eax, eax
0x1800bdcf6  jz      short loc_1800BDCFD
0x1800bdcf8  cmp     eax, 7
0x1800bdcfb  jnz     short loc_1800BDD19
0x1800bdcfd  mov     rax, [rdi]
0x1800bdd00  mov     rdx, r12
0x1800bdd03  mov     rcx, rdi
0x1800bdd06  mov     rax, [rax+38h]
0x1800bdd0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdd0f  jmp     loc_1800BDBC0
0x1800bdd14  mov     ebx, 4
0x1800bdd19  mov     rax, [rdi]
0x1800bdd1c  mov     edx, 1
0x1800bdd21  mov     rcx, rdi
0x1800bdd24  mov     rax, [rax]
0x1800bdd27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdd2c  test    r15, r15
0x1800bdd2f  jz      short loc_1800BDD3E
0x1800bdd31  mov     edx, 10h
0x1800bdd36  mov     rcx, r15; Block
0x1800bdd39  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bdd3e  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bdd42  test    rcx, rcx
0x1800bdd45  jz      short loc_1800BDD53
0x1800bdd47  call    cs:__imp_CloseHandle
0x1800bdd4e  nop     dword ptr [rax+rax+00h]
0x1800bdd53  test    r14, r14
0x1800bdd56  jz      short loc_1800BDD67
0x1800bdd58  mov     rcx, r14; pwk
0x1800bdd5b  call    cs:__imp_CloseThreadpoolWork
0x1800bdd62  nop     dword ptr [rax+rax+00h]
0x1800bdd67  mov     eax, ebx
0x1800bdd69  mov     rcx, [rbp+var_8]
0x1800bdd6d  xor     rcx, rsp; StackCookie
0x1800bdd70  call    __security_check_cookie
0x1800bdd75  mov     rbx, [rsp+80h+arg_18]
0x1800bdd7d  add     rsp, 80h
0x1800bdd84  pop     r15
0x1800bdd86  pop     r14
0x1800bdd88  pop     r13
0x1800bdd8a  pop     r12
0x1800bdd8c  pop     rdi
0x1800bdd8d  pop     rsi
0x1800bdd8e  pop     rbp
0x1800bdd8f  retn
```
