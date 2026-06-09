# CSpWmiMethod<_MI_Instance>::RunMethod<CSpSubsystem::SetAttributes,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006d074`
- end: `0x18006d3f1`
- name: `??$RunMethod@VSetAttributes@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x18006d074`
- `0x18006e388`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d252`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006d227`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006d227`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006d242`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006d242`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006d207`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006d207`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006d2fc`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006d2fc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006d3bb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006d3bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d3a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d3a7`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpSubsystem::SetAttributes,13>(
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
  CSpSubsystem::SetAttributes *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::SetAttributes *)operator new(0x170u);
  v7 = CSpSubsystem::SetAttributes::SetAttributes(v25);
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
      v25 = (CSpSubsystem::SetAttributes *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&byte_180317277,
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
0x18006d074  mov     [rsp-38h+arg_18], rbx
0x18006d079  push    rbp
0x18006d07a  push    rsi
0x18006d07b  push    rdi
0x18006d07c  push    r12
0x18006d07e  push    r13
0x18006d080  push    r14
0x18006d082  push    r15
0x18006d084  mov     rbp, rsp
0x18006d087  sub     rsp, 80h
0x18006d08e  mov     rax, cs:__security_cookie
0x18006d095  xor     rax, rsp
0x18006d098  mov     [rbp+var_8], rax
0x18006d09c  xor     eax, eax
0x18006d09e  mov     rsi, rcx
0x18006d0a1  xorps   xmm0, xmm0
0x18006d0a4  mov     [rbp+var_10], eax
0x18006d0a7  mov     ecx, 170h; Size
0x18006d0ac  mov     [rbp+var_40], eax
0x18006d0af  movups  [rbp+var_20], xmm0
0x18006d0b3  mov     [rbp+TokenHandle], rax
0x18006d0b7  mov     r12, r8
0x18006d0ba  mov     r13, rdx
0x18006d0bd  xor     r14d, r14d
0x18006d0c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006d0c5  mov     rcx, rax; this
0x18006d0c8  mov     [rbp+var_28], rax
0x18006d0cc  call    ??0SetAttributes@CSpSubsystem@@QEAA@XZ; CSpSubsystem::SetAttributes::SetAttributes(void)
0x18006d0d1  mov     rdi, rax
0x18006d0d4  test    rax, rax
0x18006d0d7  jnz     short loc_18006D0E1
0x18006d0d9  lea     ebx, [rax+1Bh]
0x18006d0dc  jmp     loc_18006D39E
0x18006d0e1  mov     rax, [rax]
0x18006d0e4  mov     rdx, rsi
0x18006d0e7  mov     rcx, rdi
0x18006d0ea  xor     r15d, r15d
0x18006d0ed  mov     rax, [rax+8]
0x18006d0f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d0f6  lea     rcx, [rbp+var_40]
0x18006d0fa  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006d0ff  mov     [rdi+1Ch], eax
0x18006d102  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006d106  mov     ecx, [rsi+14h]; unsigned int
0x18006d109  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006d10e  mov     eax, cs:dword_18039EB68
0x18006d114  cmp     eax, 5
0x18006d117  jbe     short loc_18006D187
0x18006d119  mov     rdx, 400000000000h
0x18006d123  lea     rcx, dword_18039EB68
0x18006d12a  call    _tlgKeywordOn
0x18006d12f  test    al, al
0x18006d131  jz      short loc_18006D187
0x18006d133  mov     eax, [rbp+var_40]
0x18006d136  lea     rdx, byte_180317277
0x18006d13d  xor     ecx, ecx
0x18006d13f  cmp     [rdi+1Ch], eax
0x18006d142  movzx   eax, word ptr [rbp+var_10]
0x18006d146  mov     word ptr [rbp+var_40], ax
0x18006d14a  setnz   cl
0x18006d14d  mov     eax, [rsi+14h]
0x18006d150  mov     [rbp+var_38], eax
0x18006d153  lea     rax, [rbp+var_20]
0x18006d157  mov     [rbp+var_28], rax
0x18006d15b  lea     rax, [rbp+var_3C]
0x18006d15f  mov     [rsp+80h+var_48], rax
0x18006d164  lea     rax, [rbp+var_40]
0x18006d168  mov     [rsp+80h+var_50], rax
0x18006d16d  lea     rax, [rbp+var_38]
0x18006d171  mov     [rsp+80h+var_58], rax
0x18006d176  lea     rax, [rbp+var_28]
0x18006d17a  mov     [rsp+80h+var_60], rax
0x18006d17f  mov     [rbp+var_3C], ecx
0x18006d182  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006d187  mov     rcx, [rsi]
0x18006d18a  test    rcx, rcx
0x18006d18d  jz      loc_18006D374
0x18006d193  mov     rax, [rcx]
0x18006d196  test    rax, rax
0x18006d199  jz      loc_18006D374
0x18006d19f  mov     rax, [rax+18h]
0x18006d1a3  lea     r8, [rdi+20h]
0x18006d1a7  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006d1ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d1b3  mov     ebx, eax
0x18006d1b5  test    eax, eax
0x18006d1b7  jnz     loc_18006D379
0x18006d1bd  cmp     [rsi+10h], r14d
0x18006d1c1  jz      loc_18006D30D
0x18006d1c7  lea     rbx, [rdi+148h]
0x18006d1ce  mov     rcx, rbx
0x18006d1d1  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006d1d6  mov     rcx, rbx; struct CSpJobMgr **
0x18006d1d9  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006d1de  test    eax, eax
0x18006d1e0  jnz     short loc_18006D1EA
0x18006d1e2  lea     ebx, [rax+1Ch]
0x18006d1e5  jmp     loc_18006D379
0x18006d1ea  mov     ecx, 10h; Size
0x18006d1ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006d1f4  xor     r8d, r8d; pcbe
0x18006d1f7  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006d1fe  mov     rdx, rax; pv
0x18006d201  mov     r15, rax
0x18006d204  mov     [rax], rdi
0x18006d207  call    cs:__imp_CreateThreadpoolWork
0x18006d20e  nop     dword ptr [rax+rax+00h]
0x18006d213  mov     r14, rax
0x18006d216  test    rax, rax
0x18006d219  jnz     short loc_18006D227
0x18006d21b  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006d220  mov     ebx, eax
0x18006d222  jmp     loc_18006D379
0x18006d227  call    cs:__imp_GetCurrentThread
0x18006d22e  nop     dword ptr [rax+rax+00h]
0x18006d233  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006d237  xor     r8d, r8d; OpenAsSelf
0x18006d23a  mov     rcx, rax; ThreadHandle
0x18006d23d  mov     edx, 2000Ch; DesiredAccess
0x18006d242  call    cs:__imp_OpenThreadToken
0x18006d249  nop     dword ptr [rax+rax+00h]
0x18006d24e  test    eax, eax
0x18006d250  jnz     short loc_18006D265
0x18006d252  call    cs:__imp_GetLastError
0x18006d259  nop     dword ptr [rax+rax+00h]
0x18006d25e  cmp     eax, 3F0h
0x18006d263  jnz     short loc_18006D21B
0x18006d265  mov     rax, [rbp+TokenHandle]
0x18006d269  mov     r8, r13
0x18006d26c  mov     [r15+8], rax
0x18006d270  mov     rcx, rdi
0x18006d273  mov     rax, [rdi]
0x18006d276  mov     rdx, [rsi+8]
0x18006d27a  mov     rax, [rax+18h]
0x18006d27e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d283  mov     rax, [rdi]
0x18006d286  mov     rdx, r12
0x18006d289  mov     rcx, rdi
0x18006d28c  mov     rax, [rax+28h]
0x18006d290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d295  mov     ebx, eax
0x18006d297  test    eax, eax
0x18006d299  jz      short loc_18006D2A4
0x18006d29b  cmp     eax, 7
0x18006d29e  jnz     loc_18006D379
0x18006d2a4  mov     rax, [rdi]
0x18006d2a7  mov     rdx, r12
0x18006d2aa  mov     rcx, rdi
0x18006d2ad  mov     rax, [rax+38h]
0x18006d2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d2b6  mov     ebx, eax
0x18006d2b8  test    eax, eax
0x18006d2ba  jnz     loc_18006D379
0x18006d2c0  mov     rax, [rdi+150h]
0x18006d2c7  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006d2ce  jnz     short loc_18006D2E4
0x18006d2d0  mov     rax, [rdi+158h]
0x18006d2d7  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006d2de  jz      loc_18006D379
0x18006d2e4  mov     rdx, r12
0x18006d2e7  mov     rcx, rdi
0x18006d2ea  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006d2ef  mov     ebx, eax
0x18006d2f1  test    eax, eax
0x18006d2f3  jnz     loc_18006D379
0x18006d2f9  mov     rcx, r14; pwk
0x18006d2fc  call    cs:__imp_SubmitThreadpoolWork
0x18006d303  nop     dword ptr [rax+rax+00h]
0x18006d308  jmp     loc_18006D3C7
0x18006d30d  mov     rax, [rdi]
0x18006d310  mov     r8, r13
0x18006d313  mov     rdx, [rsi+8]
0x18006d317  mov     rcx, rdi
0x18006d31a  mov     rax, [rax+10h]
0x18006d31e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d323  mov     rax, [rdi]
0x18006d326  mov     rdx, r12
0x18006d329  mov     rcx, rdi
0x18006d32c  mov     rax, [rax+30h]
0x18006d330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d335  mov     ebx, eax
0x18006d337  test    eax, eax
0x18006d339  jz      short loc_18006D340
0x18006d33b  cmp     eax, 7
0x18006d33e  jnz     short loc_18006D379
0x18006d340  mov     rax, [rdi]
0x18006d343  mov     rdx, r12
0x18006d346  mov     rcx, rdi
0x18006d349  mov     rax, [rax+28h]
0x18006d34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d352  mov     ebx, eax
0x18006d354  test    eax, eax
0x18006d356  jz      short loc_18006D35D
0x18006d358  cmp     eax, 7
0x18006d35b  jnz     short loc_18006D379
0x18006d35d  mov     rax, [rdi]
0x18006d360  mov     rdx, r12
0x18006d363  mov     rcx, rdi
0x18006d366  mov     rax, [rax+38h]
0x18006d36a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d36f  jmp     loc_18006D220
0x18006d374  mov     ebx, 4
0x18006d379  mov     rax, [rdi]
0x18006d37c  mov     edx, 1
0x18006d381  mov     rcx, rdi
0x18006d384  mov     rax, [rax]
0x18006d387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d38c  test    r15, r15
0x18006d38f  jz      short loc_18006D39E
0x18006d391  mov     edx, 10h
0x18006d396  mov     rcx, r15; Block
0x18006d399  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006d39e  mov     rcx, [rbp+TokenHandle]; hObject
0x18006d3a2  test    rcx, rcx
0x18006d3a5  jz      short loc_18006D3B3
0x18006d3a7  call    cs:__imp_CloseHandle
0x18006d3ae  nop     dword ptr [rax+rax+00h]
0x18006d3b3  test    r14, r14
0x18006d3b6  jz      short loc_18006D3C7
0x18006d3b8  mov     rcx, r14; pwk
0x18006d3bb  call    cs:__imp_CloseThreadpoolWork
0x18006d3c2  nop     dword ptr [rax+rax+00h]
0x18006d3c7  mov     eax, ebx
0x18006d3c9  mov     rcx, [rbp+var_8]
0x18006d3cd  xor     rcx, rsp; StackCookie
0x18006d3d0  call    __security_check_cookie
0x18006d3d5  mov     rbx, [rsp+80h+arg_18]
0x18006d3dd  add     rsp, 80h
0x18006d3e4  pop     r15
0x18006d3e6  pop     r14
0x18006d3e8  pop     r13
0x18006d3ea  pop     r12
0x18006d3ec  pop     rdi
0x18006d3ed  pop     rsi
0x18006d3ee  pop     rbp
0x18006d3ef  retn
```
