# PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem(INativeConfigurationElement *)

- ea: `0x180051f08`
- end: `0x180052293`
- name: `?ReadFromConfigSystem@PROTOCOL_DATA_OBJECT_TABLE_CS@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `907`
- prototype: `__int64 __fastcall(PROTOCOL_DATA_OBJECT_TABLE_CS *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800418c0`

## callees

- `0x180001234`
- `0x1800517d0`
- `0x180051af4`
- `0x180051f08`
- `0x18005229c`
- `0x180062010`

## import_xrefs

- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180052132`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180052132`
- `iisutil!PuDbgPrint` at `0x18005200c`
- `iisutil!PuDbgPrint` at `0x1800520ca`
- `iisutil!PuDbgPrint` at `0x18005200c`
- `iisutil!PuDbgPrint` at `0x1800520ca`
- `iisutil!PuDbgPrintError` at `0x180051f87`
- `iisutil!PuDbgPrintError` at `0x180052209`
- `iisutil!PuDbgPrintError` at `0x180051f87`
- `iisutil!PuDbgPrintError` at `0x180052209`

## string_xrefs

- `0x180051f7c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_cs.cxx`
- `0x180051fef`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_cs.cxx`
- `0x1800520a2`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_cs.cxx`
- `0x1800521fe`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_cs.cxx`
- `0x180051f5c`: ` Failed to get protocols collection \n`
- `0x180051f70`: `PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem`
- `0x180051fe1`: `PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem`
- `0x180052095`: `PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem`
- `0x1800521f2`: `PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem`
- `0x180051fb9`: ` Failed to get count of protocols in the collection \n`
- `0x180052000`: `System has %d protocols \n`
- `0x1800521de`: ` Failed to get a protocol element \n`
- `0x1800521c6`: ` Failed to get the name of the protocol \n`
- `0x1800520ad`: `Retrieved protocol %u '%S' \n`
- `0x1800521a4`: ` Failed to set protocol settings \n`

## pseudocode

```c
__int64 __fastcall PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem(
        PROTOCOL_DATA_OBJECT_TABLE_CS *this,
        struct INativeConfigurationElement *a2)
{
  __int64 v2; // rax
  volatile signed __int32 *v3; // rbx
  __int64 (__fastcall *v5)(struct INativeConfigurationElement *, __int64 *); // rax
  int v6; // edi
  unsigned int v7; // r15d
  unsigned __int16 *v8; // rcx
  PROTOCOL_DATA_OBJECT *v9; // rax
  int inserted; // eax
  __int64 v12; // [rsp+40h] [rbp-10h] BYREF
  __int64 v13; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v14; // [rsp+88h] [rbp+38h] BYREF
  struct INativeConfigurationElement *v15; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int16 *v16; // [rsp+98h] [rbp+48h] BYREF

  v2 = *(_QWORD *)a2;
  v3 = 0;
  v14 = 0;
  v12 = 0;
  v15 = 0;
  v5 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(v2 + 40);
  v16 = 0;
  v13 = 0;
  v6 = v5(a2, &v12);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_cs.cxx",
        231,
        "PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem",
        v6,
        " Failed to get protocols collection \n");
    goto LABEL_36;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v12 + 24LL))(v12, &v14);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_cs.cxx",
        246,
        "PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem",
        v6,
        " Failed to get count of protocols in the collection \n");
    goto LABEL_36;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_cs.cxx",
      255,
      "PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem",
      "System has %d protocols \n",
      v14);
  v7 = 0;
  if ( v14 )
  {
    while ( 1 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v12 + 32LL))(
             v12,
             v7,
             &v15);
      if ( v6 < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_cs.cxx",
            268,
            "PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem",
            v6,
            " Failed to get a protocol element \n");
        goto LABEL_35;
      }
      v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, unsigned __int16 **, __int64 *, _QWORD))(*(_QWORD *)v15 + 64LL))(
             v15,
             L"name",
             &v16,
             &v13,
             0);
      if ( v6 < 0 )
        break;
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
      {
        v8 = L"NULL";
        if ( v16 )
          v8 = v16;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_cs.cxx",
          294,
          "PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem",
          "Retrieved protocol %u '%S' \n",
          v7,
          v8);
      }
      v9 = (PROTOCOL_DATA_OBJECT *)operator new(0x128u);
      v3 = (volatile signed __int32 *)v9;
      if ( !v9 )
      {
        v6 = -2147024888;
LABEL_35:
        v3 = 0;
        goto LABEL_36;
      }
      PROTOCOL_DATA_OBJECT::PROTOCOL_DATA_OBJECT(v9);
      *(_QWORD *)v3 = &PROTOCOL_DATA_OBJECT_CS::`vftable';
      v6 = PROTOCOL_DATA_OBJECT::Create((PROTOCOL_DATA_OBJECT *)v3, v16);
      if ( v6 < 0 )
        goto LABEL_36;
      v16 = 0;
      v6 = PROTOCOL_DATA_OBJECT_CS::SetProtocolSettingsFromConfigStoreData((PROTOCOL_DATA_OBJECT_CS *)v3, v15);
      if ( v6 < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_cs.cxx",
            322,
            "PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem",
            v6,
            " Failed to set protocol settings \n");
        goto LABEL_36;
      }
      inserted = CLKRHashTable::InsertRecord((char *)this + 8, v3, 0);
      if ( (unsigned int)inserted > 1 )
      {
        if ( inserted > 0 )
          v6 = (unsigned __int16)inserted | 0x80070000;
        else
          v6 = inserted;
        goto LABEL_36;
      }
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v3)(v3, 1);
      v3 = 0;
      (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v15 + 16LL))(v15);
      ++v7;
      v15 = 0;
      if ( v7 >= v14 )
        goto LABEL_36;
    }
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_cs.cxx",
        282,
        "PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFromConfigSystem",
        v6,
        " Failed to get the name of the protocol \n");
    goto LABEL_35;
  }
