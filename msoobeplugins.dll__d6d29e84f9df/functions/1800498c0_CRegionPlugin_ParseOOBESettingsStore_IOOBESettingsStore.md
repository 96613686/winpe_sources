# CRegionPlugin::ParseOOBESettingsStore(IOOBESettingsStore *)

- ea: `0x1800498c0`
- end: `0x180049b10`
- name: `?ParseOOBESettingsStore@CRegionPlugin@@UEAAJPEAUIOOBESettingsStore@@@Z`
- size: `592`
- prototype: `__int64 __fastcall(CRegionPlugin *__hidden this, struct IOOBESettingsStore *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800098cc`
- `0x18000b358`
- `0x1800498c0`
- `0x18004b500`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004990e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049a84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049add`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004990e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049a84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049add`

## string_xrefs

- `0x180049a6e`: `Failed to read in '%s' setting from oobe.xml file with hr=0x%08X`
- `0x180049ac8`: `Found '%s' setting in oobe.xml file [%s]`
- `0x180049a2f`: `Found '%s' setting in oobe.xml file [%s] is too short.  Check that the KLID is qualified with LangID.`
- `0x18004995d`: `Found '%s' setting in oobe.xml file [%d]`
- `0x1800499bb`: `Found '%s' setting in oobe.xml file [%d]`

## pseudocode

