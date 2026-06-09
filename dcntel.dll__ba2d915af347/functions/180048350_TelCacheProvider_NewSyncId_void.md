# TelCacheProvider::NewSyncId(void)

- ea: `0x180048350`
- end: `0x18004855f`
- name: `?NewSyncId@TelCacheProvider@@AEAAXXZ`
- size: `527`
- prototype: `void __fastcall(TelCacheProvider *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180041fcc`
- `0x1800495f8`
- `0x1800496e0`

## callees

- `0x180008dc0`
- `0x1800413d4`
- `0x180048350`
- `0x18004b3e8`
- `0x18016796c`
- `0x180168eec`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180048542`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180048542`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180048522`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180048522`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180048538`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180048538`
- `RPCRT4!UuidCreate` at `0x1800483a3`
- `RPCRT4!UuidCreate` at `0x1800483a3`

## string_xrefs

- `0x1800483f2`: `InventoryCache::SetMetadata failed [%#x]`
- `0x1800484c2`: `InventoryCache::BatchBegin failed [%#x]`
- `0x180048462`: `TelCacheProvider::NewSyncId`
- `0x180048493`: `TelCacheProvider::NewSyncId`
- `0x1800484e6`: `TelCacheProvider::NewSyncId`
- `0x180048451`: `InventoryCache::GetItemCount failed [%#x]`
- `0x180048486`: `New syncId generated for a non-empty cache so forcing a full sync`

## pseudocode

```c
void __fastcall TelCacheProvider::NewSyncId(TelCacheProvider *this)
{
  char *v1; // rbx
  __int64 v3; // rdx
  int v4; // eax
  int v5; // eax
  __int64 v6; // r14
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rax
  char v13; // cl
  int v14; // [rsp+20h] [rbp-58h]
  int v15; // [rsp+20h] [rbp-58h]
  int v16; // [rsp+20h] [rbp-58h]
  int v17; // [rsp+20h] [rbp-58h]
  int v18; // [rsp+30h] [rbp-48h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-40h] BYREF

  v1 = (char *)this + 104;
  Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((TelCacheProvider *)((char *)this + 104));
  if ( *(_QWORD *)this && *((_QWORD *)this + 11) )
  {
    Uuid = 0;
    *((_WORD *)this + 4) = 0;
    UuidCreate(&Uuid);
    v4 = AslGuidToString((char *)this + 8, v3, &Uuid);
    if ( v4 )
    {
      v14 = v4;
      AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1734, "AslGuidToString failed [%d]", v14);
      goto LABEL_16;
    }
    v5 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, char *))(**((_QWORD **)this + 11) + 80LL))(
           *((_QWORD *)this + 11),
           L"ProviderSyncId",
           (char *)this + 8);
    if ( v5 < 0 )
    {
      v15 = v5;
      AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1742, "InventoryCache::SetMetadata failed [%#x]", v15);
      goto LABEL_16;
    }
    v6 = *(_QWORD *)this;
    if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 136LL))(*((_QWORD *)this + 11)) )
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v6 + 88LL))(v6, (char *)this + 8);
    v7 = *((_QWORD *)this + 11);
    v18 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v7 + 32LL))(v7, &v18);
    if ( v8 < 0 )
    {
      AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1757, "InventoryCache::GetItemCount failed [%#x]", v8);
LABEL_11:
      TelCacheProvider::ShouldForceFullSync(this, 0);
      goto LABEL_16;
    }
    if ( !v18 )
      goto LABEL_11;
    AslLogCallPrintf(
      3,
      "TelCacheProvider::NewSyncId",
      1767,
      "New syncId generated for a non-empty cache so forcing a full sync");
    v9 = *((_QWORD *)this + 11);
    LOBYTE(v10) = 1;
    *((_BYTE *)this + 97) = 1;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 104LL))(v9, v10);
    if ( v11 >= 0 )
      goto LABEL_11;
    v16 = v11;
    AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1773, "InventoryCache::BatchBegin failed [%#x]", v16);
  }
  else
  {
    v17 = -2147024809;
    AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1719, "Object not yet initialized. [%#x]", v17);
  }
LABEL_16:
  if ( !v1[36] )
  {
    if ( WaitForSingleObject(*(HANDLE *)v1, 0xFFFFFFFF) )
      return;
    --**((_DWORD **)v1 + 3);
    --*((_DWORD *)v1 + 8);
    ReleaseMutex(*(HANDLE *)v1);
    goto LABEL_23;
  }
  v12 = *((_QWORD *)v1 + 3);
  v13 = 0;
  if ( *(_DWORD *)(v12 + 4) == 1 )
  {
    v1[36] = 0;
    v13 = 1;
  }
  --*(_DWORD *)(v12 + 4);
  if ( v13 )
LABEL_23:
    SetEvent(*((HANDLE *)v1 + 2));
}

```

