# CCorSvcMgr::UpdateWorker(ushort *,__MIDL___MIDL_itf_mscorsvc_0000_0006_0001,__MIDL___MIDL_itf_mscorsvc_0000_0005_0001,bool)

- ea: `0x18001f180`
- end: `0x18001f798`
- name: `?UpdateWorker@CCorSvcMgr@@AEAAXPEAGW4__MIDL___MIDL_itf_mscorsvc_0000_0006_0001@@W4__MIDL___MIDL_itf_mscorsvc_0000_0005_0001@@_N@Z`
- size: `1560`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x18001f7a0`
- `0x180028750`

## callees

- `0x180005df0`
- `0x1800064a8`
- `0x180006a2c`
- `0x180009100`
- `0x180009704`
- `0x1800097e0`
- `0x180009df4`
- `0x18001f180`
- `0x180026438`
- `0x1800289bc`
- `0x18002d3c0`
- `0x18002ff30`
- `0x180030568`
- `0x180030ab8`
- `0x180031e08`
- `0x180034fd4`
- `0x18003dc30`
- `0x18003dc50`
- `0x18003f280`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001f605`
- `KERNEL32!CloseHandle` at `0x18001f605`
- `KERNEL32!HeapFree` at `0x18001f5cc`
- `KERNEL32!HeapFree` at `0x18001f74a`
- `KERNEL32!HeapFree` at `0x18001f5cc`
- `KERNEL32!HeapFree` at `0x18001f74a`
- `KERNEL32!GetProcessHeap` at `0x18001f5b7`
- `KERNEL32!GetProcessHeap` at `0x18001f735`
- `KERNEL32!GetProcessHeap` at `0x18001f5b7`
- `KERNEL32!GetProcessHeap` at `0x18001f735`

## string_xrefs

