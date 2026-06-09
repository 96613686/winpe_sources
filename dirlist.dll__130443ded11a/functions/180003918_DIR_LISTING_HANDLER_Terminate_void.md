# DIR_LISTING_HANDLER::Terminate(void)

- ea: `0x180003918`
- end: `0x180003967`
- name: `?Terminate@DIR_LISTING_HANDLER@@SAXXZ`
- size: `79`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180002180`
- `0x1800023d0`

## callees

- `0x180001048`
- `0x180003918`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003951`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003951`
- `iisutil!?Terminate@LANG_STRING@@QEAAJXZ` at `0x180003928`
- `iisutil!?Terminate@LANG_STRING@@QEAAJXZ` at `0x180003928`

## pseudocode

```c
void DIR_LISTING_HANDLER::Terminate(void)
{
  if ( DIR_LISTING_HANDLER::sm_pLangString )
  {
    LANG_STRING::Terminate((LANG_STRING *)DIR_LISTING_HANDLER::sm_pLangString);
    operator delete(DIR_LISTING_HANDLER::sm_pLangString);
    DIR_LISTING_HANDLER::sm_pLangString = 0;
  }
  if ( DIR_LISTING_HANDLER::sm_hResourceDll )
  {
    FreeLibrary(DIR_LISTING_HANDLER::sm_hResourceDll);
    DIR_LISTING_HANDLER::sm_hResourceDll = 0;
  }
}

```

## disassembly

```asm
0x180003918  sub     rsp, 28h
0x18000391c  mov     rcx, cs:?sm_pLangString@DIR_LISTING_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * DIR_LISTING_HANDLER::sm_pLangString
0x180003923  test    rcx, rcx
0x180003926  jz      short loc_180003945
0x180003928  call    cs:__imp_?Terminate@LANG_STRING@@QEAAJXZ; LANG_STRING::Terminate(void)
0x18000392e  mov     rcx, cs:?sm_pLangString@DIR_LISTING_HANDLER@@2PEAVLANG_STRING@@EA; Block
0x180003935  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000393a  mov     cs:?sm_pLangString@DIR_LISTING_HANDLER@@2PEAVLANG_STRING@@EA, 0; LANG_STRING * DIR_LISTING_HANDLER::sm_pLangString
0x180003945  mov     rcx, cs:?sm_hResourceDll@DIR_LISTING_HANDLER@@2PEAUHINSTANCE__@@EA; hLibModule
0x18000394c  test    rcx, rcx
0x18000394f  jz      short loc_180003962
0x180003951  call    cs:__imp_FreeLibrary
0x180003957  mov     cs:?sm_hResourceDll@DIR_LISTING_HANDLER@@2PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * DIR_LISTING_HANDLER::sm_hResourceDll
0x180003962  add     rsp, 28h
0x180003966  retn
```
