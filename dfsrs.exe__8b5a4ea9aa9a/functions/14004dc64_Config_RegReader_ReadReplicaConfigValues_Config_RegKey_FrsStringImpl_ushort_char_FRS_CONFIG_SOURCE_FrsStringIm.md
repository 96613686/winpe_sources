# Config::RegReader::ReadReplicaConfigValues(Config::RegKey &,FrsStringImpl<ushort,char> *,_FRS_CONFIG_SOURCE *,FrsStringImpl<ushort,char> *)

- ea: `0x14004dc64`
- end: `0x14004e006`
- name: `?ReadReplicaConfigValues@RegReader@Config@@QEAAPEAVFrsStatus@@AEAVRegKey@2@PEAV?$FrsStringImpl@GD@@PEAW4_FRS_CONFIG_SOURCE@@1@Z`
- size: `930`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x14004c858`
- `0x14004e00c`
- `0x140060e4c`

## callees

- `0x14000c870`
- `0x14000cb00`
- `0x140010680`
- `0x140028eec`
- `0x140049e50`
- `0x14004d564`
- `0x14004d5b8`
- `0x14004d68c`
- `0x14004dc64`
- `0x1401af7b0`
- `0x1401af7c0`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14004ddc2`
- `KERNEL32!GetCurrentThreadId` at `0x14004de61`
- `KERNEL32!GetCurrentThreadId` at `0x14004df15`
- `KERNEL32!GetCurrentThreadId` at `0x14004dfab`
- `KERNEL32!GetCurrentThreadId` at `0x14004ddc2`
- `KERNEL32!GetCurrentThreadId` at `0x14004de61`
- `KERNEL32!GetCurrentThreadId` at `0x14004df15`
- `KERNEL32!GetCurrentThreadId` at `0x14004dfab`

## string_xrefs

- `0x14004dd5d`: `base\fs\remotefs\frs\src\config\reg.cpp`
- `0x14004de7d`: `base\fs\remotefs\frs\src\config\reg.cpp`
- `0x14004df01`: `base\fs\remotefs\frs\src\config\reg.cpp`
- `0x14004dfa4`: `base\fs\remotefs\frs\src\config\reg.cpp`
- `0x14004df7f`: `Failed to Read rVal:%ws`
- `0x14004dcd5`: `Config::RegReader::ReadReplicaConfigValues`
- `0x14004dd81`: `Config::RegReader::ReadReplicaConfigValues`
- `0x14004decf`: `Config::RegReader::ReadReplicaConfigValues`
- `0x14004dca5`: `Config::RegReader::ReadReplicaConfigValues`
- `0x14004dd64`: `Config::RegReader::ReadReplicaConfigValues`
- `0x14004de72`: `Config::RegReader::ReadReplicaConfigValues`
- `0x14004dcb4`: `Replica Set Configuration File`
- `0x14004dd9f`: `Config Source`
- `0x14004df74`: `Config Source`
- `0x14004de35`: `Unknown config source:%d`

## pseudocode

