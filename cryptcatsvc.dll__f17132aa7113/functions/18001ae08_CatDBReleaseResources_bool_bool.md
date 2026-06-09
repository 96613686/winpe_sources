# _CatDBReleaseResources(bool,bool)

- ea: `0x18001ae08`
- end: `0x18001aea7`
- name: `?_CatDBReleaseResources@@YAX_N0@Z`
- size: `159`
- prototype: `void __fastcall(bool, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ad54`

## callees

- `0x1800015b0`
- `0x18001ae08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ae1b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ae28`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ae35`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ae42`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ae1b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ae28`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ae35`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ae42`
- `ntdll!EtwEventUnregister` at `0x18001ae90`
- `ntdll!EtwEventUnregister` at `0x18001ae90`

## pseudocode

```c
void __fastcall _CatDBReleaseResources(char a1, char a2)
{
  if ( a2 )
  {
    DeleteCriticalSection(&g_CatDBAddDeleteCS);
    DeleteCriticalSection(&g_CatDirCashCS);
    DeleteCriticalSection(&g_JetDBOpenCS);
    DeleteCriticalSection(&g_CleanupTempFilesCS);
  }
  if ( g_pwszCatalogFileBaseDirectory )
  {
    _CatDBFree((void *)g_pwszCatalogFileBaseDirectory);
    g_pwszCatalogFileBaseDirectory = 0;
  }
  if ( g_pwszDatabaseFileBaseDirectory )
  {
    _CatDBFree((void *)g_pwszDatabaseFileBaseDirectory);
    g_pwszDatabaseFileBaseDirectory = 0;
  }
  if ( !a1 )
  {
    if ( qword_180032A08 )
    {
      EtwEventUnregister();
      qword_180032A08 = 0;
    }
  }
}

```

## disassembly

```asm
0x18001ae08  push    rbx
0x18001ae0a  sub     rsp, 20h
0x18001ae0e  mov     bl, cl
0x18001ae10  test    dl, dl
0x18001ae12  jz      short loc_18001AE48
0x18001ae14  lea     rcx, ?g_CatDBAddDeleteCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001ae1b  call    cs:__imp_DeleteCriticalSection
0x18001ae21  lea     rcx, ?g_CatDirCashCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001ae28  call    cs:__imp_DeleteCriticalSection
0x18001ae2e  lea     rcx, ?g_JetDBOpenCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001ae35  call    cs:__imp_DeleteCriticalSection
0x18001ae3b  lea     rcx, ?g_CleanupTempFilesCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001ae42  call    cs:__imp_DeleteCriticalSection
0x18001ae48  mov     rcx, cs:?g_pwszCatalogFileBaseDirectory@@3PEAGEA; void *
0x18001ae4f  test    rcx, rcx
0x18001ae52  jz      short loc_18001AE64
0x18001ae54  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001ae59  mov     cs:?g_pwszCatalogFileBaseDirectory@@3PEAGEA, 0; ushort * g_pwszCatalogFileBaseDirectory
0x18001ae64  mov     rcx, cs:?g_pwszDatabaseFileBaseDirectory@@3PEAGEA; void *
0x18001ae6b  test    rcx, rcx
0x18001ae6e  jz      short loc_18001AE80
0x18001ae70  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001ae75  mov     cs:?g_pwszDatabaseFileBaseDirectory@@3PEAGEA, 0; ushort * g_pwszDatabaseFileBaseDirectory
0x18001ae80  test    bl, bl
0x18001ae82  jnz     short loc_18001AEA1
0x18001ae84  mov     rcx, cs:qword_180032A08
0x18001ae8b  test    rcx, rcx
0x18001ae8e  jz      short loc_18001AEA1
0x18001ae90  call    cs:__imp_EtwEventUnregister
0x18001ae96  mov     cs:qword_180032A08, 0
0x18001aea1  add     rsp, 20h
0x18001aea5  pop     rbx
0x18001aea6  retn
```
