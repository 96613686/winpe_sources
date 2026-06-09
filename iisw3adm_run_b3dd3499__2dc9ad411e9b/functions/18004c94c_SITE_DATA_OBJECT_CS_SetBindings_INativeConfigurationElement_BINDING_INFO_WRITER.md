# SITE_DATA_OBJECT_CS::SetBindings(INativeConfigurationElement *,BINDING_INFO_WRITER *)

- ea: `0x18004c94c`
- end: `0x18004cdb3`
- name: `?SetBindings@SITE_DATA_OBJECT_CS@@QEAAJPEAVINativeConfigurationElement@@PEAVBINDING_INFO_WRITER@@@Z`
- size: `1127`
- prototype: `__int64 __fastcall(SITE_DATA_OBJECT_CS *__hidden this, struct INativeConfigurationElement *, struct BINDING_INFO_WRITER *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004c3e0`

## callees

- `0x18004c94c`
- `0x180051254`
- `0x1800515b0`
- `0x1800570f4`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18004caef`
- `iisutil!PuDbgPrint` at `0x18004cb6c`
- `iisutil!PuDbgPrint` at `0x18004cc0d`
- `iisutil!PuDbgPrint` at `0x18004caef`
- `iisutil!PuDbgPrint` at `0x18004cb6c`
- `iisutil!PuDbgPrint` at `0x18004cc0d`
- `iisutil!PuDbgPrintError` at `0x18004cd3a`
- `iisutil!PuDbgPrintError` at `0x18004cd3a`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18004cb98`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18004cb98`

## string_xrefs

- `0x18004ca88`: `protocol`
- `0x18004c9ca`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_cs.cxx`
- `0x18004ca52`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_cs.cxx`
- `0x18004ccff`: ` Failed getting the protocol string \n`
- `0x18004cad7`: ` Protocol '%S' \n`
- `0x18004cc89`: ` Failed adding the binding info to BINDING_INFO_WRITER \n`

## pseudocode

```c
__int64 __fastcall SITE_DATA_OBJECT_CS::SetBindings(
        PROTOCOL_BINDING_LIST **this,
        struct INativeConfigurationElement *a2,
        struct BINDING_INFO_WRITER *a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct INativeConfigurationElement *, const wchar_t *, __int64 *); // rax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  unsigned int v10; // r15d
  int v11; // eax
  int v12; // eax
  unsigned __int16 *v13; // rcx
  int v14; // eax
  unsigned __int16 *v15; // rcx
  int v16; // esi
  int v17; // eax
  const char *v18; // rax
  __int64 v19; // r8
  PROTOCOL_BINDING_LIST *v20; // rcx
  __int64 v22; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int16 *v23; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int16 *v24; // [rsp+40h] [rbp-20h] BYREF
  __int64 v25; // [rsp+48h] [rbp-18h] BYREF
  __int64 v26; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v27; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v28; // [rsp+B8h] [rbp+58h] BYREF

  v3 = *(_QWORD *)a2;
  v25 = 0;
  v22 = 0;
  v26 = 0;
  v6 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *))(v3 + 32);
  v28 = 0;
  v23 = 0;
  v24 = 0;
  v27 = 0;
  v7 = v6(a2, L"bindings", &v26);
  if ( v7 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
        173,
        "SITE_DATA_OBJECT_CS::SetBindings",
        v7,
        " Failed getting bindings element \n");
    goto LABEL_46;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 40LL))(v26, &v25);
  if ( v8 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
        182,
        "SITE_DATA_OBJECT_CS::SetBindings",
        v8,
        " Failed getting binding collection \n");
    goto LABEL_46;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v25 + 24LL))(v25, &v28);
  if ( v9 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
        191,
        "SITE_DATA_OBJECT_CS::SetBindings",
        v9,
        " Failed getting count of bindings in binding collection \n");
    goto LABEL_46;
  }
  v10 = 0;
  if ( v28 )
  {
    while ( 1 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v25 + 32LL))(v25, v10, &v22);
      if ( v11 < 0 )
        break;
      v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v22 + 64LL))(
              v22,
              L"protocol",
              &v23,
              0,
              0);
      if ( v12 < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
            215,
            "SITE_DATA_OBJECT_CS::SetBindings",
            v12,
            " Failed getting the protocol string \n");
        goto LABEL_46;
      }
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
      {
        v13 = L"NULL";
        if ( v23 )
          v13 = v23;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
          223,
          "SITE_DATA_OBJECT_CS::SetBindings",
          " Protocol '%S' \n",
          v13);
      }
      v14 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v22 + 64LL))(
              v22,
              L"bindingInformation",
              &v24,
              0,
              0);
      if ( v14 < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
            235,
            "SITE_DATA_OBJECT_CS::SetBindings",
            v14,
            " Failed getting the binding info \n");
        goto LABEL_46;
      }
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
      {
        v15 = L"NULL";
        if ( v24 )
          v15 = v24;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
          243,
          "SITE_DATA_OBJECT_CS::SetBindings",
          " Binding '%S' \n",
          v15);
      }
      v16 = PROTOCOL_BINDING_LIST::AddBinding(this[8], v23, v24);
      if ( v16 < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) == 0 )
          goto LABEL_46;
        v18 = " Failed setting up the binding info \n";
        v19 = 256;
