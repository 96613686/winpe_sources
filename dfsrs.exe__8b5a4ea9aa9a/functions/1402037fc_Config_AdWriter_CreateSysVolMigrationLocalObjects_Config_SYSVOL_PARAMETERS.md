# Config::AdWriter::CreateSysVolMigrationLocalObjects(Config::SYSVOL_PARAMETERS &)

- ea: `0x1402037fc`
- end: `0x140203cfb`
- name: `?CreateSysVolMigrationLocalObjects@AdWriter@Config@@QEAAPEAVFrsStatus@@AEAUSYSVOL_PARAMETERS@2@@Z`
- size: `1279`
- prototype: `struct FrsStatus *__fastcall(Config::AdWriter *__hidden this, struct Config::SYSVOL_PARAMETERS *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1401f794c`

## callees

- `0x14000c910`
- `0x14000cd1c`
- `0x14001e104`
- `0x14001ecc8`
- `0x1401b9494`
- `0x1401de2f8`
- `0x1401de4ec`
- `0x1401de8d0`
- `0x1401e2e2c`
- `0x1401e56f0`
- `0x1401e6058`
- `0x1401e8aa4`
- `0x1401eaaac`
- `0x1402000f8`
- `0x14020174c`
- `0x140202a50`
- `0x140203318`
- `0x1402037fc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140203a79`
- `KERNEL32!GetCurrentThreadId` at `0x140203b77`
- `KERNEL32!GetCurrentThreadId` at `0x140203c49`
- `KERNEL32!GetCurrentThreadId` at `0x140203a79`
- `KERNEL32!GetCurrentThreadId` at `0x140203b77`
- `KERNEL32!GetCurrentThreadId` at `0x140203c49`

## string_xrefs

