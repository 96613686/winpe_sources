# WriteJavaScript(void)

- ea: `0x18012f3c0`
- end: `0x18012f77a`
- name: `?WriteJavaScript@@YAJXZ`
- size: `954`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180126450`
- `0x1801266fc`

## callees

- `0x180019000`
- `0x1800e4444`
- `0x1800e66b8`
- `0x1800e66dc`
- `0x1800e680c`
- `0x1800e87e8`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef498`
- `0x1800ef5d8`
- `0x1800f3f8c`
- `0x1800f9a0c`
- `0x180110e2c`
- `0x180126ae8`
- `0x180128428`
- `0x18012f3c0`
- `0x180131690`
- `0x18013191c`

## import_xrefs

- `msvcp_win!?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18012f494`
- `msvcp_win!?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18012f6ad`
- `msvcp_win!?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18012f494`
- `msvcp_win!?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18012f6ad`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18012f57a`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18012f597`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18012f6ca`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18012f6ed`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18012f713`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18012f57a`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18012f597`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18012f6ca`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18012f6ed`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18012f713`

## string_xrefs

- `0x18012f5da`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012f61f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012f5f5`: `\n        var hiddenOverlay;\n        window.onload = function () {\n            hiddenOverlay = document.getElementById("Overlay");\n        }\n\n        var currentOverlayCell;\n        var overlayProcessByDocumentBody = false;\n        document.body.addEventListener('click', function () {\n            if (hiddenOverlay.style.visibility == "visible") {\n                // If mouse click is inside the overlay, do not dismiss the overlay\n                var posX = event.clientX, posY = event.cl`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 WriteJavaScript(void)
{
  __int64 v0; // rax
  int v1; // ebx
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rax
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v6; // rax
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // eax
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v20; // rax
  __int64 v21; // rdi
  __int64 i; // rbx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  int v27; // [rsp+20h] [rbp-E0h]
  _QWORD v28[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v29[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v30[112]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v31; // [rsp+B8h] [rbp-48h]
  _BYTE v32[16]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v33; // [rsp+140h] [rbp+40h]
  _BYTE v34[32]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v28);
  v0 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, L"<script type=\"text/javascript\">");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v0, L"\n");
  std::basic_stringbuf<unsigned short>::str(v30, v32);
  v1 = WriteToFile((__int64)v32);
  std::wstring::_Tidy_deallocate(v32);
  if ( v1 < 0 )
  {
    v2 = 2534;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v1,
      v27);
    goto LABEL_17;
  }
  v3 = std::wstring::wstring(v32);
  std::basic_stringbuf<unsigned short>::_Tidy(v30);
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v3);
  std::basic_stringbuf<unsigned short>::_Init(v30, v4, *(_QWORD *)(v3 + 16), v31);
  std::wstring::_Tidy_deallocate(v32);
  std::basic_ios<unsigned short>::clear((char *)v28 + *(int *)(v28[0] + 4LL), 0, 0);
  v5 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
         v29,
         L"document.addEventListener(\"DOMContentLoaded\", function () {");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v5, L"\n");
  std::wstring::wstring(v32);
  v6 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::ConstructSummaryForErrors(v6, v32);
  if ( v33 )
  {
    v7 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
           v29,
           L"var summary = document.getElementById(\"ErrorSummary\");");
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v7, L"\n");
    v8 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, L"summary.innerHTML = \"");
    v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
    v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v8, v9);
    v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v10, L"\";");
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, L"\n");
    v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, L"summary.hidden = false;");
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v12, L"\n");
  }
  std::wstring::_Tidy_deallocate(v32);
  v13 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          v29,
          L"ProcessTableWithLargeCellContent(\"ManagedPoliciesTable\");");
  std::basic_ostream<unsigned short>::operator<<(v13, std::endl<unsigned short,std::char_traits<unsigned short>>);
  v14 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          v29,
          L"\n"
           "                if (!String.prototype.startsWith) {\n"
           "                    String.prototype.startsWith = function (searchString, position) {\n"
           "                        position = position || 0;\n"
           "                        return this.substr(position, searchString.length) === searchString;\n"
           "                    };\n"
           "                }");
  std::basic_ostream<unsigned short>::operator<<(v14, std::endl<unsigned short,std::char_traits<unsigned short>>);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, L"});\n");
  std::basic_stringbuf<unsigned short>::str(v30, v32);
  v1 = WriteToFile((__int64)v32);
  std::wstring::_Tidy_deallocate(v32);
  if ( v1 < 0 )
  {
    v2 = 2566;
    goto LABEL_7;
  }
  std::wstring::wstring(v34, aVarHiddenoverl);
  v15 = WriteToFile((__int64)v34);
  v1 = v15;
  if ( v15 >= 0 )
  {
    v16 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
    if ( *((_QWORD *)v16 + 14) == *((_QWORD *)v16 + 13) )
    {
      v1 = WriteToFile(L"</script>");
    }
    else
    {
      v17 = std::wstring::wstring(v32);
      std::basic_stringbuf<unsigned short>::_Tidy(v30);
      v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
      std::basic_stringbuf<unsigned short>::_Init(v30, v18, *(_QWORD *)(v17 + 16), v31);
      std::wstring::_Tidy_deallocate(v32);
      std::basic_ios<unsigned short>::clear((char *)v28 + *(int *)(v28[0] + 4LL), 0, 0);
      v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, L"/*");
      std::basic_ostream<unsigned short>::operator<<(v19, std::endl<unsigned short,std::char_traits<unsigned short>>);
      v20 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      v21 = *((_QWORD *)v20 + 14);
      for ( i = *((_QWORD *)v20 + 13); i != v21; i += 32 )
      {
        v23 = std::operator<<<unsigned short>(v29, i);
        std::basic_ostream<unsigned short>::operator<<(v23, std::endl<unsigned short,std::char_traits<unsigned short>>);
      }
      v24 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, L"*/");
      v25 = std::basic_ostream<unsigned short>::operator<<(
              v24,
              std::endl<unsigned short,std::char_traits<unsigned short>>);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v25, L"</script>");
      std::basic_stringbuf<unsigned short>::str(v30, v32);
      v1 = WriteToFile((__int64)v32);
      std::wstring::_Tidy_deallocate(v32);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA77,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v15,
      v27);
  }
  std::wstring::_Tidy_deallocate(v34);
