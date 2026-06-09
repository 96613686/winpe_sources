# TelCacheProvider::NewSyncId(void)

- ea: `0x180012078`
- end: `0x180012287`
- name: `?NewSyncId@TelCacheProvider@@AEAAXXZ`
- size: `527`
- prototype: `void __fastcall(TelCacheProvider *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180012888`
- `0x18002f0f4`
- `0x180032c14`
- `0x18003d8c0`

## callees

- `0x180005e40`
- `0x180010b3c`
- `0x180012078`
- `0x180012af4`
- `0x180066c10`
- `0x180067ebc`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012260`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012260`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001226a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001226a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001224a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001224a`
- `RPCRT4!UuidCreate` at `0x1800120cb`
- `RPCRT4!UuidCreate` at `0x1800120cb`

## string_xrefs

- `0x18001211a`: `InventoryCache::SetMetadata failed [%#x]`
- `0x180012179`: `InventoryCache::GetItemCount failed [%#x]`
- `0x1800121ae`: `New syncId generated for a non-empty cache so forcing a full sync`
- `0x1800121ea`: `InventoryCache::BatchBegin failed [%#x]`
- `0x18001218a`: `TelCacheProvider::NewSyncId`
- `0x1800121bb`: `TelCacheProvider::NewSyncId`
- `0x18001220e`: `TelCacheProvider::NewSyncId`

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
0x180012078  push    rbx
0x18001207a  push    rsi
0x18001207b  push    rdi
0x18001207c  push    r14
0x18001207e  sub     rsp, 58h
0x180012082  mov     rax, cs:__security_cookie
0x180012089  xor     rax, rsp
0x18001208c  mov     [rsp+78h+var_30], rax
0x180012091  lea     rbx, [rcx+68h]
0x180012095  mov     rdi, rcx
0x180012098  mov     rcx, rbx; this
0x18001209b  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x1800120a0  cmp     qword ptr [rdi], 0
0x1800120a4  jz      loc_1800121F9
0x1800120aa  cmp     qword ptr [rdi+58h], 0
0x1800120af  jz      loc_1800121F9
0x1800120b5  xorps   xmm0, xmm0
0x1800120b8  lea     rsi, [rdi+8]
0x1800120bc  xor     eax, eax
0x1800120be  lea     rcx, [rsp+78h+Uuid]; Uuid
0x1800120c3  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x1800120c8  mov     [rsi], ax
0x1800120cb  call    cs:__imp_UuidCreate
0x1800120d1  lea     r8, [rsp+78h+Uuid]
0x1800120d6  mov     rcx, rsi
0x1800120d9  call    AslGuidToString
0x1800120de  test    eax, eax
0x1800120e0  jz      short loc_1800120F8
0x1800120e2  mov     [rsp+78h+var_58], eax
0x1800120e6  lea     r9, aAslguidtostrin; "AslGuidToString failed [%d]"
0x1800120ed  mov     r8d, 6C6h
0x1800120f3  jmp     loc_18001220E
0x1800120f8  mov     rcx, [rdi+58h]
0x1800120fc  lea     rdx, aProvidersyncid; "ProviderSyncId"
0x180012103  mov     r8, rsi
0x180012106  mov     rax, [rcx]
0x180012109  mov     rax, [rax+50h]
0x18001210d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012112  test    eax, eax
0x180012114  jns     short loc_18001212C
0x180012116  mov     [rsp+78h+var_58], eax
0x18001211a  lea     r9, aInventorycache_7; "InventoryCache::SetMetadata failed [%#x"...
0x180012121  mov     r8d, 6CEh
0x180012127  jmp     loc_18001220E
0x18001212c  mov     rcx, [rdi+58h]
0x180012130  mov     r14, [rdi]
0x180012133  mov     rax, [rcx]
0x180012136  mov     rax, [rax+88h]
0x18001213d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012142  test    eax, eax
0x180012144  jnz     short loc_180012158
0x180012146  mov     rax, [r14]
0x180012149  mov     rdx, rsi
0x18001214c  mov     rcx, r14
0x18001214f  mov     rax, [rax+58h]
0x180012153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012158  mov     rcx, [rdi+58h]
0x18001215c  lea     rdx, [rsp+78h+var_48]
0x180012161  mov     [rsp+78h+var_48], 0
0x180012169  mov     rax, [rcx]
0x18001216c  mov     rax, [rax+20h]
0x180012170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012175  test    eax, eax
0x180012177  jns     short loc_1800121A7
0x180012179  lea     r9, aInventorycache_4; "InventoryCache::GetItemCount failed [%#"...
0x180012180  mov     [rsp+78h+var_58], eax
0x180012184  mov     r8d, 6DDh
0x18001218a  lea     rdx, aTelcacheprovid_13; "TelCacheProvider::NewSyncId"
0x180012191  mov     ecx, 1
0x180012196  call    AslLogCallPrintf
0x18001219b  xor     edx, edx; unsigned __int16 *
0x18001219d  mov     rcx, rdi; this
0x1800121a0  call    ?ShouldForceFullSync@TelCacheProvider@@AEAAHPEBG@Z; TelCacheProvider::ShouldForceFullSync(ushort const *)
0x1800121a5  jmp     short loc_18001221F
0x1800121a7  cmp     [rsp+78h+var_48], 0
0x1800121ac  jbe     short loc_18001219B
0x1800121ae  lea     r9, aNewSyncidGener; "New syncId generated for a non-empty ca"...
0x1800121b5  mov     r8d, 6E7h
0x1800121bb  lea     rdx, aTelcacheprovid_13; "TelCacheProvider::NewSyncId"
0x1800121c2  mov     ecx, 3
0x1800121c7  call    AslLogCallPrintf
0x1800121cc  mov     rcx, [rdi+58h]
0x1800121d0  mov     dl, 1
0x1800121d2  mov     byte ptr [rdi+61h], 1
0x1800121d6  mov     rax, [rcx]
0x1800121d9  mov     rax, [rax+68h]
0x1800121dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121e2  test    eax, eax
0x1800121e4  jns     short loc_18001219B
0x1800121e6  mov     [rsp+78h+var_58], eax
0x1800121ea  lea     r9, aInventorycache_12; "InventoryCache::BatchBegin failed [%#x]"
0x1800121f1  mov     r8d, 6EDh
0x1800121f7  jmp     short loc_18001220E
0x1800121f9  mov     [rsp+78h+var_58], 80070057h
0x180012201  lea     r9, aObjectNotYetIn; "Object not yet initialized. [%#x]"
0x180012208  mov     r8d, 6B7h
0x18001220e  lea     rdx, aTelcacheprovid_13; "TelCacheProvider::NewSyncId"
0x180012215  mov     ecx, 1
0x18001221a  call    AslLogCallPrintf
0x18001221f  cmp     byte ptr [rbx+24h], 0
0x180012223  jz      short loc_180012242
0x180012225  mov     rax, [rbx+18h]
0x180012229  xor     cl, cl
0x18001222b  cmp     dword ptr [rax+4], 1
0x18001222f  jnz     short loc_180012236
0x180012231  mov     [rbx+24h], cl
0x180012234  mov     cl, 1
0x180012236  or      edi, 0FFFFFFFFh
0x180012239  add     [rax+4], edi
0x18001223c  test    cl, cl
0x18001223e  jz      short loc_180012270
0x180012240  jmp     short loc_180012266
0x180012242  mov     rcx, [rbx]; hHandle
0x180012245  or      edi, 0FFFFFFFFh
0x180012248  mov     edx, edi; dwMilliseconds
0x18001224a  call    cs:__imp_WaitForSingleObject
0x180012250  test    eax, eax
0x180012252  jnz     short loc_180012270
0x180012254  mov     rax, [rbx+18h]
0x180012258  add     [rax], edi
0x18001225a  add     [rbx+20h], edi
0x18001225d  mov     rcx, [rbx]; hMutex
0x180012260  call    cs:__imp_ReleaseMutex
0x180012266  mov     rcx, [rbx+10h]; hEvent
0x18001226a  call    cs:__imp_SetEvent
0x180012270  mov     rcx, [rsp+78h+var_30]
0x180012275  xor     rcx, rsp; StackCookie
0x180012278  call    __security_check_cookie
0x18001227d  add     rsp, 58h
0x180012281  pop     r14
0x180012283  pop     rdi
0x180012284  pop     rsi
0x180012285  pop     rbx
0x180012286  retn
```
