# SetupConfigurationSpec

- ea: `0x10015240`
- end: `0x10015360`
- name: `SetupConfigurationSpec`
- size: `288`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x100148d0`
- `0x10015100`
- `0x100151e0`

## callees

- `0x10009e50`
- `0x10009ea0`
- `0x10009f00`
- `0x10009f50`
- `0x10009fa0`
- `0x10015240`
- `0x10019b40`

## string_xrefs

- `0x10015292`: `Extensions`
- `0x1001530d`: `DisabledExtensions`

## pseudocode

```c
int __stdcall SetupConfigurationSpec(int a1)
{
  int result; // eax
  int v2; // esi

  result = ConfigAllocate();
  v2 = result;
  if ( result )
  {
    ConfigAddBoolParameter(result, L"ExportCurrencySymbols", &ISAMDefaults, 1);
    ConfigAddIntParameter(v2, L"MaxScanRows", &dword_10046A30, 25);
    ConfigAddBoolParameter(v2, L"FirstRowHasNames", &dword_10046A1C, 1);
    ConfigAddStrParameter(v2, L"Extensions", &String, 64, L"txt,csv,tab,asc");
    EncodeFormat(&pszDest, 0x40u);
    ConfigAddStrParameter(v2, L"Format", dword_10041068, 1026, &pszDest);
    ConfigAddStrParameter(v2, L"ImportFixedFormat", DefaultImportFixedFormat, 1026, L"RaggedEdge");
    ConfigAddStrParameter(v2, L"CharacterSet", &DefaultCharacterSet, 1026, L"ANSI");
    if ( !a1 )
      ConfigAddStrParameter(v2, L"DisabledExtensions", &DefaultSecureExtensions, 1026, L"!txt,csv,tab,asc,tmp,htm,html");
    ConfigAddEnumParameter(v2, L"ImportMixedTypes", &dword_100459B0, L"Majority Type", L"Text", L"Text RW", 0);
    ConfigAddEnumParameter(v2, L"UseZeroMaxScanAs", &dword_100459B4, L"None", L"One", L"All", 1);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x10015240  push    esi
0x10015241  call    _ConfigAllocate@0; ConfigAllocate()
0x10015246  mov     esi, eax
0x10015248  test    esi, esi
0x1001524a  jnz     short loc_10015250
0x1001524c  pop     esi
0x1001524d  retn    4
0x10015250  push    1
0x10015252  push    offset _ISAMDefaults
0x10015257  push    offset aExportcurrency; "ExportCurrencySymbols"
0x1001525c  push    esi
0x1001525d  call    _ConfigAddBoolParameter@16; ConfigAddBoolParameter(x,x,x,x)
0x10015262  push    19h
0x10015264  push    offset dword_10046A30
0x10015269  push    offset aMaxscanrows; "MaxScanRows"
0x1001526e  push    esi
0x1001526f  call    _ConfigAddIntParameter@16; ConfigAddIntParameter(x,x,x,x)
0x10015274  push    1
0x10015276  push    offset dword_10046A1C
0x1001527b  push    offset aFirstrowhasnam; "FirstRowHasNames"
0x10015280  push    esi
0x10015281  call    _ConfigAddBoolParameter@16; ConfigAddBoolParameter(x,x,x,x)
0x10015286  push    offset aTxtCsvTabAsc; "txt,csv,tab,asc"
0x1001528b  push    40h ; '@'
0x1001528d  push    offset String
0x10015292  push    offset aExtensions; "Extensions"
0x10015297  push    esi
0x10015298  call    _ConfigAddStrParameter@20; ConfigAddStrParameter(x,x,x,x,x)
0x1001529d  push    40h ; '@'; cchDest
0x1001529f  push    offset pszDest; pszDest
0x100152a4  call    _EncodeFormat@8; EncodeFormat(x,x)
0x100152a9  push    offset pszDest
0x100152ae  push    402h
0x100152b3  push    offset dword_10041068
0x100152b8  push    offset aFormat; "Format"
0x100152bd  push    esi
0x100152be  call    _ConfigAddStrParameter@20; ConfigAddStrParameter(x,x,x,x,x)
0x100152c3  push    offset aRaggededge; "RaggedEdge"
0x100152c8  push    402h
0x100152cd  push    offset _DefaultImportFixedFormat
0x100152d2  push    offset aImportfixedfor; "ImportFixedFormat"
0x100152d7  push    esi
0x100152d8  call    _ConfigAddStrParameter@20; ConfigAddStrParameter(x,x,x,x,x)
0x100152dd  push    offset aAnsi; "ANSI"
0x100152e2  push    402h
0x100152e7  push    offset _DefaultCharacterSet
0x100152ec  push    offset aCharacterset; "CharacterSet"
0x100152f1  push    esi
0x100152f2  call    _ConfigAddStrParameter@20; ConfigAddStrParameter(x,x,x,x,x)
0x100152f7  cmp     [esp+4+arg_0], 0
0x100152fc  jnz     short loc_10015318
0x100152fe  push    offset aTxtCsvTabAscTm; "!txt,csv,tab,asc,tmp,htm,html"
0x10015303  push    402h
0x10015308  push    offset _DefaultSecureExtensions
0x1001530d  push    offset aDisabledextens; "DisabledExtensions"
0x10015312  push    esi
0x10015313  call    _ConfigAddStrParameter@20; ConfigAddStrParameter(x,x,x,x,x)
0x10015318  push    0
0x1001531a  push    offset aTextRw; "Text RW"
0x1001531f  push    offset aText; "Text"
0x10015324  push    offset aMajorityType; "Majority Type"
0x10015329  push    offset dword_100459B0
0x1001532e  push    offset aImportmixedtyp; "ImportMixedTypes"
0x10015333  push    esi
0x10015334  call    _ConfigAddEnumParameter@28; ConfigAddEnumParameter(x,x,x,x,x,x,x)
0x10015339  push    1
0x1001533b  push    offset aAll; "All"
0x10015340  push    offset aOne; "One"
0x10015345  push    offset aNone; "None"
0x1001534a  push    offset dword_100459B4
0x1001534f  push    offset aUsezeromaxscan; "UseZeroMaxScanAs"
0x10015354  push    esi
0x10015355  call    _ConfigAddEnumParameter@28; ConfigAddEnumParameter(x,x,x,x,x,x,x)
0x1001535a  mov     eax, esi
0x1001535c  pop     esi
0x1001535d  retn    4
```
