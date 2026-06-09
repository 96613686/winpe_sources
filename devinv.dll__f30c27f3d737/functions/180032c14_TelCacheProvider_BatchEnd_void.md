# TelCacheProvider::BatchEnd(void)

- ea: `0x180032c14`
- end: `0x18003323b`
- name: `?BatchEnd@TelCacheProvider@@QEAAJXZ`
- size: `1575`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180034d4c`
- `0x180044f20`

## callees

- `0x180005e40`
- `0x180006eac`
- `0x180006ec4`
- `0x180010b3c`
- `0x180012078`
- `0x180012888`
- `0x180017adc`
- `0x180018778`
- `0x18001ae20`
- `0x180032394`
- `0x1800328c4`
- `0x180032c14`
- `0x180036c58`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180032d74`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180032d74`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800331fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800331fa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180033205`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180033205`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800331e0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800331e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032e1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032e1a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032db7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032db7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032c56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032c6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032c56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032c6c`

## string_xrefs

- `0x180032e6d`: `InventoryCache::NextBatchMarkedItem failed. [%#x]`
- `0x180032fef`: `InventoryCache::GetNextItem failed. [%#x]`
- `0x1800330c0`: `TelCacheProvider::GetItem failed. [%#x]`
- `0x180033135`: `IAmiInventoryTelemetryItem::OnRemove(%ls) failed. [%#x]`
- `0x180032f2c`: `InventoryCache::RemoveItem failed. [%#x]`
- `0x180033174`: `InventoryCache::RemoveItem failed. [%#x]`
- `0x180032cd7`: `TelCacheProvider::BatchEnd`
- `0x180032e55`: `TelCacheProvider::BatchEnd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TelCacheProvider::BatchEnd(TelCacheProvider *this)
{
  HANDLE ProcessHeap; // r13
  unsigned __int64 v4; // rdi
  char *v5; // r12
  signed int v6; // ebx
  const char *v7; // r9
  __int64 v8; // r8
  __int64 v9; // rdx
  unsigned __int64 v10; // r14
  unsigned __int64 v11; // r12
  unsigned __int64 v12; // rbx
  _QWORD *v13; // rdx
  unsigned __int64 v14; // rax
  __int64 v15; // rax
  SIZE_T v16; // rdi
  wchar_t *v17; // rax
  wchar_t *v18; // rbx
  int v19; // eax
  int ItemCount; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned int v23; // edi
  unsigned __int64 v24; // r12
  _QWORD *v25; // rdx
  unsigned __int64 v26; // rax
  int v27; // eax
  struct IAmiInventoryItem *v28; // r14
  int i; // eax
  __int64 v30; // rdx
  void (__fastcall *v31)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL); // rdi
  BOOL v32; // ebx
  const unsigned __int16 *v33; // rax
  unsigned __int128 v34; // rax
  unsigned __int64 v35; // r12
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
  const wchar_t *v51[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v52; // [rsp+40h] [rbp-C0h] BYREF
  int v53; // [rsp+44h] [rbp-BCh]
  struct IAmiInventoryItem *v54; // [rsp+48h] [rbp-B8h]
  HANDLE v55; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v56; // [rsp+58h] [rbp-A8h]
  __int128 v57; // [rsp+60h] [rbp-A0h]
  __int128 v58; // [rsp+70h] [rbp-90h]
  int v59; // [rsp+80h] [rbp-80h]
  char *v60; // [rsp+88h] [rbp-78h]
  _WORD Src[264]; // [rsp+90h] [rbp-70h] BYREF

  if ( !*((_QWORD *)this + 11) )
    return 2147500034LL;
  GetProcessHeap();
  v59 = 0;
  ProcessHeap = GetProcessHeap();
  v55 = ProcessHeap;
  v51[0] = (const wchar_t *)16;
  v58 = 0x10u;
  v57 = 0;
  v4 = 0;
  v56 = 16;
  memset_0(Src, 0, 0x208u);
  v5 = (char *)this + 104;
  v60 = (char *)this + 104;
  Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((TelCacheProvider *)((char *)this + 104));
  if ( !*((_BYTE *)this + 96) )
  {
    v6 = -2147418113;
    v7 = "BatchEnd called but batch not in progress [%#x]";
    v8 = 1149;
LABEL_5:
    LODWORD(v50) = v6;
    AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", v8, v7, v50);
    goto LABEL_79;
  }
  *((_BYTE *)this + 96) = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, __int64))(**((_QWORD **)this + 11) + 112LL))(
         *((_QWORD *)this + 11),
         Src,
         260);
  v10 = v57;
  if ( v6 < 0 )
    goto LABEL_27;
  v11 = 16;
  do
  {
    v51[0] = 0;
    v51[1] = 0;
    if ( !v59 )
      goto LABEL_18;
    v12 = 0;
    if ( !v10 )
      goto LABEL_18;
    while ( 1 )
    {
      v13 = 0;
      if ( v12 < v10 )
      {
        v54 = 0;
        v14 = v11 * v12;
        if ( !is_mul_ok(v11, v12) || (v13 = (_QWORD *)(v4 + v14), v4 + v14 < v4) )
          v13 = 0;
      }
      if ( !(unsigned int)_o__wcsicmp(Src, *v13) )
        break;
      if ( ++v12 >= v10 )
        goto LABEL_18;
    }
    if ( v12 == -1 )
    {
LABEL_18:
      v15 = -1;
      do
        ++v15;
      while ( Src[v15] );
      v16 = 2 * v15 + 2;
      v17 = (wchar_t *)HeapAlloc(ProcessHeap, 0, v16);
      v18 = v17;
      if ( v17 )
      {
        memset_0(v17, 0, v16);
        v51[0] = v18;
        memcpy_0(v18, Src, v16);
        v19 = RtlArray<RtlStringArray::RTL_STRING_ITEM>::Append(&v55, v51);
        v10 = v57;
        v11 = v56;
        ProcessHeap = v55;
        if ( !v19 )
          goto LABEL_25;
        v18 = (wchar_t *)v51[0];
      }
      if ( v18 )
        HeapFree(ProcessHeap, 0, v18);
    }
LABEL_25:
    v6 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, __int64))(**((_QWORD **)this + 11) + 112LL))(
           *((_QWORD *)this + 11),
           Src,
           260);
    v4 = *((_QWORD *)&v58 + 1);
  }
  while ( v6 >= 0 );
  v51[0] = (const wchar_t *)v11;
  v5 = (char *)this + 104;
LABEL_27:
  if ( v6 == -2147024637 )
    v6 = 0;
  else
    AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", 1170, "InventoryCache::NextBatchMarkedItem failed. [%#x]", v6);
  v52 = 0;
  if ( *((_BYTE *)this + 97)
    && *(_QWORD *)this
    && (*(unsigned __int8 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, v9, 0) )
  {
    *((_BYTE *)this + 97) = 0;
    goto LABEL_79;
  }
  ItemCount = TelCacheProvider::GetItemCount(this, &v52);
  v22 = 0;
  if ( ItemCount < 0 || v10 <= (unsigned __int64)v52 >> 1 )
  {
    *((_QWORD *)&v34 + 1) = 0;
    v53 = 0;
    if ( !v10 )
      goto LABEL_79;
    v35 = (unsigned __int64)v51[0];
    while ( 1 )
    {
      v36 = 0;
      if ( DWORD2(v34) < v10 )
      {
        v54 = 0;
        v37 = DWORD2(v34);
        v34 = v35 * (unsigned __int128)DWORD2(v34);
        if ( !is_mul_ok(v35, v37) || (v36 = (const wchar_t **)(v4 + v34), v4 + (unsigned __int64)v34 < v4) )
          v36 = 0;
      }
      v38 = *v36;
      v51[0] = *v36;
      if ( *(_QWORD *)this
        && (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)this + 56LL))(
             *(_QWORD *)this,
             *((_QWORD *)&v34 + 1),
             0) )
      {
        v39 = *(struct IAmiInventoryItem **)this;
        v54 = v39;
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
        v46 = v43(v54, SyncId, v44);
        v6 = v46;
        if ( v46 > 0 )
          v6 = (unsigned __int16)v46 | 0x80070000;
        if ( v6 < 0 )
        {
          AslLogCallPrintf(
            1,
            "TelCacheProvider::BatchEnd",
            1249,
            "IAmiInventoryTelemetryItem::OnRemove(%ls) failed. [%#x]",
            v51[0],
            v6);
LABEL_76:
          v22 = 0;
          goto LABEL_77;
        }
        v38 = v51[0];
      }
      v47 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)this + 11) + 24LL))(
              *((_QWORD *)this + 11),
              v38,
              v22);
      v6 = v47;
      v22 = 0;
      if ( v47 < 0 )
      {
        AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", 1257, "InventoryCache::RemoveItem failed. [%#x]", v47);
        goto LABEL_76;
      }
LABEL_77:
      *((_QWORD *)&v34 + 1) = (unsigned int)(v53 + 1);
      v53 = DWORD2(v34);
      v4 = *((_QWORD *)&v58 + 1);
      if ( DWORD2(v34) >= v10 )
      {
        v5 = v60;
        goto LABEL_79;
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
        v26 = (unsigned __int64)v51[0] * v23;
        if ( !is_mul_ok((unsigned __int64)v51[0], v23) || (v25 = (_QWORD *)(v24 + v26), v24 + v26 < v24) )
          v25 = 0;
      }
      v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 11) + 24LL))(
              *((_QWORD *)this + 11),
              *v25,
              0);
      v6 = v27;
      if ( v27 < 0 )
        AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", 1195, "InventoryCache::RemoveItem failed. [%#x]", v27);
      ++v23;
    }
    while ( v23 < v10 );
    v5 = (char *)this + 104;
  }
  if ( *(_QWORD *)this
    && (*(unsigned __int8 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, v21, 0) )
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
    v6 = 0;
    if ( i != -2147024637 )
      v6 = i;
    if ( v6 < 0 )
    {
      v7 = "InventoryCache::GetNextItem failed. [%#x]";
      v8 = 1218;
      goto LABEL_5;
    }
  }
LABEL_79:
  if ( v5[36] )
  {
    v48 = 0;
    v49 = *((_QWORD *)v5 + 3);
    if ( *(_DWORD *)(v49 + 4) == 1 )
    {
      v5[36] = 0;
      v48 = 1;
    }
    --*(_DWORD *)(v49 + 4);
    if ( v48 )
LABEL_86:
      SetEvent(*((HANDLE *)v5 + 2));
  }
  else if ( !WaitForSingleObject(*(HANDLE *)v5, 0xFFFFFFFF) )
  {
    --**((_DWORD **)v5 + 3);
    --*((_DWORD *)v5 + 8);
    ReleaseMutex(*(HANDLE *)v5);
    goto LABEL_86;
  }
  RtlNameValueArray::Free((RtlNameValueArray *)&v55);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180032c14  push    rbp
0x180032c16  push    rbx
0x180032c17  push    rsi
0x180032c18  push    rdi
0x180032c19  push    r12
0x180032c1b  push    r13
0x180032c1d  push    r14
0x180032c1f  push    r15
0x180032c21  lea     rbp, [rsp-1B8h]
0x180032c29  sub     rsp, 2B8h
0x180032c30  mov     rax, cs:__security_cookie
0x180032c37  xor     rax, rsp
0x180032c3a  mov     [rbp+1F0h+var_50], rax
0x180032c41  mov     rsi, rcx
0x180032c44  xor     ebx, ebx
0x180032c46  cmp     [rcx+58h], rbx
0x180032c4a  jnz     short loc_180032C56
0x180032c4c  mov     eax, 80004002h
0x180032c51  jmp     loc_180033218
0x180032c56  call    cs:__imp_GetProcessHeap
0x180032c5c  mov     [rbp+1F0h+var_270], ebx
0x180032c5f  xorps   xmm0, xmm0
0x180032c62  movups  [rsp+2F0h+var_2A0], xmm0
0x180032c67  movups  [rsp+2F0h+var_280], xmm0
0x180032c6c  call    cs:__imp_GetProcessHeap
0x180032c72  mov     r13, rax
0x180032c75  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x180032c7a  mov     eax, 10h
0x180032c7f  mov     [rsp+2F0h+var_2C0], rax
0x180032c84  mov     qword ptr [rsp+2F0h+var_280], rax
0x180032c89  xorps   xmm0, xmm0
0x180032c8c  movdqu  [rsp+2F0h+var_290], xmm0
0x180032c92  mov     rdi, rbx
0x180032c95  mov     qword ptr [rsp+2F0h+var_280+8], rbx
0x180032c9a  mov     qword ptr [rsp+2F0h+var_2A0+8], rax
0x180032c9f  xor     edx, edx; Val
0x180032ca1  mov     r8d, 208h; Size
0x180032ca7  lea     rcx, [rbp+1F0h+Src]; void *
0x180032cab  call    memset_0
0x180032cb0  lea     r12, [rsi+68h]
0x180032cb4  mov     [rbp+1F0h+var_268], r12
0x180032cb8  mov     rcx, r12; this
0x180032cbb  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x180032cc0  cmp     [rsi+60h], bl
0x180032cc3  jnz     short loc_180032CF8
0x180032cc5  mov     ebx, 8000FFFFh
0x180032cca  lea     r9, aBatchendCalled; "BatchEnd called but batch not in progre"...
0x180032cd1  mov     r8d, 47Dh
0x180032cd7  lea     rdx, aTelcacheprovid_19; "TelCacheProvider::BatchEnd"
0x180032cde  mov     r15d, 1
0x180032ce4  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x180032ce8  mov     ecx, r15d
0x180032ceb  call    AslLogCallPrintf
0x180032cf0  xor     r8d, r8d
0x180032cf3  jmp     loc_1800331AE
0x180032cf8  mov     [rsi+60h], bl
0x180032cfb  mov     rcx, [rsi+58h]
0x180032cff  mov     rax, [rcx]
0x180032d02  mov     r8d, 104h
0x180032d08  lea     rdx, [rbp+1F0h+Src]
0x180032d0c  mov     rax, [rax+70h]
0x180032d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d15  mov     ebx, eax
0x180032d17  mov     r15d, 1
0x180032d1d  xor     r8d, r8d
0x180032d20  mov     r14, qword ptr [rsp+2F0h+var_290]
0x180032d25  test    eax, eax
0x180032d27  js      loc_180032E55
0x180032d2d  lea     r12d, [r15+0Fh]
0x180032d31  mov     [rsp+2F0h+var_2C0], r8
0x180032d36  mov     [rsp+2F0h+var_2B8], r8
0x180032d3b  cmp     [rbp+1F0h+var_270], r8d
0x180032d3f  jz      short loc_180032D95
0x180032d41  mov     rbx, r8
0x180032d44  test    r14, r14
0x180032d47  jz      short loc_180032D95
0x180032d49  mov     rdx, r8
0x180032d4c  cmp     rbx, r14
0x180032d4f  jnb     short loc_180032D6D
0x180032d51  mov     [rsp+2F0h+var_2A8], r8
0x180032d56  mov     rax, rbx
0x180032d59  mul     r12
0x180032d5c  test    rdx, rdx
0x180032d5f  jnz     short loc_180032D6A
0x180032d61  lea     rdx, [rdi+rax]
0x180032d65  cmp     rdx, rdi
0x180032d68  jnb     short loc_180032D6D
0x180032d6a  mov     rdx, r8
0x180032d6d  mov     rdx, [rdx]
0x180032d70  lea     rcx, [rbp+1F0h+Src]
0x180032d74  call    cs:__imp__o__wcsicmp
0x180032d7a  xor     r8d, r8d
0x180032d7d  test    eax, eax
0x180032d7f  jz      short loc_180032D8B
0x180032d81  add     rbx, r15
0x180032d84  cmp     rbx, r14
0x180032d87  jb      short loc_180032D49
0x180032d89  jmp     short loc_180032D95
0x180032d8b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180032d8f  jnz     loc_180032E20
0x180032d95  lea     rcx, [rbp+1F0h+Src]
0x180032d99  or      rax, 0FFFFFFFFFFFFFFFFh
0x180032d9d  inc     rax
0x180032da0  cmp     [rcx+rax*2], r8w
0x180032da5  jnz     short loc_180032D9D
0x180032da7  lea     rdi, ds:2[rax*2]
0x180032daf  mov     r8, rdi; dwBytes
0x180032db2  xor     edx, edx; dwFlags
0x180032db4  mov     rcx, r13; hHeap
0x180032db7  call    cs:__imp_HeapAlloc
0x180032dbd  mov     rbx, rax
0x180032dc0  test    rax, rax
0x180032dc3  jz      short loc_180032E0D
0x180032dc5  mov     r8, rdi; Size
0x180032dc8  xor     edx, edx; Val
0x180032dca  mov     rcx, rax; void *
0x180032dcd  call    memset_0
0x180032dd2  mov     [rsp+2F0h+var_2C0], rbx
0x180032dd7  mov     r8, rdi; Size
0x180032dda  lea     rdx, [rbp+1F0h+Src]; Src
0x180032dde  mov     rcx, rbx; void *
0x180032de1  call    memcpy_0
0x180032de6  lea     rdx, [rsp+2F0h+var_2C0]
0x180032deb  lea     rcx, [rsp+2F0h+var_2A0]
0x180032df0  call    ?Append@?$RtlArray@URTL_STRING_ITEM@RtlStringArray@@@@QEAAJAEBURTL_STRING_ITEM@RtlStringArray@@@Z; RtlArray<RtlStringArray::RTL_STRING_ITEM>::Append(RtlStringArray::RTL_STRING_ITEM const &)
0x180032df5  mov     r14, qword ptr [rsp+2F0h+var_290]
0x180032dfa  mov     r12, qword ptr [rsp+2F0h+var_2A0+8]
0x180032dff  mov     r13, qword ptr [rsp+2F0h+var_2A0]
0x180032e04  test    eax, eax
0x180032e06  jz      short loc_180032E20
0x180032e08  mov     rbx, [rsp+2F0h+var_2C0]
0x180032e0d  test    rbx, rbx
0x180032e10  jz      short loc_180032E20
0x180032e12  mov     r8, rbx; lpMem
0x180032e15  xor     edx, edx; dwFlags
0x180032e17  mov     rcx, r13; hHeap
0x180032e1a  call    cs:__imp_HeapFree
0x180032e20  mov     rcx, [rsi+58h]
0x180032e24  mov     rax, [rcx]
0x180032e27  mov     r8d, 104h
0x180032e2d  lea     rdx, [rbp+1F0h+Src]
0x180032e31  mov     rax, [rax+70h]
0x180032e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e3a  mov     ebx, eax
0x180032e3c  xor     r8d, r8d
0x180032e3f  test    eax, eax
0x180032e41  mov     rdi, qword ptr [rsp+2F0h+var_280+8]
0x180032e46  jns     loc_180032D31
0x180032e4c  mov     [rsp+2F0h+var_2C0], r12
0x180032e51  lea     r12, [rsi+68h]
0x180032e55  lea     r13, aTelcacheprovid_19; "TelCacheProvider::BatchEnd"
0x180032e5c  cmp     ebx, 80070103h
0x180032e62  jnz     short loc_180032E69
0x180032e64  mov     ebx, r8d
0x180032e67  jmp     short loc_180032E88
0x180032e69  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x180032e6d  lea     r9, aInventorycache_8; "InventoryCache::NextBatchMarkedItem fai"...
0x180032e74  mov     r8d, 492h
0x180032e7a  mov     rdx, r13
0x180032e7d  mov     ecx, r15d
0x180032e80  call    AslLogCallPrintf
0x180032e85  xor     r8d, r8d
0x180032e88  mov     [rsp+2F0h+var_2B0], r8d
0x180032e8d  cmp     [rsi+61h], r8b
0x180032e91  jz      short loc_180032EB7
0x180032e93  mov     rcx, [rsi]
0x180032e96  test    rcx, rcx
0x180032e99  jz      short loc_180032EB7
0x180032e9b  mov     rax, [rcx]
0x180032e9e  mov     rax, [rax+38h]
0x180032ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ea7  xor     r8d, r8d
0x180032eaa  test    al, al
0x180032eac  jz      short loc_180032EB7
0x180032eae  mov     [rsi+61h], r8b
0x180032eb2  jmp     loc_1800331AE
0x180032eb7  lea     rdx, [rsp+2F0h+var_2B0]; unsigned int *
0x180032ebc  mov     rcx, rsi; this
0x180032ebf  call    ?GetItemCount@TelCacheProvider@@QEAAJAEAK@Z; TelCacheProvider::GetItemCount(ulong &)
0x180032ec4  xor     r8d, r8d
0x180032ec7  test    eax, eax
0x180032ec9  js      loc_180033004
0x180032ecf  mov     eax, [rsp+2F0h+var_2B0]
0x180032ed3  shr     rax, 1
0x180032ed6  cmp     r14, rax
0x180032ed9  jbe     loc_180033004
0x180032edf  mov     edi, r8d
0x180032ee2  test    r14, r14
0x180032ee5  jz      short loc_180032F55
0x180032ee7  mov     r12, qword ptr [rsp+2F0h+var_280+8]
0x180032eec  mov     rdx, r8
0x180032eef  mov     eax, edi
0x180032ef1  cmp     rax, r14
0x180032ef4  jnb     short loc_180032F0C
0x180032ef6  mul     [rsp+2F0h+var_2C0]
0x180032efb  test    rdx, rdx
0x180032efe  jnz     short loc_180032F09
0x180032f00  lea     rdx, [r12+rax]
0x180032f04  cmp     rdx, r12
0x180032f07  jnb     short loc_180032F0C
0x180032f09  mov     rdx, r8
0x180032f0c  mov     rcx, [rsi+58h]
0x180032f10  mov     rax, [rcx]
0x180032f13  mov     rdx, [rdx]
0x180032f16  mov     rax, [rax+18h]
0x180032f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f1f  mov     ebx, eax
0x180032f21  xor     r8d, r8d
0x180032f24  test    eax, eax
0x180032f26  jns     short loc_180032F47
0x180032f28  mov     dword ptr [rsp+2F0h+var_2D0], eax
0x180032f2c  lea     r9, aInventorycache_11; "InventoryCache::RemoveItem failed. [%#x"...
0x180032f33  mov     r8d, 4ABh
0x180032f39  mov     rdx, r13
0x180032f3c  mov     ecx, r15d
0x180032f3f  call    AslLogCallPrintf
0x180032f44  xor     r8d, r8d
0x180032f47  add     edi, r15d
0x180032f4a  mov     eax, edi
0x180032f4c  cmp     rax, r14
0x180032f4f  jb      short loc_180032EEC
0x180032f51  lea     r12, [rsi+68h]
0x180032f55  mov     rcx, [rsi]
0x180032f58  test    rcx, rcx
0x180032f5b  jz      loc_1800331AE
0x180032f61  mov     rax, [rcx]
0x180032f64  mov     rax, [rax+38h]
0x180032f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f6d  xor     r8d, r8d
0x180032f70  test    al, al
0x180032f72  jz      loc_1800331AE
0x180032f78  mov     r14, [rsi]
0x180032f7b  mov     rcx, rsi; this
0x180032f7e  call    ?NewSyncId@TelCacheProvider@@AEAAXXZ; TelCacheProvider::NewSyncId(void)
0x180032f83  mov     rdx, r14; struct IAmiInventoryItem *
0x180032f86  mov     rcx, rsi; this
0x180032f89  call    ?GetFirstItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetFirstItem(IAmiInventoryItem *)
0x180032f8e  jmp     short loc_180032FD5
0x180032f90  mov     rax, [r14]
0x180032f93  mov     rdi, [rax+48h]
0x180032f97  mov     rcx, [rsi+58h]
0x180032f9b  mov     rax, [rcx]
0x180032f9e  mov     rax, [rax+88h]
0x180032fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032faa  xor     ebx, ebx
0x180032fac  test    eax, eax
0x180032fae  setz    bl
0x180032fb1  mov     rcx, rsi; this
0x180032fb4  call    ?RetrieveSyncId@TelCacheProvider@@AEAAPEBGXZ; TelCacheProvider::RetrieveSyncId(void)
0x180032fb9  mov     r8d, ebx
0x180032fbc  mov     rdx, rax
0x180032fbf  mov     rcx, r14
0x180032fc2  mov     rax, rdi
0x180032fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032fca  mov     rdx, r14; struct IAmiInventoryItem *
0x180032fcd  mov     rcx, rsi; this
0x180032fd0  call    ?GetNextItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetNextItem(IAmiInventoryItem *)
0x180032fd5  xor     r8d, r8d
0x180032fd8  test    eax, eax
0x180032fda  jns     short loc_180032F90
0x180032fdc  mov     ebx, r8d
0x180032fdf  cmp     eax, 80070103h
0x180032fe4  cmovnz  ebx, eax
0x180032fe7  test    ebx, ebx
0x180032fe9  jns     loc_1800331AE
0x180032fef  lea     r9, aInventorycache_10; "InventoryCache::GetNextItem failed. [%#"...
0x180032ff6  mov     r8d, 4C2h
0x180032ffc  mov     rdx, r13
0x180032fff  jmp     loc_180032CE4
0x180033004  mov     edx, r8d
0x180033007  mov     [rsp+2F0h+var_2AC], edx
0x18003300b  test    r14, r14
0x18003300e  jz      loc_1800331AE
0x180033014  mov     r12, [rsp+2F0h+var_2C0]
0x180033019  mov     rcx, r8
0x18003301c  mov     eax, edx
0x18003301e  cmp     rax, r14
0x180033021  jnb     short loc_18003303C
0x180033023  mov     [rsp+2F0h+var_2A8], r8
0x180033028  mul     r12
0x18003302b  test    rdx, rdx
0x18003302e  jnz     short loc_180033039
0x180033030  lea     rcx, [rdi+rax]
0x180033034  cmp     rcx, rdi
0x180033037  jnb     short loc_18003303C
0x180033039  mov     rcx, r8
0x18003303c  mov     rdi, [rcx]
0x18003303f  mov     [rsp+2F0h+var_2C0], rdi
0x180033044  mov     rcx, [rsi]
0x180033047  test    rcx, rcx
0x18003304a  jz      loc_180033154
0x180033050  mov     rax, [rcx]
0x180033053  mov     rax, [rax+38h]
0x180033057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003305c  test    al, al
0x18003305e  jz      loc_180033154
0x180033064  mov     rbx, [rsi]
0x180033067  mov     [rsp+2F0h+var_2A8], rbx
0x18003306c  mov     rax, [rbx]
0x18003306f  mov     rdx, rdi
  ... truncated ...
```
