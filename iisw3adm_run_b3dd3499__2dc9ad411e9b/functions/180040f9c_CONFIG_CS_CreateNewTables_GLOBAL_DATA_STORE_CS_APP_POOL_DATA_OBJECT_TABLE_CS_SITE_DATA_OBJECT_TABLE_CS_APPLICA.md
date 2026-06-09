# CONFIG_CS::CreateNewTables(GLOBAL_DATA_STORE_CS * *,APP_POOL_DATA_OBJECT_TABLE_CS * *,SITE_DATA_OBJECT_TABLE_CS * *,APPLICATION_DATA_OBJECT_TABLE_CS * *,PROTOCOL_DATA_OBJECT_TABLE_CS * *)

- ea: `0x180040f9c`
- end: `0x1800412aa`
- name: `?CreateNewTables@CONFIG_CS@@AEAAJPEAPEAVGLOBAL_DATA_STORE_CS@@PEAPEAVAPP_POOL_DATA_OBJECT_TABLE_CS@@PEAPEAVSITE_DATA_OBJECT_TABLE_CS@@PEAPEAVAPPLICATION_DATA_OBJECT_TABLE_CS@@PEAPEAVPROTOCOL_DATA_OBJECT_TABLE_CS@@@Z`
- size: `782`
- prototype: `__int64 __fastcall(CONFIG_CS *__hidden this, struct GLOBAL_DATA_STORE_CS **, struct APP_POOL_DATA_OBJECT_TABLE_CS **, struct SITE_DATA_OBJECT_TABLE_CS **, struct APPLICATION_DATA_OBJECT_TABLE_CS **, struct PROTOCOL_DATA_OBJECT_TABLE_CS **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800418c0`

## callees

- `0x180001234`
- `0x18003cb7c`
- `0x180040f9c`
- `0x18006101a`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x180041124`
- `iisutil!PuDbgPrintError` at `0x180041171`
- `iisutil!PuDbgPrintError` at `0x1800411ba`
- `iisutil!PuDbgPrintError` at `0x18004123c`
- `iisutil!PuDbgPrintError` at `0x180041291`
- `iisutil!PuDbgPrintError` at `0x180041124`
- `iisutil!PuDbgPrintError` at `0x180041171`
- `iisutil!PuDbgPrintError` at `0x1800411ba`
- `iisutil!PuDbgPrintError` at `0x18004123c`
- `iisutil!PuDbgPrintError` at `0x180041291`

## string_xrefs

- `0x18004111d`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_cs.cxx`
- `0x18004116a`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_cs.cxx`
- `0x1800411b3`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_cs.cxx`
- `0x180041235`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_cs.cxx`
- `0x18004128a`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_cs.cxx`
- `0x180041269`: `Failed to create a global store\n`
- `0x180041108`: `CONFIG_CS::CreateNewTables`
- `0x180041155`: `CONFIG_CS::CreateNewTables`
- `0x18004119e`: `CONFIG_CS::CreateNewTables`
- `0x180041220`: `CONFIG_CS::CreateNewTables`
- `0x180041275`: `CONFIG_CS::CreateNewTables`
- `0x180041214`: `Failed to create a app pool table\n`
- `0x180041192`: `Failed to create a site table\n`
- `0x180041149`: `Failed to create a application table\n`
- `0x1800410fc`: `Failed to create a protocol table\n`

## pseudocode

