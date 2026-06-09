# SaveSchema(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x1800120b4`
- end: `0x18001281e`
- name: `?SaveSchema@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `1898`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180012824`

## callees

- `0x180004290`
- `0x1800089c8`
- `0x180008a08`
- `0x180009b80`
- `0x180011320`
- `0x180011c74`
- `0x180011e74`
- `0x1800120b4`
- `0x180012938`
- `0x18001be0c`
- `0x18001be78`
- `0x1800231ec`
- `0x180027534`
- `0x18002d4fc`
- `0x18002d788`
- `0x18002da58`
- `0x18002db80`
- `0x18002f24c`
- `0x18002f998`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180012687`
- `KERNEL32!GetFileAttributesW` at `0x180012687`
- `KERNEL32!DeleteFileW` at `0x1800125cb`
- `KERNEL32!DeleteFileW` at `0x1800125cb`
- `KERNEL32!GetLastError` at `0x1800125d9`
- `KERNEL32!GetLastError` at `0x1800125d9`
- `IisRTL!PuDbgPrintW` at `0x18001215b`
- `IisRTL!PuDbgPrintW` at `0x180012256`
- `IisRTL!PuDbgPrintW` at `0x1800123a5`
- `IisRTL!PuDbgPrintW` at `0x18001240c`
- `IisRTL!PuDbgPrintW` at `0x180012466`
- `IisRTL!PuDbgPrintW` at `0x1800125b9`
- `IisRTL!PuDbgPrintW` at `0x180012630`
- `IisRTL!PuDbgPrintW` at `0x180012671`
- `IisRTL!PuDbgPrintW` at `0x1800126f5`
- `IisRTL!PuDbgPrintW` at `0x180012732`
- `IisRTL!PuDbgPrintW` at `0x18001277e`
- `IisRTL!PuDbgPrintW` at `0x18001215b`
- `IisRTL!PuDbgPrintW` at `0x180012256`
- `IisRTL!PuDbgPrintW` at `0x1800123a5`
- `IisRTL!PuDbgPrintW` at `0x18001240c`
- `IisRTL!PuDbgPrintW` at `0x180012466`
- `IisRTL!PuDbgPrintW` at `0x1800125b9`
- `IisRTL!PuDbgPrintW` at `0x180012630`
- `IisRTL!PuDbgPrintW` at `0x180012671`
- `IisRTL!PuDbgPrintW` at `0x1800126f5`
- `IisRTL!PuDbgPrintW` at `0x180012732`
- `IisRTL!PuDbgPrintW` at `0x18001277e`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x180012114`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x180012114`

## string_xrefs

- `0x18001224a`: `[SaveSchema] Initializing writer with write file: %s bin file: %s.\n`
- `0x18001213a`: `[SaveSchema] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n`
- `0x1800121a3`: `[SaveSchema] QueryInterface on compiler failed with hr = 0x%x.\n`
- `0x18001280c`: `[SaveSchema] Unable to open /Schema. GetChildObject failed with hr = 0x%x.\n`
- `0x1800127e6`: `[SaveSchema] Unable to open /Schema/Properties. GetChildObject failed with hr = 0x%x.\n`
- `0x1800127c6`: `[SaveSchema] Error while saving schema tree. Cannot initialize writer. Failed with hr = 0x%x.\n`
- `0x180012384`: `[SaveSchema] Error while saving schema tree. CWriter::BeginWrite failed with hr = 0x%x.\n`
- `0x180012509`: `[SaveSchema] Error while saving schema tree. CMBSchemaWriter::WriteSchema. Failed with hr = 0x%x.\n`
- `0x180012542`: `[SaveSchema] Error while saving schema tree. CWriter::EndWrite Failed with hr = 0x%x.\n`
- `0x1800125ad`: `[SaveSchema] CompileSchema from %s failed with hr = 0x%x.\n`
- `0x180012624`: `[CompileIfNeeded] Compile from schema extensions file: %s succeeded, but cannot cleanup the extensions file:%s. Delete file failed with hr = 0x%x.\n`
- `0x180012651`: `[SaveSchema] No extensions found. - Either schema tree was changed, but no extensions added, or all extensions were deleted.\n`
- `0x18001270d`: `[SaveSchema] Compiling from schema file %s\n`
- `0x18001275e`: `[SaveSchema] Schema file not found. Compiling from shipped schema\n`
- `0x180012454`: `[CompileIfNeeded] UpdateTimeStamp failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall SaveSchema(unsigned __int16 *a1, struct _SECURITY_ATTRIBUTES *a2)
{
  _QWORD *v2; // rdi
  unsigned __int16 *v4; // r15
  struct CMBSchemaWriter *v5; // r14
  int SimpleObjectByIDEx; // eax
  unsigned int v7; // edx
  int GlobalHelper; // ebx
  int v9; // eax
  CMDBaseObject *ChildObject; // rax
  struct CMDBaseObject *v11; // r12
  struct CMDBaseObject *v12; // rax
  struct CMDBaseObject *v13; // r15
  const CHAR *v14; // rcx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int updated; // eax
  __int64 i; // r15
  int v22; // eax
  int v23; // eax
  signed int LastError; // eax
  __int64 v25; // [rsp+28h] [rbp-38h]
  __int64 v26; // [rsp+30h] [rbp-30h]
  struct IMetabaseSchemaCompiler *v27; // [rsp+40h] [rbp-20h] BYREF
  __int64 v28; // [rsp+48h] [rbp-18h] BYREF
  char *v29; // [rsp+50h] [rbp-10h] BYREF
  char *v30; // [rsp+58h] [rbp-8h] BYREF
  struct CMBCollectionWriter *v32; // [rsp+B0h] [rbp+50h] BYREF
  struct CMBSchemaWriter *v33; // [rsp+B8h] [rbp+58h] BYREF

  v2 = 0;
  v29 = (char *)L"Schema";
  v28 = 0;
  v4 = a1;
  v27 = 0;
  v5 = 0;
  v33 = 0;
  v30 = (char *)L"Properties";
  SimpleObjectByIDEx = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, &v28, L"IIS");
  GlobalHelper = SimpleObjectByIDEx;
  if ( SimpleObjectByIDEx < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
        226,
        "SaveSchema",
        L"[SaveSchema] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n",
        SimpleObjectByIDEx);
    goto LABEL_26;
  }
  v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IMetabaseSchemaCompiler **))v28)(
         v28,
         &IID_IMetabaseSchemaCompiler,
         &v27);
  LODWORD(v32) = v9;
  GlobalHelper = v9;
  if ( v9 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
        236,
        "SaveSchema",
        L"[SaveSchema] QueryInterface on compiler failed with hr = 0x%x.\n",
        v9);
    goto LABEL_26;
  }
  ChildObject = CMDBaseObject::GetChildObject(g_pboMasterRoot, &v29, (int *)&v32, 1);
  GlobalHelper = (int)v32;
  v11 = ChildObject;
  if ( (int)v32 < 0 || !ChildObject )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
        252,
        "SaveSchema",
        L"[SaveSchema] Unable to open /Schema. GetChildObject failed with hr = 0x%x.\n",
        (_DWORD)v32);
    goto LABEL_26;
  }
  v12 = CMDBaseObject::GetChildObject(ChildObject, &v30, (int *)&v32, 1);
  GlobalHelper = (int)v32;
  v13 = v12;
  if ( (int)v32 < 0 || !v12 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
        264,
        "SaveSchema",
        L"[SaveSchema] Unable to open /Schema/Properties. GetChildObject failed with hr = 0x%x.\n",
        (_DWORD)v32);
    goto LABEL_25;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
      276,
      "SaveSchema",
      L"[SaveSchema] Initializing writer with write file: %s bin file: %s.\n",
      g_wszSchemaExtensionFile,
      *((_QWORD *)g_pGlobalISTHelper + 31));
  v2 = operator new(0x10050u);
  if ( !v2 )
  {
    GlobalHelper = -2147024882;
    v2 = 0;
    v15 = -2147024882;
LABEL_78:
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v25) = v15;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
        310,
        "SaveSchema",
        L"[SaveSchema] Error while saving schema tree. Cannot initialize writer. Failed with hr = 0x%x.\n",
        v25);
    }
    goto LABEL_25;
  }
  v14 = (const CHAR *)g_wszSchemaExtensionFile;
  *v2 = 0;
  v2[8199] = -1;
  v2[1] = 0;
  v2[8200] = 0;
  v2[8201] = 0;
  *((_DWORD *)v2 + 4) = 0;
  v2[8195] = 0;
  v2[8196] = 0;
  v2[8197] = 0;
  v2[8198] = 0;
  ResetFileAttributesIfNeeded(v14, 1);
  v15 = CWriter::Initialize((CWriter *)v2, g_wszSchemaExtensionFile, g_pGlobalISTHelper, 0);
  GlobalHelper = v15;
  if ( v15 < 0 )
    goto LABEL_78;
  v32 = 0;
  GlobalHelper = SaveNames(v13, (struct CWriter *)v2, &v33, &v32);
  if ( GlobalHelper >= 0 )
  {
    GlobalHelper = SaveTypes(v13, (struct CWriter *)v2, &v33, &v32);
    if ( GlobalHelper >= 0 )
      GlobalHelper = SaveDefaults(v13, (struct CWriter *)v2, &v33, &v32);
  }
  if ( GlobalHelper < 0 )
  {
    v5 = v33;
    goto LABEL_35;
  }
  v16 = CreateNonIISConfigObjectCollections(v11, (struct CWriter *)v2, &v33);
  v5 = v33;
  GlobalHelper = v16;
  if ( v16 < 0 )
    goto LABEL_25;
  if ( v33 )
  {
    v17 = CWriter::BeginWrite(v2, 0, a2);
    GlobalHelper = v17;
    if ( v17 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v25) = v17;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
          353,
          "SaveSchema",
          L"[SaveSchema] Error while saving schema tree. CWriter::BeginWrite failed with hr = 0x%x.\n",
          v25);
      }
