# TelCacheProvider::BatchBegin(void)

- ea: `0x180032a00`
- end: `0x180032c0d`
- name: `?BatchBegin@TelCacheProvider@@QEAAJXZ`
- size: `525`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180034d4c`
- `0x180044f20`

## callees

- `0x180010b3c`
- `0x180012af4`
- `0x180030d6c`
- `0x180032a00`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180032bed`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180032bed`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180032bf7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180032bf7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032bd7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032bd7`

## string_xrefs

- `0x180032b37`: `InventoryCache::SetMetadata failed [%#x]`
- `0x180032b94`: `InventoryCache::BatchBegin failed [%#x]`
- `0x180032ac8`: `InventoryCache::GetMetadata [%#x]`
- `0x180032ad9`: `TelCacheProvider::GetVersion`
- `0x180032a3b`: `BatchBegin called but batch already in progress [%#x]`
- `0x180032a4c`: `TelCacheProvider::BatchBegin`

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
0x180032a00  push    rbx
0x180032a02  push    rbp
0x180032a03  push    rdi
0x180032a04  push    r12
0x180032a06  push    r14
0x180032a08  push    r15
0x180032a0a  sub     rsp, 38h
0x180032a0e  xor     r12d, r12d
0x180032a11  mov     rbx, rcx
0x180032a14  cmp     [rcx+58h], r12
0x180032a18  jnz     short loc_180032A24
0x180032a1a  mov     eax, 80004002h
0x180032a1f  jmp     loc_180032BFF
0x180032a24  lea     rdi, [rcx+68h]
0x180032a28  mov     rcx, rdi; this
0x180032a2b  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x180032a30  cmp     [rbx+60h], r12b
0x180032a34  jz      short loc_180032A62
0x180032a36  mov     ebp, 8000FFFFh
0x180032a3b  lea     r9, aBatchbeginCall; "BatchBegin called but batch already in "...
0x180032a42  mov     dword ptr [rsp+68h+var_48], ebp
0x180032a46  mov     r8d, 432h
0x180032a4c  lea     rdx, aTelcacheprovid_0; "TelCacheProvider::BatchBegin"
0x180032a53  mov     ecx, 1
0x180032a58  call    AslLogCallPrintf
0x180032a5d  jmp     loc_180032BAA
0x180032a62  cmp     [rbx+61h], r12b
0x180032a66  jz      loc_180032B78
0x180032a6c  mov     rcx, [rbx]
0x180032a6f  test    rcx, rcx
0x180032a72  jz      loc_180032B78
0x180032a78  mov     rax, [rcx]
0x180032a7b  mov     rax, [rax+38h]
0x180032a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a84  test    al, al
0x180032a86  jz      loc_180032B78
0x180032a8c  mov     rcx, [rbx+58h]
0x180032a90  lea     r8, [rsp+68h+arg_0]
0x180032a95  mov     [rsp+68h+arg_0], r12d
0x180032a9a  lea     rdx, aProviderversio; "ProviderVersion"
0x180032aa1  mov     rax, [rcx]
0x180032aa4  mov     rax, [rax+48h]
0x180032aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032aad  mov     r14d, eax
0x180032ab0  cmp     eax, 80070002h
0x180032ab5  jnz     short loc_180032AC4
0x180032ab7  mov     [rsp+68h+arg_0], r12d
0x180032abc  mov     r14d, 1
0x180032ac2  jmp     short loc_180032AEF
0x180032ac4  test    eax, eax
0x180032ac6  jns     short loc_180032AEC
0x180032ac8  lea     r9, aInventorycache_0; "InventoryCache::GetMetadata [%#x]"
0x180032acf  mov     dword ptr [rsp+68h+var_48], eax
0x180032ad3  mov     r8d, 709h
0x180032ad9  lea     rdx, aTelcacheprovid_32; "TelCacheProvider::GetVersion"
0x180032ae0  mov     ecx, 1
0x180032ae5  call    AslLogCallPrintf
0x180032aea  jmp     short loc_180032AEF
0x180032aec  mov     r14d, r12d
0x180032aef  mov     rcx, [rbx+58h]
0x180032af3  mov     rax, [rcx]
0x180032af6  mov     rax, [rax+78h]
0x180032afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032aff  mov     ebp, eax
0x180032b01  cmp     [rbx+8], r12w
0x180032b06  jz      short loc_180032B49
0x180032b08  xor     edx, edx; unsigned __int16 *
0x180032b0a  mov     rcx, rbx; this
0x180032b0d  call    ?ShouldForceFullSync@TelCacheProvider@@AEAAHPEBG@Z; TelCacheProvider::ShouldForceFullSync(ushort const *)
0x180032b12  mov     rcx, [rbx+58h]
0x180032b16  lea     r8, [rbx+8]
0x180032b1a  lea     rdx, aProvidersyncid; "ProviderSyncId"
0x180032b21  mov     rax, [rcx]
0x180032b24  mov     rax, [rax+50h]
0x180032b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b2d  mov     ebp, eax
0x180032b2f  test    eax, eax
0x180032b31  jns     short loc_180032B49
0x180032b33  mov     dword ptr [rsp+68h+var_48], eax
0x180032b37  lea     r9, aInventorycache_7; "InventoryCache::SetMetadata failed [%#x"...
0x180032b3e  mov     r8d, 44Dh
0x180032b44  jmp     loc_180032A4C
0x180032b49  test    r14d, r14d
0x180032b4c  jnz     short loc_180032BA6
0x180032b4e  mov     r8d, [rsp+68h+arg_0]; unsigned int
0x180032b53  mov     rdx, [rbx+58h]; struct Windows::Compat::Inventory::InventoryCache *
0x180032b57  call    ?SetVersion@TelCacheProvider@@AEAAJPEAVInventoryCache@Inventory@Compat@Windows@@K@Z; TelCacheProvider::SetVersion(Windows::Compat::Inventory::InventoryCache *,ulong)
0x180032b5c  mov     ebp, eax
0x180032b5e  test    eax, eax
0x180032b60  jns     short loc_180032BA6
0x180032b62  mov     dword ptr [rsp+68h+var_48], eax
0x180032b66  lea     r9, aSetversionFail; "SetVersion failed [%#x]"
0x180032b6d  mov     r8d, 457h
0x180032b73  jmp     loc_180032A4C
0x180032b78  mov     rcx, [rbx+58h]
0x180032b7c  xor     edx, edx
0x180032b7e  mov     rax, [rcx]
0x180032b81  mov     rax, [rax+68h]
0x180032b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b8a  mov     ebp, eax
0x180032b8c  test    eax, eax
0x180032b8e  jns     short loc_180032BA6
0x180032b90  mov     dword ptr [rsp+68h+var_48], eax
0x180032b94  lea     r9, aInventorycache_12; "InventoryCache::BatchBegin failed [%#x]"
0x180032b9b  mov     r8d, 461h
0x180032ba1  jmp     loc_180032A4C
0x180032ba6  mov     byte ptr [rbx+60h], 1
0x180032baa  cmp     [rdi+24h], r12b
0x180032bae  jz      short loc_180032BCF
0x180032bb0  mov     rax, [rdi+18h]
0x180032bb4  mov     cl, r12b
0x180032bb7  cmp     dword ptr [rax+4], 1
0x180032bbb  jnz     short loc_180032BC3
0x180032bbd  mov     [rdi+24h], r12b
0x180032bc1  mov     cl, 1
0x180032bc3  or      ebx, 0FFFFFFFFh
0x180032bc6  add     [rax+4], ebx
0x180032bc9  test    cl, cl
0x180032bcb  jz      short loc_180032BFD
0x180032bcd  jmp     short loc_180032BF3
0x180032bcf  mov     rcx, [rdi]; hHandle
0x180032bd2  or      ebx, 0FFFFFFFFh
0x180032bd5  mov     edx, ebx; dwMilliseconds
0x180032bd7  call    cs:__imp_WaitForSingleObject
0x180032bdd  test    eax, eax
0x180032bdf  jnz     short loc_180032BFD
0x180032be1  mov     rax, [rdi+18h]
0x180032be5  add     [rax], ebx
0x180032be7  add     [rdi+20h], ebx
0x180032bea  mov     rcx, [rdi]; hMutex
0x180032bed  call    cs:__imp_ReleaseMutex
0x180032bf3  mov     rcx, [rdi+10h]; hEvent
0x180032bf7  call    cs:__imp_SetEvent
0x180032bfd  mov     eax, ebp
0x180032bff  add     rsp, 38h
0x180032c03  pop     r15
0x180032c05  pop     r14
0x180032c07  pop     r12
0x180032c09  pop     rdi
0x180032c0a  pop     rbp
0x180032c0b  pop     rbx
0x180032c0c  retn
```
