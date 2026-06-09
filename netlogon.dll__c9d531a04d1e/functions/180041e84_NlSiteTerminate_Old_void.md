# NlSiteTerminate_Old(void)

- ea: `0x180041e84`
- end: `0x180041f92`
- name: `?NlSiteTerminate_Old@@YAXXZ`
- size: `270`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180028834`

## callees

- `0x180007278`
- `0x18000d710`
- `0x1800416f0`
- `0x180041b60`
- `0x180041e84`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041ef8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041ef8`
- `ntdll!RtlLeaveCriticalSection` at `0x180041f10`
- `ntdll!RtlLeaveCriticalSection` at `0x180041f10`
- `ntdll!RtlDeleteCriticalSection` at `0x180041f6f`
- `ntdll!RtlDeleteCriticalSection` at `0x180041f6f`
- `ntdll!RtlEnterCriticalSection` at `0x180041ead`
- `ntdll!RtlEnterCriticalSection` at `0x180041ead`

## string_xrefs

- `0x180041f2c`: `onecore\ds\netapi\svcdlls\logonsrv\server\nlsite.cxx`
- `0x180041f55`: `onecore\ds\netapi\svcdlls\logonsrv\server\nlsite.cxx`
- `0x180041f33`: `IsListEmpty( &NlGlobalSiteList )`
- `0x180041f5c`: `IsListEmpty( &NlGlobalSubnetList )`

## pseudocode

```c
void NlSiteTerminate_Old(void)
{
  char *v0; // r9

  if ( NlGlobalSiteInitialized )
  {
    NlPrintRoutine(0x8000000u, L"NlSiteTerminate: Entered\n");
    RtlEnterCriticalSection(&NlGlobalSiteCritSect);
    NlSiteDeleteSubnetTree((struct _NL_SUBNET_TREE_ENTRY *)&NlGlobalSubnetTree);
    NlSiteDeleteSubnetTree((struct _NL_SUBNET_TREE_ENTRY *)&NlGlobalNewSubnetTree);
    NlSiteDeleteSubnetTree((struct _NL_SUBNET_TREE_ENTRY *)&NlGlobalV6SubnetTree);
    NlSiteDeleteSubnetTree((struct _NL_SUBNET_TREE_ENTRY *)&NlGlobalV6NewSubnetTree);
    NlSetSiteName_Old(0, 0);
    if ( NlGlobalUnicodeNextClosestSiteName )
    {
      LocalFree(NlGlobalUnicodeNextClosestSiteName);
      NlGlobalUnicodeNextClosestSiteName = 0;
    }
    RtlLeaveCriticalSection(&NlGlobalSiteCritSect);
    if ( NlGlobalSiteList != (struct _NL_SITE_ENTRY *)&NlGlobalSiteList )
      NlAssertFailed(
        "IsListEmpty( &NlGlobalSiteList )",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\nlsite.cxx",
        4045,
        v0);
    if ( NlGlobalSubnetList != (struct _NL_SUBNET *)&NlGlobalSubnetList )
      NlAssertFailed(
        "IsListEmpty( &NlGlobalSubnetList )",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\nlsite.cxx",
        4046,
        v0);
    RtlDeleteCriticalSection(&NlGlobalSiteCritSect);
    NlGlobalSiteInitialized = 0;
    NlPrintRoutine(0x8000000u, L"NlSiteTerminate: Exitted\n");
  }
}

```

## disassembly

