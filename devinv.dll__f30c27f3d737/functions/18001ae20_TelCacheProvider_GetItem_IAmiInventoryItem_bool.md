# TelCacheProvider::GetItem(IAmiInventoryItem *,bool)

- ea: `0x18001ae20`
- end: `0x18001aff5`
- name: `?GetItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@_N@Z`
- size: `469`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, struct IAmiInventoryItem *, bool)`
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001cfb0`
- `0x18001d310`
- `0x18002f0f4`
- `0x180032c14`
- `0x180049694`
- `0x18004f594`
- `0x180052200`
- `0x18005b1cc`
- `0x18005d170`

## callees

- `0x180010c08`
- `0x18001ae20`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001afb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001afb6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001afc0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001afc0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001afa0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001afa0`

## string_xrefs

- `0x18001aef4`: `InventoryCache::ClearBatchMark failed. [%#x]`
- `0x18001aea9`: `InventoryCache::OpenItem(%ls) failed. [%#x]`
- `0x18001af41`: `Failed to retrieve inventory item %ls from the cache`
- `0x18001aebf`: `TelCacheProvider::GetItem`
- `0x18001af05`: `TelCacheProvider::GetItem`
- `0x18001af53`: `TelCacheProvider::GetItem`

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
0x18001ae20  push    rbx
0x18001ae22  push    rbp
0x18001ae23  push    rsi
0x18001ae24  push    rdi
0x18001ae25  push    r14
0x18001ae27  push    r15
0x18001ae29  sub     rsp, 38h
0x18001ae2d  cmp     qword ptr [rcx+58h], 0
0x18001ae32  mov     r15b, r8b
0x18001ae35  mov     r14, rdx
0x18001ae38  mov     rbp, rcx
0x18001ae3b  jnz     short loc_18001AE47
0x18001ae3d  mov     eax, 80004002h
0x18001ae42  jmp     loc_18001AFE8
0x18001ae47  lea     rsi, [rcx+68h]
0x18001ae4b  mov     [rsp+68h+arg_0], 0
0x18001ae54  mov     rcx, rsi; this
0x18001ae57  call    ?AcquireSharedLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock(void)
0x18001ae5c  mov     rdi, [rbp+58h]
0x18001ae60  mov     rcx, r14
0x18001ae63  mov     rax, [rdi]
0x18001ae66  mov     rbx, [rax+8]
0x18001ae6a  mov     rax, [r14]
0x18001ae6d  mov     rax, [rax+8]
0x18001ae71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae76  mov     rdx, rax
0x18001ae79  lea     r8, [rsp+68h+arg_0]
0x18001ae7e  mov     rax, rbx
0x18001ae81  mov     rcx, rdi
0x18001ae84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae89  mov     ebx, eax
0x18001ae8b  test    eax, eax
0x18001ae8d  jns     short loc_18001AED5
0x18001ae8f  cmp     eax, 80070002h
0x18001ae94  jz      loc_18001AF75
0x18001ae9a  mov     rcx, [r14]
0x18001ae9d  mov     rax, [rcx+8]
0x18001aea1  mov     rcx, r14
0x18001aea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aea9  lea     r9, aInventorycache_1; "InventoryCache::OpenItem(%ls) failed. ["...
0x18001aeb0  mov     [rsp+68h+var_40], ebx
0x18001aeb4  mov     r8d, 3FEh
0x18001aeba  mov     [rsp+68h+var_48], rax
0x18001aebf  lea     rdx, aTelcacheprovid; "TelCacheProvider::GetItem"
0x18001aec6  mov     ecx, 1
0x18001aecb  call    AslLogCallPrintf
0x18001aed0  jmp     loc_18001AF75
0x18001aed5  test    r15b, r15b
0x18001aed8  jz      short loc_18001AF18
0x18001aeda  mov     rcx, [rsp+68h+arg_0]
0x18001aedf  mov     rax, [rcx]
0x18001aee2  mov     rax, [rax+0A0h]
0x18001aee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aeee  mov     ebx, eax
0x18001aef0  test    eax, eax
0x18001aef2  jns     short loc_18001AF18
0x18001aef4  lea     r9, aInventorycache; "InventoryCache::ClearBatchMark failed. "...
0x18001aefb  mov     dword ptr [rsp+68h+var_48], eax
0x18001aeff  mov     r8d, 408h
0x18001af05  lea     rdx, aTelcacheprovid; "TelCacheProvider::GetItem"
0x18001af0c  mov     ecx, 1
0x18001af11  call    AslLogCallPrintf
0x18001af16  jmp     short loc_18001AF75
0x18001af18  mov     rax, [r14]
0x18001af1b  mov     rcx, r14
0x18001af1e  mov     rdx, [rsp+68h+arg_0]
0x18001af23  mov     rax, [rax+28h]
0x18001af27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af2c  mov     edi, eax
0x18001af2e  test    eax, eax
0x18001af30  jz      short loc_18001AF75
0x18001af32  mov     rcx, [r14]
0x18001af35  mov     rax, [rcx+8]
0x18001af39  mov     rcx, r14
0x18001af3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af41  lea     r9, aFailedToRetrie; "Failed to retrieve inventory item %ls f"...
0x18001af48  mov     [rsp+68h+var_48], rax
0x18001af4d  mov     r8d, 410h
0x18001af53  lea     rdx, aTelcacheprovid; "TelCacheProvider::GetItem"
0x18001af5a  mov     ecx, 3
0x18001af5f  call    AslLogCallPrintf
0x18001af64  test    edi, edi
0x18001af66  jg      short loc_18001AF6C
0x18001af68  mov     ebx, edi
0x18001af6a  jmp     short loc_18001AF75
0x18001af6c  movzx   ebx, di
0x18001af6f  or      ebx, 80070000h
0x18001af75  cmp     byte ptr [rsi+24h], 0
0x18001af79  jz      short loc_18001AF98
0x18001af7b  mov     rax, [rsi+18h]
0x18001af7f  xor     cl, cl
0x18001af81  cmp     dword ptr [rax+4], 1
0x18001af85  jnz     short loc_18001AF8C
0x18001af87  mov     [rsi+24h], cl
0x18001af8a  mov     cl, 1
0x18001af8c  or      edi, 0FFFFFFFFh
0x18001af8f  add     [rax+4], edi
0x18001af92  test    cl, cl
0x18001af94  jz      short loc_18001AFC6
0x18001af96  jmp     short loc_18001AFBC
0x18001af98  mov     rcx, [rsi]; hHandle
0x18001af9b  or      edi, 0FFFFFFFFh
0x18001af9e  mov     edx, edi; dwMilliseconds
0x18001afa0  call    cs:__imp_WaitForSingleObject
0x18001afa6  test    eax, eax
0x18001afa8  jnz     short loc_18001AFC6
0x18001afaa  mov     rax, [rsi+18h]
0x18001afae  add     [rax], edi
0x18001afb0  add     [rsi+20h], edi
0x18001afb3  mov     rcx, [rsi]; hMutex
0x18001afb6  call    cs:__imp_ReleaseMutex
0x18001afbc  mov     rcx, [rsi+10h]; hEvent
0x18001afc0  call    cs:__imp_SetEvent
0x18001afc6  cmp     [rsp+68h+arg_0], 0
0x18001afcc  jz      short loc_18001AFE6
0x18001afce  mov     rcx, [rbp+58h]
0x18001afd2  lea     rdx, [rsp+68h+arg_0]
0x18001afd7  mov     rax, [rcx]
0x18001afda  mov     rax, [rax+80h]
0x18001afe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afe6  mov     eax, ebx
0x18001afe8  add     rsp, 38h
0x18001afec  pop     r15
0x18001afee  pop     r14
0x18001aff0  pop     rdi
0x18001aff1  pop     rsi
0x18001aff2  pop     rbp
0x18001aff3  pop     rbx
0x18001aff4  retn
```
