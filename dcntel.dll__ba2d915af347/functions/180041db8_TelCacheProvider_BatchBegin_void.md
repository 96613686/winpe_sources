# TelCacheProvider::BatchBegin(void)

- ea: `0x180041db8`
- end: `0x180041fc5`
- name: `?BatchBegin@TelCacheProvider@@QEAAJXZ`
- size: `525`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800b5df0`
- `0x1800d4c30`

## callees

- `0x1800413d4`
- `0x180041db8`
- `0x18004b2ec`
- `0x18004b3e8`
- `0x18016796c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180041faf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180041faf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041f8f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041f8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180041fa5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180041fa5`

## string_xrefs

- `0x180041e04`: `TelCacheProvider::BatchBegin`
- `0x180041df3`: `BatchBegin called but batch already in progress [%#x]`
- `0x180041e80`: `InventoryCache::GetMetadata [%#x]`
- `0x180041e91`: `TelCacheProvider::GetVersion`
- `0x180041eef`: `InventoryCache::SetMetadata failed [%#x]`
- `0x180041f4c`: `InventoryCache::BatchBegin failed [%#x]`

## pseudocode

```c
__int64 __fastcall TelCacheProvider::BatchBegin(TelCacheProvider *this)
{
  char *v3; // rdi
  unsigned int v4; // ebp
  __int64 v5; // rcx
  int v6; // eax
  int v7; // r14d
  TelCacheProvider *v8; // rcx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rax
  char v13; // cl
  __int64 v14; // [rsp+20h] [rbp-48h]
  unsigned int v15; // [rsp+70h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 11) )
    return 2147500034LL;
  v3 = (char *)this + 104;
  Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((TelCacheProvider *)((char *)this + 104));
  if ( *((_BYTE *)this + 96) )
  {
    v4 = -2147418113;
    AslLogCallPrintf(
      1,
      "TelCacheProvider::BatchBegin",
      1074,
      "BatchBegin called but batch already in progress [%#x]",
      -2147418113);
  }
  else
  {
    if ( *((_BYTE *)this + 97)
      && *(_QWORD *)this
      && (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)this + 56LL))(*(_QWORD *)this) )
    {
      v5 = *((_QWORD *)this + 11);
      v15 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *))(*(_QWORD *)v5 + 72LL))(
             v5,
             L"ProviderVersion",
             &v15);
      v7 = v6;
      if ( v6 == -2147024894 )
      {
        v15 = 0;
        v7 = 1;
      }
      else if ( v6 >= 0 )
      {
        v7 = 0;
      }
      else
      {
        AslLogCallPrintf(1, "TelCacheProvider::GetVersion", 1801, "InventoryCache::GetMetadata [%#x]", v6);
      }
      v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 120LL))(*((_QWORD *)this + 11));
      if ( *((_WORD *)this + 4) )
      {
        TelCacheProvider::ShouldForceFullSync(this, 0);
        v9 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, char *))(**((_QWORD **)this + 11) + 80LL))(
               *((_QWORD *)this + 11),
               L"ProviderSyncId",
               (char *)this + 8);
        v4 = v9;
        if ( v9 < 0 )
        {
          LODWORD(v14) = v9;
          AslLogCallPrintf(1, "TelCacheProvider::BatchBegin", 1101, "InventoryCache::SetMetadata failed [%#x]", v14);
          goto LABEL_23;
        }
      }
      if ( !v7 )
      {
        v10 = TelCacheProvider::SetVersion(v8, *((struct Windows::Compat::Inventory::InventoryCache **)this + 11), v15);
        v4 = v10;
        if ( v10 < 0 )
        {
          LODWORD(v14) = v10;
          AslLogCallPrintf(1, "TelCacheProvider::BatchBegin", 1111, "SetVersion failed [%#x]", v14);
          goto LABEL_23;
        }
      }
    }
    else
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 11) + 104LL))(*((_QWORD *)this + 11), 0);
      v4 = v11;
      if ( v11 < 0 )
      {
        AslLogCallPrintf(1, "TelCacheProvider::BatchBegin", 1121, "InventoryCache::BatchBegin failed [%#x]", v11);
        goto LABEL_23;
      }
    }
    *((_BYTE *)this + 96) = 1;
  }
LABEL_23:
  if ( v3[36] )
  {
    v12 = *((_QWORD *)v3 + 3);
    v13 = 0;
    if ( *(_DWORD *)(v12 + 4) == 1 )
    {
      v3[36] = 0;
      v13 = 1;
    }
    --*(_DWORD *)(v12 + 4);
    if ( !v13 )
      return v4;
    goto LABEL_30;
  }
  if ( !WaitForSingleObject(*(HANDLE *)v3, 0xFFFFFFFF) )
  {
    --**((_DWORD **)v3 + 3);
    --*((_DWORD *)v3 + 8);
    ReleaseMutex(*(HANDLE *)v3);
LABEL_30:
    SetEvent(*((HANDLE *)v3 + 2));
  }
  return v4;
}

```

## disassembly

```asm
0x180041db8  push    rbx
0x180041dba  push    rbp
0x180041dbb  push    rdi
0x180041dbc  push    r12
0x180041dbe  push    r14
0x180041dc0  push    r15
0x180041dc2  sub     rsp, 38h
0x180041dc6  xor     r12d, r12d
0x180041dc9  mov     rbx, rcx
0x180041dcc  cmp     [rcx+58h], r12
0x180041dd0  jnz     short loc_180041DDC
0x180041dd2  mov     eax, 80004002h
0x180041dd7  jmp     loc_180041FB7
0x180041ddc  lea     rdi, [rcx+68h]
0x180041de0  mov     rcx, rdi; this
0x180041de3  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x180041de8  cmp     [rbx+60h], r12b
0x180041dec  jz      short loc_180041E1A
0x180041dee  mov     ebp, 8000FFFFh
0x180041df3  lea     r9, aBatchbeginCall; "BatchBegin called but batch already in "...
0x180041dfa  mov     dword ptr [rsp+68h+var_48], ebp
0x180041dfe  mov     r8d, 432h
0x180041e04  lea     rdx, aTelcacheprovid_0; "TelCacheProvider::BatchBegin"
0x180041e0b  mov     ecx, 1
0x180041e10  call    AslLogCallPrintf
0x180041e15  jmp     loc_180041F62
0x180041e1a  cmp     [rbx+61h], r12b
0x180041e1e  jz      loc_180041F30
0x180041e24  mov     rcx, [rbx]
0x180041e27  test    rcx, rcx
0x180041e2a  jz      loc_180041F30
0x180041e30  mov     rax, [rcx]
0x180041e33  mov     rax, [rax+38h]
0x180041e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e3c  test    al, al
0x180041e3e  jz      loc_180041F30
0x180041e44  mov     rcx, [rbx+58h]
0x180041e48  lea     r8, [rsp+68h+arg_0]
0x180041e4d  mov     [rsp+68h+arg_0], r12d
0x180041e52  lea     rdx, aProviderversio; "ProviderVersion"
0x180041e59  mov     rax, [rcx]
0x180041e5c  mov     rax, [rax+48h]
0x180041e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e65  mov     r14d, eax
0x180041e68  cmp     eax, 80070002h
0x180041e6d  jnz     short loc_180041E7C
0x180041e6f  mov     [rsp+68h+arg_0], r12d
0x180041e74  mov     r14d, 1
0x180041e7a  jmp     short loc_180041EA7
0x180041e7c  test    eax, eax
0x180041e7e  jns     short loc_180041EA4
0x180041e80  lea     r9, aInventorycache_0; "InventoryCache::GetMetadata [%#x]"
0x180041e87  mov     dword ptr [rsp+68h+var_48], eax
0x180041e8b  mov     r8d, 709h
0x180041e91  lea     rdx, aTelcacheprovid_18; "TelCacheProvider::GetVersion"
0x180041e98  mov     ecx, 1
0x180041e9d  call    AslLogCallPrintf
0x180041ea2  jmp     short loc_180041EA7
0x180041ea4  mov     r14d, r12d
0x180041ea7  mov     rcx, [rbx+58h]
0x180041eab  mov     rax, [rcx]
0x180041eae  mov     rax, [rax+78h]
0x180041eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041eb7  mov     ebp, eax
0x180041eb9  cmp     [rbx+8], r12w
0x180041ebe  jz      short loc_180041F01
0x180041ec0  xor     edx, edx; unsigned __int16 *
0x180041ec2  mov     rcx, rbx; this
0x180041ec5  call    ?ShouldForceFullSync@TelCacheProvider@@AEAAHPEBG@Z; TelCacheProvider::ShouldForceFullSync(ushort const *)
0x180041eca  mov     rcx, [rbx+58h]
0x180041ece  lea     r8, [rbx+8]
0x180041ed2  lea     rdx, aProvidersyncid; "ProviderSyncId"
0x180041ed9  mov     rax, [rcx]
0x180041edc  mov     rax, [rax+50h]
0x180041ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ee5  mov     ebp, eax
0x180041ee7  test    eax, eax
0x180041ee9  jns     short loc_180041F01
0x180041eeb  mov     dword ptr [rsp+68h+var_48], eax
0x180041eef  lea     r9, aInventorycache_4; "InventoryCache::SetMetadata failed [%#x"...
0x180041ef6  mov     r8d, 44Dh
0x180041efc  jmp     loc_180041E04
0x180041f01  test    r14d, r14d
0x180041f04  jnz     short loc_180041F5E
0x180041f06  mov     r8d, [rsp+68h+arg_0]; unsigned int
0x180041f0b  mov     rdx, [rbx+58h]; struct Windows::Compat::Inventory::InventoryCache *
0x180041f0f  call    ?SetVersion@TelCacheProvider@@AEAAJPEAVInventoryCache@Inventory@Compat@Windows@@K@Z; TelCacheProvider::SetVersion(Windows::Compat::Inventory::InventoryCache *,ulong)
0x180041f14  mov     ebp, eax
0x180041f16  test    eax, eax
0x180041f18  jns     short loc_180041F5E
0x180041f1a  mov     dword ptr [rsp+68h+var_48], eax
0x180041f1e  lea     r9, aSetversionFail; "SetVersion failed [%#x]"
0x180041f25  mov     r8d, 457h
0x180041f2b  jmp     loc_180041E04
0x180041f30  mov     rcx, [rbx+58h]
0x180041f34  xor     edx, edx
0x180041f36  mov     rax, [rcx]
0x180041f39  mov     rax, [rax+68h]
0x180041f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f42  mov     ebp, eax
0x180041f44  test    eax, eax
0x180041f46  jns     short loc_180041F5E
0x180041f48  mov     dword ptr [rsp+68h+var_48], eax
0x180041f4c  lea     r9, aInventorycache_8; "InventoryCache::BatchBegin failed [%#x]"
0x180041f53  mov     r8d, 461h
0x180041f59  jmp     loc_180041E04
0x180041f5e  mov     byte ptr [rbx+60h], 1
0x180041f62  cmp     [rdi+24h], r12b
0x180041f66  jz      short loc_180041F87
0x180041f68  mov     rax, [rdi+18h]
0x180041f6c  mov     cl, r12b
0x180041f6f  cmp     dword ptr [rax+4], 1
0x180041f73  jnz     short loc_180041F7B
0x180041f75  mov     [rdi+24h], r12b
0x180041f79  mov     cl, 1
0x180041f7b  or      ebx, 0FFFFFFFFh
0x180041f7e  add     [rax+4], ebx
0x180041f81  test    cl, cl
0x180041f83  jz      short loc_180041FB5
0x180041f85  jmp     short loc_180041FAB
0x180041f87  mov     rcx, [rdi]; hHandle
0x180041f8a  or      ebx, 0FFFFFFFFh
0x180041f8d  mov     edx, ebx; dwMilliseconds
0x180041f8f  call    cs:__imp_WaitForSingleObject
0x180041f95  test    eax, eax
0x180041f97  jnz     short loc_180041FB5
0x180041f99  mov     rax, [rdi+18h]
0x180041f9d  add     [rax], ebx
0x180041f9f  add     [rdi+20h], ebx
0x180041fa2  mov     rcx, [rdi]; hMutex
0x180041fa5  call    cs:__imp_ReleaseMutex
0x180041fab  mov     rcx, [rdi+10h]; hEvent
0x180041faf  call    cs:__imp_SetEvent
0x180041fb5  mov     eax, ebp
0x180041fb7  add     rsp, 38h
0x180041fbb  pop     r15
0x180041fbd  pop     r14
0x180041fbf  pop     r12
0x180041fc1  pop     rdi
0x180041fc2  pop     rbp
0x180041fc3  pop     rbx
0x180041fc4  retn
```
