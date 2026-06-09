# ParseManifestDirectives(_PSETUP_LOCAL_DATA *,_MANIFEST_CALLBACK_CONTEXT *)

- ea: `0x180032a34`
- end: `0x180032e9c`
- name: `?ParseManifestDirectives@@YAJPEAU_PSETUP_LOCAL_DATA@@PEAU_MANIFEST_CALLBACK_CONTEXT@@@Z`
- size: `1128`
- prototype: `__int64 __fastcall(struct _PSETUP_LOCAL_DATA *, struct _MANIFEST_CALLBACK_CONTEXT *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800340b4`

## callees

- `0x180002300`
- `0x18000b200`
- `0x18000d57c`
- `0x18000d624`
- `0x1800162c8`
- `0x180017810`
- `0x18001bc44`
- `0x1800216f0`
- `0x180032210`
- `0x180032a34`
- `0x180032ea4`
- `0x180033e28`
- `0x180034a60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180032bac`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180032bd1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180032bac`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180032bd1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180032b7b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180032c0b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180032b7b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180032c0b`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180032a9e`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180032a9e`

## string_xrefs

- `0x180032dbf`: `Manifest does not contain a PrinterDriverID: hr: 0x%x`
- `0x180032abe`: `ParseManifestDirectives`
- `0x180032b4c`: `ParseManifestDirectives`
- `0x180032dc6`: `ParseManifestDirectives`
- `0x180032c95`: `DriverFile was specified in the manifest, which is only allowed for class drivers.`

## pseudocode

