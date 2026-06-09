# APPLICATION_DATA_OBJECT_TABLE_CS::ReadFromSiteElement(INativeConfigurationElement *,ulong,SITE_DATA_OBJECT_CS *)

- ea: `0x180050030`
- end: `0x1800503ef`
- name: `?ReadFromSiteElement@APPLICATION_DATA_OBJECT_TABLE_CS@@QEAAJPEAVINativeConfigurationElement@@KPEAVSITE_DATA_OBJECT_CS@@@Z`
- size: `959`
- prototype: `int(APPLICATION_DATA_OBJECT_TABLE_CS *__hidden this, struct INativeConfigurationElement *, unsigned int, struct SITE_DATA_OBJECT_CS *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004c3e0`

## callees

- `0x180001234`
- `0x180039938`
- `0x18003a8d8`
- `0x18003ac14`
- `0x18003ac88`
- `0x180050030`
- `0x1800503f8`
- `0x1800504cc`
- `0x18006101a`
- `0x180062010`

## import_xrefs

- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18005029f`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18005029f`
- `iisutil!PuDbgPrint` at `0x1800501c9`
- `iisutil!PuDbgPrint` at `0x1800501c9`
- `iisutil!PuDbgPrintError` at `0x18005013e`
- `iisutil!PuDbgPrintError` at `0x180050339`
- `iisutil!PuDbgPrintError` at `0x18005039c`
- `iisutil!PuDbgPrintError` at `0x18005013e`
- `iisutil!PuDbgPrintError` at `0x180050339`
- `iisutil!PuDbgPrintError` at `0x18005039c`

## string_xrefs

- `0x180050133`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\applicationstore_cs.cxx`
- `0x1800501a6`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\applicationstore_cs.cxx`
- `0x180050332`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\applicationstore_cs.cxx`
- `0x180050391`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\applicationstore_cs.cxx`
- `0x180050125`: `APPLICATION_DATA_OBJECT_TABLE_CS::ReadFromSiteElement`
- `0x180050199`: `APPLICATION_DATA_OBJECT_TABLE_CS::ReadFromSiteElement`
- `0x180050321`: `APPLICATION_DATA_OBJECT_TABLE_CS::ReadFromSiteElement`
- `0x180050385`: `APPLICATION_DATA_OBJECT_TABLE_CS::ReadFromSiteElement`
- `0x180050371`: ` Failed to get the path of the app \n`
- `0x1800501b1`: ` App Path '%S' \n `
- `0x180050315`: ` Failed to setup enabled protocols for application \n`

## pseudocode