LABEL_25:
      v4 = a1;
      goto LABEL_26;
    }
    GlobalHelper = 0;
    for ( i = 0; (unsigned int)i < *((_DWORD *)v5 + 3); i = (unsigned int)(i + 1) )
    {
      GlobalHelper = CMBCollectionWriter::WriteCollection(*(CMBCollectionWriter **)(*(_QWORD *)v5 + 8 * i));
      if ( GlobalHelper < 0 )
        break;
    }
    if ( GlobalHelper < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v25) = GlobalHelper;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
          362,
          "SaveSchema",
          L"[SaveSchema] Error while saving schema tree. CMBSchemaWriter::WriteSchema. Failed with hr = 0x%x.\n",
          v25);
      }
      goto LABEL_25;
    }
    v22 = CWriter::EndWrite(v2, 0);
    GlobalHelper = v22;
    if ( v22 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v25) = v22;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
          372,
          "SaveSchema",
          L"[SaveSchema] Error while saving schema tree. CWriter::EndWrite Failed with hr = 0x%x.\n",
          v25);
      }
      goto LABEL_25;
    }
    CWriter::`scalar deleting destructor'((CWriter *)v2, v7);
    v4 = a1;
    v2 = 0;
    v23 = CompileIntoBin(v27, g_wszSchemaExtensionFile, a1);
    GlobalHelper = v23;
    if ( v23 >= 0 )
    {
      if ( !DeleteFileW(g_wszSchemaExtensionFile) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
            407,
            "SaveSchema",
            L"[CompileIfNeeded] Compile from schema extensions file: %s succeeded, but cannot cleanup the extensions file:"
             "%s. Delete file failed with hr = 0x%x.\n",
            g_wszSchemaExtensionFile,
            g_wszSchemaExtensionFile,
            LastError);
        GlobalHelper = 0;
      }
      goto LABEL_26;
    }
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v26) = v23;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
        395,
        "SaveSchema",
        L"[SaveSchema] CompileSchema from %s failed with hr = 0x%x.\n",
        g_wszSchemaExtensionFile,
        v26);
    }
    goto LABEL_65;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
      419,
      "SaveSchema",
      L"[SaveSchema] No extensions found. - Either schema tree was changed, but no extensions added, or all extensions were deleted.\n");
    v4 = a1;
LABEL_65:
    if ( v5 && GetFileAttributesW(v4) != -1 )
    {
      if ( g_pGlobalISTHelper )
        goto LABEL_26;
      GlobalHelper = GetGlobalHelper(1, &g_pGlobalISTHelper);
      if ( GlobalHelper >= 0 )
        goto LABEL_26;
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v25) = GlobalHelper;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
          456,
          "SaveSchema",
          L"[SaveSchema] Unable to get the the bin file name. (Assuming file missing or invalid). InitializeGlobalISTHelpe"
           "r failed with hr = 0x%x.\n",
          v25);
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
            472,
            "SaveSchema",
            L"[SaveSchema] Compiling from schema file %s\n",
            v4);
      }
      GlobalHelper = CompileIntoBinFromSchemaFile(v27, v4);
      if ( GlobalHelper >= 0 )
        goto LABEL_26;
    }
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
        491,
        "SaveSchema",
        L"[SaveSchema] Schema file not found. Compiling from shipped schema\n");
  }
  v4 = a1;
  GlobalHelper = CompileIntoBin(v27, 0, a1);
LABEL_26:
  if ( GlobalHelper >= 0 )
  {
    if ( !g_pGlobalISTHelper )
    {
      v18 = GetGlobalHelper(1, &g_pGlobalISTHelper);
      GlobalHelper = v18;
      if ( v18 < 0 && (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v25) = v18;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
          510,
          "SaveSchema",
          L"[SaveSchema] Unable to get the the bin file name. (Assuming file is invalid). InitializeGlobalISTHelper failed"
           " with hr = 0x%x.\n",
          v25);
      }
    }
    if ( GlobalHelper >= 0 )
    {
      updated = UpdateTimeStamp(v4, *((unsigned __int16 **)g_pGlobalISTHelper + 31));
      GlobalHelper = updated;
      if ( updated < 0 && (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v25) = updated;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
          522,
          "SaveSchema",
          L"[CompileIfNeeded] UpdateTimeStamp failed with hr = 0x%x.\n",
          v25);
      }
    }
  }
LABEL_35:
  if ( v5 )
  {
    CMBSchemaWriter::~CMBSchemaWriter(v5);
    operator delete(v5);
  }
  if ( v2 )
    CWriter::`scalar deleting destructor'((CWriter *)v2, v7);
  if ( v27 )
    (*(void (__fastcall **)(struct IMetabaseSchemaCompiler *))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  return (unsigned int)GlobalHelper;
}

