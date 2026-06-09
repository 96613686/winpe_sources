# CUSTOM_ERROR_HANDLER::Terminate(void)

- ea: `0x180001f40`
- end: `0x180001fe9`
- name: `?Terminate@CUSTOM_ERROR_HANDLER@@SAXXZ`
- size: `169`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180001d3c`
- `0x180005360`

## callees

- `0x180001f40`
- `0x180002030`
- `0x180002c28`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001fc9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001fc9`
- `iisutil!?Terminate@LANG_STRING@@QEAAJXZ` at `0x180001f9b`
- `iisutil!?Terminate@LANG_STRING@@QEAAJXZ` at `0x180001f9b`

## pseudocode

```c
void CUSTOM_ERROR_HANDLER::Terminate(void)
{
  if ( CUSTOM_ERROR_HANDLER::sm_StartupState != 1 )
  {
    if ( CUSTOM_ERROR_HANDLER::sm_StartupState == 2 )
      goto LABEL_10;
    if ( CUSTOM_ERROR_HANDLER::sm_StartupState != 3 )
    {
      if ( (unsigned int)(CUSTOM_ERROR_HANDLER::sm_StartupState - 4) > 1 )
        goto LABEL_14;
      if ( _InterlockedExchangeAdd(&MIME_MAP_TABLE::sm_lInitializeCount, 0xFFFFFFFF) == 1
        && MIME_MAP_TABLE::sm_pGlobalTable )
      {
        MIME_MAP_TABLE::Dereference(MIME_MAP_TABLE::sm_pGlobalTable);
        MIME_MAP_TABLE::sm_pGlobalTable = 0;
      }
    }
    if ( CUSTOM_ERROR_HANDLER::sm_pLangString )
    {
      LANG_STRING::Terminate((LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString);
LABEL_10:
      if ( CUSTOM_ERROR_HANDLER::sm_pLangString )
      {
        operator delete(CUSTOM_ERROR_HANDLER::sm_pLangString);
        CUSTOM_ERROR_HANDLER::sm_pLangString = 0;
      }
    }
  }
  if ( CUSTOM_ERROR_HANDLER::sm_hResourceDll )
  {
    FreeLibrary(CUSTOM_ERROR_HANDLER::sm_hResourceDll);
    CUSTOM_ERROR_HANDLER::sm_hResourceDll = 0;
  }
LABEL_14:
  CUSTOM_ERROR_HANDLER::sm_StartupState = 6;
}

```

## disassembly

```asm
0x180001f40  sub     rsp, 28h
0x180001f44  mov     ecx, cs:?sm_StartupState@CUSTOM_ERROR_HANDLER@@0W4CusterrStartup@@A; CusterrStartup CUSTOM_ERROR_HANDLER::sm_StartupState
0x180001f4a  sub     ecx, 1
0x180001f4d  jz      short loc_180001FBD
0x180001f4f  sub     ecx, 1
0x180001f52  jz      short loc_180001FA1
0x180001f54  sub     ecx, 1
0x180001f57  jz      short loc_180001F8F
0x180001f59  sub     ecx, 1
0x180001f5c  jz      short loc_180001F63
0x180001f5e  cmp     ecx, 1
0x180001f61  jnz     short loc_180001FDA
0x180001f63  or      eax, 0FFFFFFFFh
0x180001f66  lock xadd cs:?sm_lInitializeCount@MIME_MAP_TABLE@@0JA, eax; long MIME_MAP_TABLE::sm_lInitializeCount
0x180001f6e  cmp     eax, 1
0x180001f71  jnz     short loc_180001F8F
0x180001f73  mov     rcx, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; this
0x180001f7a  test    rcx, rcx
0x180001f7d  jz      short loc_180001F8F
0x180001f7f  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x180001f84  mov     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, 0; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180001f8f  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x180001f96  test    rcx, rcx
0x180001f99  jz      short loc_180001FBD
0x180001f9b  call    cs:__imp_?Terminate@LANG_STRING@@QEAAJXZ; LANG_STRING::Terminate(void)
0x180001fa1  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; Block
0x180001fa8  test    rcx, rcx
0x180001fab  jz      short loc_180001FBD
0x180001fad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001fb2  mov     cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA, 0; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x180001fbd  mov     rcx, cs:?sm_hResourceDll@CUSTOM_ERROR_HANDLER@@0PEAUHINSTANCE__@@EA; hLibModule
0x180001fc4  test    rcx, rcx
0x180001fc7  jz      short loc_180001FDA
0x180001fc9  call    cs:__imp_FreeLibrary
0x180001fcf  mov     cs:?sm_hResourceDll@CUSTOM_ERROR_HANDLER@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * CUSTOM_ERROR_HANDLER::sm_hResourceDll
0x180001fda  mov     cs:?sm_StartupState@CUSTOM_ERROR_HANDLER@@0W4CusterrStartup@@A, 6; CusterrStartup CUSTOM_ERROR_HANDLER::sm_StartupState
0x180001fe4  add     rsp, 28h
0x180001fe8  retn
```
