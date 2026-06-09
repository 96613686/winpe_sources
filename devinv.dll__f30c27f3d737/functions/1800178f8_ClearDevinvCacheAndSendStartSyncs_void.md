# ClearDevinvCacheAndSendStartSyncs(void)

- ea: `0x1800178f8`
- end: `0x180017ad3`
- name: `?ClearDevinvCacheAndSendStartSyncs@@YAJXZ`
- size: `475`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002a500`

## callees

- `0x180006d02`
- `0x180007014`
- `0x18000eb24`
- `0x180010b3c`
- `0x1800178f8`
- `0x18006041c`
- `0x180066c10`
- `0x18010d8dc`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800179da`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800179da`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800179e4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800179e4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800179c2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800179c2`

## string_xrefs

- `0x180017a23`: `TelCacheProvider::ClearData %ls FAILED %#x`
- `0x180017a40`: `ClearDevinvCacheAndSendStartSyncs`
- `0x180017a64`: `ClearDevinvCacheAndSendStartSyncs`

## pseudocode

```c
__int64 ClearDevinvCacheAndSendStartSyncs(void)
{
  __int64 v0; // rbp
  __int64 v1; // rsi
  HANDLE *v2; // rbx
  int v3; // edi
  __int64 v4; // rax
  char v5; // cl
  FILE *v7; // rax
  const wchar_t *v8; // rbx
  FILE *v9; // rax
  FILE *v10; // rax

  v0 = 0;
  if ( !off_180155028 )
    return 0;
  while ( 1 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl)
      && !wcscmp_0((const wchar_t *)*(&g_Stores + 3 * v0), L"DriverPackageExtended") )
    {
      goto LABEL_16;
    }
    v1 = (__int64)*(&g_Stores + 3 * v0 + 1);
    if ( !*(_QWORD *)(v1 + 88) )
      break;
    v2 = (HANDLE *)(v1 + 104);
    Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((Windows::Compat::Inventory::InventorySynchronization *)(v1 + 104));
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v1 + 88) + 120LL))(*(_QWORD *)(v1 + 88));
    if ( v3 >= 0 )
    {
      *(_WORD *)(v1 + 8) = 0;
      *(_WORD *)(v1 + 96) = 0;
    }
    if ( !*(_BYTE *)(v1 + 140) )
    {
      if ( WaitForSingleObject(*v2, 0xFFFFFFFF) )
        goto LABEL_15;
      --**(_DWORD **)(v1 + 128);
      --*(_DWORD *)(v1 + 136);
      ReleaseMutex(*v2);
LABEL_14:
      SetEvent(*(HANDLE *)(v1 + 120));
      goto LABEL_15;
    }
    v4 = *(_QWORD *)(v1 + 128);
    v5 = 0;
    if ( *(_DWORD *)(v4 + 4) == 1 )
    {
      *(_BYTE *)(v1 + 140) = 0;
      v5 = 1;
    }
    --*(_DWORD *)(v4 + 4);
    if ( v5 )
      goto LABEL_14;
LABEL_15:
    if ( v3 < 0 )
      goto LABEL_20;
LABEL_16:
    v0 = (unsigned int)(v0 + 1);
    if ( !*(&g_Stores + 3 * v0 + 1) )
      return 0;
  }
  v3 = -2147467262;
LABEL_20:
  AslLogCallPrintf(
    2,
    "ClearDevinvCacheAndSendStartSyncs",
    266,
    "TelCacheProvider::ClearData %ls FAILED %#x",
    (const wchar_t *)*(&g_Stores + 3 * v0),
    v3);
  if ( EnableDevInvStdErrLog )
  {
    v7 = o___acrt_iob_func_0(2u);
    fprintf(v7, "Error: %s, %u: ", "ClearDevinvCacheAndSendStartSyncs", 266);
    v8 = (const wchar_t *)*(&g_Stores + 3 * v0);
    v9 = o___acrt_iob_func_0(2u);
    fprintf(v9, "TelCacheProvider::ClearData %ls FAILED %#x", v8, v3);
    v10 = o___acrt_iob_func_0(2u);
    fprintf(v10, "\n");
  }
  if ( g_DeviceMapLogFunction )
    TraceMessageCallback(
      0x2000000,
      "TelCacheProvider::ClearData %ls FAILED %#x",
      (const wchar_t *)*(&g_Stores + 3 * v0),
      v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800178f8  push    rbx
0x1800178fa  push    rbp
0x1800178fb  push    rsi
0x1800178fc  push    rdi
0x1800178fd  push    r12
0x1800178ff  push    r13
0x180017901  push    r14
0x180017903  sub     rsp, 30h
0x180017907  xor     ebp, ebp
0x180017909  cmp     cs:off_180155028, rbp
0x180017910  jz      loc_180017A07
0x180017916  lea     r12, ?g_Stores@@3PAU_DEVINV_TELCACHE_STORE@@A; _DEVINV_TELCACHE_STORE near * g_Stores
0x18001791d  or      r13d, 0FFFFFFFFh
0x180017921  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x180017928  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18001792d  test    al, al
0x18001792f  jz      short loc_180017954
0x180017931  lea     rcx, ds:0[rbp*2]
0x180017939  add     rcx, rbp
0x18001793c  lea     rdx, aDriverpackagee; "DriverPackageExtended"
0x180017943  mov     rcx, [r12+rcx*8]; String1
0x180017947  call    wcscmp_0
0x18001794c  test    eax, eax
0x18001794e  jz      loc_1800179EE
0x180017954  lea     r14, ds:0[rbp*2]
0x18001795c  add     r14, rbp
0x18001795f  mov     rsi, [r12+r14*8+8]
0x180017964  cmp     qword ptr [rsi+58h], 0
0x180017969  jz      loc_180017A1A
0x18001796f  lea     rbx, [rsi+68h]
0x180017973  mov     rcx, rbx; this
0x180017976  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x18001797b  mov     rcx, [rsi+58h]
0x18001797f  mov     rax, [rcx]
0x180017982  mov     rax, [rax+78h]
0x180017986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001798b  mov     edi, eax
0x18001798d  test    eax, eax
0x18001798f  js      short loc_18001799B
0x180017991  xor     eax, eax
0x180017993  mov     [rsi+8], ax
0x180017997  mov     [rsi+60h], ax
0x18001799b  cmp     byte ptr [rbx+24h], 0
0x18001799f  jz      short loc_1800179BC
0x1800179a1  mov     rax, [rbx+18h]
0x1800179a5  xor     cl, cl
0x1800179a7  cmp     dword ptr [rax+4], 1
0x1800179ab  jnz     short loc_1800179B2
0x1800179ad  mov     [rbx+24h], cl
0x1800179b0  mov     cl, 1
0x1800179b2  add     [rax+4], r13d
0x1800179b6  test    cl, cl
0x1800179b8  jz      short loc_1800179EA
0x1800179ba  jmp     short loc_1800179E0
0x1800179bc  mov     rcx, [rbx]; hHandle
0x1800179bf  mov     edx, r13d; dwMilliseconds
0x1800179c2  call    cs:__imp_WaitForSingleObject
0x1800179c8  test    eax, eax
0x1800179ca  jnz     short loc_1800179EA
0x1800179cc  mov     rax, [rbx+18h]
0x1800179d0  add     [rax], r13d
0x1800179d3  add     [rbx+20h], r13d
0x1800179d7  mov     rcx, [rbx]; hMutex
0x1800179da  call    cs:__imp_ReleaseMutex
0x1800179e0  mov     rcx, [rbx+10h]; hEvent
0x1800179e4  call    cs:__imp_SetEvent
0x1800179ea  test    edi, edi
0x1800179ec  js      short loc_180017A1F
0x1800179ee  inc     ebp
0x1800179f0  lea     rcx, ds:0[rbp*2]
0x1800179f8  add     rcx, rbp
0x1800179fb  cmp     qword ptr [r12+rcx*8+8], 0
0x180017a01  jnz     loc_180017921
0x180017a07  xor     edi, edi
0x180017a09  mov     eax, edi
0x180017a0b  add     rsp, 30h
0x180017a0f  pop     r14
0x180017a11  pop     r13
0x180017a13  pop     r12
0x180017a15  pop     rdi
0x180017a16  pop     rsi
0x180017a17  pop     rbp
0x180017a18  pop     rbx
0x180017a19  retn
0x180017a1a  mov     edi, 80004002h
0x180017a1f  mov     rax, [r12+r14*8]
0x180017a23  lea     rsi, aTelcacheprovid_7; "TelCacheProvider::ClearData %ls FAILED "...
0x180017a2a  mov     ebx, 10Ah
0x180017a2f  mov     [rsp+68h+var_40], edi
0x180017a33  mov     ebp, 2
0x180017a38  mov     [rsp+68h+var_48], rax
0x180017a3d  mov     r9, rsi
0x180017a40  lea     rdx, aCleardevinvcac; "ClearDevinvCacheAndSendStartSyncs"
0x180017a47  mov     r8d, ebx
0x180017a4a  mov     ecx, ebp
0x180017a4c  call    AslLogCallPrintf
0x180017a51  cmp     cs:EnableDevInvStdErrLog, 0
0x180017a58  jz      short loc_180017AAC
0x180017a5a  mov     ecx, ebp; Ix
0x180017a5c  call    _o___acrt_iob_func_0
0x180017a61  mov     rcx, rax; Stream
0x180017a64  lea     r8, aCleardevinvcac; "ClearDevinvCacheAndSendStartSyncs"
0x180017a6b  mov     r9d, ebx
0x180017a6e  lea     rdx, Format; "Error: %s, %u: "
0x180017a75  call    fprintf
0x180017a7a  mov     rbx, [r12+r14*8]
0x180017a7e  mov     ecx, ebp; Ix
0x180017a80  call    _o___acrt_iob_func_0
0x180017a85  mov     r9d, edi
0x180017a88  mov     r8, rbx
0x180017a8b  mov     rdx, rsi; Format
0x180017a8e  mov     rcx, rax; Stream
0x180017a91  call    fprintf
0x180017a96  mov     ecx, ebp; Ix
0x180017a98  call    _o___acrt_iob_func_0
0x180017a9d  mov     rcx, rax; Stream
0x180017aa0  lea     rdx, asc_18011EAD8; "\n"
0x180017aa7  call    fprintf
0x180017aac  cmp     cs:g_DeviceMapLogFunction, 0
0x180017ab4  jz      loc_180017A09
0x180017aba  mov     r8, [r12+r14*8]
0x180017abe  mov     r9d, edi
0x180017ac1  mov     rdx, rsi
0x180017ac4  mov     ecx, 2000000h
0x180017ac9  call    TraceMessageCallback
0x180017ace  jmp     loc_180017A09
```