```c
__int64 __fastcall ParseManifestDirectives(struct _PSETUP_LOCAL_DATA *a1, WCHAR *a2)
{
  const WCHAR *v2; // r12
  int StringFromManifest; // eax
  int v6; // edi
  unsigned int LastErrorAsFailHR; // esi
  SplLogType *v8; // rdi
  SplLogType *v9; // rbx
  struct SplLogType *v10; // rax
  __int64 v11; // r10
  __int64 v12; // r11
  int v13; // eax
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rdi
  int v17; // eax
  __int64 v18; // rax
  NCoreLibrary *v19; // rcx
  SplLogType *v20; // rbx
  struct SplLogType *v21; // rax
  __int64 v22; // r10
  __int64 v23; // r11
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  unsigned int v28; // eax
  SplLogType *v29; // rbx
  struct SplLogType *v30; // rax
  __int64 v31; // r10
  __int64 v32; // r11
  wchar_t *Context; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h]
  int v37; // [rsp+58h] [rbp-A8h]
  int v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h]
  int v40; // [rsp+70h] [rbp-90h]
  _BYTE v41[24]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v42[24]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v43[24]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v44[32]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[264]; // [rsp+E0h] [rbp-20h] BYREF

  v2 = a2 + 1;
  StringFromManifest = GetStringFromManifest(L"PrinterDriverID", sz, 0x104u, a2 + 1);
  v6 = StringFromManifest;
  if ( StringFromManifest < 0 )
  {
    ClassInstallerTelemetry::WriteDbgTraceError(
      "ParseManifestDirectives",
      L"Manifest does not contain a PrinterDriverID: hr: 0x%x",
      (unsigned int)StringFromManifest);
    v37 = 1;
    v35 = L"-";
    v36 = 4;
    if ( v6 == -2147024894 )
      v6 = -2147021875;
    LastErrorAsFailHR = v6;
    v29 = SplLogType::SplLogType((SplLogType *)v44, L"PrinterDriverID");
    SplLogType::SplLogType((SplLogType *)v43, *((const unsigned __int16 **)a1 + 14));
    SplLogType::SplLogType((SplLogType *)v42, *(const unsigned __int16 **)a1);
    v30 = SplLogType::SplLogType((SplLogType *)v41, *((const unsigned __int16 **)a1 + 1));
    SplLogEvent2(&SETUP_INSTALL_PRINTER_DRIVER_MISSING_DIRECTIVE, v30, v31, v32, v29, &v35, 0);
    return LastErrorAsFailHR;
  }
  if ( IIDFromString(sz, (LPIID)((char *)a1 + 132)) < 0 )
  {
    LastErrorAsFailHR = -2147021875;
    ClassInstallerTelemetry::WriteDbgTraceError("ParseManifestDirectives", L"PrinterDriverID is not a GUID: %ws", sz);
    v8 = SplLogType::SplLogType((SplLogType *)&v35, sz);
    v9 = SplLogType::SplLogType((SplLogType *)&v38, L"PrinterDriverID");
    SplLogType::SplLogType((SplLogType *)v41, *((const unsigned __int16 **)a1 + 14));
    SplLogType::SplLogType((SplLogType *)v42, *(const unsigned __int16 **)a1);
    v10 = SplLogType::SplLogType((SplLogType *)v43, *((const unsigned __int16 **)a1 + 1));
    SplLogEvent2(&SETUP_INSTALL_PRINTER_DRIVER_GUID_REQUIRED, v10, v11, v12, v9, v8, 0);
    return LastErrorAsFailHR;
  }
  v13 = GetStringFromManifest(L"Flags", sz, 0x104u, v2);
  LastErrorAsFailHR = v13;
  if ( v13 < 0 )
  {
    if ( v13 != -2147024894 )
      return LastErrorAsFailHR;
  }
  else
  {
    Context = 0;
    v14 = wcstok_s(sz, L",", &Context);
    *((_DWORD *)a1 + 20) = 0;
    if ( v14 )
    {
      do
      {
        v15 = StripWhitespaceAndQuotes(v14);
        v16 = v15;
        if ( *v15 )
        {
          if ( (unsigned int)_o__wcsicmp(L"NotShareable", v15) )
          {
            if ( (unsigned int)_o__wcsicmp(L"SoftResetOnJobCancellation", v16) )
            {
              ClassInstallerTelemetry::WriteDbgTraceWarning("ParseManifestDirectives", L"Unhandled flag: %ws", v16);
            }
            else
            {
              *((_DWORD *)a1 + 20) |= 0x400u;
              ClassInstallerTelemetry::WriteDbgTraceInfo("ParseManifestDirectives", L"Driver requires a USB soft reset");
            }
          }
          else
          {
            *((_DWORD *)a1 + 20) |= 0x20u;
            ClassInstallerTelemetry::WriteDbgTraceInfo(
              "ParseManifestDirectives",
              L"Driver has the NotShareable flag set");
          }
        }
        v14 = wcstok_s(0, L",", &Context);
      }
      while ( v14 );
      v2 = a2 + 1;
    }
  }
  v17 = GetStringFromManifest(L"DriverFile", sz, 0x104u, v2);
  LastErrorAsFailHR = v17;
  if ( v17 < 0 )
  {
    if ( v17 != -2147024894 )
      return LastErrorAsFailHR;
LABEL_24:
    LastErrorAsFailHR = ParseRequiredClassDirective(a1, (struct _MANIFEST_CALLBACK_CONTEXT *)a2);
    if ( (LastErrorAsFailHR & 0x80000000) == 0 )
    {
      v24 = GetStringFromManifest(L"DriverCategory", sz, 0x104u, v2);
      LastErrorAsFailHR = v24;
      if ( v24 < 0 )
      {
        if ( v24 == -2147024894 )
          return 0;
      }
      else
      {
        v28 = ParseDriverCategory(sz, v25, v26, v27);
        *((_DWORD *)a1 + 37) = v28;
        ClassInstallerTelemetry::WriteDbgTraceInfo("ParseManifestDirectives", L"DriverCategory='%ws' (%d)", sz, v28);
      }
    }
    return LastErrorAsFailHR;
  }
  if ( !*((_DWORD *)a1 + 32) )
  {
    LastErrorAsFailHR = -2147021875;
    ClassInstallerTelemetry::WriteDbgTraceError(
      "ParseManifestDirectives",
      L"DriverFile was specified in the manifest, which is only allowed for class drivers.");
    v38 = 0;
    v39 = 4;
    v36 = 4;
    v40 = 0;
    LODWORD(v35) = 1;
    v37 = 0;
    v20 = SplLogType::SplLogType((SplLogType *)v43, L"DriverFile");
    SplLogType::SplLogType((SplLogType *)v42, *((const unsigned __int16 **)a1 + 14));
    SplLogType::SplLogType((SplLogType *)v41, *(const unsigned __int16 **)a1);
    v21 = SplLogType::SplLogType((SplLogType *)v44, *((const unsigned __int16 **)a1 + 1));
    SplLogEvent2(&SETUP_INSTALL_PRINTER_DRIVER_FORBIDDEN_DIRECTIVE, v21, v22, v23, v20, &v35, &v38, 0);
    return LastErrorAsFailHR;
  }
  v18 = AllocStr(sz);
  *((_QWORD *)a1 + 36) = v18;
  if ( v18 )
    ClassInstallerTelemetry::WriteDbgTraceInfo("ParseManifestDirectives", L"DriverFile='%ws'", sz);
  else
    LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v19);
  if ( (LastErrorAsFailHR & 0x80000000) == 0 )
    goto LABEL_24;
  return LastErrorAsFailHR;
}

```

