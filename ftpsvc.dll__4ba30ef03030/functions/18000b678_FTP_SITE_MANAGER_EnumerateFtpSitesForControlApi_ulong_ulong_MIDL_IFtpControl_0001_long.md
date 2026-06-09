# FTP_SITE_MANAGER::EnumerateFtpSitesForControlApi(ulong *,ulong * *,__MIDL_IFtpControl_0001 * *,long * *)

- ea: `0x18000b678`
- end: `0x18000b87f`
- name: `?EnumerateFtpSitesForControlApi@FTP_SITE_MANAGER@@QEAAJPEAKPEAPEAKPEAPEAW4__MIDL_IFtpControl_0001@@PEAPEAJ@Z`
- size: `519`
- prototype: `__int64 __fastcall(FTP_SITE_MANAGER *__hidden this, unsigned int *, unsigned int **, enum __MIDL_IFtpControl_0001 **, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x1800166d0`

## callees

- `0x180001250`
- `0x180008f40`
- `0x18000b678`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000b707`
- `ole32!CoTaskMemAlloc` at `0x18000b724`
- `ole32!CoTaskMemAlloc` at `0x18000b735`
- `ole32!CoTaskMemAlloc` at `0x18000b707`
- `ole32!CoTaskMemAlloc` at `0x18000b724`
- `ole32!CoTaskMemAlloc` at `0x18000b735`
- `ole32!CoTaskMemFree` at `0x18000b851`
- `ole32!CoTaskMemFree` at `0x18000b85f`
- `ole32!CoTaskMemFree` at `0x18000b851`
- `ole32!CoTaskMemFree` at `0x18000b85f`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b6b2`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b6b2`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b843`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b843`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18000b6f8`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18000b6f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FTP_SITE_MANAGER::EnumerateFtpSitesForControlApi(
        FTP_SITE_MANAGER *this,
        unsigned int *a2,
        unsigned int **a3,
        enum __MIDL_IFtpControl_0001 **a4,
        int **a5)
{
  SIZE_T v8; // rbx
  unsigned int *v9; // r14
  enum __MIDL_IFtpControl_0001 *v10; // rdi
  unsigned int v11; // ebx
  int *v12; // rsi
  __int64 v13; // r15
  __int64 v14; // rax
  __int64 v15; // rcx
  FTP_SITE *v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rcx
  FTP_SITE *v19; // rsi
  _QWORD v21[2]; // [rsp+20h] [rbp-30h] BYREF
  _QWORD v22[4]; // [rsp+30h] [rbp-20h] BYREF
  CReaderWriterLock3 *v23; // [rsp+90h] [rbp+40h]

  v23 = (FTP_SITE_MANAGER *)((char *)this + 192);
  CReaderWriterLock3::WriteLock((FTP_SITE_MANAGER *)((char *)this + 192));
  v22[0] = 0;
  v21[1] = v21;
  v21[0] = v21;
  v22[1] = &FTP_SITE_MANAGER::BuildFtpSiteGlobalEnumerationListAction;
  v22[2] = v21;
  v8 = 4LL
     * (unsigned int)CLKRHashTable::Apply(
                       (char *)this + 8,
                       CTypedHashTable<FTP_LOG_FILE_TABLE,FTP_LOG_FILE,unsigned short const *,CLKRHashTable>::_Action,
                       v22,
                       2);
  v9 = (unsigned int *)CoTaskMemAlloc(v8);
  if ( !v9 )
  {
    v10 = 0;
LABEL_3:
    v11 = -2147024882;
    goto LABEL_13;
  }
  v10 = (enum __MIDL_IFtpControl_0001 *)CoTaskMemAlloc(v8);
  if ( !v10 )
    goto LABEL_3;
  v12 = (int *)CoTaskMemAlloc(v8);
  if ( !v12 )
    goto LABEL_3;
  v13 = 0;
  while ( 1 )
  {
    v14 = v21[0];
    if ( (_QWORD *)v21[0] == v21 )
      break;
    if ( *(_QWORD **)(v21[0] + 8LL) != v21 || (v15 = *(_QWORD *)v21[0], *(_QWORD *)(*(_QWORD *)v21[0] + 8LL) != v21[0]) )
LABEL_19:
      __fastfail(3u);
    v21[0] = *(_QWORD *)v21[0];
    v16 = (FTP_SITE *)(v14 - 280);
    *(_QWORD *)(v15 + 8) = v21;
    v9[v13] = *(_DWORD *)(v14 - 280 + 4);
    *((_DWORD *)v10 + v13) = *(_DWORD *)(v14 - 280 + 296);
    v12[v13] = *(_DWORD *)(v14 - 280 + 308);
    v13 = (unsigned int)(v13 + 1);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v14 - 280 + 176), 0xFFFFFFFF) == 1 )
    {
      FTP_SITE::~FTP_SITE(v16);
      operator delete(v16);
    }
  }
  *a2 = v13;
  *a3 = v9;
  v9 = 0;
  *a4 = v10;
  v10 = 0;
  v11 = 0;
  *a5 = v12;
