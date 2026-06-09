# PROTOCOL_DATA_OBJECT_CS::SetProtocolSettingsFromConfigStoreData(INativeConfigurationElement *)

- ea: `0x18005229c`
- end: `0x1800526c7`
- name: `?SetProtocolSettingsFromConfigStoreData@PROTOCOL_DATA_OBJECT_CS@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `1067`
- prototype: `__int64 __fastcall(PROTOCOL_DATA_OBJECT_CS *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180051f08`

## callees

- `0x180001234`
- `0x18005229c`
- `0x180052ccc`
- `0x1800531cc`
- `0x180053818`
- `0x180053908`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180052473`
- `iisutil!PuDbgPrint` at `0x180052562`
- `iisutil!PuDbgPrint` at `0x180052651`
- `iisutil!PuDbgPrint` at `0x180052473`
- `iisutil!PuDbgPrint` at `0x180052562`
- `iisutil!PuDbgPrint` at `0x180052651`
- `iisutil!PuDbgPrintError` at `0x18005232d`
- `iisutil!PuDbgPrintError` at `0x1800523a7`
- `iisutil!PuDbgPrintError` at `0x180052415`
- `iisutil!PuDbgPrintError` at `0x18005232d`
- `iisutil!PuDbgPrintError` at `0x1800523a7`
- `iisutil!PuDbgPrintError` at `0x180052415`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180052486`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180052578`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180052667`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180052486`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180052578`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180052667`

## string_xrefs

- `0x18005249f`: ` Failed copying string property \n`
- `0x180052591`: ` Failed copying string property \n`
- `0x18005267c`: ` Failed copying string property \n`
- `0x18005230d`: ` Failed reading identity property \n`
- `0x1800522ec`: `PROTOCOL_DATA_OBJECT_CS::SetProtocolSettingsFromConfigStoreData`
- `0x180052319`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_cs.cxx`
- `0x180052393`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_cs.cxx`
- `0x18005240b`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_cs.cxx`
- `0x180052460`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_cs.cxx`
- `0x180052530`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_cs.cxx`
- `0x180052622`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_cs.cxx`
- `0x1800523ea`: ` Out of memory creating config error object \n`
- `0x180052387`: ` Error initializing config error object \n`
- `0x1800524d5`: `protocolManagerDll`
- `0x1800524fb`: ` Failed reading protocolManagerDll property \n`
- `0x18005254a`: ` ProtocolManagerDll = '%s' \n`
- `0x1800525c7`: `protocolManagerDllInitFunction`
- `0x1800525ed`: ` Failed reading ProtocolManagerDllInitFunction property \n`
- `0x180052640`: ` ProtocolManagerDllInitFunction = '%s' \n`

## pseudocode

```c
__int64 __fastcall PROTOCOL_DATA_OBJECT_CS::SetProtocolSettingsFromConfigStoreData(
        PROTOCOL_DATA_OBJECT_CS *this,
        struct INativeConfigurationElement *a2)
{
  __int64 v2; // rax
  int v5; // ebx
  CONFIG_ERROR *v6; // rax
  CONFIG_ERROR *v7; // rax
  CONFIG_ERROR *v8; // rdi
  unsigned __int16 *v9; // rdx
  unsigned __int16 *v10; // rdi
  const char *v11; // rax
  unsigned __int16 *v12; // rcx
  unsigned __int16 *v14; // [rsp+68h] [rbp+38h] BYREF
  struct INativePropertyException *v15; // [rsp+70h] [rbp+40h] BYREF

  v2 = *(_QWORD *)a2;
  v14 = 0;
  v15 = 0;
  v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, unsigned __int16 **, struct INativePropertyException **, _QWORD))(v2 + 64))(
         a2,
         L"identity",
         &v14,
         &v15,
         0);
  if ( v5 >= 0 )
  {
    v9 = v14;
  }
  else
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_cs.cxx",
        58,
        "PROTOCOL_DATA_OBJECT_CS::SetProtocolSettingsFromConfigStoreData",
        v5,
        " Failed reading identity property \n");
    v6 = (CONFIG_ERROR *)operator new(0x138u);
    if ( !v6 || (v7 = CONFIG_ERROR::CONFIG_ERROR(v6), (v8 = v7) == 0) )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_cs.cxx",
          66,
          "PROTOCOL_DATA_OBJECT_CS::SetProtocolSettingsFromConfigStoreData",
          -2147024882,
          " Out of memory creating config error object \n");
      goto LABEL_48;
    }
    v5 = CONFIG_ERROR::InitializeWithString(v7, L"identity", v14, v15);
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_cs.cxx",
          78,
          "PROTOCOL_DATA_OBJECT_CS::SetProtocolSettingsFromConfigStoreData",
          v5,
          " Error initializing config error object \n");
      CONFIG_ERROR::Dereference(v8);
      goto LABEL_48;
    }
    *((_DWORD *)v8 + 2) = 81;
    CONFIG_ERROR_LIST::Add((PROTOCOL_DATA_OBJECT_CS *)((char *)this + 272), v8);
    v9 = (unsigned __int16 *)&SourceString;
    v14 = (unsigned __int16 *)&SourceString;
  }
  v10 = L"NULL";
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    v11 = (const char *)L"NULL";
    if ( v9 )
      v11 = (const char *)v9;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_cs.cxx",
      93,
      "PROTOCOL_DATA_OBJECT_CS::SetProtocolSettingsFromConfigStoreData",
      " Identity = '%s' \n",
      v11);
    v9 = v14;
  }
  if ( v9 )
  {
    v5 = STRU::Copy((PROTOCOL_DATA_OBJECT_CS *)((char *)this + 104), v9);
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_cs.cxx",
          103,
          "PROTOCOL_DATA_OBJECT_CS::SetProtocolSettingsFromConfigStoreData",
          v5,
          " Failed copying string property \n");
      goto LABEL_48;
    }
    v14 = 0;
  }
  v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
         a2,
         L"protocolManagerDll",
         &v14,
         0,
         0);
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_cs.cxx",
        117,
        "PROTOCOL_DATA_OBJECT_CS::SetProtocolSettingsFromConfigStoreData",
        v5,
        " Failed reading protocolManagerDll property \n");
    goto LABEL_48;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    v12 = L"NULL";
    if ( v14 )
      v12 = v14;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_cs.cxx",
      125,
      "PROTOCOL_DATA_OBJECT_CS::SetProtocolSettingsFromConfigStoreData",
      " ProtocolManagerDll = '%s' \n",
      (const char *)v12);
  }
  if ( v14 )
  {
    v5 = STRU::Copy((PROTOCOL_DATA_OBJECT_CS *)((char *)this + 160), v14);
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_cs.cxx",
          135,
          "PROTOCOL_DATA_OBJECT_CS::SetProtocolSettingsFromConfigStoreData",
          v5,
          " Failed copying string property \n");
      goto LABEL_48;
    }
    v14 = 0;
  }
  v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
         a2,
         L"protocolManagerDllInitFunction",
         &v14,
         0,
         0);
  if ( v5 >= 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    {
      if ( v14 )
        v10 = v14;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_cs.cxx",
        157,
        "PROTOCOL_DATA_OBJECT_CS::SetProtocolSettingsFromConfigStoreData",
        " ProtocolManagerDllInitFunction = '%s' \n",
        (const char *)v10);
    }
    if ( v14 )
    {
      v5 = STRU::Copy((PROTOCOL_DATA_OBJECT_CS *)((char *)this + 216), v14);
      if ( v5 >= 0 )
      {
        v14 = 0;
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_cs.cxx",
          167,
          "PROTOCOL_DATA_OBJECT_CS::SetProtocolSettingsFromConfigStoreData",
          v5,
          " Failed copying string property \n");
      }
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_cs.cxx",
      149,
      "PROTOCOL_DATA_OBJECT_CS::SetProtocolSettingsFromConfigStoreData",
      v5,
      " Failed reading ProtocolManagerDllInitFunction property \n");
  }
LABEL_48:
  if ( v15 )
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v15 + 16LL))(v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005229c  mov     [rsp-28h+arg_0], rbx
0x1800522a1  push    rbp
0x1800522a2  push    rsi
0x1800522a3  push    rdi
0x1800522a4  push    r13
0x1800522a6  push    r14
0x1800522a8  mov     rbp, rsp
0x1800522ab  sub     rsp, 30h
0x1800522af  mov     rax, [rdx]
0x1800522b2  lea     r9, [rbp+arg_10]
0x1800522b6  mov     r14, rdx
0x1800522b9  mov     [rbp+arg_8], 0
0x1800522c1  mov     rsi, rcx
0x1800522c4  mov     [rbp+arg_10], 0
0x1800522cc  lea     r8, [rbp+arg_8]
0x1800522d0  mov     [rsp+30h+var_10], 0
0x1800522d9  mov     rax, [rax+40h]
0x1800522dd  lea     rdx, aIdentity; "identity"
0x1800522e4  mov     rcx, r14
0x1800522e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522ec  lea     r13, aProtocolDataOb_3; "PROTOCOL_DATA_OBJECT_CS::SetProtocolSet"...
0x1800522f3  mov     ebx, eax
0x1800522f5  test    eax, eax
0x1800522f7  jns     loc_180052420
0x1800522fd  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180052304  jz      short loc_180052333
0x180052306  mov     rcx, cs:g_pDebug
0x18005230d  lea     rax, aFailedReadingI; " Failed reading identity property \n"
0x180052314  mov     [rsp+30h+var_8], rax
0x180052319  lea     rdx, aServercommonIn_16; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180052320  mov     r9, r13
0x180052323  mov     dword ptr [rsp+30h+var_10], ebx
0x180052327  mov     r8d, 3Ah ; ':'
0x18005232d  call    cs:__imp_PuDbgPrintError
0x180052333  mov     ecx, 138h; Size
0x180052338  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005233d  test    rax, rax
0x180052340  jz      loc_1800523DD
0x180052346  mov     rcx, rax; this
0x180052349  call    ??0CONFIG_ERROR@@QEAA@XZ; CONFIG_ERROR::CONFIG_ERROR(void)
0x18005234e  mov     rdi, rax
0x180052351  test    rax, rax
0x180052354  jz      loc_1800523DD
0x18005235a  mov     r9, [rbp+arg_10]; struct INativePropertyException *
0x18005235e  lea     rdx, aIdentity; "identity"
0x180052365  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x180052369  mov     rcx, rax; this
0x18005236c  call    ?InitializeWithString@CONFIG_ERROR@@QEAAJPEBG0PEAVINativePropertyException@@@Z; CONFIG_ERROR::InitializeWithString(ushort const *,ushort const *,INativePropertyException *)
0x180052371  mov     ebx, eax
0x180052373  test    eax, eax
0x180052375  jns     short loc_1800523BA
0x180052377  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005237e  jz      short loc_1800523AD
0x180052380  mov     rcx, cs:g_pDebug
0x180052387  lea     rax, aErrorInitializ; " Error initializing config error object"...
0x18005238e  mov     [rsp+30h+var_8], rax
0x180052393  lea     rdx, aServercommonIn_16; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18005239a  mov     r9, r13
0x18005239d  mov     dword ptr [rsp+30h+var_10], ebx
0x1800523a1  mov     r8d, 4Eh ; 'N'
0x1800523a7  call    cs:__imp_PuDbgPrintError
0x1800523ad  mov     rcx, rdi; this
0x1800523b0  call    ?Dereference@CONFIG_ERROR@@QEAAXXZ; CONFIG_ERROR::Dereference(void)
0x1800523b5  jmp     loc_18005269F
0x1800523ba  lea     rcx, [rsi+110h]; this
0x1800523c1  mov     dword ptr [rdi+8], 51h ; 'Q'
0x1800523c8  mov     rdx, rdi; struct CONFIG_ERROR *
0x1800523cb  call    ?Add@CONFIG_ERROR_LIST@@QEAAXPEAVCONFIG_ERROR@@@Z; CONFIG_ERROR_LIST::Add(CONFIG_ERROR *)
0x1800523d0  lea     rdx, SourceString
0x1800523d7  mov     [rbp+arg_8], rdx
0x1800523db  jmp     short loc_180052424
0x1800523dd  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800523e4  jz      loc_18005269F
0x1800523ea  lea     rax, aOutOfMemoryCre; " Out of memory creating config error ob"...
0x1800523f1  mov     r8d, 42h ; 'B'
0x1800523f7  mov     [rsp+30h+var_8], rax
0x1800523fc  mov     dword ptr [rsp+30h+var_10], 8007000Eh
0x180052404  mov     rcx, cs:g_pDebug
0x18005240b  lea     rdx, aServercommonIn_16; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180052412  mov     r9, r13
0x180052415  call    cs:__imp_PuDbgPrintError
0x18005241b  jmp     loc_18005269F
0x180052420  mov     rdx, [rbp+arg_8]
0x180052424  mov     eax, cs:g_dwDebugFlags
0x18005242a  lea     rdi, aNull_0; "NULL"
0x180052431  test    al, 3
0x180052433  setnz   cl
0x180052436  bt      eax, 1Eh
0x18005243a  setb    al
0x18005243d  test    al, cl
0x18005243f  jz      short loc_18005247D
0x180052441  mov     rcx, cs:g_pDebug
0x180052448  test    rdx, rdx
0x18005244b  mov     rax, rdi
0x18005244e  mov     r9, r13
0x180052451  cmovnz  rax, rdx
0x180052455  mov     r8d, 5Dh ; ']'
0x18005245b  mov     [rsp+30h+var_8], rax
0x180052460  lea     rdx, aServercommonIn_16; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180052467  lea     rax, aIdentityS; " Identity = '%s' \n"
0x18005246e  mov     [rsp+30h+var_10], rax
0x180052473  call    cs:__imp_PuDbgPrint
0x180052479  mov     rdx, [rbp+arg_8]
0x18005247d  test    rdx, rdx
0x180052480  jz      short loc_1800524C2
0x180052482  lea     rcx, [rsi+68h]
0x180052486  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005248c  mov     ebx, eax
0x18005248e  test    eax, eax
0x180052490  jns     short loc_1800524BA
0x180052492  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180052499  jz      loc_18005269F
0x18005249f  lea     rax, aFailedCopyingS; " Failed copying string property \n"
0x1800524a6  mov     r8d, 67h ; 'g'
0x1800524ac  mov     [rsp+30h+var_8], rax
0x1800524b1  mov     dword ptr [rsp+30h+var_10], ebx
0x1800524b5  jmp     loc_180052404
0x1800524ba  mov     [rbp+arg_8], 0
0x1800524c2  mov     rax, [r14]
0x1800524c5  lea     r8, [rbp+arg_8]
0x1800524c9  xor     r9d, r9d
0x1800524cc  mov     [rsp+30h+var_10], 0
0x1800524d5  lea     rdx, aProtocolmanage_2; "protocolManagerDll"
0x1800524dc  mov     rcx, r14
0x1800524df  mov     rax, [rax+40h]
0x1800524e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800524e8  mov     ebx, eax
0x1800524ea  test    eax, eax
0x1800524ec  jns     short loc_180052516
0x1800524ee  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800524f5  jz      loc_18005269F
0x1800524fb  lea     rax, aFailedReadingP_0; " Failed reading protocolManagerDll prop"...
0x180052502  mov     r8d, 75h ; 'u'
0x180052508  mov     [rsp+30h+var_8], rax
0x18005250d  mov     dword ptr [rsp+30h+var_10], ebx
0x180052511  jmp     loc_180052404
0x180052516  mov     eax, cs:g_dwDebugFlags
0x18005251c  test    al, 3
0x18005251e  setnz   cl
0x180052521  bt      eax, 1Eh
0x180052525  setb    al
0x180052528  test    al, cl
0x18005252a  jz      short loc_180052568
0x18005252c  mov     rax, [rbp+arg_8]
0x180052530  lea     rdx, aServercommonIn_16; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180052537  test    rax, rax
0x18005253a  mov     rcx, rdi
0x18005253d  mov     r9, r13
0x180052540  mov     r8d, 7Dh ; '}'
0x180052546  cmovnz  rcx, rax
0x18005254a  lea     rax, aProtocolmanage_0; " ProtocolManagerDll = '%s' \n"
0x180052551  mov     [rsp+30h+var_8], rcx
0x180052556  mov     rcx, cs:g_pDebug
0x18005255d  mov     [rsp+30h+var_10], rax
0x180052562  call    cs:__imp_PuDbgPrint
0x180052568  mov     rdx, [rbp+arg_8]
0x18005256c  test    rdx, rdx
0x18005256f  jz      short loc_1800525B4
0x180052571  lea     rcx, [rsi+0A0h]
0x180052578  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005257e  mov     ebx, eax
0x180052580  test    eax, eax
0x180052582  jns     short loc_1800525AC
0x180052584  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005258b  jz      loc_18005269F
0x180052591  lea     rax, aFailedCopyingS; " Failed copying string property \n"
0x180052598  mov     r8d, 87h
0x18005259e  mov     [rsp+30h+var_8], rax
0x1800525a3  mov     dword ptr [rsp+30h+var_10], ebx
0x1800525a7  jmp     loc_180052404
0x1800525ac  mov     [rbp+arg_8], 0
0x1800525b4  mov     rax, [r14]
0x1800525b7  lea     r8, [rbp+arg_8]
0x1800525bb  xor     r9d, r9d
0x1800525be  mov     [rsp+30h+var_10], 0
0x1800525c7  lea     rdx, aProtocolmanage_1; "protocolManagerDllInitFunction"
0x1800525ce  mov     rcx, r14
0x1800525d1  mov     rax, [rax+40h]
0x1800525d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800525da  mov     ebx, eax
0x1800525dc  test    eax, eax
0x1800525de  jns     short loc_180052608
0x1800525e0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800525e7  jz      loc_18005269F
0x1800525ed  lea     rax, aFailedReadingP; " Failed reading ProtocolManagerDllInitF"...
0x1800525f4  mov     r8d, 95h
0x1800525fa  mov     [rsp+30h+var_8], rax
0x1800525ff  mov     dword ptr [rsp+30h+var_10], ebx
0x180052603  jmp     loc_180052404
0x180052608  mov     eax, cs:g_dwDebugFlags
0x18005260e  test    al, 3
0x180052610  setnz   cl
0x180052613  bt      eax, 1Eh
0x180052617  setb    al
0x18005261a  test    al, cl
0x18005261c  jz      short loc_180052657
0x18005261e  mov     rax, [rbp+arg_8]
0x180052622  lea     rdx, aServercommonIn_16; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180052629  mov     rcx, cs:g_pDebug
0x180052630  test    rax, rax
0x180052633  mov     r9, r13
0x180052636  mov     r8d, 9Dh
0x18005263c  cmovnz  rdi, rax
0x180052640  lea     rax, aProtocolmanage; " ProtocolManagerDllInitFunction = '%s' "...
0x180052647  mov     [rsp+30h+var_8], rdi
0x18005264c  mov     [rsp+30h+var_10], rax
0x180052651  call    cs:__imp_PuDbgPrint
0x180052657  mov     rdx, [rbp+arg_8]
0x18005265b  test    rdx, rdx
0x18005265e  jz      short loc_18005269F
0x180052660  lea     rcx, [rsi+0D8h]
0x180052667  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005266d  mov     ebx, eax
0x18005266f  test    eax, eax
0x180052671  jns     short loc_180052697
0x180052673  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005267a  jz      short loc_18005269F
0x18005267c  lea     rax, aFailedCopyingS; " Failed copying string property \n"
0x180052683  mov     r8d, 0A7h
0x180052689  mov     [rsp+30h+var_8], rax
0x18005268e  mov     dword ptr [rsp+30h+var_10], ebx
0x180052692  jmp     loc_180052404
0x180052697  mov     [rbp+arg_8], 0
0x18005269f  mov     rcx, [rbp+arg_10]
0x1800526a3  test    rcx, rcx
0x1800526a6  jz      short loc_1800526B4
0x1800526a8  mov     rax, [rcx]
0x1800526ab  mov     rax, [rax+10h]
0x1800526af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800526b4  mov     eax, ebx
0x1800526b6  mov     rbx, [rsp+30h+arg_0]
0x1800526bb  add     rsp, 30h
0x1800526bf  pop     r14
0x1800526c1  pop     r13
0x1800526c3  pop     rdi
0x1800526c4  pop     rsi
0x1800526c5  pop     rbp
0x1800526c6  retn
```
