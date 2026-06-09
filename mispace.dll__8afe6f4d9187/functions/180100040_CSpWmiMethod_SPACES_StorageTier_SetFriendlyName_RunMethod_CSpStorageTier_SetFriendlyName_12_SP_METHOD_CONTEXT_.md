# CSpWmiMethod<_SPACES_StorageTier_SetFriendlyName>::RunMethod<CSpStorageTier::SetFriendlyName,12>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x180100040`
- end: `0x18010038e`
- name: `??$RunMethod@VSetFriendlyName@CSpStorageTier@@$0M@@?$CSpWmiMethod@U_SPACES_StorageTier_SetFriendlyName@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180102030`

## callees

- `0x1800014ec`
- `0x180001970`
- `0x180006290`
- `0x1800062e0`
- `0x1800062ec`
- `0x18000c704`
- `0x180013898`
- `0x180014000`
- `0x180014720`
- `0x180024dfc`
- `0x18005d58c`
- `0x180100040`
- `0x1801006a0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010020c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010020c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801001ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801001ed`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180100202`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180100202`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801001d3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801001d3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801002ac`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801002ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18010035f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18010035f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180100351`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180100351`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageTier_SetFriendlyName>::RunMethod<CSpStorageTier::SetFriendlyName,12>(
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
  CSpStorageTier::SetFriendlyName *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageTier::SetFriendlyName *)operator new(0x160u);
  v7 = CSpStorageTier::SetFriendlyName::SetFriendlyName(v25);
  v8 = v7;
  if ( v7 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 8LL))(v7, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStorageTier::SetFriendlyName *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_18033A5EE,
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
0x180100040  mov     [rsp-38h+arg_18], rbx
0x180100045  push    rbp
0x180100046  push    rsi
0x180100047  push    rdi
0x180100048  push    r12
0x18010004a  push    r13
0x18010004c  push    r14
0x18010004e  push    r15
0x180100050  mov     rbp, rsp
0x180100053  sub     rsp, 80h
0x18010005a  mov     rax, cs:__security_cookie
0x180100061  xor     rax, rsp
0x180100064  mov     [rbp+var_8], rax
0x180100068  xor     eax, eax
0x18010006a  mov     rsi, rcx
0x18010006d  xorps   xmm0, xmm0
0x180100070  mov     [rbp+var_10], eax
0x180100073  mov     ecx, 160h; Size
0x180100078  mov     [rbp+var_40], eax
0x18010007b  movups  [rbp+var_20], xmm0
0x18010007f  mov     [rbp+TokenHandle], rax
0x180100083  mov     r12, r8
0x180100086  mov     r13, rdx
0x180100089  xor     r14d, r14d
0x18010008c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180100091  mov     rcx, rax; this
0x180100094  mov     [rbp+var_28], rax
0x180100098  call    ??0SetFriendlyName@CSpStorageTier@@QEAA@XZ; CSpStorageTier::SetFriendlyName::SetFriendlyName(void)
0x18010009d  mov     rdi, rax
0x1801000a0  test    rax, rax
0x1801000a3  jnz     short loc_1801000AD
0x1801000a5  lea     ebx, [rax+1Bh]
0x1801000a8  jmp     loc_180100348
0x1801000ad  mov     rax, [rax]
0x1801000b0  mov     rdx, rsi
0x1801000b3  mov     rcx, rdi
0x1801000b6  xor     r15d, r15d
0x1801000b9  mov     rax, [rax+8]
0x1801000bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801000c2  lea     rcx, [rbp+var_40]
0x1801000c6  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1801000cb  mov     [rdi+1Ch], eax
0x1801000ce  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1801000d2  mov     ecx, [rsi+14h]; unsigned int
0x1801000d5  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1801000da  mov     eax, cs:dword_180397B68
0x1801000e0  cmp     eax, 5
0x1801000e3  jbe     short loc_180100153
0x1801000e5  mov     rdx, 400000000000h
0x1801000ef  lea     rcx, dword_180397B68
0x1801000f6  call    _tlgKeywordOn
0x1801000fb  test    al, al
0x1801000fd  jz      short loc_180100153
0x1801000ff  mov     eax, [rbp+var_40]
0x180100102  lea     rdx, word_18033A5EE
0x180100109  xor     ecx, ecx
0x18010010b  cmp     [rdi+1Ch], eax
0x18010010e  movzx   eax, word ptr [rbp+var_10]
0x180100112  mov     word ptr [rbp+var_40], ax
0x180100116  setnz   cl
0x180100119  mov     eax, [rsi+14h]
0x18010011c  mov     [rbp+var_38], eax
0x18010011f  lea     rax, [rbp+var_20]
0x180100123  mov     [rbp+var_28], rax
0x180100127  lea     rax, [rbp+var_3C]
0x18010012b  mov     [rsp+80h+var_48], rax
0x180100130  lea     rax, [rbp+var_40]
0x180100134  mov     [rsp+80h+var_50], rax
0x180100139  lea     rax, [rbp+var_38]
0x18010013d  mov     [rsp+80h+var_58], rax
0x180100142  lea     rax, [rbp+var_28]
0x180100146  mov     [rsp+80h+var_60], rax
0x18010014b  mov     [rbp+var_3C], ecx
0x18010014e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x180100153  mov     rcx, [rsi]
0x180100156  test    rcx, rcx
0x180100159  jz      loc_18010031E
0x18010015f  mov     rax, [rcx]
0x180100162  test    rax, rax
0x180100165  jz      loc_18010031E
0x18010016b  mov     rax, [rax+18h]
0x18010016f  lea     r8, [rdi+20h]
0x180100173  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18010017a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010017f  mov     ebx, eax
0x180100181  test    eax, eax
0x180100183  jnz     loc_180100323
0x180100189  cmp     [rsi+10h], r14d
0x18010018d  jz      loc_1801002B7
0x180100193  lea     rbx, [rdi+148h]
0x18010019a  mov     rcx, rbx
0x18010019d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1801001a2  mov     rcx, rbx; struct CSpJobMgr **
0x1801001a5  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1801001aa  test    eax, eax
0x1801001ac  jnz     short loc_1801001B6
0x1801001ae  lea     ebx, [rax+1Ch]
0x1801001b1  jmp     loc_180100323
0x1801001b6  mov     ecx, 10h; Size
0x1801001bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801001c0  xor     r8d, r8d; pcbe
0x1801001c3  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1801001ca  mov     rdx, rax; pv
0x1801001cd  mov     r15, rax
0x1801001d0  mov     [rax], rdi
0x1801001d3  call    cs:__imp_CreateThreadpoolWork
0x1801001d9  mov     r14, rax
0x1801001dc  test    rax, rax
0x1801001df  jnz     short loc_1801001ED
0x1801001e1  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1801001e6  mov     ebx, eax
0x1801001e8  jmp     loc_180100323
0x1801001ed  call    cs:__imp_GetCurrentThread
0x1801001f3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1801001f7  xor     r8d, r8d; OpenAsSelf
0x1801001fa  mov     rcx, rax; ThreadHandle
0x1801001fd  mov     edx, 2000Ch; DesiredAccess
0x180100202  call    cs:__imp_OpenThreadToken
0x180100208  test    eax, eax
0x18010020a  jnz     short loc_180100219
0x18010020c  call    cs:__imp_GetLastError
0x180100212  cmp     eax, 3F0h
0x180100217  jnz     short loc_1801001E1
0x180100219  mov     rax, [rbp+TokenHandle]
0x18010021d  mov     r8, r13
0x180100220  mov     [r15+8], rax
0x180100224  mov     rcx, rdi
0x180100227  mov     rax, [rdi]
0x18010022a  mov     rdx, [rsi+8]
0x18010022e  mov     rax, [rax+18h]
0x180100232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100237  mov     rax, [rdi]
0x18010023a  mov     rdx, r12
0x18010023d  mov     rcx, rdi
0x180100240  mov     rax, [rax+28h]
0x180100244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100249  mov     ebx, eax
0x18010024b  test    eax, eax
0x18010024d  jz      short loc_180100258
0x18010024f  cmp     eax, 7
0x180100252  jnz     loc_180100323
0x180100258  mov     rax, [rdi]
0x18010025b  mov     rdx, r12
0x18010025e  mov     rcx, rdi
0x180100261  mov     rax, [rax+38h]
0x180100265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010026a  mov     ebx, eax
0x18010026c  test    eax, eax
0x18010026e  jnz     loc_180100323
0x180100274  mov     rax, [rdi+150h]
0x18010027b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180100282  jnz     short loc_180100298
0x180100284  mov     rax, [rdi+158h]
0x18010028b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180100292  jz      loc_180100323
0x180100298  mov     rdx, r12
0x18010029b  mov     rcx, rdi
0x18010029e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1801002a3  mov     ebx, eax
0x1801002a5  test    eax, eax
0x1801002a7  jnz     short loc_180100323
0x1801002a9  mov     rcx, r14; pwk
0x1801002ac  call    cs:__imp_SubmitThreadpoolWork
0x1801002b2  jmp     loc_180100365
0x1801002b7  mov     rax, [rdi]
0x1801002ba  mov     r8, r13
0x1801002bd  mov     rdx, [rsi+8]
0x1801002c1  mov     rcx, rdi
0x1801002c4  mov     rax, [rax+10h]
0x1801002c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801002cd  mov     rax, [rdi]
0x1801002d0  mov     rdx, r12
0x1801002d3  mov     rcx, rdi
0x1801002d6  mov     rax, [rax+30h]
0x1801002da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801002df  mov     ebx, eax
0x1801002e1  test    eax, eax
0x1801002e3  jz      short loc_1801002EA
0x1801002e5  cmp     eax, 7
0x1801002e8  jnz     short loc_180100323
0x1801002ea  mov     rax, [rdi]
0x1801002ed  mov     rdx, r12
0x1801002f0  mov     rcx, rdi
0x1801002f3  mov     rax, [rax+28h]
0x1801002f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801002fc  mov     ebx, eax
0x1801002fe  test    eax, eax
0x180100300  jz      short loc_180100307
0x180100302  cmp     eax, 7
0x180100305  jnz     short loc_180100323
0x180100307  mov     rax, [rdi]
0x18010030a  mov     rdx, r12
0x18010030d  mov     rcx, rdi
0x180100310  mov     rax, [rax+38h]
0x180100314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100319  jmp     loc_1801001E6
0x18010031e  mov     ebx, 4
0x180100323  mov     rax, [rdi]
0x180100326  mov     edx, 1
0x18010032b  mov     rcx, rdi
0x18010032e  mov     rax, [rax]
0x180100331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100336  test    r15, r15
0x180100339  jz      short loc_180100348
0x18010033b  mov     edx, 10h
0x180100340  mov     rcx, r15; Block
0x180100343  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180100348  mov     rcx, [rbp+TokenHandle]; hObject
0x18010034c  test    rcx, rcx
0x18010034f  jz      short loc_180100357
0x180100351  call    cs:__imp_CloseHandle
0x180100357  test    r14, r14
0x18010035a  jz      short loc_180100365
0x18010035c  mov     rcx, r14; pwk
0x18010035f  call    cs:__imp_CloseThreadpoolWork
0x180100365  mov     eax, ebx
0x180100367  mov     rcx, [rbp+var_8]
0x18010036b  xor     rcx, rsp; StackCookie
0x18010036e  call    __security_check_cookie
0x180100373  mov     rbx, [rsp+80h+arg_18]
0x18010037b  add     rsp, 80h
0x180100382  pop     r15
0x180100384  pop     r14
0x180100386  pop     r13
0x180100388  pop     r12
0x18010038a  pop     rdi
0x18010038b  pop     rsi
0x18010038c  pop     rbp
0x18010038d  retn
```