LABEL_36:
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( v3 && _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v3)(v3, 1);
  if ( v15 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180051f08  push    rbp
0x180051f0a  push    rbx
0x180051f0b  push    rdi
0x180051f0c  push    r13
0x180051f0e  push    r15
0x180051f10  mov     rbp, rsp
0x180051f13  sub     rsp, 50h
0x180051f17  mov     rax, [rdx]
0x180051f1a  xor     ebx, ebx
0x180051f1c  mov     r8, rdx
0x180051f1f  mov     [rbp+arg_8], 0
0x180051f26  mov     r13, rcx
0x180051f29  mov     [rbp+var_10], rbx
0x180051f2d  lea     rdx, [rbp+var_10]
0x180051f31  mov     [rbp+arg_10], rbx
0x180051f35  mov     rax, [rax+28h]
0x180051f39  mov     rcx, r8
0x180051f3c  mov     [rbp+arg_18], rbx
0x180051f40  mov     [rbp+var_8], rbx
0x180051f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f49  mov     edi, eax
0x180051f4b  test    eax, eax
0x180051f4d  jns     short loc_180051F92
0x180051f4f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180051f56  jz      loc_180052211
0x180051f5c  lea     rax, aFailedToGetPro; " Failed to get protocols collection \n"
0x180051f63  mov     r8d, 0E7h
0x180051f69  mov     rcx, cs:g_pDebug
0x180051f70  lea     r9, aProtocolDataOb_1; "PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFrom"...
0x180051f77  mov     [rsp+50h+var_28], rax
0x180051f7c  lea     rdx, aServercommonIn_16; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180051f83  mov     dword ptr [rsp+50h+var_30], edi
0x180051f87  call    cs:__imp_PuDbgPrintError
0x180051f8d  jmp     loc_180052211
0x180051f92  mov     rcx, [rbp+var_10]
0x180051f96  lea     rdx, [rbp+arg_8]
0x180051f9a  mov     rax, [rcx]
0x180051f9d  mov     rax, [rax+18h]
0x180051fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051fa6  mov     edi, eax
0x180051fa8  test    eax, eax
0x180051faa  jns     short loc_180051FC8
0x180051fac  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180051fb3  jz      loc_180052211
0x180051fb9  lea     rax, aFailedToGetCou_1; " Failed to get count of protocols in th"...
0x180051fc0  mov     r8d, 0F6h
0x180051fc6  jmp     short loc_180051F69
0x180051fc8  mov     eax, cs:g_dwDebugFlags
0x180051fce  test    al, 3
0x180051fd0  setnz   cl
0x180051fd3  bt      eax, 1Eh
0x180051fd7  setb    al
0x180051fda  test    al, cl
0x180051fdc  jz      short loc_180052012
0x180051fde  mov     eax, [rbp+arg_8]
0x180051fe1  lea     r9, aProtocolDataOb_1; "PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFrom"...
0x180051fe8  mov     rcx, cs:g_pDebug
0x180051fef  lea     rdx, aServercommonIn_16; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180051ff6  mov     dword ptr [rsp+50h+var_28], eax
0x180051ffa  mov     r8d, 0FFh
0x180052000  lea     rax, aSystemHasDProt; "System has %d protocols \n"
0x180052007  mov     [rsp+50h+var_30], rax
0x18005200c  call    cs:__imp_PuDbgPrint
0x180052012  xor     r15d, r15d
0x180052015  cmp     [rbp+arg_8], ebx
0x180052018  jbe     loc_180052211
0x18005201e  mov     rcx, [rbp+var_10]
0x180052022  lea     r8, [rbp+arg_10]
0x180052026  mov     edx, r15d
0x180052029  mov     rax, [rcx]
0x18005202c  mov     rax, [rax+20h]
0x180052030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052035  mov     edi, eax
0x180052037  test    eax, eax
0x180052039  js      loc_1800521D5
0x18005203f  mov     rcx, [rbp+arg_10]
0x180052043  lea     r9, [rbp+var_8]
0x180052047  lea     r8, [rbp+arg_18]
0x18005204b  mov     [rsp+50h+var_30], 0
0x180052054  lea     rdx, aName_0; "name"
0x18005205b  mov     rax, [rcx]
0x18005205e  mov     rax, [rax+40h]
0x180052062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052067  mov     edi, eax
0x180052069  test    eax, eax
0x18005206b  js      loc_1800521BD
0x180052071  mov     eax, cs:g_dwDebugFlags
0x180052077  test    al, 3
0x180052079  setnz   cl
0x18005207c  bt      eax, 1Eh
0x180052080  setb    al
0x180052083  test    al, cl
0x180052085  jz      short loc_1800520D0
0x180052087  mov     rax, [rbp+arg_18]
0x18005208b  lea     rcx, aNull_0; "NULL"
0x180052092  test    rax, rax
0x180052095  lea     r9, aProtocolDataOb_1; "PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFrom"...
0x18005209c  mov     r8d, 126h
0x1800520a2  lea     rdx, aServercommonIn_16; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800520a9  cmovnz  rcx, rax
0x1800520ad  lea     rax, aRetrievedProto; "Retrieved protocol %u '%S' \n"
0x1800520b4  mov     [rsp+50h+var_20], rcx
0x1800520b9  mov     rcx, cs:g_pDebug
0x1800520c0  mov     dword ptr [rsp+50h+var_28], r15d
0x1800520c5  mov     [rsp+50h+var_30], rax
0x1800520ca  call    cs:__imp_PuDbgPrint
0x1800520d0  mov     ecx, 128h; Size
0x1800520d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800520da  mov     rbx, rax
0x1800520dd  test    rax, rax
0x1800520e0  jz      loc_1800521B6
0x1800520e6  mov     rcx, rax; this
0x1800520e9  call    ??0PROTOCOL_DATA_OBJECT@@QEAA@XZ; PROTOCOL_DATA_OBJECT::PROTOCOL_DATA_OBJECT(void)
0x1800520ee  lea     rax, ??_7PROTOCOL_DATA_OBJECT_CS@@6B@; const PROTOCOL_DATA_OBJECT_CS::`vftable'
0x1800520f5  mov     rcx, rbx; this
0x1800520f8  mov     [rbx], rax
0x1800520fb  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x1800520ff  call    ?Create@PROTOCOL_DATA_OBJECT@@QEAAJPEBG@Z; PROTOCOL_DATA_OBJECT::Create(ushort const *)
0x180052104  mov     edi, eax
0x180052106  test    eax, eax
0x180052108  js      loc_180052211
0x18005210e  mov     rdx, [rbp+arg_10]; struct INativeConfigurationElement *
0x180052112  mov     rcx, rbx; this
0x180052115  mov     [rbp+arg_18], 0
0x18005211d  call    ?SetProtocolSettingsFromConfigStoreData@PROTOCOL_DATA_OBJECT_CS@@QEAAJPEAVINativeConfigurationElement@@@Z; PROTOCOL_DATA_OBJECT_CS::SetProtocolSettingsFromConfigStoreData(INativeConfigurationElement *)
0x180052122  mov     edi, eax
0x180052124  test    eax, eax
0x180052126  js      short loc_18005219B
0x180052128  lea     rcx, [r13+8]
0x18005212c  xor     r8d, r8d
0x18005212f  mov     rdx, rbx
0x180052132  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180052138  cmp     eax, 1
0x18005213b  ja      short loc_180052185
0x18005213d  or      eax, 0FFFFFFFFh
0x180052140  lock xadd [rbx+0Ch], eax
0x180052145  cmp     eax, 1
0x180052148  jnz     short loc_18005215D
0x18005214a  mov     rax, [rbx]
0x18005214d  mov     edx, 1
0x180052152  mov     rcx, rbx
0x180052155  mov     rax, [rax]
0x180052158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005215d  mov     rcx, [rbp+arg_10]
0x180052161  xor     ebx, ebx
0x180052163  mov     rax, [rcx]
0x180052166  mov     rax, [rax+10h]
0x18005216a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005216f  inc     r15d
0x180052172  mov     [rbp+arg_10], rbx
0x180052176  cmp     r15d, [rbp+arg_8]
0x18005217a  jb      loc_18005201E
0x180052180  jmp     loc_180052211
0x180052185  test    eax, eax
0x180052187  jg      short loc_180052190
0x180052189  mov     edi, eax
0x18005218b  jmp     loc_180052211
0x180052190  movzx   edi, ax
0x180052193  or      edi, 80070000h
0x180052199  jmp     short loc_180052211
0x18005219b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800521a2  jz      short loc_180052211
0x1800521a4  lea     rax, aFailedToSetPro; " Failed to set protocol settings \n"
0x1800521ab  mov     r8d, 142h
0x1800521b1  jmp     loc_180051F69
0x1800521b6  mov     edi, 80070008h
0x1800521bb  jmp     short loc_18005220F
0x1800521bd  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800521c4  jz      short loc_18005220F
0x1800521c6  lea     rax, aFailedToGetThe_0; " Failed to get the name of the protocol"...
0x1800521cd  mov     r8d, 11Ah
0x1800521d3  jmp     short loc_1800521EB
0x1800521d5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800521dc  jz      short loc_18005220F
0x1800521de  lea     rax, aFailedToGetAPr; " Failed to get a protocol element \n"
0x1800521e5  mov     r8d, 10Ch
0x1800521eb  mov     rcx, cs:g_pDebug
0x1800521f2  lea     r9, aProtocolDataOb_1; "PROTOCOL_DATA_OBJECT_TABLE_CS::ReadFrom"...
0x1800521f9  mov     [rsp+50h+var_28], rax
0x1800521fe  lea     rdx, aServercommonIn_16; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180052205  mov     dword ptr [rsp+50h+var_30], edi
0x180052209  call    cs:__imp_PuDbgPrintError
0x18005220f  xor     ebx, ebx
0x180052211  mov     rcx, [rbp+var_8]
0x180052215  test    rcx, rcx
0x180052218  jz      short loc_18005222E
0x18005221a  mov     rax, [rcx]
0x18005221d  mov     rax, [rax+10h]
0x180052221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052226  mov     [rbp+var_8], 0
0x18005222e  test    rbx, rbx
0x180052231  jz      short loc_180052253
0x180052233  or      eax, 0FFFFFFFFh
0x180052236  lock xadd [rbx+0Ch], eax
0x18005223b  cmp     eax, 1
0x18005223e  jnz     short loc_180052253
0x180052240  mov     rax, [rbx]
0x180052243  mov     edx, 1
0x180052248  mov     rcx, rbx
0x18005224b  mov     rax, [rax]
0x18005224e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052253  mov     rcx, [rbp+arg_10]
0x180052257  test    rcx, rcx
0x18005225a  jz      short loc_180052270
0x18005225c  mov     rax, [rcx]
0x18005225f  mov     rax, [rax+10h]
0x180052263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052268  mov     [rbp+arg_10], 0
0x180052270  mov     rcx, [rbp+var_10]
0x180052274  test    rcx, rcx
0x180052277  jz      short loc_180052285
0x180052279  mov     rax, [rcx]
0x18005227c  mov     rax, [rax+10h]
0x180052280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052285  mov     eax, edi
0x180052287  add     rsp, 50h
0x18005228b  pop     r15
0x18005228d  pop     r13
0x18005228f  pop     rdi
0x180052290  pop     rbx
0x180052291  pop     rbp
0x180052292  retn
```