```c
__int64 __fastcall APPLICATION_DATA_OBJECT_TABLE_CS::ReadFromSiteElement(
        APPLICATION_DATA_OBJECT_TABLE_CS *this,
        struct INativeConfigurationElement *a2,
        unsigned int a3,
        struct SITE_DATA_OBJECT_CS *a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *v6)(struct INativeConfigurationElement *, __int64 *); // rax
  int FakeAppRoot; // edi
  unsigned int v10; // esi
  int v11; // eax
  unsigned __int16 *v12; // rcx
  char *v13; // rax
  char *v14; // rbx
  int inserted; // eax
  struct INativeConfigurationElement *v17; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v18; // [rsp+38h] [rbp-18h] BYREF
  __int64 v19; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v20; // [rsp+88h] [rbp+38h] BYREF

  v4 = *(_QWORD *)a2;
  v20 = 0;
  v19 = 0;
  v17 = 0;
  v6 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(v4 + 40);
  v18 = 0;
  FakeAppRoot = v6(a2, &v19);
  if ( FakeAppRoot >= 0 )
  {
    FakeAppRoot = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 24LL))(v19, &v20);
    if ( FakeAppRoot >= 0 )
    {
      v10 = 0;
      if ( v20 )
      {
        while ( 1 )
        {
          v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v19 + 32LL))(
                  v19,
                  v10,
                  &v17);
          if ( v11 < 0 && (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\applicationstore_cs.cxx",
              270,
              "APPLICATION_DATA_OBJECT_TABLE_CS::ReadFromSiteElement",
              v11,
              " Failed to get an app element \n");
          FakeAppRoot = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
                          v17,
                          L"path",
                          &v18,
                          0,
                          0);
          if ( FakeAppRoot < 0 )
            break;
          if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
          {
            v12 = L"NULL";
            if ( v18 )
              v12 = v18;
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\applicationstore_cs.cxx",
              291,
              "APPLICATION_DATA_OBJECT_TABLE_CS::ReadFromSiteElement",
              " App Path '%S' \n ",
              v12);
          }
          v13 = (char *)operator new(0x168u);
          v14 = v13;
          if ( !v13 )
          {
            FakeAppRoot = -2147024888;
            goto LABEL_37;
          }
          memset_0(v13, 0, 0x168u);
          APPLICATION_DATA_OBJECT::APPLICATION_DATA_OBJECT((APPLICATION_DATA_OBJECT *)v14);
          *(_QWORD *)v14 = &APPLICATION_DATA_OBJECT_CS::`vftable';
          FakeAppRoot = APPLICATION_DATA_OBJECT::Create((APPLICATION_DATA_OBJECT *)v14, v18, a3);
          if ( FakeAppRoot < 0 )
            goto LABEL_32;
          FakeAppRoot = CreateFakeAppRoot(
                          *((_DWORD *)v14 + 26),
                          *((const unsigned __int16 **)v14 + 10),
                          (struct STRU *)(v14 + 176));
          if ( FakeAppRoot < 0 )
            goto LABEL_32;
          *((_QWORD *)v14 + 37) = 0;
          v18 = 0;
          FakeAppRoot = APPLICATION_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData(
                          (APPLICATION_DATA_OBJECT_CS *)v14,
                          v17);
          if ( FakeAppRoot < 0 )
            goto LABEL_32;
          FakeAppRoot = APPLICATION_DATA_OBJECT_CS::SetEnabledProtocols((APPLICATION_DATA_OBJECT_CS *)v14, v17);
          if ( FakeAppRoot < 0 )
          {
            if ( (g_dwDebugFlags & 0xF) != 0 )
              PuDbgPrintError(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\applicationstore_cs.cxx",
                333,
                "APPLICATION_DATA_OBJECT_TABLE_CS::ReadFromSiteElement",
                FakeAppRoot,
                " Failed to setup enabled protocols for application \n");
            goto LABEL_32;
          }
          FakeAppRoot = SITE_DATA_OBJECT::AddAppPoolName(a4, *((const unsigned __int16 **)v14 + 19));
          if ( FakeAppRoot < 0 )
            goto LABEL_32;
          inserted = CLKRHashTable::InsertRecord((char *)this + 8, v14, 0);
          if ( (unsigned int)inserted > 1 )
          {
            if ( inserted > 0 )
              FakeAppRoot = (unsigned __int16)inserted | 0x80070000;
            else
              FakeAppRoot = inserted;
LABEL_32:
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 + 3, 0xFFFFFFFF) == 1 )
              (**(void (__fastcall ***)(void *, __int64))v14)(v14, 1);
            goto LABEL_37;
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 + 3, 0xFFFFFFFF) == 1 )
            (**(void (__fastcall ***)(void *, __int64))v14)(v14, 1);
          (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v17 + 16LL))(v17);
          ++v10;
          v17 = 0;
          if ( v10 >= v20 )
            goto LABEL_39;
        }
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\applicationstore_cs.cxx",
            282,
            "APPLICATION_DATA_OBJECT_TABLE_CS::ReadFromSiteElement",
            FakeAppRoot,
            " Failed to get the path of the app \n");
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\applicationstore_cs.cxx",
        250,
        "APPLICATION_DATA_OBJECT_TABLE_CS::ReadFromSiteElement",
        FakeAppRoot,
        " Failed to get count of applications in the collection \n");
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\applicationstore_cs.cxx",
      238,
      "APPLICATION_DATA_OBJECT_TABLE_CS::ReadFromSiteElement",
      FakeAppRoot,
      " Failed to get apps collection \n");
  }
LABEL_37:
  if ( v17 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
LABEL_39:
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return (unsigned int)FakeAppRoot;
}

