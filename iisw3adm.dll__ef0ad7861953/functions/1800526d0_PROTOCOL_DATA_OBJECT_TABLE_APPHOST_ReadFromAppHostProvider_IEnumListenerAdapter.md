# PROTOCOL_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider(IEnumListenerAdapter *)

- ea: `0x1800526d0`
- end: `0x1800529b0`
- name: `?ReadFromAppHostProvider@PROTOCOL_DATA_OBJECT_TABLE_APPHOST@@QEAAJPEAUIEnumListenerAdapter@@@Z`
- size: `736`
- prototype: `__int64 __fastcall(PROTOCOL_DATA_OBJECT_TABLE_APPHOST *__hidden this, struct IEnumListenerAdapter *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005aaa0`

## callees

- `0x180001234`
- `0x1800517d0`
- `0x180051af4`
- `0x1800526d0`
- `0x1800529b8`
- `0x18006101a`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800527ef`
- `OLEAUT32!__imp_SysFreeString` at `0x180052955`
- `OLEAUT32!__imp_SysFreeString` at `0x1800527ef`
- `OLEAUT32!__imp_SysFreeString` at `0x180052955`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180052819`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180052819`
- `iisutil!PuDbgPrint` at `0x180052792`
- `iisutil!PuDbgPrint` at `0x180052946`
- `iisutil!PuDbgPrint` at `0x180052792`
- `iisutil!PuDbgPrint` at `0x180052946`
- `iisutil!PuDbgPrintError` at `0x1800528b3`
- `iisutil!PuDbgPrintError` at `0x1800528f9`
- `iisutil!PuDbgPrintError` at `0x1800528b3`
- `iisutil!PuDbgPrintError` at `0x1800528f9`

## string_xrefs

- `0x180052922`: `System has %d protocols \n`
- `0x1800528d5`: ` Failed to get the name of the protocol \n`
- `0x180052786`: `Retrieved protocol %u '%S' \n`
- `0x18005288f`: ` Failed to set protocol settings \n`
- `0x180052768`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_apphost.cxx`
- `0x1800528ac`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_apphost.cxx`
- `0x1800528f2`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_apphost.cxx`
- `0x18005293f`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_apphost.cxx`
- `0x18005275b`: `PROTOCOL_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider`
- `0x18005289b`: `PROTOCOL_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider`
- `0x1800528e1`: `PROTOCOL_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider`
- `0x18005292d`: `PROTOCOL_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider`

## pseudocode

```c
__int64 __fastcall PROTOCOL_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider(
        PROTOCOL_DATA_OBJECT_TABLE_APPHOST *this,
        struct IEnumListenerAdapter *a2)
{
  int v2; // esi
  int v5; // edi
  const wchar_t *v6; // rcx
  volatile signed __int32 *v7; // rax
  volatile signed __int32 *v8; // rbx
  int inserted; // eax
  BSTR bstrString; // [rsp+78h] [rbp+38h] BYREF
  struct IListenerAdapter *v12; // [rsp+80h] [rbp+40h] BYREF