## disassembly

```asm
0x180032a34  mov     [rsp-8+arg_10], rbx
0x180032a39  push    rbp
0x180032a3a  push    rsi
0x180032a3b  push    rdi
0x180032a3c  push    r12
0x180032a3e  push    r13
0x180032a40  push    r14
0x180032a42  push    r15
0x180032a44  lea     rbp, [rsp-200h]
0x180032a4c  sub     rsp, 300h
0x180032a53  mov     rax, cs:__security_cookie
0x180032a5a  xor     rax, rsp
0x180032a5d  mov     [rbp+230h+var_40], rax
0x180032a64  lea     r12, [rdx+2]
0x180032a68  mov     r13, rdx
0x180032a6b  mov     r14, rcx
0x180032a6e  lea     rdx, [rbp+230h+sz]; lpReturnedString
0x180032a72  mov     ebx, 104h
0x180032a77  lea     rcx, aPrinterdriveri_0; "PrinterDriverID"
0x180032a7e  mov     r9, r12; lpFileName
0x180032a81  mov     r8d, ebx; nSize
0x180032a84  call    ?GetStringFromManifest@@YAJPEBGPEAGK0@Z; GetStringFromManifest(ushort const *,ushort *,ulong,ushort const *)
0x180032a89  mov     edi, eax
0x180032a8b  test    eax, eax
0x180032a8d  js      loc_180032DBC
0x180032a93  lea     rdx, [r14+84h]; lpiid
0x180032a9a  lea     rcx, [rbp+230h+sz]; lpsz
0x180032a9e  call    cs:__imp_IIDFromString
0x180032aa4  xor     edi, edi
0x180032aa6  test    eax, eax
0x180032aa8  jns     loc_180032B36
0x180032aae  lea     r8, [rbp+230h+sz]
0x180032ab2  mov     esi, 80070BCDh
0x180032ab7  lea     rdx, aPrinterdriveri; "PrinterDriverID is not a GUID: %ws"
0x180032abe  lea     rcx, aParsemanifestd; "ParseManifestDirectives"
0x180032ac5  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180032aca  lea     rdx, [rbp+230h+sz]; unsigned __int16 *
0x180032ace  lea     rcx, [rsp+330h+var_2E8]; this
0x180032ad3  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032ad8  lea     rdx, aPrinterdriveri_0; "PrinterDriverID"
0x180032adf  mov     rdi, rax
0x180032ae2  lea     rcx, [rsp+330h+var_2D0]; this
0x180032ae7  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032aec  mov     rdx, [r14+70h]; unsigned __int16 *
0x180032af0  lea     rcx, [rsp+330h+var_2B8]; this
0x180032af5  mov     rbx, rax
0x180032af8  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032afd  mov     rdx, [r14]; unsigned __int16 *
0x180032b00  lea     rcx, [rbp+230h+var_2A0]; this
0x180032b04  mov     r11, rax
0x180032b07  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032b0c  mov     rdx, [r14+8]; unsigned __int16 *
0x180032b10  lea     rcx, [rbp+230h+var_288]; this
0x180032b14  mov     r10, rax
0x180032b17  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032b1c  mov     [rsp+330h+var_300], 0
0x180032b25  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_GUID_REQUIRED
0x180032b2c  mov     [rsp+330h+var_308], rdi
0x180032b31  jmp     loc_180032E5D
0x180032b36  mov     r9, r12; lpFileName
0x180032b39  lea     rdx, [rbp+230h+sz]; lpReturnedString
0x180032b3d  mov     r8d, ebx; nSize
0x180032b40  lea     rcx, aFlags; "Flags"
0x180032b47  call    ?GetStringFromManifest@@YAJPEBGPEAGK0@Z; GetStringFromManifest(ushort const *,ushort *,ulong,ushort const *)
0x180032b4c  lea     rbx, aParsemanifestd; "ParseManifestDirectives"
0x180032b53  mov     esi, eax
0x180032b55  mov     r15d, 80070002h
0x180032b5b  test    eax, eax
0x180032b5d  js      loc_180032C22
0x180032b63  lea     rsi, Delimiter; ","
0x180032b6a  mov     [rsp+330h+Context], rdi
0x180032b6f  mov     rdx, rsi; Delimiter
0x180032b72  lea     r8, [rsp+330h+Context]; Context
0x180032b77  lea     rcx, [rbp+230h+sz]; String
0x180032b7b  call    cs:__imp_wcstok_s
0x180032b81  mov     [r14+50h], edi
0x180032b85  test    rax, rax
0x180032b88  jz      loc_180032C2B
0x180032b8e  xor     r12d, r12d
0x180032b91  mov     rcx, rax; unsigned __int16 *
0x180032b94  call    ?StripWhitespaceAndQuotes@@YAPEAGPEAG@Z; StripWhitespaceAndQuotes(ushort *)
0x180032b99  mov     rdi, rax
0x180032b9c  cmp     [rax], r12w
0x180032ba0  jz      short loc_180032C01
0x180032ba2  mov     rdx, rax
0x180032ba5  lea     rcx, aNotshareable; "NotShareable"
0x180032bac  call    cs:__imp__o__wcsicmp
0x180032bb2  test    eax, eax
0x180032bb4  jnz     short loc_180032BC7
0x180032bb6  or      dword ptr [r14+50h], 20h
0x180032bbb  lea     rdx, aDriverHasTheNo; "Driver has the NotShareable flag set"
0x180032bc2  mov     rcx, rbx
0x180032bc5  jmp     short loc_180032BEB
0x180032bc7  mov     rdx, rdi
0x180032bca  lea     rcx, aSoftresetonjob; "SoftResetOnJobCancellation"
0x180032bd1  call    cs:__imp__o__wcsicmp
0x180032bd7  mov     rcx, rbx; char *
0x180032bda  test    eax, eax
0x180032bdc  jnz     short loc_180032BF2
0x180032bde  bts     dword ptr [r14+50h], 0Ah
0x180032be4  lea     rdx, aDriverRequires_0; "Driver requires a USB soft reset"
0x180032beb  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180032bf0  jmp     short loc_180032C01
0x180032bf2  mov     r8, rdi
0x180032bf5  lea     rdx, aUnhandledFlagW; "Unhandled flag: %ws"
0x180032bfc  call    ?WriteDbgTraceWarning@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180032c01  lea     r8, [rsp+330h+Context]; Context
0x180032c06  mov     rdx, rsi; Delimiter
0x180032c09  xor     ecx, ecx; String
0x180032c0b  call    cs:__imp_wcstok_s
0x180032c11  test    rax, rax
0x180032c14  jnz     loc_180032B91
0x180032c1a  lea     r12, [r13+2]
0x180032c1e  xor     edi, edi
0x180032c20  jmp     short loc_180032C2B
0x180032c22  cmp     eax, r15d
0x180032c25  jnz     loc_180032E70
0x180032c2b  mov     r9, r12; lpFileName
0x180032c2e  lea     rdx, [rbp+230h+sz]; lpReturnedString
0x180032c32  mov     r8d, 104h; nSize
0x180032c38  lea     rcx, aDriverfile; "DriverFile"
0x180032c3f  call    ?GetStringFromManifest@@YAJPEBGPEAGK0@Z; GetStringFromManifest(ushort const *,ushort *,ulong,ushort const *)
0x180032c44  mov     esi, eax
0x180032c46  test    eax, eax
0x180032c48  js      loc_180032D44
0x180032c4e  cmp     [r14+80h], edi
0x180032c55  jz      short loc_180032C95
0x180032c57  lea     rcx, [rbp+230h+sz]; unsigned __int16 *
0x180032c5b  call    AllocStr
0x180032c60  mov     [r14+120h], rax
0x180032c67  test    rax, rax
0x180032c6a  jz      short loc_180032C81
0x180032c6c  lea     r8, [rbp+230h+sz]
0x180032c70  mov     rcx, rbx; char *
0x180032c73  lea     rdx, aDriverfileWs; "DriverFile='%ws'"
0x180032c7a  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180032c7f  jmp     short loc_180032C88
0x180032c81  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180032c86  mov     esi, eax
0x180032c88  test    esi, esi
0x180032c8a  jns     loc_180032D4D
0x180032c90  jmp     loc_180032E70
0x180032c95  lea     rdx, aDriverfileWasS; "DriverFile was specified in the manifes"...
0x180032c9c  mov     rcx, rbx; char *
0x180032c9f  mov     esi, 80070BCDh
0x180032ca4  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180032ca9  mov     eax, 4
0x180032cae  mov     [rsp+330h+var_2D0], edi
0x180032cb2  lea     rdx, aDriverfile; "DriverFile"
0x180032cb9  mov     [rsp+330h+var_2C8], rax
0x180032cbe  lea     rcx, [rbp+230h+var_288]; this
0x180032cc2  mov     [rsp+330h+var_2E0], rax
0x180032cc7  mov     [rsp+330h+var_2C0], edi
0x180032ccb  mov     dword ptr [rsp+330h+var_2E8], 1
0x180032cd3  mov     [rsp+330h+var_2D8], edi
0x180032cd7  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032cdc  mov     rdx, [r14+70h]; unsigned __int16 *
0x180032ce0  lea     rcx, [rbp+230h+var_2A0]; this
0x180032ce4  mov     rbx, rax
0x180032ce7  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032cec  mov     rdx, [r14]; unsigned __int16 *
0x180032cef  lea     rcx, [rsp+330h+var_2B8]; this
0x180032cf4  mov     r11, rax
0x180032cf7  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032cfc  mov     rdx, [r14+8]; unsigned __int16 *
0x180032d00  lea     rcx, [rbp+230h+var_270]; this
0x180032d04  mov     r10, rax
0x180032d07  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032d0c  mov     [rsp+330h+var_2F8], rdi
0x180032d11  lea     rcx, [rsp+330h+var_2D0]
0x180032d16  mov     [rsp+330h+var_300], rcx
0x180032d1b  mov     r9, r11
0x180032d1e  lea     rcx, [rsp+330h+var_2E8]
0x180032d23  mov     r8, r10
0x180032d26  mov     [rsp+330h+var_308], rcx
0x180032d2b  mov     rdx, rax; struct SplLogType *
0x180032d2e  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FORBIDDEN_DIRECTIVE; struct _EVENT_DESCRIPTOR *
0x180032d35  mov     [rsp+330h+var_310], rbx
0x180032d3a  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x180032d3f  jmp     loc_180032E70
0x180032d44  cmp     eax, r15d
0x180032d47  jnz     loc_180032E70
0x180032d4d  mov     rdx, r13; struct _MANIFEST_CALLBACK_CONTEXT *
0x180032d50  mov     rcx, r14; struct _PSETUP_LOCAL_DATA *
0x180032d53  call    ?ParseRequiredClassDirective@@YAJPEAU_PSETUP_LOCAL_DATA@@PEAU_MANIFEST_CALLBACK_CONTEXT@@@Z; ParseRequiredClassDirective(_PSETUP_LOCAL_DATA *,_MANIFEST_CALLBACK_CONTEXT *)
0x180032d58  mov     esi, eax
0x180032d5a  test    eax, eax
0x180032d5c  js      loc_180032E70
0x180032d62  mov     r9, r12; lpFileName
0x180032d65  lea     rdx, [rbp+230h+sz]; lpReturnedString
0x180032d69  mov     r8d, 104h; nSize
0x180032d6f  lea     rcx, aDrivercategory_1; "DriverCategory"
0x180032d76  call    ?GetStringFromManifest@@YAJPEBGPEAGK0@Z; GetStringFromManifest(ushort const *,ushort *,ulong,ushort const *)
0x180032d7b  mov     esi, eax
0x180032d7d  test    eax, eax
0x180032d7f  js      short loc_180032DAC
0x180032d81  lea     rcx, [rbp+230h+sz]
0x180032d85  call    ParseDriverCategory
0x180032d8a  mov     r9d, eax
0x180032d8d  mov     [r14+94h], eax
0x180032d94  lea     r8, [rbp+230h+sz]
0x180032d98  mov     rcx, rbx; char *
0x180032d9b  lea     rdx, aDrivercategory; "DriverCategory='%ws' (%d)"
0x180032da2  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180032da7  jmp     loc_180032E70
0x180032dac  cmp     eax, r15d
0x180032daf  jnz     loc_180032E70
0x180032db5  mov     esi, edi
0x180032db7  jmp     loc_180032E70
0x180032dbc  mov     r8d, edi
0x180032dbf  lea     rdx, aManifestDoesNo; "Manifest does not contain a PrinterDriv"...
0x180032dc6  lea     rcx, aParsemanifestd; "ParseManifestDirectives"
0x180032dcd  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180032dd2  lea     rax, asc_180041954; "-"
0x180032dd9  mov     [rsp+330h+var_2D8], 1
0x180032de1  mov     esi, 80070BCDh
0x180032de6  mov     [rsp+330h+var_2E8], rax
0x180032deb  mov     eax, 4
0x180032df0  lea     rdx, aPrinterdriveri_0; "PrinterDriverID"
0x180032df7  mov     r15d, 80070002h
0x180032dfd  mov     [rsp+330h+var_2E0], rax
0x180032e02  cmp     edi, r15d
0x180032e05  lea     rcx, [rbp+230h+var_270]; this
0x180032e09  cmovz   edi, esi
0x180032e0c  mov     esi, edi
0x180032e0e  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032e13  mov     rdx, [r14+70h]; unsigned __int16 *
0x180032e17  lea     rcx, [rbp+230h+var_288]; this
0x180032e1b  mov     rbx, rax
0x180032e1e  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032e23  mov     rdx, [r14]; unsigned __int16 *
0x180032e26  lea     rcx, [rbp+230h+var_2A0]; this
0x180032e2a  mov     r11, rax
0x180032e2d  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032e32  mov     rdx, [r14+8]; unsigned __int16 *
0x180032e36  lea     rcx, [rsp+330h+var_2B8]; this
0x180032e3b  mov     r10, rax
0x180032e3e  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032e43  lea     rcx, [rsp+330h+var_2E8]
0x180032e48  mov     [rsp+330h+var_300], 0
0x180032e51  mov     [rsp+330h+var_308], rcx
0x180032e56  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_MISSING_DIRECTIVE; struct _EVENT_DESCRIPTOR *
0x180032e5d  mov     r9, r11
0x180032e60  mov     [rsp+330h+var_310], rbx
0x180032e65  mov     r8, r10
0x180032e68  mov     rdx, rax; struct SplLogType *
0x180032e6b  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x180032e70  mov     eax, esi
0x180032e72  mov     rcx, [rbp+230h+var_40]
0x180032e79  xor     rcx, rsp; StackCookie
0x180032e7c  call    __security_check_cookie
0x180032e81  mov     rbx, [rsp+330h+arg_10]
0x180032e89  add     rsp, 300h
0x180032e90  pop     r15
0x180032e92  pop     r14
0x180032e94  pop     r13
0x180032e96  pop     r12
0x180032e98  pop     rdi
0x180032e99  pop     rsi
0x180032e9a  pop     rbp
0x180032e9b  retn
```
