# CSpWmiMethod<_SPACES_StoragePool_Upgrade>::RunMethod<CSpStoragePool::Upgrade,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800c0460`
- end: `0x1800c07dd`
- name: `??$RunMethod@VUpgrade@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_Upgrade@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800c5060`

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
- `0x1800c0460`
- `0x1800c1420`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c063e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c063e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c0613`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c0613`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c062e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c062e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800c05f3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800c05f3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800c06e8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800c06e8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800c07a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800c07a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0793`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0793`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StoragePool_Upgrade>::RunMethod<CSpStoragePool::Upgrade,11>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 v7; // rax
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
  CSpStoragePool::Upgrade *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::Upgrade *)operator new(0x160u);
  v7 = CSpStoragePool::Upgrade::Upgrade(v25);
  v8 = v7;
  if ( v7 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 8LL))(v7, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStoragePool::Upgrade *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18032D9AD,
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
0x1800c0460  mov     [rsp-38h+arg_18], rbx
0x1800c0465  push    rbp
0x1800c0466  push    rsi
0x1800c0467  push    rdi
0x1800c0468  push    r12
0x1800c046a  push    r13
0x1800c046c  push    r14
0x1800c046e  push    r15
0x1800c0470  mov     rbp, rsp
0x1800c0473  sub     rsp, 80h
0x1800c047a  mov     rax, cs:__security_cookie
0x1800c0481  xor     rax, rsp
0x1800c0484  mov     [rbp+var_8], rax
0x1800c0488  xor     eax, eax
0x1800c048a  mov     rsi, rcx
0x1800c048d  xorps   xmm0, xmm0
0x1800c0490  mov     [rbp+var_10], eax
0x1800c0493  mov     ecx, 160h; Size
0x1800c0498  mov     [rbp+var_40], eax
0x1800c049b  movups  [rbp+var_20], xmm0
0x1800c049f  mov     [rbp+TokenHandle], rax
0x1800c04a3  mov     r12, r8
0x1800c04a6  mov     r13, rdx
0x1800c04a9  xor     r14d, r14d
0x1800c04ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c04b1  mov     rcx, rax; this
0x1800c04b4  mov     [rbp+var_28], rax
0x1800c04b8  call    ??0Upgrade@CSpStoragePool@@QEAA@XZ; CSpStoragePool::Upgrade::Upgrade(void)
0x1800c04bd  mov     rdi, rax
0x1800c04c0  test    rax, rax
0x1800c04c3  jnz     short loc_1800C04CD
0x1800c04c5  lea     ebx, [rax+1Bh]
0x1800c04c8  jmp     loc_1800C078A
0x1800c04cd  mov     rax, [rax]
0x1800c04d0  mov     rdx, rsi
0x1800c04d3  mov     rcx, rdi
0x1800c04d6  xor     r15d, r15d
0x1800c04d9  mov     rax, [rax+8]
0x1800c04dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c04e2  lea     rcx, [rbp+var_40]
0x1800c04e6  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800c04eb  mov     [rdi+1Ch], eax
0x1800c04ee  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800c04f2  mov     ecx, [rsi+14h]; unsigned int
0x1800c04f5  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800c04fa  mov     eax, cs:dword_18039EB68
0x1800c0500  cmp     eax, 5
0x1800c0503  jbe     short loc_1800C0573
0x1800c0505  mov     rdx, 400000000000h
0x1800c050f  lea     rcx, dword_18039EB68
0x1800c0516  call    _tlgKeywordOn
0x1800c051b  test    al, al
0x1800c051d  jz      short loc_1800C0573
0x1800c051f  mov     eax, [rbp+var_40]
0x1800c0522  lea     rdx, byte_18032D9AD
0x1800c0529  xor     ecx, ecx
0x1800c052b  cmp     [rdi+1Ch], eax
0x1800c052e  movzx   eax, word ptr [rbp+var_10]
0x1800c0532  mov     word ptr [rbp+var_40], ax
0x1800c0536  setnz   cl
0x1800c0539  mov     eax, [rsi+14h]
0x1800c053c  mov     [rbp+var_38], eax
0x1800c053f  lea     rax, [rbp+var_20]
0x1800c0543  mov     [rbp+var_28], rax
0x1800c0547  lea     rax, [rbp+var_3C]
0x1800c054b  mov     [rsp+80h+var_48], rax
0x1800c0550  lea     rax, [rbp+var_40]
0x1800c0554  mov     [rsp+80h+var_50], rax
0x1800c0559  lea     rax, [rbp+var_38]
0x1800c055d  mov     [rsp+80h+var_58], rax
0x1800c0562  lea     rax, [rbp+var_28]
0x1800c0566  mov     [rsp+80h+var_60], rax
0x1800c056b  mov     [rbp+var_3C], ecx
0x1800c056e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800c0573  mov     rcx, [rsi]
0x1800c0576  test    rcx, rcx
0x1800c0579  jz      loc_1800C0760
0x1800c057f  mov     rax, [rcx]
0x1800c0582  test    rax, rax
0x1800c0585  jz      loc_1800C0760
0x1800c058b  mov     rax, [rax+18h]
0x1800c058f  lea     r8, [rdi+20h]
0x1800c0593  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800c059a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c059f  mov     ebx, eax
0x1800c05a1  test    eax, eax
0x1800c05a3  jnz     loc_1800C0765
0x1800c05a9  cmp     [rsi+10h], r14d
0x1800c05ad  jz      loc_1800C06F9
0x1800c05b3  lea     rbx, [rdi+148h]
0x1800c05ba  mov     rcx, rbx
0x1800c05bd  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800c05c2  mov     rcx, rbx; struct CSpJobMgr **
0x1800c05c5  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800c05ca  test    eax, eax
0x1800c05cc  jnz     short loc_1800C05D6
0x1800c05ce  lea     ebx, [rax+1Ch]
0x1800c05d1  jmp     loc_1800C0765
0x1800c05d6  mov     ecx, 10h; Size
0x1800c05db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c05e0  xor     r8d, r8d; pcbe
0x1800c05e3  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800c05ea  mov     rdx, rax; pv
0x1800c05ed  mov     r15, rax
0x1800c05f0  mov     [rax], rdi
0x1800c05f3  call    cs:__imp_CreateThreadpoolWork
0x1800c05fa  nop     dword ptr [rax+rax+00h]
0x1800c05ff  mov     r14, rax
0x1800c0602  test    rax, rax
0x1800c0605  jnz     short loc_1800C0613
0x1800c0607  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800c060c  mov     ebx, eax
0x1800c060e  jmp     loc_1800C0765
0x1800c0613  call    cs:__imp_GetCurrentThread
0x1800c061a  nop     dword ptr [rax+rax+00h]
0x1800c061f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800c0623  xor     r8d, r8d; OpenAsSelf
0x1800c0626  mov     rcx, rax; ThreadHandle
0x1800c0629  mov     edx, 2000Ch; DesiredAccess
0x1800c062e  call    cs:__imp_OpenThreadToken
0x1800c0635  nop     dword ptr [rax+rax+00h]
0x1800c063a  test    eax, eax
0x1800c063c  jnz     short loc_1800C0651
0x1800c063e  call    cs:__imp_GetLastError
0x1800c0645  nop     dword ptr [rax+rax+00h]
0x1800c064a  cmp     eax, 3F0h
0x1800c064f  jnz     short loc_1800C0607
0x1800c0651  mov     rax, [rbp+TokenHandle]
0x1800c0655  mov     r8, r13
0x1800c0658  mov     [r15+8], rax
0x1800c065c  mov     rcx, rdi
0x1800c065f  mov     rax, [rdi]
0x1800c0662  mov     rdx, [rsi+8]
0x1800c0666  mov     rax, [rax+18h]
0x1800c066a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c066f  mov     rax, [rdi]
0x1800c0672  mov     rdx, r12
0x1800c0675  mov     rcx, rdi
0x1800c0678  mov     rax, [rax+28h]
0x1800c067c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0681  mov     ebx, eax
0x1800c0683  test    eax, eax
0x1800c0685  jz      short loc_1800C0690
0x1800c0687  cmp     eax, 7
0x1800c068a  jnz     loc_1800C0765
0x1800c0690  mov     rax, [rdi]
0x1800c0693  mov     rdx, r12
0x1800c0696  mov     rcx, rdi
0x1800c0699  mov     rax, [rax+38h]
0x1800c069d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c06a2  mov     ebx, eax
0x1800c06a4  test    eax, eax
0x1800c06a6  jnz     loc_1800C0765
0x1800c06ac  mov     rax, [rdi+150h]
0x1800c06b3  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800c06ba  jnz     short loc_1800C06D0
0x1800c06bc  mov     rax, [rdi+158h]
0x1800c06c3  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800c06ca  jz      loc_1800C0765
0x1800c06d0  mov     rdx, r12
0x1800c06d3  mov     rcx, rdi
0x1800c06d6  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800c06db  mov     ebx, eax
0x1800c06dd  test    eax, eax
0x1800c06df  jnz     loc_1800C0765
0x1800c06e5  mov     rcx, r14; pwk
0x1800c06e8  call    cs:__imp_SubmitThreadpoolWork
0x1800c06ef  nop     dword ptr [rax+rax+00h]
0x1800c06f4  jmp     loc_1800C07B3
0x1800c06f9  mov     rax, [rdi]
0x1800c06fc  mov     r8, r13
0x1800c06ff  mov     rdx, [rsi+8]
0x1800c0703  mov     rcx, rdi
0x1800c0706  mov     rax, [rax+10h]
0x1800c070a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c070f  mov     rax, [rdi]
0x1800c0712  mov     rdx, r12
0x1800c0715  mov     rcx, rdi
0x1800c0718  mov     rax, [rax+30h]
0x1800c071c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0721  mov     ebx, eax
0x1800c0723  test    eax, eax
0x1800c0725  jz      short loc_1800C072C
0x1800c0727  cmp     eax, 7
0x1800c072a  jnz     short loc_1800C0765
0x1800c072c  mov     rax, [rdi]
0x1800c072f  mov     rdx, r12
0x1800c0732  mov     rcx, rdi
0x1800c0735  mov     rax, [rax+28h]
0x1800c0739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c073e  mov     ebx, eax
0x1800c0740  test    eax, eax
0x1800c0742  jz      short loc_1800C0749
0x1800c0744  cmp     eax, 7
0x1800c0747  jnz     short loc_1800C0765
0x1800c0749  mov     rax, [rdi]
0x1800c074c  mov     rdx, r12
0x1800c074f  mov     rcx, rdi
0x1800c0752  mov     rax, [rax+38h]
0x1800c0756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c075b  jmp     loc_1800C060C
0x1800c0760  mov     ebx, 4
0x1800c0765  mov     rax, [rdi]
0x1800c0768  mov     edx, 1
0x1800c076d  mov     rcx, rdi
0x1800c0770  mov     rax, [rax]
0x1800c0773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0778  test    r15, r15
0x1800c077b  jz      short loc_1800C078A
0x1800c077d  mov     edx, 10h
0x1800c0782  mov     rcx, r15; Block
0x1800c0785  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800c078a  mov     rcx, [rbp+TokenHandle]; hObject
0x1800c078e  test    rcx, rcx
0x1800c0791  jz      short loc_1800C079F
0x1800c0793  call    cs:__imp_CloseHandle
0x1800c079a  nop     dword ptr [rax+rax+00h]
0x1800c079f  test    r14, r14
0x1800c07a2  jz      short loc_1800C07B3
0x1800c07a4  mov     rcx, r14; pwk
0x1800c07a7  call    cs:__imp_CloseThreadpoolWork
0x1800c07ae  nop     dword ptr [rax+rax+00h]
0x1800c07b3  mov     eax, ebx
0x1800c07b5  mov     rcx, [rbp+var_8]
0x1800c07b9  xor     rcx, rsp; StackCookie
0x1800c07bc  call    __security_check_cookie
0x1800c07c1  mov     rbx, [rsp+80h+arg_18]
0x1800c07c9  add     rsp, 80h
0x1800c07d0  pop     r15
0x1800c07d2  pop     r14
0x1800c07d4  pop     r13
0x1800c07d6  pop     r12
0x1800c07d8  pop     rdi
0x1800c07d9  pop     rsi
0x1800c07da  pop     rbp
0x1800c07db  retn
```