  v2 = 0;
  v12 = 0;
  bstrString = 0;
  while ( 1 )
  {
    v5 = (*(__int64 (__fastcall **)(struct IEnumListenerAdapter *, struct IListenerAdapter **))(*(_QWORD *)a2 + 56LL))(
           a2,
           &v12);
    if ( v5 < 0 || !v12 )
      break;
    v5 = (*(__int64 (__fastcall **)(struct IListenerAdapter *, BSTR *))(*(_QWORD *)v12 + 56LL))(v12, &bstrString);
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_apphost.cxx",
          201,
          "PROTOCOL_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider",
          v5,
          " Failed to get the name of the protocol \n");
      goto LABEL_25;
    }
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    {
      v6 = L"NULL";
      if ( bstrString )
        v6 = bstrString;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_apphost.cxx",
        211,
        "PROTOCOL_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider",
        "Retrieved protocol %u '%S' \n",
        v2 + 1,
        v6);
    }
    v7 = (volatile signed __int32 *)operator new(0x128u);
    v8 = v7;
    if ( !v7 )
    {
      v5 = -2147024888;
LABEL_25:
      v8 = 0;
      goto LABEL_28;
    }
    memset_0((void *)v7, 0, 0x128u);
    PROTOCOL_DATA_OBJECT::PROTOCOL_DATA_OBJECT((PROTOCOL_DATA_OBJECT *)v8);
    *(_QWORD *)v8 = &PROTOCOL_DATA_OBJECT_CS::`vftable';
    v5 = PROTOCOL_DATA_OBJECT::Create((PROTOCOL_DATA_OBJECT *)v8, bstrString);
    if ( v5 < 0 )
      goto LABEL_28;
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    v5 = PROTOCOL_DATA_OBJECT_APPHOST::SetProtocolSettingsFromConfigStoreData((PROTOCOL_DATA_OBJECT_APPHOST *)v8, v12);
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_apphost.cxx",
          242,
          "PROTOCOL_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider",
          v5,
          " Failed to set protocol settings \n");
      goto LABEL_28;
    }
    inserted = CLKRHashTable::InsertRecord((char *)this + 8, v8, 0);
    v5 = inserted;
    if ( (unsigned int)inserted > 1 )
    {
      if ( inserted > 0 )
        v5 = (unsigned __int16)inserted | 0x80070000;
      goto LABEL_28;
    }
    if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v8)(v8, 1);
    (*(void (__fastcall **)(struct IListenerAdapter *))(*(_QWORD *)v12 + 16LL))(v12);
    ++v2;
    v12 = 0;
  }
  v8 = 0;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_apphost.cxx",
      277,
      "PROTOCOL_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider",
      "System has %d protocols \n",
      v2);
LABEL_28:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v8 && _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v8)(v8, 1);
  if ( v12 )
    (*(void (__fastcall **)(struct IListenerAdapter *))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800526d0  mov     [rsp-28h+arg_0], rbx
0x1800526d5  push    rbp
0x1800526d6  push    rsi
0x1800526d7  push    rdi
0x1800526d8  push    r14
0x1800526da  push    r15
0x1800526dc  mov     rbp, rsp
0x1800526df  sub     rsp, 40h
0x1800526e3  xor     esi, esi
0x1800526e5  mov     r14, rdx
0x1800526e8  mov     [rbp+arg_10], rsi
0x1800526ec  mov     r15, rcx
0x1800526ef  mov     [rbp+bstrString], rsi
0x1800526f3  mov     rax, [r14]
0x1800526f6  lea     rdx, [rbp+arg_10]
0x1800526fa  mov     rcx, r14
0x1800526fd  mov     rax, [rax+38h]
0x180052701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052706  mov     edi, eax
0x180052708  test    eax, eax
0x18005270a  js      loc_180052903
0x180052710  mov     rcx, [rbp+arg_10]
0x180052714  test    rcx, rcx
0x180052717  jz      loc_180052903
0x18005271d  mov     rax, [rcx]
0x180052720  lea     rdx, [rbp+bstrString]
0x180052724  mov     rax, [rax+38h]
0x180052728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005272d  mov     edi, eax
0x18005272f  test    eax, eax
0x180052731  js      loc_1800528C5
0x180052737  mov     eax, cs:g_dwDebugFlags
0x18005273d  test    al, 3
0x18005273f  setnz   cl
0x180052742  bt      eax, 1Eh
0x180052746  setb    al
0x180052749  test    al, cl
0x18005274b  jz      short loc_180052798
0x18005274d  mov     rax, [rbp+bstrString]
0x180052751  lea     rcx, aNull_0; "NULL"
0x180052758  test    rax, rax
0x18005275b  lea     r9, aProtocolDataOb_0; "PROTOCOL_DATA_OBJECT_TABLE_APPHOST::Rea"...
0x180052762  mov     r8d, 0D3h
0x180052768  lea     rdx, aServercommonIn_8; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18005276f  cmovnz  rcx, rax
0x180052773  lea     eax, [rsi+1]
0x180052776  mov     [rsp+40h+var_10], rcx
0x18005277b  mov     rcx, cs:g_pDebug
0x180052782  mov     dword ptr [rsp+40h+var_18], eax
0x180052786  lea     rax, aRetrievedProto; "Retrieved protocol %u '%S' \n"
0x18005278d  mov     [rsp+40h+var_20], rax
0x180052792  call    cs:__imp_PuDbgPrint
0x180052798  mov     ecx, 128h; Size
0x18005279d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800527a2  mov     rbx, rax
0x1800527a5  test    rax, rax
0x1800527a8  jz      loc_1800528BE
0x1800527ae  xor     edx, edx; Val
0x1800527b0  mov     r8d, 128h; Size
0x1800527b6  mov     rcx, rax; void *
0x1800527b9  call    memset_0
0x1800527be  mov     rcx, rbx; this
0x1800527c1  call    ??0PROTOCOL_DATA_OBJECT@@QEAA@XZ; PROTOCOL_DATA_OBJECT::PROTOCOL_DATA_OBJECT(void)
0x1800527c6  lea     rax, ??_7PROTOCOL_DATA_OBJECT_CS@@6B@; const PROTOCOL_DATA_OBJECT_CS::`vftable'
0x1800527cd  mov     rcx, rbx; this
0x1800527d0  mov     [rbx], rax
0x1800527d3  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x1800527d7  call    ?Create@PROTOCOL_DATA_OBJECT@@QEAAJPEBG@Z; PROTOCOL_DATA_OBJECT::Create(ushort const *)
0x1800527dc  mov     edi, eax
0x1800527de  test    eax, eax
0x1800527e0  js      loc_18005294C
0x1800527e6  mov     rcx, [rbp+bstrString]; bstrString
0x1800527ea  test    rcx, rcx
0x1800527ed  jz      short loc_1800527FD
0x1800527ef  call    cs:__imp_SysFreeString
0x1800527f5  mov     [rbp+bstrString], 0
0x1800527fd  mov     rdx, [rbp+arg_10]; struct IListenerAdapter *
0x180052801  mov     rcx, rbx; this
0x180052804  call    ?SetProtocolSettingsFromConfigStoreData@PROTOCOL_DATA_OBJECT_APPHOST@@QEAAJPEAUIListenerAdapter@@@Z; PROTOCOL_DATA_OBJECT_APPHOST::SetProtocolSettingsFromConfigStoreData(IListenerAdapter *)
0x180052809  mov     edi, eax
0x18005280b  test    eax, eax
0x18005280d  js      short loc_18005287B
0x18005280f  lea     rcx, [r15+8]
0x180052813  xor     r8d, r8d
0x180052816  mov     rdx, rbx
0x180052819  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18005281f  mov     edi, eax
0x180052821  cmp     eax, 1
0x180052824  ja      short loc_180052865
0x180052826  or      eax, 0FFFFFFFFh
0x180052829  lock xadd [rbx+0Ch], eax
0x18005282e  cmp     eax, 1
0x180052831  jnz     short loc_180052846
0x180052833  mov     rax, [rbx]
0x180052836  mov     edx, 1
0x18005283b  mov     rcx, rbx
0x18005283e  mov     rax, [rax]
0x180052841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052846  mov     rcx, [rbp+arg_10]
0x18005284a  mov     rax, [rcx]
0x18005284d  mov     rax, [rax+10h]
0x180052851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052856  inc     esi
0x180052858  mov     [rbp+arg_10], 0
0x180052860  jmp     loc_1800526F3
0x180052865  test    eax, eax
0x180052867  jle     loc_18005294C
0x18005286d  movzx   edi, ax
0x180052870  or      edi, 80070000h
0x180052876  jmp     loc_18005294C
0x18005287b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180052882  jz      loc_18005294C
0x180052888  mov     rcx, cs:g_pDebug
0x18005288f  lea     rax, aFailedToSetPro; " Failed to set protocol settings \n"
0x180052896  mov     [rsp+40h+var_18], rax
0x18005289b  lea     r9, aProtocolDataOb_0; "PROTOCOL_DATA_OBJECT_TABLE_APPHOST::Rea"...
0x1800528a2  mov     r8d, 0F2h
0x1800528a8  mov     dword ptr [rsp+40h+var_20], edi
0x1800528ac  lea     rdx, aServercommonIn_8; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800528b3  call    cs:__imp_PuDbgPrintError
0x1800528b9  jmp     loc_18005294C
0x1800528be  mov     edi, 80070008h
0x1800528c3  jmp     short loc_1800528FF
0x1800528c5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800528cc  jz      short loc_1800528FF
0x1800528ce  mov     rcx, cs:g_pDebug
0x1800528d5  lea     rax, aFailedToGetThe_0; " Failed to get the name of the protocol"...
0x1800528dc  mov     [rsp+40h+var_18], rax
0x1800528e1  lea     r9, aProtocolDataOb_0; "PROTOCOL_DATA_OBJECT_TABLE_APPHOST::Rea"...
0x1800528e8  mov     r8d, 0C9h
0x1800528ee  mov     dword ptr [rsp+40h+var_20], edi
0x1800528f2  lea     rdx, aServercommonIn_8; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800528f9  call    cs:__imp_PuDbgPrintError
0x1800528ff  xor     ebx, ebx
0x180052901  jmp     short loc_18005294C
0x180052903  mov     eax, cs:g_dwDebugFlags
0x180052909  xor     ebx, ebx
0x18005290b  test    al, 3
0x18005290d  setnz   cl
0x180052910  bt      eax, 1Eh
0x180052914  setb    al
0x180052917  test    al, cl
0x180052919  jz      short loc_18005294C
0x18005291b  mov     rcx, cs:g_pDebug
0x180052922  lea     rax, aSystemHasDProt; "System has %d protocols \n"
0x180052929  mov     dword ptr [rsp+40h+var_18], esi
0x18005292d  lea     r9, aProtocolDataOb_0; "PROTOCOL_DATA_OBJECT_TABLE_APPHOST::Rea"...
0x180052934  mov     r8d, 115h
0x18005293a  mov     [rsp+40h+var_20], rax
0x18005293f  lea     rdx, aServercommonIn_8; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180052946  call    cs:__imp_PuDbgPrint
0x18005294c  mov     rcx, [rbp+bstrString]; bstrString
0x180052950  test    rcx, rcx
0x180052953  jz      short loc_180052963
0x180052955  call    cs:__imp_SysFreeString
0x18005295b  mov     [rbp+bstrString], 0
0x180052963  test    rbx, rbx
0x180052966  jz      short loc_180052988
0x180052968  or      eax, 0FFFFFFFFh
0x18005296b  lock xadd [rbx+0Ch], eax
0x180052970  cmp     eax, 1
0x180052973  jnz     short loc_180052988
0x180052975  mov     rax, [rbx]
0x180052978  mov     edx, 1
0x18005297d  mov     rcx, rbx
0x180052980  mov     rax, [rax]
0x180052983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052988  mov     rcx, [rbp+arg_10]
0x18005298c  test    rcx, rcx
0x18005298f  jz      short loc_18005299D
0x180052991  mov     rax, [rcx]
0x180052994  mov     rax, [rax+10h]
0x180052998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005299d  mov     rbx, [rsp+40h+arg_0]
0x1800529a2  mov     eax, edi
0x1800529a4  add     rsp, 40h
0x1800529a8  pop     r15
0x1800529aa  pop     r14
0x1800529ac  pop     rdi
0x1800529ad  pop     rsi
0x1800529ae  pop     rbp
0x1800529af  retn
```
