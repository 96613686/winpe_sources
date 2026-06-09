# ParseAppSection(_FILELIST_CALLBACK_CONTEXT *,ushort const *)

- ea: `0x1800324ac`
- end: `0x180032a2c`
- name: `?ParseAppSection@@YAJPEAU_FILELIST_CALLBACK_CONTEXT@@PEBG@Z`
- size: `1408`
- prototype: `int(struct _FILELIST_CALLBACK_CONTEXT *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180033398`

## callees

- `0x180002300`
- `0x1800026f0`
- `0x1800029b0`
- `0x18000b200`
- `0x18000d57c`
- `0x1800162c8`
- `0x180017810`
- `0x180031378`
- `0x1800324ac`
- `0x180033d54`
- `0x180033e28`
- `0x180034a60`
- `0x180035ac4`
- `0x180035ae0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180032761`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003277e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180032761`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003277e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180032679`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800327da`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180032679`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800327da`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18003257d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180032592`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18003257d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180032592`
- `KERNEL32!GetPrivateProfileSectionW` at `0x18003252d`
- `KERNEL32!GetPrivateProfileSectionW` at `0x18003252d`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800326da`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18003279d`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800326da`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18003279d`

## string_xrefs

- `0x1800325a4`: `Empty token found in printer extension directive: '%ws'`
- `0x1800325bc`: `PrinterExtension`
- `0x180032810`: `PrinterExtension`
- `0x18003292d`: `PrinterExtension`
- `0x180032909`: `Empty token found in printer extension directive`
- `0x180032892`: `PrinterExtensionID`
- `0x1800327f8`: `Invalid printer extension directive: '%ws'`
- `0x180032523`: `PrinterExtensions`

## pseudocode

```c
__int64 __fastcall ParseAppSection(struct _FILELIST_CALLBACK_CONTEXT *a1, const unsigned __int16 *a2)
{
  const unsigned __int16 **v2; // r12
  const unsigned __int16 *v4; // r13
  WCHAR *v5; // r14
  DWORD PrivateProfileSectionW; // eax
  NCoreLibrary *v7; // rcx
  int LastErrorAsFailHR; // esi
  __int64 v9; // r15
  SplLogType *v10; // rbx
  struct SplLogType *v11; // rax
  __int64 v12; // r10
  __int64 v13; // r11
  char v14; // r12
  int v15; // edi
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rbx
  TAppRegistration *v18; // rax
  TAppRegistration *v19; // rcx
  struct NCoreLibrary::TLink *v20; // rcx
  GUID v21; // xmm0
  SplLogType *v22; // rbx
  SplLogType *v23; // rdi
  SplLogType *v24; // rbx
  struct SplLogType *v25; // rax
  __int64 v26; // r10
  __int64 v27; // r11
  struct SplLogType *v28; // rax
  __int64 v29; // r10
  __int64 v30; // r11
  const unsigned __int16 **v32; // [rsp+40h] [rbp-C0h]
  WCHAR *v33; // [rsp+48h] [rbp-B8h] BYREF
  int v34; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+58h] [rbp-A8h]
  int v36; // [rsp+60h] [rbp-A0h]
  int v37; // [rsp+68h] [rbp-98h] BYREF
  __int64 v38; // [rsp+70h] [rbp-90h]
  int v39; // [rsp+78h] [rbp-88h]
  wchar_t *Context; // [rsp+80h] [rbp-80h] BYREF
  struct _FILELIST_CALLBACK_CONTEXT *v41; // [rsp+88h] [rbp-78h]
  _BYTE v42[24]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v43[24]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v44[24]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v45[24]; // [rsp+D8h] [rbp-28h] BYREF
  GUID v46; // [rsp+F0h] [rbp-10h] BYREF
  GUID iid; // [rsp+100h] [rbp+0h] BYREF

  v2 = (const unsigned __int16 **)*((_QWORD *)a1 + 12);
  v41 = a1;
  v32 = v2;
  v4 = 0;
  v33 = 0;
  v5 = (WCHAR *)operator new[](0x2000u, (const struct std::nothrow_t *)&NCoreLibrary::nothrow);
  NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&v33);
  if ( v5 )
  {
    v33 = v5;
    PrivateProfileSectionW = GetPrivateProfileSectionW(L"PrinterExtensions", v5, 0x1000u, a2);
    if ( PrivateProfileSectionW )
    {
      LastErrorAsFailHR = -2147021875;
      if ( PrivateProfileSectionW != 4094 )
        LastErrorAsFailHR = 0;
    }
    else
    {
      LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v7);
    }
    while ( LastErrorAsFailHR >= 0 && *v5 )
    {
      v9 = -1;
      do
        ++v9;
      while ( v5[v9] );
      if ( wcsstr(v5, L",,") || wcsstr(v5, L"==") )
      {
        LastErrorAsFailHR = -2147021875;
        ClassInstallerTelemetry::WriteDbgTraceError(
          "ParseAppSection",
          L"Empty token found in printer extension directive: '%ws'",
          v5);
        v37 = 0;
        v38 = 4;
        v39 = 0;
        v34 = 1;
        v35 = 4;
        v36 = 0;
        v10 = SplLogType::SplLogType((SplLogType *)v42, L"PrinterExtension");
        SplLogType::SplLogType((SplLogType *)v43, v2[14]);
        SplLogType::SplLogType((SplLogType *)v44, *v2);
        v11 = SplLogType::SplLogType((SplLogType *)v45, v2[1]);
        SplLogEvent2(&SETUP_INSTALL_PRINTER_DRIVER_MALFORMED_DIRECTIVE, v11, v12, v13, v10, &v34, &v37, 0);
      }
      Context = 0;
      v14 = 1;
      v46 = 0;
      v15 = 0;
      v16 = wcstok_s(v5, L"=", &Context);
      if ( v16 )
      {
        while ( 1 )
        {
          if ( LastErrorAsFailHR < 0 )
          {
            v4 = 0;
LABEL_47:
            v2 = v32;
            goto LABEL_48;
          }
          if ( !++v15 )
            goto LABEL_38;
          v17 = StripWhitespaceAndQuotes(v16);
          if ( !*v17 )
          {
            LastErrorAsFailHR = -2147021875;
            ClassInstallerTelemetry::WriteDbgTraceError(
              "ParseAppSection",
              L"Empty token found in printer extension directive");
            v4 = 0;
            v35 = 4;
            v34 = 0;
            v36 = 0;
            v39 = 0;
            v37 = 1;
            v38 = 4;
            v2 = v32;
            v22 = SplLogType::SplLogType((SplLogType *)v45, L"PrinterExtension");
            SplLogType::SplLogType((SplLogType *)v44, v32[14]);
            goto LABEL_43;
          }
          switch ( v15 )
          {
            case 1:
              if ( (unsigned int)_o__wcsicmp(v17, L"DriverEvent") )
              {
                if ( (unsigned int)_o__wcsicmp(v17, L"PrintPreferences") )
                {
                  if ( IIDFromString(v17, &v46) < 0 )
                  {
                    v14 = 0;
                    ClassInstallerTelemetry::WriteDbgTraceWarning(
                      "ParseAppSection",
                      L"Unknown app activation contract found: '%ws'",
                      v17);
                  }
                  break;
                }
                v21 = (GUID)PRINTER_EXTENSION_REASON_PRINT_PREFERENCES;
              }
              else
              {
                v21 = (GUID)PRINTER_EXTENSION_REASON_DRIVER_EVENT;
              }
              v46 = v21;
              break;
            case 2:
              if ( v14 )
                v4 = v17;
              break;
            case 3:
              iid = 0;
              if ( IIDFromString(v17, &iid) < 0 )
              {
                LastErrorAsFailHR = -2147021875;
                ClassInstallerTelemetry::WriteDbgTraceError("ParseAppSection", L"AppID is not a GUID: %ws", v17);
                v23 = SplLogType::SplLogType((SplLogType *)v45, v17);
                v2 = v32;
                v24 = SplLogType::SplLogType((SplLogType *)v44, L"PrinterExtensionID");
                SplLogType::SplLogType((SplLogType *)v43, v32[14]);
                SplLogType::SplLogType((SplLogType *)v42, *v32);
                v25 = SplLogType::SplLogType((SplLogType *)&v34, v32[1]);
                v4 = 0;
                SplLogEvent2(&SETUP_INSTALL_PRINTER_DRIVER_GUID_REQUIRED, v25, v26, v27, v24, v23, 0);
                goto LABEL_48;
              }
              if ( v14 )
              {
                v18 = (TAppRegistration *)operator new(0x58u, (const struct std::nothrow_t *)&NCoreLibrary::nothrow);
                v19 = 0;
                if ( v18 )
                  v19 = TAppRegistration::TAppRegistration(v18, &v46, &iid, v4);
                LastErrorAsFailHR = *((_DWORD *)v19 + 20);
                if ( LastErrorAsFailHR < 0 )
                  goto LABEL_44;
                LastErrorAsFailHR = NCoreLibrary::TLink::IsValid(v19);
                if ( LastErrorAsFailHR >= 0 )
                  LastErrorAsFailHR = NCoreLibrary::TLink::Link(*((NCoreLibrary::TLink **)v41 + 4), v20);
              }
              break;
          }
          if ( LastErrorAsFailHR < 0 )
            break;
          if ( v15 < 3 )
          {
            v16 = wcstok_s(0, L",", &Context);
            if ( v16 )
              continue;
          }
LABEL_38:
          v4 = 0;
          goto LABEL_39;
        }
      }
LABEL_44:
      v4 = 0;
      if ( LastErrorAsFailHR < 0 )
        goto LABEL_47;
LABEL_39:
      if ( v15 >= 3 )
        goto LABEL_47;
      LastErrorAsFailHR = -2147021875;
      ClassInstallerTelemetry::WriteDbgTraceError("ParseAppSection", L"Invalid printer extension directive: '%ws'", v5);
      v34 = 1;
      v35 = 4;
      v36 = 0;
      v37 = 0;
      v38 = 4;
      v39 = 0;
      v22 = SplLogType::SplLogType((SplLogType *)v45, L"PrinterExtension");
      SplLogType::SplLogType((SplLogType *)v44, *(const unsigned __int16 **)(*((_QWORD *)v41 + 12) + 112LL));
      v2 = v32;
LABEL_43:
      SplLogType::SplLogType((SplLogType *)v43, *v2);
      v28 = SplLogType::SplLogType((SplLogType *)v42, v2[1]);
      SplLogEvent2(&SETUP_INSTALL_PRINTER_DRIVER_MALFORMED_DIRECTIVE, v28, v29, v30, v22, &v37, &v34, 0);
LABEL_48:
      v5 += v9 + 1;
    }
  }
  else
  {
    v33 = 0;
    LastErrorAsFailHR = -2147024882;
  }
  NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&v33);
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x1800324ac  mov     [rsp-8+arg_10], rbx
0x1800324b1  push    rbp
0x1800324b2  push    rsi
0x1800324b3  push    rdi
0x1800324b4  push    r12
0x1800324b6  push    r13
0x1800324b8  push    r14
0x1800324ba  push    r15
0x1800324bc  lea     rbp, [rsp-20h]
0x1800324c1  sub     rsp, 120h
0x1800324c8  mov     rax, cs:__security_cookie
0x1800324cf  xor     rax, rsp
0x1800324d2  mov     [rbp+50h+var_40], rax
0x1800324d6  mov     r12, [rcx+60h]
0x1800324da  mov     rbx, rdx
0x1800324dd  mov     [rbp+50h+var_C8], rcx
0x1800324e1  lea     rdx, ?nothrow@NCoreLibrary@@3Unothrow_t@std@@B; struct std::nothrow_t *
0x1800324e8  mov     ecx, 2000h; unsigned __int64
0x1800324ed  mov     [rsp+150h+var_110], r12
0x1800324f2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800324f7  xor     r13d, r13d
0x1800324fa  lea     rcx, [rsp+150h+var_108]
0x1800324ff  mov     [rsp+150h+var_108], r13
0x180032504  mov     r14, rax
0x180032507  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x18003250c  test    r14, r14
0x18003250f  jz      loc_1800329EF
0x180032515  mov     r9, rbx; lpFileName
0x180032518  mov     [rsp+150h+var_108], r14
0x18003251d  mov     r8d, 1000h; nSize
0x180032523  lea     rcx, aPrinterextensi_1; "PrinterExtensions"
0x18003252a  mov     rdx, r14; lpReturnedString
0x18003252d  call    cs:__imp_GetPrivateProfileSectionW
0x180032533  test    eax, eax
0x180032535  jnz     short loc_180032543
0x180032537  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18003253c  mov     esi, eax
0x18003253e  jmp     loc_1800329E5
0x180032543  mov     esi, 80070BCDh
0x180032548  cmp     eax, 0FFEh
0x18003254d  jz      loc_1800329E5
0x180032553  mov     esi, r13d
0x180032556  jmp     loc_1800329E5
0x18003255b  cmp     [r14], r13w
0x18003255f  jz      loc_1800329F9
0x180032565  or      r15, 0FFFFFFFFFFFFFFFFh
0x180032569  inc     r15
0x18003256c  cmp     [r14+r15*2], r13w
0x180032571  jnz     short loc_180032569
0x180032573  lea     rdx, asc_18004B7AC; ",,"
0x18003257a  mov     rcx, r14; Str
0x18003257d  call    cs:__imp_wcsstr
0x180032583  test    rax, rax
0x180032586  jnz     short loc_1800325A1
0x180032588  lea     rdx, asc_18004B854; "=="
0x18003258f  mov     rcx, r14; Str
0x180032592  call    cs:__imp_wcsstr
0x180032598  test    rax, rax
0x18003259b  jz      loc_18003265A
0x1800325a1  mov     r8, r14
0x1800325a4  lea     rdx, aEmptyTokenFoun_1; "Empty token found in printer extension "...
0x1800325ab  lea     rcx, aParseappsectio; "ParseAppSection"
0x1800325b2  mov     esi, 80070BCDh
0x1800325b7  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800325bc  lea     rdx, aPrinterextensi; "PrinterExtension"
0x1800325c3  mov     [rsp+150h+var_E8], r13d
0x1800325c8  lea     rcx, [rbp+50h+var_C0]; this
0x1800325cc  mov     [rsp+150h+var_E0], 4
0x1800325d5  mov     [rsp+150h+var_D8], r13d
0x1800325da  mov     [rsp+150h+var_100], 1
0x1800325e2  mov     [rsp+150h+var_F8], 4
0x1800325eb  mov     [rsp+150h+var_F0], r13d
0x1800325f0  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x1800325f5  mov     rdx, [r12+70h]; unsigned __int16 *
0x1800325fa  lea     rcx, [rbp+50h+var_A8]; this
0x1800325fe  mov     rbx, rax
0x180032601  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032606  mov     rdx, [r12]; unsigned __int16 *
0x18003260a  lea     rcx, [rbp+50h+var_90]; this
0x18003260e  mov     r11, rax
0x180032611  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032616  mov     rdx, [r12+8]; unsigned __int16 *
0x18003261b  lea     rcx, [rbp+50h+var_78]; this
0x18003261f  mov     r10, rax
0x180032622  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032627  mov     [rsp+150h+var_118], r13
0x18003262c  lea     rcx, [rsp+150h+var_E8]
0x180032631  mov     [rsp+150h+var_120], rcx
0x180032636  mov     r9, r11
0x180032639  lea     rcx, [rsp+150h+var_100]
0x18003263e  mov     r8, r10
0x180032641  mov     [rsp+150h+var_128], rcx
0x180032646  mov     rdx, rax; struct SplLogType *
0x180032649  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_MALFORMED_DIRECTIVE; struct _EVENT_DESCRIPTOR *
0x180032650  mov     [rsp+150h+var_130], rbx
0x180032655  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x18003265a  xorps   xmm0, xmm0
0x18003265d  mov     [rbp+50h+Context], r13
0x180032661  lea     r8, [rbp+50h+Context]; Context
0x180032665  mov     rcx, r14; String
0x180032668  lea     rdx, asc_18004B910; "="
0x18003266f  mov     r12b, 1
0x180032672  movups  xmmword ptr [rbp+50h+var_60.Data1], xmm0
0x180032676  mov     edi, r13d
0x180032679  call    cs:__imp_wcstok_s
0x18003267f  test    rax, rax
0x180032682  jz      loc_1800329C9
0x180032688  test    esi, esi
0x18003268a  js      loc_1800329D5
0x180032690  add     edi, 1
0x180032693  jz      loc_1800327E9
0x180032699  mov     rcx, rax; unsigned __int16 *
0x18003269c  call    ?StripWhitespaceAndQuotes@@YAPEAGPEAG@Z; StripWhitespaceAndQuotes(ushort *)
0x1800326a1  mov     rbx, rax
0x1800326a4  xor     eax, eax
0x1800326a6  cmp     [rbx], ax
0x1800326a9  jz      loc_180032909
0x1800326af  mov     eax, edi
0x1800326b1  sub     eax, 1
0x1800326b4  jz      loc_180032757
0x1800326ba  sub     eax, 1
0x1800326bd  jz      loc_18003274D
0x1800326c3  cmp     eax, 1
0x1800326c6  jnz     loc_1800327C0
0x1800326cc  xorps   xmm0, xmm0
0x1800326cf  lea     rdx, [rbp+50h+iid]; lpiid
0x1800326d3  mov     rcx, rbx; lpsz
0x1800326d6  movups  xmmword ptr [rbp+50h+iid.Data1], xmm0
0x1800326da  call    cs:__imp_IIDFromString
0x1800326e0  test    eax, eax
0x1800326e2  js      loc_18003286B
0x1800326e8  test    r12b, r12b
0x1800326eb  jz      loc_1800327C0
0x1800326f1  lea     rdx, ?nothrow@NCoreLibrary@@3Unothrow_t@std@@B; struct std::nothrow_t *
0x1800326f8  mov     ecx, 58h ; 'X'; unsigned __int64
0x1800326fd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180032702  xor     ecx, ecx
0x180032704  test    rax, rax
0x180032707  jz      short loc_18003271F
0x180032709  mov     r9, r13; unsigned __int16 *
0x18003270c  lea     r8, [rbp+50h+iid]; struct _GUID *
0x180032710  lea     rdx, [rbp+50h+var_60]; struct _GUID *
0x180032714  mov     rcx, rax; this
0x180032717  call    ??0TAppRegistration@@QEAA@PEAU_GUID@@0PEBG@Z; TAppRegistration::TAppRegistration(_GUID *,_GUID *,ushort const *)
0x18003271c  mov     rcx, rax; this
0x18003271f  mov     esi, [rcx+50h]
0x180032722  test    esi, esi
0x180032724  js      loc_1800329C9
0x18003272a  call    ?IsValid@TLink@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TLink::IsValid(void)
0x18003272f  mov     esi, eax
0x180032731  test    eax, eax
0x180032733  js      loc_1800327C0
0x180032739  mov     rax, [rbp+50h+var_C8]
0x18003273d  mov     rdx, rcx; struct NCoreLibrary::TLink *
0x180032740  mov     rcx, [rax+20h]; this
0x180032744  call    ?Link@TLink@NCoreLibrary@@QEAAJPEAV12@@Z; NCoreLibrary::TLink::Link(NCoreLibrary::TLink *)
0x180032749  mov     esi, eax
0x18003274b  jmp     short loc_1800327C0
0x18003274d  test    r12b, r12b
0x180032750  jz      short loc_1800327C0
0x180032752  mov     r13, rbx
0x180032755  jmp     short loc_1800327C0
0x180032757  lea     rdx, aDriverevent; "DriverEvent"
0x18003275e  mov     rcx, rbx
0x180032761  call    cs:__imp__o__wcsicmp
0x180032767  test    eax, eax
0x180032769  jnz     short loc_180032774
0x18003276b  movups  xmm0, cs:PRINTER_EXTENSION_REASON_DRIVER_EVENT
0x180032772  jmp     short loc_18003278F
0x180032774  lea     rdx, aPrintpreferenc; "PrintPreferences"
0x18003277b  mov     rcx, rbx
0x18003277e  call    cs:__imp__o__wcsicmp
0x180032784  test    eax, eax
0x180032786  jnz     short loc_180032796
0x180032788  movups  xmm0, cs:PRINTER_EXTENSION_REASON_PRINT_PREFERENCES
0x18003278f  movdqu  xmmword ptr [rbp+50h+var_60.Data1], xmm0
0x180032794  jmp     short loc_1800327C0
0x180032796  lea     rdx, [rbp+50h+var_60]; lpiid
0x18003279a  mov     rcx, rbx; lpsz
0x18003279d  call    cs:__imp_IIDFromString
0x1800327a3  test    eax, eax
0x1800327a5  jns     short loc_1800327C0
0x1800327a7  xor     r12b, r12b
0x1800327aa  lea     rdx, aUnknownAppActi; "Unknown app activation contract found: "...
0x1800327b1  mov     r8, rbx
0x1800327b4  lea     rcx, aParseappsectio; "ParseAppSection"
0x1800327bb  call    ?WriteDbgTraceWarning@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800327c0  test    esi, esi
0x1800327c2  js      loc_1800329C9
0x1800327c8  cmp     edi, 3
0x1800327cb  jge     short loc_1800327E9
0x1800327cd  lea     r8, [rbp+50h+Context]; Context
0x1800327d1  xor     ecx, ecx; String
0x1800327d3  lea     rdx, Delimiter; ","
0x1800327da  call    cs:__imp_wcstok_s
0x1800327e0  test    rax, rax
0x1800327e3  jnz     loc_180032688
0x1800327e9  xor     r13d, r13d
0x1800327ec  cmp     edi, 3
0x1800327ef  jge     loc_1800329D8
0x1800327f5  mov     r8, r14
0x1800327f8  lea     rdx, aInvalidPrinter; "Invalid printer extension directive: '%"...
0x1800327ff  lea     rcx, aParseappsectio; "ParseAppSection"
0x180032806  mov     esi, 80070BCDh
0x18003280b  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180032810  lea     rdx, aPrinterextensi; "PrinterExtension"
0x180032817  mov     [rsp+150h+var_100], 1
0x18003281f  lea     rcx, [rbp+50h+var_78]; this
0x180032823  mov     [rsp+150h+var_F8], 4
0x18003282c  mov     [rsp+150h+var_F0], r13d
0x180032831  mov     [rsp+150h+var_E8], r13d
0x180032836  mov     [rsp+150h+var_E0], 4
0x18003283f  mov     [rsp+150h+var_D8], r13d
0x180032844  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032849  mov     rbx, rax
0x18003284c  lea     rcx, [rbp+50h+var_90]; this
0x180032850  mov     rax, [rbp+50h+var_C8]
0x180032854  mov     rdx, [rax+60h]
0x180032858  mov     rdx, [rdx+70h]; unsigned __int16 *
0x18003285c  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032861  mov     r12, [rsp+150h+var_110]
0x180032866  jmp     loc_180032973
0x18003286b  mov     r8, rbx
0x18003286e  lea     rdx, aAppidIsNotAGui; "AppID is not a GUID: %ws"
0x180032875  lea     rcx, aParseappsectio; "ParseAppSection"
0x18003287c  mov     esi, 80070BCDh
0x180032881  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180032886  mov     rdx, rbx; unsigned __int16 *
0x180032889  lea     rcx, [rbp+50h+var_78]; this
0x18003288d  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032892  lea     rdx, aPrinterextensi_0; "PrinterExtensionID"
0x180032899  mov     rdi, rax
0x18003289c  lea     rcx, [rbp+50h+var_90]; this
0x1800328a0  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x1800328a5  mov     r12, [rsp+150h+var_110]
0x1800328aa  lea     rcx, [rbp+50h+var_A8]; this
0x1800328ae  mov     rbx, rax
0x1800328b1  mov     rdx, [r12+70h]; unsigned __int16 *
0x1800328b6  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x1800328bb  mov     rdx, [r12]; unsigned __int16 *
0x1800328bf  lea     rcx, [rbp+50h+var_C0]; this
0x1800328c3  mov     r11, rax
0x1800328c6  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x1800328cb  mov     rdx, [r12+8]; unsigned __int16 *
0x1800328d0  lea     rcx, [rsp+150h+var_100]; this
0x1800328d5  mov     r10, rax
0x1800328d8  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x1800328dd  xor     r13d, r13d
0x1800328e0  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_GUID_REQUIRED; struct _EVENT_DESCRIPTOR *
0x1800328e7  mov     [rsp+150h+var_120], r13
0x1800328ec  mov     r9, r11
0x1800328ef  mov     [rsp+150h+var_128], rdi
0x1800328f4  mov     r8, r10
0x1800328f7  mov     rdx, rax; struct SplLogType *
0x1800328fa  mov     [rsp+150h+var_130], rbx
0x1800328ff  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x180032904  jmp     loc_1800329DD
0x180032909  lea     rdx, aEmptyTokenFoun_0; "Empty token found in printer extension "...
0x180032910  mov     esi, 80070BCDh
0x180032915  lea     rcx, aParseappsectio; "ParseAppSection"
0x18003291c  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180032921  xor     r13d, r13d
0x180032924  mov     [rsp+150h+var_F8], 4
0x18003292d  lea     rdx, aPrinterextensi; "PrinterExtension"
0x180032934  mov     [rsp+150h+var_100], r13d
0x180032939  lea     rcx, [rbp+50h+var_78]; this
0x18003293d  mov     [rsp+150h+var_F0], r13d
0x180032942  mov     [rsp+150h+var_D8], r13d
0x180032947  mov     [rsp+150h+var_E8], 1
0x18003294f  mov     [rsp+150h+var_E0], 4
0x180032958  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18003295d  mov     r12, [rsp+150h+var_110]
0x180032962  lea     rcx, [rbp+50h+var_90]; this
0x180032966  mov     rbx, rax
0x180032969  mov     rdx, [r12+70h]; unsigned __int16 *
0x18003296e  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032973  mov     rdx, [r12]; unsigned __int16 *
0x180032977  lea     rcx, [rbp+50h+var_A8]; this
0x18003297b  mov     r11, rax
0x18003297e  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032983  mov     rdx, [r12+8]; unsigned __int16 *
0x180032988  lea     rcx, [rbp+50h+var_C0]; this
0x18003298c  mov     r10, rax
0x18003298f  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032994  mov     [rsp+150h+var_118], r13
0x180032999  lea     rcx, [rsp+150h+var_100]
0x18003299e  mov     [rsp+150h+var_120], rcx
0x1800329a3  mov     r9, r11
0x1800329a6  lea     rcx, [rsp+150h+var_E8]
0x1800329ab  mov     r8, r10
0x1800329ae  mov     [rsp+150h+var_128], rcx
0x1800329b3  mov     rdx, rax; struct SplLogType *
0x1800329b6  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_MALFORMED_DIRECTIVE; struct _EVENT_DESCRIPTOR *
0x1800329bd  mov     [rsp+150h+var_130], rbx
0x1800329c2  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x1800329c7  jmp     short loc_1800329DD
0x1800329c9  xor     r13d, r13d
0x1800329cc  test    esi, esi
0x1800329ce  js      short loc_1800329D8
0x1800329d0  jmp     loc_1800327EC
  ... truncated ...
```
