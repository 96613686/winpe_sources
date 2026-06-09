# WriteJavaScript(void)

- ea: `0x18013116c`
- end: `0x18013154b`
- name: `?WriteJavaScript@@YAJXZ`
- size: `991`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180127e8c`
- `0x180128138`

## callees

- `0x180019080`
- `0x1800e4508`
- `0x1800e688c`
- `0x1800e68b0`
- `0x1800e69f4`
- `0x1800e8a44`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efc2c`
- `0x1800efd9c`
- `0x1800f4b2c`
- `0x1800faa0c`
- `0x18011229c`
- `0x180128538`
- `0x180129f58`
- `0x18013116c`
- `0x1801334ac`
- `0x18013375c`

## import_xrefs

- `msvcp_win!?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18013123c`
- `msvcp_win!?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x180131466`
- `msvcp_win!?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18013123c`
- `msvcp_win!?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x180131466`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180131328`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18013134b`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180131489`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x1801314b2`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x1801314de`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180131328`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18013134b`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180131489`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x1801314b2`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x1801314de`

## string_xrefs

- `0x180131393`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x1801313d8`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x1801313ae`: `\n        var hiddenOverlay;\n        window.onload = function () {\n            hiddenOverlay = document.getElementById("Overlay");\n        }\n\n        var currentOverlayCell;\n        var overlayProcessByDocumentBody = false;\n        document.body.addEventListener('click', function () {\n            if (hiddenOverlay.style.visibility == "visible") {\n                // If mouse click is inside the overlay, do not dismiss the overlay\n                var posX = event.clientX, posY = event.cl`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 WriteJavaScript(void)
{
  __int64 v0; // rax
  __int64 v1; // rax
  int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  int v17; // eax
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rax
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v22; // rax
  __int64 v23; // rdi
  __int64 i; // rbx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  int v30[4]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v31[8]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v32[112]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v33; // [rsp+A8h] [rbp-58h]
  _BYTE v34[16]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v35; // [rsp+130h] [rbp+30h]
  _BYTE v36[32]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v30);
  v0 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v31, L"<script type=\"text/javascript\">");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v0, L"\n");
  v1 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
         v30,
         v34);
  v2 = WriteToFile(v1);
  std::wstring::_Tidy_deallocate(v34);
  if ( v2 < 0 )
  {
    v3 = 2534;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v2,
      v30[0]);
    goto LABEL_17;
  }
  v4 = std::wstring::wstring(v34);
  std::basic_stringbuf<unsigned short>::_Tidy(v32);
  v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
  std::basic_stringbuf<unsigned short>::_Init(v32, v5, *(_QWORD *)(v4 + 16), v33);
  std::wstring::_Tidy_deallocate(v34);
  std::basic_ios<unsigned short>::clear((char *)v30 + *(int *)(*(_QWORD *)v30 + 4LL), 0, 0);
  v6 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
         v31,
         L"document.addEventListener(\"DOMContentLoaded\", function () {");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v6, L"\n");
  std::wstring::wstring(v34);
  v7 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::ConstructSummaryForErrors(v7, v34);
  if ( v35 )
  {
    v8 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
           v31,
           L"var summary = document.getElementById(\"ErrorSummary\");");
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v8, L"\n");
    v9 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v31, L"summary.innerHTML = \"");
    v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34);
    v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v9, v10);
    v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, L"\";");
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v12, L"\n");
    v13 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v31, L"summary.hidden = false;");
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v13, L"\n");
  }
  std::wstring::_Tidy_deallocate(v34);
  v14 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          v31,
          L"ProcessTableWithLargeCellContent(\"ManagedPoliciesTable\");");
  std::basic_ostream<unsigned short>::operator<<(v14, std::endl<unsigned short,std::char_traits<unsigned short>>);
  v15 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          v31,
          L"\n"
           "                if (!String.prototype.startsWith) {\n"
           "                    String.prototype.startsWith = function (searchString, position) {\n"
           "                        position = position || 0;\n"
           "                        return this.substr(position, searchString.length) === searchString;\n"
           "                    };\n"
           "                }");
  std::basic_ostream<unsigned short>::operator<<(v15, std::endl<unsigned short,std::char_traits<unsigned short>>);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v31, L"});\n");
  v16 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
          v30,
          v34);
  v2 = WriteToFile(v16);
  std::wstring::_Tidy_deallocate(v34);
  if ( v2 < 0 )
  {
    v3 = 2566;
    goto LABEL_7;
  }
  std::wstring::wstring(v36, aVarHiddenoverl);
  v17 = WriteToFile((__int64)v36);
  v2 = v17;
  if ( v17 >= 0 )
  {
    v18 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
    if ( *((_QWORD *)v18 + 14) == *((_QWORD *)v18 + 13) )
    {
      v2 = WriteToFile(L"</script>");
    }
    else
    {
      v19 = std::wstring::wstring(v34);
      std::basic_stringbuf<unsigned short>::_Tidy(v32);
      v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v19);
      std::basic_stringbuf<unsigned short>::_Init(v32, v20, *(_QWORD *)(v19 + 16), v33);
      std::wstring::_Tidy_deallocate(v34);
      std::basic_ios<unsigned short>::clear((char *)v30 + *(int *)(*(_QWORD *)v30 + 4LL), 0, 0);
      v21 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v31, L"/*");
      std::basic_ostream<unsigned short>::operator<<(v21, std::endl<unsigned short,std::char_traits<unsigned short>>);
      v22 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      v23 = *((_QWORD *)v22 + 14);
      for ( i = *((_QWORD *)v22 + 13); i != v23; i += 32 )
      {
        v25 = std::operator<<<unsigned short>(v31, i);
        std::basic_ostream<unsigned short>::operator<<(v25, std::endl<unsigned short,std::char_traits<unsigned short>>);
      }
      v26 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v31, L"*/");
      v27 = std::basic_ostream<unsigned short>::operator<<(
              v26,
              std::endl<unsigned short,std::char_traits<unsigned short>>);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v27, L"</script>");
      v28 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
              v30,
              v34);
      v2 = WriteToFile(v28);
      std::wstring::_Tidy_deallocate(v34);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA77,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v17,
      v30[0]);
  }
  std::wstring::_Tidy_deallocate(v36);
