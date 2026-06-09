# TelCacheProvider::BatchEnd(void)

- ea: `0x180041fcc`
- end: `0x180042655`
- name: `?BatchEnd@TelCacheProvider@@QEAAJXZ`
- size: `1673`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800b5df0`
- `0x1800d4c30`

## callees

- `0x180008dc0`
- `0x180009efc`
- `0x180009f14`
- `0x180040db4`
- `0x1800413d4`
- `0x1800414a0`
- `0x180041af4`
- `0x180041fcc`
- `0x180044344`
- `0x180044500`
- `0x1800464c0`
- `0x180048350`
- `0x1800495f8`
- `0x18016796c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004212d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004212d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800422ea`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004261f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800422ea`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004261f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800422c4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800425ff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800422c4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800425ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800422e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180042615`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800422e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180042615`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042170`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042170`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004200e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042024`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004200e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042024`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800421d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800421d3`

## string_xrefs

- `0x180042225`: `InventoryCache::NextBatchMarkedItem failed. [%#x]`
- `0x18004241b`: `InventoryCache::GetNextItem failed. [%#x]`
- `0x1800424ed`: `TelCacheProvider::GetItem failed. [%#x]`
- `0x180042562`: `IAmiInventoryTelemetryItem::OnRemove(%ls) failed. [%#x]`
- `0x18004208f`: `TelCacheProvider::BatchEnd`
- `0x18004220d`: `TelCacheProvider::BatchEnd`
- `0x180042357`: `InventoryCache::RemoveItem failed. [%#x]`
- `0x1800425a1`: `InventoryCache::RemoveItem failed. [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TelCacheProvider::BatchEnd(TelCacheProvider *this)
{
  unsigned __int64 v3; // r13
  __int128 v4; // rdi
  signed int v5; // ebx
  const char *v6; // r9
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned __int64 v10; // r12
  unsigned __int64 v11; // rbx
  _QWORD *v12; // rdx
  unsigned __int64 v13; // rax
  __int64 v14; // rax
  SIZE_T v15; // r13
  wchar_t *v16; // rax
  wchar_t *v17; // rbx
  int v18; // eax
  char v19; // al
  char v20; // dl
  __int64 v21; // rcx
  DWORD v22; // eax
  unsigned int v23; // edi
  unsigned __int64 v24; // rsi
  _QWORD *v25; // rdx
  unsigned __int64 v26; // rax
  int v27; // eax
  struct IAmiInventoryItem *v28; // r12
  int i; // eax
  __int64 v30; // rdx
  void (__fastcall *v31)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL); // rdi
  BOOL v32; // ebx
  const unsigned __int16 *v33; // rax
  unsigned __int128 v34; // rax
  unsigned __int64 v35; // rsi
  const wchar_t **v36; // rcx
  unsigned __int64 v37; // kr10_8
  const wchar_t *v38; // rdi
  struct IAmiInventoryItem *v39; // rbx
  signed int v40; // eax
  bool v41; // sf
  int Item; // eax
  __int64 (__fastcall *v43)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL); // rdi
  BOOL v44; // ebx
  const unsigned __int16 *SyncId; // rax
  int v46; // eax
  int v47; // eax
  char v48; // cl
  __int64 v49; // rax
  __int64 v50; // [rsp+20h] [rbp-E0h]
  unsigned int v51; // [rsp+30h] [rbp-D0h] BYREF
  int v52; // [rsp+34h] [rbp-CCh]
  unsigned __int64 v53; // [rsp+38h] [rbp-C8h]
  const wchar_t *v54[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct IAmiInventoryItem *v55; // [rsp+50h] [rbp-B0h]
  __int128 v56; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v57; // [rsp+68h] [rbp-98h]
  __int128 v58; // [rsp+78h] [rbp-88h]
  int v59; // [rsp+88h] [rbp-78h]
  char *v60; // [rsp+90h] [rbp-70h]
  _WORD Src[264]; // [rsp+A0h] [rbp-60h] BYREF

  if ( !*((_QWORD *)this + 11) )
    return 2147500034LL;
  GetProcessHeap();
  v59 = 0;
  *(_QWORD *)&v4 = GetProcessHeap();
  *(_QWORD *)&v56 = v4;
  v53 = 16;
  v58 = 0x10u;
  v57 = 0;
  v3 = 0;
  *((_QWORD *)&v56 + 1) = 16;
  memset_0(Src, 0, 0x208u);
  *((_QWORD *)&v4 + 1) = (char *)this + 104;
  v60 = (char *)this + 104;
  Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((TelCacheProvider *)((char *)this + 104));
  if ( !*((_BYTE *)this + 96) )
  {
    v5 = -2147418113;
    v6 = "BatchEnd called but batch not in progress [%#x]";
    v7 = 1149;
LABEL_5:
    LODWORD(v50) = v5;
    AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", v7, v6, v50);
    goto LABEL_89;
  }
  *((_BYTE *)this + 96) = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, __int64))(**((_QWORD **)this + 11) + 112LL))(
         *((_QWORD *)this + 11),
         Src,
         260);
  v9 = 0;
  v10 = v57;
  if ( v5 < 0 )
    goto LABEL_28;
  *((_QWORD *)&v4 + 1) = 16;
  do
  {
    v54[0] = 0;
    v54[1] = 0;
    if ( !v59 )
      goto LABEL_18;
    v11 = 0;
    if ( !v10 )
      goto LABEL_18;
    while ( 1 )
    {
      v12 = 0;
      if ( v11 < v10 )
      {
        v55 = 0;
        v13 = *((_QWORD *)&v4 + 1) * v11;
        if ( !is_mul_ok(*((unsigned __int64 *)&v4 + 1), v11) || (v12 = (_QWORD *)(v13 + v3), v13 + v3 < v3) )
          v12 = 0;
      }
      if ( !(unsigned int)_o__wcsicmp(Src, *v12) )
        break;
      if ( ++v11 >= v10 )
        goto LABEL_18;
    }
    if ( v11 == -1 )
    {
LABEL_18:
      v14 = -1;
      do
        ++v14;
      while ( Src[v14] );
      v15 = 2 * v14 + 2;
      v16 = (wchar_t *)HeapAlloc((HANDLE)v4, 0, v15);
      v17 = v16;
      if ( v16 )
      {
        memset_0(v16, 0, v15);
        v54[0] = v17;
        memcpy_0(v17, Src, v15);
        v18 = RtlArray<RtlStringArray::RTL_STRING_ITEM>::Append(&v56, v54);
        v10 = v57;
        v4 = v56;
        if ( !v18 )
        {
LABEL_25:
          v3 = *((_QWORD *)&v58 + 1);
          goto LABEL_26;
        }
        v17 = (wchar_t *)v54[0];
      }
      if ( v17 )
        HeapFree((HANDLE)v4, 0, v17);
      goto LABEL_25;
    }
LABEL_26:
    v5 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, __int64))(**((_QWORD **)this + 11) + 112LL))(
           *((_QWORD *)this + 11),
           Src,
           260);
    v9 = 0;
  }
  while ( v5 >= 0 );
  v53 = *((_QWORD *)&v4 + 1);
  *((_QWORD *)&v4 + 1) = (char *)this + 104;
LABEL_28:
  if ( v5 == -2147024637 )
  {
    v5 = 0;
  }
  else
  {
    AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", 1170, "InventoryCache::NextBatchMarkedItem failed. [%#x]", v5);
    v9 = 0;
  }
  v51 = 0;
  if ( *((_BYTE *)this + 97) )
  {
    if ( *(_QWORD *)this )
    {
      v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, v8, 0);
      v9 = 0;
      if ( v19 )
      {
        *((_BYTE *)this + 97) = 0;
        goto LABEL_89;
      }
    }
  }
  if ( !*((_QWORD *)this + 11) )
    goto LABEL_65;
  Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock(*((Windows::Compat::Inventory::InventorySynchronization **)&v4
                                                                          + 1));
  LODWORD(v4) = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 11) + 32LL))(
                  *((_QWORD *)this + 11),
                  &v51);
  v9 = 0;
  if ( *(_BYTE *)(*((_QWORD *)&v4 + 1) + 36LL) )
  {
    v20 = 0;
    v21 = *(_QWORD *)(*((_QWORD *)&v4 + 1) + 24LL);
    if ( *(_DWORD *)(v21 + 4) == 1 )
    {
      *(_BYTE *)(*((_QWORD *)&v4 + 1) + 36LL) = 0;
      v20 = 1;
    }
    --*(_DWORD *)(v21 + 4);
    if ( v20 )
    {
LABEL_43:
      SetEvent(*(HANDLE *)(*((_QWORD *)&v4 + 1) + 16LL));
      v9 = 0;
    }
  }
  else
  {
    v22 = WaitForSingleObject(**((HANDLE **)&v4 + 1), 0xFFFFFFFF);
    v9 = 0;
    if ( !v22 )
    {
      --**(_DWORD **)(*((_QWORD *)&v4 + 1) + 24LL);
      --*(_DWORD *)(*((_QWORD *)&v4 + 1) + 32LL);
      ReleaseMutex(**((HANDLE **)&v4 + 1));
      goto LABEL_43;
    }
  }
  if ( (int)v4 < 0 || v10 <= (unsigned __int64)v51 >> 1 )
  {
LABEL_65:
    *((_QWORD *)&v34 + 1) = 0;
    v52 = 0;
    if ( !v10 )
      goto LABEL_89;
    v35 = *((_QWORD *)&v58 + 1);
    while ( 1 )
    {
      v36 = 0;
      if ( DWORD2(v34) < v10 )
      {
        v55 = 0;
        v37 = DWORD2(v34);
        v34 = v53 * (unsigned __int128)DWORD2(v34);
        if ( !is_mul_ok(v53, v37) || (v36 = (const wchar_t **)(v35 + v34), v35 + (unsigned __int64)v34 < v35) )
          v36 = 0;
      }
      v38 = *v36;
      v54[0] = *v36;
      if ( *(_QWORD *)this
        && (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)this + 56LL))(
             *(_QWORD *)this,
             *((_QWORD *)&v34 + 1),
             0) )
      {
        v39 = *(struct IAmiInventoryItem **)this;
        v55 = v39;
        v40 = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *, const wchar_t *))(*(_QWORD *)v39 + 16LL))(v39, v38);
        v41 = v40 < 0;
        if ( v40 > 0 )
        {
          v40 = (unsigned __int16)v40 | 0x80070000;
          v41 = v40 < 0;
        }
        if ( v41 )
          AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", 1237, "IAmiInventoryItem::SetItemKey failed. [%#x]", v40);
        Item = TelCacheProvider::GetItem(this, v39, 0);
        if ( Item < 0 )
          AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", 1243, "TelCacheProvider::GetItem failed. [%#x]", Item);
        v43 = *(__int64 (__fastcall **)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL))(*(_QWORD *)v39 + 80LL);
        v44 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 136LL))(*((_QWORD *)this + 11)) == 0;
        SyncId = TelCacheProvider::RetrieveSyncId(this);
        v46 = v43(v55, SyncId, v44);
        v5 = v46;
        if ( v46 > 0 )
          v5 = (unsigned __int16)v46 | 0x80070000;
        if ( v5 < 0 )
        {
          AslLogCallPrintf(
            1,
            "TelCacheProvider::BatchEnd",
            1249,
            "IAmiInventoryTelemetryItem::OnRemove(%ls) failed. [%#x]",
            v54[0],
            v5);
LABEL_86:
          v9 = 0;
          goto LABEL_87;
        }
        v38 = v54[0];
      }
      v47 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)this + 11) + 24LL))(
              *((_QWORD *)this + 11),
              v38,
              v9);
      v5 = v47;
      v9 = 0;
      if ( v47 < 0 )
      {
        AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", 1257, "InventoryCache::RemoveItem failed. [%#x]", v47);
        goto LABEL_86;
      }
LABEL_87:
      *((_QWORD *)&v34 + 1) = (unsigned int)(v52 + 1);
      v52 = DWORD2(v34);
      if ( DWORD2(v34) >= v10 )
      {
        *((_QWORD *)&v4 + 1) = v60;
        goto LABEL_89;
      }
    }
  }
  v23 = 0;
  if ( v10 )
  {
    v24 = *((_QWORD *)&v58 + 1);
    do
    {
      v25 = 0;
      if ( v23 < v10 )
      {
        v26 = v53 * v23;
        if ( !is_mul_ok(v53, v23) || (v25 = (_QWORD *)(v24 + v26), v24 + v26 < v24) )
          v25 = 0;
      }
      v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 11) + 24LL))(*((_QWORD *)this + 11), *v25);
      v5 = v27;
      if ( v27 < 0 )
        AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", 1195, "InventoryCache::RemoveItem failed. [%#x]", v27);
      ++v23;
    }
    while ( v23 < v10 );
    *((_QWORD *)&v4 + 1) = (char *)this + 104;
  }
  if ( *(_QWORD *)this && (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)this + 56LL))(*(_QWORD *)this) )
  {
    v28 = *(struct IAmiInventoryItem **)this;
    TelCacheProvider::NewSyncId(this);
    for ( i = TelCacheProvider::GetFirstItem(this, v28); i >= 0; i = TelCacheProvider::GetNextItem(this, v28) )
    {
      v31 = *(void (__fastcall **)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL))(*(_QWORD *)v28 + 72LL);
      v32 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 11) + 136LL))(
              *((_QWORD *)this + 11),
              v30,
              0) == 0;
      v33 = TelCacheProvider::RetrieveSyncId(this);
      v31(v28, v33, v32);
    }
    v5 = 0;
    if ( i != -2147024637 )
      v5 = i;
    if ( v5 < 0 )
    {
      v6 = "InventoryCache::GetNextItem failed. [%#x]";
      v7 = 1218;
      goto LABEL_5;
    }
  }
LABEL_89:
  if ( *(_BYTE *)(*((_QWORD *)&v4 + 1) + 36LL) )
  {
    v48 = 0;
    v49 = *(_QWORD *)(*((_QWORD *)&v4 + 1) + 24LL);
    if ( *(_DWORD *)(v49 + 4) == 1 )
    {
      *(_BYTE *)(*((_QWORD *)&v4 + 1) + 36LL) = 0;
      v48 = 1;
    }
    --*(_DWORD *)(v49 + 4);
    if ( v48 )
LABEL_96:
      SetEvent(*(HANDLE *)(*((_QWORD *)&v4 + 1) + 16LL));
  }
  else if ( !WaitForSingleObject(**((HANDLE **)&v4 + 1), 0xFFFFFFFF) )
  {
    --**(_DWORD **)(*((_QWORD *)&v4 + 1) + 24LL);
    --*(_DWORD *)(*((_QWORD *)&v4 + 1) + 32LL);
    ReleaseMutex(**((HANDLE **)&v4 + 1));
    goto LABEL_96;
  }
  RtlNameValueArray::Free((RtlNameValueArray *)&v56);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180041fcc  push    rbp
0x180041fce  push    rbx
0x180041fcf  push    rsi
0x180041fd0  push    rdi
0x180041fd1  push    r12
0x180041fd3  push    r13
0x180041fd5  push    r14
0x180041fd7  push    r15
0x180041fd9  lea     rbp, [rsp-1C8h]
0x180041fe1  sub     rsp, 2C8h
0x180041fe8  mov     rax, cs:__security_cookie
0x180041fef  xor     rax, rsp
0x180041ff2  mov     [rbp+200h+var_50], rax
0x180041ff9  mov     r14, rcx
0x180041ffc  xor     ebx, ebx
0x180041ffe  cmp     [rcx+58h], rbx
0x180042002  jnz     short loc_18004200E
0x180042004  mov     eax, 80004002h
0x180042009  jmp     loc_180042632
0x18004200e  call    cs:__imp_GetProcessHeap
0x180042014  mov     [rbp+200h+var_278], ebx
0x180042017  xorps   xmm0, xmm0
0x18004201a  movups  [rsp+300h+var_2A8], xmm0
0x18004201f  movups  [rsp+300h+var_288], xmm0
0x180042024  call    cs:__imp_GetProcessHeap
0x18004202a  mov     rdi, rax
0x18004202d  mov     qword ptr [rsp+300h+var_2A8], rax
0x180042032  mov     eax, 10h
0x180042037  mov     [rsp+300h+var_2C8], rax
0x18004203c  mov     qword ptr [rsp+300h+var_288], rax
0x180042041  xorps   xmm0, xmm0
0x180042044  movdqu  [rsp+300h+var_298], xmm0
0x18004204a  mov     r13, rbx
0x18004204d  mov     qword ptr [rbp+200h+var_288+8], rbx
0x180042051  mov     qword ptr [rsp+300h+var_2A8+8], rax
0x180042056  xor     edx, edx; Val
0x180042058  mov     r8d, 208h; Size
0x18004205e  lea     rcx, [rbp+200h+Src]; void *
0x180042062  call    memset_0
0x180042067  lea     rsi, [r14+68h]
0x18004206b  mov     [rbp+200h+var_270], rsi
0x18004206f  mov     rcx, rsi; this
0x180042072  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x180042077  cmp     [r14+60h], bl
0x18004207b  jnz     short loc_1800420B0
0x18004207d  mov     ebx, 8000FFFFh
0x180042082  lea     r9, aBatchendCalled; "BatchEnd called but batch not in progre"...
0x180042089  mov     r8d, 47Dh
0x18004208f  lea     rdx, aTelcacheprovid_9; "TelCacheProvider::BatchEnd"
0x180042096  mov     r15d, 1
0x18004209c  mov     dword ptr [rsp+300h+var_2E0], ebx
0x1800420a0  mov     ecx, r15d
0x1800420a3  call    AslLogCallPrintf
0x1800420a8  xor     r8d, r8d
0x1800420ab  jmp     loc_1800425D6
0x1800420b0  mov     [r14+60h], bl
0x1800420b4  mov     rcx, [r14+58h]
0x1800420b8  mov     rax, [rcx]
0x1800420bb  mov     r8d, 104h
0x1800420c1  lea     rdx, [rbp+200h+Src]
0x1800420c5  mov     rax, [rax+70h]
0x1800420c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800420ce  mov     ebx, eax
0x1800420d0  mov     r15d, 1
0x1800420d6  xor     r8d, r8d
0x1800420d9  mov     r12, qword ptr [rsp+300h+var_298]
0x1800420de  test    eax, eax
0x1800420e0  js      loc_18004220D
0x1800420e6  lea     esi, [r15+0Fh]
0x1800420ea  mov     [rsp+300h+var_2C0], r8
0x1800420ef  mov     [rsp+300h+var_2B8], r8
0x1800420f4  cmp     [rbp+200h+var_278], r8d
0x1800420f8  jz      short loc_18004214E
0x1800420fa  mov     rbx, r8
0x1800420fd  test    r12, r12
0x180042100  jz      short loc_18004214E
0x180042102  mov     rdx, r8
0x180042105  cmp     rbx, r12
0x180042108  jnb     short loc_180042126
0x18004210a  mov     [rsp+300h+var_2B0], r8
0x18004210f  mov     rax, rbx
0x180042112  mul     rsi
0x180042115  test    rdx, rdx
0x180042118  jnz     short loc_180042123
0x18004211a  lea     rdx, [rax+r13]
0x18004211e  cmp     rdx, r13
0x180042121  jnb     short loc_180042126
0x180042123  mov     rdx, r8
0x180042126  mov     rdx, [rdx]
0x180042129  lea     rcx, [rbp+200h+Src]
0x18004212d  call    cs:__imp__o__wcsicmp
0x180042133  xor     r8d, r8d
0x180042136  test    eax, eax
0x180042138  jz      short loc_180042144
0x18004213a  add     rbx, r15
0x18004213d  cmp     rbx, r12
0x180042140  jb      short loc_180042102
0x180042142  jmp     short loc_18004214E
0x180042144  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180042148  jnz     loc_1800421DD
0x18004214e  lea     rcx, [rbp+200h+Src]
0x180042152  or      rax, 0FFFFFFFFFFFFFFFFh
0x180042156  inc     rax
0x180042159  cmp     [rcx+rax*2], r8w
0x18004215e  jnz     short loc_180042156
0x180042160  lea     r13, ds:2[rax*2]
0x180042168  mov     r8, r13; dwBytes
0x18004216b  xor     edx, edx; dwFlags
0x18004216d  mov     rcx, rdi; hHeap
0x180042170  call    cs:__imp_HeapAlloc
0x180042176  mov     rbx, rax
0x180042179  test    rax, rax
0x18004217c  jz      short loc_1800421C6
0x18004217e  mov     r8, r13; Size
0x180042181  xor     edx, edx; Val
0x180042183  mov     rcx, rax; void *
0x180042186  call    memset_0
0x18004218b  mov     [rsp+300h+var_2C0], rbx
0x180042190  mov     r8, r13; Size
0x180042193  lea     rdx, [rbp+200h+Src]; Src
0x180042197  mov     rcx, rbx; void *
0x18004219a  call    memcpy_0
0x18004219f  lea     rdx, [rsp+300h+var_2C0]
0x1800421a4  lea     rcx, [rsp+300h+var_2A8]
0x1800421a9  call    ?Append@?$RtlArray@URTL_STRING_ITEM@RtlStringArray@@@@QEAAJAEBURTL_STRING_ITEM@RtlStringArray@@@Z; RtlArray<RtlStringArray::RTL_STRING_ITEM>::Append(RtlStringArray::RTL_STRING_ITEM const &)
0x1800421ae  mov     r12, qword ptr [rsp+300h+var_298]
0x1800421b3  mov     rsi, qword ptr [rsp+300h+var_2A8+8]
0x1800421b8  mov     rdi, qword ptr [rsp+300h+var_2A8]
0x1800421bd  test    eax, eax
0x1800421bf  jz      short loc_1800421D9
0x1800421c1  mov     rbx, [rsp+300h+var_2C0]
0x1800421c6  test    rbx, rbx
0x1800421c9  jz      short loc_1800421D9
0x1800421cb  mov     r8, rbx; lpMem
0x1800421ce  xor     edx, edx; dwFlags
0x1800421d0  mov     rcx, rdi; hHeap
0x1800421d3  call    cs:__imp_HeapFree
0x1800421d9  mov     r13, qword ptr [rbp+200h+var_288+8]
0x1800421dd  mov     rcx, [r14+58h]
0x1800421e1  mov     rax, [rcx]
0x1800421e4  mov     r8d, 104h
0x1800421ea  lea     rdx, [rbp+200h+Src]
0x1800421ee  mov     rax, [rax+70h]
0x1800421f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421f7  mov     ebx, eax
0x1800421f9  xor     r8d, r8d
0x1800421fc  test    eax, eax
0x1800421fe  jns     loc_1800420EA
0x180042204  mov     [rsp+300h+var_2C8], rsi
0x180042209  lea     rsi, [r14+68h]
0x18004220d  lea     r13, aTelcacheprovid_9; "TelCacheProvider::BatchEnd"
0x180042214  cmp     ebx, 80070103h
0x18004221a  jnz     short loc_180042221
0x18004221c  mov     ebx, r8d
0x18004221f  jmp     short loc_180042240
0x180042221  mov     dword ptr [rsp+300h+var_2E0], ebx
0x180042225  lea     r9, aInventorycache_5; "InventoryCache::NextBatchMarkedItem fai"...
0x18004222c  mov     r8d, 492h
0x180042232  mov     rdx, r13
0x180042235  mov     ecx, r15d
0x180042238  call    AslLogCallPrintf
0x18004223d  xor     r8d, r8d
0x180042240  mov     [rsp+300h+var_2D0], r8d
0x180042245  cmp     [r14+61h], r8b
0x180042249  jz      short loc_18004226F
0x18004224b  mov     rcx, [r14]
0x18004224e  test    rcx, rcx
0x180042251  jz      short loc_18004226F
0x180042253  mov     rax, [rcx]
0x180042256  mov     rax, [rax+38h]
0x18004225a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004225f  xor     r8d, r8d
0x180042262  test    al, al
0x180042264  jz      short loc_18004226F
0x180042266  mov     [r14+61h], r8b
0x18004226a  jmp     loc_1800425D6
0x18004226f  cmp     [r14+58h], r8
0x180042273  jz      loc_180042430
0x180042279  mov     rcx, rsi; this
0x18004227c  call    ?AcquireSharedLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock(void)
0x180042281  mov     rcx, [r14+58h]
0x180042285  mov     rax, [rcx]
0x180042288  lea     rdx, [rsp+300h+var_2D0]
0x18004228d  mov     rax, [rax+20h]
0x180042291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042296  mov     edi, eax
0x180042298  xor     r8d, r8d
0x18004229b  cmp     [rsi+24h], r8b
0x18004229f  jz      short loc_1800422BE
0x1800422a1  mov     dl, r8b
0x1800422a4  mov     rcx, [rsi+18h]
0x1800422a8  cmp     [rcx+4], r15d
0x1800422ac  jnz     short loc_1800422B5
0x1800422ae  mov     [rsi+24h], r8b
0x1800422b2  mov     dl, r15b
0x1800422b5  dec     dword ptr [rcx+4]
0x1800422b8  test    dl, dl
0x1800422ba  jz      short loc_1800422F3
0x1800422bc  jmp     short loc_1800422E6
0x1800422be  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800422c1  mov     rcx, [rsi]; hHandle
0x1800422c4  call    cs:__imp_WaitForSingleObject
0x1800422ca  xor     r8d, r8d
0x1800422cd  test    eax, eax
0x1800422cf  jnz     short loc_1800422F3
0x1800422d1  mov     rax, [rsi+18h]
0x1800422d5  or      ecx, 0FFFFFFFFh
0x1800422d8  add     [rax], ecx
0x1800422da  add     [rsi+20h], ecx
0x1800422dd  mov     rcx, [rsi]; hMutex
0x1800422e0  call    cs:__imp_ReleaseMutex
0x1800422e6  mov     rcx, [rsi+10h]; hEvent
0x1800422ea  call    cs:__imp_SetEvent
0x1800422f0  xor     r8d, r8d
0x1800422f3  test    edi, edi
0x1800422f5  js      loc_180042430
0x1800422fb  mov     eax, [rsp+300h+var_2D0]
0x1800422ff  shr     rax, 1
0x180042302  cmp     r12, rax
0x180042305  jbe     loc_180042430
0x18004230b  mov     edi, r8d
0x18004230e  test    r12, r12
0x180042311  jz      short loc_180042380
0x180042313  mov     rsi, qword ptr [rbp+200h+var_288+8]
0x180042317  mov     rdx, r8
0x18004231a  mov     eax, edi
0x18004231c  cmp     rax, r12
0x18004231f  jnb     short loc_180042337
0x180042321  mul     [rsp+300h+var_2C8]
0x180042326  test    rdx, rdx
0x180042329  jnz     short loc_180042334
0x18004232b  lea     rdx, [rsi+rax]
0x18004232f  cmp     rdx, rsi
0x180042332  jnb     short loc_180042337
0x180042334  mov     rdx, r8
0x180042337  mov     rcx, [r14+58h]
0x18004233b  mov     rax, [rcx]
0x18004233e  mov     rdx, [rdx]
0x180042341  mov     rax, [rax+18h]
0x180042345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004234a  mov     ebx, eax
0x18004234c  xor     r8d, r8d
0x18004234f  test    eax, eax
0x180042351  jns     short loc_180042372
0x180042353  mov     dword ptr [rsp+300h+var_2E0], eax
0x180042357  lea     r9, aInventorycache_7; "InventoryCache::RemoveItem failed. [%#x"...
0x18004235e  mov     r8d, 4ABh
0x180042364  mov     rdx, r13
0x180042367  mov     ecx, r15d
0x18004236a  call    AslLogCallPrintf
0x18004236f  xor     r8d, r8d
0x180042372  add     edi, r15d
0x180042375  mov     eax, edi
0x180042377  cmp     rax, r12
0x18004237a  jb      short loc_180042317
0x18004237c  lea     rsi, [r14+68h]
0x180042380  mov     rcx, [r14]
0x180042383  test    rcx, rcx
0x180042386  jz      loc_1800425D6
0x18004238c  mov     rax, [rcx]
0x18004238f  mov     rax, [rax+38h]
0x180042393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042398  xor     r8d, r8d
0x18004239b  test    al, al
0x18004239d  jz      loc_1800425D6
0x1800423a3  mov     r12, [r14]
0x1800423a6  mov     rcx, r14; this
0x1800423a9  call    ?NewSyncId@TelCacheProvider@@AEAAXXZ; TelCacheProvider::NewSyncId(void)
0x1800423ae  mov     rdx, r12; struct IAmiInventoryItem *
0x1800423b1  mov     rcx, r14; this
0x1800423b4  call    ?GetFirstItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetFirstItem(IAmiInventoryItem *)
0x1800423b9  jmp     short loc_180042401
0x1800423bb  mov     rax, [r12]
0x1800423bf  mov     rdi, [rax+48h]
0x1800423c3  mov     rcx, [r14+58h]
0x1800423c7  mov     rax, [rcx]
0x1800423ca  mov     rax, [rax+88h]
0x1800423d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423d6  xor     ebx, ebx
0x1800423d8  test    eax, eax
0x1800423da  setz    bl
0x1800423dd  mov     rcx, r14; this
0x1800423e0  call    ?RetrieveSyncId@TelCacheProvider@@AEAAPEBGXZ; TelCacheProvider::RetrieveSyncId(void)
0x1800423e5  mov     r8d, ebx
0x1800423e8  mov     rdx, rax
0x1800423eb  mov     rcx, r12
0x1800423ee  mov     rax, rdi
0x1800423f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423f6  mov     rdx, r12; struct IAmiInventoryItem *
0x1800423f9  mov     rcx, r14; this
0x1800423fc  call    ?GetNextItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetNextItem(IAmiInventoryItem *)
0x180042401  xor     r8d, r8d
0x180042404  test    eax, eax
0x180042406  jns     short loc_1800423BB
0x180042408  mov     ebx, r8d
0x18004240b  cmp     eax, 80070103h
0x180042410  cmovnz  ebx, eax
0x180042413  test    ebx, ebx
0x180042415  jns     loc_1800425D6
0x18004241b  lea     r9, aInventorycache_6; "InventoryCache::GetNextItem failed. [%#"...
  ... truncated ...
```
