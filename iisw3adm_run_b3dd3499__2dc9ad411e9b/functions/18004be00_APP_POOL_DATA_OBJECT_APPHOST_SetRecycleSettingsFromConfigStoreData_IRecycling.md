# APP_POOL_DATA_OBJECT_APPHOST::SetRecycleSettingsFromConfigStoreData(IRecycling *)

- ea: `0x18004be00`
- end: `0x18004c056`
- name: `?SetRecycleSettingsFromConfigStoreData@APP_POOL_DATA_OBJECT_APPHOST@@QEAAJPEAUIRecycling@@@Z`
- size: `598`
- prototype: `__int64 __fastcall(APP_POOL_DATA_OBJECT_APPHOST *__hidden this, struct IRecycling *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180048f34`

## callees

- `0x18004a980`
- `0x18004be00`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18004beda`
- `iisutil!PuDbgPrint` at `0x18004bf71`
- `iisutil!PuDbgPrint` at `0x18004bff2`
- `iisutil!PuDbgPrint` at `0x18004beda`
- `iisutil!PuDbgPrint` at `0x18004bf71`
- `iisutil!PuDbgPrint` at `0x18004bff2`
- `iisutil!PuDbgPrintError` at `0x18004c035`
- `iisutil!PuDbgPrintError` at `0x18004c035`

## string_xrefs

- `0x18004be4a`: ` Failed reading property \n`
- `0x18004bf0e`: ` Failed reading property \n`
- `0x18004bfa3`: ` Failed reading property \n`
- `0x18004bf4e`: ` Don't Rotate on Config Change = %S \n`
- `0x18004be5e`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_apphost.cxx`
- `0x18004be79`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_apphost.cxx`
- `0x18004be57`: `APP_POOL_DATA_OBJECT_APPHOST::SetRecycleSettingsFromConfigStoreData`
- `0x18004be70`: `APP_POOL_DATA_OBJECT_APPHOST::SetRecycleSettingsFromConfigStoreData`

## pseudocode

