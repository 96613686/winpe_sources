# NlSiteTerminate_Old(void)

- ea: `0x180044b14`
- end: `0x180044c3b`
- name: `?NlSiteTerminate_Old@@YAXXZ`
- size: `295`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180029d5c`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x1800442dc`
- `0x180044798`
- `0x180044b14`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044b8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044b8e`
- `ntdll!RtlLeaveCriticalSection` at `0x180044bac`
- `ntdll!RtlLeaveCriticalSection` at `0x180044bac`
- `ntdll!RtlDeleteCriticalSection` at `0x180044c11`
- `ntdll!RtlDeleteCriticalSection` at `0x180044c11`
- `ntdll!RtlEnterCriticalSection` at `0x180044b3d`
- `ntdll!RtlEnterCriticalSection` at `0x180044b3d`

## string_xrefs

- `0x180044bce`: `onecore\ds\netapi\svcdlls\logonsrv\server\nlsite.cxx`
- `0x180044bf7`: `onecore\ds\netapi\svcdlls\logonsrv\server\nlsite.cxx`
- `0x180044bd5`: `IsListEmpty( &NlGlobalSiteList )`
- `0x180044bfe`: `IsListEmpty( &NlGlobalSubnetList )`

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
        0xFCDu,
        v0);
    if ( NlGlobalSubnetList != (struct _NL_SUBNET *)&NlGlobalSubnetList )
      NlAssertFailed(
        "IsListEmpty( &NlGlobalSubnetList )",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\nlsite.cxx",
        0xFCEu,
        v0);
    RtlDeleteCriticalSection(&NlGlobalSiteCritSect);
    NlGlobalSiteInitialized = 0;
    NlPrintRoutine(0x8000000u, L"NlSiteTerminate: Exitted\n");
  }
}

```

## disassembly

```asm
0x180044b14  sub     rsp, 28h
0x180044b18  cmp     cs:?NlGlobalSiteInitialized@@3EA, 0; uchar NlGlobalSiteInitialized
0x180044b1f  jz      loc_180044C35
0x180044b25  lea     rdx, aNlsiteterminat; "NlSiteTerminate: Entered\n"
0x180044b2c  mov     ecx, 8000000h; unsigned int
0x180044b31  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180044b36  lea     rcx, ?NlGlobalSiteCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180044b3d  call    cs:__imp_RtlEnterCriticalSection
0x180044b44  nop     dword ptr [rax+rax+00h]
0x180044b49  lea     rcx, ?NlGlobalSubnetTree@@3U_NL_SUBNET_TREE_ENTRY@@A; struct _NL_SUBNET_TREE_ENTRY *
0x180044b50  call    ?NlSiteDeleteSubnetTree@@YAXPEAU_NL_SUBNET_TREE_ENTRY@@@Z; NlSiteDeleteSubnetTree(_NL_SUBNET_TREE_ENTRY *)
0x180044b55  lea     rcx, ?NlGlobalNewSubnetTree@@3U_NL_SUBNET_TREE_ENTRY@@A; struct _NL_SUBNET_TREE_ENTRY *
0x180044b5c  call    ?NlSiteDeleteSubnetTree@@YAXPEAU_NL_SUBNET_TREE_ENTRY@@@Z; NlSiteDeleteSubnetTree(_NL_SUBNET_TREE_ENTRY *)
0x180044b61  lea     rcx, ?NlGlobalV6SubnetTree@@3U_NL_SUBNET_TREE_ENTRY@@A; struct _NL_SUBNET_TREE_ENTRY *
0x180044b68  call    ?NlSiteDeleteSubnetTree@@YAXPEAU_NL_SUBNET_TREE_ENTRY@@@Z; NlSiteDeleteSubnetTree(_NL_SUBNET_TREE_ENTRY *)
0x180044b6d  lea     rcx, ?NlGlobalV6NewSubnetTree@@3U_NL_SUBNET_TREE_ENTRY@@A; struct _NL_SUBNET_TREE_ENTRY *
0x180044b74  call    ?NlSiteDeleteSubnetTree@@YAXPEAU_NL_SUBNET_TREE_ENTRY@@@Z; NlSiteDeleteSubnetTree(_NL_SUBNET_TREE_ENTRY *)
0x180044b79  xor     edx, edx; unsigned __int8 *
0x180044b7b  xor     ecx, ecx; Src
0x180044b7d  call    ?NlSetSiteName_Old@@YAKPEAGPEAE@Z; NlSetSiteName_Old(ushort *,uchar *)
0x180044b82  mov     rcx, cs:?NlGlobalUnicodeNextClosestSiteName@@3PEAGEA; hMem
0x180044b89  test    rcx, rcx
0x180044b8c  jz      short loc_180044BA5
0x180044b8e  call    cs:__imp_LocalFree
0x180044b95  nop     dword ptr [rax+rax+00h]
0x180044b9a  mov     cs:?NlGlobalUnicodeNextClosestSiteName@@3PEAGEA, 0; ushort * NlGlobalUnicodeNextClosestSiteName
0x180044ba5  lea     rcx, ?NlGlobalSiteCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180044bac  call    cs:__imp_RtlLeaveCriticalSection
0x180044bb3  nop     dword ptr [rax+rax+00h]
0x180044bb8  lea     rax, ?NlGlobalSiteList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalSiteList
0x180044bbf  cmp     cs:?NlGlobalSiteList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalSiteList
0x180044bc6  jz      short loc_180044BE1
0x180044bc8  mov     r8d, 0FCDh; unsigned int
0x180044bce  lea     rdx, aOnecoreDsNetap_18; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180044bd5  lea     rcx, aIslistemptyNlg_3; "IsListEmpty( &NlGlobalSiteList )"
0x180044bdc  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180044be1  lea     rax, ?NlGlobalSubnetList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalSubnetList
0x180044be8  cmp     cs:?NlGlobalSubnetList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalSubnetList
0x180044bef  jz      short loc_180044C0A
0x180044bf1  mov     r8d, 0FCEh; unsigned int
0x180044bf7  lea     rdx, aOnecoreDsNetap_18; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180044bfe  lea     rcx, aIslistemptyNlg; "IsListEmpty( &NlGlobalSubnetList )"
0x180044c05  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180044c0a  lea     rcx, ?NlGlobalSiteCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180044c11  call    cs:__imp_RtlDeleteCriticalSection
0x180044c18  nop     dword ptr [rax+rax+00h]
0x180044c1d  lea     rdx, aNlsiteterminat_0; "NlSiteTerminate: Exitted\n"
0x180044c24  mov     cs:?NlGlobalSiteInitialized@@3EA, 0; uchar NlGlobalSiteInitialized
0x180044c2b  mov     ecx, 8000000h; unsigned int
0x180044c30  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180044c35  add     rsp, 28h
0x180044c39  retn
```
