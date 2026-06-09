# __scrt_dllmain_after_initialize_c

- ea: `0x180001650`
- end: `0x180001684`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800011f8`

## callees

- `0x180001650`
- `0x180001ef8`
- `0x180002184`
- `0x18000220e`
- `0x180002232`
- `0x180015b50`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  struct _PROPSHEETPAGEW *v0; // rdx
  DiskQuotaPropPage *v1; // rcx
  _crt_argv_mode v2; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    v2 = DiskQuotaPropPage::OnPropSheetPageCreate(v1, v0);
    if ( o__configure_narrow_argv_0(v2) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180001650  sub     rsp, 28h
0x180001654  call    __scrt_is_ucrt_dll_in_use
0x180001659  test    eax, eax
0x18000165b  jz      short loc_180001664
0x18000165d  call    __isa_available_init
0x180001662  jmp     short loc_18000167D
0x180001664  call    ?OnPropSheetPageCreate@DiskQuotaPropPage@@MEAAIPEAU_PROPSHEETPAGEW@@@Z; DiskQuotaPropPage::OnPropSheetPageCreate(_PROPSHEETPAGEW *)
0x180001669  mov     ecx, eax; mode
0x18000166b  call    _o__configure_narrow_argv_0
0x180001670  test    eax, eax
0x180001672  jz      short loc_180001678
0x180001674  xor     al, al
0x180001676  jmp     short loc_18000167F
0x180001678  call    _initialize_narrow_environment
0x18000167d  mov     al, 1
0x18000167f  add     rsp, 28h
0x180001683  retn
```