```c
__int64 __fastcall CRegionPlugin::ParseOOBESettingsStore(CRegionPlugin *this, struct IOOBESettingsStore *a2)
{
  __int64 v4; // rax
  int v5; // eax
  int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rax
  size_t v9; // rdi
  unsigned __int64 v10; // rax
  const wchar_t *v11; // r8
  __int64 v12; // rdx
  unsigned __int64 v13; // rcx
  __int64 v15; // [rsp+20h] [rbp-10h]
  unsigned int v16; // [rsp+60h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+40h] BYREF

  if ( *((_BYTE *)this + 80) )
    return 0;
  SafeRelease<IOOBETimeZoneItem>((char *)this + 40);
  SafeRelease<IOOBETimeZoneItem>((char *)this + 48);
  SafeRelease<IOOBETimeZoneItem>((char *)this + 56);
  CoTaskMemFree(*((LPVOID *)this + 9));
  *((_QWORD *)this + 9) = 0;
  v4 = *(_QWORD *)a2;
  v16 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IOOBESettingsStore *, const WCHAR *, unsigned int *))(v4 + 32))(
         a2,
         L"defaults/location",
         &v16);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( v5 != -2147023728 )
    {
      v11 = L"defaults/location";
      goto LABEL_16;
    }
  }
  else
  {
    v6 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 1) + 72LL))((char *)this + 8, v16);
    UnattendLogW(0, L"Found '%s' setting in oobe.xml file [%d]", L"defaults/location", v16);
    if ( v6 < 0 )
      return (unsigned int)v6;
  }
  v7 = *(_QWORD *)a2;
  LODWORD(pv) = 0;
  v5 = (*(__int64 (__fastcall **)(struct IOOBESettingsStore *, const wchar_t *, LPVOID *))(v7 + 32))(
         a2,
         L"defaults/locale",
         &pv);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( v5 == -2147023728 )
      goto LABEL_6;
    v11 = L"defaults/locale";
LABEL_16:
    UnattendLogW(1, L"Failed to read in '%s' setting from oobe.xml file with hr=0x%08X", v11, (unsigned int)v5);
    return (unsigned int)v6;
  }
  v6 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 1) + 104LL))((char *)this + 8, (unsigned int)pv);
  UnattendLogW(0, L"Found '%s' setting in oobe.xml file [%d]", L"defaults/locale", (unsigned int)pv);
  if ( v6 < 0 )
    return (unsigned int)v6;
LABEL_6:
  v6 = CRegionPlugin::_SetPendingRegionAndLocaleFromLanguageDefaultIfNeeded((CRegionPlugin *)((char *)this - 24));
  if ( v6 < 0 )
    return (unsigned int)v6;
  v8 = *(_QWORD *)a2;
  pv = 0;
  v5 = (*(__int64 (__fastcall **)(struct IOOBESettingsStore *, const WCHAR *, LPVOID *))(v8 + 40))(
         a2,
         L"defaults/keyboard",
         &pv);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( v5 != -2147023728 )
    {
      v11 = L"defaults/keyboard";
      goto LABEL_16;
    }
    return 0;
  }
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( *((_WORD *)pv + v10) );
  if ( v10 >= 0xD )
  {
    CoTaskMemFree(*((LPVOID *)this + 9));
    do
      ++v9;
    while ( *((_WORD *)pv + v9) );
    v6 = _AllocStringWorker<CTCoAllocPolicy>(v13, v12, (const wchar_t *)pv, v9, v15, (void **)this + 9);
    if ( v6 >= 0 )
      v6 = (*(__int64 (__fastcall **)(char *, LPVOID))(*((_QWORD *)this + 1) + 136LL))((char *)this + 8, pv);
    UnattendLogW(0, L"Found '%s' setting in oobe.xml file [%s]", L"defaults/keyboard", pv);
  }
  else
  {
    UnattendLogW(
      2,
      L"Found '%s' setting in oobe.xml file [%s] is too short.  Check that the KLID is qualified with LangID.",
      L"defaults/keyboard",
      pv);
  }
  CoTaskMemFree(pv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800498c0  mov     [rsp-28h+arg_8], rbx
0x1800498c5  mov     [rsp-28h+arg_18], rsi
0x1800498ca  push    rbp
0x1800498cb  push    rdi
0x1800498cc  push    r12
0x1800498ce  push    r14
0x1800498d0  push    r15
0x1800498d2  mov     rbp, rsp
0x1800498d5  sub     rsp, 30h
0x1800498d9  xor     r12d, r12d
0x1800498dc  mov     rdi, rdx
0x1800498df  mov     rsi, rcx
0x1800498e2  cmp     [rcx+50h], r12b
0x1800498e6  jnz     loc_180049AF4
0x1800498ec  add     rcx, 28h ; '('
0x1800498f0  call    ??$SafeRelease@UIOOBETimeZoneItem@@@@YAXPEAPEAUIOOBETimeZoneItem@@@Z; SafeRelease<IOOBETimeZoneItem>(IOOBETimeZoneItem * *)
0x1800498f5  lea     rcx, [rsi+30h]
0x1800498f9  call    ??$SafeRelease@UIOOBETimeZoneItem@@@@YAXPEAPEAUIOOBETimeZoneItem@@@Z; SafeRelease<IOOBETimeZoneItem>(IOOBETimeZoneItem * *)
0x1800498fe  lea     rcx, [rsi+38h]
0x180049902  call    ??$SafeRelease@UIOOBETimeZoneItem@@@@YAXPEAPEAUIOOBETimeZoneItem@@@Z; SafeRelease<IOOBETimeZoneItem>(IOOBETimeZoneItem * *)
0x180049907  lea     r15, [rsi+48h]
0x18004990b  mov     rcx, [r15]; pv
0x18004990e  call    cs:__imp_CoTaskMemFree
0x180049914  mov     [r15], r12
0x180049917  lea     r8, [rbp+arg_0]
0x18004991b  mov     rax, [rdi]
0x18004991e  lea     rdx, aDefaultsLocati; "defaults/location"
0x180049925  mov     rcx, rdi
0x180049928  mov     [rbp+arg_0], r12d
0x18004992c  mov     rax, [rax+20h]
0x180049930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049935  mov     ebx, eax
0x180049937  test    eax, eax
0x180049939  js      loc_180049A45
0x18004993f  mov     edx, [rbp+arg_0]
0x180049942  lea     rcx, [rsi+8]
0x180049946  mov     rax, [rcx]
0x180049949  mov     rax, [rax+48h]
0x18004994d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049952  mov     r9d, [rbp+arg_0]
0x180049956  lea     r8, aDefaultsLocati; "defaults/location"
0x18004995d  lea     rdx, aFoundSSettingI_1; "Found '%s' setting in oobe.xml file [%d"...
0x180049964  xor     ecx, ecx
0x180049966  mov     ebx, eax
0x180049968  call    UnattendLogW
0x18004996d  test    ebx, ebx
0x18004996f  js      loc_180049AF7
0x180049975  mov     rax, [rdi]
0x180049978  lea     r8, [rbp+pv]
0x18004997c  lea     rdx, aDefaultsLocale; "defaults/locale"
0x180049983  mov     dword ptr [rbp+pv], r12d
0x180049987  mov     rcx, rdi
0x18004998a  mov     rax, [rax+20h]
0x18004998e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049993  mov     ebx, eax
0x180049995  test    eax, eax
0x180049997  js      loc_180049A59
0x18004999d  mov     edx, dword ptr [rbp+pv]
0x1800499a0  lea     rcx, [rsi+8]
0x1800499a4  mov     rax, [rcx]
0x1800499a7  mov     rax, [rax+68h]
0x1800499ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499b0  mov     r9d, dword ptr [rbp+pv]
0x1800499b4  lea     r8, aDefaultsLocale; "defaults/locale"
0x1800499bb  lea     rdx, aFoundSSettingI_1; "Found '%s' setting in oobe.xml file [%d"...
0x1800499c2  xor     ecx, ecx
0x1800499c4  mov     ebx, eax
0x1800499c6  call    UnattendLogW
0x1800499cb  test    ebx, ebx
0x1800499cd  js      loc_180049AF7
0x1800499d3  lea     rcx, [rsi-18h]; this
0x1800499d7  call    ?_SetPendingRegionAndLocaleFromLanguageDefaultIfNeeded@CRegionPlugin@@AEAAJXZ; CRegionPlugin::_SetPendingRegionAndLocaleFromLanguageDefaultIfNeeded(void)
0x1800499dc  mov     ebx, eax
0x1800499de  test    eax, eax
0x1800499e0  js      loc_180049AF7
0x1800499e6  mov     rax, [rdi]
0x1800499e9  lea     r14, aDefaultsKeyboa; "defaults/keyboard"
0x1800499f0  lea     r8, [rbp+pv]
0x1800499f4  mov     [rbp+pv], r12
0x1800499f8  mov     rdx, r14
0x1800499fb  mov     rcx, rdi
0x1800499fe  mov     rax, [rax+28h]
0x180049a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a07  mov     ebx, eax
0x180049a09  test    eax, eax
0x180049a0b  js      loc_180049AE5
0x180049a11  mov     r9, [rbp+pv]
0x180049a15  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180049a19  mov     rax, rdi
0x180049a1c  inc     rax
0x180049a1f  cmp     [r9+rax*2], r12w
0x180049a24  jnz     short loc_180049A1C
0x180049a26  cmp     rax, 0Dh
0x180049a2a  jnb     short loc_180049A81
0x180049a2c  mov     r8, r14
0x180049a2f  lea     rdx, aFoundSSettingI_2; "Found '%s' setting in oobe.xml file [%s"...
0x180049a36  mov     ecx, 2
0x180049a3b  call    UnattendLogW
0x180049a40  jmp     loc_180049AD9
0x180049a45  cmp     eax, 80070490h
0x180049a4a  jz      loc_180049975
0x180049a50  lea     r8, aDefaultsLocati; "defaults/location"
0x180049a57  jmp     short loc_180049A6B
0x180049a59  cmp     eax, 80070490h
0x180049a5e  jz      loc_1800499D3
0x180049a64  lea     r8, aDefaultsLocale; "defaults/locale"
0x180049a6b  mov     r9d, eax
0x180049a6e  lea     rdx, aFailedToReadIn_0; "Failed to read in '%s' setting from oob"...
0x180049a75  mov     ecx, 1
0x180049a7a  call    UnattendLogW
0x180049a7f  jmp     short loc_180049AF7
0x180049a81  mov     rcx, [r15]; pv
0x180049a84  call    cs:__imp_CoTaskMemFree
0x180049a8a  mov     r8, [rbp+pv]
0x180049a8e  inc     rdi
0x180049a91  cmp     [r8+rdi*2], r12w
0x180049a96  jnz     short loc_180049A8E
0x180049a98  mov     r9, rdi
0x180049a9b  mov     [rsp+30h+var_8], r15
0x180049aa0  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180049aa5  mov     ebx, eax
0x180049aa7  test    eax, eax
0x180049aa9  js      short loc_180049AC4
0x180049aab  mov     rdx, [rbp+pv]
0x180049aaf  lea     rcx, [rsi+8]
0x180049ab3  mov     rax, [rcx]
0x180049ab6  mov     rax, [rax+88h]
0x180049abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ac2  mov     ebx, eax
0x180049ac4  mov     r9, [rbp+pv]
0x180049ac8  lea     rdx, aFoundSSettingI; "Found '%s' setting in oobe.xml file [%s"...
0x180049acf  mov     r8, r14
0x180049ad2  xor     ecx, ecx
0x180049ad4  call    UnattendLogW
0x180049ad9  mov     rcx, [rbp+pv]; pv
0x180049add  call    cs:__imp_CoTaskMemFree
0x180049ae3  jmp     short loc_180049AF7
0x180049ae5  cmp     eax, 80070490h
0x180049aea  jz      short loc_180049AF4
0x180049aec  mov     r8, r14
0x180049aef  jmp     loc_180049A6B
0x180049af4  mov     ebx, r12d
0x180049af7  mov     rsi, [rsp+30h+arg_18]
0x180049afc  mov     eax, ebx
0x180049afe  mov     rbx, [rsp+30h+arg_8]
0x180049b03  add     rsp, 30h
0x180049b07  pop     r15
0x180049b09  pop     r14
0x180049b0b  pop     r12
0x180049b0d  pop     rdi
0x180049b0e  pop     rbp
0x180049b0f  retn
```