```c
__int64 __fastcall Config::RegReader::ReadReplicaConfigValues(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        __int64 a5)
{
  __int64 v5; // rsi
  __int64 v6; // rbx
  unsigned int *ConfigFilePath; // rdi
  unsigned __int16 *v11; // r14
  int StringValue; // eax
  DWORD v13; // eax
  __int64 v14; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v16; // rcx
  DWORD v17; // eax
  __int64 v18; // rcx
  DWORD v19; // eax
  __int64 v20; // rcx
  const wchar_t *v22; // [rsp+50h] [rbp-20h] BYREF
  int v23; // [rsp+58h] [rbp-18h]
  int v24; // [rsp+5Ch] [rbp-14h]
  const wchar_t *v25; // [rsp+60h] [rbp-10h]
  __int64 v26; // [rsp+A0h] [rbp+30h] BYREF

  v26 = a1;
  v5 = a5;
  v6 = 0;
  ConfigFilePath = 0;
  if ( a5 )
    FrsStringImpl<unsigned short,char>::SetEmpty(a5);
  if ( a3 )
  {
    ConfigFilePath = (unsigned int *)Config::RegConfig::ReadConfigFilePath(
                                       a1,
                                       a2,
                                       L"Replica Set Configuration File",
                                       a3);
    if ( ConfigFilePath )
      goto LABEL_32;
  }
  if ( dword_1403167F8 && v5 )
  {
    LODWORD(v26) = 0;
    v11 = 0;
    StringValue = ATL::CRegKey::QueryStringValue(
                    (ATL::CRegKey *)(a2 + 8),
                    L"Replica Set VCO Resource Name",
                    0,
                    (unsigned int *)&v26);
    if ( StringValue
      || (v11 = (unsigned __int16 *)operator_new(saturated_mul((unsigned int)(v26 + 1), 2u)),
          (StringValue = ATL::CRegKey::QueryStringValue(
                           (ATL::CRegKey *)(a2 + 8),
                           L"Replica Set VCO Resource Name",
                           v11,
                           (unsigned int *)&v26)) != 0) )
    {
      if ( StringValue != 2 )
      {
        CurrentThreadId = GetCurrentThreadId();
        ConfigFilePath = (unsigned int *)FrsStatusList::PushNewError(
                                           v16,
                                           9115,
                                           0,
                                           3,
                                           "base\\fs\\remotefs\\frs\\src\\config\\reg.cpp",
                                           "Config::RegReader::ReadReplicaConfigValues",
                                           1230,
                                           CurrentThreadId,
                                           0);
        if ( g_DebugLog )
        {
          if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
          {
            v23 = 1231;
            v22 = L"Config::RegReader::ReadReplicaConfigValues";
            v24 = 3;
            v25 = L"CREG";
            dbgobj::DbgPrint<unsigned short,unsigned short [30]>(&v22);
          }
        }
      }
    }
    else
    {
      FrsStringImpl<unsigned short,char>::Set(v5, v11);
    }
    if ( v11 )
      operator delete[](v11);
    if ( ConfigFilePath )
      goto LABEL_32;
  }
  if ( a4 )
  {
    *a4 = 0;
    LODWORD(v26) = 0;
    if ( (unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)(a2 + 8), L"Config Source", (unsigned int *)&v26) )
    {
      v17 = GetCurrentThreadId();
      ConfigFilePath = (unsigned int *)FrsStatusList::PushNewError(
                                         v18,
                                         9115,
                                         0,
                                         3,
                                         "base\\fs\\remotefs\\frs\\src\\config\\reg.cpp",
                                         "Config::RegReader::ReadReplicaConfigValues",
                                         1257,
                                         v17,
                                         0);
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v22 = L"Config::RegReader::ReadReplicaConfigValues";
        v25 = L"CREG";
        v23 = 1258;
        v24 = 3;
        dbgobj::DbgPrint<unsigned short,unsigned short [39]>(&v22, L"Failed to Read rVal:%ws", L"Config Source");
      }
    }
    else if ( (unsigned int)(v26 - 1) <= 1 )
    {
      *a4 = v26;
    }
    else
    {
      v13 = GetCurrentThreadId();
      ConfigFilePath = (unsigned int *)FrsStatusList::PushNewError(
                                         v14,
                                         9113,
                                         0,
                                         3,
                                         "base\\fs\\remotefs\\frs\\src\\config\\reg.cpp",
                                         "Config::RegReader::ReadReplicaConfigValues",
                                         1252,
                                         v13,
                                         0);
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v22 = L"Config::RegReader::ReadReplicaConfigValues";
        v25 = L"CREG";
        v23 = 1253;
        v24 = 4;
        dbgobj::DbgPrint<unsigned short,unsigned int>(&v22, L"Unknown config source:%d", &v26);
      }
    }
    if ( ConfigFilePath )
    {
LABEL_32:
      v19 = GetCurrentThreadId();
      return FrsStatusList::PushNewError(
               v20,
               ConfigFilePath[1],
               ConfigFilePath[2],
               *ConfigFilePath,
               "base\\fs\\remotefs\\frs\\src\\config\\reg.cpp",
               "Config::RegReader::ReadReplicaConfigValues",
               1262,
               v19,
               ConfigFilePath);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x14004dc64  mov     rax, rsp
0x14004dc67  mov     [rax+10h], rbx
0x14004dc6b  mov     [rax+18h], rsi
0x14004dc6f  mov     [rax+20h], rdi
0x14004dc73  mov     [rax+8], rcx
0x14004dc77  push    rbp
0x14004dc78  push    r12
0x14004dc7a  push    r13
0x14004dc7c  push    r14
0x14004dc7e  push    r15
0x14004dc80  mov     rbp, rsp
0x14004dc83  sub     rsp, 70h
0x14004dc87  mov     rsi, [rbp+arg_20]
0x14004dc8b  xor     ebx, ebx
0x14004dc8d  mov     r15, r9
0x14004dc90  mov     r14, r8
0x14004dc93  mov     r13, rdx
0x14004dc96  mov     edi, ebx
0x14004dc98  test    rsi, rsi
0x14004dc9b  jz      short loc_14004DCA5
0x14004dc9d  mov     rcx, rsi
0x14004dca0  call    ?SetEmpty@?$FrsStringImpl@GD@@QEAAXXZ; FrsStringImpl<ushort,char>::SetEmpty(void)
0x14004dca5  lea     r12, aConfigRegreade_9; "Config::RegReader::ReadReplicaConfigVal"...
0x14004dcac  test    r14, r14
0x14004dcaf  jz      short loc_14004DCCF
0x14004dcb1  mov     r9, r14
0x14004dcb4  lea     r8, aReplicaSetConf_0; "Replica Set Configuration File"
0x14004dcbb  mov     rdx, r13
0x14004dcbe  call    ?ReadConfigFilePath@RegConfig@Config@@QEAAPEAVFrsStatus@@AEAVRegKey@2@PEBGAEAV?$FrsStringImpl@GD@@@Z; Config::RegConfig::ReadConfigFilePath(Config::RegKey &,ushort const *,FrsStringImpl<ushort,char> &)
0x14004dcc3  mov     rdi, rax
0x14004dcc6  test    rax, rax
0x14004dcc9  jnz     loc_14004DFA4
0x14004dccf  cmp     cs:dword_1403167F8, ebx
0x14004dcd5  lea     r14, aConfigRegreade_2; "Config::RegReader::ReadReplicaConfigVal"...
0x14004dcdc  jz      loc_14004DF01
0x14004dce2  test    rsi, rsi
0x14004dce5  jz      loc_14004DF01
0x14004dceb  lea     r9, [rbp+arg_0]; unsigned int *
0x14004dcef  mov     dword ptr [rbp+arg_0], ebx
0x14004dcf2  xor     r8d, r8d; unsigned __int16 *
0x14004dcf5  lea     rdx, aReplicaSetVcoR; "Replica Set VCO Resource Name"
0x14004dcfc  lea     rcx, [r13+8]; this
0x14004dd00  mov     r14, rbx
0x14004dd03  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14004dd08  test    eax, eax
0x14004dd0a  jnz     loc_14004DE58
0x14004dd10  mov     ecx, dword ptr [rbp+arg_0]
0x14004dd13  mov     eax, 2
0x14004dd18  inc     ecx
0x14004dd1a  mul     rcx
0x14004dd1d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14004dd24  cmovo   rax, rcx
0x14004dd28  mov     rcx, rax; unsigned __int64
0x14004dd2b  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x14004dd30  lea     r9, [rbp+arg_0]; unsigned int *
0x14004dd34  mov     r8, rax; unsigned __int16 *
0x14004dd37  lea     rdx, aReplicaSetVcoR; "Replica Set VCO Resource Name"
0x14004dd3e  mov     r14, rax
0x14004dd41  lea     rcx, [r13+8]; this
0x14004dd45  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14004dd4a  test    eax, eax
0x14004dd4c  jnz     loc_14004DE58
0x14004dd52  mov     rdx, r14
0x14004dd55  mov     rcx, rsi
0x14004dd58  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x14004dd5d  lea     rsi, aBaseFsRemotefs_47; "base\\fs\\remotefs\\frs\\src\\config\\r"...
0x14004dd64  lea     r12, aConfigRegreade_9; "Config::RegReader::ReadReplicaConfigVal"...
0x14004dd6b  test    r14, r14
0x14004dd6e  jz      short loc_14004DD78
0x14004dd70  mov     rcx, r14; Block
0x14004dd73  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x14004dd78  test    rdi, rdi
0x14004dd7b  jnz     loc_14004DFAB
0x14004dd81  lea     r14, aConfigRegreade_2; "Config::RegReader::ReadReplicaConfigVal"...
0x14004dd88  test    r15, r15
0x14004dd8b  jz      loc_14004DFE4
0x14004dd91  lea     rcx, [r13+8]; this
0x14004dd95  mov     [r15], ebx
0x14004dd98  lea     r8, [rbp+arg_0]; unsigned int *
0x14004dd9c  mov     dword ptr [rbp+arg_0], ebx
0x14004dd9f  lea     rdx, aConfigSource; "Config Source"
0x14004dda6  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x14004ddab  test    eax, eax
0x14004ddad  jnz     loc_14004DF15
0x14004ddb3  mov     ecx, dword ptr [rbp+arg_0]
0x14004ddb6  lea     eax, [rcx-1]
0x14004ddb9  cmp     eax, 1
0x14004ddbc  jbe     loc_14004DF0D
0x14004ddc2  call    cs:__imp_GetCurrentThreadId
0x14004ddc9  nop     dword ptr [rax+rax+00h]
0x14004ddce  mov     [rsp+70h+var_30], rbx
0x14004ddd3  mov     r9d, 3
0x14004ddd9  mov     [rsp+70h+var_38], eax
0x14004dddd  xor     r8d, r8d
0x14004dde0  mov     [rsp+70h+var_40], 4E4h
0x14004dde8  mov     edx, 2399h
0x14004dded  mov     [rsp+70h+var_48], r12
0x14004ddf2  mov     [rsp+70h+var_50], rsi
0x14004ddf7  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14004ddfc  mov     rdi, rax
0x14004ddff  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14004de06  test    rax, rax
0x14004de09  jz      loc_14004DF9D
0x14004de0f  cmp     [rax+40h], ebx
0x14004de12  jz      loc_14004DF9D
0x14004de18  cmp     dword ptr [rax+38h], 4
0x14004de1c  jl      loc_14004DF9D
0x14004de22  lea     rax, aCreg; "CREG"
0x14004de29  mov     [rbp+var_20], r14
0x14004de2d  lea     r8, [rbp+arg_0]
0x14004de31  mov     [rbp+var_10], rax
0x14004de35  lea     rdx, aUnknownConfigS_0; "Unknown config source:%d"
0x14004de3c  mov     [rbp+var_18], 4E5h
0x14004de43  lea     rcx, [rbp+var_20]
0x14004de47  mov     [rbp+var_14], 4
0x14004de4e  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x14004de53  jmp     loc_14004DF9D
0x14004de58  cmp     eax, 2
0x14004de5b  jz      loc_14004DD5D
0x14004de61  call    cs:__imp_GetCurrentThreadId
0x14004de68  nop     dword ptr [rax+rax+00h]
0x14004de6d  mov     [rsp+70h+var_30], rbx
0x14004de72  lea     r12, aConfigRegreade_9; "Config::RegReader::ReadReplicaConfigVal"...
0x14004de79  mov     [rsp+70h+var_38], eax
0x14004de7d  lea     rsi, aBaseFsRemotefs_47; "base\\fs\\remotefs\\frs\\src\\config\\r"...
0x14004de84  mov     [rsp+70h+var_40], 4CEh
0x14004de8c  mov     r9d, 3
0x14004de92  mov     [rsp+70h+var_48], r12
0x14004de97  xor     r8d, r8d
0x14004de9a  mov     edx, 239Bh
0x14004de9f  mov     [rsp+70h+var_50], rsi
0x14004dea4  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14004dea9  mov     rdi, rax
0x14004deac  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14004deb3  test    rax, rax
0x14004deb6  jz      loc_14004DD6B
0x14004debc  cmp     [rax+40h], ebx
0x14004debf  jz      loc_14004DD6B
0x14004dec5  cmp     dword ptr [rax+38h], 3
0x14004dec9  jl      loc_14004DD6B
0x14004decf  lea     rax, aConfigRegreade_2; "Config::RegReader::ReadReplicaConfigVal"...
0x14004ded6  mov     [rbp+var_18], 4CFh
0x14004dedd  mov     [rbp+var_20], rax
0x14004dee1  lea     rcx, [rbp+var_20]
0x14004dee5  lea     rax, aCreg; "CREG"
0x14004deec  mov     [rbp+var_14], 3
0x14004def3  mov     [rbp+var_10], rax
0x14004def7  call    ??$DbgPrint@G$$BY0BO@G@dbgobj@@QEAA_KPEBGAEAY0BO@$$CBG@Z; dbgobj::DbgPrint<ushort,ushort [30]>(ushort const *,ushort const (&)[30])
0x14004defc  jmp     loc_14004DD6B
0x14004df01  lea     rsi, aBaseFsRemotefs_47; "base\\fs\\remotefs\\frs\\src\\config\\r"...
0x14004df08  jmp     loc_14004DD88
0x14004df0d  mov     [r15], ecx
0x14004df10  jmp     loc_14004DF9D
0x14004df15  call    cs:__imp_GetCurrentThreadId
0x14004df1c  nop     dword ptr [rax+rax+00h]
0x14004df21  mov     [rsp+70h+var_30], rbx
0x14004df26  mov     r9d, 3
0x14004df2c  mov     [rsp+70h+var_38], eax
0x14004df30  xor     r8d, r8d
0x14004df33  mov     [rsp+70h+var_40], 4E9h
0x14004df3b  mov     edx, 239Bh
0x14004df40  mov     [rsp+70h+var_48], r12
0x14004df45  mov     [rsp+70h+var_50], rsi
0x14004df4a  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14004df4f  mov     rdi, rax
0x14004df52  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14004df59  test    rax, rax
0x14004df5c  jz      short loc_14004DF9D
0x14004df5e  cmp     [rax+40h], ebx
0x14004df61  jz      short loc_14004DF9D
0x14004df63  cmp     dword ptr [rax+38h], 3
0x14004df67  jl      short loc_14004DF9D
0x14004df69  lea     rax, aCreg; "CREG"
0x14004df70  mov     [rbp+var_20], r14
0x14004df74  lea     r8, aConfigSource; "Config Source"
0x14004df7b  mov     [rbp+var_10], rax
0x14004df7f  lea     rdx, aFailedToReadRv; "Failed to Read rVal:%ws"
0x14004df86  mov     [rbp+var_18], 4EAh
0x14004df8d  lea     rcx, [rbp+var_20]
0x14004df91  mov     [rbp+var_14], 3
0x14004df98  call    ??$DbgPrint@G$$BY0CH@G@dbgobj@@QEAA_KPEBGAEAY0CH@$$CBG@Z; dbgobj::DbgPrint<ushort,ushort [39]>(ushort const *,ushort const (&)[39])
0x14004df9d  test    rdi, rdi
0x14004dfa0  jz      short loc_14004DFE4
0x14004dfa2  jmp     short loc_14004DFAB
0x14004dfa4  lea     rsi, aBaseFsRemotefs_47; "base\\fs\\remotefs\\frs\\src\\config\\r"...
0x14004dfab  call    cs:__imp_GetCurrentThreadId
0x14004dfb2  nop     dword ptr [rax+rax+00h]
0x14004dfb7  mov     r9d, [rdi]
0x14004dfba  mov     r8d, [rdi+8]
0x14004dfbe  mov     edx, [rdi+4]
0x14004dfc1  mov     [rsp+70h+var_30], rdi
0x14004dfc6  mov     [rsp+70h+var_38], eax
0x14004dfca  mov     [rsp+70h+var_40], 4EEh
0x14004dfd2  mov     [rsp+70h+var_48], r12
0x14004dfd7  mov     [rsp+70h+var_50], rsi
0x14004dfdc  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14004dfe1  mov     rbx, rax
0x14004dfe4  lea     r11, [rsp+70h+var_s0]
0x14004dfe9  mov     rax, rbx
0x14004dfec  mov     rbx, [r11+38h]
0x14004dff0  mov     rsi, [r11+40h]
0x14004dff4  mov     rdi, [r11+48h]
0x14004dff8  mov     rsp, r11
0x14004dffb  pop     r15
0x14004dffd  pop     r14
0x14004dfff  pop     r13
0x14004e001  pop     r12
0x14004e003  pop     rbp
0x14004e004  retn
```