LABEL_35:
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
          v19,
          "SITE_DATA_OBJECT_CS::SetBindings",
          v16,
          v18);
        goto LABEL_46;
      }
      if ( IsStringEqualOrdinalIgnoreCase(L"HTTPS", v23) )
      {
        v17 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v22 + 48LL))(
                v22,
                L"sslFlags",
                &v27,
                0,
                0);
        if ( v17 < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
              269,
              "SITE_DATA_OBJECT_CS::SetBindings",
              v17,
              " Failed getting the sslFlag \n");
          goto LABEL_46;
        }
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
            277,
            "SITE_DATA_OBJECT_CS::SetBindings",
            " sslFlag '%d' \n",
            v27);
        v16 = BINDING_INFO_WRITER::AddBindingInfo(a3, v24, v27);
        if ( v16 < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_46;
          v18 = " Failed adding the binding info to BINDING_INFO_WRITER \n";
          v19 = 287;
          goto LABEL_35;
        }
        if ( !*((_DWORD *)g_pWebAdminService + 412) && (v27 & 1) != 0 )
          ++*((_DWORD *)this + 82);
      }
      v23 = 0;
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      ++v10;
      v22 = 0;
      if ( v10 >= v28 )
        goto LABEL_48;
    }
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_cs.cxx",
        204,
        "SITE_DATA_OBJECT_CS::SetBindings",
        v11,
        " Failed getting the binding element \n");
LABEL_46:
    v20 = this[8];
    if ( v20 )
    {
      PROTOCOL_BINDING_LIST::Dereference(v20);
      this[8] = 0;
    }
  }
LABEL_48:
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  return 0;
}

