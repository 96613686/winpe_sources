# ParseRequiredClassDirective(_PSETUP_LOCAL_DATA *,_MANIFEST_CALLBACK_CONTEXT *)

- ea: `0x180032ea4`
- end: `0x180033255`
- name: `?ParseRequiredClassDirective@@YAJPEAU_PSETUP_LOCAL_DATA@@PEAU_MANIFEST_CALLBACK_CONTEXT@@@Z`
- size: `945`
- prototype: `__int64 __fastcall(struct _PSETUP_LOCAL_DATA *, struct _MANIFEST_CALLBACK_CONTEXT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x180032a34`

## callees

- `0x180002300`
- `0x18000b200`
- `0x18000d57c`
- `0x18000d624`
- `0x180017810`
- `0x18001bc44`
- `0x180032210`
- `0x180032ea4`
- `0x180033e28`
- `0x180034a60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180033084`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180033124`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180033084`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180033124`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180032fc2`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180032fc2`

## string_xrefs

- `0x180032f10`: `RequiredClass was specified in the manifest, which is not allowed for class drivers.`
- `0x180032fd1`: `Empty token found in RequiredClass directive`
- `0x18003313b`: `Empty token found in RequiredClass directive`
- `0x1800331f4`: `Too many tokens found in RequiredClass directive`

## pseudocode

```c
__int64 __fastcall ParseRequiredClassDirective(const unsigned __int16 **a1, const WCHAR *a2)
{
  int StringFromManifest; // edi
  SplLogType *v4; // rbx
  struct SplLogType *v5; // rax
  __int64 v6; // r10
  __int64 v7; // r11
  const unsigned __int16 *v8; // rdx
  __int64 v9; // r10
  struct SplLogType *v10; // rax
  __int64 v11; // r10
  __int64 v12; // r11
  const wchar_t **v13; // r9
  const wchar_t **v14; // rcx
  unsigned __int16 *v15; // rbx
  int v16; // esi
  unsigned __int16 *v17; // rax
  __int64 v18; // rax
  NCoreLibrary *v19; // rcx
  __int64 v20; // rax
  const unsigned __int16 *v21; // rdx
  __int64 v22; // r10
  const wchar_t **v24; // [rsp+30h] [rbp-D0h]
  const wchar_t *v25; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h]
  __int64 v30; // [rsp+68h] [rbp-98h]
  const wchar_t *v31; // [rsp+70h] [rbp-90h] BYREF
  __int64 v32; // [rsp+78h] [rbp-88h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  wchar_t *Context; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v35[24]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v36[24]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v37[32]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t Str[264]; // [rsp+E0h] [rbp-20h] BYREF

  StringFromManifest = GetStringFromManifest(L"RequiredClass", Str, 0x104u, a2 + 1);
  if ( StringFromManifest < 0 )
  {
    if ( StringFromManifest == -2147024894 )
      return 0;
    return (unsigned int)StringFromManifest;
  }
  if ( *((_DWORD *)a1 + 32) )
  {
    StringFromManifest = -2147021875;
    ClassInstallerTelemetry::WriteDbgTraceError(
      "ParseRequiredClassDirective",
      L"RequiredClass was specified in the manifest, which is not allowed for class drivers.");
    LODWORD(v25) = 1;
    v26 = 4;
    v29 = 4;
    LODWORD(v27) = 0;
    LODWORD(v28) = 0;
    LODWORD(v30) = 0;
    v4 = SplLogType::SplLogType((SplLogType *)&v31, L"RequiredClass");
    SplLogType::SplLogType((SplLogType *)v35, a1[14]);
    SplLogType::SplLogType((SplLogType *)v36, *a1);
    v5 = SplLogType::SplLogType((SplLogType *)v37, a1[1]);
    SplLogEvent2(
      &SETUP_INSTALL_PRINTER_DRIVER_FORBIDDEN_DIRECTIVE,
      v5,
      v6,
      v7,
      v4,
      &v28,
      &v25,
      0,
      v25,
      4,
      v27,
      v28,
      4,
      v30,
      v31,
      v32,
      v33);
    return (unsigned int)StringFromManifest;
  }
  if ( !wcsstr(Str, L",,") )
  {
    Context = 0;
    v15 = wcstok_s(Str, L",", &Context);
    v16 = 0;
    if ( !v15 )
      return (unsigned int)StringFromManifest;
    while ( 1 )
    {
      if ( StringFromManifest < 0 )
        return (unsigned int)StringFromManifest;
      if ( ++v16 > 2 )
      {
        StringFromManifest = -2147021875;
        ClassInstallerTelemetry::WriteDbgTraceError(
          "ParseRequiredClassDirective",
          L"Too many tokens found in RequiredClass directive");
        LODWORD(v31) = 1;
        LODWORD(v28) = 0;
        goto LABEL_21;
      }
      v17 = StripWhitespaceAndQuotes(v15);
      v15 = v17;
      if ( !*v17 )
      {
        StringFromManifest = -2147021875;
        ClassInstallerTelemetry::WriteDbgTraceError(
          "ParseRequiredClassDirective",
          L"Empty token found in RequiredClass directive");
        LODWORD(v31) = 0;
        LODWORD(v28) = 1;
LABEL_21:
        LODWORD(v33) = 0;
        v32 = 4;
        v29 = 4;
        LODWORD(v30) = 0;
        SplLogType::SplLogType((SplLogType *)v37, L"RequiredClass");
        v21 = *a1;
        v26 = v22;
        LODWORD(v27) = 1;
        v25 = L"-";
        SplLogType::SplLogType((SplLogType *)v36, v21);
        v10 = SplLogType::SplLogType((SplLogType *)v35, a1[1]);
        v24 = &v31;
        v13 = &v25;
        v14 = (const wchar_t **)&v28;
        goto LABEL_22;
      }
      if ( v16 == 1 )
      {
        v20 = AllocStr(v17);
        a1[14] = (const unsigned __int16 *)v20;
        if ( v20 )
        {
          ClassInstallerTelemetry::WriteDbgTraceInfo("ParseRequiredClassDirective", L"Base driver name='%ws'", v15);
          goto LABEL_17;
        }
      }
      else
      {
        if ( v16 != 2 )
          goto LABEL_17;
        v18 = AllocStr(v17);
        a1[15] = (const unsigned __int16 *)v18;
        if ( v18 )
        {
          ClassInstallerTelemetry::WriteDbgTraceInfo("ParseRequiredClassDirective", L"Base driver ID=%ws", v15);
LABEL_17:
          v15 = wcstok_s(0, L",", &Context);
          goto LABEL_18;
        }
      }
      StringFromManifest = NCoreLibrary::GetLastErrorAsFailHR(v19);
      if ( StringFromManifest >= 0 )
        goto LABEL_17;
LABEL_18:
      if ( !v15 )
        return (unsigned int)StringFromManifest;
    }
  }
  StringFromManifest = -2147021875;
  ClassInstallerTelemetry::WriteDbgTraceError(
    "ParseRequiredClassDirective",
    L"Empty token found in RequiredClass directive");
  LODWORD(v28) = 0;
  v29 = 4;
  v26 = 4;
  LODWORD(v30) = 0;
  LODWORD(v25) = 1;
  LODWORD(v27) = 0;
  SplLogType::SplLogType((SplLogType *)v37, L"RequiredClass");
  v8 = *a1;
  v32 = v9;
  LODWORD(v33) = 1;
  v31 = L"-";
  SplLogType::SplLogType((SplLogType *)v36, v8);
  v10 = SplLogType::SplLogType((SplLogType *)v35, a1[1]);
  v24 = (const wchar_t **)&v28;
  v13 = &v31;
  v14 = &v25;