- `0x18001f34e`: `ngennicupdatelock.dat`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
int __fastcall CCorSvcMgr::UpdateWorker(CCorSvcMgr *a1, const unsigned __int16 *a2, char a3, __int64 a4, char a5)
{
  CCorSvcMgr *v5; // r13
  int v7; // edi
  char v8; // r14
  struct RootList *RootList; // rax
  void **RootArray; // rax
  void **v11; // r15
  __int64 v12; // rcx
  CCorSvcMgr::WorkerPoolItem *PooledSvcWorker; // rdi
  int v14; // eax
  unsigned int v15; // edi
  char *v16; // r12
  __int64 v17; // rax
  CCorSvcMgr::WorkerPoolItem *v18; // r15
  int v19; // r14d
  int v20; // eax
  bool v21; // r8
  HANDLE ProcessHeap; // rax
  unsigned int v23; // edi
  __int64 v24; // r14
  unsigned int v25; // eax
  __int64 v26; // r15
  __int64 v27; // r12
  int v28; // edi
  __int64 v29; // rax
  struct Configuration *v30; // r9
  void *v31; // rdi
  HANDLE v32; // rax
  struct Exception *v33; // rbx
  BOOL v34; // edi
  struct Exception *v35; // rdx
  Exception *v36; // rcx
  bool v37; // dl
  unsigned int CurrentExceptionCode; // eax
  int v39; // edx
  bool v41; // [rsp+50h] [rbp-348h] BYREF
  unsigned int v42; // [rsp+54h] [rbp-344h]
  void ***v43; // [rsp+58h] [rbp-340h] BYREF
  unsigned int v44; // [rsp+60h] [rbp-338h]
  int v45; // [rsp+64h] [rbp-334h]
  void **v46; // [rsp+68h] [rbp-330h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-328h]
  CCorSvcMgr::WorkerPoolItem *v48; // [rsp+78h] [rbp-320h]
  BOOL v49; // [rsp+80h] [rbp-318h]
  __int128 v50; // [rsp+90h] [rbp-308h] BYREF
  void *v51; // [rsp+A0h] [rbp-2F8h]
  int v52; // [rsp+B0h] [rbp-2E8h]
  void **v53; // [rsp+B8h] [rbp-2E0h]
  int v54; // [rsp+C0h] [rbp-2D8h] BYREF
  struct Exception *v55; // [rsp+C8h] [rbp-2D0h]
  LPVOID lpMem; // [rsp+D0h] [rbp-2C8h] BYREF
  int v57; // [rsp+D8h] [rbp-2C0h]
  CCorSvcMgr *v58; // [rsp+E0h] [rbp-2B8h]
  CCorSvcMgr *v59; // [rsp+E8h] [rbp-2B0h]
  __int128 v60; // [rsp+F0h] [rbp-2A8h] BYREF
  _QWORD v61[4]; // [rsp+100h] [rbp-298h] BYREF
  void ***v62; // [rsp+120h] [rbp-278h]
  struct Exception *v63; // [rsp+128h] [rbp-270h] BYREF
  unsigned int v64; // [rsp+130h] [rbp-268h] BYREF
  __int64 v65; // [rsp+134h] [rbp-264h]
  LPVOID v66; // [rsp+140h] [rbp-258h]
  __int16 v67; // [rsp+148h] [rbp-250h] BYREF

  v5 = a1;
  v58 = a1;
  v59 = a1;
  v7 = 0;
  v44 = 0;
  v65 = 512;
  v66 = &v67;
  v64 = 2;
  v67 = 0;
  SString::Set((SString *)&v64, a2);
  if ( v64 >> ((v65 & 0x100000000LL) == 0) == 1
    || (*(_QWORD *)&v50 = 0x400000004LL,
        v51 = (void *)L"*",
        DWORD2(v50) = 276,
        v7 = 1,
        v44 = 1,
        v8 = 0,
        (unsigned int)SString::Equals((SString *)&v64, (const struct SString *)&v50)) )
  {
    v8 = 1;
  }
  if ( (v7 & 1) != 0 )
  {
    v44 = v7 & 0xFFFFFFFE;
    if ( (BYTE8(v50) & 8) != 0 )
      operator delete(v51);
  }
  if ( !v8 )
    ThrowHR(-2147467263);
  RootList = GetRootList(0);
  RootArray = (void **)RootList::GetRootArray(RootList);
  v11 = RootArray;
  v53 = RootArray;
  v45 = a3 & 1;
  v52 = v45;
  if ( (a3 & 1) != 0 )
  {
    v43 = &v46;
    hObject = (HANDLE)-1LL;
    v46 = &MachineWideMutexHolder::`vftable';
    GetRootList(0);
    if ( *v46 == MachineWideMutexHolder::Acquire )
      MachineWideMutexHolder::Acquire((MachineWideMutexHolder *)&v46, L"ngennicupdatelock.dat", 0, 0);
    else
      ((void (__fastcall *)(void ***, const unsigned __int16 *, _QWORD, _QWORD))*v46)(
        &v46,
        L"ngennicupdatelock.dat",
        0,
        0);
    if ( (unsigned int)Helpers::IsUsingPrivateStore() )
    {
      v60 = *((_OWORD *)v5 + 17);
      PooledSvcWorker = (CCorSvcMgr::WorkerPoolItem *)CCorSvcMgr::GetPooledSvcWorker(
                                                        v5,
                                                        *((_QWORD *)v5 + 162),
                                                        ((unsigned __int64)v5 + 24) & -(__int64)(a1 != 0),
                                                        &v60,
                                                        0,
                                                        0);
      v48 = PooledSvcWorker;
      v49 = PooledSvcWorker != 0;
      v14 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD))(**((_QWORD **)PooledSvcWorker + 3) + 40LL))(
              *((_QWORD **)PooledSvcWorker + 3),
              0,
              0);
      if ( v14 < 0 )
        ThrowHR(v14);
      if ( PooledSvcWorker )
      {
        CCorSvcMgr::WorkerPoolItem::~WorkerPoolItem(PooledSvcWorker);
        operator delete(PooledSvcWorker);
        v49 = 0;
      }
    }
    else
    {
      lpMem = 0;
      v57 = 0;
      LODWORD(v43) = 0;
      CCorSvcMgr::GetNativeImageRuntimeVersions(v12, &lpMem, &v43);
      v15 = 0;
      v42 = 0;
      v16 = (char *)lpMem;
      while ( v15 < (unsigned int)v43 )
      {
        v54 = 0;
        v55 = 0;
        try
        {
          try
          {
            v62 = (void ***)&v54;
            v50 = *((_OWORD *)v5 + 17);
            v17 = CCorSvcMgr::GetPooledSvcWorker(
                    v5,
                    *((_QWORD *)v5 + 162),
                    ((unsigned __int64)v59 + 24) & -(__int64)(v59 != 0),
                    &v50,
                    &v16[64 * (unsigned __int64)v15],
                    0);
            v18 = (CCorSvcMgr::WorkerPoolItem *)v17;
            *(_QWORD *)&v60 = v17;
            v19 = 0;
            DWORD2(v60) = 0;
            if ( v17 )
            {
              v19 = 1;
              DWORD2(v60) = 1;
            }
            v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(v17 + 24) + 40LL))(
                    *(_QWORD *)(v17 + 24),
                    0,
                    0);
            if ( v20 < 0 )
              ThrowHR(v20);
            if ( v19 )
            {
              CCorSvcMgr::WorkerPoolItem::~WorkerPoolItem(v18);
              operator delete(v18);
              DWORD2(v60) = 0;
            }
          }
          catch ( Exception *v63 )
          {
            Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v54);
            v55 = v63;
            throw;
          }
        }
        catch ( ... )
        {
          v61[1] = 0;
          v61[0] = &DelegatingException::`vftable';
          v61[2] = -1;
          v33 = v55;
          v48 = v55;
          v34 = v55 != 0;
          v49 = v34;
          Exception::HandlerState::SetupCatch((Exception::HandlerState *)&v54, 853, v21);
          v35 = (struct Exception *)v61;
          if ( v33 )
            v35 = v33;
          CCorSvcMgr::HandlePerRuntimeException(
            v58,
            v35,
            L"Error while deleting native images",
            (const unsigned __int16 *)lpMem + 32 * (unsigned __int64)v42,
            0);
          v36 = (Exception *)v61;
          if ( v33 )
            v36 = v33;
          if ( !(unsigned int)Exception::IsTerminal(v36) )
          {
            if ( CLRConfig::GetConfigValue(
                   (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_legacyCorruptedStateExceptionsPolicy,
                   v37,
                   &v41)
              || (CurrentExceptionCode = GetCurrentExceptionCode(),
                  !(unsigned int)IsProcessCorruptedStateException(CurrentExceptionCode, v39)) )
            {
              if ( v34 )
              {
                if ( v33 && !(*(unsigned int (__fastcall **)(struct Exception *))(*(_QWORD *)v33 + 80LL))(v33) )
                  (**(void (__fastcall ***)(struct Exception *, __int64))v33)(v33, 5);
                v49 = 0;
              }
              DelegatingException::~DelegatingException((DelegatingException *)v61);
              v16 = (char *)lpMem;
              v15 = v42;
              v5 = v58;
              v59 = v58;
              v45 = v52;
              goto LABEL_24;
            }
          }
          v49 = 0;
          throw;
        }
LABEL_24:
        if ( (v54 & 2) != 0 && g_fpHandleStackOverflowAfterCatch )
          g_fpHandleStackOverflowAfterCatch();
        v42 = ++v15;
      }
      if ( v57 )
      {
        if ( v16 )
        {
          ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
          if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
          {
            ProcessHeap = GetProcessHeap();
            `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
          }
          HeapFree(ProcessHeap, 0, v16);
        }
        v57 = 0;
      }
      v11 = v53;
    }
    v62 = &v46;
    RootArray = &FileLockHolder::`vftable';
    v46 = &FileLockHolder::`vftable';
    if ( hObject != (HANDLE)-1LL )
    {
      LODWORD(RootArray) = CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
    }
  }
  v23 = 0;
  LODWORD(v43) = 0;
  if ( (*(_DWORD *)v11 & 0xFFFFFFF8) != 0 )
  {
    do
    {
      v24 = *((_QWORD *)v11[2] + v23);
      v25 = *(_DWORD *)(v24 + 48) >> 3;
      if ( v25 )
      {
        v26 = 0;
        v27 = v25;
        v28 = v45;
        do
        {
          v29 = *(_QWORD *)(v24 + 64);
          v30 = *(struct Configuration **)(v26 + v29);
          if ( *((_DWORD *)v30 + 4) && (*((_DWORD *)v30 + 4) != 2 || *((_DWORD *)v30 + 8) >= 8u) )
            v30 = Configuration::Invalidate(*(Configuration **)(v26 + v29));
          if ( v28 || *((_DWORD *)v30 + 146) >> ((*((_BYTE *)v30 + 592) & 1) == 0) == 1 )
            Configuration::SetRepository(v30, *((_QWORD *)v5 + 31), *((unsigned int *)v5 + 66));
          v26 += 8;
          --v27;
        }
        while ( v27 );
        v23 = (unsigned int)v43;
        v11 = v53;
      }
      Root::SetStatus(v24, 3);
      if ( a5 )
        WorkQueue::AppendJobToPrimaryList((CCorSvcMgr *)((char *)v5 + 104), (struct Root *)v24);
      LODWORD(v43) = ++v23;
      LODWORD(RootArray) = *(_DWORD *)v11 >> 3;
    }
    while ( v23 < (unsigned int)RootArray );
  }
  *((_DWORD *)v5 + 328) = 1;
  if ( (a3 & 2) != 0 )
  {
    LODWORD(RootArray) = (*(__int64 (__fastcall **)(__int64, __int64))(*((_QWORD *)v5 + 6) + 40LL))((__int64)v5 + 48, 3);
    if ( (int)RootArray < 0 )
      ThrowHR((int)RootArray);
  }
  if ( (v65 & 0x800000000LL) != 0 )
  {
    v31 = v66;
    if ( v66 )
    {
      v32 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v32 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v32;
      }
      LODWORD(RootArray) = HeapFree(v32, 0, v31);
    }
  }
  return (int)RootArray;
}

```

## disassembly

```asm
0x18001f180  mov     r11, rsp
0x18001f183  mov     [r11+18h], r8d
0x18001f187  push    rbx
0x18001f188  push    rsi
0x18001f189  push    rdi
0x18001f18a  push    r12
0x18001f18c  push    r13
0x18001f18e  push    r14
0x18001f190  push    r15
0x18001f192  sub     rsp, 360h
0x18001f199  mov     rax, cs:__security_cookie
0x18001f1a0  xor     rax, rsp
0x18001f1a3  mov     [rsp+398h+var_48], rax
0x18001f1ab  mov     r13, rcx
0x18001f1ae  mov     [rsp+398h+var_2B8], rcx
0x18001f1b6  mov     r12, rcx
0x18001f1b9  mov     [rsp+398h+var_2B0], rcx
0x18001f1c1  xor     ebx, ebx
0x18001f1c3  mov     edi, ebx
0x18001f1c5  mov     [rsp+398h+var_338], ebx
0x18001f1c9  mov     [r11-268h], rbx
0x18001f1d0  mov     qword ptr [r11-264h], 200h
0x18001f1db  mov     [r11-258h], rbx
0x18001f1e2  lea     rax, [r11-250h]
0x18001f1e9  mov     [r11-258h], rax
0x18001f1f0  mov     [rsp+398h+var_268], 2
0x18001f1fb  mov     rax, [r11-258h]
0x18001f202  mov     [rax], bx
0x18001f205  lea     rcx, [r11-268h]; this
0x18001f20c  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x18001f211  nop
0x18001f212  mov     ecx, [rsp+398h+var_260]
0x18001f219  not     ecx
0x18001f21b  lea     esi, [rbx+1]
0x18001f21e  and     ecx, esi
0x18001f220  mov     eax, [rsp+398h+var_268]
0x18001f227  shr     eax, cl
0x18001f229  cmp     eax, esi
0x18001f22b  jz      short loc_18001F2A3
0x18001f22d  lea     edx, [rbx+4]
0x18001f230  mov     dword ptr [rsp+398h+var_308], edx
0x18001f237  mov     dword ptr [rsp+398h+var_308+4], edx
0x18001f23e  mov     dword ptr [rsp+398h+var_308+8], 10h
0x18001f249  lea     rax, asc_180052DBC; "*"
0x18001f250  mov     [rsp+398h+var_2F8], rax
0x18001f258  mov     ecx, dword ptr [rsp+398h+var_308+8]
0x18001f25f  and     ecx, 0FFFFFFF8h
0x18001f262  mov     dword ptr [rsp+398h+var_308+8], ecx
0x18001f269  mov     eax, ecx
0x18001f26b  or      eax, edx
0x18001f26d  mov     dword ptr [rsp+398h+var_308+8], eax
0x18001f274  or      ecx, 104h
0x18001f27a  mov     dword ptr [rsp+398h+var_308+8], ecx
0x18001f281  mov     edi, esi
0x18001f283  mov     [rsp+398h+var_338], esi
0x18001f287  lea     rdx, [rsp+398h+var_308]; struct SString *
0x18001f28f  lea     rcx, [rsp+398h+var_268]; this
0x18001f297  call    ?Equals@SString@@QEBAHAEBV1@@Z; SString::Equals(SString const &)
0x18001f29c  test    eax, eax
0x18001f29e  mov     r14b, bl
0x18001f2a1  jz      short loc_18001F2A6
0x18001f2a3  mov     r14b, sil
0x18001f2a6  test    sil, dil
0x18001f2a9  jz      short loc_18001F2C9
0x18001f2ab  and     edi, 0FFFFFFFEh
0x18001f2ae  mov     [rsp+398h+var_338], edi
0x18001f2b2  test    byte ptr [rsp+398h+var_308+8], 8
0x18001f2ba  jz      short loc_18001F2C9
0x18001f2bc  mov     rcx, [rsp+398h+var_2F8]; lpMem
0x18001f2c4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f2c9  test    r14b, r14b
0x18001f2cc  jz      loc_18001F775
0x18001f2d2  xor     ecx, ecx; int
0x18001f2d4  call    ?GetRootList@@YAPEAVRootList@@H@Z; GetRootList(int)
0x18001f2d9  mov     rcx, rax
0x18001f2dc  call    ?GetRootArray@RootList@@QEAAPEAV?$ArrayOfPointers@VRoot@@@@XZ; RootList::GetRootArray(void)
0x18001f2e1  mov     r15, rax
0x18001f2e4  mov     [rsp+398h+var_2E0], rax
0x18001f2ec  mov     r14d, [rsp+398h+arg_10]
0x18001f2f4  and     r14d, esi
0x18001f2f7  mov     [rsp+398h+var_334], r14d
0x18001f2fc  mov     [rsp+398h+var_2E8], r14d
0x18001f304  jz      loc_18001F611
0x18001f30a  lea     rax, [rsp+398h+var_330]
0x18001f30f  mov     [rsp+398h+var_340], rax
0x18001f314  lea     rax, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x18001f31b  mov     [rsp+398h+var_330], rax
0x18001f320  or      [rsp+398h+hObject], 0FFFFFFFFFFFFFFFFh
0x18001f326  lea     rax, ??_7MachineWideMutexHolder@@6B@; const MachineWideMutexHolder::`vftable'
0x18001f32d  mov     [rsp+398h+var_330], rax
0x18001f332  xor     ecx, ecx; int
0x18001f334  call    ?GetRootList@@YAPEAVRootList@@H@Z; GetRootList(int)
0x18001f339  mov     rax, [rsp+398h+var_330]
0x18001f33e  mov     rax, [rax]
0x18001f341  lea     rcx, ?Acquire@MachineWideMutexHolder@@UEAAXPEBGPEAXPEAH@Z; MachineWideMutexHolder::Acquire(ushort const *,void *,int *)
0x18001f348  xor     r9d, r9d; int *
0x18001f34b  xor     r8d, r8d; void *
0x18001f34e  lea     rdx, aNgennicupdatel; "ngennicupdatelock.dat"
0x18001f355  cmp     rax, rcx
0x18001f358  lea     rcx, [rsp+398h+var_330]; this
0x18001f35d  jnz     short loc_18001F366
0x18001f35f  call    ?Acquire@MachineWideMutexHolder@@UEAAXPEBGPEAXPEAH@Z; MachineWideMutexHolder::Acquire(ushort const *,void *,int *)
0x18001f364  jmp     short loc_18001F36D
0x18001f366  call    cs:__guard_dispatch_icall_fptr
0x18001f36c  nop
0x18001f36d  call    ?IsUsingPrivateStore@Helpers@@SAHXZ; Helpers::IsUsingPrivateStore(void)
0x18001f372  test    eax, eax
0x18001f374  jz      loc_18001F42C
0x18001f37a  movups  xmm0, xmmword ptr [r13+110h]
0x18001f382  movdqu  [rsp+398h+var_2A8], xmm0
0x18001f38b  lea     rax, [r13+18h]
0x18001f38f  neg     r12
0x18001f392  sbb     r8, r8
0x18001f395  and     r8, rax
0x18001f398  mov     [rsp+398h+var_350], rbx
0x18001f39d  mov     [rsp+398h+var_360], rbx
0x18001f3a2  mov     [rsp+398h+var_370], rbx
0x18001f3a7  mov     [rsp+398h+var_378], rbx
0x18001f3ac  lea     r9, [rsp+398h+var_2A8]
0x18001f3b4  mov     rdx, [r13+510h]
0x18001f3bb  mov     rcx, r13
0x18001f3be  call    ?GetPooledSvcWorker@CCorSvcMgr@@AEAAPEAVWorkerPoolItem@1@PEAXPEAUICorSvcLogger@@U_NGenPrivateAttributes@@PEBG3HPEAGW4__MIDL___MIDL_itf_mscorsvc_0001_0004_0001@@PEAVLogicalImage@@@Z; CCorSvcMgr::GetPooledSvcWorker(void *,ICorSvcLogger *,_NGenPrivateAttributes,ushort const *,ushort const *,int,ushort *,__MIDL___MIDL_itf_mscorsvc_0001_0004_0001,LogicalImage *)
0x18001f3c3  mov     rdi, rax
0x18001f3c6  mov     [rsp+398h+var_320], rax
0x18001f3cb  mov     [rsp+398h+var_318], ebx
0x18001f3d2  mov     r14d, ebx
0x18001f3d5  test    rax, rax
0x18001f3d8  cmovnz  r14d, esi
0x18001f3dc  mov     [rsp+398h+var_318], r14d
0x18001f3e4  mov     rcx, [rax+18h]
0x18001f3e8  mov     rax, [rcx]
0x18001f3eb  xor     r8d, r8d
0x18001f3ee  xor     edx, edx
0x18001f3f0  mov     rax, [rax+28h]
0x18001f3f4  call    cs:__guard_dispatch_icall_fptr
0x18001f3fa  test    eax, eax
0x18001f3fc  js      loc_18001F780
0x18001f402  test    r14d, r14d
0x18001f405  jz      loc_18001F5E1
0x18001f40b  mov     rcx, rdi; this
0x18001f40e  call    ??1WorkerPoolItem@CCorSvcMgr@@QEAA@XZ; CCorSvcMgr::WorkerPoolItem::~WorkerPoolItem(void)
0x18001f413  mov     edx, 40h ; '@'; unsigned __int64
0x18001f418  mov     rcx, rdi; void *
0x18001f41b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f420  mov     [rsp+398h+var_318], ebx
0x18001f427  jmp     loc_18001F5E1
0x18001f42c  mov     [rsp+398h+lpMem], rbx
0x18001f434  mov     [rsp+398h+var_2C0], ebx
0x18001f43b  mov     dword ptr [rsp+398h+var_340], ebx
0x18001f43f  lea     r8, [rsp+398h+var_340]
0x18001f444  lea     rdx, [rsp+398h+lpMem]
0x18001f44c  call    ?GetNativeImageRuntimeVersions@CCorSvcMgr@@AEAAXAEAV?$NewArrayHolder@VVersionStr@@@@AEAI@Z; CCorSvcMgr::GetNativeImageRuntimeVersions(NewArrayHolder<VersionStr> &,uint &)
0x18001f451  mov     edi, ebx
0x18001f453  mov     [rsp+398h+var_344], ebx
0x18001f457  mov     r12, [rsp+398h+lpMem]
0x18001f45f  cmp     edi, dword ptr [rsp+398h+var_340]
0x18001f463  jnb     loc_18001F59D
0x18001f469  mov     [rsp+398h+var_2D8], ebx
0x18001f470  mov     [rsp+398h+var_2D0], rbx
0x18001f478  lea     rax, [rsp+398h+var_2D8]
0x18001f480  mov     [rsp+398h+var_278], rax
0x18001f488  movups  xmm0, xmmword ptr [r13+110h]
0x18001f490  movdqu  [rsp+398h+var_308], xmm0
0x18001f499  mov     edx, edi
0x18001f49b  shl     rdx, 6
0x18001f49f  add     rdx, r12
0x18001f4a2  mov     rcx, [rsp+398h+var_2B0]
0x18001f4aa  mov     rax, rcx
0x18001f4ad  add     rcx, 18h
0x18001f4b1  neg     rax
0x18001f4b4  sbb     r8, r8
0x18001f4b7  and     r8, rcx
0x18001f4ba  mov     [rsp+398h+var_350], rbx
0x18001f4bf  mov     [rsp+398h+var_360], rbx
0x18001f4c4  mov     [rsp+398h+var_370], rbx
0x18001f4c9  mov     [rsp+398h+var_378], rdx
0x18001f4ce  lea     r9, [rsp+398h+var_308]
0x18001f4d6  mov     rdx, [r13+510h]
0x18001f4dd  mov     rcx, r13
0x18001f4e0  call    ?GetPooledSvcWorker@CCorSvcMgr@@AEAAPEAVWorkerPoolItem@1@PEAXPEAUICorSvcLogger@@U_NGenPrivateAttributes@@PEBG3HPEAGW4__MIDL___MIDL_itf_mscorsvc_0001_0004_0001@@PEAVLogicalImage@@@Z; CCorSvcMgr::GetPooledSvcWorker(void *,ICorSvcLogger *,_NGenPrivateAttributes,ushort const *,ushort const *,int,ushort *,__MIDL___MIDL_itf_mscorsvc_0001_0004_0001,LogicalImage *)
0x18001f4e5  mov     r15, rax
0x18001f4e8  mov     qword ptr [rsp+398h+var_2A8], rax
0x18001f4f0  mov     r14d, ebx
0x18001f4f3  mov     dword ptr [rsp+398h+var_2A8+8], ebx
0x18001f4fa  test    rax, rax
0x18001f4fd  jz      short loc_18001F509
0x18001f4ff  mov     r14d, esi
0x18001f502  mov     dword ptr [rsp+398h+var_2A8+8], esi
0x18001f509  mov     rcx, [rax+18h]
0x18001f50d  mov     rax, [rcx]
0x18001f510  xor     r8d, r8d
0x18001f513  xor     edx, edx
0x18001f515  mov     rax, [rax+28h]
0x18001f519  call    cs:__guard_dispatch_icall_fptr
0x18001f51f  test    eax, eax
0x18001f521  js      loc_18001F788
0x18001f527  test    r14d, r14d
0x18001f52a  jz      short loc_18001F548
0x18001f52c  mov     rcx, r15; this
0x18001f52f  call    ??1WorkerPoolItem@CCorSvcMgr@@QEAA@XZ; CCorSvcMgr::WorkerPoolItem::~WorkerPoolItem(void)
0x18001f534  mov     edx, 40h ; '@'; unsigned __int64
0x18001f539  mov     rcx, r15; void *
0x18001f53c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f541  mov     dword ptr [rsp+398h+var_2A8+8], ebx
0x18001f548  jmp     short loc_18001F576
0x18001f54a  xor     ebx, ebx
0x18001f54c  lea     esi, [rbx+1]
0x18001f54f  mov     r12, [rsp+398h+lpMem]
0x18001f557  mov     edi, [rsp+398h+var_344]
0x18001f55b  mov     r13, [rsp+398h+var_2B8]
0x18001f563  mov     [rsp+398h+var_2B0], r13
0x18001f56b  mov     eax, [rsp+398h+var_2E8]
0x18001f572  mov     [rsp+398h+var_334], eax
0x18001f576  test    byte ptr [rsp+398h+var_2D8], 2
0x18001f57e  jz      short loc_18001F592
0x18001f580  mov     rax, cs:?g_fpHandleStackOverflowAfterCatch@@3P6AXXZEA; void (*g_fpHandleStackOverflowAfterCatch)(void)
0x18001f587  test    rax, rax
0x18001f58a  jz      short loc_18001F592
0x18001f58c  call    cs:__guard_dispatch_icall_fptr
0x18001f592  add     edi, esi
0x18001f594  mov     [rsp+398h+var_344], edi
0x18001f598  jmp     loc_18001F45F
0x18001f59d  cmp     [rsp+398h+var_2C0], ebx
0x18001f5a4  jz      short loc_18001F5D9
0x18001f5a6  test    r12, r12
0x18001f5a9  jz      short loc_18001F5D2
0x18001f5ab  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001f5b2  test    rax, rax
0x18001f5b5  jnz     short loc_18001F5C4
0x18001f5b7  call    cs:__imp_GetProcessHeap
0x18001f5bd  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001f5c4  mov     r8, r12; lpMem
0x18001f5c7  xor     edx, edx; dwFlags
0x18001f5c9  mov     rcx, rax; hHeap
0x18001f5cc  call    cs:__imp_HeapFree
0x18001f5d2  mov     [rsp+398h+var_2C0], ebx
0x18001f5d9  mov     r15, [rsp+398h+var_2E0]
0x18001f5e1  lea     rax, [rsp+398h+var_330]
0x18001f5e6  mov     [rsp+398h+var_278], rax
0x18001f5ee  lea     rax, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x18001f5f5  mov     [rsp+398h+var_330], rax
0x18001f5fa  mov     rcx, [rsp+398h+hObject]; hObject
0x18001f5ff  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001f603  jz      short loc_18001F611
0x18001f605  call    cs:__imp_CloseHandle
0x18001f60b  or      [rsp+398h+hObject], 0FFFFFFFFFFFFFFFFh
0x18001f611  mov     edi, ebx
0x18001f613  mov     dword ptr [rsp+398h+var_340], ebx
0x18001f617  test    dword ptr [r15], 0FFFFFFF8h
0x18001f61e  jbe     loc_18001F6E7
0x18001f624  mov     ecx, edi
0x18001f626  mov     rax, [r15+10h]
0x18001f62a  mov     r14, [rax+rcx*8]
0x18001f62e  mov     eax, [r14+30h]
0x18001f632  shr     eax, 3
0x18001f635  test    eax, eax
0x18001f637  jz      short loc_18001F6B1
0x18001f639  mov     r15, rbx
0x18001f63c  mov     r12d, eax
0x18001f63f  mov     edi, [rsp+398h+var_334]
0x18001f643  mov     rax, [r14+40h]
0x18001f647  mov     r9, [r15+rax]
0x18001f64b  cmp     [r9+10h], ebx
0x18001f64f  jz      short loc_18001F66A
0x18001f651  cmp     dword ptr [r9+10h], 2
0x18001f656  jnz     short loc_18001F65F
0x18001f658  cmp     dword ptr [r9+20h], 8
0x18001f65d  jb      short loc_18001F66A
0x18001f65f  mov     rcx, r9; this
0x18001f662  call    ?Invalidate@Configuration@@QEAAPEAV1@XZ; Configuration::Invalidate(void)
0x18001f667  mov     r9, rax
0x18001f66a  test    edi, edi
0x18001f66c  jnz     short loc_18001F686
0x18001f66e  mov     ecx, [r9+250h]
0x18001f675  not     ecx
0x18001f677  and     ecx, esi
0x18001f679  mov     eax, [r9+248h]
0x18001f680  shr     eax, cl
0x18001f682  cmp     eax, esi
0x18001f684  jnz     short loc_18001F69C
0x18001f686  mov     r8d, [r13+108h]
0x18001f68d  mov     rdx, [r13+0F8h]
0x18001f694  mov     rcx, r9
0x18001f697  call    ?SetRepository@Configuration@@QEAAXPEBGW4__MIDL___MIDL_itf_mscorsvc_0001_0008_0001@@@Z; Configuration::SetRepository(ushort const *,__MIDL___MIDL_itf_mscorsvc_0001_0008_0001)
0x18001f69c  add     r15, 8
0x18001f6a0  sub     r12, rsi
0x18001f6a3  jnz     short loc_18001F643
0x18001f6a5  mov     edi, dword ptr [rsp+398h+var_340]
0x18001f6a9  mov     r15, [rsp+398h+var_2E0]
0x18001f6b1  mov     edx, 3
0x18001f6b6  mov     rcx, r14
0x18001f6b9  call    ?SetStatus@Root@@QEAAXW4EntryStatus@@@Z; Root::SetStatus(EntryStatus)
0x18001f6be  cmp     [rsp+398h+arg_20], bl
0x18001f6c5  jz      short loc_18001F6D3
0x18001f6c7  lea     rcx, [r13+68h]; this
0x18001f6cb  mov     rdx, r14; struct Root *
0x18001f6ce  call    ?AppendJobToPrimaryList@WorkQueue@@QEAAXPEAVRoot@@@Z; WorkQueue::AppendJobToPrimaryList(Root *)
0x18001f6d3  add     edi, esi
0x18001f6d5  mov     dword ptr [rsp+398h+var_340], edi
0x18001f6d9  mov     eax, [r15]
  ... truncated ...
```