- `0x140203aa2`: `base\fs\remotefs\frs\src\ad\adwriter.cpp`
- `0x140203ba0`: `base\fs\remotefs\frs\src\ad\adwriter.cpp`
- `0x140203c72`: `base\fs\remotefs\frs\src\ad\adwriter.cpp`
- `0x140203871`: `[MIG] Create sysvol migration local objects`
- `0x14020392b`: `[SYSVOL] member object is created.`
- `0x140203832`: `Config::AdWriter::CreateSysVolMigrationLocalObjects`
- `0x140203981`: `Config::AdWriter::CreateSysVolMigrationLocalObjects`
- `0x140203a0b`: `Config::AdWriter::CreateSysVolMigrationLocalObjects`
- `0x140203b41`: `Config::AdWriter::CreateSysVolMigrationLocalObjects`
- `0x140203c13`: `Config::AdWriter::CreateSysVolMigrationLocalObjects`
- `0x140203a96`: `Config::AdWriter::CreateSysVolMigrationLocalObjects`
- `0x140203b94`: `Config::AdWriter::CreateSysVolMigrationLocalObjects`
- `0x140203c66`: `Config::AdWriter::CreateSysVolMigrationLocalObjects`
- `0x1402039b1`: `[SYSVOL] Cannot read RG AD object. Dn:%?`
- `0x140203a3b`: `[SYSVOL] Cannot read CS AD object. Dn:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct FrsStatus *__fastcall Config::AdWriter::CreateSysVolMigrationLocalObjects(
        Config::AdWriter *this,
        struct Config::SYSVOL_PARAMETERS *a2)
{
  __int64 v4; // rbx
  struct FrsStatus *Computer; // rdi
  Config::AdBinAttr **v6; // rsi
  Config::AdBinAttr **v7; // r14
  unsigned int v8; // edx
  struct Config::AdObject *v9; // r8
  DWORD v10; // eax
  __int64 v11; // rcx
  Config::AdBinAttr *v13; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v15; // rcx
  Config::AdBinAttr *v16; // rcx
  DWORD v17; // eax
  __int64 v18; // rcx
  struct FrsStatus *SysVolLocalObjectsOnAnyWritableDc; // rax
  const wchar_t *v20; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+58h] [rbp-A8h]
  int v22; // [rsp+5Ch] [rbp-A4h]
  const wchar_t *v23; // [rsp+60h] [rbp-A0h]
  const wchar_t *v24; // [rsp+68h] [rbp-98h] BYREF
  int v25; // [rsp+70h] [rbp-90h]
  int v26; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v27; // [rsp+78h] [rbp-88h]
  _BYTE v28[72]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v29; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v30; // [rsp+F8h] [rbp-8h]
  _BYTE v31[224]; // [rsp+110h] [rbp+10h] BYREF
  struct Config::AdObject *v32; // [rsp+200h] [rbp+100h] BYREF
  struct Config::AdObject *v33; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 *v34; // [rsp+218h] [rbp+118h] BYREF

  v4 = 0;
  Computer = 0;
  Config::AdSnapshot::AdSnapshot((Config::AdSnapshot *)v31, this);
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v20 = L"Config::AdWriter::CreateSysVolMigrationLocalObjects";
    v21 = 1852;
    v22 = 4;
    v23 = L"ADWR";
    dbgobj::DbgPrint<unsigned short>(&v20, L"[MIG] Create sysvol migration local objects");
  }
  if ( !*((_QWORD *)this + 13) )
    Computer = Config::AdConfig::GetComputer(this);
  v6 = 0;
  v32 = 0;
  v7 = 0;
  v33 = 0;
  Config::AdConfig::SYSVOL_OBJECTS::SYSVOL_OBJECTS((Config::AdConfig::SYSVOL_OBJECTS *)v28);
  if ( !Computer )
  {
    Computer = Config::AdConfig::ConstructSysVolObjects(this, (struct Config::AdConfig::SYSVOL_OBJECTS *)v28);
    if ( !Computer )
    {
      if ( !*(_DWORD *)(*((_QWORD *)this + 5) + 36LL) )
      {
        Computer = Config::AdWriter::CreateMemberObject(this, (const struct Config::AdConfig::SYSVOL_OBJECTS *)v28);
        if ( Computer )
          goto LABEL_28;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v20 = L"Config::AdWriter::CreateSysVolMigrationLocalObjects";
          v21 = 1881;
          v22 = 4;
          v23 = L"ADWR";
          dbgobj::DbgPrint<unsigned short>(&v20, L"[SYSVOL] member object is created.");
        }
      }
      Computer = Config::AdSnapshot::GetReplicaSet((Config::AdSnapshot *)v31, v29, 0, &v32);
      if ( Computer )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v20 = L"Config::AdWriter::CreateSysVolMigrationLocalObjects";
          v21 = 1892;
          v22 = 2;
          v23 = L"ADWR";
          v33 = (struct Config::AdObject *)v29;
          dbgobj::DbgPrint<unsigned short,unsigned short const *>(
            &v20,
            L"[SYSVOL] Cannot read RG AD object. Dn:%?",
            &v33);
        }
        v6 = (Config::AdBinAttr **)v32;
        goto LABEL_28;
      }
      Computer = Config::AdSnapshot::GetContentSet((Config::AdSnapshot *)v31, v30, v9, &v33);
      if ( Computer )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v20 = L"Config::AdWriter::CreateSysVolMigrationLocalObjects";
          v21 = 1904;
          v22 = 2;
          v23 = L"ADWR";
          v34 = v30;
          dbgobj::DbgPrint<unsigned short,unsigned short const *>(
            &v20,
            L"[SYSVOL] Cannot read CS AD object. Dn:%?",
            &v34);
        }
        v6 = (Config::AdBinAttr **)v32;
LABEL_27:
        v7 = (Config::AdBinAttr **)v33;
        goto LABEL_28;
      }
      v6 = (Config::AdBinAttr **)v32;
      v13 = (Config::AdBinAttr *)*((_QWORD *)v32 + 7);
      if ( v13 && Config::AdBinAttr::GetValue(v13) )
      {
        *((_OWORD *)a2 + 4) = *(_OWORD *)Config::AdBinAttr::GetValue(v6[7]);
      }
      else
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v24 = L"Config::AdWriter::CreateSysVolMigrationLocalObjects";
          v25 = 1917;
          v26 = 2;
          v27 = L"ADWR";
          dbgobj::DbgPrint<unsigned short>(&v24, L"[SYSVOL] Invalid Replication Group object, missing guid");
        }
        CurrentThreadId = GetCurrentThreadId();
        Computer = (struct FrsStatus *)FrsStatusList::PushNewError(
                                         v15,
                                         13,
                                         0,
                                         1,
                                         "base\\fs\\remotefs\\frs\\src\\ad\\adwriter.cpp",
                                         "Config::AdWriter::CreateSysVolMigrationLocalObjects",
                                         1918,
                                         CurrentThreadId,
                                         0);
        if ( Computer )
          goto LABEL_27;
      }
      v7 = (Config::AdBinAttr **)v33;
      v16 = (Config::AdBinAttr *)*((_QWORD *)v33 + 7);
      if ( v16 && Config::AdBinAttr::GetValue(v16) )
      {
        *((_OWORD *)a2 + 5) = *(_OWORD *)Config::AdBinAttr::GetValue(v7[7]);
LABEL_51:
        if ( *(_DWORD *)(*((_QWORD *)this + 5) + 36LL) )
        {
          LODWORD(v32) = 4;
          SysVolLocalObjectsOnAnyWritableDc = Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc(
                                                this,
                                                a2,
                                                (const struct Config::AdConfig::SYSVOL_OBJECTS *)v28,
                                                (const struct Config::AdObject *)v6,
                                                (const struct Config::AdObject *)v7,
                                                (const unsigned int *)&v32);
        }
        else
        {
          SysVolLocalObjectsOnAnyWritableDc = Config::AdWriter::CreateSysVolLocalObjectsOnLocalDc(
                                                this,
                                                a2,
                                                (const struct Config::AdConfig::SYSVOL_OBJECTS *)v28,
                                                (const struct Config::AdObject *)v6,
                                                (const struct Config::AdObject *)v7);
        }
        Computer = SysVolLocalObjectsOnAnyWritableDc;
        if ( !SysVolLocalObjectsOnAnyWritableDc )
          Computer = Migration::SysVolUtil::SetSysvolParametersIntoRegistry(a2);
        goto LABEL_28;
      }
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v24 = L"Config::AdWriter::CreateSysVolMigrationLocalObjects";
        v25 = 1927;
        v26 = 2;
        v27 = L"ADWR";
        dbgobj::DbgPrint<unsigned short>(&v24, L"[SYSVOL] Invalid Content Set object, missing guid");
      }
      v17 = GetCurrentThreadId();
      Computer = (struct FrsStatus *)FrsStatusList::PushNewError(
                                       v18,
                                       13,
                                       0,
                                       1,
                                       "base\\fs\\remotefs\\frs\\src\\ad\\adwriter.cpp",
                                       "Config::AdWriter::CreateSysVolMigrationLocalObjects",
                                       1928,
                                       v17,
                                       0);
      if ( !Computer )
        goto LABEL_51;
    }
  }
LABEL_28:
  if ( v6 )
    Config::AdObject::`scalar deleting destructor'((Config::AdObject *)v6, v8);
  if ( v7 )
    Config::AdObject::`scalar deleting destructor'((Config::AdObject *)v7, v8);
  if ( Computer )
  {
    v10 = GetCurrentThreadId();
    v4 = FrsStatusList::PushNewError(
           v11,
           *((unsigned int *)Computer + 1),
           *((unsigned int *)Computer + 2),
           *(unsigned int *)Computer,
           "base\\fs\\remotefs\\frs\\src\\ad\\adwriter.cpp",
           "Config::AdWriter::CreateSysVolMigrationLocalObjects",
           1964,
           v10,
           Computer);
  }
  Config::AdConfig::SYSVOL_OBJECTS::~SYSVOL_OBJECTS((Config::AdConfig::SYSVOL_OBJECTS *)v28);
  Config::AdSnapshot::~AdSnapshot((Config::AdSnapshot *)v31);
  return (struct FrsStatus *)v4;
}

```

