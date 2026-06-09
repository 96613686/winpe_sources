# CQueryCscPropertyInfoTask::_Exec(CCscComTaskContext *)

- ea: `0x18002b5a0`
- end: `0x18002b945`
- name: `?_Exec@CQueryCscPropertyInfoTask@@EEAAJPEAVCCscComTaskContext@@@Z`
- size: `933`
- prototype: `int(CQueryCscPropertyInfoTask *__hidden this, struct CCscComTaskContext *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800272b0`
- `0x180027b90`
- `0x18002b5a0`
- `0x18002bfc0`
- `0x18002c068`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b615`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b615`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18002b642`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18002b642`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18002b671`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18002b671`

## pseudocode

```c
__int64 __fastcall CQueryCscPropertyInfoTask::_Exec(CQueryCscPropertyInfoTask *this, DWORD *a2)
{
  int CscCacheObject; // ebx
  DWORD DueTime; // ebx
  bool v6; // cf
  unsigned int v7; // esi
  DWORD CurrentThreadId; // eax
  CQueryCscPropertyInfoTask *v9; // rcx
  struct IOfflineFilesCache *v10; // r15
  CQueryCscPropertyInfoTask *v11; // rcx
  struct IOfflineFilesItem *v12; // rcx
  struct IOfflineFilesItem *v13; // rcx
  int v14; // eax
  CQueryCscPropertyInfoTask *v15; // rcx
  struct IOfflineFilesItem *v16; // rcx
  struct IOfflineFilesItem *v17; // rcx
  __int64 v18; // rdx
  struct IOfflineFilesItem *v20; // [rsp+40h] [rbp-30h] BYREF
  struct IOfflineFilesCache *v21; // [rsp+48h] [rbp-28h] BYREF
  DWORD Parameter; // [rsp+50h] [rbp-20h] BYREF
  char v23; // [rsp+54h] [rbp-1Ch]
  HRESULT v24; // [rsp+58h] [rbp-18h]
  void *phNewTimer; // [rsp+60h] [rbp-10h] BYREF
  __int64 v26; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v27; // [rsp+B8h] [rbp+48h] BYREF

  v21 = 0;
  CscCacheObject = CCscComTaskContext::GetCscCacheObject(
                     (CCscComTaskContext *)a2,
                     (const struct _GUID *)a2,
                     (void **)&v21);
  if ( CscCacheObject >= 0 )
  {
    DueTime = a2[7];
    v6 = *((_DWORD *)this + 11) != 0;
    v20 = 0;
    v7 = v6 ? 2 : 0;
    if ( DueTime == -1 )
    {
      CscCacheObject = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, _QWORD, _QWORD, struct IOfflineFilesItem **))v21->lpVtbl->FindItem)(
                         v21,
                         *((_QWORD *)this + 2),
                         v7,
                         &v20);
    }
    else
    {
      CurrentThreadId = GetCurrentThreadId();
      v23 = 0;
      Parameter = CurrentThreadId;
      v24 = -2147467259;
      phNewTimer = 0;
      CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&Parameter);
      if ( !DueTime )
        DueTime = 5000;
      v24 = CoEnableCallCancellation(0);
      if ( v24 >= 0 )
        CreateTimerQueueTimer(&phNewTimer, 0, CBaseRPCTimeout::s_Callback, &Parameter, DueTime, 0x3E8u, 0);
      CscCacheObject = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, _QWORD, _QWORD, struct IOfflineFilesItem **))v21->lpVtbl->FindItem)(
                         v21,
                         *((_QWORD *)this + 2),
                         v7,
                         &v20);
      CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&Parameter);
    }
    if ( CscCacheObject < 0 )
    {
      v18 = *((_QWORD *)this + 2);
      LODWORD(v27) = 0;
      LODWORD(v26) = 0;
      *((_DWORD *)this + 17) = ((int (__fastcall *)(struct IOfflineFilesCache *, __int64, __int64 *, __int64 *))v21->lpVtbl->IsPathCacheable)(
                                 v21,
                                 v18,
                                 &v27,
                                 &v26) >= 0;
    }
    else
    {
      if ( !*((_DWORD *)this + 11) )
        goto LABEL_17;
      v26 = 0;
      CscCacheObject = ((__int64 (__fastcall *)(struct IOfflineFilesItem *, GUID *, __int64 *))v20->lpVtbl->QueryInterface)(
                         v20,
                         &GUID_efb23a09_a867_4be8_83a6_86969a7d0856,
                         &v26);
      if ( CscCacheObject >= 0 )
      {
        CscCacheObject = (*(__int64 (__fastcall **)(__int64, char *, char *))(*(_QWORD *)v26 + 24LL))(
                           v26,
                           (char *)this + 36,
                           (char *)this + 40);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        if ( CscCacheObject >= 0 )
        {
          v10 = v21;
          *((_DWORD *)this + 15) = 0;
          *((_DWORD *)this + 16) = 0;
          CscCacheObject = CQueryCscPropertyInfoTask::_IsSettingEnabled(
                             v9,
                             v10,
                             L"BackgroundSyncEnabled",
                             (int *)this + 15);
          if ( CscCacheObject >= 0 && *((_DWORD *)this + 15) )
            CscCacheObject = CQueryCscPropertyInfoTask::_IsSettingEnabled(
                               v11,
                               v10,
                               L"BackgroundSyncEnabledForForcedOffline",
                               (int *)this + 16);
          if ( CscCacheObject >= 0 )
          {
LABEL_17:
            v12 = v20;
            *((_DWORD *)this + 8) = 0;
            v26 = 0;
            CscCacheObject = ((__int64 (__fastcall *)(struct IOfflineFilesItem *, GUID *, __int64 *))v12->lpVtbl->QueryInterface)(
                               v12,
                               &GUID_bcaf4a01_5b68_4b56_a6a1_8d2786ede8e3,
                               &v26);
            if ( CscCacheObject >= 0 )
            {
              CscCacheObject = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v26 + 24LL))(
                                 v26,
                                 (char *)this + 32);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
            }
            if ( CscCacheObject >= 0 )
            {
              v13 = v20;
              *((_DWORD *)this + 6) = 0;
              v26 = 0;
              v14 = ((__int64 (__fastcall *)(struct IOfflineFilesItem *, GUID *, __int64 *))v13->lpVtbl->QueryInterface)(
                      v13,
                      &GUID_8dfadead_26c2_4eff_8a72_6b50723d9a00,
                      &v26);
              CscCacheObject = v14;
              if ( v14 == -2147467262 )
                goto LABEL_24;
              if ( v14 >= 0 )
              {
                CscCacheObject = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v26 + 64LL))(
                                   v26,
                                   (char *)this + 24);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
              }
              if ( CscCacheObject >= 0 )
              {
LABEL_24:
                CscCacheObject = CQueryCscPropertyInfoTask::_IsItemPinned(v15, v20, (int *)this + 7, (int *)this + 13);
                if ( CscCacheObject >= 0 )
                {
                  v16 = v20;
                  *((_DWORD *)this + 12) = 0;
                  v26 = 0;
                  CscCacheObject = ((__int64 (__fastcall *)(struct IOfflineFilesItem *, GUID *, __int64 *))v16->lpVtbl->QueryInterface)(
                                     v16,
                                     &GUID_2b09d48c_8ab5_464f_a755_a59d92f99429,
                                     &v26);
                  if ( CscCacheObject >= 0 )
                  {
                    CscCacheObject = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v26 + 24LL))(
                                       v26,
                                       (char *)this + 48);
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                  }
                  if ( CscCacheObject >= 0 )
                  {
                    v17 = v20;
                    *((_DWORD *)this + 14) = 0;
                    v27 = 0;
                    LODWORD(v26) = 0;
                    CscCacheObject = ((__int64 (__fastcall *)(struct IOfflineFilesItem *, GUID *, __int64 *))v17->lpVtbl->QueryInterface)(
                                       v17,
                                       &GUID_7bcc43e7_31ce_4ca4_8ccd_1cff2dc494da,
                                       &v27);
                    if ( CscCacheObject >= 0 )
                    {
                      CscCacheObject = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 32LL))(
                                         v27,
                                         &v26);
                      if ( (unsigned int)(v26 - 3) <= 1 )
                        *((_DWORD *)this + 14) = 1;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
                    }
                  }
                }
              }
            }
          }
        }
      }
      ((void (__fastcall *)(struct IOfflineFilesItem *))v20->lpVtbl->Release)(v20);
    }
    ((void (__fastcall *)(struct IOfflineFilesCache *))v21->lpVtbl->Release)(v21);
  }
  return (unsigned int)CscCacheObject;
}

```

