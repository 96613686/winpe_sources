# Config::RegReader::ReadSysVolConfigValues(ushort const *,Config::SYSVOL_PARAMETERS &)

- ea: `0x14004e1f0`
- end: `0x14004e8ee`
- name: `?ReadSysVolConfigValues@RegReader@Config@@QEAAPEAVFrsStatus@@PEBGAEAUSYSVOL_PARAMETERS@2@@Z`
- size: `1790`
- prototype: `struct FrsStatus *(Config::RegReader *__hidden this, const unsigned __int16 *, struct Config::SYSVOL_PARAMETERS *)`
- caller_count: `3`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140022954`
- `0x1400eb170`
- `0x140203d04`

## callees

- `0x14000c910`
- `0x14000e34c`
- `0x14000ee94`
- `0x14001bf80`
- `0x14004938c`
- `0x140049718`
- `0x14004986c`
- `0x140049b04`
- `0x140049c48`
- `0x14004a318`
- `0x14004a464`
- `0x14004a838`
- `0x14004a940`
- `0x14004a990`
- `0x14004aa9c`
- `0x14004c528`
- `0x14004cb14`
- `0x14004d888`
- `0x14004e1f0`
- `0x1401b9494`
- `0x1401c5228`
- `0x1401c5380`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14004e333`
- `KERNEL32!GetCurrentThreadId` at `0x14004e6ec`
- `KERNEL32!GetCurrentThreadId` at `0x14004e7e8`
- `KERNEL32!GetCurrentThreadId` at `0x14004e860`
- `KERNEL32!GetCurrentThreadId` at `0x14004e333`
- `KERNEL32!GetCurrentThreadId` at `0x14004e6ec`
- `KERNEL32!GetCurrentThreadId` at `0x14004e7e8`
- `KERNEL32!GetCurrentThreadId` at `0x14004e860`

## string_xrefs

- `0x14004e35c`: `base\fs\remotefs\frs\src\config\reg.cpp`
- `0x14004e715`: `base\fs\remotefs\frs\src\config\reg.cpp`
- `0x14004e811`: `base\fs\remotefs\frs\src\config\reg.cpp`
- `0x14004e889`: `base\fs\remotefs\frs\src\config\reg.cpp`
- `0x14004e2ad`: `System\CurrentControlSet\Services\DFSR\Parameters\SysVols`
- `0x14004e221`: `Config::RegReader::ReadSysVolConfigValues`
- `0x14004e777`: `Config::RegReader::ReadSysVolConfigValues`
- `0x14004e25f`: `Read key: %?\%?`
- `0x14004e350`: `Config::RegReader::ReadSysVolConfigValues`
- `0x14004e709`: `Config::RegReader::ReadSysVolConfigValues`
- `0x14004e805`: `Config::RegReader::ReadSysVolConfigValues`
- `0x14004e87d`: `Config::RegReader::ReadSysVolConfigValues`
- `0x14004e5ff`: `Parent Computer`
- `0x14004e657`: `Command`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct FrsStatus *__fastcall Config::RegReader::ReadSysVolConfigValues(
        Config::RegReader *this,
        const unsigned __int16 *a2,
        struct Config::SYSVOL_PARAMETERS *a3)
{
  const unsigned __int16 *v4; // rdi
  __int64 v5; // rbx
  BaseRegKey *v6; // r12
  struct FrsStatus *StringValue; // rdi
  struct FrsStatus *v8; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  struct FrsStatus *v17; // rsi
  struct FrsStatus *v18; // r14
  DWORD v19; // eax
  __int64 v20; // rcx
  struct FrsStatus *v21; // r14
  struct FrsStatus *v22; // rsi
  DWORD v23; // eax
  __int64 v24; // rcx
  DWORD v25; // eax
  __int64 v26; // rcx
  const wchar_t *v28; // [rsp+58h] [rbp-59h] BYREF
  int v29; // [rsp+60h] [rbp-51h]
  int v30; // [rsp+64h] [rbp-4Dh]
  const wchar_t *v31; // [rsp+68h] [rbp-49h]
  _BYTE v32[8]; // [rsp+70h] [rbp-41h] BYREF
  _QWORD v33[4]; // [rsp+78h] [rbp-39h] BYREF
  _QWORD v34[14]; // [rsp+98h] [rbp-19h] BYREF
  struct FrsStatus *v35; // [rsp+118h] [rbp+67h] BYREF
  const unsigned __int16 *v36; // [rsp+120h] [rbp+6Fh] BYREF
  unsigned __int16 *v37; // [rsp+130h] [rbp+7Fh] BYREF