```c
__int64 __fastcall APP_POOL_DATA_OBJECT_APPHOST::SetRecycleSettingsFromConfigStoreData(
        APP_POOL_DATA_OBJECT_APPHOST *this,
        struct IRecycling *a2)
{
  int v4; // ebx
  int v5; // eax
  const wchar_t *v6; // r15
  BOOL v7; // edx
  bool v8; // zf
  const wchar_t *v9; // rax
  const char *v10; // rax
  __int64 v11; // r8
  int v12; // eax
  BOOL v13; // edx
  __int16 v15; // [rsp+78h] [rbp+10h] BYREF

  v15 = 0;
  v4 = (*(__int64 (__fastcall **)(struct IRecycling *, __int16 *))(*(_QWORD *)a2 + 56LL))(a2, &v15);
  if ( v4 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
        869,
        "APP_POOL_DATA_OBJECT_APPHOST::SetRecycleSettingsFromConfigStoreData",
        v4,
        " Failed reading property \n");
    return (unsigned int)v4;
  }
  v5 = g_dwDebugFlags;
  v6 = L"TRUE";
  v7 = v15 == -1;
  v8 = (g_dwDebugFlags & 3) == 0;
  *((_DWORD *)this + 60) = v7;
  if ( !v8 && (v5 & 0x40000000) != 0 )
  {
    v9 = L"TRUE";
    if ( !v7 )
      v9 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
      878,
      "APP_POOL_DATA_OBJECT_APPHOST::SetRecycleSettingsFromConfigStoreData",
      " Don't Overlapped = %S \n",
      v9);
  }
  v15 = 0;
  v4 = (*(__int64 (__fastcall **)(struct IRecycling *, __int16 *))(*(_QWORD *)a2 + 64LL))(a2, &v15);
  if ( v4 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      return (unsigned int)v4;
    v10 = " Failed reading property \n";
    v11 = 887;
LABEL_23:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
      v11,
      "APP_POOL_DATA_OBJECT_APPHOST::SetRecycleSettingsFromConfigStoreData",
      v4,
      v10);
    return (unsigned int)v4;
  }
  v12 = g_dwDebugFlags;
  v13 = v15 == -1;
  v8 = (g_dwDebugFlags & 3) == 0;
  *((_DWORD *)this + 91) = v13;
  if ( !v8 && (v12 & 0x40000000) != 0 )
  {
    if ( !v13 )
      v6 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
      896,
      "APP_POOL_DATA_OBJECT_APPHOST::SetRecycleSettingsFromConfigStoreData",
      " Don't Rotate on Config Change = %S \n",
      v6);
  }
  v4 = (*(__int64 (__fastcall **)(struct IRecycling *, char *))(*(_QWORD *)a2 + 72LL))(a2, (char *)this + 724);
  if ( v4 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      return (unsigned int)v4;
    v10 = " Failed reading property \n";
    v11 = 904;
    goto LABEL_23;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
      913,
      "APP_POOL_DATA_OBJECT_APPHOST::SetRecycleSettingsFromConfigStoreData",
      " Recycle Logging Flag = %u (0x%X) \n",
      *((_DWORD *)this + 181),
      *((_DWORD *)this + 181));
  v4 = APP_POOL_DATA_OBJECT_APPHOST::SetPeriodicRestart(this, a2);
  if ( v4 < 0 && (g_dwDebugFlags & 0xF) != 0 )
  {
    v10 = " Failed setting up Periodic Restart\n";
    v11 = 921;
    goto LABEL_23;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004be00  mov     [rsp+arg_0], rbx
0x18004be05  mov     [rsp+arg_10], rbp
0x18004be0a  push    rsi
0x18004be0b  push    rdi
0x18004be0c  push    r13
0x18004be0e  push    r14
0x18004be10  push    r15
0x18004be12  sub     rsp, 40h
0x18004be16  xor     eax, eax
0x18004be18  mov     r14, rdx
0x18004be1b  mov     [rsp+68h+arg_8], ax
0x18004be20  mov     rbp, rcx
0x18004be23  mov     rax, [rdx]
0x18004be26  mov     rcx, r14
0x18004be29  lea     rdx, [rsp+68h+arg_8]
0x18004be2e  mov     rax, [rax+38h]
0x18004be32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be37  mov     ebx, eax
0x18004be39  test    eax, eax
0x18004be3b  jns     short loc_18004BE6A
0x18004be3d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004be44  jz      loc_18004C03B
0x18004be4a  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004be51  mov     r8d, 365h
0x18004be57  lea     r9, aAppPoolDataObj_4; "APP_POOL_DATA_OBJECT_APPHOST::SetRecycl"...
0x18004be5e  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004be65  jmp     loc_18004C025
0x18004be6a  mov     eax, cs:g_dwDebugFlags
0x18004be70  lea     rdi, aAppPoolDataObj_4; "APP_POOL_DATA_OBJECT_APPHOST::SetRecycl"...
0x18004be77  xor     edx, edx
0x18004be79  lea     rsi, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004be80  cmp     [rsp+68h+arg_8], 0FFFFh
0x18004be86  lea     r13, aFalse_1; "FALSE"
0x18004be8d  lea     r15, aTrue_1; "TRUE"
0x18004be94  setz    dl
0x18004be97  test    al, 3
0x18004be99  mov     [rbp+0F0h], edx
0x18004be9f  setnz   cl
0x18004bea2  bt      eax, 1Eh
0x18004bea6  setb    al
0x18004bea9  test    al, cl
0x18004beab  jz      short loc_18004BEE0
0x18004bead  mov     rcx, cs:g_pDebug
0x18004beb4  test    edx, edx
0x18004beb6  mov     rax, r15
0x18004beb9  mov     r9, rdi
0x18004bebc  cmovz   rax, r13
0x18004bec0  mov     r8d, 36Eh
0x18004bec6  mov     [rsp+68h+var_40], rax
0x18004becb  mov     rdx, rsi
0x18004bece  lea     rax, aDonTOverlapped; " Don't Overlapped = %S \n"
0x18004bed5  mov     [rsp+68h+var_48], rax
0x18004beda  call    cs:__imp_PuDbgPrint
0x18004bee0  xor     eax, eax
0x18004bee2  lea     rdx, [rsp+68h+arg_8]
0x18004bee7  mov     [rsp+68h+arg_8], ax
0x18004beec  mov     rcx, r14
0x18004beef  mov     rax, [r14]
0x18004bef2  mov     rax, [rax+40h]
0x18004bef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004befb  mov     ebx, eax
0x18004befd  test    eax, eax
0x18004beff  jns     short loc_18004BF20
0x18004bf01  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004bf08  jz      loc_18004C03B
0x18004bf0e  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004bf15  mov     r8d, 377h
0x18004bf1b  jmp     loc_18004C01F
0x18004bf20  mov     eax, cs:g_dwDebugFlags
0x18004bf26  xor     edx, edx
0x18004bf28  cmp     [rsp+68h+arg_8], 0FFFFh
0x18004bf2e  setz    dl
0x18004bf31  test    al, 3
0x18004bf33  mov     [rbp+16Ch], edx
0x18004bf39  setnz   cl
0x18004bf3c  bt      eax, 1Eh
0x18004bf40  setb    al
0x18004bf43  test    al, cl
0x18004bf45  jz      short loc_18004BF77
0x18004bf47  mov     rcx, cs:g_pDebug
0x18004bf4e  lea     rax, aDonTRotateOnCo; " Don't Rotate on Config Change = %S \n"
0x18004bf55  test    edx, edx
0x18004bf57  mov     r9, rdi
0x18004bf5a  mov     r8d, 380h
0x18004bf60  mov     rdx, rsi
0x18004bf63  cmovz   r15, r13
0x18004bf67  mov     [rsp+68h+var_40], r15
0x18004bf6c  mov     [rsp+68h+var_48], rax
0x18004bf71  call    cs:__imp_PuDbgPrint
0x18004bf77  mov     rax, [r14]
0x18004bf7a  lea     r15, [rbp+2D4h]
0x18004bf81  mov     rdx, r15
0x18004bf84  mov     rcx, r14
0x18004bf87  mov     rax, [rax+48h]
0x18004bf8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf90  mov     ebx, eax
0x18004bf92  test    eax, eax
0x18004bf94  jns     short loc_18004BFB2
0x18004bf96  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004bf9d  jz      loc_18004C03B
0x18004bfa3  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004bfaa  mov     r8d, 388h
0x18004bfb0  jmp     short loc_18004C01F
0x18004bfb2  mov     eax, cs:g_dwDebugFlags
0x18004bfb8  test    al, 3
0x18004bfba  setnz   cl
0x18004bfbd  bt      eax, 1Eh
0x18004bfc1  setb    al
0x18004bfc4  test    al, cl
0x18004bfc6  jz      short loc_18004BFF8
0x18004bfc8  mov     eax, [r15]
0x18004bfcb  mov     r9, rdi
0x18004bfce  mov     rcx, cs:g_pDebug
0x18004bfd5  mov     r8d, 391h
0x18004bfdb  mov     [rsp+68h+var_38], eax
0x18004bfdf  mov     rdx, rsi
0x18004bfe2  mov     dword ptr [rsp+68h+var_40], eax
0x18004bfe6  lea     rax, aRecycleLogging; " Recycle Logging Flag = %u (0x%X) \n"
0x18004bfed  mov     [rsp+68h+var_48], rax
0x18004bff2  call    cs:__imp_PuDbgPrint
0x18004bff8  mov     rdx, r14; struct IRecycling *
0x18004bffb  mov     rcx, rbp; this
0x18004bffe  call    ?SetPeriodicRestart@APP_POOL_DATA_OBJECT_APPHOST@@AEAAJPEAUIRecycling@@@Z; APP_POOL_DATA_OBJECT_APPHOST::SetPeriodicRestart(IRecycling *)
0x18004c003  mov     ebx, eax
0x18004c005  test    eax, eax
0x18004c007  jns     short loc_18004C03B
0x18004c009  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004c010  jz      short loc_18004C03B
0x18004c012  lea     rax, aFailedSettingU; " Failed setting up Periodic Restart\n"
0x18004c019  mov     r8d, 399h
0x18004c01f  mov     r9, rdi
0x18004c022  mov     rdx, rsi
0x18004c025  mov     rcx, cs:g_pDebug
0x18004c02c  mov     [rsp+68h+var_40], rax
0x18004c031  mov     dword ptr [rsp+68h+var_48], ebx
0x18004c035  call    cs:__imp_PuDbgPrintError
0x18004c03b  lea     r11, [rsp+68h+var_28]
0x18004c040  mov     eax, ebx
0x18004c042  mov     rbx, [r11+30h]
0x18004c046  mov     rbp, [r11+40h]
0x18004c04a  mov     rsp, r11
0x18004c04d  pop     r15
0x18004c04f  pop     r14
0x18004c051  pop     r13
0x18004c053  pop     rdi
0x18004c054  pop     rsi
0x18004c055  retn
```
