# CSpWmiMethod<_SPACES_VirtualDisk_Repair>::RunMethod<CSpVirtualDisk::Repair,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800def64`
- end: `0x1800df2b2`
- name: `??$RunMethod@VRepair@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_Repair@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x1800e4700`

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
- `0x1800def64`
- `0x1800e0aac`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df130`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df130`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800df111`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800df111`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800df126`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800df126`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800df0f7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800df0f7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800df1d0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800df1d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800df283`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800df283`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800df275`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800df275`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_Repair>::RunMethod<CSpVirtualDisk::Repair,16>(
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
  CSpVirtualDisk::Repair *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::Repair *)operator new(0x170u);
  v7 = CSpVirtualDisk::Repair::Repair(v25);
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
      v25 = (CSpVirtualDisk::Repair *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_1803302D5,
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
0x1800def64  mov     [rsp-38h+arg_18], rbx
0x1800def69  push    rbp
0x1800def6a  push    rsi
0x1800def6b  push    rdi
0x1800def6c  push    r12
0x1800def6e  push    r13
0x1800def70  push    r14
0x1800def72  push    r15
0x1800def74  mov     rbp, rsp
0x1800def77  sub     rsp, 80h
0x1800def7e  mov     rax, cs:__security_cookie
0x1800def85  xor     rax, rsp
0x1800def88  mov     [rbp+var_8], rax
0x1800def8c  xor     eax, eax
0x1800def8e  mov     rsi, rcx
0x1800def91  xorps   xmm0, xmm0
0x1800def94  mov     [rbp+var_10], eax
0x1800def97  mov     ecx, 170h; Size
0x1800def9c  mov     [rbp+var_40], eax
0x1800def9f  movups  [rbp+var_20], xmm0
0x1800defa3  mov     [rbp+TokenHandle], rax
0x1800defa7  mov     r12, r8
0x1800defaa  mov     r13, rdx
0x1800defad  xor     r14d, r14d
0x1800defb0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800defb5  mov     rcx, rax; this
0x1800defb8  mov     [rbp+var_28], rax
0x1800defbc  call    ??0Repair@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::Repair::Repair(void)
0x1800defc1  mov     rdi, rax
0x1800defc4  test    rax, rax
0x1800defc7  jnz     short loc_1800DEFD1
0x1800defc9  lea     ebx, [rax+1Bh]
0x1800defcc  jmp     loc_1800DF26C
0x1800defd1  mov     rax, [rax]
0x1800defd4  mov     rdx, rsi
0x1800defd7  mov     rcx, rdi
0x1800defda  xor     r15d, r15d
0x1800defdd  mov     rax, [rax+8]
0x1800defe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800defe6  lea     rcx, [rbp+var_40]
0x1800defea  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800defef  mov     [rdi+1Ch], eax
0x1800deff2  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800deff6  mov     ecx, [rsi+14h]; unsigned int
0x1800deff9  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800deffe  mov     eax, cs:dword_180397B68
0x1800df004  cmp     eax, 5
0x1800df007  jbe     short loc_1800DF077
0x1800df009  mov     rdx, 400000000000h
0x1800df013  lea     rcx, dword_180397B68
0x1800df01a  call    _tlgKeywordOn
0x1800df01f  test    al, al
0x1800df021  jz      short loc_1800DF077
0x1800df023  mov     eax, [rbp+var_40]
0x1800df026  lea     rdx, byte_1803302D5
0x1800df02d  xor     ecx, ecx
0x1800df02f  cmp     [rdi+1Ch], eax
0x1800df032  movzx   eax, word ptr [rbp+var_10]
0x1800df036  mov     word ptr [rbp+var_40], ax
0x1800df03a  setnz   cl
0x1800df03d  mov     eax, [rsi+14h]
0x1800df040  mov     [rbp+var_38], eax
0x1800df043  lea     rax, [rbp+var_20]
0x1800df047  mov     [rbp+var_28], rax
0x1800df04b  lea     rax, [rbp+var_3C]
0x1800df04f  mov     [rsp+80h+var_48], rax
0x1800df054  lea     rax, [rbp+var_40]
0x1800df058  mov     [rsp+80h+var_50], rax
0x1800df05d  lea     rax, [rbp+var_38]
0x1800df061  mov     [rsp+80h+var_58], rax
0x1800df066  lea     rax, [rbp+var_28]
0x1800df06a  mov     [rsp+80h+var_60], rax
0x1800df06f  mov     [rbp+var_3C], ecx
0x1800df072  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800df077  mov     rcx, [rsi]
0x1800df07a  test    rcx, rcx
0x1800df07d  jz      loc_1800DF242
0x1800df083  mov     rax, [rcx]
0x1800df086  test    rax, rax
0x1800df089  jz      loc_1800DF242
0x1800df08f  mov     rax, [rax+18h]
0x1800df093  lea     r8, [rdi+20h]
0x1800df097  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800df09e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df0a3  mov     ebx, eax
0x1800df0a5  test    eax, eax
0x1800df0a7  jnz     loc_1800DF247
0x1800df0ad  cmp     [rsi+10h], r14d
0x1800df0b1  jz      loc_1800DF1DB
0x1800df0b7  lea     rbx, [rdi+148h]
0x1800df0be  mov     rcx, rbx
0x1800df0c1  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800df0c6  mov     rcx, rbx; struct CSpJobMgr **
0x1800df0c9  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800df0ce  test    eax, eax
0x1800df0d0  jnz     short loc_1800DF0DA
0x1800df0d2  lea     ebx, [rax+1Ch]
0x1800df0d5  jmp     loc_1800DF247
0x1800df0da  mov     ecx, 10h; Size
0x1800df0df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800df0e4  xor     r8d, r8d; pcbe
0x1800df0e7  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800df0ee  mov     rdx, rax; pv
0x1800df0f1  mov     r15, rax
0x1800df0f4  mov     [rax], rdi
0x1800df0f7  call    cs:__imp_CreateThreadpoolWork
0x1800df0fd  mov     r14, rax
0x1800df100  test    rax, rax
0x1800df103  jnz     short loc_1800DF111
0x1800df105  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800df10a  mov     ebx, eax
0x1800df10c  jmp     loc_1800DF247
0x1800df111  call    cs:__imp_GetCurrentThread
0x1800df117  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800df11b  xor     r8d, r8d; OpenAsSelf
0x1800df11e  mov     rcx, rax; ThreadHandle
0x1800df121  mov     edx, 2000Ch; DesiredAccess
0x1800df126  call    cs:__imp_OpenThreadToken
0x1800df12c  test    eax, eax
0x1800df12e  jnz     short loc_1800DF13D
0x1800df130  call    cs:__imp_GetLastError
0x1800df136  cmp     eax, 3F0h
0x1800df13b  jnz     short loc_1800DF105
0x1800df13d  mov     rax, [rbp+TokenHandle]
0x1800df141  mov     r8, r13
0x1800df144  mov     [r15+8], rax
0x1800df148  mov     rcx, rdi
0x1800df14b  mov     rax, [rdi]
0x1800df14e  mov     rdx, [rsi+8]
0x1800df152  mov     rax, [rax+18h]
0x1800df156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df15b  mov     rax, [rdi]
0x1800df15e  mov     rdx, r12
0x1800df161  mov     rcx, rdi
0x1800df164  mov     rax, [rax+28h]
0x1800df168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df16d  mov     ebx, eax
0x1800df16f  test    eax, eax
0x1800df171  jz      short loc_1800DF17C
0x1800df173  cmp     eax, 7
0x1800df176  jnz     loc_1800DF247
0x1800df17c  mov     rax, [rdi]
0x1800df17f  mov     rdx, r12
0x1800df182  mov     rcx, rdi
0x1800df185  mov     rax, [rax+38h]
0x1800df189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df18e  mov     ebx, eax
0x1800df190  test    eax, eax
0x1800df192  jnz     loc_1800DF247
0x1800df198  mov     rax, [rdi+150h]
0x1800df19f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800df1a6  jnz     short loc_1800DF1BC
0x1800df1a8  mov     rax, [rdi+158h]
0x1800df1af  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800df1b6  jz      loc_1800DF247
0x1800df1bc  mov     rdx, r12
0x1800df1bf  mov     rcx, rdi
0x1800df1c2  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800df1c7  mov     ebx, eax
0x1800df1c9  test    eax, eax
0x1800df1cb  jnz     short loc_1800DF247
0x1800df1cd  mov     rcx, r14; pwk
0x1800df1d0  call    cs:__imp_SubmitThreadpoolWork
0x1800df1d6  jmp     loc_1800DF289
0x1800df1db  mov     rax, [rdi]
0x1800df1de  mov     r8, r13
0x1800df1e1  mov     rdx, [rsi+8]
0x1800df1e5  mov     rcx, rdi
0x1800df1e8  mov     rax, [rax+10h]
0x1800df1ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df1f1  mov     rax, [rdi]
0x1800df1f4  mov     rdx, r12
0x1800df1f7  mov     rcx, rdi
0x1800df1fa  mov     rax, [rax+30h]
0x1800df1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df203  mov     ebx, eax
0x1800df205  test    eax, eax
0x1800df207  jz      short loc_1800DF20E
0x1800df209  cmp     eax, 7
0x1800df20c  jnz     short loc_1800DF247
0x1800df20e  mov     rax, [rdi]
0x1800df211  mov     rdx, r12
0x1800df214  mov     rcx, rdi
0x1800df217  mov     rax, [rax+28h]
0x1800df21b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df220  mov     ebx, eax
0x1800df222  test    eax, eax
0x1800df224  jz      short loc_1800DF22B
0x1800df226  cmp     eax, 7
0x1800df229  jnz     short loc_1800DF247
0x1800df22b  mov     rax, [rdi]
0x1800df22e  mov     rdx, r12
0x1800df231  mov     rcx, rdi
0x1800df234  mov     rax, [rax+38h]
0x1800df238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df23d  jmp     loc_1800DF10A
0x1800df242  mov     ebx, 4
0x1800df247  mov     rax, [rdi]
0x1800df24a  mov     edx, 1
0x1800df24f  mov     rcx, rdi
0x1800df252  mov     rax, [rax]
0x1800df255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df25a  test    r15, r15
0x1800df25d  jz      short loc_1800DF26C
0x1800df25f  mov     edx, 10h
0x1800df264  mov     rcx, r15; Block
0x1800df267  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800df26c  mov     rcx, [rbp+TokenHandle]; hObject
0x1800df270  test    rcx, rcx
0x1800df273  jz      short loc_1800DF27B
0x1800df275  call    cs:__imp_CloseHandle
0x1800df27b  test    r14, r14
0x1800df27e  jz      short loc_1800DF289
0x1800df280  mov     rcx, r14; pwk
0x1800df283  call    cs:__imp_CloseThreadpoolWork
0x1800df289  mov     eax, ebx
0x1800df28b  mov     rcx, [rbp+var_8]
0x1800df28f  xor     rcx, rsp; StackCookie
0x1800df292  call    __security_check_cookie
0x1800df297  mov     rbx, [rsp+80h+arg_18]
0x1800df29f  add     rsp, 80h
0x1800df2a6  pop     r15
0x1800df2a8  pop     r14
0x1800df2aa  pop     r13
0x1800df2ac  pop     r12
0x1800df2ae  pop     rdi
0x1800df2af  pop     rsi
0x1800df2b0  pop     rbp
0x1800df2b1  retn
```