LABEL_13:
  while ( 1 )
  {
    v17 = v21[0];
    if ( (_QWORD *)v21[0] == v21 )
      break;
    if ( *(_QWORD **)(v21[0] + 8LL) != v21 )
      goto LABEL_19;
    v18 = *(_QWORD *)v21[0];
    if ( *(_QWORD *)(*(_QWORD *)v21[0] + 8LL) != v21[0] )
      goto LABEL_19;
    v21[0] = *(_QWORD *)v21[0];
    v19 = (FTP_SITE *)(v17 - 280);
    *(_QWORD *)(v18 + 8) = v21;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v17 - 280 + 176), 0xFFFFFFFF) == 1 && v17 != 280 )
    {
      FTP_SITE::~FTP_SITE(v19);
      operator delete(v19);
    }
  }
  CReaderWriterLock3::WriteUnlock(v23);
  if ( v10 )
    CoTaskMemFree(v10);
  if ( v9 )
    CoTaskMemFree(v9);
  return v11;
}

```

## disassembly

```asm
0x18000b678  mov     [rsp-38h+arg_10], rbx
0x18000b67d  mov     [rsp-38h+arg_8], rdx
0x18000b682  push    rbp
0x18000b683  push    rsi
0x18000b684  push    rdi
0x18000b685  push    r12
0x18000b687  push    r13
0x18000b689  push    r14
0x18000b68b  push    r15
0x18000b68d  mov     rbp, rsp
0x18000b690  sub     rsp, 50h
0x18000b694  lea     rsi, [rcx+0C0h]
0x18000b69b  mov     rbx, rcx
0x18000b69e  xorps   xmm0, xmm0
0x18000b6a1  mov     [rbp+arg_0], rsi
0x18000b6a5  mov     rcx, rsi
0x18000b6a8  mov     r12, r9
0x18000b6ab  mov     r13, r8
0x18000b6ae  movups  [rbp+var_30], xmm0
0x18000b6b2  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000b6b8  lea     rax, [rbp+var_30]
0x18000b6bc  mov     [rbp+var_20], 0
0x18000b6c4  mov     qword ptr [rbp+var_30+8], rax
0x18000b6c8  lea     rcx, [rbx+8]
0x18000b6cc  lea     rax, [rbp+var_30]
0x18000b6d0  mov     r9d, 2
0x18000b6d6  mov     qword ptr [rbp+var_30], rax
0x18000b6da  lea     r8, [rbp+var_20]
0x18000b6de  lea     rax, ?BuildFtpSiteGlobalEnumerationListAction@FTP_SITE_MANAGER@@SA?AW4LK_ACTION@@PEAVFTP_SITE@@PEAX@Z; FTP_SITE_MANAGER::BuildFtpSiteGlobalEnumerationListAction(FTP_SITE *,void *)
0x18000b6e5  mov     [rbp+var_18], rax
0x18000b6e9  lea     rdx, ?_Action@?$CTypedHashTable@VFTP_LOG_FILE_TABLE@@VFTP_LOG_FILE@@PEBGVCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z; CTypedHashTable<FTP_LOG_FILE_TABLE,FTP_LOG_FILE,ushort const *,CLKRHashTable>::_Action(void const *,void *)
0x18000b6f0  lea     rax, [rbp+var_30]
0x18000b6f4  mov     [rbp+var_10], rax
0x18000b6f8  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x18000b6fe  mov     ebx, eax
0x18000b700  shl     rbx, 2
0x18000b704  mov     rcx, rbx; cb
0x18000b707  call    cs:__imp_CoTaskMemAlloc
0x18000b70d  mov     r14, rax
0x18000b710  test    rax, rax
0x18000b713  jnz     short loc_18000B721
0x18000b715  xor     edi, edi
0x18000b717  mov     ebx, 8007000Eh
0x18000b71c  jmp     loc_18000B7DE
0x18000b721  mov     rcx, rbx; cb
0x18000b724  call    cs:__imp_CoTaskMemAlloc
0x18000b72a  mov     rdi, rax
0x18000b72d  test    rax, rax
0x18000b730  jz      short loc_18000B717
0x18000b732  mov     rcx, rbx; cb
0x18000b735  call    cs:__imp_CoTaskMemAlloc
0x18000b73b  mov     rsi, rax
0x18000b73e  test    rax, rax
0x18000b741  jz      short loc_18000B717
0x18000b743  xor     r15d, r15d
0x18000b746  mov     rax, qword ptr [rbp+var_30]
0x18000b74a  lea     rcx, [rbp+var_30]
0x18000b74e  cmp     rax, rcx
0x18000b751  jz      short loc_18000B7C1
0x18000b753  lea     rcx, [rbp+var_30]
0x18000b757  cmp     [rax+8], rcx
0x18000b75b  jnz     loc_18000B838
0x18000b761  mov     rcx, [rax]
0x18000b764  cmp     [rcx+8], rax
0x18000b768  jnz     loc_18000B838
0x18000b76e  mov     qword ptr [rbp+var_30], rcx
0x18000b772  lea     rbx, [rax-118h]
0x18000b779  lea     rdx, [rbp+var_30]
0x18000b77d  mov     [rcx+8], rdx
0x18000b781  mov     eax, [rbx+4]
0x18000b784  mov     [r14+r15*4], eax
0x18000b788  mov     eax, [rbx+128h]
0x18000b78e  mov     [rdi+r15*4], eax
0x18000b792  mov     eax, [rbx+134h]
0x18000b798  mov     [rsi+r15*4], eax
0x18000b79c  inc     r15d
0x18000b79f  or      eax, 0FFFFFFFFh
0x18000b7a2  lock xadd [rbx+0B0h], eax
0x18000b7aa  cmp     eax, 1
0x18000b7ad  jnz     short loc_18000B746
0x18000b7af  mov     rcx, rbx; this
0x18000b7b2  call    ??1FTP_SITE@@AEAA@XZ; FTP_SITE::~FTP_SITE(void)
0x18000b7b7  mov     rcx, rbx; Block
0x18000b7ba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b7bf  jmp     short loc_18000B746
0x18000b7c1  mov     rax, [rbp+arg_8]
0x18000b7c5  mov     [rax], r15d
0x18000b7c8  mov     rax, [rbp+arg_20]
0x18000b7cc  mov     [r13+0], r14
0x18000b7d0  xor     r14d, r14d
0x18000b7d3  mov     [r12], rdi
0x18000b7d7  xor     edi, edi
0x18000b7d9  xor     ebx, ebx
0x18000b7db  mov     [rax], rsi
0x18000b7de  mov     rax, qword ptr [rbp+var_30]
0x18000b7e2  lea     rcx, [rbp+var_30]
0x18000b7e6  cmp     rax, rcx
0x18000b7e9  jz      short loc_18000B83F
0x18000b7eb  lea     rcx, [rbp+var_30]
0x18000b7ef  cmp     [rax+8], rcx
0x18000b7f3  jnz     short loc_18000B838
0x18000b7f5  mov     rcx, [rax]
0x18000b7f8  cmp     [rcx+8], rax
0x18000b7fc  jnz     short loc_18000B838
0x18000b7fe  lea     rdx, [rbp+var_30]
0x18000b802  mov     qword ptr [rbp+var_30], rcx
0x18000b806  lea     rsi, [rax-118h]
0x18000b80d  mov     [rcx+8], rdx
0x18000b811  or      eax, 0FFFFFFFFh
0x18000b814  lock xadd [rsi+0B0h], eax
0x18000b81c  cmp     eax, 1
0x18000b81f  jnz     short loc_18000B7DE
0x18000b821  test    rsi, rsi
0x18000b824  jz      short loc_18000B7DE
0x18000b826  mov     rcx, rsi; this
0x18000b829  call    ??1FTP_SITE@@AEAA@XZ; FTP_SITE::~FTP_SITE(void)
0x18000b82e  mov     rcx, rsi; Block
0x18000b831  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b836  jmp     short loc_18000B7DE
0x18000b838  mov     ecx, 3
0x18000b83d  int     29h; Win8: RtlFailFast(ecx)
0x18000b83f  mov     rcx, [rbp+arg_0]
0x18000b843  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000b849  test    rdi, rdi
0x18000b84c  jz      short loc_18000B857
0x18000b84e  mov     rcx, rdi; pv
0x18000b851  call    cs:__imp_CoTaskMemFree
0x18000b857  test    r14, r14
0x18000b85a  jz      short loc_18000B865
0x18000b85c  mov     rcx, r14; pv
0x18000b85f  call    cs:__imp_CoTaskMemFree
0x18000b865  mov     eax, ebx
0x18000b867  mov     rbx, [rsp+50h+arg_10]
0x18000b86f  add     rsp, 50h
0x18000b873  pop     r15
0x18000b875  pop     r14
0x18000b877  pop     r13
0x18000b879  pop     r12
0x18000b87b  pop     rdi
0x18000b87c  pop     rsi
0x18000b87d  pop     rbp
0x18000b87e  retn
```