```

## disassembly

```asm
0x180050030  mov     [rsp-28h+arg_0], rbx
0x180050035  mov     [rsp-28h+arg_10], rsi
0x18005003a  push    rbp
0x18005003b  push    rdi
0x18005003c  push    r12
0x18005003e  push    r14
0x180050040  push    r15
0x180050042  mov     rbp, rsp
0x180050045  sub     rsp, 50h
0x180050049  mov     rax, [rdx]
0x18005004c  mov     r10, rdx
0x18005004f  mov     r15, rcx
0x180050052  mov     [rbp+arg_8], 0
0x180050059  lea     rdx, [rbp+var_10]
0x18005005d  mov     [rbp+var_10], 0
0x180050065  mov     rcx, r10
0x180050068  mov     [rbp+var_20], 0
0x180050070  mov     rax, [rax+28h]
0x180050074  mov     r14, r9
0x180050077  mov     r12d, r8d
0x18005007a  mov     [rbp+var_18], 0
0x180050082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050087  mov     edi, eax
0x180050089  test    eax, eax
0x18005008b  jns     short loc_1800500AC
0x18005008d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180050094  jz      loc_1800503A2
0x18005009a  lea     rax, aFailedToGetApp_2; " Failed to get apps collection \n"
0x1800500a1  mov     r8d, 0EEh
0x1800500a7  jmp     loc_18005037E
0x1800500ac  mov     rcx, [rbp+var_10]
0x1800500b0  lea     rdx, [rbp+arg_8]
0x1800500b4  mov     rax, [rcx]
0x1800500b7  mov     rax, [rax+18h]
0x1800500bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500c0  mov     edi, eax
0x1800500c2  test    eax, eax
0x1800500c4  jns     short loc_1800500E5
0x1800500c6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800500cd  jz      loc_1800503A2
0x1800500d3  lea     rax, aFailedToGetCou; " Failed to get count of applications in"...
0x1800500da  mov     r8d, 0FAh
0x1800500e0  jmp     loc_18005037E
0x1800500e5  xor     esi, esi
0x1800500e7  cmp     [rbp+arg_8], esi
0x1800500ea  jbe     loc_1800503A2
0x1800500f0  mov     rcx, [rbp+var_10]
0x1800500f4  lea     r8, [rbp+var_20]
0x1800500f8  mov     edx, esi
0x1800500fa  mov     rax, [rcx]
0x1800500fd  mov     rax, [rax+20h]
0x180050101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050106  test    eax, eax
0x180050108  jns     short loc_180050144
0x18005010a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180050111  jz      short loc_180050144
0x180050113  lea     rcx, aFailedToGetAnA; " Failed to get an app element \n"
0x18005011a  mov     r8d, 10Eh
0x180050120  mov     [rsp+50h+var_28], rcx
0x180050125  lea     r9, aApplicationDat_6; "APPLICATION_DATA_OBJECT_TABLE_CS::ReadF"...
0x18005012c  mov     rcx, cs:g_pDebug
0x180050133  lea     rdx, aServercommonIn_12; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18005013a  mov     dword ptr [rsp+50h+var_30], eax
0x18005013e  call    cs:__imp_PuDbgPrintError
0x180050144  mov     rcx, [rbp+var_20]
0x180050148  lea     r8, [rbp+var_18]
0x18005014c  xor     r9d, r9d
0x18005014f  mov     [rsp+50h+var_30], 0
0x180050158  lea     rdx, aPath; "path"
0x18005015f  mov     rax, [rcx]
0x180050162  mov     rax, [rax+40h]
0x180050166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005016b  mov     edi, eax
0x18005016d  test    eax, eax
0x18005016f  js      loc_180050368
0x180050175  mov     eax, cs:g_dwDebugFlags
0x18005017b  test    al, 3
0x18005017d  setnz   cl
0x180050180  bt      eax, 1Eh
0x180050184  setb    al
0x180050187  test    al, cl
0x180050189  jz      short loc_1800501CF
0x18005018b  mov     rax, [rbp+var_18]
0x18005018f  lea     rcx, aNull_0; "NULL"
0x180050196  test    rax, rax
0x180050199  lea     r9, aApplicationDat_6; "APPLICATION_DATA_OBJECT_TABLE_CS::ReadF"...
0x1800501a0  mov     r8d, 123h
0x1800501a6  lea     rdx, aServercommonIn_12; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800501ad  cmovnz  rcx, rax
0x1800501b1  lea     rax, aAppPathS; " App Path '%S' \n "
0x1800501b8  mov     [rsp+50h+var_28], rcx
0x1800501bd  mov     rcx, cs:g_pDebug
0x1800501c4  mov     [rsp+50h+var_30], rax
0x1800501c9  call    cs:__imp_PuDbgPrint
0x1800501cf  mov     ecx, 168h; Size
0x1800501d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800501d9  mov     rbx, rax
0x1800501dc  test    rax, rax
0x1800501df  jz      loc_180050361
0x1800501e5  xor     edx, edx; Val
0x1800501e7  mov     r8d, 168h; Size
0x1800501ed  mov     rcx, rax; void *
0x1800501f0  call    memset_0
0x1800501f5  mov     rcx, rbx; this
0x1800501f8  call    ??0APPLICATION_DATA_OBJECT@@QEAA@XZ; APPLICATION_DATA_OBJECT::APPLICATION_DATA_OBJECT(void)
0x1800501fd  lea     rax, ??_7APPLICATION_DATA_OBJECT_CS@@6B@; const APPLICATION_DATA_OBJECT_CS::`vftable'
0x180050204  mov     r8d, r12d; unsigned int
0x180050207  mov     [rbx], rax
0x18005020a  mov     rcx, rbx; this
0x18005020d  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x180050211  call    ?Create@APPLICATION_DATA_OBJECT@@QEAAJPEBGK@Z; APPLICATION_DATA_OBJECT::Create(ushort const *,ulong)
0x180050216  mov     edi, eax
0x180050218  test    eax, eax
0x18005021a  js      loc_18005033F
0x180050220  mov     rdx, [rbx+50h]; unsigned __int16 *
0x180050224  lea     r8, [rbx+0B0h]; struct STRU *
0x18005022b  mov     ecx, [rbx+68h]; Value
0x18005022e  call    ?CreateFakeAppRoot@@YAJKPEBGPEAVSTRU@@@Z; CreateFakeAppRoot(ulong,ushort const *,STRU *)
0x180050233  mov     edi, eax
0x180050235  test    eax, eax
0x180050237  js      loc_18005033F
0x18005023d  mov     qword ptr [rbx+128h], 0
0x180050248  mov     rcx, rbx; this
0x18005024b  mov     rdx, [rbp+var_20]; struct INativeConfigurationElement *
0x18005024f  mov     [rbp+var_18], 0
0x180050257  call    ?SetGenericSettingsFromConfigStoreData@APPLICATION_DATA_OBJECT_CS@@QEAAJPEAVINativeConfigurationElement@@@Z; APPLICATION_DATA_OBJECT_CS::SetGenericSettingsFromConfigStoreData(INativeConfigurationElement *)
0x18005025c  mov     edi, eax
0x18005025e  test    eax, eax
0x180050260  js      loc_18005033F
0x180050266  mov     rdx, [rbp+var_20]; struct INativeConfigurationElement *
0x18005026a  mov     rcx, rbx; this
0x18005026d  call    ?SetEnabledProtocols@APPLICATION_DATA_OBJECT_CS@@QEAAJPEAVINativeConfigurationElement@@@Z; APPLICATION_DATA_OBJECT_CS::SetEnabledProtocols(INativeConfigurationElement *)
0x180050272  mov     edi, eax
0x180050274  test    eax, eax
0x180050276  js      loc_180050305
0x18005027c  mov     rdx, [rbx+98h]; unsigned __int16 *
0x180050283  mov     rcx, r14; this
0x180050286  call    ?AddAppPoolName@SITE_DATA_OBJECT@@QEAAJPEBG@Z; SITE_DATA_OBJECT::AddAppPoolName(ushort const *)
0x18005028b  mov     edi, eax
0x18005028d  test    eax, eax
0x18005028f  js      loc_18005033F
0x180050295  lea     rcx, [r15+8]
0x180050299  xor     r8d, r8d
0x18005029c  mov     rdx, rbx
0x18005029f  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x1800502a5  cmp     eax, 1
0x1800502a8  ja      short loc_1800502F2
0x1800502aa  or      eax, 0FFFFFFFFh
0x1800502ad  lock xadd [rbx+0Ch], eax
0x1800502b2  cmp     eax, 1
0x1800502b5  jnz     short loc_1800502CA
0x1800502b7  mov     rax, [rbx]
0x1800502ba  mov     edx, 1
0x1800502bf  mov     rcx, rbx
0x1800502c2  mov     rax, [rax]
0x1800502c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502ca  mov     rcx, [rbp+var_20]
0x1800502ce  mov     rax, [rcx]
0x1800502d1  mov     rax, [rax+10h]
0x1800502d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502da  inc     esi
0x1800502dc  mov     [rbp+var_20], 0
0x1800502e4  cmp     esi, [rbp+arg_8]
0x1800502e7  jb      loc_1800500F0
0x1800502ed  jmp     loc_1800503BF
0x1800502f2  test    eax, eax
0x1800502f4  jg      short loc_1800502FA
0x1800502f6  mov     edi, eax
0x1800502f8  jmp     short loc_18005033F
0x1800502fa  movzx   edi, ax
0x1800502fd  or      edi, 80070000h
0x180050303  jmp     short loc_18005033F
0x180050305  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005030c  jz      short loc_18005033F
0x18005030e  mov     rcx, cs:g_pDebug
0x180050315  lea     rax, aFailedToSetupE; " Failed to setup enabled protocols for "...
0x18005031c  mov     [rsp+50h+var_28], rax
0x180050321  lea     r9, aApplicationDat_6; "APPLICATION_DATA_OBJECT_TABLE_CS::ReadF"...
0x180050328  mov     r8d, 14Dh
0x18005032e  mov     dword ptr [rsp+50h+var_30], edi
0x180050332  lea     rdx, aServercommonIn_12; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180050339  call    cs:__imp_PuDbgPrintError
0x18005033f  or      eax, 0FFFFFFFFh
0x180050342  lock xadd [rbx+0Ch], eax
0x180050347  cmp     eax, 1
0x18005034a  jnz     short loc_1800503A2
0x18005034c  mov     rax, [rbx]
0x18005034f  mov     edx, 1
0x180050354  mov     rcx, rbx
0x180050357  mov     rax, [rax]
0x18005035a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005035f  jmp     short loc_1800503A2
0x180050361  mov     edi, 80070008h
0x180050366  jmp     short loc_1800503A2
0x180050368  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005036f  jz      short loc_1800503A2
0x180050371  lea     rax, aFailedToGetThe_2; " Failed to get the path of the app \n"
0x180050378  mov     r8d, 11Ah
0x18005037e  mov     rcx, cs:g_pDebug
0x180050385  lea     r9, aApplicationDat_6; "APPLICATION_DATA_OBJECT_TABLE_CS::ReadF"...
0x18005038c  mov     [rsp+50h+var_28], rax
0x180050391  lea     rdx, aServercommonIn_12; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180050398  mov     dword ptr [rsp+50h+var_30], edi
0x18005039c  call    cs:__imp_PuDbgPrintError
0x1800503a2  mov     rcx, [rbp+var_20]
0x1800503a6  test    rcx, rcx
0x1800503a9  jz      short loc_1800503BF
0x1800503ab  mov     rax, [rcx]
0x1800503ae  mov     rax, [rax+10h]
0x1800503b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503b7  mov     [rbp+var_20], 0
0x1800503bf  mov     rcx, [rbp+var_10]
0x1800503c3  test    rcx, rcx
0x1800503c6  jz      short loc_1800503D4
0x1800503c8  mov     rax, [rcx]
0x1800503cb  mov     rax, [rax+10h]
0x1800503cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503d4  lea     r11, [rsp+50h+var_s0]
0x1800503d9  mov     eax, edi
0x1800503db  mov     rbx, [r11+30h]
0x1800503df  mov     rsi, [r11+40h]
0x1800503e3  mov     rsp, r11
0x1800503e6  pop     r15
0x1800503e8  pop     r14
0x1800503ea  pop     r12
0x1800503ec  pop     rdi
0x1800503ed  pop     rbp
0x1800503ee  retn
```
