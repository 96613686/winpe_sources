# CTokenManager::ProcessDxgkAdapterTokens(uint)

- ea: `0x140009ba0`
- end: `0x14000a62d`
- name: `?ProcessDxgkAdapterTokens@CTokenManager@@IEAAJI@Z`
- size: `2701`
- prototype: `__int64 __fastcall(CTokenManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1400098d0`

## callees

- `0x140008f9c`
- `0x140009064`
- `0x1400094fc`
- `0x1400097f4`
- `0x140009ba0`
- `0x14000a634`
- `0x14000a6cc`
- `0x14000a71c`
- `0x14000aa44`
- `0x14000ae00`
- `0x140011574`
- `0x140012540`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a0d00`
- `0x14037ac34`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140009c00`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140009c00`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140009f0c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a052`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a2cd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140009f0c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a052`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a2cd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009f94`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a0cd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a336`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009f94`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a0cd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a336`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140009d7a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000a3b9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000a458`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000a471`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140009d7a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000a3b9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000a458`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000a471`
- `ntoskrnl!ExAllocatePool2` at `0x140009fb0`
- `ntoskrnl!ExAllocatePool2` at `0x140009fb0`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140009f88`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000a0c1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000a32a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140009f88`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000a0c1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000a32a`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140009f1e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000a064`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000a2df`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140009f1e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000a064`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000a2df`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a188`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a53d`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a55a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a188`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a53d`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a55a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009eb2`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000a29c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009eb2`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000a29c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140009f6c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000a0a5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000a30e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140009f6c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000a0a5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000a30e`
- `ntoskrnl!ObCloseHandle` at `0x14000a179`
- `ntoskrnl!ObCloseHandle` at `0x14000a179`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x14000a00d`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x14000a00d`
- `ntoskrnl!ZwSetEvent` at `0x140009d52`
- `ntoskrnl!ZwSetEvent` at `0x14000a5f8`
- `ntoskrnl!ZwSetEvent` at `0x140009d52`
- `ntoskrnl!ZwSetEvent` at `0x14000a5f8`
- `ntoskrnl!NtClose` at `0x14000a397`
- `ntoskrnl!NtClose` at `0x14000a397`

## pseudocode

```c
__int64 __fastcall CTokenManager::ProcessDxgkAdapterTokens(CTokenManager *this, unsigned int a2)
{
  char v2; // di
  unsigned int v3; // r12d
  char *v4; // r13
  unsigned int v5; // r15d
  struct CLegacyTokenBuffer **v6; // rbx
  struct CLegacyTokenBuffer *v8; // rbx
  int PresentHistoryInternal; // eax
  int v10; // r14d
  int v11; // edx
  _BYTE *v12; // rbx
  unsigned int v13; // edi
  int v14; // r15d
  unsigned int v15; // r12d
  int v16; // eax
  __int64 v17; // rcx
  void *v18; // rcx
  _QWORD *v20; // rcx
  CTokenManager *v21; // rax
  __int64 v22; // rdx
  char *v23; // rax
  char *v24; // r13
  __int64 v25; // rax
  void *v26; // r13
  void *v27; // rcx
  char *v28; // r15
  int v29; // eax
  char *i; // rax
  HANDLE v31; // rax
  char *v32; // rcx
  __int64 Pool2; // rax
  __int64 v34; // rdi
  __int64 v35; // r15
  __int64 v36; // r13
  bool v37; // zf
  __int64 *j; // rax
  char v39; // r13
  HANDLE v40; // rax
  __int64 v41; // rcx
  bool v42; // r8
  struct CToken *v43; // r15
  int v44; // r13d
  CompositionSurfaceObject *v45; // rdi
  char v46; // r13
  CompositionSurfaceObject *v47; // rcx
  __int64 v48; // rdi
  void *v49; // r15
  _QWORD *v50; // rdi
  __int64 v51; // rax
  HANDLE CurrentThreadId; // rax
  char *v53; // rcx
  CTokenManager **v54; // rdx
  __int64 v55; // rdi
  struct DXGGLOBAL *Global; // rax
  _QWORD *v57; // rcx
  __int64 v58; // rdx
  __int64 Win32kImportTable; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  int v62; // eax
  struct FlipManagerTokenObject *v63; // rdx
  void *v64; // rcx
  __int64 v65; // rax
  char v66; // [rsp+30h] [rbp-D0h]
  bool v67; // [rsp+31h] [rbp-CFh] BYREF
  int v68; // [rsp+34h] [rbp-CCh]
  int v69; // [rsp+38h] [rbp-C8h]
  char v70; // [rsp+3Ch] [rbp-C4h]
  LONG v71; // [rsp+40h] [rbp-C0h] BYREF
  LONG PreviousState; // [rsp+44h] [rbp-BCh] BYREF
  PVOID v73; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v74; // [rsp+50h] [rbp-B0h]
  int v75; // [rsp+54h] [rbp-ACh]
  PVOID Object; // [rsp+58h] [rbp-A8h] BYREF
  PVOID v77; // [rsp+60h] [rbp-A0h]
  void *v78; // [rsp+68h] [rbp-98h]
  _DWORD v79[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v80; // [rsp+78h] [rbp-88h]
  _BYTE *v81; // [rsp+80h] [rbp-80h]
  __int64 v82; // [rsp+88h] [rbp-78h]
  HANDLE Handle; // [rsp+90h] [rbp-70h]
  _BYTE Src[2048]; // [rsp+A0h] [rbp-60h] BYREF

  v2 = 1;
  v74 = a2;
  v3 = 640;
  v66 = 1;
  v75 = 640;
  v4 = (char *)this + 88;
  v5 = a2;
  v6 = (struct CLegacyTokenBuffer **)((char *)this + 184);
  do
  {
    ExAcquirePushLockExclusiveEx(v4, 0);
    *((_QWORD *)this + 12) = KeGetCurrentThread();
    if ( !*v6 )
    {
      v20 = (_QWORD *)((char *)this + 160);
      v21 = (CTokenManager *)*((_QWORD *)this + 20);
      if ( v21 == (CTokenManager *)((char *)this + 160) )
      {
        v10 = CLegacyTokenBuffer::Create(v6);
        if ( v10 < 0 )
          goto LABEL_19;
      }
      else
      {
        if ( *((_QWORD **)v21 + 1) != v20 || (v22 = *(_QWORD *)v21, *(CTokenManager **)(*(_QWORD *)v21 + 8LL) != v21) )
LABEL_24:
          __fastfail(3u);
        *v20 = v22;
        *(_QWORD *)(v22 + 8) = v20;
        --*((_DWORD *)this + 44);
        *v6 = v21;
      }
    }
    v8 = *v6;
    if ( v3 > *((_DWORD *)v8 + 526) )
    {
      v73 = 0;
      v10 = CLegacyTokenBuffer::TokenBlock::Create(
              (struct CLegacyTokenBuffer *)((char *)v8 + 16),
              (struct CLegacyTokenBuffer::TokenBlock **)&v73);
      if ( v10 < 0 )
        goto LABEL_107;
      v23 = (char *)v73;
      *((_QWORD *)v8 + 261) = v73;
      *((_QWORD *)v8 + 262) = v23 + 20;
      *((_DWORD *)v8 + 526) = 2048;
    }
    v78 = (void *)*((_QWORD *)v8 + 262);
    v79[1] = *((_DWORD *)v8 + 526);
    v81 = Src;
    v80 = 0;
    v82 = 0;
    v79[0] = v5;
    PresentHistoryInternal = DxgkGetPresentHistoryInternal(v79);
    v10 = PresentHistoryInternal;
    if ( PresentHistoryInternal )
    {
      if ( PresentHistoryInternal != 261 )
      {
        if ( PresentHistoryInternal != -1073741789 )
        {
          v2 = 0;
          v6 = (struct CLegacyTokenBuffer **)((char *)this + 184);
          v66 = 0;
          goto LABEL_19;
        }
        v3 = 640;
        if ( (unsigned int)v80 > 0x280 )
          v3 = v80;
        v10 = 0;
        v75 = v3;
LABEL_107:
        v6 = (struct CLegacyTokenBuffer **)((char *)this + 184);
        goto LABEL_18;
      }
    }
    else
    {
      v66 = 0;
    }
    v11 = 0;
    v12 = Src;
    v13 = 0;
    v68 = 0;
    v14 = 0;
    PreviousState = 0;
    v15 = 0;
    v69 = 0;
    if ( !(_DWORD)v82 )
      goto LABEL_15;
    do
    {
      v16 = *(_DWORD *)v12;
      if ( *(_DWORD *)v12 == 7 )
      {
        v49 = (void *)*((_QWORD *)v12 + 2);
        if ( v49 )
        {
          v73 = 0;
          if ( ObReferenceObjectByHandle(v49, 2u, g_pDxgkCompositionObjectType, 1, &v73, 0) >= 0 )
          {
            v50 = v73;
            if ( (***((unsigned int (__fastcall ****)(_QWORD))v73 + 2))(*((_QWORD *)v73 + 2)) != 2 )
              goto LABEL_110;
            KeEnterCriticalRegion();
            ExAcquirePushLockSharedEx(v50 + 11, 0);
            if ( *((_DWORD *)v50 + 16) == 1 )
            {
              v51 = v50[5];
              v71 = 0;
              (*(void (__fastcall **)(_QWORD *))(v51 + 24))(v50 + 5);
            }
            else
            {
              v71 = -1073741823;
            }
            CurrentThreadId = PsGetCurrentThreadId();
            v53 = (char *)(v50 + 11);
            if ( CurrentThreadId == (HANDLE)v50[12] )
            {
              v50[12] = 0;
              ExReleasePushLockExclusiveEx(v53, 0);
            }
            else
            {
              ExReleasePushLockSharedEx(v53, 0);
            }
            KeLeaveCriticalRegion();
            if ( v71 >= 0 )
            {
              v54 = (CTokenManager **)*((_QWORD *)this + 34);
              if ( *v54 != (CTokenManager *)((char *)this + 264) )
                goto LABEL_24;
              v50[6] = (char *)this + 264;
              v50[7] = v54;
              *v54 = (CTokenManager *)(v50 + 6);
              *((_QWORD *)this + 34) = v50 + 6;
              v55 = v50[15];
              if ( v55 )
              {
                Global = DXGGLOBAL::GetGlobal();
                (*(void (__fastcall **)(__int64))(*((_QWORD *)Global + 38121) + 64LL))(v55);
              }
            }
            else
            {
LABEL_110:
              ObfDereferenceObject(v50);
            }
          }
          NtClose(v49);
LABEL_85:
          v11 = v68;
        }
        v14 = v69;
        goto LABEL_13;
      }
      if ( v16 == 8 )
      {
        Win32kImportTable = DxgkGetWin32kImportTable();
        (*(void (**)(void))(Win32kImportTable + 456))();
        v60 = DxgkGetWin32kImportTable();
        (*(void (__fastcall **)(_QWORD))(v60 + 32))(*((_QWORD *)v12 + 2));
        v61 = DxgkGetWin32kImportTable();
        (*(void (**)(void))(v61 + 496))();
        v11 = v68;
        goto LABEL_13;
      }
      if ( v16 != 2 )
      {
        if ( v16 != 9 )
        {
          v24 = (char *)v78;
          memmove(v78, v12, *((unsigned int *)v12 + 1));
          v25 = *((unsigned int *)v12 + 1);
          v11 = ++v68;
          PreviousState = v25 + v13;
          v78 = &v24[v25];
          goto LABEL_13;
        }
        v62 = *((_DWORD *)v12 + 8);
        v67 = 1;
        if ( (v62 & 4) == 0 )
          goto LABEL_102;
        v63 = (struct FlipManagerTokenObject *)*((_QWORD *)v12 + 2);
        if ( !v63 || (CTokenManager::CompleteFlipManagerToken(this, v63, &v67), v67) )
        {
          v11 = v68;
LABEL_102:
          v69 = ++v14;
          goto LABEL_13;
        }
        goto LABEL_119;
      }
      if ( (*((_DWORD *)v12 + 15) & 0x2000) != 0 && (*((_DWORD *)v12 + 15) & 0xC000) == 0x4000 )
      {
        CTokenManager::CompleteIndependentFlipToken(
          this,
          *((_QWORD *)v12 + 1),
          (const struct _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN *)(v12 + 16),
          v74);
        v11 = v68;
        v69 = ++v14;
        goto LABEL_13;
      }
      v26 = (void *)*((_QWORD *)v12 + 1);
      v27 = (void *)*((_QWORD *)v12 + 8);
      v73 = v26;
      Handle = v27;
      Object = 0;
      if ( ObReferenceObjectByHandle(v27, 2u, g_pDxgkCompositionObjectType, 1, &Object, 0) >= 0 )
      {
        v28 = (char *)Object;
        v77 = Object;
        if ( (***((unsigned int (__fastcall ****)(_QWORD))Object + 2))(*((_QWORD *)Object + 2)) != 1 )
        {
          ObfDereferenceObject(v28);
          v11 = v68;
          v14 = v69;
          goto LABEL_13;
        }
        v29 = *((_DWORD *)v12 + 15);
        v67 = 1;
        v71 = v29 & 0x2000;
        if ( (v29 & 0x42000) == 0x2000 )
        {
          KeEnterCriticalRegion();
          ExAcquirePushLockSharedEx(v28 + 48, 0);
          if ( *((_DWORD *)v28 + 40) )
          {
            for ( i = (char *)*((_QWORD *)v28 + 18); i != v28 + 144; i = *(char **)i )
            {
              if ( *((void **)i - 1) == v26 )
              {
                v67 = (*(__int64 (__fastcall **)(_QWORD *))(*((_QWORD *)i - 3) + 200LL))((_QWORD *)i - 3);
                goto LABEL_37;
              }
            }
          }
          v67 = 0;
LABEL_37:
          v31 = PsGetCurrentThreadId();
          v32 = v28 + 48;
          if ( v31 == *((HANDLE *)v28 + 7) )
          {
            *((_QWORD *)v28 + 7) = 0;
            ExReleasePushLockExclusiveEx(v32, 0);
          }
          else
          {
            ExReleasePushLockSharedEx(v32, 0);
          }
          KeLeaveCriticalRegion();
        }
        Pool2 = ExAllocatePool2(256, 616, 1869892948);
        v34 = Pool2;
        if ( Pool2 )
        {
          *(_DWORD *)(Pool2 + 24) = 6;
          *(_QWORD *)(Pool2 + 56) = v26;
          *(_QWORD *)(Pool2 + 32) = 0;
          *(_DWORD *)(Pool2 + 40) = 0;
          *(_WORD *)(Pool2 + 64) = 0;
          *(_QWORD *)Pool2 = &CToken::`vftable';
          *(_QWORD *)(Pool2 + 96) = 0;
          *(_DWORD *)(Pool2 + 68) = 0;
          *(_QWORD *)(Pool2 + 48) = v28;
          ObReferenceObjectByPointer(v28, 3u, g_pDxgkCompositionObjectType, 0);
          v35 = *(_QWORD *)(v34 + 48);
          *(_QWORD *)(v34 + 104) = 0;
          *(_QWORD *)(v34 + 112) = 0;
          *(_DWORD *)(v34 + 577) = 0;
          *(_QWORD *)(v34 + 592) = 0;
          *(_QWORD *)(v34 + 600) = 0;
          v36 = *(_QWORD *)(v34 + 56);
          *(_QWORD *)v34 = &CFlipToken::`vftable';
          *(_DWORD *)(v34 + 581) = 256;
          KeEnterCriticalRegion();
          ExAcquirePushLockSharedEx(v35 + 48, 0);
          v37 = *(_DWORD *)(v35 + 160) == 0;
          v70 = 0;
          if ( v37 )
          {
            v39 = 0;
          }
          else
          {
            for ( j = *(__int64 **)(v35 + 144); j != (__int64 *)(v35 + 144); j = (__int64 *)*j )
            {
              if ( *(j - 1) == v36 )
              {
                v39 = *((_BYTE *)j + 17);
                goto LABEL_46;
              }
            }
            v39 = v70;
          }
LABEL_46:
          v40 = PsGetCurrentThreadId();
          v41 = v35 + 48;
          if ( v40 == *(HANDLE *)(v35 + 56) )
          {
            *(_QWORD *)(v35 + 56) = 0;
            ExReleasePushLockExclusiveEx(v41, 0);
          }
          else
          {
            ExReleasePushLockSharedEx(v41, 0);
          }
          KeLeaveCriticalRegion();
          v42 = v67;
          v43 = 0;
          *(_QWORD *)(v34 + 164) = 0;
          *(_QWORD *)(v34 + 172) = 0;
          *(_QWORD *)(v34 + 180) = 0;
          *(_QWORD *)(v34 + 188) = 0;
          *(_BYTE *)(v34 + 576) = v39 == 0;
          *(_QWORD *)(v34 + 204) = 1065353216;
          *(_DWORD *)(v34 + 212) = 0;
          *(_QWORD *)(v34 + 216) = 1065353216;
          *(_DWORD *)(v34 + 224) = 0;
          *(_QWORD *)(v34 + 136) = 0;
          *(_QWORD *)(v34 + 144) = 0;
          v44 = CFlipToken::InitializeCompleted(
                  (CFlipToken *)v34,
                  (const struct _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN *)(v12 + 16),
                  v42);
          if ( v44 < 0 )
            (**(void (__fastcall ***)(__int64, __int64))v34)(v34, 1);
          else
            v43 = (struct CToken *)v34;
          if ( v44 >= 0 )
          {
            v45 = (CompositionSurfaceObject *)v77;
            goto LABEL_52;
          }
        }
        else
        {
          v44 = -1073741801;
        }
        v45 = (CompositionSurfaceObject *)v77;
        v43 = 0;
        CompositionSurfaceObject::SignalGpuFence(
          (CompositionSurfaceObject *)v77,
          (unsigned __int64)v73,
          *((_QWORD *)v12 + 2),
          1);
        if ( *((_QWORD *)v12 + 6) )
          CompositionSurfaceObject::SignalPresentLimitSemaphore(v45, (unsigned __int64)v73);
LABEL_52:
        if ( v44 < 0 )
          v43 = 0;
        if ( !v71 )
          ObCloseHandle(Handle, 1);
        ObfDereferenceObject(v45);
        if ( v44 < 0 )
        {
          v14 = v69;
        }
        else
        {
          if ( !(*(unsigned __int8 (__fastcall **)(struct CToken *))(*(_QWORD *)v43 + 144LL))(v43)
            || (*(unsigned __int8 (__fastcall **)(struct CToken *))(*(_QWORD *)v43 + 152LL))(v43) )
          {
            if ( CTokenManager::AddTokenToQueue(this, v43) < 0 )
            {
              (*(void (__fastcall **)(struct CToken *))(*(_QWORD *)v43 + 56LL))(v43);
              (**(void (__fastcall ***)(struct CToken *, __int64))v43)(v43, 1);
              goto LABEL_85;
            }
            v46 = 0;
          }
          else
          {
            v57 = (_QWORD *)((char *)this + 328);
            v58 = *((_QWORD *)this + 41);
            if ( *(CTokenManager **)(v58 + 8) != (CTokenManager *)((char *)this + 328) )
              goto LABEL_24;
            v46 = 1;
            *((_QWORD *)v43 + 1) = v58;
            *((_QWORD *)v43 + 2) = v57;
            *(_QWORD *)(v58 + 8) = (char *)v43 + 8;
            *v57 = (char *)v43 + 8;
          }
          v47 = (CompositionSurfaceObject *)*((_QWORD *)v43 + 6);
          if ( v47 && CompositionSurfaceObject::StartCompositionEarly(v47, (unsigned __int64)v73) )
          {
            v64 = (void *)*((_QWORD *)this + 9);
            v71 = 0;
            ZwSetEvent(v64, &v71);
          }
          v48 = *((_QWORD *)v12 + 11);
          if ( v48 )
          {
            v65 = DxgkGetWin32kImportTable();
            (*(void (__fastcall **)(__int64))(v65 + 64))(v48);
          }
          v14 = v69;
          if ( v46 )
          {
            v11 = v68;
            v14 = ++v69;
            goto LABEL_13;
          }
        }
      }
LABEL_119:
      v11 = v68;
LABEL_13:
      ++v15;
      v13 = PreviousState;
      v12 += *((unsigned int *)v12 + 1);
    }
    while ( v15 < (unsigned int)v82 );
    v4 = (char *)this + 88;
LABEL_15:
    v6 = (struct CLegacyTokenBuffer **)((char *)this + 184);
    v17 = *((_QWORD *)this + 23);
    *(_DWORD *)(*(_QWORD *)(v17 + 2088) + 16LL) += v11;
    *(_DWORD *)(*(_QWORD *)(v17 + 2088) + 2068LL) += v13;
    *(_DWORD *)(v17 + 2104) -= v13;
    *(_QWORD *)(v17 + 2096) += v13;
    if ( (_DWORD)v82 != v14 )
    {
      v18 = (void *)*((_QWORD *)this + 8);
      PreviousState = 0;
      ZwSetEvent(v18, &PreviousState);
    }
    v3 = v75;
    v5 = v74;
LABEL_18:
    v2 = v66;
LABEL_19:
    *((_QWORD *)this + 12) = 0;
    ExReleasePushLockExclusiveEx(v4, 0);
  }
  while ( v10 >= 0 && v2 );
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140009ba0  mov     [rsp-8+arg_10], rbx
0x140009ba5  push    rbp
0x140009ba6  push    rsi
0x140009ba7  push    rdi
0x140009ba8  push    r12
0x140009baa  push    r13
0x140009bac  push    r14
0x140009bae  push    r15
0x140009bb0  lea     rbp, [rsp-7B0h]
0x140009bb8  sub     rsp, 8B0h
0x140009bbf  mov     rax, cs:__security_cookie
0x140009bc6  xor     rax, rsp
0x140009bc9  mov     [rbp+7E0h+var_40], rax
0x140009bd0  mov     dil, 1
0x140009bd3  mov     [rsp+8E0h+var_890], edx
0x140009bd7  mov     r12d, 280h
0x140009bdd  mov     [rsp+8E0h+var_8B0], dil
0x140009be2  mov     [rsp+8E0h+var_88C], r12d
0x140009be7  lea     r13, [rcx+58h]
0x140009beb  mov     r15d, edx
0x140009bee  lea     rbx, [rcx+0B8h]
0x140009bf5  mov     rsi, rcx
0x140009bf8  xor     edx, edx
0x140009bfa  mov     rcx, r13
0x140009bfd  xor     r14d, r14d
0x140009c00  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140009c07  nop     dword ptr [rax+rax+00h]
0x140009c0c  mov     rax, gs:188h
0x140009c15  mov     [rsi+60h], rax
0x140009c19  cmp     [rbx], r14
0x140009c1c  jz      loc_140009DBD
0x140009c22  mov     rbx, [rbx]
0x140009c25  cmp     r12d, [rbx+838h]
0x140009c2c  ja      loc_140009DEA
0x140009c32  mov     rax, [rbx+830h]
0x140009c39  lea     rcx, [rsp+8E0h+var_870]; Src
0x140009c3e  mov     [rsp+8E0h+var_878], rax
0x140009c43  xor     edx, edx
0x140009c45  mov     eax, [rbx+838h]
0x140009c4b  mov     [rsp+8E0h+var_86C], eax
0x140009c4f  lea     rax, [rbp+7E0h+Src]
0x140009c53  mov     [rbp+7E0h+var_860], rax
0x140009c57  mov     [rsp+8E0h+var_868], r14
0x140009c5c  mov     [rbp+7E0h+var_858], r14
0x140009c60  mov     [rsp+8E0h+var_870], r15d
0x140009c65  call    DxgkGetPresentHistoryInternal
0x140009c6a  mov     r14d, eax
0x140009c6d  test    eax, eax
0x140009c6f  jnz     loc_14000A214
0x140009c75  mov     [rsp+8E0h+var_8B0], al
0x140009c79  xor     edx, edx
0x140009c7b  lea     rbx, [rbp+7E0h+Src]
0x140009c7f  xor     edi, edi
0x140009c81  mov     [rsp+8E0h+var_8AC], edx
0x140009c85  xor     r15d, r15d
0x140009c88  mov     [rsp+8E0h+PreviousState], edi
0x140009c8c  xor     r12d, r12d
0x140009c8f  mov     [rsp+8E0h+var_8A8], r15d
0x140009c94  cmp     dword ptr [rbp+7E0h+var_858], edx
0x140009c97  jbe     short loc_140009D0B
0x140009c99  mov     eax, [rbx]
0x140009c9b  cmp     eax, 7
0x140009c9e  jz      loc_14000A261
0x140009ca4  cmp     eax, 8
0x140009ca7  jz      loc_14000A482
0x140009cad  cmp     eax, 2
0x140009cb0  jnz     loc_140009E36
0x140009cb6  mov     eax, [rbx+3Ch]
0x140009cb9  bt      eax, 0Dh
0x140009cbd  jnb     loc_140009E73
0x140009cc3  and     eax, 0C000h
0x140009cc8  cmp     eax, 4000h
0x140009ccd  jnz     loc_140009E73
0x140009cd3  mov     r9d, [rsp+8E0h+var_890]; unsigned int
0x140009cd8  lea     r8, [rbx+10h]; struct _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN *
0x140009cdc  mov     rdx, [rbx+8]; unsigned __int64
0x140009ce0  mov     rcx, rsi; this
0x140009ce3  call    ?CompleteIndependentFlipToken@CTokenManager@@IEAAJ_KAEBU_D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN@@I@Z; CTokenManager::CompleteIndependentFlipToken(unsigned __int64,_D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN const &,uint)
0x140009ce8  mov     edx, [rsp+8E0h+var_8AC]
0x140009cec  inc     r15d
0x140009cef  mov     [rsp+8E0h+var_8A8], r15d
0x140009cf4  mov     eax, [rbx+4]
0x140009cf7  inc     r12d
0x140009cfa  mov     edi, [rsp+8E0h+PreviousState]
0x140009cfe  add     rbx, rax
0x140009d01  cmp     r12d, dword ptr [rbp+7E0h+var_858]
0x140009d05  jb      short loc_140009C99
0x140009d07  lea     r13, [rsi+58h]
0x140009d0b  lea     rbx, [rsi+0B8h]
0x140009d12  mov     rcx, [rbx]
0x140009d15  mov     rax, [rcx+828h]
0x140009d1c  add     [rax+10h], edx
0x140009d1f  mov     rax, [rcx+828h]
0x140009d26  add     [rax+814h], edi
0x140009d2c  sub     [rcx+838h], edi
0x140009d32  mov     eax, edi
0x140009d34  add     [rcx+830h], rax
0x140009d3b  cmp     dword ptr [rbp+7E0h+var_858], r15d
0x140009d3f  jz      short loc_140009D5E
0x140009d41  mov     rcx, [rsi+40h]; EventHandle
0x140009d45  lea     rdx, [rsp+8E0h+PreviousState]; PreviousState
0x140009d4a  mov     [rsp+8E0h+PreviousState], 0
0x140009d52  call    cs:__imp_ZwSetEvent
0x140009d59  nop     dword ptr [rax+rax+00h]
0x140009d5e  mov     r12d, [rsp+8E0h+var_88C]
0x140009d63  mov     r15d, [rsp+8E0h+var_890]
0x140009d68  movzx   edi, [rsp+8E0h+var_8B0]
0x140009d6d  xor     edx, edx
0x140009d6f  mov     qword ptr [rsi+60h], 0
0x140009d77  mov     rcx, r13
0x140009d7a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140009d81  nop     dword ptr [rax+rax+00h]
0x140009d86  test    r14d, r14d
0x140009d89  jns     loc_14000A23E
0x140009d8f  mov     eax, r14d
0x140009d92  mov     rcx, [rbp+7E0h+var_40]
0x140009d99  xor     rcx, rsp; StackCookie
0x140009d9c  call    __security_check_cookie
0x140009da1  mov     rbx, [rsp+8E0h+arg_10]
0x140009da9  add     rsp, 8B0h
0x140009db0  pop     r15
0x140009db2  pop     r14
0x140009db4  pop     r13
0x140009db6  pop     r12
0x140009db8  pop     rdi
0x140009db9  pop     rsi
0x140009dba  pop     rbp
0x140009dbb  retn
0x140009dbd  lea     rcx, [rsi+0A0h]
0x140009dc4  mov     rax, [rcx]
0x140009dc7  cmp     rax, rcx
0x140009dca  jz      loc_14000A575
0x140009dd0  cmp     [rax+8], rcx
0x140009dd4  jnz     short loc_140009DE3
0x140009dd6  mov     rdx, [rax]
0x140009dd9  cmp     [rdx+8], rax
0x140009ddd  jz      loc_14000A24C
0x140009de3  mov     ecx, 3
0x140009de8  int     29h; Win8: RtlFailFast(ecx)
0x140009dea  lea     rcx, [rbx+10h]; struct CLegacyTokenBuffer::TokenBlock *
0x140009dee  mov     [rsp+8E0h+var_898], r14
0x140009df3  lea     rdx, [rsp+8E0h+var_898]; struct CLegacyTokenBuffer::TokenBlock **
0x140009df8  call    ?Create@TokenBlock@CLegacyTokenBuffer@@SAJAEAU12@PEAPEAU12@@Z; CLegacyTokenBuffer::TokenBlock::Create(CLegacyTokenBuffer::TokenBlock &,CLegacyTokenBuffer::TokenBlock * *)
0x140009dfd  mov     r14d, eax
0x140009e00  test    eax, eax
0x140009e02  js      short loc_140009E25
0x140009e04  mov     rax, [rsp+8E0h+var_898]
0x140009e09  mov     [rbx+828h], rax
0x140009e10  add     rax, 14h
0x140009e14  mov     [rbx+830h], rax
0x140009e1b  mov     dword ptr [rbx+838h], 800h
0x140009e25  test    r14d, r14d
0x140009e28  js      loc_14000A526
0x140009e2e  xor     r14d, r14d
0x140009e31  jmp     loc_140009C32
0x140009e36  cmp     eax, 9
0x140009e39  jz      loc_14000A4C7
0x140009e3f  mov     r13, [rsp+8E0h+var_878]
0x140009e44  mov     rdx, rbx; Src
0x140009e47  mov     r8d, [rbx+4]; Size
0x140009e4b  mov     rcx, r13; void *
0x140009e4e  call    memmove
0x140009e53  mov     edx, [rsp+8E0h+var_8AC]
0x140009e57  mov     eax, [rbx+4]
0x140009e5a  inc     edx
0x140009e5c  add     edi, eax
0x140009e5e  mov     [rsp+8E0h+var_8AC], edx
0x140009e62  add     r13, rax
0x140009e65  mov     [rsp+8E0h+PreviousState], edi
0x140009e69  mov     [rsp+8E0h+var_878], r13
0x140009e6e  jmp     loc_140009CF4
0x140009e73  mov     rax, [rbx+40h]
0x140009e77  lea     rcx, [rsp+8E0h+var_888]
0x140009e7c  mov     r13, [rbx+8]
0x140009e80  mov     r9b, 1; AccessMode
0x140009e83  mov     r8, cs:g_pDxgkCompositionObjectType; ObjectType
0x140009e8a  mov     edx, 2; DesiredAccess
0x140009e8f  mov     [rsp+8E0h+HandleInformation], 0; HandleInformation
0x140009e98  mov     [rsp+8E0h+Object], rcx; Object
0x140009e9d  mov     rcx, rax; Handle
0x140009ea0  mov     [rsp+8E0h+var_898], r13
0x140009ea5  mov     [rbp+7E0h+Handle], rax
0x140009ea9  mov     [rsp+8E0h+var_888], 0
0x140009eb2  call    cs:__imp_ObReferenceObjectByHandle
0x140009eb9  nop     dword ptr [rax+rax+00h]
0x140009ebe  test    eax, eax
0x140009ec0  js      loc_14000A624
0x140009ec6  mov     r15, [rsp+8E0h+var_888]
0x140009ecb  mov     [rsp+8E0h+var_880], r15
0x140009ed0  mov     rcx, [r15+10h]
0x140009ed4  mov     rax, [rcx]
0x140009ed7  mov     rax, [rax]
0x140009eda  call    _guard_dispatch_icall
0x140009edf  cmp     eax, 1
0x140009ee2  jnz     loc_14000A53A
0x140009ee8  mov     eax, [rbx+3Ch]
0x140009eeb  mov     ecx, eax
0x140009eed  and     ecx, 2000h
0x140009ef3  mov     [rsp+8E0h+var_8AF], 1
0x140009ef8  and     eax, 42000h
0x140009efd  mov     [rsp+8E0h+var_8A0], ecx
0x140009f01  cmp     eax, 2000h
0x140009f06  jnz     loc_140009FA0
0x140009f0c  call    cs:__imp_KeEnterCriticalRegion
0x140009f13  nop     dword ptr [rax+rax+00h]
0x140009f18  xor     edx, edx
0x140009f1a  lea     rcx, [r15+30h]
0x140009f1e  call    cs:__imp_ExAcquirePushLockSharedEx
0x140009f25  nop     dword ptr [rax+rax+00h]
0x140009f2a  cmp     dword ptr [r15+0A0h], 0
0x140009f32  jbe     loc_14000A56B
0x140009f38  lea     rdx, [r15+90h]
0x140009f3f  mov     rax, [rdx]
0x140009f42  cmp     rax, rdx
0x140009f45  jz      loc_14000A56B
0x140009f4b  cmp     [rax-8], r13
0x140009f4f  lea     rcx, [rax-18h]
0x140009f53  jnz     loc_14000A505
0x140009f59  mov     rax, [rcx]
0x140009f5c  mov     rax, [rax+0C8h]
0x140009f63  call    _guard_dispatch_icall
0x140009f68  mov     [rsp+8E0h+var_8AF], al
0x140009f6c  call    cs:__imp_PsGetCurrentThreadId
0x140009f73  nop     dword ptr [rax+rax+00h]
0x140009f78  xor     edx, edx
0x140009f7a  lea     rcx, [r15+30h]
0x140009f7e  cmp     rax, [r15+38h]
0x140009f82  jz      loc_14000A469
0x140009f88  call    cs:__imp_ExReleasePushLockSharedEx
0x140009f8f  nop     dword ptr [rax+rax+00h]
0x140009f94  call    cs:__imp_KeLeaveCriticalRegion
0x140009f9b  nop     dword ptr [rax+rax+00h]
0x140009fa0  mov     edx, 268h
0x140009fa5  mov     ecx, 100h
0x140009faa  mov     r8d, 6F744D54h
0x140009fb0  call    cs:__imp_ExAllocatePool2
0x140009fb7  nop     dword ptr [rax+rax+00h]
0x140009fbc  mov     rdi, rax
0x140009fbf  test    rax, rax
0x140009fc2  jz      loc_14000A412
0x140009fc8  mov     dword ptr [rax+18h], 6
0x140009fcf  xor     r9d, r9d; AccessMode
0x140009fd2  xor     eax, eax
0x140009fd4  mov     [rdi+38h], r13
0x140009fd8  mov     [rdi+20h], rax
0x140009fdc  xor     r13d, r13d
0x140009fdf  mov     [rdi+28h], eax
0x140009fe2  mov     edx, 3; DesiredAccess
0x140009fe7  lea     rax, ??_7CToken@@6B@; const CToken::`vftable'
0x140009fee  mov     word ptr [rdi+40h], 0
0x140009ff4  mov     [rdi], rax
0x140009ff7  mov     rcx, r15; Object
0x140009ffa  mov     [rdi+60h], r13
0x140009ffe  mov     [rdi+44h], r13d
0x14000a002  mov     [rdi+30h], r15
0x14000a006  mov     r8, cs:g_pDxgkCompositionObjectType; ObjectType
0x14000a00d  call    cs:__imp_ObReferenceObjectByPointer
0x14000a014  nop     dword ptr [rax+rax+00h]
0x14000a019  mov     r15, [rdi+30h]
0x14000a01d  lea     rax, ??_7CFlipToken@@6B@; const CFlipToken::`vftable'
0x14000a024  mov     [rdi+68h], r13
0x14000a028  mov     [rdi+70h], r13
0x14000a02c  mov     [rdi+241h], r13d
0x14000a033  mov     [rdi+250h], r13
0x14000a03a  mov     [rdi+258h], r13
0x14000a041  mov     r13, [rdi+38h]
0x14000a045  mov     [rdi], rax
0x14000a048  mov     dword ptr [rdi+245h], 100h
0x14000a052  call    cs:__imp_KeEnterCriticalRegion
0x14000a059  nop     dword ptr [rax+rax+00h]
0x14000a05e  lea     rcx, [r15+30h]
0x14000a062  xor     edx, edx
0x14000a064  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000a06b  nop     dword ptr [rax+rax+00h]
0x14000a070  cmp     dword ptr [r15+0A0h], 0
0x14000a078  mov     [rsp+8E0h+var_8A4], 0
0x14000a07d  jbe     loc_14000A532
0x14000a083  lea     rcx, [r15+90h]
0x14000a08a  mov     rax, [rcx]
0x14000a08d  cmp     rax, rcx
0x14000a090  jz      loc_14000A59D
0x14000a096  cmp     [rax-8], r13
0x14000a09a  jnz     loc_14000A4BF
0x14000a0a0  movzx   r13d, byte ptr [rax+11h]
0x14000a0a5  call    cs:__imp_PsGetCurrentThreadId
0x14000a0ac  nop     dword ptr [rax+rax+00h]
0x14000a0b1  xor     edx, edx
0x14000a0b3  lea     rcx, [r15+30h]
0x14000a0b7  cmp     rax, [r15+38h]
0x14000a0bb  jz      loc_14000A3B1
0x14000a0c1  call    cs:__imp_ExReleasePushLockSharedEx
0x14000a0c8  nop     dword ptr [rax+rax+00h]
0x14000a0cd  call    cs:__imp_KeLeaveCriticalRegion
0x14000a0d4  nop     dword ptr [rax+rax+00h]
0x14000a0d9  movzx   r8d, [rsp+8E0h+var_8AF]; bool
0x14000a0df  lea     rdx, [rbx+10h]; struct _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN *
0x14000a0e3  test    r13b, r13b
0x14000a0e6  mov     rcx, rdi; this
0x14000a0e9  setz    al
0x14000a0ec  xor     r15d, r15d
  ... truncated ...
```