```

## disassembly

```asm
0x18004c94c  mov     [rsp-38h+arg_0], rbx
0x18004c951  push    rbp
0x18004c952  push    rsi
0x18004c953  push    rdi
0x18004c954  push    r12
0x18004c956  push    r13
0x18004c958  push    r14
0x18004c95a  push    r15
0x18004c95c  mov     rbp, rsp
0x18004c95f  sub     rsp, 60h
0x18004c963  mov     rax, [rdx]
0x18004c966  xor     r13d, r13d
0x18004c969  mov     r9, rdx
0x18004c96c  mov     [rbp+var_18], r13
0x18004c970  mov     r12, r8
0x18004c973  mov     [rbp+var_30], r13
0x18004c977  mov     r14, rcx
0x18004c97a  mov     [rbp+var_10], r13
0x18004c97e  mov     rax, [rax+20h]
0x18004c982  lea     r8, [rbp+var_10]
0x18004c986  lea     rdx, aBindings; "bindings"
0x18004c98d  mov     [rbp+arg_18], r13d
0x18004c991  mov     rcx, r9
0x18004c994  mov     [rbp+var_28], r13
0x18004c998  mov     [rbp+var_20], r13
0x18004c99c  mov     [rbp+arg_8], r13d
0x18004c9a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c9a5  test    eax, eax
0x18004c9a7  jns     short loc_18004C9D6
0x18004c9a9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004c9b0  jz      loc_18004CD40
0x18004c9b6  lea     rcx, aFailedGettingB; " Failed getting bindings element \n"
0x18004c9bd  mov     r8d, 0ADh
0x18004c9c3  lea     r9, aSiteDataObject; "SITE_DATA_OBJECT_CS::SetBindings"
0x18004c9ca  lea     rdx, aServercommonIn_40; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004c9d1  jmp     loc_18004CD2A
0x18004c9d6  mov     rcx, [rbp+var_10]
0x18004c9da  lea     rdx, [rbp+var_18]
0x18004c9de  mov     rax, [rcx]
0x18004c9e1  mov     rax, [rax+28h]
0x18004c9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c9ea  test    eax, eax
0x18004c9ec  jns     short loc_18004CA0A
0x18004c9ee  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004c9f5  jz      loc_18004CD40
0x18004c9fb  lea     rcx, aFailedGettingB_0; " Failed getting binding collection \n"
0x18004ca02  mov     r8d, 0B6h
0x18004ca08  jmp     short loc_18004C9C3
0x18004ca0a  mov     rcx, [rbp+var_18]
0x18004ca0e  lea     rdx, [rbp+arg_18]
0x18004ca12  mov     rax, [rcx]
0x18004ca15  mov     rax, [rax+18h]
0x18004ca19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca1e  test    eax, eax
0x18004ca20  jns     short loc_18004CA3E
0x18004ca22  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004ca29  jz      loc_18004CD40
0x18004ca2f  lea     rcx, aFailedGettingC_2; " Failed getting count of bindings in bi"...
0x18004ca36  mov     r8d, 0BFh
0x18004ca3c  jmp     short loc_18004C9C3
0x18004ca3e  mov     r15d, r13d
0x18004ca41  cmp     [rbp+arg_18], r13d
0x18004ca45  jbe     loc_18004CD52
0x18004ca4b  lea     rbx, aSiteDataObject; "SITE_DATA_OBJECT_CS::SetBindings"
0x18004ca52  lea     rdi, aServercommonIn_40; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004ca59  mov     rcx, [rbp+var_18]
0x18004ca5d  lea     r8, [rbp+var_30]
0x18004ca61  mov     edx, r15d
0x18004ca64  mov     rax, [rcx]
0x18004ca67  mov     rax, [rax+20h]
0x18004ca6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca70  test    eax, eax
0x18004ca72  js      loc_18004CD0E
0x18004ca78  mov     rcx, [rbp+var_30]
0x18004ca7c  lea     r8, [rbp+var_28]
0x18004ca80  xor     r9d, r9d
0x18004ca83  mov     [rsp+60h+var_40], r13
0x18004ca88  lea     rdx, aProtocol; "protocol"
0x18004ca8f  mov     rax, [rcx]
0x18004ca92  mov     rax, [rax+40h]
0x18004ca96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca9b  test    eax, eax
0x18004ca9d  js      loc_18004CCF6
0x18004caa3  mov     eax, cs:g_dwDebugFlags
0x18004caa9  test    al, 3
0x18004caab  setnz   cl
0x18004caae  bt      eax, 1Eh
0x18004cab2  setb    al
0x18004cab5  test    al, cl
0x18004cab7  jz      short loc_18004CAF5
0x18004cab9  mov     rax, [rbp+var_28]
0x18004cabd  lea     rcx, aNull_0; "NULL"
0x18004cac4  test    rax, rax
0x18004cac7  mov     r9, rbx
0x18004caca  mov     r8d, 0DFh
0x18004cad0  mov     rdx, rdi
0x18004cad3  cmovnz  rcx, rax
0x18004cad7  lea     rax, aProtocolS; " Protocol '%S' \n"
0x18004cade  mov     [rsp+60h+var_38], rcx
0x18004cae3  mov     rcx, cs:g_pDebug
0x18004caea  mov     [rsp+60h+var_40], rax
0x18004caef  call    cs:__imp_PuDbgPrint
0x18004caf5  mov     rcx, [rbp+var_30]
0x18004caf9  lea     r8, [rbp+var_20]
0x18004cafd  xor     r9d, r9d
0x18004cb00  mov     [rsp+60h+var_40], r13
0x18004cb05  lea     rdx, aBindinginforma; "bindingInformation"
0x18004cb0c  mov     rax, [rcx]
0x18004cb0f  mov     rax, [rax+40h]
0x18004cb13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb18  test    eax, eax
0x18004cb1a  js      loc_18004CCDE
0x18004cb20  mov     eax, cs:g_dwDebugFlags
0x18004cb26  test    al, 3
0x18004cb28  setnz   cl
0x18004cb2b  bt      eax, 1Eh
0x18004cb2f  setb    al
0x18004cb32  test    al, cl
0x18004cb34  jz      short loc_18004CB72
0x18004cb36  mov     rax, [rbp+var_20]
0x18004cb3a  lea     rcx, aNull_0; "NULL"
0x18004cb41  test    rax, rax
0x18004cb44  mov     r9, rbx
0x18004cb47  mov     r8d, 0F3h
0x18004cb4d  mov     rdx, rdi
0x18004cb50  cmovnz  rcx, rax
0x18004cb54  lea     rax, aBindingS; " Binding '%S' \n"
0x18004cb5b  mov     [rsp+60h+var_38], rcx
0x18004cb60  mov     rcx, cs:g_pDebug
0x18004cb67  mov     [rsp+60h+var_40], rax
0x18004cb6c  call    cs:__imp_PuDbgPrint
0x18004cb72  mov     r8, [rbp+var_20]; unsigned __int16 *
0x18004cb76  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x18004cb7a  mov     rcx, [r14+40h]; this
0x18004cb7e  call    ?AddBinding@PROTOCOL_BINDING_LIST@@QEAAJPEBG0@Z; PROTOCOL_BINDING_LIST::AddBinding(ushort const *,ushort const *)
0x18004cb83  mov     esi, eax
0x18004cb85  test    eax, eax
0x18004cb87  js      loc_18004CCC6
0x18004cb8d  mov     rdx, [rbp+var_28]
0x18004cb91  lea     rcx, aHttps_0; "HTTPS"
0x18004cb98  call    cs:__imp_?IsStringEqualOrdinalIgnoreCase@@YA_NPEBG0@Z; IsStringEqualOrdinalIgnoreCase(ushort const *,ushort const *)
0x18004cb9e  test    al, al
0x18004cba0  jz      loc_18004CC46
0x18004cba6  mov     rcx, [rbp+var_30]
0x18004cbaa  lea     r8, [rbp+arg_8]
0x18004cbae  xor     r9d, r9d
0x18004cbb1  mov     [rsp+60h+var_40], r13
0x18004cbb6  lea     rdx, aSslflags; "sslFlags"
0x18004cbbd  mov     rax, [rcx]
0x18004cbc0  mov     rax, [rax+30h]
0x18004cbc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbc9  test    eax, eax
0x18004cbcb  js      loc_18004CCAA
0x18004cbd1  mov     eax, cs:g_dwDebugFlags
0x18004cbd7  test    al, 3
0x18004cbd9  setnz   cl
0x18004cbdc  bt      eax, 1Eh
0x18004cbe0  setb    al
0x18004cbe3  test    al, cl
0x18004cbe5  jz      short loc_18004CC13
0x18004cbe7  mov     eax, [rbp+arg_8]
0x18004cbea  mov     r9, rbx
0x18004cbed  mov     rcx, cs:g_pDebug
0x18004cbf4  mov     r8d, 115h
0x18004cbfa  mov     dword ptr [rsp+60h+var_38], eax
0x18004cbfe  mov     rdx, rdi
0x18004cc01  lea     rax, aSslflagD; " sslFlag '%d' \n"
0x18004cc08  mov     [rsp+60h+var_40], rax
0x18004cc0d  call    cs:__imp_PuDbgPrint
0x18004cc13  mov     r8d, [rbp+arg_8]
0x18004cc17  mov     rcx, r12
0x18004cc1a  mov     rdx, [rbp+var_20]
0x18004cc1e  call    ?AddBindingInfo@BINDING_INFO_WRITER@@QEAAJPEBGW4BindingSslFlag@@@Z; BINDING_INFO_WRITER::AddBindingInfo(ushort const *,BindingSslFlag)
0x18004cc23  mov     esi, eax
0x18004cc25  test    eax, eax
0x18004cc27  js      short loc_18004CC7C
0x18004cc29  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18004cc30  cmp     [rax+670h], r13d
0x18004cc37  jnz     short loc_18004CC46
0x18004cc39  test    byte ptr [rbp+arg_8], 1
0x18004cc3d  jz      short loc_18004CC46
0x18004cc3f  inc     dword ptr [r14+148h]
0x18004cc46  mov     rcx, [rbp+var_30]
0x18004cc4a  mov     [rbp+var_28], r13
0x18004cc4e  mov     [rbp+var_20], r13
0x18004cc52  mov     rax, [rcx]
0x18004cc55  mov     rax, [rax+10h]
0x18004cc59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc5e  inc     r15d
0x18004cc61  mov     [rbp+var_30], r13
0x18004cc65  cmp     r15d, [rbp+arg_18]
0x18004cc69  jb      loc_18004CA59
0x18004cc6f  test    esi, esi
0x18004cc71  jns     loc_18004CD52
0x18004cc77  jmp     loc_18004CD40
0x18004cc7c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004cc83  jz      loc_18004CD40
0x18004cc89  lea     rax, aFailedAddingTh_0; " Failed adding the binding info to BIND"...
0x18004cc90  mov     r8d, 11Fh
0x18004cc96  mov     [rsp+60h+var_38], rax
0x18004cc9b  mov     r9, rbx
0x18004cc9e  mov     dword ptr [rsp+60h+var_40], esi
0x18004cca2  mov     rdx, rdi
0x18004cca5  jmp     loc_18004CD33
0x18004ccaa  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004ccb1  jz      loc_18004CD40
0x18004ccb7  lea     rcx, aFailedGettingT_2; " Failed getting the sslFlag \n"
0x18004ccbe  mov     r8d, 10Dh
0x18004ccc4  jmp     short loc_18004CD24
0x18004ccc6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004cccd  jz      short loc_18004CD40
0x18004cccf  lea     rax, aFailedSettingU_0; " Failed setting up the binding info \n"
0x18004ccd6  mov     r8d, 100h
0x18004ccdc  jmp     short loc_18004CC96
0x18004ccde  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004cce5  jz      short loc_18004CD40
0x18004cce7  lea     rcx, aFailedGettingT_1; " Failed getting the binding info \n"
0x18004ccee  mov     r8d, 0EBh
0x18004ccf4  jmp     short loc_18004CD24
0x18004ccf6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004ccfd  jz      short loc_18004CD40
0x18004ccff  lea     rcx, aFailedGettingT; " Failed getting the protocol string \n"
0x18004cd06  mov     r8d, 0D7h
0x18004cd0c  jmp     short loc_18004CD24
0x18004cd0e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004cd15  jz      short loc_18004CD40
0x18004cd17  lea     rcx, aFailedGettingT_0; " Failed getting the binding element \n"
0x18004cd1e  mov     r8d, 0CCh
0x18004cd24  mov     rdx, rdi
0x18004cd27  mov     r9, rbx
0x18004cd2a  mov     [rsp+60h+var_38], rcx
0x18004cd2f  mov     dword ptr [rsp+60h+var_40], eax
0x18004cd33  mov     rcx, cs:g_pDebug
0x18004cd3a  call    cs:__imp_PuDbgPrintError
0x18004cd40  mov     rcx, [r14+40h]; this
0x18004cd44  test    rcx, rcx
0x18004cd47  jz      short loc_18004CD52
0x18004cd49  call    ?Dereference@PROTOCOL_BINDING_LIST@@QEAAXXZ; PROTOCOL_BINDING_LIST::Dereference(void)
0x18004cd4e  mov     [r14+40h], r13
0x18004cd52  mov     rcx, [rbp+var_30]
0x18004cd56  test    rcx, rcx
0x18004cd59  jz      short loc_18004CD6B
0x18004cd5b  mov     rax, [rcx]
0x18004cd5e  mov     rax, [rax+10h]
0x18004cd62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd67  mov     [rbp+var_30], r13
0x18004cd6b  mov     rcx, [rbp+var_18]
0x18004cd6f  test    rcx, rcx
0x18004cd72  jz      short loc_18004CD84
0x18004cd74  mov     rax, [rcx]
0x18004cd77  mov     rax, [rax+10h]
0x18004cd7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd80  mov     [rbp+var_18], r13
0x18004cd84  mov     rcx, [rbp+var_10]
0x18004cd88  test    rcx, rcx
0x18004cd8b  jz      short loc_18004CD99
0x18004cd8d  mov     rax, [rcx]
0x18004cd90  mov     rax, [rax+10h]
0x18004cd94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd99  mov     rbx, [rsp+60h+arg_0]
0x18004cda1  xor     eax, eax
0x18004cda3  add     rsp, 60h
0x18004cda7  pop     r15
0x18004cda9  pop     r14
0x18004cdab  pop     r13
0x18004cdad  pop     r12
0x18004cdaf  pop     rdi
0x18004cdb0  pop     rsi
0x18004cdb1  pop     rbp
0x18004cdb2  retn
```
