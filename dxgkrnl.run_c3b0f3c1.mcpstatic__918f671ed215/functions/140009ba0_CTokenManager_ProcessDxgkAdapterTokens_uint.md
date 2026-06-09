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
  __int64 v8; // r8
  struct CLegacyTokenBuffer *v9; // rbx
  int PresentHistoryInternal; // eax
  CompositionSurfaceObject *v11; // rcx
  int v12; // r14d
  int v13; // edx
  _BYTE *v14; // rbx
  unsigned int v15; // edi
  int v16; // r15d
  unsigned int v17; // r12d
  int v18; // eax
  __int64 v19; // rcx
  void *v20; // rcx
  _QWORD *v22; // rcx
  CTokenManager *v23; // rax
  __int64 v24; // rdx
  char *v25; // rax
  char *v26; // r13
  __int64 v27; // rax
  void *v28; // r13
  void *v29; // rcx
  char *v30; // r15
  int v31; // eax
  char *i; // rax
  HANDLE v33; // rax
  char *v34; // rcx
  __int64 Pool2; // rax
  __int64 v36; // rdi
  __int64 v37; // r15
  __int64 v38; // r13
  bool v39; // zf
  __int64 *j; // rax
  char v41; // r13
  HANDLE v42; // rax
  __int64 v43; // rcx
  bool v44; // r8
  struct CToken *v45; // r15
  int v46; // r13d
  CompositionSurfaceObject *v47; // rdi
  char v48; // r13
  __int64 v49; // rdi
  void *v50; // r15
  _QWORD *v51; // rdi
  __int64 v52; // rax
  HANDLE CurrentThreadId; // rax
  char *v54; // rcx
  CTokenManager **v55; // rdx
  __int64 v56; // rdi
  struct DXGGLOBAL *Global; // rax
  _QWORD *v58; // rcx
  __int64 v59; // rdx
  __int64 Win32kImportTable; // rax
  __int64 v61; // rcx
  __int64 v62; // rax
  __int64 v63; // rcx
  __int64 v64; // rax
  int v65; // eax
  struct FlipManagerTokenObject *v66; // rdx
  void *v67; // rcx
  __int64 v68; // rax
  char v69; // [rsp+30h] [rbp-D0h]
  bool v70; // [rsp+31h] [rbp-CFh] BYREF
  int v71; // [rsp+34h] [rbp-CCh]
  int v72; // [rsp+38h] [rbp-C8h]
  char v73; // [rsp+3Ch] [rbp-C4h]
  LONG v74; // [rsp+40h] [rbp-C0h] BYREF
  LONG PreviousState; // [rsp+44h] [rbp-BCh] BYREF
  PVOID v76; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v77; // [rsp+50h] [rbp-B0h]
  int v78; // [rsp+54h] [rbp-ACh]
  PVOID Object; // [rsp+58h] [rbp-A8h] BYREF
  PVOID v80; // [rsp+60h] [rbp-A0h]
  void *v81; // [rsp+68h] [rbp-98h]
  _DWORD v82[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v83; // [rsp+78h] [rbp-88h]
  _BYTE *v84; // [rsp+80h] [rbp-80h]
  __int64 v85; // [rsp+88h] [rbp-78h]
  HANDLE Handle; // [rsp+90h] [rbp-70h]
  _BYTE Src[2048]; // [rsp+A0h] [rbp-60h] BYREF

  v2 = 1;
  v77 = a2;
  v3 = 640;
  v69 = 1;
  v78 = 640;
  v4 = (char *)this + 88;
  v5 = a2;
  v6 = (struct CLegacyTokenBuffer **)((char *)this + 184);
  do
  {
    ExAcquirePushLockExclusiveEx(v4, 0);
    *((_QWORD *)this + 12) = KeGetCurrentThread();
    if ( !*v6 )
    {
      v22 = (_QWORD *)((char *)this + 160);
      v23 = (CTokenManager *)*((_QWORD *)this + 20);
      if ( v23 == (CTokenManager *)((char *)this + 160) )
      {
        v12 = CLegacyTokenBuffer::Create(v6);
        if ( v12 < 0 )
          goto LABEL_19;
      }
      else
      {
        if ( *((_QWORD **)v23 + 1) != v22 || (v24 = *(_QWORD *)v23, *(CTokenManager **)(*(_QWORD *)v23 + 8LL) != v23) )
LABEL_24:
          __fastfail(3u);
        *v22 = v24;
        *(_QWORD *)(v24 + 8) = v22;
        --*((_DWORD *)this + 44);
        *v6 = v23;
      }
    }
    v9 = *v6;
    if ( v3 > *((_DWORD *)v9 + 526) )
    {
      v76 = 0;
      v12 = CLegacyTokenBuffer::TokenBlock::Create(
              (struct CLegacyTokenBuffer *)((char *)v9 + 16),
              (struct CLegacyTokenBuffer::TokenBlock **)&v76);
      if ( v12 < 0 )
        goto LABEL_107;
      v25 = (char *)v76;
      *((_QWORD *)v9 + 261) = v76;
      *((_QWORD *)v9 + 262) = v25 + 20;
      *((_DWORD *)v9 + 526) = 2048;
    }
    v81 = (void *)*((_QWORD *)v9 + 262);
    v82[1] = *((_DWORD *)v9 + 526);
    v84 = Src;
    v83 = 0;
    v85 = 0;
    v82[0] = v5;
    PresentHistoryInternal = DxgkGetPresentHistoryInternal((char *)v82, 0, v8);
    v12 = PresentHistoryInternal;
    if ( PresentHistoryInternal )
    {
      if ( PresentHistoryInternal != 261 )
      {
        if ( PresentHistoryInternal != -1073741789 )
        {
          v2 = 0;
          v6 = (struct CLegacyTokenBuffer **)((char *)this + 184);
          v69 = 0;
          goto LABEL_19;
        }
        v3 = 640;
        if ( (unsigned int)v83 > 0x280 )
          v3 = v83;
        v12 = 0;
        v78 = v3;
LABEL_107:
        v6 = (struct CLegacyTokenBuffer **)((char *)this + 184);
        goto LABEL_18;
      }
    }
    else
    {
      v69 = 0;
    }
    v13 = 0;
    v14 = Src;
    v15 = 0;
    v71 = 0;
    v16 = 0;
    PreviousState = 0;
    v17 = 0;
    v72 = 0;
    if ( !(_DWORD)v85 )
      goto LABEL_15;
    do
    {
      v18 = *(_DWORD *)v14;
      if ( *(_DWORD *)v14 == 7 )
      {
        v50 = (void *)*((_QWORD *)v14 + 2);
        if ( v50 )
        {
          v76 = 0;
          if ( ObReferenceObjectByHandle(v50, 2u, g_pDxgkCompositionObjectType, 1, &v76, 0) >= 0 )
          {
            v51 = v76;
            if ( (***((unsigned int (__fastcall ****)(_QWORD))v76 + 2))(*((_QWORD *)v76 + 2)) != 2 )
              goto LABEL_110;
            KeEnterCriticalRegion();
            ExAcquirePushLockSharedEx(v51 + 11, 0);
            if ( *((_DWORD *)v51 + 16) == 1 )
            {
              v52 = v51[5];
              v74 = 0;
              (*(void (__fastcall **)(_QWORD *))(v52 + 24))(v51 + 5);
            }
            else
            {
              v74 = -1073741823;
            }
            CurrentThreadId = PsGetCurrentThreadId();
            v54 = (char *)(v51 + 11);
            if ( CurrentThreadId == (HANDLE)v51[12] )
            {
              v51[12] = 0;
              ExReleasePushLockExclusiveEx(v54, 0);
            }
            else
            {
              ExReleasePushLockSharedEx(v54, 0);
            }
            KeLeaveCriticalRegion();
            if ( v74 >= 0 )
            {
              v55 = (CTokenManager **)*((_QWORD *)this + 34);
              if ( *v55 != (CTokenManager *)((char *)this + 264) )
                goto LABEL_24;
              v51[6] = (char *)this + 264;
              v51[7] = v55;
              *v55 = (CTokenManager *)(v51 + 6);
              *((_QWORD *)this + 34) = v51 + 6;
              v56 = v51[15];
              if ( v56 )
              {
                Global = DXGGLOBAL::GetGlobal();
                (*(void (__fastcall **)(__int64))(*((_QWORD *)Global + 38121) + 64LL))(v56);
              }
            }
            else
            {
LABEL_110:
              ObfDereferenceObject(v51);
            }
          }
          NtClose(v50);
LABEL_85:
          v13 = v71;
        }
        v16 = v72;
        goto LABEL_13;
      }
      if ( v18 == 8 )
      {
        Win32kImportTable = DxgkGetWin32kImportTable(v11);
        (*(void (**)(void))(Win32kImportTable + 456))();
        v62 = DxgkGetWin32kImportTable(v61);
        (*(void (__fastcall **)(_QWORD))(v62 + 32))(*((_QWORD *)v14 + 2));
        v64 = DxgkGetWin32kImportTable(v63);
        (*(void (**)(void))(v64 + 496))();
        v13 = v71;
        goto LABEL_13;
      }
      if ( v18 != 2 )
      {
        if ( v18 != 9 )
        {
          v26 = (char *)v81;
          memmove(v81, v14, *((unsigned int *)v14 + 1));
          v27 = *((unsigned int *)v14 + 1);
          v13 = ++v71;
          PreviousState = v27 + v15;
          v81 = &v26[v27];
          goto LABEL_13;
        }
        v65 = *((_DWORD *)v14 + 8);
        v70 = 1;
        if ( (v65 & 4) == 0 )
          goto LABEL_102;
        v66 = (struct FlipManagerTokenObject *)*((_QWORD *)v14 + 2);
        if ( !v66 || (CTokenManager::CompleteFlipManagerToken(this, v66, &v70), v70) )
        {
          v13 = v71;
LABEL_102:
          v72 = ++v16;
          goto LABEL_13;
        }
        goto LABEL_119;
      }
      if ( (*((_DWORD *)v14 + 15) & 0x2000) != 0 && (*((_DWORD *)v14 + 15) & 0xC000) == 0x4000 )
      {
        CTokenManager::CompleteIndependentFlipToken(
          this,
          *((_QWORD *)v14 + 1),
          (const struct _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN *)(v14 + 16),
          v77);
        v13 = v71;
        v72 = ++v16;
        goto LABEL_13;
      }
      v28 = (void *)*((_QWORD *)v14 + 1);
      v29 = (void *)*((_QWORD *)v14 + 8);
      v76 = v28;
      Handle = v29;
      Object = 0;
      if ( ObReferenceObjectByHandle(v29, 2u, g_pDxgkCompositionObjectType, 1, &Object, 0) >= 0 )
      {
        v30 = (char *)Object;
        v80 = Object;
        if ( (***((unsigned int (__fastcall ****)(_QWORD))Object + 2))(*((_QWORD *)Object + 2)) != 1 )
        {
          ObfDereferenceObject(v30);
          v13 = v71;
          v16 = v72;
          goto LABEL_13;
        }
        v31 = *((_DWORD *)v14 + 15);
        v70 = 1;
        v74 = v31 & 0x2000;
        if ( (v31 & 0x42000) == 0x2000 )
        {
          KeEnterCriticalRegion();
          ExAcquirePushLockSharedEx(v30 + 48, 0);
          if ( *((_DWORD *)v30 + 40) )
          {
            for ( i = (char *)*((_QWORD *)v30 + 18); i != v30 + 144; i = *(char **)i )
            {
              if ( *((void **)i - 1) == v28 )
              {
                v70 = (*(__int64 (__fastcall **)(_QWORD *))(*((_QWORD *)i - 3) + 200LL))((_QWORD *)i - 3);
                goto LABEL_37;
              }
            }
          }
          v70 = 0;
LABEL_37:
          v33 = PsGetCurrentThreadId();
          v34 = v30 + 48;
          if ( v33 == *((HANDLE *)v30 + 7) )
          {
            *((_QWORD *)v30 + 7) = 0;
            ExReleasePushLockExclusiveEx(v34, 0);
          }
          else
          {
            ExReleasePushLockSharedEx(v34, 0);
          }
          KeLeaveCriticalRegion();
        }
        Pool2 = ExAllocatePool2(256, 616, 1869892948);
        v36 = Pool2;
        if ( Pool2 )
        {
          *(_DWORD *)(Pool2 + 24) = 6;
          *(_QWORD *)(Pool2 + 56) = v28;
          *(_QWORD *)(Pool2 + 32) = 0;
          *(_DWORD *)(Pool2 + 40) = 0;
          *(_WORD *)(Pool2 + 64) = 0;
          *(_QWORD *)Pool2 = &CToken::`vftable';
          *(_QWORD *)(Pool2 + 96) = 0;
          *(_DWORD *)(Pool2 + 68) = 0;
          *(_QWORD *)(Pool2 + 48) = v30;
          ObReferenceObjectByPointer(v30, 3u, g_pDxgkCompositionObjectType, 0);
          v37 = *(_QWORD *)(v36 + 48);
          *(_QWORD *)(v36 + 104) = 0;
          *(_QWORD *)(v36 + 112) = 0;
          *(_DWORD *)(v36 + 577) = 0;
          *(_QWORD *)(v36 + 592) = 0;
          *(_QWORD *)(v36 + 600) = 0;
          v38 = *(_QWORD *)(v36 + 56);
          *(_QWORD *)v36 = &CFlipToken::`vftable';
          *(_DWORD *)(v36 + 581) = 256;
          KeEnterCriticalRegion();
          ExAcquirePushLockSharedEx(v37 + 48, 0);
          v39 = *(_DWORD *)(v37 + 160) == 0;
          v73 = 0;
          if ( v39 )
          {
            v41 = 0;
          }
          else
          {
            for ( j = *(__int64 **)(v37 + 144); j != (__int64 *)(v37 + 144); j = (__int64 *)*j )
            {
              if ( *(j - 1) == v38 )
              {
                v41 = *((_BYTE *)j + 17);
                goto LABEL_46;
              }
            }
            v41 = v73;
          }
LABEL_46:
          v42 = PsGetCurrentThreadId();
          v43 = v37 + 48;
          if ( v42 == *(HANDLE *)(v37 + 56) )
          {
            *(_QWORD *)(v37 + 56) = 0;
            ExReleasePushLockExclusiveEx(v43, 0);
          }
          else
          {
            ExReleasePushLockSharedEx(v43, 0);
          }
          KeLeaveCriticalRegion();
          v44 = v70;
          v45 = 0;
          *(_QWORD *)(v36 + 164) = 0;
          *(_QWORD *)(v36 + 172) = 0;
          *(_QWORD *)(v36 + 180) = 0;
          *(_QWORD *)(v36 + 188) = 0;
          *(_BYTE *)(v36 + 576) = v41 == 0;
          *(_QWORD *)(v36 + 204) = 1065353216;
          *(_DWORD *)(v36 + 212) = 0;
          *(_QWORD *)(v36 + 216) = 1065353216;
          *(_DWORD *)(v36 + 224) = 0;
          *(_QWORD *)(v36 + 136) = 0;
          *(_QWORD *)(v36 + 144) = 0;
          v46 = CFlipToken::InitializeCompleted(
                  (CFlipToken *)v36,
                  (const struct _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN *)(v14 + 16),
                  v44);
          if ( v46 < 0 )
            (**(void (__fastcall ***)(__int64, __int64))v36)(v36, 1);
          else
            v45 = (struct CToken *)v36;
          if ( v46 >= 0 )
          {
            v47 = (CompositionSurfaceObject *)v80;
            goto LABEL_52;
          }
        }
        else
        {
          v46 = -1073741801;
        }
        v47 = (CompositionSurfaceObject *)v80;
        v45 = 0;
        CompositionSurfaceObject::SignalGpuFence(
          (CompositionSurfaceObject *)v80,
          (unsigned __int64)v76,
          *((_QWORD *)v14 + 2),
          1);
        if ( *((_QWORD *)v14 + 6) )
          CompositionSurfaceObject::SignalPresentLimitSemaphore(v47, (unsigned __int64)v76);
LABEL_52:
        if ( v46 < 0 )
          v45 = 0;
        if ( !v74 )
          ObCloseHandle(Handle, 1);
        ObfDereferenceObject(v47);
        if ( v46 < 0 )
        {
          v16 = v72;
        }
        else
        {
          if ( !(*(unsigned __int8 (__fastcall **)(struct CToken *))(*(_QWORD *)v45 + 144LL))(v45)
            || (*(unsigned __int8 (__fastcall **)(struct CToken *))(*(_QWORD *)v45 + 152LL))(v45) )
          {
            if ( CTokenManager::AddTokenToQueue(this, v45) < 0 )
            {
              (*(void (__fastcall **)(struct CToken *))(*(_QWORD *)v45 + 56LL))(v45);
              (**(void (__fastcall ***)(struct CToken *, __int64))v45)(v45, 1);
              goto LABEL_85;
            }
            v48 = 0;
          }
          else
          {
            v58 = (_QWORD *)((char *)this + 328);
            v59 = *((_QWORD *)this + 41);
            if ( *(CTokenManager **)(v59 + 8) != (CTokenManager *)((char *)this + 328) )
              goto LABEL_24;
            v48 = 1;
            *((_QWORD *)v45 + 1) = v59;
            *((_QWORD *)v45 + 2) = v58;
            *(_QWORD *)(v59 + 8) = (char *)v45 + 8;
            *v58 = (char *)v45 + 8;
          }
          v11 = (CompositionSurfaceObject *)*((_QWORD *)v45 + 6);
          if ( v11 && CompositionSurfaceObject::StartCompositionEarly(v11, (unsigned __int64)v76) )
          {
            v67 = (void *)*((_QWORD *)this + 9);
            v74 = 0;
            ZwSetEvent(v67, &v74);
          }
          v49 = *((_QWORD *)v14 + 11);
          if ( v49 )
          {
            v68 = DxgkGetWin32kImportTable(v11);
            (*(void (__fastcall **)(__int64))(v68 + 64))(v49);
          }
          v16 = v72;
          if ( v48 )
          {
            v13 = v71;
            v16 = ++v72;
            goto LABEL_13;
          }
        }
      }
LABEL_119:
      v13 = v71;
LABEL_13:
      ++v17;
      v15 = PreviousState;
      v14 += *((unsigned int *)v14 + 1);
    }
    while ( v17 < (unsigned int)v85 );
    v4 = (char *)this + 88;
LABEL_15:
    v6 = (struct CLegacyTokenBuffer **)((char *)this + 184);
    v19 = *((_QWORD *)this + 23);
    *(_DWORD *)(*(_QWORD *)(v19 + 2088) + 16LL) += v13;
    *(_DWORD *)(*(_QWORD *)(v19 + 2088) + 2068LL) += v15;
    *(_DWORD *)(v19 + 2104) -= v15;
    *(_QWORD *)(v19 + 2096) += v15;
    if ( (_DWORD)v85 != v16 )
    {
      v20 = (void *)*((_QWORD *)this + 8);
      PreviousState = 0;
      ZwSetEvent(v20, &PreviousState);
    }
    v3 = v78;
    v5 = v77;
LABEL_18:
    v2 = v69;
LABEL_19:
    *((_QWORD *)this + 12) = 0;
    ExReleasePushLockExclusiveEx(v4, 0);
  }
  while ( v12 >= 0 && v2 );
  return (unsigned int)v12;
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
