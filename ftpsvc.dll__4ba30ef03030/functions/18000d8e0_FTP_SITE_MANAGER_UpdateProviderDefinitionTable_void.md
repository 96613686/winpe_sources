# FTP_SITE_MANAGER::UpdateProviderDefinitionTable(void)

- ea: `0x18000d8e0`
- end: `0x18000de58`
- name: `?UpdateProviderDefinitionTable@FTP_SITE_MANAGER@@AEAAJXZ`
- size: `1400`
- prototype: `__int64 __fastcall(FTP_SITE_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000cb74`

## callees

- `0x180001210`
- `0x180001250`
- `0x18000b0bc`
- `0x18000b888`
- `0x18000d8e0`
- `0x18001908c`
- `0x18002b488`
- `0x18002b5bc`
- `0x18002b65c`
- `0x180049010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000dc5f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dc6d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dc79`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dc83`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dd3f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dd52`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dd8b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dc5f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dc6d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dc79`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dc83`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dd3f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dd52`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dd8b`
- `OLEAUT32!__imp_VariantInit` at `0x18000d942`
- `OLEAUT32!__imp_VariantInit` at `0x18000d942`
- `OLEAUT32!__imp_VariantClear` at `0x18000dd0b`
- `OLEAUT32!__imp_VariantClear` at `0x18000dd0b`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18000d956`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18000d956`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000dc02`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000dc02`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000dba7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000dbba`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000dbd3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000dba7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000dbba`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000dbd3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000db45`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000db5d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000db78`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000db45`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000db5d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000db78`
- `iisutil!PuDbgPrintError` at `0x18000dce8`
- `iisutil!PuDbgPrintError` at `0x18000dce8`

## string_xrefs