```

## disassembly

```asm
0x1800120b4  mov     [rsp-38h+arg_8], rbx
0x1800120b9  mov     [rsp-38h+lpFileName], rcx
0x1800120be  push    rbp
0x1800120bf  push    rsi
0x1800120c0  push    rdi
0x1800120c1  push    r12
0x1800120c3  push    r13
0x1800120c5  push    r14
0x1800120c7  push    r15
0x1800120c9  mov     rbp, rsp
0x1800120cc  sub     rsp, 60h
0x1800120d0  xor     edi, edi
0x1800120d2  lea     rax, aSchema_4; "Schema"
0x1800120d9  mov     [rbp+var_10], rax
0x1800120dd  lea     r9, aIis; "IIS"
0x1800120e4  mov     r13, rdx
0x1800120e7  mov     [rbp+var_18], rdi
0x1800120eb  mov     r15, rcx
0x1800120ee  mov     [rbp+var_20], rdi
0x1800120f2  lea     rax, aProperties; "Properties"
0x1800120f9  xor     r14d, r14d
0x1800120fc  lea     esi, [rdi+1]
0x1800120ff  mov     [rbp+arg_18], r14
0x180012103  mov     ecx, esi
0x180012105  mov     [rbp+var_8], rax
0x180012109  lea     r8, [rbp+var_18]
0x18001210d  lea     rdx, IID_ISimpleTableDispenser2
0x180012114  call    cs:__imp_DllGetSimpleObjectByIDEx
0x18001211a  mov     ebx, eax
0x18001211c  test    eax, eax
0x18001211e  jns     short loc_180012166
0x180012120  mov     sil, 3
0x180012123  test    byte ptr cs:g_dwDebugFlags, sil
0x18001212a  jz      loc_1800123AF
0x180012130  mov     dword ptr [rsp+60h+var_38], eax
0x180012134  mov     r8d, 0E2h
0x18001213a  lea     rax, aSaveschemaDllg; "[SaveSchema] DllGetSimpleObjectByIDEx f"...
0x180012141  mov     rcx, cs:g_pDebug
0x180012148  lea     r9, aSaveschema; "SaveSchema"
0x18001214f  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x180012156  mov     [rsp+60h+var_40], rax
0x18001215b  call    cs:__imp_PuDbgPrintW
0x180012161  jmp     loc_1800123AF
0x180012166  mov     rcx, [rbp+var_18]
0x18001216a  lea     r8, [rbp+var_20]
0x18001216e  lea     rdx, IID_IMetabaseSchemaCompiler
0x180012175  mov     rax, [rcx]
0x180012178  mov     rax, [rax]
0x18001217b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012180  mov     dword ptr [rbp+arg_10], eax
0x180012183  mov     ebx, eax
0x180012185  test    eax, eax
0x180012187  jns     short loc_1800121AC
0x180012189  mov     sil, 3
0x18001218c  test    byte ptr cs:g_dwDebugFlags, sil
0x180012193  jz      loc_1800123AF
0x180012199  mov     dword ptr [rsp+60h+var_38], eax
0x18001219d  mov     r8d, 0ECh
0x1800121a3  lea     rax, aSaveschemaQuer; "[SaveSchema] QueryInterface on compiler"...
0x1800121aa  jmp     short loc_180012141
0x1800121ac  mov     rcx, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; this
0x1800121b3  lea     r8, [rbp+arg_10]; int *
0x1800121b7  mov     r9d, esi; int
0x1800121ba  lea     rdx, [rbp+var_10]; char **
0x1800121be  call    ?GetChildObject@CMDBaseObject@@QEAAPEAV1@AEAPEADPEAJH@Z; CMDBaseObject::GetChildObject(char * &,long *,int)
0x1800121c3  mov     ebx, dword ptr [rbp+arg_10]
0x1800121c6  mov     r12, rax
0x1800121c9  test    ebx, ebx
0x1800121cb  js      loc_1800127F8
0x1800121d1  test    rax, rax
0x1800121d4  jz      loc_1800127F8
0x1800121da  mov     r9d, esi; int
0x1800121dd  lea     r8, [rbp+arg_10]; int *
0x1800121e1  lea     rdx, [rbp+var_8]; char **
0x1800121e5  mov     rcx, rax; this
0x1800121e8  call    ?GetChildObject@CMDBaseObject@@QEAAPEAV1@AEAPEADPEAJH@Z; CMDBaseObject::GetChildObject(char * &,long *,int)
0x1800121ed  mov     ebx, dword ptr [rbp+arg_10]
0x1800121f0  mov     r15, rax
0x1800121f3  test    ebx, ebx
0x1800121f5  js      loc_1800127D2
0x1800121fb  test    rax, rax
0x1800121fe  jz      loc_1800127D2
0x180012204  mov     sil, 3
0x180012207  test    byte ptr cs:g_dwDebugFlags, sil
0x18001220e  jz      short loc_18001225C
0x180012210  mov     rax, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x180012217  lea     r9, aSaveschema; "SaveSchema"
0x18001221e  mov     r8d, 114h
0x180012224  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x18001222b  mov     rcx, [rax+0F8h]
0x180012232  mov     rax, cs:?g_wszSchemaExtensionFile@@3PEAGEA; ushort * g_wszSchemaExtensionFile
0x180012239  mov     [rsp+60h+var_30], rcx
0x18001223e  mov     rcx, cs:g_pDebug
0x180012245  mov     [rsp+60h+var_38], rax
0x18001224a  lea     rax, aSaveschemaInit; "[SaveSchema] Initializing writer with w"...
0x180012251  mov     [rsp+60h+var_40], rax
0x180012256  call    cs:__imp_PuDbgPrintW
0x18001225c  mov     ecx, 10050h; Size
0x180012261  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012266  mov     rdi, rax
0x180012269  xor     eax, eax
0x18001226b  test    rdi, rdi
0x18001226e  jz      loc_1800127A6
0x180012274  mov     rcx, cs:?g_wszSchemaExtensionFile@@3PEAGEA; lpFileName
0x18001227b  lea     edx, [rax+1]; int
0x18001227e  mov     [rdi], rax
0x180012281  mov     qword ptr [rdi+10038h], 0FFFFFFFFFFFFFFFFh
0x18001228c  mov     [rdi+8], rax
0x180012290  mov     [rdi+10040h], rax
0x180012297  mov     [rdi+10048h], rax
0x18001229e  mov     [rdi+10h], eax
0x1800122a1  mov     [rdi+10018h], rax
0x1800122a8  mov     [rdi+10020h], rax
0x1800122af  mov     [rdi+10028h], rax
0x1800122b6  mov     [rdi+10030h], rax
0x1800122bd  call    ?ResetFileAttributesIfNeeded@@YAXPEADH@Z; ResetFileAttributesIfNeeded(char *,int)
0x1800122c2  mov     r8, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; struct CWriterGlobalHelper *
0x1800122c9  xor     r9d, r9d; void *
0x1800122cc  mov     rdx, cs:?g_wszSchemaExtensionFile@@3PEAGEA; unsigned __int16 *
0x1800122d3  mov     rcx, rdi; this
0x1800122d6  call    ?Initialize@CWriter@@QEAAJPEBGPEAVCWriterGlobalHelper@@PEAX@Z; CWriter::Initialize(ushort const *,CWriterGlobalHelper *,void *)
0x1800122db  mov     ebx, eax
0x1800122dd  test    eax, eax
0x1800122df  js      loc_1800127AF
0x1800122e5  lea     r9, [rbp+arg_10]; struct CMBCollectionWriter **
0x1800122e9  mov     [rbp+arg_10], r14
0x1800122ed  lea     r8, [rbp+arg_18]; struct CMBSchemaWriter **
0x1800122f1  mov     rdx, rdi; struct CWriter *
0x1800122f4  mov     rcx, r15; struct CMDBaseObject *
0x1800122f7  call    ?SaveNames@@YAJPEAVCMDBaseObject@@PEAVCWriter@@PEAPEAVCMBSchemaWriter@@PEAPEAVCMBCollectionWriter@@@Z; SaveNames(CMDBaseObject *,CWriter *,CMBSchemaWriter * *,CMBCollectionWriter * *)
0x1800122fc  mov     ebx, eax
0x1800122fe  test    eax, eax
0x180012300  js      short loc_180012330
0x180012302  lea     r9, [rbp+arg_10]; struct CMBCollectionWriter **
0x180012306  mov     rdx, rdi; struct CWriter *
0x180012309  lea     r8, [rbp+arg_18]; struct CMBSchemaWriter **
0x18001230d  mov     rcx, r15; struct CMDBaseObject *
0x180012310  call    ?SaveTypes@@YAJPEAVCMDBaseObject@@PEAVCWriter@@PEAPEAVCMBSchemaWriter@@PEAPEAVCMBCollectionWriter@@@Z; SaveTypes(CMDBaseObject *,CWriter *,CMBSchemaWriter * *,CMBCollectionWriter * *)
0x180012315  mov     ebx, eax
0x180012317  test    eax, eax
0x180012319  js      short loc_180012330
0x18001231b  lea     r9, [rbp+arg_10]; struct CMBCollectionWriter **
0x18001231f  mov     rdx, rdi; struct CWriter *
0x180012322  lea     r8, [rbp+arg_18]; struct CMBSchemaWriter **
0x180012326  mov     rcx, r15; struct CMDBaseObject *
0x180012329  call    ?SaveDefaults@@YAJPEAVCMDBaseObject@@PEAVCWriter@@PEAPEAVCMBSchemaWriter@@PEAPEAVCMBCollectionWriter@@@Z; SaveDefaults(CMDBaseObject *,CWriter *,CMBSchemaWriter * *,CMBCollectionWriter * *)
0x18001232e  mov     ebx, eax
0x180012330  test    ebx, ebx
0x180012332  js      loc_18001279D
0x180012338  lea     r8, [rbp+arg_18]; struct CMBSchemaWriter **
0x18001233c  mov     rdx, rdi; struct CWriter *
0x18001233f  mov     rcx, r12; struct CMDBaseObject *
0x180012342  call    ?CreateNonIISConfigObjectCollections@@YAJPEAVCMDBaseObject@@PEAVCWriter@@PEAPEAVCMBSchemaWriter@@@Z; CreateNonIISConfigObjectCollections(CMDBaseObject *,CWriter *,CMBSchemaWriter * *)
0x180012347  mov     r14, [rbp+arg_18]
0x18001234b  mov     ebx, eax
0x18001234d  test    eax, eax
0x18001234f  js      short loc_1800123AB
0x180012351  test    r14, r14
0x180012354  jz      loc_18001263D
0x18001235a  mov     r8, r13
0x18001235d  xor     edx, edx
0x18001235f  mov     rcx, rdi
0x180012362  call    ?BeginWrite@CWriter@@QEAAJW4eWriter@@PEAU_SECURITY_ATTRIBUTES@@@Z; CWriter::BeginWrite(eWriter,_SECURITY_ATTRIBUTES *)
0x180012367  mov     ebx, eax
0x180012369  test    eax, eax
0x18001236b  jns     loc_1800124D2
0x180012371  test    byte ptr cs:g_dwDebugFlags, sil
0x180012378  jz      short loc_1800123AB
0x18001237a  mov     dword ptr [rsp+60h+var_38], eax
0x18001237e  mov     r8d, 161h
0x180012384  lea     rax, aSaveschemaErro_5; "[SaveSchema] Error while saving schema "...
0x18001238b  mov     rcx, cs:g_pDebug
0x180012392  lea     r9, aSaveschema; "SaveSchema"
0x180012399  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x1800123a0  mov     [rsp+60h+var_40], rax
0x1800123a5  call    cs:__imp_PuDbgPrintW
0x1800123ab  mov     r15, [rbp+lpFileName]
0x1800123af  test    ebx, ebx
0x1800123b1  js      loc_18001246C
0x1800123b7  cmp     cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA, 0; CWriterGlobalHelper * g_pGlobalISTHelper
0x1800123bf  jnz     short loc_180012412
0x1800123c1  lea     rdx, ?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; struct CWriterGlobalHelper **
0x1800123c8  mov     ecx, 1; int
0x1800123cd  call    ?GetGlobalHelper@@YAJHPEAPEAVCWriterGlobalHelper@@@Z; GetGlobalHelper(int,CWriterGlobalHelper * *)
0x1800123d2  mov     ebx, eax
0x1800123d4  test    eax, eax
0x1800123d6  jns     short loc_180012412
0x1800123d8  test    byte ptr cs:g_dwDebugFlags, sil
0x1800123df  jz      short loc_180012412
0x1800123e1  mov     rcx, cs:g_pDebug
0x1800123e8  lea     r9, aSaveschema; "SaveSchema"
0x1800123ef  mov     dword ptr [rsp+60h+var_38], eax
0x1800123f3  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x1800123fa  lea     rax, aSaveschemaUnab_0; "[SaveSchema] Unable to get the the bin "...
0x180012401  mov     r8d, 1FEh
0x180012407  mov     [rsp+60h+var_40], rax
0x18001240c  call    cs:__imp_PuDbgPrintW
0x180012412  test    ebx, ebx
0x180012414  js      short loc_18001246C
0x180012416  mov     rdx, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x18001241d  mov     rcx, r15; unsigned __int16 *
0x180012420  mov     rdx, [rdx+0F8h]; unsigned __int16 *
0x180012427  call    ?UpdateTimeStamp@@YAJPEAG0@Z; UpdateTimeStamp(ushort *,ushort *)
0x18001242c  mov     ebx, eax
0x18001242e  test    eax, eax
0x180012430  jns     short loc_18001246C
0x180012432  test    byte ptr cs:g_dwDebugFlags, sil
0x180012439  jz      short loc_18001246C
0x18001243b  mov     rcx, cs:g_pDebug
0x180012442  lea     r9, aSaveschema; "SaveSchema"
0x180012449  mov     dword ptr [rsp+60h+var_38], eax
0x18001244d  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x180012454  lea     rax, aCompileifneede_5; "[CompileIfNeeded] UpdateTimeStamp faile"...
0x18001245b  mov     r8d, 20Ah
0x180012461  mov     [rsp+60h+var_40], rax
0x180012466  call    cs:__imp_PuDbgPrintW
0x18001246c  test    r14, r14
0x18001246f  jz      short loc_180012481
0x180012471  mov     rcx, r14; this
0x180012474  call    ??1CMBSchemaWriter@@QEAA@XZ; CMBSchemaWriter::~CMBSchemaWriter(void)
0x180012479  mov     rcx, r14; Block
0x18001247c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012481  test    rdi, rdi
0x180012484  jz      short loc_18001248E
0x180012486  mov     rcx, rdi; this
0x180012489  call    ??_GCWriter@@QEAAPEAXI@Z; CWriter::`scalar deleting destructor'(uint)
0x18001248e  mov     rcx, [rbp+var_20]
0x180012492  test    rcx, rcx
0x180012495  jz      short loc_1800124A3
0x180012497  mov     rax, [rcx]
0x18001249a  mov     rax, [rax+10h]
0x18001249e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124a3  mov     rcx, [rbp+var_18]
0x1800124a7  test    rcx, rcx
0x1800124aa  jz      short loc_1800124B8
0x1800124ac  mov     rax, [rcx]
0x1800124af  mov     rax, [rax+10h]
0x1800124b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124b8  mov     eax, ebx
0x1800124ba  mov     rbx, [rsp+60h+arg_8]
0x1800124c2  add     rsp, 60h
0x1800124c6  pop     r15
0x1800124c8  pop     r14
0x1800124ca  pop     r13
0x1800124cc  pop     r12
0x1800124ce  pop     rdi
0x1800124cf  pop     rsi
0x1800124d0  pop     rbp
0x1800124d1  retn
0x1800124d2  xor     ebx, ebx
0x1800124d4  xor     r15d, r15d
0x1800124d7  cmp     r15d, [r14+0Ch]
0x1800124db  jnb     short loc_1800124F4
0x1800124dd  mov     rcx, [r14]
0x1800124e0  mov     rcx, [rcx+r15*8]; this
0x1800124e4  call    ?WriteCollection@CMBCollectionWriter@@QEAAJXZ; CMBCollectionWriter::WriteCollection(void)
0x1800124e9  mov     ebx, eax
0x1800124eb  test    eax, eax
0x1800124ed  js      short loc_1800124F4
0x1800124ef  inc     r15d
0x1800124f2  jmp     short loc_1800124D7
0x1800124f4  test    ebx, ebx
0x1800124f6  jns     short loc_18001251B
0x1800124f8  test    byte ptr cs:g_dwDebugFlags, sil
0x1800124ff  jz      loc_1800123AB
0x180012505  mov     dword ptr [rsp+60h+var_38], ebx
0x180012509  lea     rax, aSaveschemaErro_4; "[SaveSchema] Error while saving schema "...
0x180012510  mov     r8d, 16Ah
0x180012516  jmp     loc_18001238B
0x18001251b  xor     edx, edx
0x18001251d  mov     rcx, rdi
0x180012520  call    ?EndWrite@CWriter@@QEAAJW4eWriter@@@Z; CWriter::EndWrite(eWriter)
0x180012525  mov     ebx, eax
0x180012527  test    eax, eax
0x180012529  jns     short loc_18001254E
0x18001252b  test    byte ptr cs:g_dwDebugFlags, sil
0x180012532  jz      loc_1800123AB
0x180012538  mov     dword ptr [rsp+60h+var_38], eax
0x18001253c  mov     r8d, 174h
0x180012542  lea     rax, aSaveschemaErro; "[SaveSchema] Error while saving schema "...
0x180012549  jmp     loc_18001238B
0x18001254e  mov     rcx, rdi; this
0x180012551  call    ??_GCWriter@@QEAAPEAXI@Z; CWriter::`scalar deleting destructor'(uint)
0x180012556  mov     r15, [rbp+lpFileName]
0x18001255a  xor     edi, edi
0x18001255c  mov     rdx, cs:?g_wszSchemaExtensionFile@@3PEAGEA; unsigned __int16 *
0x180012563  mov     r8, r15; unsigned __int16 *
0x180012566  mov     rcx, [rbp+var_20]; struct IMetabaseSchemaCompiler *
0x18001256a  call    ?CompileIntoBin@@YAJPEAUIMetabaseSchemaCompiler@@PEBG1@Z; CompileIntoBin(IMetabaseSchemaCompiler *,ushort const *,ushort const *)
0x18001256f  mov     ebx, eax
0x180012571  test    eax, eax
0x180012573  jns     short loc_1800125C4
0x180012575  test    byte ptr cs:g_dwDebugFlags, sil
0x18001257c  jz      loc_18001267B
0x180012582  mov     rcx, cs:g_pDebug
0x180012589  lea     r9, aSaveschema; "SaveSchema"
0x180012590  mov     dword ptr [rsp+60h+var_30], eax
0x180012594  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x18001259b  mov     rax, cs:?g_wszSchemaExtensionFile@@3PEAGEA; ushort * g_wszSchemaExtensionFile
0x1800125a2  mov     r8d, 18Bh
  ... truncated ...
```