LABEL_22:
  SplLogEvent2(
    &SETUP_INSTALL_PRINTER_DRIVER_MALFORMED_DIRECTIVE,
    v10,
    v11,
    v13,
    v12,
    v14,
    v24,
    0,
    v25,
    v26,
    v27,
    v28,
    v29,
    v30,
    v31,
    v32,
    v33);
  return (unsigned int)StringFromManifest;
}

```

## disassembly

```asm
0x180032ea4  mov     [rsp-8+arg_10], rbx
0x180032ea9  mov     [rsp-8+arg_18], rsi
0x180032eae  push    rbp
0x180032eaf  push    rdi
0x180032eb0  push    r12
0x180032eb2  push    r13
0x180032eb4  push    r14
0x180032eb6  lea     rbp, [rsp-200h]
0x180032ebe  sub     rsp, 300h
0x180032ec5  mov     rax, cs:__security_cookie
0x180032ecc  xor     rax, rsp
0x180032ecf  mov     [rbp+220h+var_30], rax
0x180032ed6  mov     r14, rcx
0x180032ed9  lea     r9, [rdx+2]; lpFileName
0x180032edd  lea     r13, aRequiredclass; "RequiredClass"
0x180032ee4  mov     r8d, 104h; nSize
0x180032eea  mov     rcx, r13; lpKeyName
0x180032eed  lea     rdx, [rbp+220h+Str]; lpReturnedString
0x180032ef1  call    ?GetStringFromManifest@@YAJPEBGPEAGK0@Z; GetStringFromManifest(ushort const *,ushort *,ulong,ushort const *)
0x180032ef6  xor     r12d, r12d
0x180032ef9  mov     edi, eax
0x180032efb  test    eax, eax
0x180032efd  js      loc_18003321E
0x180032f03  cmp     [r14+80h], r12d
0x180032f0a  jz      loc_180032FB7
0x180032f10  lea     rdx, aRequiredclassW; "RequiredClass was specified in the mani"...
0x180032f17  mov     edi, 80070BCDh
0x180032f1c  lea     rcx, aParserequiredc; "ParseRequiredClassDirective"
0x180032f23  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180032f28  lea     r10d, [r12+4]
0x180032f2d  mov     dword ptr [rsp+320h+var_2E0], 1
0x180032f35  mov     rdx, r13; unsigned __int16 *
0x180032f38  mov     [rsp+320h+var_2D8], r10
0x180032f3d  lea     rcx, [rsp+320h+var_2B0]; this
0x180032f42  mov     [rsp+320h+var_2C0], r10
0x180032f47  mov     dword ptr [rsp+320h+var_2D0], r12d
0x180032f4c  mov     dword ptr [rsp+320h+var_2C8], r12d
0x180032f51  mov     dword ptr [rsp+320h+var_2B8], r12d
0x180032f56  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032f5b  mov     rdx, [r14+70h]; unsigned __int16 *
0x180032f5f  lea     rcx, [rbp+220h+var_290]; this
0x180032f63  mov     rbx, rax
0x180032f66  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032f6b  mov     rdx, [r14]; unsigned __int16 *
0x180032f6e  lea     rcx, [rbp+220h+var_278]; this
0x180032f72  mov     r11, rax
0x180032f75  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032f7a  mov     rdx, [r14+8]; unsigned __int16 *
0x180032f7e  lea     rcx, [rbp+220h+var_260]; this
0x180032f82  mov     r10, rax
0x180032f85  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180032f8a  mov     [rsp+320h+var_2E8], r12
0x180032f8f  lea     rcx, [rsp+320h+var_2E0]
0x180032f94  mov     [rsp+320h+var_2F0], rcx
0x180032f99  mov     r9, r11
0x180032f9c  lea     rcx, [rsp+320h+var_2C8]
0x180032fa1  mov     [rsp+320h+var_2F8], rcx
0x180032fa6  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FORBIDDEN_DIRECTIVE
0x180032fad  mov     [rsp+320h+var_300], rbx
0x180032fb2  jmp     loc_1800331E7
0x180032fb7  lea     rdx, asc_18004B7AC; ",,"
0x180032fbe  lea     rcx, [rbp+220h+Str]; Str
0x180032fc2  call    cs:__imp_wcsstr
0x180032fc8  test    rax, rax
0x180032fcb  jz      loc_180033071
0x180032fd1  lea     rdx, aEmptyTokenFoun; "Empty token found in RequiredClass dire"...
0x180032fd8  mov     edi, 80070BCDh
0x180032fdd  lea     rcx, aParserequiredc; "ParseRequiredClassDirective"
0x180032fe4  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180032fe9  mov     r10d, 4
0x180032fef  mov     dword ptr [rsp+320h+var_2C8], r12d
0x180032ff4  mov     rdx, r13; unsigned __int16 *
0x180032ff7  mov     [rsp+320h+var_2C0], r10
0x180032ffc  lea     rcx, [rbp+220h+var_260]; this
0x180033000  mov     [rsp+320h+var_2D8], r10
0x180033005  mov     dword ptr [rsp+320h+var_2B8], r12d
0x18003300a  mov     dword ptr [rsp+320h+var_2E0], 1
0x180033012  mov     dword ptr [rsp+320h+var_2D0], r12d
0x180033017  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18003301c  mov     rdx, [r14]; unsigned __int16 *
0x18003301f  lea     rcx, [rbp+220h+var_278]; this
0x180033023  mov     r11, rax
0x180033026  mov     [rsp+320h+var_2A8], r10
0x18003302b  lea     rax, asc_180041954; "-"
0x180033032  mov     dword ptr [rbp+220h+var_2A0], 1
0x180033039  mov     [rsp+320h+var_2B0], rax
0x18003303e  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180033043  mov     rdx, [r14+8]; unsigned __int16 *
0x180033047  lea     rcx, [rbp+220h+var_290]; this
0x18003304b  mov     r10, rax
0x18003304e  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180033053  lea     rcx, [rsp+320h+var_2C8]
0x180033058  mov     [rsp+320h+var_2E8], r12
0x18003305d  mov     [rsp+320h+var_2F0], rcx
0x180033062  lea     r9, [rsp+320h+var_2B0]
0x180033067  lea     rcx, [rsp+320h+var_2E0]
0x18003306c  jmp     loc_1800331D6
0x180033071  lea     r8, [rbp+220h+Context]; Context
0x180033075  mov     [rbp+220h+Context], r12
0x180033079  lea     rdx, Delimiter; ","
0x180033080  lea     rcx, [rbp+220h+Str]; String
0x180033084  call    cs:__imp_wcstok_s
0x18003308a  mov     rbx, rax
0x18003308d  mov     esi, r12d
0x180033090  test    rax, rax
0x180033093  jz      loc_180033228
0x180033099  test    edi, edi
0x18003309b  js      loc_180033228
0x1800330a1  inc     esi
0x1800330a3  cmp     esi, 2
0x1800330a6  jg      loc_1800331F4
0x1800330ac  mov     rcx, rbx; unsigned __int16 *
0x1800330af  call    ?StripWhitespaceAndQuotes@@YAPEAGPEAG@Z; StripWhitespaceAndQuotes(ushort *)
0x1800330b4  mov     rbx, rax
0x1800330b7  cmp     [rax], r12w
0x1800330bb  jz      short loc_18003313B
0x1800330bd  mov     ecx, esi
0x1800330bf  sub     ecx, 1
0x1800330c2  jz      short loc_1800330E3
0x1800330c4  cmp     ecx, 1
0x1800330c7  jnz     short loc_180033117
0x1800330c9  mov     rcx, rax; unsigned __int16 *
0x1800330cc  call    AllocStr
0x1800330d1  mov     [r14+78h], rax
0x1800330d5  test    rax, rax
0x1800330d8  jz      short loc_18003310C
0x1800330da  lea     rdx, aBaseDriverIdWs; "Base driver ID=%ws"
0x1800330e1  jmp     short loc_1800330FB
0x1800330e3  mov     rcx, rbx; unsigned __int16 *
0x1800330e6  call    AllocStr
0x1800330eb  mov     [r14+70h], rax
0x1800330ef  test    rax, rax
0x1800330f2  jz      short loc_18003310C
0x1800330f4  lea     rdx, aBaseDriverName; "Base driver name='%ws'"
0x1800330fb  mov     r8, rbx
0x1800330fe  lea     rcx, aParserequiredc; "ParseRequiredClassDirective"
0x180033105  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18003310a  jmp     short loc_180033117
0x18003310c  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180033111  mov     edi, eax
0x180033113  test    eax, eax
0x180033115  js      short loc_18003312D
0x180033117  lea     r8, [rbp+220h+Context]; Context
0x18003311b  xor     ecx, ecx; String
0x18003311d  lea     rdx, Delimiter; ","
0x180033124  call    cs:__imp_wcstok_s
0x18003312a  mov     rbx, rax
0x18003312d  test    rbx, rbx
0x180033130  jnz     loc_180033099
0x180033136  jmp     loc_180033228
0x18003313b  lea     rdx, aEmptyTokenFoun; "Empty token found in RequiredClass dire"...
0x180033142  mov     edi, 80070BCDh
0x180033147  lea     rcx, aParserequiredc; "ParseRequiredClassDirective"
0x18003314e  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180033153  mov     dword ptr [rsp+320h+var_2B0], r12d
0x180033158  mov     dword ptr [rsp+320h+var_2C8], 1
0x180033160  mov     r10d, 4
0x180033166  mov     dword ptr [rbp+220h+var_2A0], r12d
0x18003316a  mov     rdx, r13; unsigned __int16 *
0x18003316d  mov     [rsp+320h+var_2A8], r10
0x180033172  lea     rcx, [rbp+220h+var_260]; this
0x180033176  mov     [rsp+320h+var_2C0], r10
0x18003317b  mov     dword ptr [rsp+320h+var_2B8], r12d
0x180033180  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180033185  mov     rdx, [r14]; unsigned __int16 *
0x180033188  lea     rcx, [rbp+220h+var_278]; this
0x18003318c  mov     r11, rax
0x18003318f  mov     [rsp+320h+var_2D8], r10
0x180033194  lea     rax, asc_180041954; "-"
0x18003319b  mov     dword ptr [rsp+320h+var_2D0], 1
0x1800331a3  mov     [rsp+320h+var_2E0], rax
0x1800331a8  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x1800331ad  mov     rdx, [r14+8]; unsigned __int16 *
0x1800331b1  lea     rcx, [rbp+220h+var_290]; this
0x1800331b5  mov     r10, rax
0x1800331b8  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x1800331bd  lea     rcx, [rsp+320h+var_2B0]
0x1800331c2  mov     [rsp+320h+var_2E8], r12
0x1800331c7  mov     [rsp+320h+var_2F0], rcx
0x1800331cc  lea     r9, [rsp+320h+var_2E0]
0x1800331d1  lea     rcx, [rsp+320h+var_2C8]
0x1800331d6  mov     [rsp+320h+var_2F8], rcx
0x1800331db  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_MALFORMED_DIRECTIVE; struct _EVENT_DESCRIPTOR *
0x1800331e2  mov     [rsp+320h+var_300], r11
0x1800331e7  mov     rdx, rax; struct SplLogType *
0x1800331ea  mov     r8, r10
0x1800331ed  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x1800331f2  jmp     short loc_180033228
0x1800331f4  lea     rdx, aTooManyTokensF; "Too many tokens found in RequiredClass "...
0x1800331fb  mov     edi, 80070BCDh
0x180033200  lea     rcx, aParserequiredc; "ParseRequiredClassDirective"
0x180033207  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18003320c  mov     dword ptr [rsp+320h+var_2B0], 1
0x180033214  mov     dword ptr [rsp+320h+var_2C8], r12d
0x180033219  jmp     loc_180033160
0x18003321e  cmp     edi, 80070002h
0x180033224  cmovz   edi, r12d
0x180033228  mov     eax, edi
0x18003322a  mov     rcx, [rbp+220h+var_30]
0x180033231  xor     rcx, rsp; StackCookie
0x180033234  call    __security_check_cookie
0x180033239  lea     r11, [rsp+320h+var_20]
0x180033241  mov     rbx, [r11+40h]
0x180033245  mov     rsi, [r11+48h]
0x180033249  mov     rsp, r11
0x18003324c  pop     r14
0x18003324e  pop     r13
0x180033250  pop     r12
0x180033252  pop     rdi
0x180033253  pop     rbp
0x180033254  retn
```