## disassembly

```asm
0x180048350  push    rbx
0x180048352  push    rsi
0x180048353  push    rdi
0x180048354  push    r14
0x180048356  sub     rsp, 58h
0x18004835a  mov     rax, cs:__security_cookie
0x180048361  xor     rax, rsp
0x180048364  mov     [rsp+78h+var_30], rax
0x180048369  lea     rbx, [rcx+68h]
0x18004836d  mov     rdi, rcx
0x180048370  mov     rcx, rbx; this
0x180048373  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x180048378  cmp     qword ptr [rdi], 0
0x18004837c  jz      loc_1800484D1
0x180048382  cmp     qword ptr [rdi+58h], 0
0x180048387  jz      loc_1800484D1
0x18004838d  xorps   xmm0, xmm0
0x180048390  lea     rsi, [rdi+8]
0x180048394  xor     eax, eax
0x180048396  lea     rcx, [rsp+78h+Uuid]; Uuid
0x18004839b  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x1800483a0  mov     [rsi], ax
0x1800483a3  call    cs:__imp_UuidCreate
0x1800483a9  lea     r8, [rsp+78h+Uuid]
0x1800483ae  mov     rcx, rsi
0x1800483b1  call    AslGuidToString
0x1800483b6  test    eax, eax
0x1800483b8  jz      short loc_1800483D0
0x1800483ba  mov     [rsp+78h+var_58], eax
0x1800483be  lea     r9, aAslguidtostrin; "AslGuidToString failed [%d]"
0x1800483c5  mov     r8d, 6C6h
0x1800483cb  jmp     loc_1800484E6
0x1800483d0  mov     rcx, [rdi+58h]
0x1800483d4  lea     rdx, aProvidersyncid; "ProviderSyncId"
0x1800483db  mov     r8, rsi
0x1800483de  mov     rax, [rcx]
0x1800483e1  mov     rax, [rax+50h]
0x1800483e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800483ea  test    eax, eax
0x1800483ec  jns     short loc_180048404
0x1800483ee  mov     [rsp+78h+var_58], eax
0x1800483f2  lea     r9, aInventorycache_4; "InventoryCache::SetMetadata failed [%#x"...
0x1800483f9  mov     r8d, 6CEh
0x1800483ff  jmp     loc_1800484E6
0x180048404  mov     rcx, [rdi+58h]
0x180048408  mov     r14, [rdi]
0x18004840b  mov     rax, [rcx]
0x18004840e  mov     rax, [rax+88h]
0x180048415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004841a  test    eax, eax
0x18004841c  jnz     short loc_180048430
0x18004841e  mov     rax, [r14]
0x180048421  mov     rdx, rsi
0x180048424  mov     rcx, r14
0x180048427  mov     rax, [rax+58h]
0x18004842b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048430  mov     rcx, [rdi+58h]
0x180048434  lea     rdx, [rsp+78h+var_48]
0x180048439  mov     [rsp+78h+var_48], 0
0x180048441  mov     rax, [rcx]
0x180048444  mov     rax, [rax+20h]
0x180048448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004844d  test    eax, eax
0x18004844f  jns     short loc_18004847F
0x180048451  lea     r9, aInventorycache_2; "InventoryCache::GetItemCount failed [%#"...
0x180048458  mov     [rsp+78h+var_58], eax
0x18004845c  mov     r8d, 6DDh
0x180048462  lea     rdx, aTelcacheprovid_8; "TelCacheProvider::NewSyncId"
0x180048469  mov     ecx, 1
0x18004846e  call    AslLogCallPrintf
0x180048473  xor     edx, edx; unsigned __int16 *
0x180048475  mov     rcx, rdi; this
0x180048478  call    ?ShouldForceFullSync@TelCacheProvider@@AEAAHPEBG@Z; TelCacheProvider::ShouldForceFullSync(ushort const *)
0x18004847d  jmp     short loc_1800484F7
0x18004847f  cmp     [rsp+78h+var_48], 0
0x180048484  jbe     short loc_180048473
0x180048486  lea     r9, aNewSyncidGener; "New syncId generated for a non-empty ca"...
0x18004848d  mov     r8d, 6E7h
0x180048493  lea     rdx, aTelcacheprovid_8; "TelCacheProvider::NewSyncId"
0x18004849a  mov     ecx, 3
0x18004849f  call    AslLogCallPrintf
0x1800484a4  mov     rcx, [rdi+58h]
0x1800484a8  mov     dl, 1
0x1800484aa  mov     byte ptr [rdi+61h], 1
0x1800484ae  mov     rax, [rcx]
0x1800484b1  mov     rax, [rax+68h]
0x1800484b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484ba  test    eax, eax
0x1800484bc  jns     short loc_180048473
0x1800484be  mov     [rsp+78h+var_58], eax
0x1800484c2  lea     r9, aInventorycache_8; "InventoryCache::BatchBegin failed [%#x]"
0x1800484c9  mov     r8d, 6EDh
0x1800484cf  jmp     short loc_1800484E6
0x1800484d1  mov     [rsp+78h+var_58], 80070057h
0x1800484d9  lea     r9, aObjectNotYetIn; "Object not yet initialized. [%#x]"
0x1800484e0  mov     r8d, 6B7h
0x1800484e6  lea     rdx, aTelcacheprovid_8; "TelCacheProvider::NewSyncId"
0x1800484ed  mov     ecx, 1
0x1800484f2  call    AslLogCallPrintf
0x1800484f7  cmp     byte ptr [rbx+24h], 0
0x1800484fb  jz      short loc_18004851A
0x1800484fd  mov     rax, [rbx+18h]
0x180048501  xor     cl, cl
0x180048503  cmp     dword ptr [rax+4], 1
0x180048507  jnz     short loc_18004850E
0x180048509  mov     [rbx+24h], cl
0x18004850c  mov     cl, 1
0x18004850e  or      edi, 0FFFFFFFFh
0x180048511  add     [rax+4], edi
0x180048514  test    cl, cl
0x180048516  jz      short loc_180048548
0x180048518  jmp     short loc_18004853E
0x18004851a  mov     rcx, [rbx]; hHandle
0x18004851d  or      edi, 0FFFFFFFFh
0x180048520  mov     edx, edi; dwMilliseconds
0x180048522  call    cs:__imp_WaitForSingleObject
0x180048528  test    eax, eax
0x18004852a  jnz     short loc_180048548
0x18004852c  mov     rax, [rbx+18h]
0x180048530  add     [rax], edi
0x180048532  add     [rbx+20h], edi
0x180048535  mov     rcx, [rbx]; hMutex
0x180048538  call    cs:__imp_ReleaseMutex
0x18004853e  mov     rcx, [rbx+10h]; hEvent
0x180048542  call    cs:__imp_SetEvent
0x180048548  mov     rcx, [rsp+78h+var_30]
0x18004854d  xor     rcx, rsp; StackCookie
0x180048550  call    __security_check_cookie
0x180048555  add     rsp, 58h
0x180048559  pop     r14
0x18004855b  pop     rdi
0x18004855c  pop     rsi
0x18004855d  pop     rbx
0x18004855e  retn
```
