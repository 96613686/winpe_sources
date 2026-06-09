# TelCacheProvider::RemoveItem(IAmiInventoryItem *)

- ea: `0x18001d750`
- end: `0x18001d8e2`
- name: `?RemoveItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, struct IAmiInventoryItem *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001cfb0`
- `0x180048300`

## callees

- `0x180010b3c`
- `0x180012888`
- `0x18001d750`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001d8c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001d8c5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d8cf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d8cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d8af`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d8af`

## string_xrefs

- `0x18001d81e`: `IAmiInventoryTelemetryItem::OnRemove failed [%#x]`
- `0x18001d85d`: `InventoryCache::RemoveItem(%ls) failed [%#x]`
- `0x18001d82f`: `TelCacheProvider::RemoveItem`
- `0x18001d873`: `TelCacheProvider::RemoveItem`

## pseudocode

```c
__int64 __fastcall TelCacheProvider::RemoveItem(TelCacheProvider *this, struct IAmiInventoryItem *a2)
{
  char *v5; // rsi
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64); // rbx
  __int64 v8; // rax
  signed int v9; // ebx
  __int64 (__fastcall *v10)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL); // rdi
  BOOL v11; // ebx
  const unsigned __int16 *SyncId; // rax
  int v13; // eax
  const wchar_t *v14; // rax
  __int64 v15; // rax
  char v16; // cl

  if ( !*((_QWORD *)this + 11) )
    return 2147500034LL;
  v5 = (char *)this + 104;
  Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((TelCacheProvider *)((char *)this + 104));
  v6 = *((_QWORD *)this + 11);
  v7 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 24LL);
  v8 = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 8LL))(a2);
  v9 = v7(v6, v8);
  if ( v9 < 0 )
  {
    if ( v9 == -2147024894 )
    {
      v9 = 0;
    }
    else
    {
      v14 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 8LL))(a2);
      AslLogCallPrintf(1, "TelCacheProvider::RemoveItem", 999, "InventoryCache::RemoveItem(%ls) failed [%#x]", v14, v9);
    }
  }
  else if ( (*(unsigned __int8 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 56LL))(a2)
         && !*((_BYTE *)this + 97) )
  {
    v10 = *(__int64 (__fastcall **)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL))(*(_QWORD *)a2 + 80LL);
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 136LL))(*((_QWORD *)this + 11)) == 0;
    SyncId = TelCacheProvider::RetrieveSyncId(this);
    v13 = v10(a2, SyncId, v11);
    v9 = v13;
    if ( v13 > 0 )
      v9 = (unsigned __int16)v13 | 0x80070000;
    if ( v9 < 0 )
      AslLogCallPrintf(1, "TelCacheProvider::RemoveItem", 985, "IAmiInventoryTelemetryItem::OnRemove failed [%#x]", v9);
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
      return (unsigned int)v9;
    goto LABEL_20;
  }
  if ( !WaitForSingleObject(*(HANDLE *)v5, 0xFFFFFFFF) )
  {
    --**((_DWORD **)v5 + 3);
    --*((_DWORD *)v5 + 8);
    ReleaseMutex(*(HANDLE *)v5);
LABEL_20:
    SetEvent(*((HANDLE *)v5 + 2));
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001d750  push    rbx
0x18001d752  push    rbp
0x18001d753  push    rsi
0x18001d754  push    rdi
0x18001d755  push    r14
0x18001d757  sub     rsp, 30h
0x18001d75b  cmp     qword ptr [rcx+58h], 0
0x18001d760  mov     r14, rdx
0x18001d763  mov     rbp, rcx
0x18001d766  jnz     short loc_18001D772
0x18001d768  mov     eax, 80004002h
0x18001d76d  jmp     loc_18001D8D7
0x18001d772  lea     rsi, [rcx+68h]
0x18001d776  mov     rcx, rsi; this
0x18001d779  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x18001d77e  mov     rdi, [rbp+58h]
0x18001d782  mov     rcx, r14
0x18001d785  mov     rax, [rdi]
0x18001d788  mov     rbx, [rax+18h]
0x18001d78c  mov     rax, [r14]
0x18001d78f  mov     rax, [rax+8]
0x18001d793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d798  mov     rdx, rax
0x18001d79b  mov     rcx, rdi
0x18001d79e  mov     rax, rbx
0x18001d7a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7a6  mov     ebx, eax
0x18001d7a8  test    eax, eax
0x18001d7aa  js      loc_18001D842
0x18001d7b0  mov     rcx, [r14]
0x18001d7b3  mov     rax, [rcx+38h]
0x18001d7b7  mov     rcx, r14
0x18001d7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7bf  test    al, al
0x18001d7c1  jz      loc_18001D884
0x18001d7c7  cmp     byte ptr [rbp+61h], 0
0x18001d7cb  jnz     loc_18001D884
0x18001d7d1  mov     rax, [r14]
0x18001d7d4  mov     rcx, [rbp+58h]
0x18001d7d8  mov     rdi, [rax+50h]
0x18001d7dc  mov     rax, [rcx]
0x18001d7df  mov     rax, [rax+88h]
0x18001d7e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7eb  xor     ebx, ebx
0x18001d7ed  mov     rcx, rbp; this
0x18001d7f0  test    eax, eax
0x18001d7f2  setz    bl
0x18001d7f5  call    ?RetrieveSyncId@TelCacheProvider@@AEAAPEBGXZ; TelCacheProvider::RetrieveSyncId(void)
0x18001d7fa  mov     rdx, rax
0x18001d7fd  mov     r8d, ebx
0x18001d800  mov     rax, rdi
0x18001d803  mov     rcx, r14
0x18001d806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d80b  mov     ebx, eax
0x18001d80d  test    eax, eax
0x18001d80f  jle     short loc_18001D81A
0x18001d811  movzx   ebx, ax
0x18001d814  or      ebx, 80070000h
0x18001d81a  test    ebx, ebx
0x18001d81c  jns     short loc_18001D884
0x18001d81e  lea     r9, aIamiinventoryt_0; "IAmiInventoryTelemetryItem::OnRemove fa"...
0x18001d825  mov     dword ptr [rsp+58h+var_38], ebx
0x18001d829  mov     r8d, 3D9h
0x18001d82f  lea     rdx, aTelcacheprovid_18; "TelCacheProvider::RemoveItem"
0x18001d836  mov     ecx, 1
0x18001d83b  call    AslLogCallPrintf
0x18001d840  jmp     short loc_18001D884
0x18001d842  cmp     ebx, 80070002h
0x18001d848  jnz     short loc_18001D84E
0x18001d84a  xor     ebx, ebx
0x18001d84c  jmp     short loc_18001D884
0x18001d84e  mov     rax, [r14]
0x18001d851  mov     rcx, r14
0x18001d854  mov     rax, [rax+8]
0x18001d858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d85d  lea     r9, aInventorycache_6; "InventoryCache::RemoveItem(%ls) failed "...
0x18001d864  mov     [rsp+58h+var_30], ebx
0x18001d868  mov     r8d, 3E7h
0x18001d86e  mov     [rsp+58h+var_38], rax
0x18001d873  lea     rdx, aTelcacheprovid_18; "TelCacheProvider::RemoveItem"
0x18001d87a  mov     ecx, 1
0x18001d87f  call    AslLogCallPrintf
0x18001d884  cmp     byte ptr [rsi+24h], 0
0x18001d888  jz      short loc_18001D8A7
0x18001d88a  mov     rax, [rsi+18h]
0x18001d88e  xor     cl, cl
0x18001d890  cmp     dword ptr [rax+4], 1
0x18001d894  jnz     short loc_18001D89B
0x18001d896  mov     [rsi+24h], cl
0x18001d899  mov     cl, 1
0x18001d89b  or      edi, 0FFFFFFFFh
0x18001d89e  add     [rax+4], edi
0x18001d8a1  test    cl, cl
0x18001d8a3  jz      short loc_18001D8D5
0x18001d8a5  jmp     short loc_18001D8CB
0x18001d8a7  mov     rcx, [rsi]; hHandle
0x18001d8aa  or      edi, 0FFFFFFFFh
0x18001d8ad  mov     edx, edi; dwMilliseconds
0x18001d8af  call    cs:__imp_WaitForSingleObject
0x18001d8b5  test    eax, eax
0x18001d8b7  jnz     short loc_18001D8D5
0x18001d8b9  mov     rax, [rsi+18h]
0x18001d8bd  add     [rax], edi
0x18001d8bf  add     [rsi+20h], edi
0x18001d8c2  mov     rcx, [rsi]; hMutex
0x18001d8c5  call    cs:__imp_ReleaseMutex
0x18001d8cb  mov     rcx, [rsi+10h]; hEvent
0x18001d8cf  call    cs:__imp_SetEvent
0x18001d8d5  mov     eax, ebx
0x18001d8d7  add     rsp, 30h
0x18001d8db  pop     r14
0x18001d8dd  pop     rdi
0x18001d8de  pop     rsi
0x18001d8df  pop     rbp
0x18001d8e0  pop     rbx
0x18001d8e1  retn
```