## disassembly

```asm
0x18002b5a0  mov     [rsp-28h+arg_0], rbx
0x18002b5a5  mov     [rsp-28h+arg_8], rsi
0x18002b5aa  push    rbp
0x18002b5ab  push    rdi
0x18002b5ac  push    r12
0x18002b5ae  push    r14
0x18002b5b0  push    r15
0x18002b5b2  mov     rbp, rsp
0x18002b5b5  sub     rsp, 70h
0x18002b5b9  mov     rdi, rcx
0x18002b5bc  lea     r8, [rbp+var_28]; void **
0x18002b5c0  xor     r12d, r12d
0x18002b5c3  mov     rcx, rdx; this
0x18002b5c6  mov     [rbp+var_28], r12
0x18002b5ca  mov     r14, rdx
0x18002b5cd  call    ?GetCscCacheObject@CCscComTaskContext@@QEAAJAEBU_GUID@@PEAPEAX@Z; CCscComTaskContext::GetCscCacheObject(_GUID const &,void * *)
0x18002b5d2  mov     ebx, eax
0x18002b5d4  test    eax, eax
0x18002b5d6  js      loc_18002B92A
0x18002b5dc  mov     eax, [rdi+2Ch]
0x18002b5df  mov     ebx, [r14+1Ch]
0x18002b5e3  neg     eax
0x18002b5e5  mov     [rbp+var_30], r12
0x18002b5e9  sbb     esi, esi
0x18002b5eb  and     esi, 2
0x18002b5ee  cmp     ebx, 0FFFFFFFFh
0x18002b5f1  jnz     short loc_18002B615
0x18002b5f3  mov     rcx, [rbp+var_28]
0x18002b5f7  lea     r9, [rbp+var_30]
0x18002b5fb  mov     rdx, [rdi+10h]
0x18002b5ff  mov     r8d, esi
0x18002b602  mov     rax, [rcx]
0x18002b605  mov     rax, [rax+50h]
0x18002b609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b60e  mov     ebx, eax
0x18002b610  jmp     loc_18002B69D
0x18002b615  call    cs:__imp_GetCurrentThreadId
0x18002b61b  lea     rcx, [rbp+Parameter]; this
0x18002b61f  mov     [rbp+var_1C], r12b
0x18002b623  mov     [rbp+Parameter], eax
0x18002b626  mov     [rbp+var_18], 80004005h
0x18002b62d  mov     [rbp+phNewTimer], r12
0x18002b631  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x18002b636  mov     eax, 1388h
0x18002b63b  test    ebx, ebx
0x18002b63d  cmovz   ebx, eax
0x18002b640  xor     ecx, ecx; pReserved
0x18002b642  call    cs:__imp_CoEnableCallCancellation
0x18002b648  mov     [rbp+var_18], eax
0x18002b64b  test    eax, eax
0x18002b64d  js      short loc_18002B677
0x18002b64f  mov     [rsp+70h+Flags], r12d; Flags
0x18002b654  lea     r9, [rbp+Parameter]; Parameter
0x18002b658  mov     [rsp+70h+Period], 3E8h; Period
0x18002b660  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x18002b667  xor     edx, edx; TimerQueue
0x18002b669  mov     [rsp+70h+DueTime], ebx; DueTime
0x18002b66d  lea     rcx, [rbp+phNewTimer]; phNewTimer
0x18002b671  call    cs:__imp_CreateTimerQueueTimer
0x18002b677  mov     rcx, [rbp+var_28]
0x18002b67b  lea     r9, [rbp+var_30]
0x18002b67f  mov     rdx, [rdi+10h]
0x18002b683  mov     r8d, esi
0x18002b686  mov     rax, [rcx]
0x18002b689  mov     rax, [rax+50h]
0x18002b68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b692  lea     rcx, [rbp+Parameter]; this
0x18002b696  mov     ebx, eax
0x18002b698  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x18002b69d  test    ebx, ebx
0x18002b69f  js      loc_18002B8E8
0x18002b6a5  cmp     [rdi+2Ch], r12d
0x18002b6a9  jz      loc_18002B752
0x18002b6af  mov     rcx, [rbp+var_30]
0x18002b6b3  lea     r8, [rbp+arg_10]
0x18002b6b7  lea     rdx, _GUID_efb23a09_a867_4be8_83a6_86969a7d0856
0x18002b6be  mov     [rbp+arg_10], r12
0x18002b6c2  mov     rax, [rcx]
0x18002b6c5  mov     rax, [rax]
0x18002b6c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6cd  mov     ebx, eax
0x18002b6cf  test    eax, eax
0x18002b6d1  js      loc_18002B8D6
0x18002b6d7  mov     rcx, [rbp+arg_10]
0x18002b6db  lea     r8, [rdi+28h]
0x18002b6df  lea     rdx, [rdi+24h]
0x18002b6e3  mov     rax, [rcx]
0x18002b6e6  mov     rax, [rax+18h]
0x18002b6ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6ef  mov     rcx, [rbp+arg_10]
0x18002b6f3  mov     ebx, eax
0x18002b6f5  mov     rax, [rcx]
0x18002b6f8  mov     rax, [rax+10h]
0x18002b6fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b701  test    ebx, ebx
0x18002b703  js      loc_18002B8D6
0x18002b709  mov     r15, [rbp+var_28]
0x18002b70d  lea     rsi, [rdi+3Ch]
0x18002b711  mov     [rsi], r12d
0x18002b714  lea     r8, aBackgroundsync_3; "BackgroundSyncEnabled"
0x18002b71b  mov     r9, rsi; int *
0x18002b71e  mov     [rdi+40h], r12d
0x18002b722  mov     rdx, r15; struct IOfflineFilesCache *
0x18002b725  call    ?_IsSettingEnabled@CQueryCscPropertyInfoTask@@AEAAJPEAUIOfflineFilesCache@@PEBGPEAH@Z; CQueryCscPropertyInfoTask::_IsSettingEnabled(IOfflineFilesCache *,ushort const *,int *)
0x18002b72a  mov     ebx, eax
0x18002b72c  test    eax, eax
0x18002b72e  js      short loc_18002B74A
0x18002b730  cmp     [rsi], r12d
0x18002b733  jz      short loc_18002B74A
0x18002b735  lea     r9, [rdi+40h]; int *
0x18002b739  mov     rdx, r15; struct IOfflineFilesCache *
0x18002b73c  lea     r8, aBackgroundsync_4; "BackgroundSyncEnabledForForcedOffline"
0x18002b743  call    ?_IsSettingEnabled@CQueryCscPropertyInfoTask@@AEAAJPEAUIOfflineFilesCache@@PEBGPEAH@Z; CQueryCscPropertyInfoTask::_IsSettingEnabled(IOfflineFilesCache *,ushort const *,int *)
0x18002b748  mov     ebx, eax
0x18002b74a  test    ebx, ebx
0x18002b74c  js      loc_18002B8D6
0x18002b752  mov     rcx, [rbp+var_30]
0x18002b756  lea     r8, [rbp+arg_10]
0x18002b75a  mov     [rdi+20h], r12d
0x18002b75e  lea     rdx, _GUID_bcaf4a01_5b68_4b56_a6a1_8d2786ede8e3
0x18002b765  mov     [rbp+arg_10], r12
0x18002b769  mov     rax, [rcx]
0x18002b76c  mov     rax, [rax]
0x18002b76f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b774  mov     ebx, eax
0x18002b776  test    eax, eax
0x18002b778  js      short loc_18002B7A0
0x18002b77a  mov     rcx, [rbp+arg_10]
0x18002b77e  lea     rdx, [rdi+20h]
0x18002b782  mov     rax, [rcx]
0x18002b785  mov     rax, [rax+18h]
0x18002b789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b78e  mov     rcx, [rbp+arg_10]
0x18002b792  mov     ebx, eax
0x18002b794  mov     rax, [rcx]
0x18002b797  mov     rax, [rax+10h]
0x18002b79b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7a0  test    ebx, ebx
0x18002b7a2  js      loc_18002B8D6
0x18002b7a8  mov     rcx, [rbp+var_30]
0x18002b7ac  lea     r8, [rbp+arg_10]
0x18002b7b0  mov     [rdi+18h], r12d
0x18002b7b4  lea     rdx, _GUID_8dfadead_26c2_4eff_8a72_6b50723d9a00
0x18002b7bb  mov     [rbp+arg_10], r12
0x18002b7bf  mov     rax, [rcx]
0x18002b7c2  mov     rax, [rax]
0x18002b7c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7ca  mov     ebx, eax
0x18002b7cc  cmp     eax, 80004002h
0x18002b7d1  jz      short loc_18002B805
0x18002b7d3  test    eax, eax
0x18002b7d5  js      short loc_18002B7FD
0x18002b7d7  mov     rcx, [rbp+arg_10]
0x18002b7db  lea     rdx, [rdi+18h]
0x18002b7df  mov     rax, [rcx]
0x18002b7e2  mov     rax, [rax+40h]
0x18002b7e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7eb  mov     rcx, [rbp+arg_10]
0x18002b7ef  mov     ebx, eax
0x18002b7f1  mov     rax, [rcx]
0x18002b7f4  mov     rax, [rax+10h]
0x18002b7f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7fd  test    ebx, ebx
0x18002b7ff  js      loc_18002B8D6
0x18002b805  mov     rdx, [rbp+var_30]; struct IOfflineFilesItem *
0x18002b809  lea     r9, [rdi+34h]; int *
0x18002b80d  lea     r8, [rdi+1Ch]; int *
0x18002b811  call    ?_IsItemPinned@CQueryCscPropertyInfoTask@@AEAAJPEAUIOfflineFilesItem@@PEAH1@Z; CQueryCscPropertyInfoTask::_IsItemPinned(IOfflineFilesItem *,int *,int *)
0x18002b816  mov     ebx, eax
0x18002b818  test    eax, eax
0x18002b81a  js      loc_18002B8D6
0x18002b820  mov     rcx, [rbp+var_30]
0x18002b824  lea     r8, [rbp+arg_10]
0x18002b828  mov     [rdi+30h], r12d
0x18002b82c  lea     rdx, _GUID_2b09d48c_8ab5_464f_a755_a59d92f99429
0x18002b833  mov     [rbp+arg_10], r12
0x18002b837  mov     rax, [rcx]
0x18002b83a  mov     rax, [rax]
0x18002b83d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b842  mov     ebx, eax
0x18002b844  test    eax, eax
0x18002b846  js      short loc_18002B86E
0x18002b848  mov     rcx, [rbp+arg_10]
0x18002b84c  lea     rdx, [rdi+30h]
0x18002b850  mov     rax, [rcx]
0x18002b853  mov     rax, [rax+18h]
0x18002b857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b85c  mov     rcx, [rbp+arg_10]
0x18002b860  mov     ebx, eax
0x18002b862  mov     rax, [rcx]
0x18002b865  mov     rax, [rax+10h]
0x18002b869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b86e  test    ebx, ebx
0x18002b870  js      short loc_18002B8D6
0x18002b872  mov     rcx, [rbp+var_30]
0x18002b876  lea     r8, [rbp+arg_18]
0x18002b87a  mov     [rdi+38h], r12d
0x18002b87e  lea     rdx, _GUID_7bcc43e7_31ce_4ca4_8ccd_1cff2dc494da
0x18002b885  mov     [rbp+arg_18], r12
0x18002b889  mov     dword ptr [rbp+arg_10], r12d
0x18002b88d  mov     rax, [rcx]
0x18002b890  mov     rax, [rax]
0x18002b893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b898  mov     ebx, eax
0x18002b89a  test    eax, eax
0x18002b89c  js      short loc_18002B8D6
0x18002b89e  mov     rcx, [rbp+arg_18]
0x18002b8a2  lea     rdx, [rbp+arg_10]
0x18002b8a6  mov     rax, [rcx]
0x18002b8a9  mov     rax, [rax+20h]
0x18002b8ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8b2  mov     ebx, eax
0x18002b8b4  mov     eax, dword ptr [rbp+arg_10]
0x18002b8b7  add     eax, 0FFFFFFFDh
0x18002b8ba  cmp     eax, 1
0x18002b8bd  ja      short loc_18002B8C6
0x18002b8bf  mov     dword ptr [rdi+38h], 1
0x18002b8c6  mov     rcx, [rbp+arg_18]
0x18002b8ca  mov     rax, [rcx]
0x18002b8cd  mov     rax, [rax+10h]
0x18002b8d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8d6  mov     rcx, [rbp+var_30]
0x18002b8da  mov     rax, [rcx]
0x18002b8dd  mov     rax, [rax+10h]
0x18002b8e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8e6  jmp     short loc_18002B91A
0x18002b8e8  mov     rcx, [rbp+var_28]
0x18002b8ec  lea     r9, [rbp+arg_10]
0x18002b8f0  mov     rdx, [rdi+10h]
0x18002b8f4  lea     r8, [rbp+arg_18]
0x18002b8f8  mov     dword ptr [rbp+arg_18], r12d
0x18002b8fc  mov     dword ptr [rbp+arg_10], r12d
0x18002b900  mov     rax, [rcx]
0x18002b903  mov     rax, [rax+98h]
0x18002b90a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b90f  mov     ecx, r12d
0x18002b912  test    eax, eax
0x18002b914  setns   cl
0x18002b917  mov     [rdi+44h], ecx
0x18002b91a  mov     rcx, [rbp+var_28]
0x18002b91e  mov     rax, [rcx]
0x18002b921  mov     rax, [rax+10h]
0x18002b925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b92a  lea     r11, [rsp+70h+var_s0]
0x18002b92f  mov     eax, ebx
0x18002b931  mov     rbx, [r11+30h]
0x18002b935  mov     rsi, [r11+38h]
0x18002b939  mov     rsp, r11
0x18002b93c  pop     r15
0x18002b93e  pop     r14
0x18002b940  pop     r12
0x18002b942  pop     rdi
0x18002b943  pop     rbp
0x18002b944  retn
```
