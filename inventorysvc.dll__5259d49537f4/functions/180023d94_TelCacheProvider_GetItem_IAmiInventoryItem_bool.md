# TelCacheProvider::GetItem(IAmiInventoryItem *,bool)

- ea: `0x180023d94`
- end: `0x180023f6c`
- name: `?GetItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@_N@Z`
- size: `472`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, struct IAmiInventoryItem *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002a1bc`

## callees

- `0x1800152d0`
- `0x180021450`
- `0x180023d94`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180023f31`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180023f31`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180023f27`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180023f27`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023f11`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023f11`

## string_xrefs

- `0x180023e65`: `InventoryCache::ClearBatchMark failed. [%#x]`
- `0x180023e35`: `TelCacheProvider::GetItem`
- `0x180023e76`: `TelCacheProvider::GetItem`
- `0x180023ec4`: `TelCacheProvider::GetItem`
- `0x180023eb2`: `Failed to retrieve inventory item %ls from the cache`
- `0x180023e1f`: `InventoryCache::OpenItem(%ls) failed. [%#x]`

## pseudocode

```c
__int64 __fastcall TelCacheProvider::GetItem(TelCacheProvider *this, struct IAmiInventoryItem *a2)
{
  char *v5; // rsi
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64, __int64 *); // rbx
  __int64 v8; // rax
  int v9; // eax
  unsigned int v10; // ebx
  const wchar_t *v11; // rax
  int v12; // eax
  int v13; // edi
  const wchar_t *v14; // rax
  __int64 v15; // rax
  char v16; // cl
  __int64 v17; // [rsp+50h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 11) )
    return 2147500034LL;
  v5 = (char *)this + 104;
  v17 = 0;
  Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock((TelCacheProvider *)((char *)this + 104));
  v6 = *((_QWORD *)this + 11);
  v7 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v6 + 8LL);
  v8 = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 8LL))(a2);
  v9 = v7(v6, v8, &v17);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 160LL))(v17);
    v10 = v12;
    if ( v12 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *, __int64))(*(_QWORD *)a2 + 40LL))(a2, v17);
      if ( v13 )
      {
        v14 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 8LL))(a2);
        AslLogCallPrintf(
          3,
          "TelCacheProvider::GetItem",
          1040,
          "Failed to retrieve inventory item %ls from the cache",
          v14);
        if ( v13 > 0 )
          v10 = (unsigned __int16)v13 | 0x80070000;
        else
          v10 = v13;
      }
    }
    else
    {
      AslLogCallPrintf(1, "TelCacheProvider::GetItem", 1032, "InventoryCache::ClearBatchMark failed. [%#x]", v12);
    }
  }
  else if ( v9 != -2147024894 )
  {
    v11 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 8LL))(a2);
    AslLogCallPrintf(1, "TelCacheProvider::GetItem", 1022, "InventoryCache::OpenItem(%ls) failed. [%#x]", v11, v10);
  }
  if ( v5[36] )
  {
    v15 = *((_QWORD *)v5 + 3);
    v16 = 0;
    if ( *(_DWORD *)(v15 + 4) == 1 )
    {
      v5[36] = 0;
      v16 = 1;
    }
    --*(_DWORD *)(v15 + 4);
    if ( !v16 )
      goto LABEL_20;
    goto LABEL_19;
  }
  if ( !WaitForSingleObject(*(HANDLE *)v5, 0xFFFFFFFF) )
  {
    --**((_DWORD **)v5 + 3);
    --*((_DWORD *)v5 + 8);
    ReleaseMutex(*(HANDLE *)v5);
LABEL_19:
    SetEvent(*((HANDLE *)v5 + 2));
  }
LABEL_20:
  if ( v17 )
    (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 11) + 128LL))(*((_QWORD *)this + 11), &v17);
  return v10;
}

```

## disassembly

```asm
0x180023d94  mov     [rsp+arg_8], rbx
0x180023d99  mov     [rsp+arg_10], rbp
0x180023d9e  push    rsi
0x180023d9f  push    rdi
0x180023da0  push    r14
0x180023da2  sub     rsp, 30h
0x180023da6  cmp     qword ptr [rcx+58h], 0
0x180023dab  mov     r14, rdx
0x180023dae  mov     rbp, rcx
0x180023db1  jnz     short loc_180023DBD
0x180023db3  mov     eax, 80004002h
0x180023db8  jmp     loc_180023F59
0x180023dbd  lea     rsi, [rcx+68h]
0x180023dc1  mov     [rsp+48h+arg_0], 0
0x180023dca  mov     rcx, rsi; this
0x180023dcd  call    ?AcquireSharedLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock(void)
0x180023dd2  mov     rdi, [rbp+58h]
0x180023dd6  mov     rcx, r14
0x180023dd9  mov     rax, [rdi]
0x180023ddc  mov     rbx, [rax+8]
0x180023de0  mov     rax, [r14]
0x180023de3  mov     rax, [rax+8]
0x180023de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023dec  mov     rdx, rax
0x180023def  lea     r8, [rsp+48h+arg_0]
0x180023df4  mov     rax, rbx
0x180023df7  mov     rcx, rdi
0x180023dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023dff  mov     ebx, eax
0x180023e01  test    eax, eax
0x180023e03  jns     short loc_180023E4B
0x180023e05  cmp     eax, 80070002h
0x180023e0a  jz      loc_180023EE6
0x180023e10  mov     rcx, [r14]
0x180023e13  mov     rax, [rcx+8]
0x180023e17  mov     rcx, r14
0x180023e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e1f  lea     r9, aInventorycache_1; "InventoryCache::OpenItem(%ls) failed. ["...
0x180023e26  mov     [rsp+48h+var_20], ebx
0x180023e2a  mov     r8d, 3FEh
0x180023e30  mov     [rsp+48h+var_28], rax
0x180023e35  lea     rdx, aTelcacheprovid; "TelCacheProvider::GetItem"
0x180023e3c  mov     ecx, 1
0x180023e41  call    AslLogCallPrintf
0x180023e46  jmp     loc_180023EE6
0x180023e4b  mov     rcx, [rsp+48h+arg_0]
0x180023e50  mov     rax, [rcx]
0x180023e53  mov     rax, [rax+0A0h]
0x180023e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e5f  mov     ebx, eax
0x180023e61  test    eax, eax
0x180023e63  jns     short loc_180023E89
0x180023e65  lea     r9, aInventorycache; "InventoryCache::ClearBatchMark failed. "...
0x180023e6c  mov     dword ptr [rsp+48h+var_28], eax
0x180023e70  mov     r8d, 408h
0x180023e76  lea     rdx, aTelcacheprovid; "TelCacheProvider::GetItem"
0x180023e7d  mov     ecx, 1
0x180023e82  call    AslLogCallPrintf
0x180023e87  jmp     short loc_180023EE6
0x180023e89  mov     rax, [r14]
0x180023e8c  mov     rcx, r14
0x180023e8f  mov     rdx, [rsp+48h+arg_0]
0x180023e94  mov     rax, [rax+28h]
0x180023e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e9d  mov     edi, eax
0x180023e9f  test    eax, eax
0x180023ea1  jz      short loc_180023EE6
0x180023ea3  mov     rcx, [r14]
0x180023ea6  mov     rax, [rcx+8]
0x180023eaa  mov     rcx, r14
0x180023ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023eb2  lea     r9, aFailedToRetrie; "Failed to retrieve inventory item %ls f"...
0x180023eb9  mov     [rsp+48h+var_28], rax
0x180023ebe  mov     r8d, 410h
0x180023ec4  lea     rdx, aTelcacheprovid; "TelCacheProvider::GetItem"
0x180023ecb  mov     ecx, 3
0x180023ed0  call    AslLogCallPrintf
0x180023ed5  test    edi, edi
0x180023ed7  jg      short loc_180023EDD
0x180023ed9  mov     ebx, edi
0x180023edb  jmp     short loc_180023EE6
0x180023edd  movzx   ebx, di
0x180023ee0  or      ebx, 80070000h
0x180023ee6  cmp     byte ptr [rsi+24h], 0
0x180023eea  jz      short loc_180023F09
0x180023eec  mov     rax, [rsi+18h]
0x180023ef0  xor     cl, cl
0x180023ef2  cmp     dword ptr [rax+4], 1
0x180023ef6  jnz     short loc_180023EFD
0x180023ef8  mov     [rsi+24h], cl
0x180023efb  mov     cl, 1
0x180023efd  or      edi, 0FFFFFFFFh
0x180023f00  add     [rax+4], edi
0x180023f03  test    cl, cl
0x180023f05  jz      short loc_180023F37
0x180023f07  jmp     short loc_180023F2D
0x180023f09  mov     rcx, [rsi]; hHandle
0x180023f0c  or      edi, 0FFFFFFFFh
0x180023f0f  mov     edx, edi; dwMilliseconds
0x180023f11  call    cs:__imp_WaitForSingleObject
0x180023f17  test    eax, eax
0x180023f19  jnz     short loc_180023F37
0x180023f1b  mov     rax, [rsi+18h]
0x180023f1f  add     [rax], edi
0x180023f21  add     [rsi+20h], edi
0x180023f24  mov     rcx, [rsi]; hMutex
0x180023f27  call    cs:__imp_ReleaseMutex
0x180023f2d  mov     rcx, [rsi+10h]; hEvent
0x180023f31  call    cs:__imp_SetEvent
0x180023f37  cmp     [rsp+48h+arg_0], 0
0x180023f3d  jz      short loc_180023F57
0x180023f3f  mov     rcx, [rbp+58h]
0x180023f43  lea     rdx, [rsp+48h+arg_0]
0x180023f48  mov     rax, [rcx]
0x180023f4b  mov     rax, [rax+80h]
0x180023f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f57  mov     eax, ebx
0x180023f59  mov     rbx, [rsp+48h+arg_8]
0x180023f5e  mov     rbp, [rsp+48h+arg_10]
0x180023f63  add     rsp, 30h
0x180023f67  pop     r14
0x180023f69  pop     rdi
0x180023f6a  pop     rsi
0x180023f6b  retn
```