```c
__int64 __fastcall CONFIG_CS::CreateNewTables(
        CONFIG_CS *this,
        struct GLOBAL_DATA_STORE_CS **a2,
        struct APP_POOL_DATA_OBJECT_TABLE_CS **a3,
        struct SITE_DATA_OBJECT_TABLE_CS **a4,
        struct APPLICATION_DATA_OBJECT_TABLE_CS **a5,
        struct PROTOCOL_DATA_OBJECT_TABLE_CS **a6)
{
  struct GLOBAL_DATA_STORE_CS *v8; // rax
  struct GLOBAL_DATA_STORE_CS *v9; // rdi
  DATA_OBJECT_TABLE *v10; // rax
  DATA_OBJECT_TABLE *v11; // r14
  DATA_OBJECT_TABLE *v12; // rax
  DATA_OBJECT_TABLE *v13; // r15
  DATA_OBJECT_TABLE *v14; // rax
  DATA_OBJECT_TABLE *v15; // rsi
  DATA_OBJECT_TABLE *v16; // rax
  DATA_OBJECT_TABLE *v17; // rbp
  unsigned int v18; // ebx

  v8 = (struct GLOBAL_DATA_STORE_CS *)operator new(0x10u);
  v9 = v8;
  if ( v8 )
  {
    *((_QWORD *)v8 + 1) = 0;
    *(_QWORD *)v8 = &GLOBAL_DATA_STORE_CS::`vftable';
    v10 = (DATA_OBJECT_TABLE *)operator new(0x58u);
    v11 = v10;
    if ( v10 )
    {
      memset_0(v10, 0, 0x58u);
      DATA_OBJECT_TABLE::DATA_OBJECT_TABLE(v11);
      *(_QWORD *)v11 = &DATA_OBJECT_TABLE::`vftable';
      v12 = (DATA_OBJECT_TABLE *)operator new(0x60u);
      v13 = v12;
      if ( v12 )
      {
        memset_0(v12, 0, 0x60u);
        DATA_OBJECT_TABLE::DATA_OBJECT_TABLE(v13);
        *((_QWORD *)v13 + 11) = 0;
        *(_QWORD *)v13 = &DATA_OBJECT_TABLE::`vftable';
        v14 = (DATA_OBJECT_TABLE *)operator new(0x58u);
        v15 = v14;
        if ( v14 )
        {
          memset_0(v14, 0, 0x58u);
          DATA_OBJECT_TABLE::DATA_OBJECT_TABLE(v15);
          *(_QWORD *)v15 = &DATA_OBJECT_TABLE::`vftable';
          v16 = (DATA_OBJECT_TABLE *)operator new(0x58u);
          v17 = v16;
          if ( v16 )
          {
            memset_0(v16, 0, 0x58u);
            DATA_OBJECT_TABLE::DATA_OBJECT_TABLE(v17);
            *a3 = v11;
            *(_QWORD *)v17 = &DATA_OBJECT_TABLE::`vftable';
            v18 = 0;
            *a4 = v13;
            *a5 = v15;
            *a2 = v9;
            *a6 = v17;
            return v18;
          }
          v18 = -2147024882;
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_cs.cxx",
              538,
              "CONFIG_CS::CreateNewTables",
              -2147024882,
              "Failed to create a protocol table\n");
        }
        else
        {
          v18 = -2147024882;
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_cs.cxx",
              524,
              "CONFIG_CS::CreateNewTables",
              -2147024882,
              "Failed to create a application table\n");
          v15 = 0;
        }
      }
      else
      {
        v15 = 0;
        v18 = -2147024882;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_cs.cxx",
            510,
            "CONFIG_CS::CreateNewTables",
            -2147024882,
            "Failed to create a site table\n");
        v13 = 0;
      }
      (**(void (__fastcall ***)(DATA_OBJECT_TABLE *, __int64))v11)(v11, 1);
      if ( v13 )
        (**(void (__fastcall ***)(DATA_OBJECT_TABLE *, __int64))v13)(v13, 1);
      if ( v15 )
        (**(void (__fastcall ***)(DATA_OBJECT_TABLE *, __int64))v15)(v15, 1);
    }
    else
    {
      v18 = -2147024882;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_cs.cxx",
          496,
          "CONFIG_CS::CreateNewTables",
          -2147024882,
          "Failed to create a app pool table\n");
    }
    (**(void (__fastcall ***)(struct GLOBAL_DATA_STORE_CS *, __int64))v9)(v9, 1);
    return v18;
  }
  v18 = -2147024882;
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_cs.cxx",
      482,
      "CONFIG_CS::CreateNewTables",
      -2147024882,
      "Failed to create a global store\n");
  return v18;
}