```asm
0x180041e84  sub     rsp, 28h
0x180041e88  cmp     cs:?NlGlobalSiteInitialized@@3EA, 0; uchar NlGlobalSiteInitialized
0x180041e8f  jz      loc_180041F8D
0x180041e95  lea     rdx, aNlsiteterminat; "NlSiteTerminate: Entered\n"
0x180041e9c  mov     ecx, 8000000h; unsigned int
0x180041ea1  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180041ea6  lea     rcx, ?NlGlobalSiteCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180041ead  call    cs:__imp_RtlEnterCriticalSection
0x180041eb3  lea     rcx, ?NlGlobalSubnetTree@@3U_NL_SUBNET_TREE_ENTRY@@A; struct _NL_SUBNET_TREE_ENTRY *
0x180041eba  call    ?NlSiteDeleteSubnetTree@@YAXPEAU_NL_SUBNET_TREE_ENTRY@@@Z; NlSiteDeleteSubnetTree(_NL_SUBNET_TREE_ENTRY *)
0x180041ebf  lea     rcx, ?NlGlobalNewSubnetTree@@3U_NL_SUBNET_TREE_ENTRY@@A; struct _NL_SUBNET_TREE_ENTRY *
0x180041ec6  call    ?NlSiteDeleteSubnetTree@@YAXPEAU_NL_SUBNET_TREE_ENTRY@@@Z; NlSiteDeleteSubnetTree(_NL_SUBNET_TREE_ENTRY *)
0x180041ecb  lea     rcx, ?NlGlobalV6SubnetTree@@3U_NL_SUBNET_TREE_ENTRY@@A; struct _NL_SUBNET_TREE_ENTRY *
0x180041ed2  call    ?NlSiteDeleteSubnetTree@@YAXPEAU_NL_SUBNET_TREE_ENTRY@@@Z; NlSiteDeleteSubnetTree(_NL_SUBNET_TREE_ENTRY *)
0x180041ed7  lea     rcx, ?NlGlobalV6NewSubnetTree@@3U_NL_SUBNET_TREE_ENTRY@@A; struct _NL_SUBNET_TREE_ENTRY *
0x180041ede  call    ?NlSiteDeleteSubnetTree@@YAXPEAU_NL_SUBNET_TREE_ENTRY@@@Z; NlSiteDeleteSubnetTree(_NL_SUBNET_TREE_ENTRY *)
0x180041ee3  xor     edx, edx; unsigned __int8 *
0x180041ee5  xor     ecx, ecx; Src
0x180041ee7  call    ?NlSetSiteName_Old@@YAKPEAGPEAE@Z; NlSetSiteName_Old(ushort *,uchar *)
0x180041eec  mov     rcx, cs:?NlGlobalUnicodeNextClosestSiteName@@3PEAGEA; hMem
0x180041ef3  test    rcx, rcx
0x180041ef6  jz      short loc_180041F09
0x180041ef8  call    cs:__imp_LocalFree
0x180041efe  mov     cs:?NlGlobalUnicodeNextClosestSiteName@@3PEAGEA, 0; ushort * NlGlobalUnicodeNextClosestSiteName
0x180041f09  lea     rcx, ?NlGlobalSiteCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180041f10  call    cs:__imp_RtlLeaveCriticalSection
0x180041f16  lea     rax, ?NlGlobalSiteList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalSiteList
0x180041f1d  cmp     cs:?NlGlobalSiteList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalSiteList
0x180041f24  jz      short loc_180041F3F
0x180041f26  mov     r8d, 0FCDh; unsigned int
0x180041f2c  lea     rdx, aOnecoreDsNetap_18; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180041f33  lea     rcx, aIslistemptyNlg_3; "IsListEmpty( &NlGlobalSiteList )"
0x180041f3a  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180041f3f  lea     rax, ?NlGlobalSubnetList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalSubnetList
0x180041f46  cmp     cs:?NlGlobalSubnetList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalSubnetList
0x180041f4d  jz      short loc_180041F68
0x180041f4f  mov     r8d, 0FCEh; unsigned int
0x180041f55  lea     rdx, aOnecoreDsNetap_18; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180041f5c  lea     rcx, aIslistemptyNlg; "IsListEmpty( &NlGlobalSubnetList )"
0x180041f63  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180041f68  lea     rcx, ?NlGlobalSiteCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180041f6f  call    cs:__imp_RtlDeleteCriticalSection
0x180041f75  lea     rdx, aNlsiteterminat_0; "NlSiteTerminate: Exitted\n"
0x180041f7c  mov     cs:?NlGlobalSiteInitialized@@3EA, 0; uchar NlGlobalSiteInitialized
0x180041f83  mov     ecx, 8000000h; unsigned int
0x180041f88  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180041f8d  add     rsp, 28h
0x180041f91  retn
```