LABEL_17:
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v28);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18012f3c0  push    rbp
0x18012f3c2  push    rbx
0x18012f3c3  push    rsi
0x18012f3c4  push    rdi
0x18012f3c5  lea     rbp, [rsp-88h]
0x18012f3cd  sub     rsp, 188h
0x18012f3d4  mov     rax, cs:__security_cookie
0x18012f3db  xor     rax, rsp
0x18012f3de  mov     [rbp+0A0h+var_30], rax
0x18012f3e2  lea     rcx, [rsp+1A0h+var_170]
0x18012f3e7  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18012f3ec  nop
0x18012f3ed  lea     rdx, aScriptTypeText; "<script type=\"text/javascript\">"
0x18012f3f4  lea     rcx, [rsp+1A0h+var_160]
0x18012f3f9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18012f3fe  mov     rcx, rax
0x18012f401  lea     rdi, asc_1801B9CF8; "\n"
0x18012f408  mov     rdx, rdi
0x18012f40b  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18012f410  lea     rdx, [rbp+0A0h+var_70]
0x18012f414  lea     rcx, [rsp+1A0h+var_158]
0x18012f419  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18012f41e  nop
0x18012f41f  lea     rcx, [rbp+0A0h+var_70]
0x18012f423  call    ?WriteToFile@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WriteToFile(std::wstring const &)
0x18012f428  mov     ebx, eax
0x18012f42a  lea     rcx, [rbp+0A0h+var_70]
0x18012f42e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f433  test    ebx, ebx
0x18012f435  jns     short loc_18012F441
0x18012f437  mov     edx, 9E6h
0x18012f43c  jmp     loc_18012F5DA
0x18012f441  lea     rcx, [rbp+0A0h+var_70]
0x18012f445  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18012f44a  mov     rbx, rax
0x18012f44d  lea     rcx, [rsp+1A0h+var_158]
0x18012f452  call    ?_Tidy@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXXZ; std::basic_stringbuf<ushort>::_Tidy(void)
0x18012f457  mov     rcx, rbx
0x18012f45a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012f45f  mov     r9d, [rbp+0A0h+var_E8]
0x18012f463  mov     r8, [rbx+10h]
0x18012f467  mov     rdx, rax
0x18012f46a  lea     rcx, [rsp+1A0h+var_158]
0x18012f46f  call    ?_Init@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXPEBG_KH@Z; std::basic_stringbuf<ushort>::_Init(ushort const *,unsigned __int64,int)
0x18012f474  nop
0x18012f475  lea     rcx, [rbp+0A0h+var_70]
0x18012f479  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f47e  mov     rax, [rsp+1A0h+var_170]
0x18012f483  movsxd  rcx, dword ptr [rax+4]
0x18012f487  lea     rax, [rsp+1A0h+var_170]
0x18012f48c  add     rcx, rax
0x18012f48f  xor     r8d, r8d
0x18012f492  xor     edx, edx
0x18012f494  call    cs:__imp_?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::clear(int,bool)
0x18012f49a  lea     rdx, aDocumentAddeve; "document.addEventListener(\"DOMContentL"...
0x18012f4a1  lea     rcx, [rsp+1A0h+var_160]
0x18012f4a6  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18012f4ab  mov     rcx, rax
0x18012f4ae  mov     rdx, rdi
0x18012f4b1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18012f4b6  lea     rcx, [rbp+0A0h+var_70]
0x18012f4ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18012f4bf  nop
0x18012f4c0  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012f4c5  lea     rdx, [rbp+0A0h+var_70]
0x18012f4c9  mov     rcx, rax
0x18012f4cc  call    ?ConstructSummaryForErrors@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::ConstructSummaryForErrors(std::wstring &)
0x18012f4d1  cmp     [rbp+0A0h+var_60], 0
0x18012f4d6  jbe     short loc_18012F553
0x18012f4d8  lea     rdx, aVarSummaryDocu; "var summary = document.getElementById("...
0x18012f4df  lea     rcx, [rsp+1A0h+var_160]
0x18012f4e4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18012f4e9  mov     rcx, rax
0x18012f4ec  mov     rdx, rdi
0x18012f4ef  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18012f4f4  lea     rdx, aSummaryInnerht; "summary.innerHTML = \""
0x18012f4fb  lea     rcx, [rsp+1A0h+var_160]
0x18012f500  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18012f505  mov     rbx, rax
0x18012f508  lea     rcx, [rbp+0A0h+var_70]
0x18012f50c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012f511  mov     rdx, rax
0x18012f514  mov     rcx, rbx
0x18012f517  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18012f51c  mov     rcx, rax
0x18012f51f  lea     rdx, asc_1801EE430; "\";"
0x18012f526  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18012f52b  mov     rcx, rax
0x18012f52e  mov     rdx, rdi
0x18012f531  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18012f536  lea     rdx, aSummaryHiddenF; "summary.hidden = false;"
0x18012f53d  lea     rcx, [rsp+1A0h+var_160]
0x18012f542  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18012f547  mov     rcx, rax
0x18012f54a  mov     rdx, rdi
0x18012f54d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18012f552  nop
0x18012f553  lea     rcx, [rbp+0A0h+var_70]
0x18012f557  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f55c  lea     rdx, aProcesstablewi; "ProcessTableWithLargeCellContent(\"Mana"...
0x18012f563  lea     rcx, [rsp+1A0h+var_160]
0x18012f568  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18012f56d  lea     rsi, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x18012f574  mov     rdx, rsi
0x18012f577  mov     rcx, rax
0x18012f57a  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x18012f580  lea     rdx, aIfStringProtot; "\n                if (!String.prototype"...
0x18012f587  lea     rcx, [rsp+1A0h+var_160]
0x18012f58c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18012f591  mov     rdx, rsi
0x18012f594  mov     rcx, rax
0x18012f597  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x18012f59d  lea     rdx, asc_1801EE438; "});\n"
0x18012f5a4  lea     rcx, [rsp+1A0h+var_160]
0x18012f5a9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18012f5ae  lea     rdx, [rbp+0A0h+var_70]
0x18012f5b2  lea     rcx, [rsp+1A0h+var_158]
0x18012f5b7  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18012f5bc  nop
0x18012f5bd  lea     rcx, [rbp+0A0h+var_70]
0x18012f5c1  call    ?WriteToFile@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WriteToFile(std::wstring const &)
0x18012f5c6  mov     ebx, eax
0x18012f5c8  lea     rcx, [rbp+0A0h+var_70]
0x18012f5cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f5d1  test    ebx, ebx
0x18012f5d3  jns     short loc_18012F5F5
0x18012f5d5  mov     edx, 0A06h; void *
0x18012f5da  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012f5e1  mov     r9d, ebx; char *
0x18012f5e4  mov     rcx, [rbp+0A8h]; this
0x18012f5eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f5f0  jmp     loc_18012F756
0x18012f5f5  lea     rdx, aVarHiddenoverl; "\n        var hiddenOverlay;\n        w"...
0x18012f5fc  lea     rcx, [rbp+0A0h+var_50]
0x18012f600  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012f605  nop
0x18012f606  lea     rcx, [rbp+0A0h+var_50]
0x18012f60a  call    ?WriteToFile@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WriteToFile(std::wstring const &)
0x18012f60f  mov     ebx, eax
0x18012f611  test    eax, eax
0x18012f613  jns     short loc_18012F635
0x18012f615  mov     rcx, [rbp+0A8h]; this
0x18012f61c  mov     r9d, eax; char *
0x18012f61f  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012f626  mov     edx, 0A77h; void *
0x18012f62b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f630  jmp     loc_18012F74C
0x18012f635  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012f63a  mov     rcx, rax
0x18012f63d  mov     rax, [rax+70h]
0x18012f641  cmp     rax, [rcx+68h]
0x18012f645  jnz     short loc_18012F65A
0x18012f647  lea     rcx, aScript; "</script>"
0x18012f64e  call    ?WriteToFile@@YAJPEBG@Z; WriteToFile(ushort const *)
0x18012f653  mov     ebx, eax
0x18012f655  jmp     loc_18012F74C
0x18012f65a  lea     rcx, [rbp+0A0h+var_70]
0x18012f65e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18012f663  mov     rbx, rax
0x18012f666  lea     rcx, [rsp+1A0h+var_158]
0x18012f66b  call    ?_Tidy@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXXZ; std::basic_stringbuf<ushort>::_Tidy(void)
0x18012f670  mov     rcx, rbx
0x18012f673  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012f678  mov     r9d, [rbp+0A0h+var_E8]
0x18012f67c  mov     r8, [rbx+10h]
0x18012f680  mov     rdx, rax
0x18012f683  lea     rcx, [rsp+1A0h+var_158]
0x18012f688  call    ?_Init@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXPEBG_KH@Z; std::basic_stringbuf<ushort>::_Init(ushort const *,unsigned __int64,int)
0x18012f68d  nop
0x18012f68e  lea     rcx, [rbp+0A0h+var_70]
0x18012f692  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f697  mov     rax, [rsp+1A0h+var_170]
0x18012f69c  movsxd  rcx, dword ptr [rax+4]
0x18012f6a0  lea     rax, [rsp+1A0h+var_170]
0x18012f6a5  add     rcx, rax
0x18012f6a8  xor     r8d, r8d
0x18012f6ab  xor     edx, edx
0x18012f6ad  call    cs:__imp_?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::clear(int,bool)
0x18012f6b3  lea     rdx, asc_1801F0DE4; "/*"
0x18012f6ba  lea     rcx, [rsp+1A0h+var_160]
0x18012f6bf  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18012f6c4  mov     rdx, rsi
0x18012f6c7  mov     rcx, rax
0x18012f6ca  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x18012f6d0  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012f6d5  mov     rdi, [rax+70h]
0x18012f6d9  mov     rbx, [rax+68h]
0x18012f6dd  jmp     short loc_18012F6F7
0x18012f6df  mov     rdx, rbx
0x18012f6e2  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18012f6e7  mov     rdx, rsi
0x18012f6ea  mov     rcx, rax
0x18012f6ed  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x18012f6f3  add     rbx, 20h ; ' '
0x18012f6f7  lea     rcx, [rsp+1A0h+var_160]
0x18012f6fc  cmp     rbx, rdi
0x18012f6ff  jnz     short loc_18012F6DF
0x18012f701  lea     rdx, asc_1801F0DC4; "*/"
0x18012f708  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18012f70d  mov     rdx, rsi
0x18012f710  mov     rcx, rax
0x18012f713  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x18012f719  mov     rcx, rax
0x18012f71c  lea     rdx, aScript; "</script>"
0x18012f723  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18012f728  lea     rdx, [rbp+0A0h+var_70]
0x18012f72c  lea     rcx, [rsp+1A0h+var_158]
0x18012f731  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18012f736  nop
0x18012f737  lea     rcx, [rbp+0A0h+var_70]
0x18012f73b  call    ?WriteToFile@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WriteToFile(std::wstring const &)
0x18012f740  mov     ebx, eax
0x18012f742  lea     rcx, [rbp+0A0h+var_70]
0x18012f746  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f74b  nop
0x18012f74c  lea     rcx, [rbp+0A0h+var_50]
0x18012f750  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f755  nop
0x18012f756  lea     rcx, [rsp+1A0h+var_170]
0x18012f75b  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x18012f760  mov     eax, ebx
0x18012f762  mov     rcx, [rbp+0A0h+var_30]
0x18012f766  xor     rcx, rsp; StackCookie
0x18012f769  call    __security_check_cookie
0x18012f76e  add     rsp, 188h
0x18012f775  pop     rdi
0x18012f776  pop     rsi
0x18012f777  pop     rbx
0x18012f778  pop     rbp
0x18012f779  retn
```
