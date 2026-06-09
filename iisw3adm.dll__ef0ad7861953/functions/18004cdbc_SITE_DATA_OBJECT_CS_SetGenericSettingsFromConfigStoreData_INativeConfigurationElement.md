# SITE_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData(INativeConfigurationElement *)

- ea: `0x18004cdbc`
- end: `0x18004d012`
- name: `?SetGenericSettingsFromConfigStoreData@SITE_DATA_OBJECT_CS@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `598`
- prototype: `__int64 __fastcall(SITE_DATA_OBJECT_CS *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004c3e0`

## callees

- `0x18004cdbc`
- `0x180052d90`
- `0x180053908`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18004cead`
- `iisutil!PuDbgPrint` at `0x18004cfe8`
- `iisutil!PuDbgPrint` at `0x18004cead`
- `iisutil!PuDbgPrint` at `0x18004cfe8`
- `iisutil!PuDbgPrintError` at `0x18004ce4e`
- `iisutil!PuDbgPrintError` at `0x18004ce4e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004cec0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004cec0`

## string_xrefs

- `0x18004ce29`: ` Failed reading property \n`
- `0x18004ced9`: ` Failed copying string property \n`
- `0x18004ce37`: `SITE_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData`
- `0x18004ce7d`: `SITE_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData`
- `0x18004cfc2`: `SITE_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData`
- `0x18004ce43`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_cs.cxx`
- `0x18004ce8a`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_cs.cxx`
- `0x18004cfd0`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_cs.cxx`

## pseudocode

```c
__int64 __fastcall SITE_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData(
        SITE_DATA_OBJECT_CS *this,
        struct INativeConfigurationElement *a2)
{
  __int64 v2; // rax
  int v5; // ebx
  __int64 v6; // r8
  const wchar_t *v7; // rcx
  int *v8; // r12
  struct CONFIG_ERROR *v9; // rdx
  const wchar_t *v10; // rax
  struct INativePropertyException *v12; // [rsp+68h] [rbp+38h] BYREF
  const unsigned __int16 *v13; // [rsp+70h] [rbp+40h] BYREF
  struct CONFIG_ERROR *v14; // [rsp+78h] [rbp+48h] BYREF

  v2 = *(_QWORD *)a2;
  v13 = 0;
  v12 = 0;
  v14 = 0;
  v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, const unsigned __int16 **, _QWORD, _QWORD))(v2 + 64))(
         a2,
         L"name",
         &v13,
         0,
         0);
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_26;
    v6 = 57;
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
      v6,
      "SITE_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData",
      v5,
      " Failed reading property \n");
    goto LABEL_26;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    v7 = L"NULL";
    if ( v13 )
      v7 = v13;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
      65,
      "SITE_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData",
      " Site Name '%S' \n",
      v7);
  }
  if ( v13 )
  {
    v5 = STRU::Copy((SITE_DATA_OBJECT_CS *)((char *)this + 80), v13);
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
          76,
          "SITE_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData",
          v5,
          " Failed copying string property \n");
      goto LABEL_26;
    }
    v13 = 0;
  }
  v8 = (int *)((char *)this + 72);
  v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, struct INativePropertyException **, _QWORD))(*(_QWORD *)a2 + 72LL))(
         a2,
         L"serverAutoStart",
         (char *)this + 72,
         &v12,
         0);
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_26;
    v6 = 90;
    goto LABEL_4;
  }
  if ( v12 )
  {
    CONFIG_ERROR::CreateAndInitWithBool(&v14, L"serverAutoStart", *v8, v12);
    v9 = v14;
    if ( v14 )
    {
      *((_DWORD *)v14 + 2) = 71;
      CONFIG_ERROR_LIST::Add((SITE_DATA_OBJECT_CS *)((char *)this + 304), v9);
    }
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    v10 = L"TRUE";
    if ( !*v8 )
      v10 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
      111,
      "SITE_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData",
      " Auto Start '%S' \n",
      v10);
  }
