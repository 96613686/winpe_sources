# DestroyNotifyCommon(_CNOTIFY *,int)

- ea: `0x18005c424`
- end: `0x18005c6d1`
- name: `?DestroyNotifyCommon@@YAXPEAU_CNOTIFY@@H@Z`
- size: `685`
- prototype: `void __fastcall(HLOCAL hMem, int)`
- caller_count: `4`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18005cbb4`
- `0x18005e7c0`
- `0x18005e840`
- `0x18005ea10`

## callees

- `0x180019b68`
- `0x18001cff4`
- `0x180023bf4`
- `0x180026ae0`
- `0x18005b184`
- `0x18005c424`
- `0x18005c6d8`
- `0x18005c960`
- `0x18009e1f8`
- `0x1800a2ddc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005c5a5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005c605`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005c5a5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005c605`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005c69b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005c69b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c571`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c5fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c571`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c5fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005c48e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005c59b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005c48e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005c59b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c6b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c6b8`

## pseudocode

```c
void __fastcall DestroyNotifyCommon(char *hMem, int a2)
{
  char *v3; // rsi
  __int64 v4; // rbx
  _QWORD **v5; // rcx
  _QWORD *v6; // rax
  _QWORD *v7; // rdx
  __int64 v8; // r9
  _QWORD *v9; // r8
  HLOCAL *v10; // r8
  bool v11; // si
  __int64 v12; // rdx
  __int128 *v13; // rbx
  __int64 v14; // r8
  char *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  _CNOTIFY_EVENT **v18; // r14
  _CNOTIFY_EVENT *v19; // rsi
  _CNOTIFY_EVENT *v20; // rax
  unsigned int v21; // edx
  __int128 v22; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v23[16]; // [rsp+30h] [rbp-10h] BYREF
  char *v24; // [rsp+60h] [rbp+20h] BYREF

  v22 = 0;
  if ( a2 )
  {
    cxl::AcquireWriteLock::AcquireWriteLock((cxl::AcquireWriteLock *)v23, (RTL_SRWLOCK *)g_handleValidator);
    v24 = hMem;
    std::_Hash<std::_Uset_traits<void *,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<void *>,0>>::_Erase<void *>(
      &qword_180123EC0,
      &v24);
    cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(v23);
  }
  while ( 1 )
  {
    v3 = *(char **)hMem;
    if ( *(char **)hMem == hMem )
      break;
    v4 = *((_QWORD *)v3 + 6);
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 232));
    v5 = (_QWORD **)(v3 + 32);
    while ( 1 )
    {
      v6 = *v5;
      if ( *v5 == v5 )
        break;
      if ( (_QWORD **)v6[1] != v5 )
        goto LABEL_38;
      v7 = (_QWORD *)*v6;
      if ( *(_QWORD **)(*v6 + 8LL) != v6 )
        goto LABEL_38;
      *v5 = v7;
      v7[1] = v5;
      v8 = v6[2];
      if ( *(_QWORD **)(v8 + 8) != v6 + 2 )
        goto LABEL_38;
      v9 = (_QWORD *)v6[3];
      if ( (_QWORD *)*v9 != v6 + 2 )
        goto LABEL_38;
      *v9 = v8;
      *(_QWORD *)(v8 + 8) = v9;
      v10 = (HLOCAL *)*((_QWORD *)hMem + 96);
      if ( *v10 != hMem + 760 )
        goto LABEL_38;
      *v6 = hMem + 760;
      v6[1] = v10;
      *v10 = v6;
      *((_QWORD *)hMem + 96) = v6;
    }
    DestroySession((struct _CNOTIFY_SESSION *)v3);
    v11 = (*(_BYTE *)(v4 + 32) & 1) != 0
       && *(_QWORD *)(v4 + 56) == v4 + 56
       && *(_QWORD *)(v4 + 88) == v4 + 88
       && *(_QWORD *)(v4 + 104) == v4 + 104
       && *(_QWORD *)(v4 + 72) == v4 + 72
       && *(_QWORD *)(v4 + 120) == v4 + 120
       && *(_QWORD *)(v4 + 168) == v4 + 168
       && *(_QWORD *)(v4 + 184) == v4 + 184
       && *(_QWORD *)(v4 + 136) == v4 + 136;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 232));
    if ( v11 )
      FreeClusterCommon((struct _CLUSTER *)v4, v12, 1);
  }
  v13 = (__int128 *)(hMem + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)(hMem + 72));
  SetEvent(*((HANDLE *)hMem + 16));
  if ( *(__int128 **)v13 == v13 )
  {
    *((_QWORD *)&v22 + 1) = &v22;
    *(_QWORD *)&v22 = &v22;
  }
  else
  {
    v22 = *v13;
    *(_QWORD *)(v22 + 8) = &v22;
    **((_QWORD **)&v22 + 1) = &v22;
  }
  *((_QWORD *)hMem + 8) = 0;
  *(_QWORD *)v13 = 0;
  *((_DWORD *)hMem + 30) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(hMem + 72));
  SetEvent(*((HANDLE *)hMem + 14));
  while ( 1 )
  {
    v15 = (char *)v22;
    if ( (__int128 *)v22 == &v22 )
      break;
    if ( *(__int128 **)(v22 + 8) != &v22 || (v16 = *(_QWORD *)v22, *(_QWORD *)(*(_QWORD *)v22 + 8LL) != (_QWORD)v22) )
LABEL_38:
      __fastfail(3u);
    *(_QWORD *)&v22 = *(_QWORD *)v22;
    *(_QWORD *)(v16 + 8) = &v22;
    v17 = *((unsigned int *)hMem + 194);
    v24 = v15;
    FreePacket(&v24, v17, 0);
  }
  v18 = (_CNOTIFY_EVENT **)(hMem + 760);
  while ( 1 )
  {
    v19 = *v18;
    if ( *v18 == (_CNOTIFY_EVENT *)v18 )
      break;
    if ( *((_CNOTIFY_EVENT ***)v19 + 1) != v18 )
      goto LABEL_38;
    v20 = *(_CNOTIFY_EVENT **)v19;
    if ( *(_CNOTIFY_EVENT **)(*(_QWORD *)v19 + 8LL) != v19 )
      goto LABEL_38;
    *v18 = v20;
    *((_QWORD *)v20 + 1) = v18;
    LOBYTE(v14) = 1;
    FreePacket((char *)v19 + 128, *((unsigned int *)v19 + 26), v14);
    _CNOTIFY_EVENT::`scalar deleting destructor'(v19, v21);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(hMem + 16));
  ClRtlDeleteQueue(hMem + 56);
  ClRtlDeleteHash((LPCRITICAL_SECTION)(hMem + 136));
  LocalFree(hMem);
}

```

## disassembly

```asm
0x18005c424  mov     [rsp-18h+arg_8], rbx
0x18005c429  mov     [rsp-18h+arg_10], rsi
0x18005c42e  push    rbp
0x18005c42f  push    rdi
0x18005c430  push    r14
0x18005c432  mov     rbp, rsp
0x18005c435  sub     rsp, 40h
0x18005c439  xorps   xmm0, xmm0
0x18005c43c  mov     rdi, rcx
0x18005c43f  movups  [rbp+var_20], xmm0
0x18005c443  test    edx, edx
0x18005c445  jz      short loc_18005C474
0x18005c447  lea     rdx, ?g_handleValidator@@3U?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@A; struct cxl::NonReentrantRWLock *
0x18005c44e  lea     rcx, [rbp+var_10]; this
0x18005c452  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x18005c457  lea     rdx, [rbp+arg_0]
0x18005c45b  mov     [rbp+arg_0], rdi
0x18005c45f  lea     rcx, qword_180123EC0
0x18005c466  call    ??$_Erase@PEAX@?$_Hash@V?$_Uset_traits@PEAXV?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$allocator@PEAX@2@$0A@@std@@@std@@AEAA_KAEBQEAX@Z; std::_Hash<std::_Uset_traits<void *,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<void *>,0>>::_Erase<void *>(void * const &)
0x18005c46b  lea     rcx, [rbp+var_10]
0x18005c46f  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18005c474  mov     rsi, [rdi]
0x18005c477  cmp     rsi, rdi
0x18005c47a  jz      loc_18005C593
0x18005c480  mov     rbx, [rsi+30h]
0x18005c484  lea     r14, [rbx+0E8h]
0x18005c48b  mov     rcx, r14; lpCriticalSection
0x18005c48e  call    cs:__imp_EnterCriticalSection
0x18005c494  lea     rcx, [rsi+20h]
0x18005c498  mov     rax, [rcx]
0x18005c49b  cmp     rax, rcx
0x18005c49e  jz      short loc_18005C507
0x18005c4a0  cmp     [rax+8], rcx
0x18005c4a4  jnz     loc_18005C690
0x18005c4aa  mov     rdx, [rax]
0x18005c4ad  cmp     [rdx+8], rax
0x18005c4b1  jnz     loc_18005C690
0x18005c4b7  mov     [rcx], rdx
0x18005c4ba  mov     [rdx+8], rcx
0x18005c4be  lea     rdx, [rax+10h]
0x18005c4c2  mov     r9, [rdx]
0x18005c4c5  cmp     [r9+8], rdx
0x18005c4c9  jnz     loc_18005C690
0x18005c4cf  mov     r8, [rax+18h]
0x18005c4d3  cmp     [r8], rdx
0x18005c4d6  jnz     loc_18005C690
0x18005c4dc  mov     [r8], r9
0x18005c4df  lea     rdx, [rdi+2F8h]
0x18005c4e6  mov     [r9+8], r8
0x18005c4ea  mov     r8, [rdx+8]
0x18005c4ee  cmp     [r8], rdx
0x18005c4f1  jnz     loc_18005C690
0x18005c4f7  mov     [rax], rdx
0x18005c4fa  mov     [rax+8], r8
0x18005c4fe  mov     [r8], rax
0x18005c501  mov     [rdx+8], rax
0x18005c505  jmp     short loc_18005C498
0x18005c507  mov     rcx, rsi; struct _CNOTIFY_SESSION *
0x18005c50a  call    ?DestroySession@@YAXPEAU_CNOTIFY_SESSION@@@Z; DestroySession(_CNOTIFY_SESSION *)
0x18005c50f  test    byte ptr [rbx+20h], 1
0x18005c513  jz      short loc_18005C56B
0x18005c515  lea     rax, [rbx+38h]
0x18005c519  cmp     [rax], rax
0x18005c51c  jnz     short loc_18005C56B
0x18005c51e  lea     rax, [rbx+58h]
0x18005c522  cmp     [rax], rax
0x18005c525  jnz     short loc_18005C56B
0x18005c527  lea     rax, [rbx+68h]
0x18005c52b  cmp     [rax], rax
0x18005c52e  jnz     short loc_18005C56B
0x18005c530  lea     rax, [rbx+48h]
0x18005c534  cmp     [rax], rax
0x18005c537  jnz     short loc_18005C56B
0x18005c539  lea     rax, [rbx+78h]
0x18005c53d  cmp     [rax], rax
0x18005c540  jnz     short loc_18005C56B
0x18005c542  lea     rax, [rbx+0A8h]
0x18005c549  cmp     [rax], rax
0x18005c54c  jnz     short loc_18005C56B
0x18005c54e  lea     rax, [rbx+0B8h]
0x18005c555  cmp     [rax], rax
0x18005c558  jnz     short loc_18005C56B
0x18005c55a  lea     rax, [rbx+88h]
0x18005c561  cmp     [rax], rax
0x18005c564  jnz     short loc_18005C56B
0x18005c566  mov     sil, 1
0x18005c569  jmp     short loc_18005C56E
0x18005c56b  xor     sil, sil
0x18005c56e  mov     rcx, r14; lpCriticalSection
0x18005c571  call    cs:__imp_LeaveCriticalSection
0x18005c577  test    sil, sil
0x18005c57a  jz      loc_18005C474
0x18005c580  mov     r8d, 1; int
0x18005c586  mov     rcx, rbx; struct _CLUSTER *
0x18005c589  call    ?FreeClusterCommon@@YAXPEAU_CLUSTER@@HH@Z; FreeClusterCommon(_CLUSTER *,int,int)
0x18005c58e  jmp     loc_18005C474
0x18005c593  lea     rbx, [rdi+38h]
0x18005c597  lea     rcx, [rbx+10h]; lpCriticalSection
0x18005c59b  call    cs:__imp_EnterCriticalSection
0x18005c5a1  mov     rcx, [rbx+48h]; hEvent
0x18005c5a5  call    cs:__imp_SetEvent
0x18005c5ab  cmp     [rbx], rbx
0x18005c5ae  jnz     short loc_18005C5C2
0x18005c5b0  lea     rax, [rbp+var_20]
0x18005c5b4  mov     qword ptr [rbp+var_20+8], rax
0x18005c5b8  lea     rax, [rbp+var_20]
0x18005c5bc  mov     qword ptr [rbp+var_20], rax
0x18005c5c0  jmp     short loc_18005C5E1
0x18005c5c2  movups  xmm0, xmmword ptr [rbx]
0x18005c5c5  lea     rcx, [rbp+var_20]
0x18005c5c9  movups  [rbp+var_20], xmm0
0x18005c5cd  movq    rax, xmm0
0x18005c5d2  mov     [rax+8], rcx
0x18005c5d6  lea     rcx, [rbp+var_20]
0x18005c5da  mov     rax, qword ptr [rbp+var_20+8]
0x18005c5de  mov     [rax], rcx
0x18005c5e1  lea     rcx, [rbx+10h]; lpCriticalSection
0x18005c5e5  mov     qword ptr [rbx+8], 0
0x18005c5ed  mov     qword ptr [rbx], 0
0x18005c5f4  mov     dword ptr [rbx+40h], 0
0x18005c5fb  call    cs:__imp_LeaveCriticalSection
0x18005c601  mov     rcx, [rbx+38h]; hEvent
0x18005c605  call    cs:__imp_SetEvent
0x18005c60b  mov     rax, qword ptr [rbp+var_20]
0x18005c60f  lea     rcx, [rbp+var_20]
0x18005c613  cmp     rax, rcx
0x18005c616  jz      short loc_18005C64F
0x18005c618  lea     rcx, [rbp+var_20]
0x18005c61c  cmp     [rax+8], rcx
0x18005c620  jnz     short loc_18005C690
0x18005c622  mov     rcx, [rax]
0x18005c625  cmp     [rcx+8], rax
0x18005c629  jnz     short loc_18005C690
0x18005c62b  lea     rdx, [rbp+var_20]
0x18005c62f  mov     qword ptr [rbp+var_20], rcx
0x18005c633  mov     [rcx+8], rdx
0x18005c637  xor     r8d, r8d
0x18005c63a  mov     edx, [rdi+308h]
0x18005c640  lea     rcx, [rbp+arg_0]
0x18005c644  mov     [rbp+arg_0], rax
0x18005c648  call    ?FreePacket@@YAKAEAPEAU_CNOTIFY_PACKET@@W4CLUSTER_NOTIFICATIONS_VERSION@@_N@Z; FreePacket(_CNOTIFY_PACKET * &,CLUSTER_NOTIFICATIONS_VERSION,bool)
0x18005c64d  jmp     short loc_18005C60B
0x18005c64f  lea     r14, [rdi+2F8h]
0x18005c656  mov     rsi, [r14]
0x18005c659  cmp     rsi, r14
0x18005c65c  jz      short loc_18005C697
0x18005c65e  cmp     [rsi+8], r14
0x18005c662  jnz     short loc_18005C690
0x18005c664  mov     rax, [rsi]
0x18005c667  cmp     [rax+8], rsi
0x18005c66b  jnz     short loc_18005C690
0x18005c66d  mov     [r14], rax
0x18005c670  lea     rcx, [rsi+80h]
0x18005c677  mov     [rax+8], r14
0x18005c67b  mov     r8b, 1
0x18005c67e  mov     edx, [rsi+68h]
0x18005c681  call    ?FreePacket@@YAKAEAPEAU_CNOTIFY_PACKET@@W4CLUSTER_NOTIFICATIONS_VERSION@@_N@Z; FreePacket(_CNOTIFY_PACKET * &,CLUSTER_NOTIFICATIONS_VERSION,bool)
0x18005c686  mov     rcx, rsi; this
0x18005c689  call    ??_G_CNOTIFY_EVENT@@QEAAPEAXI@Z; _CNOTIFY_EVENT::`scalar deleting destructor'(uint)
0x18005c68e  jmp     short loc_18005C656
0x18005c690  mov     ecx, 3
0x18005c695  int     29h; Win8: RtlFailFast(ecx)
0x18005c697  lea     rcx, [rdi+10h]; lpCriticalSection
0x18005c69b  call    cs:__imp_DeleteCriticalSection
0x18005c6a1  mov     rcx, rbx; void *
0x18005c6a4  call    ClRtlDeleteQueue
0x18005c6a9  lea     rcx, [rdi+88h]; lpCriticalSection
0x18005c6b0  call    ClRtlDeleteHash
0x18005c6b5  mov     rcx, rdi; hMem
0x18005c6b8  call    cs:__imp_LocalFree
0x18005c6be  mov     rbx, [rsp+40h+arg_8]
0x18005c6c3  mov     rsi, [rsp+40h+arg_10]
0x18005c6c8  add     rsp, 40h
0x18005c6cc  pop     r14
0x18005c6ce  pop     rdi
0x18005c6cf  pop     rbp
0x18005c6d0  retn
```
