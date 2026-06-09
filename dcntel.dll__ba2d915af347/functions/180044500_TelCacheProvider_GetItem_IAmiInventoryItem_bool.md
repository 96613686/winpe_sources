# TelCacheProvider::GetItem(IAmiInventoryItem *,bool)

- ea: `0x180044500`
- end: `0x1800446d5`
- name: `?GetItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@_N@Z`
- size: `469`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, struct IAmiInventoryItem *, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180041fcc`
- `0x1800496e0`

## callees

- `0x1800414a0`
- `0x180044500`
- `0x18016796c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800446a0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800446a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044680`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044680`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180044696`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180044696`

## string_xrefs

- `0x1800445d4`: `InventoryCache::ClearBatchMark failed. [%#x]`
- `0x18004459f`: `TelCacheProvider::GetItem`
- `0x1800445e5`: `TelCacheProvider::GetItem`
- `0x180044633`: `TelCacheProvider::GetItem`
- `0x180044621`: `Failed to retrieve inventory item %ls from the cache`
- `0x180044589`: `InventoryCache::OpenItem(%ls) failed. [%#x]`

## pseudocode

```c
__int64 __fastcall TelCacheProvider::GetItem(TelCacheProvider *this, struct IAmiInventoryItem *a2, char a3)
{
  char *v7; // rsi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, __int64 *); // rbx
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // ebx
  const wchar_t *v13; // rax
  int v14; // eax
  int v15; // edi
  const wchar_t *v16; // rax
  __int64 v17; // rax
  char v18; // cl
  __int64 v19; // [rsp+70h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 11) )
    return 2147500034LL;
  v7 = (char *)this + 104;
  v19 = 0;
  Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock((TelCacheProvider *)((char *)this + 104));
  v8 = *((_QWORD *)this + 11);
  v9 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v8 + 8LL);
  v10 = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 8LL))(a2);
  v11 = v9(v8, v10, &v19);
  v12 = v11;
  if ( v11 >= 0 )
  {
    if ( a3 && (v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 160LL))(v19), v12 = v14, v14 < 0) )
    {
      AslLogCallPrintf(1, "TelCacheProvider::GetItem", 1032, "InventoryCache::ClearBatchMark failed. [%#x]", v14);
    }
    else
    {
      v15 = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *, __int64))(*(_QWORD *)a2 + 40LL))(a2, v19);
      if ( v15 )
      {
        v16 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 8LL))(a2);
        AslLogCallPrintf(
          3,
          "TelCacheProvider::GetItem",
          1040,
          "Failed to retrieve inventory item %ls from the cache",
          v16);
        if ( v15 > 0 )
          v12 = (unsigned __int16)v15 | 0x80070000;
        else
          v12 = v15;
      }
    }
  }
  else if ( v11 != -2147024894 )
  {
    v13 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 8LL))(a2);
    AslLogCallPrintf(1, "TelCacheProvider::GetItem", 1022, "InventoryCache::OpenItem(%ls) failed. [%#x]", v13, v12);
  }
  if ( v7[36] )
  {
    v17 = *((_QWORD *)v7 + 3);
    v18 = 0;
    if ( *(_DWORD *)(v17 + 4) == 1 )
    {
      v7[36] = 0;
      v18 = 1;
    }
    --*(_DWORD *)(v17 + 4);
    if ( !v18 )
      goto LABEL_21;
    goto LABEL_20;
  }
  if ( !WaitForSingleObject(*(HANDLE *)v7, 0xFFFFFFFF) )
  {
    --**((_DWORD **)v7 + 3);
    --*((_DWORD *)v7 + 8);
    ReleaseMutex(*(HANDLE *)v7);
LABEL_20:
    SetEvent(*((HANDLE *)v7 + 2));
  }
LABEL_21:
  if ( v19 )
    (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 11) + 128LL))(*((_QWORD *)this + 11), &v19);
  return v12;
}

```

## disassembly