```

## disassembly

```asm
0x180040f9c  mov     [rsp+arg_8], rdx
0x180040fa1  push    rbx
0x180040fa2  push    rbp
0x180040fa3  push    rsi
0x180040fa4  push    rdi
0x180040fa5  push    r12
0x180040fa7  push    r13
0x180040fa9  push    r14
0x180040fab  push    r15
0x180040fad  sub     rsp, 38h
0x180040fb1  mov     ecx, 10h; Size
0x180040fb6  mov     r12, r9
0x180040fb9  mov     r13, r8
0x180040fbc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040fc1  mov     rdi, rax
0x180040fc4  test    rax, rax
0x180040fc7  jz      loc_180041254
0x180040fcd  mov     qword ptr [rax+8], 0
0x180040fd5  mov     ebx, 58h ; 'X'
0x180040fda  lea     rax, ??_7GLOBAL_DATA_STORE_CS@@6B@; const GLOBAL_DATA_STORE_CS::`vftable'
0x180040fe1  mov     ecx, ebx; Size
0x180040fe3  mov     [rdi], rax
0x180040fe6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040feb  lea     ebp, [rbx-57h]
0x180040fee  mov     r14, rax
0x180040ff1  test    rax, rax
0x180040ff4  jz      loc_1800411FF
0x180040ffa  mov     r8d, ebx; Size
0x180040ffd  xor     edx, edx; Val
0x180040fff  mov     rcx, rax; void *
0x180041002  call    memset_0
0x180041007  mov     rcx, r14; this
0x18004100a  call    ??0DATA_OBJECT_TABLE@@QEAA@XZ; DATA_OBJECT_TABLE::DATA_OBJECT_TABLE(void)
0x18004100f  lea     rax, ??_7DATA_OBJECT_TABLE@@6B@; const DATA_OBJECT_TABLE::`vftable'
0x180041016  lea     esi, [rbx+8]
0x180041019  mov     [r14], rax
0x18004101c  mov     ecx, esi; Size
0x18004101e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180041023  mov     r15, rax
0x180041026  test    rax, rax
0x180041029  jz      loc_18004117B
0x18004102f  mov     r8d, esi; Size
0x180041032  xor     edx, edx; Val
0x180041034  mov     rcx, rax; void *
0x180041037  call    memset_0
0x18004103c  mov     rcx, r15; this
0x18004103f  call    ??0DATA_OBJECT_TABLE@@QEAA@XZ; DATA_OBJECT_TABLE::DATA_OBJECT_TABLE(void)
0x180041044  lea     rax, ??_7DATA_OBJECT_TABLE@@6B@; const DATA_OBJECT_TABLE::`vftable'
0x18004104b  mov     qword ptr [r15+58h], 0
0x180041053  mov     ecx, ebx; Size
0x180041055  mov     [r15], rax
0x180041058  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004105d  mov     rsi, rax
0x180041060  test    rax, rax
0x180041063  jz      loc_180041134
0x180041069  mov     r8d, ebx; Size
0x18004106c  xor     edx, edx; Val
0x18004106e  mov     rcx, rax; void *
0x180041071  call    memset_0
0x180041076  mov     rcx, rsi; this
0x180041079  call    ??0DATA_OBJECT_TABLE@@QEAA@XZ; DATA_OBJECT_TABLE::DATA_OBJECT_TABLE(void)
0x18004107e  lea     rax, ??_7DATA_OBJECT_TABLE@@6B@; const DATA_OBJECT_TABLE::`vftable'
0x180041085  mov     ecx, ebx; Size
0x180041087  mov     [rsi], rax
0x18004108a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004108f  mov     rbp, rax
0x180041092  test    rax, rax
0x180041095  jz      short loc_1800410E7
0x180041097  mov     r8d, ebx; Size
0x18004109a  xor     edx, edx; Val
0x18004109c  mov     rcx, rax; void *
0x18004109f  call    memset_0
0x1800410a4  mov     rcx, rbp; this
0x1800410a7  call    ??0DATA_OBJECT_TABLE@@QEAA@XZ; DATA_OBJECT_TABLE::DATA_OBJECT_TABLE(void)
0x1800410ac  lea     rax, ??_7DATA_OBJECT_TABLE@@6B@; const DATA_OBJECT_TABLE::`vftable'
0x1800410b3  mov     [r13+0], r14
0x1800410b7  mov     [rbp+0], rax
0x1800410bb  xor     ebx, ebx
0x1800410bd  mov     rax, [rsp+78h+arg_20]
0x1800410c5  mov     [r12], r15
0x1800410c9  mov     [rax], rsi
0x1800410cc  mov     rax, [rsp+78h+arg_8]
0x1800410d4  mov     [rax], rdi
0x1800410d7  mov     rax, [rsp+78h+arg_28]
0x1800410df  mov     [rax], rbp
0x1800410e2  jmp     loc_180041297
0x1800410e7  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800410ee  mov     ebx, 8007000Eh
0x1800410f3  jz      short loc_18004112A
0x1800410f5  mov     rcx, cs:g_pDebug
0x1800410fc  lea     rax, aFailedToCreate_10; "Failed to create a protocol table\n"
0x180041103  mov     [rsp+78h+var_50], rax
0x180041108  lea     r9, aConfigCsCreate; "CONFIG_CS::CreateNewTables"
0x18004110f  mov     r8d, 21Ah
0x180041115  mov     [rsp+78h+var_58], 8007000Eh
0x18004111d  lea     rdx, aServercommonIn_30; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180041124  call    cs:__imp_PuDbgPrintError
0x18004112a  mov     ebp, 1
0x18004112f  jmp     loc_1800411C3
0x180041134  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004113b  mov     ebx, 8007000Eh
0x180041140  jz      short loc_180041177
0x180041142  mov     rcx, cs:g_pDebug
0x180041149  lea     rax, aFailedToCreate_3; "Failed to create a application table\n"
0x180041150  mov     [rsp+78h+var_50], rax
0x180041155  lea     r9, aConfigCsCreate; "CONFIG_CS::CreateNewTables"
0x18004115c  mov     r8d, 20Ch
0x180041162  mov     [rsp+78h+var_58], 8007000Eh
0x18004116a  lea     rdx, aServercommonIn_30; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180041171  call    cs:__imp_PuDbgPrintError
0x180041177  xor     esi, esi
0x180041179  jmp     short loc_1800411C3
0x18004117b  xor     esi, esi
0x18004117d  mov     ebx, 8007000Eh
0x180041182  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180041189  jz      short loc_1800411C0
0x18004118b  mov     rcx, cs:g_pDebug
0x180041192  lea     rax, aFailedToCreate_6; "Failed to create a site table\n"
0x180041199  mov     [rsp+78h+var_50], rax
0x18004119e  lea     r9, aConfigCsCreate; "CONFIG_CS::CreateNewTables"
0x1800411a5  mov     r8d, 1FEh
0x1800411ab  mov     [rsp+78h+var_58], 8007000Eh
0x1800411b3  lea     rdx, aServercommonIn_30; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800411ba  call    cs:__imp_PuDbgPrintError
0x1800411c0  xor     r15d, r15d
0x1800411c3  mov     rax, [r14]
0x1800411c6  mov     edx, ebp
0x1800411c8  mov     rcx, r14
0x1800411cb  mov     rax, [rax]
0x1800411ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411d3  test    r15, r15
0x1800411d6  jz      short loc_1800411E8
0x1800411d8  mov     rax, [r15]
0x1800411db  mov     edx, ebp
0x1800411dd  mov     rcx, r15
0x1800411e0  mov     rax, [rax]
0x1800411e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411e8  test    rsi, rsi
0x1800411eb  jz      short loc_180041242
0x1800411ed  mov     rax, [rsi]
0x1800411f0  mov     edx, ebp
0x1800411f2  mov     rcx, rsi
0x1800411f5  mov     rax, [rax]
0x1800411f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411fd  jmp     short loc_180041242
0x1800411ff  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180041206  mov     ebx, 8007000Eh
0x18004120b  jz      short loc_180041242
0x18004120d  mov     rcx, cs:g_pDebug
0x180041214  lea     rax, aFailedToCreate_1; "Failed to create a app pool table\n"
0x18004121b  mov     [rsp+78h+var_50], rax
0x180041220  lea     r9, aConfigCsCreate; "CONFIG_CS::CreateNewTables"
0x180041227  mov     r8d, 1F0h
0x18004122d  mov     [rsp+78h+var_58], 8007000Eh
0x180041235  lea     rdx, aServercommonIn_30; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004123c  call    cs:__imp_PuDbgPrintError
0x180041242  mov     rax, [rdi]
0x180041245  mov     edx, ebp
0x180041247  mov     rcx, rdi
0x18004124a  mov     rax, [rax]
0x18004124d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041252  jmp     short loc_180041297
0x180041254  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004125b  mov     ebx, 8007000Eh
0x180041260  jz      short loc_180041297
0x180041262  mov     rcx, cs:g_pDebug
0x180041269  lea     rax, aFailedToCreate_5; "Failed to create a global store\n"
0x180041270  mov     [rsp+78h+var_50], rax
0x180041275  lea     r9, aConfigCsCreate; "CONFIG_CS::CreateNewTables"
0x18004127c  mov     r8d, 1E2h
0x180041282  mov     [rsp+78h+var_58], 8007000Eh
0x18004128a  lea     rdx, aServercommonIn_30; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180041291  call    cs:__imp_PuDbgPrintError
0x180041297  mov     eax, ebx
0x180041299  add     rsp, 38h
0x18004129d  pop     r15
0x18004129f  pop     r14
0x1800412a1  pop     r13
0x1800412a3  pop     r12
0x1800412a5  pop     rdi
0x1800412a6  pop     rsi
0x1800412a7  pop     rbp
0x1800412a8  pop     rbx
0x1800412a9  retn
```