LABEL_26:
  if ( v12 )
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004cdbc  push    rbp
0x18004cdbe  push    rbx
0x18004cdbf  push    r12
0x18004cdc1  push    r14
0x18004cdc3  push    r15
0x18004cdc5  mov     rbp, rsp
0x18004cdc8  sub     rsp, 30h
0x18004cdcc  mov     rax, [rdx]
0x18004cdcf  lea     r8, [rbp+arg_10]
0x18004cdd3  mov     r15, rdx
0x18004cdd6  mov     [rbp+arg_10], 0
0x18004cdde  mov     r14, rcx
0x18004cde1  mov     [rbp+arg_8], 0
0x18004cde9  xor     r9d, r9d
0x18004cdec  mov     [rbp+arg_18], 0
0x18004cdf4  mov     rax, [rax+40h]
0x18004cdf8  lea     rdx, aName_0; "name"
0x18004cdff  mov     rcx, r15
0x18004ce02  mov     [rsp+30h+var_10], 0
0x18004ce0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce10  mov     ebx, eax
0x18004ce12  test    eax, eax
0x18004ce14  jns     short loc_18004CE59
0x18004ce16  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004ce1d  jz      loc_18004CFEE
0x18004ce23  mov     r8d, 39h ; '9'
0x18004ce29  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004ce30  mov     rcx, cs:g_pDebug
0x18004ce37  lea     r9, aSiteDataObject_13; "SITE_DATA_OBJECT_CS::SetGenericSettings"...
0x18004ce3e  mov     [rsp+30h+var_8], rax
0x18004ce43  lea     rdx, aServercommonIn_40; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004ce4a  mov     dword ptr [rsp+30h+var_10], ebx
0x18004ce4e  call    cs:__imp_PuDbgPrintError
0x18004ce54  jmp     loc_18004CFEE
0x18004ce59  mov     eax, cs:g_dwDebugFlags
0x18004ce5f  test    al, 3
0x18004ce61  setnz   cl
0x18004ce64  bt      eax, 1Eh
0x18004ce68  setb    al
0x18004ce6b  test    al, cl
0x18004ce6d  jz      short loc_18004CEB3
0x18004ce6f  mov     rax, [rbp+arg_10]
0x18004ce73  lea     rcx, aNull_0; "NULL"
0x18004ce7a  test    rax, rax
0x18004ce7d  lea     r9, aSiteDataObject_13; "SITE_DATA_OBJECT_CS::SetGenericSettings"...
0x18004ce84  mov     r8d, 41h ; 'A'
0x18004ce8a  lea     rdx, aServercommonIn_40; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004ce91  cmovnz  rcx, rax
0x18004ce95  lea     rax, aSiteNameS; " Site Name '%S' \n"
0x18004ce9c  mov     [rsp+30h+var_8], rcx
0x18004cea1  mov     rcx, cs:g_pDebug
0x18004cea8  mov     [rsp+30h+var_10], rax
0x18004cead  call    cs:__imp_PuDbgPrint
0x18004ceb3  mov     rdx, [rbp+arg_10]
0x18004ceb7  test    rdx, rdx
0x18004ceba  jz      short loc_18004CEF3
0x18004cebc  lea     rcx, [r14+50h]
0x18004cec0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18004cec6  mov     ebx, eax
0x18004cec8  test    eax, eax
0x18004ceca  jns     short loc_18004CEEB
0x18004cecc  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004ced3  jz      loc_18004CFEE
0x18004ced9  lea     rax, aFailedCopyingS; " Failed copying string property \n"
0x18004cee0  mov     r8d, 4Ch ; 'L'
0x18004cee6  jmp     loc_18004CE30
0x18004ceeb  mov     [rbp+arg_10], 0
0x18004cef3  mov     rax, [r15]
0x18004cef6  lea     r12, [r14+48h]
0x18004cefa  lea     r9, [rbp+arg_8]
0x18004cefe  mov     [rsp+30h+var_10], 0
0x18004cf07  mov     r8, r12
0x18004cf0a  lea     rdx, aServerautostar; "serverAutoStart"
0x18004cf11  mov     rcx, r15
0x18004cf14  mov     rax, [rax+48h]
0x18004cf18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf1d  mov     ebx, eax
0x18004cf1f  test    eax, eax
0x18004cf21  jns     short loc_18004CF3B
0x18004cf23  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004cf2a  jz      loc_18004CFEE
0x18004cf30  mov     r8d, 5Ah ; 'Z'
0x18004cf36  jmp     loc_18004CE29
0x18004cf3b  mov     rcx, [rbp+arg_8]
0x18004cf3f  test    rcx, rcx
0x18004cf42  jz      short loc_18004CF8F
0x18004cf44  mov     r8d, [r12]; int
0x18004cf48  lea     rdx, aServerautostar; "serverAutoStart"
0x18004cf4f  mov     r9, rcx; struct INativePropertyException *
0x18004cf52  lea     rcx, [rbp+arg_18]; struct CONFIG_ERROR **
0x18004cf56  call    ?CreateAndInitWithBool@CONFIG_ERROR@@SAXPEAPEAV1@PEBGHPEAVINativePropertyException@@@Z; CONFIG_ERROR::CreateAndInitWithBool(CONFIG_ERROR * *,ushort const *,int,INativePropertyException *)
0x18004cf5b  mov     rdx, [rbp+arg_18]; struct CONFIG_ERROR *
0x18004cf5f  test    rdx, rdx
0x18004cf62  jz      short loc_18004CF77
0x18004cf64  lea     rcx, [r14+130h]; this
0x18004cf6b  mov     dword ptr [rdx+8], 47h ; 'G'
0x18004cf72  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x18004cf77  mov     rcx, [rbp+arg_8]
0x18004cf7b  mov     rax, [rcx]
0x18004cf7e  mov     rax, [rax+10h]
0x18004cf82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf87  mov     [rbp+arg_8], 0
0x18004cf8f  mov     eax, cs:g_dwDebugFlags
0x18004cf95  test    al, 3
0x18004cf97  setnz   cl
0x18004cf9a  bt      eax, 1Eh
0x18004cf9e  setb    al
0x18004cfa1  test    al, cl
0x18004cfa3  jz      short loc_18004CFEE
0x18004cfa5  cmp     dword ptr [r12], 0
0x18004cfaa  lea     rcx, aFalse_1; "FALSE"
0x18004cfb1  lea     rax, aTrue_1; "TRUE"
0x18004cfb8  mov     r8d, 6Fh ; 'o'
0x18004cfbe  cmovz   rax, rcx
0x18004cfc2  lea     r9, aSiteDataObject_13; "SITE_DATA_OBJECT_CS::SetGenericSettings"...
0x18004cfc9  mov     rcx, cs:g_pDebug
0x18004cfd0  lea     rdx, aServercommonIn_40; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004cfd7  mov     [rsp+30h+var_8], rax
0x18004cfdc  lea     rax, aAutoStartS; " Auto Start '%S' \n"
0x18004cfe3  mov     [rsp+30h+var_10], rax
0x18004cfe8  call    cs:__imp_PuDbgPrint
0x18004cfee  mov     rcx, [rbp+arg_8]
0x18004cff2  test    rcx, rcx
0x18004cff5  jz      short loc_18004D003
0x18004cff7  mov     rax, [rcx]
0x18004cffa  mov     rax, [rax+10h]
0x18004cffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d003  mov     eax, ebx
0x18004d005  add     rsp, 30h
0x18004d009  pop     r15
0x18004d00b  pop     r14
0x18004d00d  pop     r12
0x18004d00f  pop     rbx
0x18004d010  pop     rbp
0x18004d011  retn
```