  v36 = a2;
  v35 = this;
  v4 = a2;
  v5 = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v28 = L"Config::RegReader::ReadSysVolConfigValues";
    v29 = 1443;
    v30 = 4;
    v31 = L"CREG";
    dbgobj::DbgPrint<unsigned short,unsigned short [58],unsigned short const *>(&v28, L"Read key: %?\\%?", a3, &v36);
  }
  Config::RegKey::RegKey((Config::RegKey *)v34);
  PtrList<Config::RegKey>::PtrList<Config::RegKey>(v32);
  v6 = 0;
  v37 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !byte_140315A80 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
    v4 = v36;
  }
  StringValue = BaseRegKey::Open(
                  (BaseRegKey *)v34,
                  L"System\\CurrentControlSet\\Services\\DFSR\\Parameters\\SysVols",
                  v4,
                  0x20019u);
  v8 = StringValue;
  if ( !StringValue )
  {
    Config::RegKey::GetSubKeys((BaseRegKey *)v34);
    v8 = 0;
    if ( !(unsigned int)((__int64)(v33[1] - v33[0]) >> 3) )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v28 = L"Config::RegReader::ReadSysVolConfigValues";
        v29 = 1459;
        v30 = 2;
        v31 = L"CREG";
        dbgobj::DbgPrint<unsigned short>(&v28, L"No subkeys");
      }
      CurrentThreadId = GetCurrentThreadId();
      StringValue = (struct FrsStatus *)FrsStatusList::PushNewError(
                                          v10,
                                          1168,
                                          0,
                                          1,
                                          "base\\fs\\remotefs\\frs\\src\\config\\reg.cpp",
                                          "Config::RegReader::ReadSysVolConfigValues",
                                          1460,
                                          CurrentThreadId,
                                          0);
      v8 = StringValue;
    }
  }
  if ( !v8 )
  {
    v6 = *(BaseRegKey **)std::vector<ShutdownObject *>::at(v33, 0);
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v28 = L"Config::RegReader::ReadSysVolConfigValues";
      v29 = 1470;
      v30 = 4;
      v31 = L"CREG";
      dbgobj::DbgPrint<unsigned short,unsigned short [23]>(&v28, v11, L"Replication Group Name");
    }
    StringValue = (struct FrsStatus *)BaseRegKey::ReadStringValue(v6, L"Replication Group Name");
    if ( !StringValue )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v28 = L"Config::RegReader::ReadSysVolConfigValues";
        v29 = 1480;
        v30 = 4;
        v31 = L"CREG";
        dbgobj::DbgPrint<unsigned short,unsigned short [23]>(&v28, v12, L"Replication Group Type");
      }
      StringValue = (struct FrsStatus *)BaseRegKey::ReadStringValue(v6, L"Replication Group Type");
      if ( !StringValue )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v28 = L"Config::RegReader::ReadSysVolConfigValues";
          v29 = 1490;
          v30 = 4;
          v31 = L"CREG";
          dbgobj::DbgPrint<unsigned short,unsigned short [23]>(&v28, v13, L"Replicated Folder Name");
        }
        StringValue = (struct FrsStatus *)BaseRegKey::ReadStringValue(v6, L"Replicated Folder Name");
        if ( !StringValue )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v28 = L"Config::RegReader::ReadSysVolConfigValues";
            v29 = 1500;
            v30 = 4;
            v31 = L"CREG";
            dbgobj::DbgPrint<unsigned short,unsigned short [23]>(&v28, v14, L"Replicated Folder Root");
          }
          StringValue = (struct FrsStatus *)BaseRegKey::ReadStringValue(v6, L"Replicated Folder Root");
        }
      }
    }
  }
  if ( StringValue )
    goto LABEL_79;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v28 = L"Config::RegReader::ReadSysVolConfigValues";
    v29 = 1510;
    v30 = 4;
    v31 = L"CREG";
    dbgobj::DbgPrint<unsigned short,unsigned short [24]>(&v28);
  }
  StringValue = (struct FrsStatus *)BaseRegKey::ReadStringValue(v6, L"Replicated Folder Stage");
  if ( StringValue )
    goto LABEL_79;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v28 = L"Config::RegReader::ReadSysVolConfigValues";
    v29 = 1520;
    v30 = 4;
    v31 = L"CREG";
    dbgobj::DbgPrint<unsigned short,unsigned short [11]>(&v28);
  }
  StringValue = BaseRegKey::ReadDWordValue(v6, L"Is Primary", (unsigned int *)a3 + 6);
  if ( StringValue )
    goto LABEL_79;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v28 = L"Config::RegReader::ReadSysVolConfigValues";
    v29 = 1529;
    v30 = 4;
    v31 = L"CREG";
    dbgobj::DbgPrint<unsigned short,unsigned short [16]>(&v28);
  }
  StringValue = (struct FrsStatus *)BaseRegKey::ReadStringValue(v6, L"Parent Computer");
  if ( StringValue )
    goto LABEL_79;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v28 = L"Config::RegReader::ReadSysVolConfigValues";
    v29 = 1540;
    v30 = 4;
    v31 = L"CREG";
    dbgobj::DbgPrint<unsigned short,unsigned short [8]>(&v28);
  }
  StringValue = (struct FrsStatus *)BaseRegKey::ReadStringValue(v6, L"Command");
  if ( StringValue )
    goto LABEL_79;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v28 = L"Config::RegReader::ReadSysVolConfigValues";
    v29 = 1551;
    v30 = 4;
    v31 = L"CREG";
    dbgobj::DbgPrint<unsigned short,unsigned short [23]>(&v28, v15, L"Replication Group Guid");
  }
  StringValue = (struct FrsStatus *)BaseRegKey::ReadStringValue(v6, L"Replication Group Guid");
  v35 = StringValue;
  v17 = StringValue;
  v18 = StringValue;
  if ( !StringValue && !(unsigned int)Config::GuidParam::ToGuid(v37 + 9, (struct _GUID *)a3 + 4) )
  {
    v19 = GetCurrentThreadId();
    StringValue = (struct FrsStatus *)FrsStatusList::PushNewError(
                                        v20,
                                        87,
                                        0,
                                        1,
                                        "base\\fs\\remotefs\\frs\\src\\config\\reg.cpp",
                                        "Config::RegReader::ReadSysVolConfigValues",
                                        1558,
                                        v19,
                                        0);
    v35 = StringValue;
    v17 = StringValue;
    v18 = StringValue;
  }
  if ( v17 && *((_DWORD *)v18 + 1) == 2 )
  {
    CLEAR_ERROR(&v35);
    StringValue = v35;
  }
  if ( StringValue )
    goto LABEL_79;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v28 = L"Config::RegReader::ReadSysVolConfigValues";
    v29 = 1571;
    v30 = 4;
    v31 = L"CREG";
    dbgobj::DbgPrint<unsigned short,unsigned short [23]>(&v28, v16, L"Replicated Folder Guid");
  }
  StringValue = (struct FrsStatus *)BaseRegKey::ReadStringValue(v6, L"Replicated Folder Guid");
  v35 = StringValue;
  v21 = StringValue;
  v22 = StringValue;
  if ( !StringValue && !(unsigned int)Config::GuidParam::ToGuid(v37 + 9, (struct _GUID *)a3 + 5) )
  {
    v23 = GetCurrentThreadId();
    StringValue = (struct FrsStatus *)FrsStatusList::PushNewError(
                                        v24,
                                        87,
                                        0,
                                        1,
                                        "base\\fs\\remotefs\\frs\\src\\config\\reg.cpp",
                                        "Config::RegReader::ReadSysVolConfigValues",
                                        1577,
                                        v23,
                                        0);
    v35 = StringValue;
    v21 = StringValue;
    v22 = StringValue;
  }
  if ( v21 && *((_DWORD *)v22 + 1) == 2 )
  {
    CLEAR_ERROR(&v35);
    StringValue = v35;
  }
  if ( StringValue )
  {
LABEL_79:
    v25 = GetCurrentThreadId();
    v5 = FrsStatusList::PushNewError(
           v26,
           *((unsigned int *)StringValue + 1),
           *((unsigned int *)StringValue + 2),
           *(unsigned int *)StringValue,
           "base\\fs\\remotefs\\frs\\src\\config\\reg.cpp",
           "Config::RegReader::ReadSysVolConfigValues",
           1590,
           v25,
           StringValue);
  }
  else
  {
    Config::SYSVOL_PARAMETERS::Dump(a3);
  }
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v37);
  PtrList<Config::RegKey>::~PtrList<Config::RegKey>(v32);
  v34[0] = &Config::RegKey::`vftable';
  BaseRegKey::~BaseRegKey((BaseRegKey *)v34);
  return (struct FrsStatus *)v5;
}

```