LABEL_17:
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v30);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18013116c  push    rbp
0x18013116e  push    rbx
0x18013116f  push    rsi
0x180131170  push    rdi
0x180131171  lea     rbp, [rsp-78h]
0x180131176  sub     rsp, 178h
0x18013117d  mov     rax, cs:__security_cookie
0x180131184  xor     rax, rsp
0x180131187  mov     [rbp+90h+var_30], rax
0x18013118b  lea     rcx, [rsp+190h+var_170]
0x180131190  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180131195  nop
0x180131196  lea     rdx, aScriptTypeText; "<script type=\"text/javascript\">"
0x18013119d  lea     rcx, [rsp+190h+var_160]
0x1801311a2  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1801311a7  mov     rcx, rax
0x1801311aa  lea     rdi, asc_1801BBCF8; "\n"
0x1801311b1  mov     rdx, rdi
0x1801311b4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1801311b9  lea     rdx, [rbp+90h+var_70]
0x1801311bd  lea     rcx, [rsp+190h+var_170]
0x1801311c2  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x1801311c7  nop
0x1801311c8  mov     rcx, rax
0x1801311cb  call    ?WriteToFile@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WriteToFile(std::wstring const &)
0x1801311d0  mov     ebx, eax
0x1801311d2  lea     rcx, [rbp+90h+var_70]
0x1801311d6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801311db  test    ebx, ebx
0x1801311dd  jns     short loc_1801311E9
0x1801311df  mov     edx, 9E6h
0x1801311e4  jmp     loc_180131393
0x1801311e9  lea     rcx, [rbp+90h+var_70]
0x1801311ed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801311f2  mov     rbx, rax
0x1801311f5  lea     rcx, [rsp+190h+var_158]
0x1801311fa  call    ?_Tidy@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXXZ; std::basic_stringbuf<ushort>::_Tidy(void)
0x1801311ff  mov     rcx, rbx
0x180131202  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180131207  mov     r9d, [rbp+90h+var_E8]
0x18013120b  mov     r8, [rbx+10h]
0x18013120f  mov     rdx, rax
0x180131212  lea     rcx, [rsp+190h+var_158]
0x180131217  call    ?_Init@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXPEBG_KH@Z; std::basic_stringbuf<ushort>::_Init(ushort const *,unsigned __int64,int)
0x18013121c  nop
0x18013121d  lea     rcx, [rbp+90h+var_70]
0x180131221  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180131226  mov     rax, qword ptr [rsp+190h+var_170]
0x18013122b  movsxd  rcx, dword ptr [rax+4]
0x18013122f  lea     rax, [rsp+190h+var_170]
0x180131234  add     rcx, rax
0x180131237  xor     r8d, r8d
0x18013123a  xor     edx, edx
0x18013123c  call    cs:__imp_?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::clear(int,bool)
0x180131243  nop     dword ptr [rax+rax+00h]
0x180131248  lea     rdx, aDocumentAddeve; "document.addEventListener(\"DOMContentL"...
0x18013124f  lea     rcx, [rsp+190h+var_160]
0x180131254  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180131259  mov     rcx, rax
0x18013125c  mov     rdx, rdi
0x18013125f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180131264  lea     rcx, [rbp+90h+var_70]
0x180131268  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18013126d  nop
0x18013126e  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180131273  lea     rdx, [rbp+90h+var_70]
0x180131277  mov     rcx, rax
0x18013127a  call    ?ConstructSummaryForErrors@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::ConstructSummaryForErrors(std::wstring &)
0x18013127f  cmp     [rbp+90h+var_60], 0
0x180131284  jbe     short loc_180131301
0x180131286  lea     rdx, aVarSummaryDocu; "var summary = document.getElementById("...
0x18013128d  lea     rcx, [rsp+190h+var_160]
0x180131292  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180131297  mov     rcx, rax
0x18013129a  mov     rdx, rdi
0x18013129d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1801312a2  lea     rdx, aSummaryInnerht; "summary.innerHTML = \""
0x1801312a9  lea     rcx, [rsp+190h+var_160]
0x1801312ae  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1801312b3  mov     rbx, rax
0x1801312b6  lea     rcx, [rbp+90h+var_70]
0x1801312ba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801312bf  mov     rdx, rax
0x1801312c2  mov     rcx, rbx
0x1801312c5  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1801312ca  mov     rcx, rax
0x1801312cd  lea     rdx, asc_1801F03F0; "\";"
0x1801312d4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1801312d9  mov     rcx, rax
0x1801312dc  mov     rdx, rdi
0x1801312df  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1801312e4  lea     rdx, aSummaryHiddenF; "summary.hidden = false;"
0x1801312eb  lea     rcx, [rsp+190h+var_160]
0x1801312f0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1801312f5  mov     rcx, rax
0x1801312f8  mov     rdx, rdi
0x1801312fb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180131300  nop
0x180131301  lea     rcx, [rbp+90h+var_70]
0x180131305  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013130a  lea     rdx, aProcesstablewi; "ProcessTableWithLargeCellContent(\"Mana"...
0x180131311  lea     rcx, [rsp+190h+var_160]
0x180131316  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18013131b  lea     rsi, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x180131322  mov     rdx, rsi
0x180131325  mov     rcx, rax
0x180131328  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x18013132f  nop     dword ptr [rax+rax+00h]
0x180131334  lea     rdx, aIfStringProtot; "\n                if (!String.prototype"...
0x18013133b  lea     rcx, [rsp+190h+var_160]
0x180131340  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180131345  mov     rdx, rsi
0x180131348  mov     rcx, rax
0x18013134b  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x180131352  nop     dword ptr [rax+rax+00h]
0x180131357  lea     rdx, asc_1801F03F8; "});\n"
0x18013135e  lea     rcx, [rsp+190h+var_160]
0x180131363  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180131368  lea     rdx, [rbp+90h+var_70]
0x18013136c  lea     rcx, [rsp+190h+var_170]
0x180131371  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x180131376  nop
0x180131377  mov     rcx, rax
0x18013137a  call    ?WriteToFile@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WriteToFile(std::wstring const &)
0x18013137f  mov     ebx, eax
0x180131381  lea     rcx, [rbp+90h+var_70]
0x180131385  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013138a  test    ebx, ebx
0x18013138c  jns     short loc_1801313AE
0x18013138e  mov     edx, 0A06h; void *
0x180131393  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013139a  mov     r9d, ebx; char *
0x18013139d  mov     rcx, [rbp+98h]; this
0x1801313a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801313a9  jmp     loc_180131526
0x1801313ae  lea     rdx, aVarHiddenoverl; "\n        var hiddenOverlay;\n        w"...
0x1801313b5  lea     rcx, [rbp+90h+var_50]
0x1801313b9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801313be  nop
0x1801313bf  lea     rcx, [rbp+90h+var_50]
0x1801313c3  call    ?WriteToFile@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WriteToFile(std::wstring const &)
0x1801313c8  mov     ebx, eax
0x1801313ca  test    eax, eax
0x1801313cc  jns     short loc_1801313EE
0x1801313ce  mov     rcx, [rbp+98h]; this
0x1801313d5  mov     r9d, eax; char *
0x1801313d8  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801313df  mov     edx, 0A77h; void *
0x1801313e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801313e9  jmp     loc_18013151C
0x1801313ee  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x1801313f3  mov     rcx, rax
0x1801313f6  mov     rax, [rax+70h]
0x1801313fa  cmp     rax, [rcx+68h]
0x1801313fe  jnz     short loc_180131413
0x180131400  lea     rcx, aScript; "</script>"
0x180131407  call    ?WriteToFile@@YAJPEBG@Z; WriteToFile(ushort const *)
0x18013140c  mov     ebx, eax
0x18013140e  jmp     loc_18013151C
0x180131413  lea     rcx, [rbp+90h+var_70]
0x180131417  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18013141c  mov     rbx, rax
0x18013141f  lea     rcx, [rsp+190h+var_158]
0x180131424  call    ?_Tidy@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXXZ; std::basic_stringbuf<ushort>::_Tidy(void)
0x180131429  mov     rcx, rbx
0x18013142c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180131431  mov     r9d, [rbp+90h+var_E8]
0x180131435  mov     r8, [rbx+10h]
0x180131439  mov     rdx, rax
0x18013143c  lea     rcx, [rsp+190h+var_158]
0x180131441  call    ?_Init@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXPEBG_KH@Z; std::basic_stringbuf<ushort>::_Init(ushort const *,unsigned __int64,int)
0x180131446  nop
0x180131447  lea     rcx, [rbp+90h+var_70]
0x18013144b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180131450  mov     rax, qword ptr [rsp+190h+var_170]
0x180131455  movsxd  rcx, dword ptr [rax+4]
0x180131459  lea     rax, [rsp+190h+var_170]
0x18013145e  add     rcx, rax
0x180131461  xor     r8d, r8d
0x180131464  xor     edx, edx
0x180131466  call    cs:__imp_?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::clear(int,bool)
0x18013146d  nop     dword ptr [rax+rax+00h]
0x180131472  lea     rdx, asc_1801F2DA4; "/*"
0x180131479  lea     rcx, [rsp+190h+var_160]
0x18013147e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180131483  mov     rdx, rsi
0x180131486  mov     rcx, rax
0x180131489  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x180131490  nop     dword ptr [rax+rax+00h]
0x180131495  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013149a  mov     rdi, [rax+70h]
0x18013149e  mov     rbx, [rax+68h]
0x1801314a2  jmp     short loc_1801314C2
0x1801314a4  mov     rdx, rbx
0x1801314a7  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x1801314ac  mov     rdx, rsi
0x1801314af  mov     rcx, rax
0x1801314b2  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x1801314b9  nop     dword ptr [rax+rax+00h]
0x1801314be  add     rbx, 20h ; ' '
0x1801314c2  lea     rcx, [rsp+190h+var_160]
0x1801314c7  cmp     rbx, rdi
0x1801314ca  jnz     short loc_1801314A4
0x1801314cc  lea     rdx, asc_1801F2D84; "*/"
0x1801314d3  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1801314d8  mov     rdx, rsi
0x1801314db  mov     rcx, rax
0x1801314de  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x1801314e5  nop     dword ptr [rax+rax+00h]
0x1801314ea  mov     rcx, rax
0x1801314ed  lea     rdx, aScript; "</script>"
0x1801314f4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1801314f9  lea     rdx, [rbp+90h+var_70]
0x1801314fd  lea     rcx, [rsp+190h+var_170]
0x180131502  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x180131507  nop
0x180131508  mov     rcx, rax
0x18013150b  call    ?WriteToFile@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WriteToFile(std::wstring const &)
0x180131510  mov     ebx, eax
0x180131512  lea     rcx, [rbp+90h+var_70]
0x180131516  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013151b  nop
0x18013151c  lea     rcx, [rbp+90h+var_50]
0x180131520  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180131525  nop
0x180131526  lea     rcx, [rsp+190h+var_170]
0x18013152b  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x180131530  mov     eax, ebx
0x180131532  mov     rcx, [rbp+90h+var_30]
0x180131536  xor     rcx, rsp; StackCookie
0x180131539  call    __security_check_cookie
0x18013153e  add     rsp, 178h
0x180131545  pop     rdi
0x180131546  pop     rsi
0x180131547  pop     rbx
0x180131548  pop     rbp
0x180131549  retn
```