## disassembly

```asm
0x1402037fc  mov     [rsp-8+arg_8], rbx
0x140203801  push    rbp
0x140203802  push    rsi
0x140203803  push    rdi
0x140203804  push    r12
0x140203806  push    r13
0x140203808  push    r14
0x14020380a  push    r15
0x14020380c  lea     rbp, [rsp-0C0h]
0x140203814  sub     rsp, 1C0h
0x14020381b  mov     r12, rdx
0x14020381e  mov     r13, rcx
0x140203821  xor     ebx, ebx
0x140203823  mov     edi, ebx
0x140203825  mov     rdx, rcx; struct Config::AdConfig *
0x140203828  lea     rcx, [rbp+0F0h+var_E0]; this
0x14020382c  call    ??0AdSnapshot@Config@@QEAA@PEBVAdConfig@1@@Z; Config::AdSnapshot::AdSnapshot(Config::AdConfig const *)
0x140203831  nop
0x140203832  lea     r15, aConfigAdwriter_25; "Config::AdWriter::CreateSysVolMigration"...
0x140203839  lea     rcx, aAdwr; "ADWR"
0x140203840  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140203847  test    rax, rax
0x14020384a  jz      short loc_140203882
0x14020384c  cmp     [rax+40h], ebx
0x14020384f  jz      short loc_140203882
0x140203851  cmp     dword ptr [rax+38h], 4
0x140203855  jl      short loc_140203882
0x140203857  mov     [rsp+1F0h+var_1A0], r15
0x14020385c  mov     [rsp+1F0h+var_198], 73Ch
0x140203864  mov     [rsp+1F0h+var_194], 4
0x14020386c  mov     [rsp+1F0h+var_190], rcx
0x140203871  lea     rdx, aMigCreateSysvo; "[MIG] Create sysvol migration local obj"...
0x140203878  lea     rcx, [rsp+1F0h+var_1A0]
0x14020387d  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140203882  cmp     [r13+68h], rbx
0x140203886  jnz     short loc_140203893
0x140203888  mov     rcx, r13; this
0x14020388b  call    ?GetComputer@AdConfig@Config@@QEAAPEAVFrsStatus@@XZ; Config::AdConfig::GetComputer(void)
0x140203890  mov     rdi, rax
0x140203893  mov     rsi, rbx
0x140203896  mov     [rbp+0F0h+arg_0], rbx
0x14020389d  mov     r14, rbx
0x1402038a0  mov     [rbp+0F0h+arg_10], rbx
0x1402038a7  lea     rcx, [rbp+0F0h+var_170]; this
0x1402038ab  call    ??0SYSVOL_OBJECTS@AdConfig@Config@@QEAA@XZ; Config::AdConfig::SYSVOL_OBJECTS::SYSVOL_OBJECTS(void)
0x1402038b0  nop
0x1402038b1  test    rdi, rdi
0x1402038b4  jnz     loc_140203A5A
0x1402038ba  lea     rdx, [rbp+0F0h+var_170]; struct Config::AdConfig::SYSVOL_OBJECTS *
0x1402038be  mov     rcx, r13; this
0x1402038c1  call    ?ConstructSysVolObjects@AdConfig@Config@@IEAAPEAVFrsStatus@@PEAUSYSVOL_OBJECTS@12@@Z; Config::AdConfig::ConstructSysVolObjects(Config::AdConfig::SYSVOL_OBJECTS *)
0x1402038c6  mov     rdi, rax
0x1402038c9  test    rax, rax
0x1402038cc  jnz     loc_140203A5A
0x1402038d2  mov     rax, [r13+28h]
0x1402038d6  cmp     [rax+24h], ebx
0x1402038d9  jnz     short loc_14020393E
0x1402038db  lea     rdx, [rbp+0F0h+var_170]; struct Config::AdConfig::SYSVOL_OBJECTS *
0x1402038df  mov     rcx, r13; this
0x1402038e2  call    ?CreateMemberObject@AdWriter@Config@@IEAAPEAVFrsStatus@@PEBUSYSVOL_OBJECTS@AdConfig@2@@Z; Config::AdWriter::CreateMemberObject(Config::AdConfig::SYSVOL_OBJECTS const *)
0x1402038e7  mov     rdi, rax
0x1402038ea  test    rax, rax
0x1402038ed  jnz     loc_140203A5A
0x1402038f3  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1402038fa  test    rax, rax
0x1402038fd  jz      short loc_14020393E
0x1402038ff  cmp     [rax+40h], ebx
0x140203902  jz      short loc_14020393E
0x140203904  lea     rsi, aAdwr; "ADWR"
0x14020390b  cmp     dword ptr [rax+38h], 4
0x14020390f  jl      short loc_140203945
0x140203911  mov     [rsp+1F0h+var_1A0], r15
0x140203916  mov     [rsp+1F0h+var_198], 759h
0x14020391e  mov     [rsp+1F0h+var_194], 4
0x140203926  mov     [rsp+1F0h+var_190], rsi
0x14020392b  lea     rdx, aSysvolMemberOb; "[SYSVOL] member object is created."
0x140203932  lea     rcx, [rsp+1F0h+var_1A0]
0x140203937  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x14020393c  jmp     short loc_140203945
0x14020393e  lea     rsi, aAdwr; "ADWR"
0x140203945  lea     r9, [rbp+0F0h+arg_0]; struct Config::AdObject **
0x14020394c  xor     r8d, r8d; struct Config::AdObject *
0x14020394f  mov     rdx, [rbp+0F0h+var_128]; unsigned __int16 *
0x140203953  lea     rcx, [rbp+0F0h+var_E0]; this
0x140203957  call    ?GetReplicaSet@AdSnapshot@Config@@AEAAPEAVFrsStatus@@PEBGPEAVAdObject@2@PEAPEAV42@@Z; Config::AdSnapshot::GetReplicaSet(ushort const *,Config::AdObject *,Config::AdObject * *)
0x14020395c  mov     rdi, rax
0x14020395f  test    rax, rax
0x140203962  jz      short loc_1402039CE
0x140203964  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14020396b  test    rax, rax
0x14020396e  jz      short loc_1402039C2
0x140203970  cmp     [rax+40h], ebx
0x140203973  jz      short loc_1402039C2
0x140203975  mov     r15d, 2
0x14020397b  cmp     [rax+38h], r15d
0x14020397f  jl      short loc_1402039C2
0x140203981  lea     rax, aConfigAdwriter_25; "Config::AdWriter::CreateSysVolMigration"...
0x140203988  mov     [rsp+1F0h+var_1A0], rax
0x14020398d  mov     [rsp+1F0h+var_198], 764h
0x140203995  mov     [rsp+1F0h+var_194], r15d
0x14020399a  mov     [rsp+1F0h+var_190], rsi
0x14020399f  mov     rax, [rbp+0F0h+var_128]
0x1402039a3  mov     [rbp+0F0h+arg_10], rax
0x1402039aa  lea     r8, [rbp+0F0h+arg_10]
0x1402039b1  lea     rdx, aSysvolCannotRe_0; "[SYSVOL] Cannot read RG AD object. Dn:%"...
0x1402039b8  lea     rcx, [rsp+1F0h+var_1A0]
0x1402039bd  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x1402039c2  mov     rsi, [rbp+0F0h+arg_0]
0x1402039c9  jmp     loc_140203A5A
0x1402039ce  lea     r9, [rbp+0F0h+arg_10]; struct Config::AdObject **
0x1402039d5  mov     rdx, [rbp+0F0h+var_F8]; unsigned __int16 *
0x1402039d9  lea     rcx, [rbp+0F0h+var_E0]; this
0x1402039dd  call    ?GetContentSet@AdSnapshot@Config@@AEAAPEAVFrsStatus@@PEBGPEAVAdObject@2@PEAPEAV42@@Z; Config::AdSnapshot::GetContentSet(ushort const *,Config::AdObject *,Config::AdObject * *)
0x1402039e2  mov     rdi, rax
0x1402039e5  test    rax, rax
0x1402039e8  jz      loc_140203AF2
0x1402039ee  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1402039f5  test    rax, rax
0x1402039f8  jz      short loc_140203A4C
0x1402039fa  cmp     [rax+40h], ebx
0x1402039fd  jz      short loc_140203A4C
0x1402039ff  mov     r15d, 2
0x140203a05  cmp     [rax+38h], r15d
0x140203a09  jl      short loc_140203A4C
0x140203a0b  lea     rax, aConfigAdwriter_25; "Config::AdWriter::CreateSysVolMigration"...
0x140203a12  mov     [rsp+1F0h+var_1A0], rax
0x140203a17  mov     [rsp+1F0h+var_198], 770h
0x140203a1f  mov     [rsp+1F0h+var_194], r15d
0x140203a24  mov     [rsp+1F0h+var_190], rsi
0x140203a29  mov     rax, [rbp+0F0h+var_F8]
0x140203a2d  mov     [rbp+0F0h+arg_18], rax
0x140203a34  lea     r8, [rbp+0F0h+arg_18]
0x140203a3b  lea     rdx, aSysvolCannotRe; "[SYSVOL] Cannot read CS AD object. Dn:%"...
0x140203a42  lea     rcx, [rsp+1F0h+var_1A0]
0x140203a47  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x140203a4c  mov     rsi, [rbp+0F0h+arg_0]
0x140203a53  mov     r14, [rbp+0F0h+arg_10]
0x140203a5a  test    rsi, rsi
0x140203a5d  jz      short loc_140203A67
0x140203a5f  mov     rcx, rsi; this
0x140203a62  call    ??_GAdObject@Config@@QEAAPEAXI@Z; Config::AdObject::`scalar deleting destructor'(uint)
0x140203a67  test    r14, r14
0x140203a6a  jz      short loc_140203A74
0x140203a6c  mov     rcx, r14; this
0x140203a6f  call    ??_GAdObject@Config@@QEAAPEAXI@Z; Config::AdObject::`scalar deleting destructor'(uint)
0x140203a74  test    rdi, rdi
0x140203a77  jz      short loc_140203AC0
0x140203a79  call    cs:__imp_GetCurrentThreadId
0x140203a80  nop     dword ptr [rax+rax+00h]
0x140203a85  mov     [rsp+1F0h+var_1B0], rdi
0x140203a8a  mov     [rsp+1F0h+var_1B8], eax
0x140203a8e  mov     [rsp+1F0h+var_1C0], 7ACh
0x140203a96  lea     rax, aConfigAdwriter_8; "Config::AdWriter::CreateSysVolMigration"...
0x140203a9d  mov     [rsp+1F0h+var_1C8], rax
0x140203aa2  lea     rax, aBaseFsRemotefs_38; "base\\fs\\remotefs\\frs\\src\\ad\\adwri"...
0x140203aa9  mov     [rsp+1F0h+var_1D0], rax
0x140203aae  mov     r9d, [rdi]
0x140203ab1  mov     r8d, [rdi+8]
0x140203ab5  mov     edx, [rdi+4]
0x140203ab8  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140203abd  mov     rbx, rax
0x140203ac0  lea     rcx, [rbp+0F0h+var_170]; this
0x140203ac4  call    ??1SYSVOL_OBJECTS@AdConfig@Config@@QEAA@XZ; Config::AdConfig::SYSVOL_OBJECTS::~SYSVOL_OBJECTS(void)
0x140203ac9  nop
0x140203aca  lea     rcx, [rbp+0F0h+var_E0]; this
0x140203ace  call    ??1AdSnapshot@Config@@QEAA@XZ; Config::AdSnapshot::~AdSnapshot(void)
0x140203ad3  mov     rax, rbx
0x140203ad6  mov     rbx, [rsp+1F0h+arg_8]
0x140203ade  add     rsp, 1C0h
0x140203ae5  pop     r15
0x140203ae7  pop     r14
0x140203ae9  pop     r13
0x140203aeb  pop     r12
0x140203aed  pop     rdi
0x140203aee  pop     rsi
0x140203aef  pop     rbp
0x140203af0  retn
0x140203af2  mov     rsi, [rbp+0F0h+arg_0]
0x140203af9  mov     rcx, [rsi+38h]; this
0x140203afd  mov     r15d, 2
0x140203b03  test    rcx, rcx
0x140203b06  jz      short loc_140203B2A
0x140203b08  call    ?GetValue@AdBinAttr@Config@@QEBAPEBEXZ; Config::AdBinAttr::GetValue(void)
0x140203b0d  test    rax, rax
0x140203b10  jz      short loc_140203B2A
0x140203b12  mov     rcx, [rsi+38h]; this
0x140203b16  call    ?GetValue@AdBinAttr@Config@@QEBAPEBEXZ; Config::AdBinAttr::GetValue(void)
0x140203b1b  movups  xmm0, xmmword ptr [rax]
0x140203b1e  movdqu  xmmword ptr [r12+40h], xmm0
0x140203b25  jmp     loc_140203BCA
0x140203b2a  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140203b31  test    rax, rax
0x140203b34  jz      short loc_140203B77
0x140203b36  cmp     [rax+40h], ebx
0x140203b39  jz      short loc_140203B77
0x140203b3b  cmp     [rax+38h], r15d
0x140203b3f  jl      short loc_140203B77
0x140203b41  lea     rax, aConfigAdwriter_25; "Config::AdWriter::CreateSysVolMigration"...
0x140203b48  mov     [rsp+1F0h+var_188], rax
0x140203b4d  mov     [rsp+1F0h+var_180], 77Dh
0x140203b55  mov     [rsp+1F0h+var_17C], r15d
0x140203b5a  lea     rax, aAdwr; "ADWR"
0x140203b61  mov     [rsp+1F0h+var_178], rax
0x140203b66  lea     rdx, aSysvolInvalidR; "[SYSVOL] Invalid Replication Group obje"...
0x140203b6d  lea     rcx, [rsp+1F0h+var_188]
0x140203b72  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140203b77  call    cs:__imp_GetCurrentThreadId
0x140203b7e  nop     dword ptr [rax+rax+00h]
0x140203b83  mov     [rsp+1F0h+var_1B0], rbx
0x140203b88  mov     [rsp+1F0h+var_1B8], eax
0x140203b8c  mov     [rsp+1F0h+var_1C0], 77Eh
0x140203b94  lea     rax, aConfigAdwriter_8; "Config::AdWriter::CreateSysVolMigration"...
0x140203b9b  mov     [rsp+1F0h+var_1C8], rax
0x140203ba0  lea     rax, aBaseFsRemotefs_38; "base\\fs\\remotefs\\frs\\src\\ad\\adwri"...
0x140203ba7  mov     [rsp+1F0h+var_1D0], rax
0x140203bac  mov     r9d, 1
0x140203bb2  xor     r8d, r8d
0x140203bb5  lea     edx, [r9+0Ch]
0x140203bb9  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140203bbe  mov     rdi, rax
0x140203bc1  test    rax, rax
0x140203bc4  jnz     loc_140203A53
0x140203bca  mov     r14, [rbp+0F0h+arg_10]
0x140203bd1  mov     rcx, [r14+38h]; this
0x140203bd5  test    rcx, rcx
0x140203bd8  jz      short loc_140203BFC
0x140203bda  call    ?GetValue@AdBinAttr@Config@@QEBAPEBEXZ; Config::AdBinAttr::GetValue(void)
0x140203bdf  test    rax, rax
0x140203be2  jz      short loc_140203BFC
0x140203be4  mov     rcx, [r14+38h]; this
0x140203be8  call    ?GetValue@AdBinAttr@Config@@QEBAPEBEXZ; Config::AdBinAttr::GetValue(void)
0x140203bed  movups  xmm0, xmmword ptr [rax]
0x140203bf0  movdqu  xmmword ptr [r12+50h], xmm0
0x140203bf7  jmp     loc_140203C9C
0x140203bfc  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140203c03  test    rax, rax
0x140203c06  jz      short loc_140203C49
0x140203c08  cmp     [rax+40h], ebx
0x140203c0b  jz      short loc_140203C49
0x140203c0d  cmp     [rax+38h], r15d
0x140203c11  jl      short loc_140203C49
0x140203c13  lea     rax, aConfigAdwriter_25; "Config::AdWriter::CreateSysVolMigration"...
0x140203c1a  mov     [rsp+1F0h+var_188], rax
0x140203c1f  mov     [rsp+1F0h+var_180], 787h
0x140203c27  mov     [rsp+1F0h+var_17C], r15d
0x140203c2c  lea     rax, aAdwr; "ADWR"
0x140203c33  mov     [rsp+1F0h+var_178], rax
0x140203c38  lea     rdx, aSysvolInvalidC; "[SYSVOL] Invalid Content Set object, mi"...
0x140203c3f  lea     rcx, [rsp+1F0h+var_188]
0x140203c44  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140203c49  call    cs:__imp_GetCurrentThreadId
0x140203c50  nop     dword ptr [rax+rax+00h]
0x140203c55  mov     [rsp+1F0h+var_1B0], rbx
0x140203c5a  mov     [rsp+1F0h+var_1B8], eax
0x140203c5e  mov     [rsp+1F0h+var_1C0], 788h
0x140203c66  lea     rax, aConfigAdwriter_8; "Config::AdWriter::CreateSysVolMigration"...
0x140203c6d  mov     [rsp+1F0h+var_1C8], rax
0x140203c72  lea     rax, aBaseFsRemotefs_38; "base\\fs\\remotefs\\frs\\src\\ad\\adwri"...
0x140203c79  mov     [rsp+1F0h+var_1D0], rax
0x140203c7e  mov     r9d, 1
0x140203c84  xor     r8d, r8d
0x140203c87  lea     edx, [r9+0Ch]
0x140203c8b  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140203c90  mov     rdi, rax
0x140203c93  test    rax, rax
0x140203c96  jnz     loc_140203A5A
0x140203c9c  mov     rax, [r13+28h]
0x140203ca0  mov     r9, rsi; struct Config::AdObject *
0x140203ca3  lea     r8, [rbp+0F0h+var_170]; struct Config::AdConfig::SYSVOL_OBJECTS *
0x140203ca7  mov     rdx, r12; struct Config::SYSVOL_PARAMETERS *
0x140203caa  mov     rcx, r13; this
0x140203cad  cmp     [rax+24h], ebx
0x140203cb0  jnz     short loc_140203CBE
0x140203cb2  mov     [rsp+1F0h+var_1D0], r14; struct Config::AdObject *
0x140203cb7  call    ?CreateSysVolLocalObjectsOnLocalDc@AdWriter@Config@@IEAAPEAVFrsStatus@@PEBUSYSVOL_PARAMETERS@2@PEBUSYSVOL_OBJECTS@AdConfig@2@PEBVAdObject@2@2@Z; Config::AdWriter::CreateSysVolLocalObjectsOnLocalDc(Config::SYSVOL_PARAMETERS const *,Config::AdConfig::SYSVOL_OBJECTS const *,Config::AdObject const *,Config::AdObject const *)
0x140203cbc  jmp     short loc_140203CDE
0x140203cbe  mov     dword ptr [rbp+0F0h+arg_0], 4
0x140203cc8  lea     rax, [rbp+0F0h+arg_0]
0x140203ccf  mov     [rsp+1F0h+var_1C8], rax; unsigned int *
0x140203cd4  mov     [rsp+1F0h+var_1D0], r14; struct Config::AdObject *
0x140203cd9  call    ?CreateSysVolLocalObjectsOnAnyWritableDc@AdWriter@Config@@IEAAPEAVFrsStatus@@PEBUSYSVOL_PARAMETERS@2@PEBUSYSVOL_OBJECTS@AdConfig@2@PEBVAdObject@2@2AEBK@Z; Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc(Config::SYSVOL_PARAMETERS const *,Config::AdConfig::SYSVOL_OBJECTS const *,Config::AdObject const *,Config::AdObject const *,ulong const &)
0x140203cde  mov     rdi, rax
0x140203ce1  test    rax, rax
0x140203ce4  jnz     loc_140203A5A
0x140203cea  mov     rcx, r12; struct Config::SYSVOL_PARAMETERS *
0x140203ced  call    ?SetSysvolParametersIntoRegistry@SysVolUtil@Migration@@SAPEAVFrsStatus@@AEAUSYSVOL_PARAMETERS@Config@@@Z; Migration::SysVolUtil::SetSysvolParametersIntoRegistry(Config::SYSVOL_PARAMETERS &)
0x140203cf2  mov     rdi, rax
0x140203cf5  jmp     loc_140203A5A
```