## disassembly

```asm
0x14004e1f0  mov     rax, rsp
0x14004e1f3  mov     [rax+18h], rbx
0x14004e1f7  mov     [rax+10h], rdx
0x14004e1fb  mov     [rax+8], rcx
0x14004e1ff  push    rbp
0x14004e200  push    rsi
0x14004e201  push    rdi
0x14004e202  push    r12
0x14004e204  push    r13
0x14004e206  push    r14
0x14004e208  push    r15
0x14004e20a  lea     rbp, [rax-5Fh]
0x14004e20e  sub     rsp, 0D0h
0x14004e215  mov     r15, r8
0x14004e218  mov     rdi, rdx
0x14004e21b  mov     r13d, 4
0x14004e221  lea     rsi, aConfigRegreade_3; "Config::RegReader::ReadSysVolConfigValu"...
0x14004e228  lea     r14, aCreg; "CREG"
0x14004e22f  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14004e236  xor     ebx, ebx
0x14004e238  test    rax, rax
0x14004e23b  jz      short loc_14004E26F
0x14004e23d  cmp     [rax+40h], ebx
0x14004e240  jz      short loc_14004E26F
0x14004e242  cmp     [rax+38h], r13d
0x14004e246  jl      short loc_14004E26F
0x14004e248  mov     [rbp+57h+var_B0], rsi
0x14004e24c  mov     [rbp+57h+var_A8], 5A3h
0x14004e253  mov     [rbp+57h+var_A4], r13d
0x14004e257  mov     [rbp+57h+var_A0], r14
0x14004e25b  lea     r9, [rbp+57h+arg_8]
0x14004e25f  lea     rdx, aReadKey; "Read key: %?\\%?"
0x14004e266  lea     rcx, [rbp+57h+var_B0]
0x14004e26a  call    ??$DbgPrint@G$$BY0DK@GPEBG@dbgobj@@QEAA_KPEBGAEAY0DK@$$CBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort [58],ushort const *>(ushort const *,ushort const (&)[58],ushort const * const &)
0x14004e26f  lea     rcx, [rbp+57h+var_70]; this
0x14004e273  call    ??0RegKey@Config@@QEAA@XZ; Config::RegKey::RegKey(void)
0x14004e278  nop
0x14004e279  lea     rcx, [rbp+57h+var_98]
0x14004e27d  call    ??0?$PtrList@VRegKey@Config@@@@QEAA@XZ; PtrList<Config::RegKey>::PtrList<Config::RegKey>(void)
0x14004e282  nop
0x14004e283  mov     r12, rbx
0x14004e286  lea     rax, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x14004e28d  mov     [rbp+57h+arg_18], rax
0x14004e291  cmp     cs:byte_140315A80, bl
0x14004e297  jnz     short loc_14004E2A4
0x14004e299  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x14004e2a0  mov     rdi, [rbp+57h+arg_8]
0x14004e2a4  mov     r9d, 20019h; unsigned int
0x14004e2aa  mov     r8, rdi; unsigned __int16 *
0x14004e2ad  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\DF"...
0x14004e2b4  lea     rcx, [rbp+57h+var_70]; this
0x14004e2b8  call    ?Open@BaseRegKey@@QEAAPEAVFrsStatus@@PEBG0K@Z; BaseRegKey::Open(ushort const *,ushort const *,ulong)
0x14004e2bd  mov     rdi, rax
0x14004e2c0  mov     rcx, rax
0x14004e2c3  test    rax, rax
0x14004e2c6  jnz     loc_14004E381
0x14004e2cc  mov     r8d, 20019h
0x14004e2d2  lea     rdx, [rbp+57h+var_98]
0x14004e2d6  lea     rcx, [rbp+57h+var_70]; this
0x14004e2da  call    ?GetSubKeys@RegKey@Config@@QEAAKPEAV?$PtrList@VRegKey@Config@@@@K@Z; Config::RegKey::GetSubKeys(PtrList<Config::RegKey> *,ulong)
0x14004e2df  mov     rax, [rbp+57h+var_88]
0x14004e2e3  sub     rax, [rbp+57h+var_90]
0x14004e2e7  sar     rax, 3
0x14004e2eb  mov     rcx, rdi
0x14004e2ee  test    eax, eax
0x14004e2f0  jnz     loc_14004E381
0x14004e2f6  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14004e2fd  test    rax, rax
0x14004e300  jz      short loc_14004E333
0x14004e302  cmp     [rax+40h], ebx
0x14004e305  jz      short loc_14004E333
0x14004e307  cmp     dword ptr [rax+38h], 2
0x14004e30b  jl      short loc_14004E333
0x14004e30d  mov     [rbp+57h+var_B0], rsi
0x14004e311  mov     [rbp+57h+var_A8], 5B3h
0x14004e318  mov     [rbp+57h+var_A4], 2
0x14004e31f  mov     [rbp+57h+var_A0], r14
0x14004e323  lea     rdx, aNoSubkeys; "No subkeys"
0x14004e32a  lea     rcx, [rbp+57h+var_B0]
0x14004e32e  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x14004e333  call    cs:__imp_GetCurrentThreadId
0x14004e33a  nop     dword ptr [rax+rax+00h]
0x14004e33f  mov     [rsp+40h], rbx
0x14004e344  mov     dword ptr [rsp+100h+var_C8], eax
0x14004e348  mov     [rsp+100h+var_D0], 5B4h
0x14004e350  lea     rax, aConfigRegreade; "Config::RegReader::ReadSysVolConfigValu"...
0x14004e357  mov     qword ptr [rsp+100h+var_D8], rax
0x14004e35c  lea     rax, aBaseFsRemotefs_47; "base\\fs\\remotefs\\frs\\src\\config\\r"...
0x14004e363  mov     [rsp+100h+var_E0], rax
0x14004e368  mov     r9d, 1
0x14004e36e  xor     r8d, r8d
0x14004e371  mov     edx, 490h
0x14004e376  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14004e37b  mov     rdi, rax
0x14004e37e  mov     rcx, rax
0x14004e381  test    rcx, rcx
0x14004e384  jnz     loc_14004E510
0x14004e38a  xor     edx, edx
0x14004e38c  lea     rcx, [rbp+57h+var_90]
0x14004e390  call    ?at@?$vector@PEAVShutdownObject@@V?$allocator@PEAVShutdownObject@@@std@@@std@@QEAAAEAPEAVShutdownObject@@_K@Z; std::vector<ShutdownObject *>::at(unsigned __int64)
0x14004e395  mov     r12, [rax]
0x14004e398  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14004e39f  test    rax, rax
0x14004e3a2  jz      short loc_14004E3D2
0x14004e3a4  cmp     [rax+40h], ebx
0x14004e3a7  jz      short loc_14004E3D2
0x14004e3a9  cmp     [rax+38h], r13d
0x14004e3ad  jl      short loc_14004E3D2
0x14004e3af  mov     [rbp+57h+var_B0], rsi
0x14004e3b3  mov     [rbp+57h+var_A8], 5BEh
0x14004e3ba  mov     [rbp+57h+var_A4], r13d
0x14004e3be  mov     [rbp+57h+var_A0], r14
0x14004e3c2  lea     r8, aReplicationGro; "Replication Group Name"
0x14004e3c9  lea     rcx, [rbp+57h+var_B0]
0x14004e3cd  call    ??$DbgPrint@G$$BY0BH@G@dbgobj@@QEAA_KPEBGAEAY0BH@$$CBG@Z; dbgobj::DbgPrint<ushort,ushort [23]>(ushort const *,ushort const (&)[23])
0x14004e3d2  lea     r9, [r15+8]
0x14004e3d6  mov     r8d, 1000h
0x14004e3dc  lea     rdx, aReplicationGro; "Replication Group Name"
0x14004e3e3  mov     rcx, r12; this
0x14004e3e6  call    ?ReadStringValue@BaseRegKey@@QEAAPEAVFrsStatus@@PEBGGAEAV?$FrsStringImpl@GD@@@Z; BaseRegKey::ReadStringValue(ushort const *,ushort,FrsStringImpl<ushort,char> &)
0x14004e3eb  mov     rdi, rax
0x14004e3ee  mov     rcx, rax
0x14004e3f1  test    rax, rax
0x14004e3f4  jnz     loc_14004E510
0x14004e3fa  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14004e401  test    rax, rax
0x14004e404  jz      short loc_14004E434
0x14004e406  cmp     [rax+40h], ebx
0x14004e409  jz      short loc_14004E434
0x14004e40b  cmp     [rax+38h], r13d
0x14004e40f  jl      short loc_14004E434
0x14004e411  mov     [rbp+57h+var_B0], rsi
0x14004e415  mov     [rbp+57h+var_A8], 5C8h
0x14004e41c  mov     [rbp+57h+var_A4], r13d
0x14004e420  mov     [rbp+57h+var_A0], r14
0x14004e424  lea     r8, aReplicationGro_1; "Replication Group Type"
0x14004e42b  lea     rcx, [rbp+57h+var_B0]
0x14004e42f  call    ??$DbgPrint@G$$BY0BH@G@dbgobj@@QEAA_KPEBGAEAY0BH@$$CBG@Z; dbgobj::DbgPrint<ushort,ushort [23]>(ushort const *,ushort const (&)[23])
0x14004e434  lea     r9, [r15+10h]
0x14004e438  mov     r8d, 1000h
0x14004e43e  lea     rdx, aReplicationGro_1; "Replication Group Type"
0x14004e445  mov     rcx, r12; this
0x14004e448  call    ?ReadStringValue@BaseRegKey@@QEAAPEAVFrsStatus@@PEBGGAEAV?$FrsStringImpl@GD@@@Z; BaseRegKey::ReadStringValue(ushort const *,ushort,FrsStringImpl<ushort,char> &)
0x14004e44d  mov     rdi, rax
0x14004e450  mov     rcx, rax
0x14004e453  test    rax, rax
0x14004e456  jnz     loc_14004E510
0x14004e45c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14004e463  test    rax, rax
0x14004e466  jz      short loc_14004E496
0x14004e468  cmp     [rax+40h], ebx
0x14004e46b  jz      short loc_14004E496
0x14004e46d  cmp     [rax+38h], r13d
0x14004e471  jl      short loc_14004E496
0x14004e473  mov     [rbp+57h+var_B0], rsi
0x14004e477  mov     [rbp+57h+var_A8], 5D2h
0x14004e47e  mov     [rbp+57h+var_A4], r13d
0x14004e482  mov     [rbp+57h+var_A0], r14
0x14004e486  lea     r8, aReplicatedFold_3; "Replicated Folder Name"
0x14004e48d  lea     rcx, [rbp+57h+var_B0]
0x14004e491  call    ??$DbgPrint@G$$BY0BH@G@dbgobj@@QEAA_KPEBGAEAY0BH@$$CBG@Z; dbgobj::DbgPrint<ushort,ushort [23]>(ushort const *,ushort const (&)[23])
0x14004e496  lea     r9, [r15+20h]
0x14004e49a  mov     r8d, 1000h
0x14004e4a0  lea     rdx, aReplicatedFold_3; "Replicated Folder Name"
0x14004e4a7  mov     rcx, r12; this
0x14004e4aa  call    ?ReadStringValue@BaseRegKey@@QEAAPEAVFrsStatus@@PEBGGAEAV?$FrsStringImpl@GD@@@Z; BaseRegKey::ReadStringValue(ushort const *,ushort,FrsStringImpl<ushort,char> &)
0x14004e4af  mov     rdi, rax
0x14004e4b2  mov     rcx, rax
0x14004e4b5  test    rax, rax
0x14004e4b8  jnz     short loc_14004E510
0x14004e4ba  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14004e4c1  test    rax, rax
0x14004e4c4  jz      short loc_14004E4F4
0x14004e4c6  cmp     [rax+40h], ebx
0x14004e4c9  jz      short loc_14004E4F4
0x14004e4cb  cmp     [rax+38h], r13d
0x14004e4cf  jl      short loc_14004E4F4
0x14004e4d1  mov     [rbp+57h+var_B0], rsi
0x14004e4d5  mov     [rbp+57h+var_A8], 5DCh
0x14004e4dc  mov     [rbp+57h+var_A4], r13d
0x14004e4e0  mov     [rbp+57h+var_A0], r14
0x14004e4e4  lea     r8, aReplicatedFold_7; "Replicated Folder Root"
0x14004e4eb  lea     rcx, [rbp+57h+var_B0]
0x14004e4ef  call    ??$DbgPrint@G$$BY0BH@G@dbgobj@@QEAA_KPEBGAEAY0BH@$$CBG@Z; dbgobj::DbgPrint<ushort,ushort [23]>(ushort const *,ushort const (&)[23])
0x14004e4f4  lea     r9, [r15+30h]
0x14004e4f8  mov     r8d, 1000h
0x14004e4fe  lea     rdx, aReplicatedFold_7; "Replicated Folder Root"
0x14004e505  mov     rcx, r12; this
0x14004e508  call    ?ReadStringValue@BaseRegKey@@QEAAPEAVFrsStatus@@PEBGGAEAV?$FrsStringImpl@GD@@@Z; BaseRegKey::ReadStringValue(ushort const *,ushort,FrsStringImpl<ushort,char> &)
0x14004e50d  mov     rdi, rax
0x14004e510  test    rdi, rdi
0x14004e513  jnz     loc_14004E860
0x14004e519  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14004e520  test    rax, rax
0x14004e523  jz      short loc_14004E54C
0x14004e525  cmp     [rax+40h], ebx
0x14004e528  jz      short loc_14004E54C
0x14004e52a  cmp     [rax+38h], r13d
0x14004e52e  jl      short loc_14004E54C
0x14004e530  mov     [rbp+57h+var_B0], rsi
0x14004e534  mov     [rbp+57h+var_A8], 5E6h
0x14004e53b  mov     [rbp+57h+var_A4], r13d
0x14004e53f  mov     [rbp+57h+var_A0], r14
0x14004e543  lea     rcx, [rbp+57h+var_B0]
0x14004e547  call    ??$DbgPrint@G$$BY0BI@G@dbgobj@@QEAA_KPEBGAEAY0BI@$$CBG@Z; dbgobj::DbgPrint<ushort,ushort [24]>(ushort const *,ushort const (&)[24])
0x14004e54c  lea     r9, [r15+28h]
0x14004e550  mov     r8d, 1000h
0x14004e556  lea     rdx, aReplicatedFold; "Replicated Folder Stage"
0x14004e55d  mov     rcx, r12; this
0x14004e560  call    ?ReadStringValue@BaseRegKey@@QEAAPEAVFrsStatus@@PEBGGAEAV?$FrsStringImpl@GD@@@Z; BaseRegKey::ReadStringValue(ushort const *,ushort,FrsStringImpl<ushort,char> &)
0x14004e565  mov     rdi, rax
0x14004e568  test    rax, rax
0x14004e56b  jnz     loc_14004E860
0x14004e571  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14004e578  test    rax, rax
0x14004e57b  jz      short loc_14004E5A4
0x14004e57d  cmp     [rax+40h], ebx
0x14004e580  jz      short loc_14004E5A4
0x14004e582  cmp     [rax+38h], r13d
0x14004e586  jl      short loc_14004E5A4
0x14004e588  mov     [rbp+57h+var_B0], rsi
0x14004e58c  mov     [rbp+57h+var_A8], 5F0h
0x14004e593  mov     [rbp+57h+var_A4], r13d
0x14004e597  mov     [rbp+57h+var_A0], r14
0x14004e59b  lea     rcx, [rbp+57h+var_B0]
0x14004e59f  call    ??$DbgPrint@G$$BY0L@G@dbgobj@@QEAA_KPEBGAEAY0L@$$CBG@Z; dbgobj::DbgPrint<ushort,ushort [11]>(ushort const *,ushort const (&)[11])
0x14004e5a4  lea     r8, [r15+18h]; unsigned int *
0x14004e5a8  lea     rdx, aIsPrimary; "Is Primary"
0x14004e5af  mov     rcx, r12; this
0x14004e5b2  call    ?ReadDWordValue@BaseRegKey@@QEAAPEAVFrsStatus@@PEBGAEAK@Z; BaseRegKey::ReadDWordValue(ushort const *,ulong &)
0x14004e5b7  mov     rdi, rax
0x14004e5ba  test    rax, rax
0x14004e5bd  jnz     loc_14004E860
0x14004e5c3  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14004e5ca  test    rax, rax
0x14004e5cd  jz      short loc_14004E5F6
0x14004e5cf  cmp     [rax+40h], ebx
0x14004e5d2  jz      short loc_14004E5F6
0x14004e5d4  cmp     [rax+38h], r13d
0x14004e5d8  jl      short loc_14004E5F6
0x14004e5da  mov     [rbp+57h+var_B0], rsi
0x14004e5de  mov     [rbp+57h+var_A8], 5F9h
0x14004e5e5  mov     [rbp+57h+var_A4], r13d
0x14004e5e9  mov     [rbp+57h+var_A0], r14
0x14004e5ed  lea     rcx, [rbp+57h+var_B0]
0x14004e5f1  call    ??$DbgPrint@G$$BY0BA@G@dbgobj@@QEAA_KPEBGAEAY0BA@$$CBG@Z; dbgobj::DbgPrint<ushort,ushort [16]>(ushort const *,ushort const (&)[16])
0x14004e5f6  mov     r8d, 1000h
0x14004e5fc  mov     r9, r15
0x14004e5ff  lea     rdx, aParentComputer_0; "Parent Computer"
0x14004e606  mov     rcx, r12; this
0x14004e609  call    ?ReadStringValue@BaseRegKey@@QEAAPEAVFrsStatus@@PEBGGAEAV?$FrsStringImpl@GD@@@Z; BaseRegKey::ReadStringValue(ushort const *,ushort,FrsStringImpl<ushort,char> &)
0x14004e60e  mov     rdi, rax
0x14004e611  test    rax, rax
0x14004e614  jnz     loc_14004E860
0x14004e61a  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14004e621  test    rax, rax
0x14004e624  jz      short loc_14004E64D
0x14004e626  cmp     [rax+40h], ebx
0x14004e629  jz      short loc_14004E64D
0x14004e62b  cmp     [rax+38h], r13d
0x14004e62f  jl      short loc_14004E64D
0x14004e631  mov     [rbp+57h+var_B0], rsi
0x14004e635  mov     [rbp+57h+var_A8], 604h
0x14004e63c  mov     [rbp+57h+var_A4], r13d
0x14004e640  mov     [rbp+57h+var_A0], r14
0x14004e644  lea     rcx, [rbp+57h+var_B0]
0x14004e648  call    ??$DbgPrint@G$$BY07G@dbgobj@@QEAA_KPEBGAEAY07$$CBG@Z; dbgobj::DbgPrint<ushort,ushort [8]>(ushort const *,ushort const (&)[8])
0x14004e64d  lea     r9, [r15+38h]
0x14004e651  mov     r8d, 1000h
0x14004e657  lea     rdx, aCommand_0; "Command"
0x14004e65e  mov     rcx, r12; this
0x14004e661  call    ?ReadStringValue@BaseRegKey@@QEAAPEAVFrsStatus@@PEBGGAEAV?$FrsStringImpl@GD@@@Z; BaseRegKey::ReadStringValue(ushort const *,ushort,FrsStringImpl<ushort,char> &)
0x14004e666  mov     rdi, rax
0x14004e669  test    rax, rax
0x14004e66c  jnz     loc_14004E860
0x14004e672  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14004e679  test    rax, rax
0x14004e67c  jz      short loc_14004E6AC
0x14004e67e  cmp     [rax+40h], ebx
0x14004e681  jz      short loc_14004E6AC
0x14004e683  cmp     [rax+38h], r13d
0x14004e687  jl      short loc_14004E6AC
0x14004e689  mov     [rbp+57h+var_B0], rsi
0x14004e68d  mov     [rbp+57h+var_A8], 60Fh
0x14004e694  mov     [rbp+57h+var_A4], r13d
0x14004e698  mov     [rbp+57h+var_A0], r14
0x14004e69c  lea     r8, aReplicationGro_3; "Replication Group Guid"
0x14004e6a3  lea     rcx, [rbp+57h+var_B0]
0x14004e6a7  call    ??$DbgPrint@G$$BY0BH@G@dbgobj@@QEAA_KPEBGAEAY0BH@$$CBG@Z; dbgobj::DbgPrint<ushort,ushort [23]>(ushort const *,ushort const (&)[23])
0x14004e6ac  mov     r8d, 1000h
0x14004e6b2  lea     r9, [rbp+57h+arg_18]
0x14004e6b6  lea     rdx, aReplicationGro_3; "Replication Group Guid"
0x14004e6bd  mov     rcx, r12; this
0x14004e6c0  call    ?ReadStringValue@BaseRegKey@@QEAAPEAVFrsStatus@@PEBGGAEAV?$FrsStringImpl@GD@@@Z; BaseRegKey::ReadStringValue(ushort const *,ushort,FrsStringImpl<ushort,char> &)
0x14004e6c5  mov     rdi, rax
0x14004e6c8  mov     [rbp+57h+arg_0], rax
0x14004e6cc  mov     rsi, rax
0x14004e6cf  mov     r14, rax
0x14004e6d2  test    rax, rax
0x14004e6d5  jnz     short loc_14004E73E
  ... truncated ...
```