- `0x18000dab9`: `clsid`
- `0x18000dccd`: `FTP_SITE_MANAGER::UpdateProviderDefinitionTable`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FTP_SITE_MANAGER::UpdateProviderDefinitionTable(FTP_SITE_MANAGER *this)
{
  volatile signed __int32 *v2; // rsi
  char *v3; // rdi
  struct IAppHostAdminManager *v4; // r14
  int Section; // ebx
  struct IErrorInfo *v6; // r13
  FTP_LOG_NT_EVENT_TABLE *v7; // rax
  unsigned int v8; // eax
  LONG v9; // r14d
  const unsigned __int16 *v10; // r12
  const unsigned __int16 *v11; // r15
  BSTR v13; // [rsp+30h] [rbp-69h] BYREF
  BSTR v14; // [rsp+38h] [rbp-61h] BYREF
  void *Block; // [rsp+40h] [rbp-59h] BYREF
  struct IAppHostElement *v16; // [rsp+48h] [rbp-51h] BYREF
  __int64 v17; // [rsp+50h] [rbp-49h] BYREF
  struct IAppHostElementCollection *v18; // [rsp+58h] [rbp-41h] BYREF
  struct IAppHostElement *v19; // [rsp+60h] [rbp-39h] BYREF
  struct IErrorInfo *v20; // [rsp+68h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-29h] BYREF
  char *v22; // [rsp+88h] [rbp-11h]
  VARIANTARG v23; // [rsp+90h] [rbp-9h] BYREF
  unsigned int v24; // [rsp+100h] [rbp+67h] BYREF
  struct IAppHostAdminManager *v25; // [rsp+108h] [rbp+6Fh]
  struct IAppHostElement *v26; // [rsp+110h] [rbp+77h] BYREF
  BSTR bstrString; // [rsp+118h] [rbp+7Fh] BYREF

  v16 = 0;
  v17 = 0;
  v26 = 0;
  v19 = 0;
  v18 = 0;
  v20 = 0;
  v24 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  bstrString = 0;
  v13 = 0;
  v14 = 0;
  v2 = 0;
  Block = 0;
  v3 = 0;
  VariantInit(&pvarg);
  v22 = (char *)this + 200;
  CLKRHashTable::Clear((FTP_SITE_MANAGER *)((char *)this + 200));
  v4 = (struct IAppHostAdminManager *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 24LL))(g_pFtpServer);
  v25 = v4;
  Section = Config_GetSection(v4, L"system.ftpServer/providerDefinitions", L"MACHINE/WEBROOT/APPHOST", &v16, &v20);
  v6 = v20;
  if ( Section < 0 )
  {
    v7 = (FTP_LOG_NT_EVENT_TABLE *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 40LL))(g_pFtpServer);
    FTP_LOG_NT_EVENT_TABLE::LogEventConfigError(v7, v6, Section);
    goto LABEL_41;
  }
  Section = ((__int64 (__fastcall *)(struct IAppHostElement *, __int64 *))v16->lpVtbl->get_Collection)(v16, &v17);
  if ( Section >= 0 )
  {
    Section = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v17 + 24LL))(v17, &v24);
    if ( Section >= 0 )
    {
      v8 = v24;
      if ( v24 )
      {
        Section = Config_GetSubElement(v16, L"activation", &v19);
        if ( Section < 0 )
          goto LABEL_41;
        Section = ((__int64 (__fastcall *)(struct IAppHostElement *, struct IAppHostElementCollection **))v19->lpVtbl->get_Collection)(
                    v19,
                    &v18);
        if ( Section < 0 )
          goto LABEL_41;
        v8 = v24;
      }
      v9 = 0;
      if ( v8 )
      {
        while ( 1 )
        {
          pvarg.vt = 19;
          pvarg.lVal = v9;
          v23 = pvarg;
          Section = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, struct IAppHostElement **))(*(_QWORD *)v17 + 32LL))(
                      v17,
                      &v23,
                      &v26);
          if ( Section < 0 )
            goto LABEL_39;
          Section = Config_GetStringProperty(v26, L"name", &bstrString);
          if ( Section < 0 )
            goto LABEL_39;
          Section = Config_GetStringProperty(v26, L"clsid", &v13);
          if ( Section < 0 )
            goto LABEL_39;
          Section = Config_GetStringProperty(v26, L"type", &v14);
          if ( Section < 0 )
            goto LABEL_39;
          Section = FTP_SITE_MANAGER::GetCustomProviderConfiguration(
                      v18,
                      bstrString,
                      (struct ATTRIBUTE_SAFEARRAY **)&Block);
          if ( Section < 0 )
          {
            v2 = (volatile signed __int32 *)Block;
LABEL_39:
            v3 = 0;
            goto LABEL_40;
          }
          v3 = (char *)operator new(0x220u);
          v20 = (struct IErrorInfo *)v3;
          if ( v3 )
          {
            *(_QWORD *)v3 = &FTP_PROVIDER_DEFINITION::`vftable';
            *((_DWORD *)v3 + 3) = 1;
            *((_QWORD *)v3 + 2) = 0;
            STRU::STRU((STRU *)(v3 + 24), (unsigned __int16 *)v3 + 40, 0x10u);
            STRU::STRU((STRU *)(v3 + 112), (unsigned __int16 *)v3 + 84, 0x20u);
            STRU::STRU((STRU *)(v3 + 232), (unsigned __int16 *)v3 + 144, 0x80u);
            *((_DWORD *)v3 + 2) = 1146115142;
          }
          else
          {
            v3 = 0;
          }
          v2 = (volatile signed __int32 *)Block;
          if ( !v3 )
          {
            Section = -2147024888;
            goto LABEL_40;
          }
          v10 = v14;
          v11 = v13;
          Section = STRU::Copy((STRU *)(v3 + 24), bstrString);
          if ( Section >= 0
            && (Section = STRU::Copy((STRU *)(v3 + 112), v11), Section >= 0)
            && (Section = STRU::Copy((STRU *)(v3 + 232), v10), Section >= 0)
            && v2 )
          {
            _InterlockedIncrement(v2);
            *((_QWORD *)v3 + 2) = v2;
          }
          else if ( Section < 0 )
          {
            goto LABEL_40;
          }
          if ( (unsigned int)CLKRHashTable::InsertRecord(v22, v3, 0) )
            break;
          if ( v2 )
          {
            if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
            {
              ATTRIBUTE_SAFEARRAY::~ATTRIBUTE_SAFEARRAY((ATTRIBUTE_SAFEARRAY *)v2);
              operator delete((void *)v2);
            }
            v2 = 0;
            Block = 0;
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3 + 3, 0xFFFFFFFF) == 1 )
            (**(void (__fastcall ***)(void *, __int64))v3)(v3, 1);
          v3 = 0;
          SysFreeString(bstrString);
          bstrString = 0;
          SysFreeString(v13);
          v13 = 0;
          SysFreeString(0);
          SysFreeString(v14);
          v14 = 0;
          ((void (__fastcall *)(struct IAppHostElement *))v26->lpVtbl->Release)(v26);
          v26 = 0;
          if ( ++v9 >= v24 )
            goto LABEL_40;
        }
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_site_manager.cxx",
            2081,
            "FTP_SITE_MANAGER::UpdateProviderDefinitionTable",
            -2147467259,
            "Failed to add new provider definition to the hash table\n");
        Section = -2147467259;
      }
LABEL_40:
      v4 = v25;
    }
  }
LABEL_41:
  VariantClear(&pvarg);
  if ( v3 && _InterlockedExchangeAdd((volatile signed __int32 *)v3 + 3, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(void *, __int64))v3)(v3, 1);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v13 )
  {
    SysFreeString(v13);
    v13 = 0;
  }
  if ( v2 && _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
  {
    ATTRIBUTE_SAFEARRAY::~ATTRIBUTE_SAFEARRAY((ATTRIBUTE_SAFEARRAY *)v2);
    operator delete((void *)v2);
  }
  if ( v14 )
  {
    SysFreeString(v14);
    v14 = 0;
  }
  if ( v16 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v16->lpVtbl->Release)(v16);
    v16 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v26 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v26->lpVtbl->Release)(v26);
    v26 = 0;
  }
  if ( v18 )
  {
    ((void (__fastcall *)(struct IAppHostElementCollection *))v18->lpVtbl->Release)(v18);
    v18 = 0;
  }
  if ( v19 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v19->lpVtbl->Release)(v19);
    v19 = 0;
  }
  if ( v6 )
    ((void (__fastcall *)(struct IErrorInfo *))v6->lpVtbl->Release)(v6);
  if ( v4 )
    (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 208LL))(g_pFtpServer);
  return (unsigned int)Section;
}

```

## disassembly

```asm
0x18000d8e0  push    rbp
0x18000d8e2  push    rbx
0x18000d8e3  push    rsi
0x18000d8e4  push    rdi
0x18000d8e5  push    r12
0x18000d8e7  push    r13
0x18000d8e9  push    r14
0x18000d8eb  push    r15
0x18000d8ed  lea     rbp, [rsp-1Fh]
0x18000d8f2  sub     rsp, 0B8h
0x18000d8f9  mov     rbx, rcx
0x18000d8fc  xor     r15d, r15d
0x18000d8ff  mov     [rbp+57h+var_A8], r15
0x18000d903  mov     [rbp+57h+var_A0], r15
0x18000d907  mov     [rbp+57h+arg_10], r15
0x18000d90b  mov     [rbp+57h+var_90], r15
0x18000d90f  mov     [rbp+57h+var_98], r15
0x18000d913  mov     [rbp+57h+var_88], r15
0x18000d917  mov     [rbp+57h+arg_0], r15d
0x18000d91b  xorps   xmm0, xmm0
0x18000d91e  xor     eax, eax
0x18000d920  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18000d924  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18000d928  mov     [rbp+57h+bstrString], r15
0x18000d92c  mov     [rbp+57h+var_C0], r15
0x18000d930  mov     [rbp+57h+var_B8], r15
0x18000d934  mov     esi, r15d
0x18000d937  mov     [rbp+57h+Block], r15
0x18000d93b  mov     edi, r15d
0x18000d93e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000d942  call    cs:__imp_VariantInit
0x18000d948  lea     rax, [rbx+0C8h]
0x18000d94f  mov     [rbp+57h+var_68], rax
0x18000d953  mov     rcx, rax
0x18000d956  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x18000d95c  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000d963  mov     rax, [rcx]
0x18000d966  mov     rax, [rax+18h]
0x18000d96a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d96f  mov     r14, rax
0x18000d972  mov     [rbp+57h+arg_8], rax
0x18000d976  lea     rax, [rbp+57h+var_88]
0x18000d97a  mov     [rsp+0F0h+var_D0], rax; struct IErrorInfo **
0x18000d97f  lea     r9, [rbp+57h+var_A8]; struct IAppHostElement **
0x18000d983  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18000d98a  lea     rdx, aSystemFtpserve_1; "system.ftpServer/providerDefinitions"
0x18000d991  mov     rcx, r14; struct IAppHostAdminManager *
0x18000d994  call    ?Config_GetSection@@YAJPEAUIAppHostAdminManager@@PEBG1PEAPEAUIAppHostElement@@PEAPEAUIErrorInfo@@@Z; Config_GetSection(IAppHostAdminManager *,ushort const *,ushort const *,IAppHostElement * *,IErrorInfo * *)
0x18000d999  mov     ebx, eax
0x18000d99b  mov     r13, [rbp+57h+var_88]
0x18000d99f  test    eax, eax
0x18000d9a1  jns     short loc_18000D9C9
0x18000d9a3  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000d9aa  mov     rdx, [rcx]
0x18000d9ad  mov     rax, [rdx+28h]
0x18000d9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9b6  mov     r8d, ebx; int
0x18000d9b9  mov     rdx, r13; struct IErrorInfo *
0x18000d9bc  mov     rcx, rax; this
0x18000d9bf  call    ?LogEventConfigError@FTP_LOG_NT_EVENT_TABLE@@QEAAXPEAUIErrorInfo@@J@Z; FTP_LOG_NT_EVENT_TABLE::LogEventConfigError(IErrorInfo *,long)
0x18000d9c4  jmp     loc_18000DD07
0x18000d9c9  mov     rcx, [rbp+57h+var_A8]
0x18000d9cd  mov     rax, [rcx]
0x18000d9d0  lea     rdx, [rbp+57h+var_A0]
0x18000d9d4  mov     rax, [rax+20h]
0x18000d9d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9dd  mov     ebx, eax
0x18000d9df  test    eax, eax
0x18000d9e1  js      loc_18000DD07
0x18000d9e7  mov     rcx, [rbp+57h+var_A0]
0x18000d9eb  mov     rax, [rcx]
0x18000d9ee  lea     rdx, [rbp+57h+arg_0]
0x18000d9f2  mov     rax, [rax+18h]
0x18000d9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9fb  mov     ebx, eax
0x18000d9fd  test    eax, eax
0x18000d9ff  js      loc_18000DD07
0x18000da05  mov     eax, [rbp+57h+arg_0]
0x18000da08  test    eax, eax
0x18000da0a  jz      short loc_18000DA4B
0x18000da0c  lea     r8, [rbp+57h+var_90]; struct IAppHostElement **
0x18000da10  lea     rdx, aActivation; "activation"
0x18000da17  mov     rcx, [rbp+57h+var_A8]; struct IAppHostElement *
0x18000da1b  call    ?Config_GetSubElement@@YAJPEAUIAppHostElement@@PEBGPEAPEAU1@@Z; Config_GetSubElement(IAppHostElement *,ushort const *,IAppHostElement * *)
0x18000da20  mov     ebx, eax
0x18000da22  test    eax, eax
0x18000da24  js      loc_18000DD07
0x18000da2a  mov     rcx, [rbp+57h+var_90]
0x18000da2e  mov     rax, [rcx]
0x18000da31  lea     rdx, [rbp+57h+var_98]
0x18000da35  mov     rax, [rax+20h]
0x18000da39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da3e  mov     ebx, eax
0x18000da40  test    eax, eax
0x18000da42  js      loc_18000DD07
0x18000da48  mov     eax, [rbp+57h+arg_0]
0x18000da4b  mov     r14d, r15d
0x18000da4e  test    eax, eax
0x18000da50  jz      loc_18000DD03
0x18000da56  mov     eax, 13h
0x18000da5b  mov     word ptr [rbp+57h+pvarg], ax
0x18000da5f  mov     dword ptr [rbp+57h+pvarg+8], r14d
0x18000da63  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18000da67  movaps  [rbp+57h+var_60], xmm0
0x18000da6b  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18000da70  movsd   [rbp+57h+var_50], xmm1
0x18000da75  mov     rcx, [rbp+57h+var_A0]
0x18000da79  mov     rax, [rcx]
0x18000da7c  lea     r8, [rbp+57h+arg_10]
0x18000da80  lea     rdx, [rbp+57h+var_60]
0x18000da84  mov     rax, [rax+20h]
0x18000da88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da8d  mov     ebx, eax
0x18000da8f  test    eax, eax
0x18000da91  js      loc_18000DD00
0x18000da97  lea     r8, [rbp+57h+bstrString]; unsigned __int16 **
0x18000da9b  lea     rdx, aName; "name"
0x18000daa2  mov     rcx, [rbp+57h+arg_10]; struct IAppHostElement *
0x18000daa6  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x18000daab  mov     ebx, eax
0x18000daad  test    eax, eax
0x18000daaf  js      loc_18000DD00
0x18000dab5  lea     r8, [rbp+57h+var_C0]; unsigned __int16 **
0x18000dab9  lea     rdx, aClsid; "clsid"
0x18000dac0  mov     rcx, [rbp+57h+arg_10]; struct IAppHostElement *
0x18000dac4  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x18000dac9  mov     ebx, eax
0x18000dacb  test    eax, eax
0x18000dacd  js      loc_18000DD00
0x18000dad3  lea     r8, [rbp+57h+var_B8]; unsigned __int16 **
0x18000dad7  lea     rdx, aType; "type"
0x18000dade  mov     rcx, [rbp+57h+arg_10]; struct IAppHostElement *
0x18000dae2  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x18000dae7  mov     ebx, eax
0x18000dae9  test    eax, eax
0x18000daeb  js      loc_18000DD00
0x18000daf1  lea     r8, [rbp+57h+Block]; struct ATTRIBUTE_SAFEARRAY **
0x18000daf5  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x18000daf9  mov     rcx, [rbp+57h+var_98]; struct IAppHostElementCollection *
0x18000dafd  call    ?GetCustomProviderConfiguration@FTP_SITE_MANAGER@@CAJPEAUIAppHostElementCollection@@QEAGPEAPEAVATTRIBUTE_SAFEARRAY@@@Z; FTP_SITE_MANAGER::GetCustomProviderConfiguration(IAppHostElementCollection *,ushort * const,ATTRIBUTE_SAFEARRAY * *)
0x18000db02  mov     ebx, eax
0x18000db04  test    eax, eax
0x18000db06  js      loc_18000DCFC
0x18000db0c  mov     ecx, 220h; Size
0x18000db11  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000db16  mov     rdi, rax
0x18000db19  mov     [rbp+57h+var_88], rax
0x18000db1d  test    rax, rax
0x18000db20  jz      short loc_18000DB87
0x18000db22  lea     rax, ??_7FTP_PROVIDER_DEFINITION@@6B@; const FTP_PROVIDER_DEFINITION::`vftable'
0x18000db29  mov     [rdi], rax
0x18000db2c  mov     dword ptr [rdi+0Ch], 1
0x18000db33  mov     [rdi+10h], r15
0x18000db37  lea     rdx, [rdi+50h]
0x18000db3b  lea     rcx, [rdi+18h]
0x18000db3f  mov     r8d, 10h
0x18000db45  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000db4b  nop
0x18000db4c  lea     rdx, [rdi+0A8h]
0x18000db53  lea     rcx, [rdi+70h]
0x18000db57  mov     r8d, 20h ; ' '
0x18000db5d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000db63  nop
0x18000db64  lea     rdx, [rdi+120h]
0x18000db6b  lea     rcx, [rdi+0E8h]
0x18000db72  mov     r8d, 80h
0x18000db78  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000db7e  mov     dword ptr [rdi+8], 44505446h
0x18000db85  jmp     short loc_18000DB8A
0x18000db87  mov     rdi, r15
0x18000db8a  mov     rsi, [rbp+57h+Block]
0x18000db8e  test    rdi, rdi
0x18000db91  jz      loc_18000DCF5
0x18000db97  mov     r12, [rbp+57h+var_B8]
0x18000db9b  mov     r15, [rbp+57h+var_C0]
0x18000db9f  lea     rcx, [rdi+18h]
0x18000dba3  mov     rdx, [rbp+57h+bstrString]
0x18000dba7  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000dbad  mov     ebx, eax
0x18000dbaf  test    eax, eax
0x18000dbb1  js      short loc_18000DBED
0x18000dbb3  lea     rcx, [rdi+70h]
0x18000dbb7  mov     rdx, r15
0x18000dbba  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000dbc0  mov     ebx, eax
0x18000dbc2  xor     r15d, r15d
0x18000dbc5  test    eax, eax
0x18000dbc7  js      short loc_18000DBF0
0x18000dbc9  lea     rcx, [rdi+0E8h]
0x18000dbd0  mov     rdx, r12
0x18000dbd3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000dbd9  mov     ebx, eax
0x18000dbdb  test    eax, eax
0x18000dbdd  js      short loc_18000DBF0
0x18000dbdf  test    rsi, rsi
0x18000dbe2  jz      short loc_18000DBF0
0x18000dbe4  lock inc dword ptr [rsi]
0x18000dbe7  mov     [rdi+10h], rsi
0x18000dbeb  jmp     short loc_18000DBF8
0x18000dbed  xor     r15d, r15d
0x18000dbf0  test    ebx, ebx
0x18000dbf2  js      loc_18000DD03
0x18000dbf8  xor     r8d, r8d
0x18000dbfb  mov     rdx, rdi
0x18000dbfe  mov     rcx, [rbp+57h+var_68]
0x18000dc02  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18000dc08  test    eax, eax
0x18000dc0a  jnz     loc_18000DCB0
0x18000dc10  test    rsi, rsi
0x18000dc13  jz      short loc_18000DC38
0x18000dc15  or      eax, 0FFFFFFFFh
0x18000dc18  lock xadd [rsi], eax
0x18000dc1c  cmp     eax, 1
0x18000dc1f  jnz     short loc_18000DC31
0x18000dc21  mov     rcx, rsi; this
0x18000dc24  call    ??1ATTRIBUTE_SAFEARRAY@@AEAA@XZ; ATTRIBUTE_SAFEARRAY::~ATTRIBUTE_SAFEARRAY(void)
0x18000dc29  mov     rcx, rsi; Block
0x18000dc2c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dc31  mov     rsi, r15
0x18000dc34  mov     [rbp+57h+Block], r15
0x18000dc38  or      eax, 0FFFFFFFFh
0x18000dc3b  lock xadd [rdi+0Ch], eax
0x18000dc40  cmp     eax, 1
0x18000dc43  jnz     short loc_18000DC58
0x18000dc45  mov     rax, [rdi]
0x18000dc48  mov     edx, 1
0x18000dc4d  mov     rcx, rdi
0x18000dc50  mov     rax, [rax]
0x18000dc53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc58  mov     rdi, r15
0x18000dc5b  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000dc5f  call    cs:__imp_SysFreeString
0x18000dc65  mov     [rbp+57h+bstrString], r15
0x18000dc69  mov     rcx, [rbp+57h+var_C0]; bstrString
0x18000dc6d  call    cs:__imp_SysFreeString
0x18000dc73  mov     [rbp+57h+var_C0], r15
0x18000dc77  xor     ecx, ecx; bstrString
0x18000dc79  call    cs:__imp_SysFreeString
0x18000dc7f  mov     rcx, [rbp+57h+var_B8]; bstrString
0x18000dc83  call    cs:__imp_SysFreeString
0x18000dc89  mov     [rbp+57h+var_B8], r15
0x18000dc8d  mov     rcx, [rbp+57h+arg_10]
0x18000dc91  mov     rax, [rcx]
0x18000dc94  mov     rax, [rax+10h]
0x18000dc98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc9d  mov     [rbp+57h+arg_10], r15
0x18000dca1  inc     r14d
0x18000dca4  cmp     r14d, [rbp+57h+arg_0]
0x18000dca8  jb      loc_18000DA56
0x18000dcae  jmp     short loc_18000DD03
0x18000dcb0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000dcb7  jz      short loc_18000DCEE
0x18000dcb9  lea     rax, aFailedToAddNew_0; "Failed to add new provider definition t"...
0x18000dcc0  mov     [rsp+0F0h+var_C8], rax
0x18000dcc5  mov     dword ptr [rsp+0F0h+var_D0], 80004005h
0x18000dccd  lea     r9, aFtpSiteManager; "FTP_SITE_MANAGER::UpdateProviderDefinit"...
0x18000dcd4  mov     r8d, 821h
0x18000dcda  lea     rdx, aInetsrvIisIisr_18; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000dce1  mov     rcx, cs:g_pDebug
0x18000dce8  call    cs:__imp_PuDbgPrintError
0x18000dcee  mov     ebx, 80004005h
0x18000dcf3  jmp     short loc_18000DD03
0x18000dcf5  mov     ebx, 80070008h
0x18000dcfa  jmp     short loc_18000DD03
0x18000dcfc  mov     rsi, [rbp+57h+Block]
0x18000dd00  mov     rdi, r15
0x18000dd03  mov     r14, [rbp+57h+arg_8]
0x18000dd07  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000dd0b  call    cs:__imp_VariantClear
0x18000dd11  test    rdi, rdi
0x18000dd14  jz      short loc_18000DD36
0x18000dd16  or      eax, 0FFFFFFFFh
0x18000dd19  lock xadd [rdi+0Ch], eax
0x18000dd1e  cmp     eax, 1
0x18000dd21  jnz     short loc_18000DD36
0x18000dd23  mov     rax, [rdi]
0x18000dd26  mov     edx, 1
0x18000dd2b  mov     rcx, rdi
0x18000dd2e  mov     rax, [rax]
0x18000dd31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd36  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000dd3a  test    rcx, rcx
0x18000dd3d  jz      short loc_18000DD49
0x18000dd3f  call    cs:__imp_SysFreeString
0x18000dd45  mov     [rbp+57h+bstrString], r15
0x18000dd49  mov     rcx, [rbp+57h+var_C0]; bstrString
0x18000dd4d  test    rcx, rcx
0x18000dd50  jz      short loc_18000DD5C
0x18000dd52  call    cs:__imp_SysFreeString
0x18000dd58  mov     [rbp+57h+var_C0], r15
0x18000dd5c  test    rsi, rsi
0x18000dd5f  jz      short loc_18000DD82
0x18000dd61  or      eax, 0FFFFFFFFh
0x18000dd64  lock xadd [rsi], eax
0x18000dd68  cmp     eax, 1
0x18000dd6b  jnz     short loc_18000DD82
0x18000dd6d  test    rsi, rsi
0x18000dd70  jz      short loc_18000DD82
0x18000dd72  mov     rcx, rsi; this
0x18000dd75  call    ??1ATTRIBUTE_SAFEARRAY@@AEAA@XZ; ATTRIBUTE_SAFEARRAY::~ATTRIBUTE_SAFEARRAY(void)
  ... truncated ...
```