```asm
0x180044500  push    rbx
0x180044502  push    rbp
0x180044503  push    rsi
0x180044504  push    rdi
0x180044505  push    r14
0x180044507  push    r15
0x180044509  sub     rsp, 38h
0x18004450d  cmp     qword ptr [rcx+58h], 0
0x180044512  mov     r15b, r8b
0x180044515  mov     r14, rdx
0x180044518  mov     rbp, rcx
0x18004451b  jnz     short loc_180044527
0x18004451d  mov     eax, 80004002h
0x180044522  jmp     loc_1800446C8
0x180044527  lea     rsi, [rcx+68h]
0x18004452b  mov     [rsp+68h+arg_0], 0
0x180044534  mov     rcx, rsi; this
0x180044537  call    ?AcquireSharedLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock(void)
0x18004453c  mov     rdi, [rbp+58h]
0x180044540  mov     rcx, r14
0x180044543  mov     rax, [rdi]
0x180044546  mov     rbx, [rax+8]
0x18004454a  mov     rax, [r14]
0x18004454d  mov     rax, [rax+8]
0x180044551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044556  mov     rdx, rax
0x180044559  lea     r8, [rsp+68h+arg_0]
0x18004455e  mov     rax, rbx
0x180044561  mov     rcx, rdi
0x180044564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044569  mov     ebx, eax
0x18004456b  test    eax, eax
0x18004456d  jns     short loc_1800445B5
0x18004456f  cmp     eax, 80070002h
0x180044574  jz      loc_180044655
0x18004457a  mov     rcx, [r14]
0x18004457d  mov     rax, [rcx+8]
0x180044581  mov     rcx, r14
0x180044584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044589  lea     r9, aInventorycache_1; "InventoryCache::OpenItem(%ls) failed. ["...
0x180044590  mov     [rsp+68h+var_40], ebx
0x180044594  mov     r8d, 3FEh
0x18004459a  mov     [rsp+68h+var_48], rax
0x18004459f  lea     rdx, aTelcacheprovid; "TelCacheProvider::GetItem"
0x1800445a6  mov     ecx, 1
0x1800445ab  call    AslLogCallPrintf
0x1800445b0  jmp     loc_180044655
0x1800445b5  test    r15b, r15b
0x1800445b8  jz      short loc_1800445F8
0x1800445ba  mov     rcx, [rsp+68h+arg_0]
0x1800445bf  mov     rax, [rcx]
0x1800445c2  mov     rax, [rax+0A0h]
0x1800445c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445ce  mov     ebx, eax
0x1800445d0  test    eax, eax
0x1800445d2  jns     short loc_1800445F8
0x1800445d4  lea     r9, aInventorycache; "InventoryCache::ClearBatchMark failed. "...
0x1800445db  mov     dword ptr [rsp+68h+var_48], eax
0x1800445df  mov     r8d, 408h
0x1800445e5  lea     rdx, aTelcacheprovid; "TelCacheProvider::GetItem"
0x1800445ec  mov     ecx, 1
0x1800445f1  call    AslLogCallPrintf
0x1800445f6  jmp     short loc_180044655
0x1800445f8  mov     rax, [r14]
0x1800445fb  mov     rcx, r14
0x1800445fe  mov     rdx, [rsp+68h+arg_0]
0x180044603  mov     rax, [rax+28h]
0x180044607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004460c  mov     edi, eax
0x18004460e  test    eax, eax
0x180044610  jz      short loc_180044655
0x180044612  mov     rcx, [r14]
0x180044615  mov     rax, [rcx+8]
0x180044619  mov     rcx, r14
0x18004461c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044621  lea     r9, aFailedToRetrie; "Failed to retrieve inventory item %ls f"...
0x180044628  mov     [rsp+68h+var_48], rax
0x18004462d  mov     r8d, 410h
0x180044633  lea     rdx, aTelcacheprovid; "TelCacheProvider::GetItem"
0x18004463a  mov     ecx, 3
0x18004463f  call    AslLogCallPrintf
0x180044644  test    edi, edi
0x180044646  jg      short loc_18004464C
0x180044648  mov     ebx, edi
0x18004464a  jmp     short loc_180044655
0x18004464c  movzx   ebx, di
0x18004464f  or      ebx, 80070000h
0x180044655  cmp     byte ptr [rsi+24h], 0
0x180044659  jz      short loc_180044678
0x18004465b  mov     rax, [rsi+18h]
0x18004465f  xor     cl, cl
0x180044661  cmp     dword ptr [rax+4], 1
0x180044665  jnz     short loc_18004466C
0x180044667  mov     [rsi+24h], cl
0x18004466a  mov     cl, 1
0x18004466c  or      edi, 0FFFFFFFFh
0x18004466f  add     [rax+4], edi
0x180044672  test    cl, cl
0x180044674  jz      short loc_1800446A6
0x180044676  jmp     short loc_18004469C
0x180044678  mov     rcx, [rsi]; hHandle
0x18004467b  or      edi, 0FFFFFFFFh
0x18004467e  mov     edx, edi; dwMilliseconds
0x180044680  call    cs:__imp_WaitForSingleObject
0x180044686  test    eax, eax
0x180044688  jnz     short loc_1800446A6
0x18004468a  mov     rax, [rsi+18h]
0x18004468e  add     [rax], edi
0x180044690  add     [rsi+20h], edi
0x180044693  mov     rcx, [rsi]; hMutex
0x180044696  call    cs:__imp_ReleaseMutex
0x18004469c  mov     rcx, [rsi+10h]; hEvent
0x1800446a0  call    cs:__imp_SetEvent
0x1800446a6  cmp     [rsp+68h+arg_0], 0
0x1800446ac  jz      short loc_1800446C6
0x1800446ae  mov     rcx, [rbp+58h]
0x1800446b2  lea     rdx, [rsp+68h+arg_0]
0x1800446b7  mov     rax, [rcx]
0x1800446ba  mov     rax, [rax+80h]
0x1800446c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800446c6  mov     eax, ebx
0x1800446c8  add     rsp, 38h
0x1800446cc  pop     r15
0x1800446ce  pop     r14
0x1800446d0  pop     rdi
0x1800446d1  pop     rsi
0x1800446d2  pop     rbp
0x1800446d3  pop     rbx
0x1800446d4  retn
```
