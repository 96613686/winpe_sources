# LPA::Lpd::DownloadInstance::GetEs9ExecutionStatusAsHResult(web::json::value &,LPAERROR &)

- ea: `0x1800afbd4`
- end: `0x1800b02f5`
- name: `?GetEs9ExecutionStatusAsHResult@DownloadInstance@Lpd@LPA@@CAJAEAVvalue@json@web@@AEAW4LPAERROR@@@Z`
- size: `1825`
- prototype: `__int64 __fastcall(struct web::json::value *this, enum LPAERROR *)`
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a9920`
- `0x1800a9dbc`
- `0x1800aa0f8`
- `0x1800bdbf0`

## callees

- `0x180006260`
- `0x18000df90`
- `0x1800171a0`
- `0x180017200`
- `0x180018dd0`
- `0x180063668`
- `0x180071344`
- `0x180071650`
- `0x1800afbd4`
- `0x1800b1358`
- `0x1800c0b20`
- `0x1800c12c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800afd3b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800afd57`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800afd73`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800afd97`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800afd3b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800afd57`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800afd73`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800afd97`

## string_xrefs

- `0x1800b0176`: `LpaServiceLpd`
- `0x1800b0262`: `LpaServiceLpd`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall LPA::Lpd::DownloadInstance::GetEs9ExecutionStatusAsHResult(
        struct web::json::value *this,
        enum LPAERROR *a2)
{
  __int64 v4; // r15
  __int64 v5; // rsi
  __int64 v6; // rdi
  __int64 v7; // r13
  int v8; // r12d
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  const struct web::json::object *v12; // rbx
  web::json::value *v13; // rbx
  const struct web::json::object *v14; // rbx
  const struct web::json::object *v15; // rbx
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  const unsigned __int16 *v26; // rbx
  const unsigned __int16 *v27; // rax
  const unsigned __int16 *v28; // rax
  const unsigned __int16 *v29; // rax
  const unsigned __int16 *v30; // rax
  const char **v31; // rax
  char *v32; // rdx
  const unsigned __int16 *v33; // rbx
  const unsigned __int16 *v34; // rax
  const unsigned __int16 *v35; // rax
  const unsigned __int16 *v36; // rax
  const unsigned __int16 *v37; // rax
  const char **v39; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 **v40; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 **v41; // [rsp+48h] [rbp-B8h]
  const char **v42; // [rsp+50h] [rbp-B0h]
  const char **v43; // [rsp+58h] [rbp-A8h]
  web::json::value *v44; // [rsp+60h] [rbp-A0h] BYREF
  const char *v45; // [rsp+68h] [rbp-98h] BYREF
  const char *v46; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v47; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *v48; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v49; // [rsp+88h] [rbp-78h] BYREF
  const char *v50; // [rsp+90h] [rbp-70h] BYREF
  const char *v51; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v52[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v53[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v54[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v55[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v56[32]; // [rsp+120h] [rbp+20h] BYREF

  v4 = 0;
  v5 = 0;
  v6 = 0;
  v45 = 0;
  v7 = 0;
  v8 = -2147418113;
  if ( (unsigned __int8)LPA::Lpd::DownloadInstance::JsonCheckFieldAndOptionallyThrow(
                          this,
                          L"header",
                          web::json::value::is_object,
                          0) )
  {
    v12 = web::json::value::as_object(this);
    std::wstring::wstring(v52, L"header");
    v13 = (web::json::value *)web::json::object::at(v12, v52);
    std::wstring::_Tidy_deallocate(v52);
    if ( (unsigned __int8)LPA::Lpd::DownloadInstance::JsonCheckFieldAndOptionallyThrow(
                            v13,
                            L"functionExecutionStatus",
                            web::json::value::is_object,
                            0) )
    {
      v14 = web::json::value::as_object(v13);
      std::wstring::wstring(v53, L"functionExecutionStatus");
      v44 = (web::json::value *)web::json::object::at(v14, v53);
      std::wstring::_Tidy_deallocate(v53);
      if ( (unsigned __int8)LPA::Lpd::DownloadInstance::JsonCheckFieldAndOptionallyThrow(
                              v44,
                              L"status",
                              web::json::value::is_string,
                              0) )
      {
        v15 = web::json::value::as_object(v44);
        std::wstring::wstring(v52, L"status");
        v16 = web::json::object::at(v15, v52);
        std::wstring::_Tidy_deallocate(v52);
        v4 = web::json::value::as_string(v16);
        v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
        if ( (unsigned int)_o__wcsicmp(v17, L"Executed-Success")
          && (v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4),
              (unsigned int)_o__wcsicmp(v18, L"Executed-WithWarning")) )
        {
          v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
          if ( (unsigned int)_o__wcsicmp(v19, L"Failed") )
          {
            v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
            if ( !(unsigned int)_o__wcsicmp(v20, L"Expired") )
              v8 = -2147023436;
          }
          else
          {
            v8 = -2147467259;
          }
        }
        else
        {
          v8 = 0;
        }
      }
      if ( (unsigned __int8)LPA::Lpd::DownloadInstance::JsonCheckFieldAndOptionallyThrow(
                              v44,
                              L"statusCodeData",
                              web::json::value::is_object,
                              0) )
      {
        std::wstring::wstring(v52, L"statusCodeData");
        v21 = web::json::value::at(v44, v52);
        std::wstring::_Tidy_deallocate(v52);
        if ( (unsigned __int8)LPA::Lpd::DownloadInstance::JsonCheckFieldAndOptionallyThrow(
                                v21,
                                L"subjectCode",
                                web::json::value::is_string,
                                0) )
        {
          std::wstring::wstring(v53, L"subjectCode");
          v22 = web::json::value::at(v21, v53);
          v5 = web::json::value::as_string(v22);
          std::wstring::_Tidy_deallocate(v53);
        }
        if ( (unsigned __int8)LPA::Lpd::DownloadInstance::JsonCheckFieldAndOptionallyThrow(
                                v21,
                                L"reasonCode",
                                web::json::value::is_string,
                                0) )
        {
          std::wstring::wstring(v54, L"reasonCode");
          v23 = web::json::value::at(v21, v54);
          v6 = web::json::value::as_string(v23);
          std::wstring::_Tidy_deallocate(v54);
        }
        if ( (unsigned __int8)LPA::Lpd::DownloadInstance::JsonCheckFieldAndOptionallyThrow(
                                v21,
                                L"subjectIdentifier",
                                web::json::value::is_string,
                                0) )
        {
          std::wstring::wstring(v55, L"subjectIdentifier");
          v24 = web::json::value::at(v21, v55);
          v45 = (const char *)web::json::value::as_string(v24);
          std::wstring::_Tidy_deallocate(v55);
        }
        if ( (unsigned __int8)LPA::Lpd::DownloadInstance::JsonCheckFieldAndOptionallyThrow(
                                v21,
                                L"message",
                                web::json::value::is_string,
                                0) )
        {
          std::wstring::wstring(v56, L"message");
          v25 = web::json::value::at(v21, v56);
          v7 = web::json::value::as_string(v25);
          std::wstring::_Tidy_deallocate(v56);
        }
      }
    }
  }
  *(_DWORD *)a2 = 13;
  if ( v5 && v6 )
  {
    if ( (unsigned int)std::wstring::compare(v5, L"8.2.7") )
    {
      if ( (unsigned int)std::wstring::compare(v5, L"8.8.5") )
      {
        if ( (unsigned int)std::wstring::compare(v5, L"8.1.1") )
        {
          if ( (unsigned int)std::wstring::compare(v5, L"8.2.6") )
          {
            if ( (unsigned int)std::wstring::compare(v5, L"8.2") )
            {
              if ( !(unsigned int)std::wstring::compare(v5, L"8.2.5")
                && !(unsigned int)std::wstring::compare(v6, L"4.3") )
              {
                *(_DWORD *)a2 = 7;
              }
            }
            else if ( (unsigned int)std::wstring::compare(v6, L"1.2") )
            {
              if ( !(unsigned int)std::wstring::compare(v6, L"3.7") )
                *(_DWORD *)a2 = 11;
            }
            else
            {
              *(_DWORD *)a2 = 12;
            }
          }
          else if ( !(unsigned int)std::wstring::compare(v6, L"3.8") )
          {
            *(_DWORD *)a2 = 6;
          }
        }
        else if ( !(unsigned int)std::wstring::compare(v6, L"3.8") )
        {
          *(_DWORD *)a2 = 10;
        }
      }
      else if ( !(unsigned int)std::wstring::compare(v6, L"6.4") )
      {
        *(_DWORD *)a2 = 23;
      }
    }
    else if ( (unsigned int)std::wstring::compare(v6, L"3.8") )
    {
      if ( (unsigned int)std::wstring::compare(v6, L"6.4") )
      {
        if ( !(unsigned int)std::wstring::compare(v6, L"2.2") )
          *(_DWORD *)a2 = 3;
      }
      else
      {
        *(_DWORD *)a2 = 4;
      }
    }
    else
    {
      *(_DWORD *)a2 = 2;
    }
  }
  if ( v8 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v33 = &qword_1801130E8;
      if ( v7 )
        v34 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7);
      else
        v34 = &qword_1801130E8;
      v51 = (const char *)v34;
      if ( v45 )
        v35 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
      else
        v35 = &qword_1801130E8;
      v50 = (const char *)v35;
      if ( v6 )
        v36 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6);
      else
        v36 = &qword_1801130E8;
      v49 = v36;
      if ( v5 )
        v37 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5);
      else
        v37 = &qword_1801130E8;
      v48 = v37;
      if ( v4 )
        v33 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
      v47 = v33;
      v46 = "LPA::Lpd::DownloadInstance::GetEs9ExecutionStatusAsHResult";
      v45 = "LpaServiceLpd";
      v43 = &v51;
      v42 = &v50;
      v41 = &v49;
      v40 = &v47;
      v39 = &v46;
      v31 = &v45;
      v32 = byte_18012FA51;
      goto LABEL_79;
    }
  }
  else if ( (unsigned int)CallbackContext > 4 )
  {
    v26 = &qword_1801130E8;
    if ( v7 )
      v27 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7);
    else
      v27 = &qword_1801130E8;
    v46 = (const char *)v27;
    if ( v45 )
      v28 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
    else
      v28 = &qword_1801130E8;
    v45 = (const char *)v28;
    if ( v6 )
      v29 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6);
    else
      v29 = &qword_1801130E8;
    v47 = v29;
    if ( v5 )
      v30 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5);
    else
      v30 = &qword_1801130E8;
    v48 = v30;
    if ( v4 )
      v26 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
    v49 = v26;
    v50 = "LPA::Lpd::DownloadInstance::GetEs9ExecutionStatusAsHResult";
    v51 = "LpaServiceLpd";
    v43 = &v46;
    v42 = &v45;
    v41 = &v47;
    v40 = &v49;
    v39 = &v50;
    v31 = &v51;
    v32 = &byte_18012FAC7;
LABEL_79:
    LODWORD(v44) = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v9,
      (_DWORD)v32,
      v10,
      v11,
      (__int64)v31,
      (__int64)v39,
      (__int64)&v44,
      (__int64)v40,
      (__int64)&v48,
      (__int64)v41,
      (__int64)v42,
      (__int64)v43);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800afbd4  mov     [rsp-8+arg_10], rbx
0x1800afbd9  push    rbp
0x1800afbda  push    rsi
0x1800afbdb  push    rdi
0x1800afbdc  push    r12
0x1800afbde  push    r13
0x1800afbe0  push    r14
0x1800afbe2  push    r15
0x1800afbe4  lea     rbp, [rsp-50h]
0x1800afbe9  sub     rsp, 150h
0x1800afbf0  mov     rax, cs:__security_cookie
0x1800afbf7  xor     rax, rsp
0x1800afbfa  mov     [rbp+80h+var_40], rax
0x1800afbfe  mov     r14, rdx
0x1800afc01  mov     rbx, rcx
0x1800afc04  xor     r15d, r15d
0x1800afc07  xor     esi, esi
0x1800afc09  xor     edi, edi
0x1800afc0b  xor     eax, eax
0x1800afc0d  mov     [rsp+180h+var_118], rax
0x1800afc12  xor     r13d, r13d
0x1800afc15  mov     r12d, 8000FFFFh
0x1800afc1b  xor     r9d, r9d
0x1800afc1e  lea     r8, ?is_object@value@json@web@@QEBA_NXZ; web::json::value::is_object(void)
0x1800afc25  lea     rdx, aHeader; "header"
0x1800afc2c  call    ?JsonCheckFieldAndOptionallyThrow@DownloadInstance@Lpd@LPA@@CA_NAEAVvalue@json@web@@PEBGP8456@EBA_NXZ_N@Z; LPA::Lpd::DownloadInstance::JsonCheckFieldAndOptionallyThrow(web::json::value &,ushort const *,bool (web::json::value::*)(void),bool)
0x1800afc31  test    al, al
0x1800afc33  jz      loc_1800AFF34
0x1800afc39  mov     rcx, rbx; this
0x1800afc3c  call    ?as_object@value@json@web@@QEBAAEBVobject@23@XZ; web::json::value::as_object(void)
0x1800afc41  mov     rbx, rax
0x1800afc44  lea     rdx, aHeader; "header"
0x1800afc4b  lea     rcx, [rbp+80h+var_E0]
0x1800afc4f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800afc54  nop
0x1800afc55  lea     rdx, [rbp+80h+var_E0]
0x1800afc59  mov     rcx, rbx
0x1800afc5c  call    ?at@object@json@web@@QEAAAEAVvalue@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::object::at(std::wstring const &)
0x1800afc61  mov     rbx, rax
0x1800afc64  lea     rcx, [rbp+80h+var_E0]
0x1800afc68  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800afc6d  xor     r9d, r9d
0x1800afc70  lea     r8, ?is_object@value@json@web@@QEBA_NXZ; web::json::value::is_object(void)
0x1800afc77  lea     rdx, aFunctionexecut; "functionExecutionStatus"
0x1800afc7e  mov     rcx, rbx
0x1800afc81  call    ?JsonCheckFieldAndOptionallyThrow@DownloadInstance@Lpd@LPA@@CA_NAEAVvalue@json@web@@PEBGP8456@EBA_NXZ_N@Z; LPA::Lpd::DownloadInstance::JsonCheckFieldAndOptionallyThrow(web::json::value &,ushort const *,bool (web::json::value::*)(void),bool)
0x1800afc86  test    al, al
0x1800afc88  jz      loc_1800AFF34
0x1800afc8e  mov     rcx, rbx; this
0x1800afc91  call    ?as_object@value@json@web@@QEBAAEBVobject@23@XZ; web::json::value::as_object(void)
0x1800afc96  mov     rbx, rax
0x1800afc99  lea     rdx, aFunctionexecut; "functionExecutionStatus"
0x1800afca0  lea     rcx, [rbp+80h+var_C0]
0x1800afca4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800afca9  nop
0x1800afcaa  lea     rdx, [rbp+80h+var_C0]
0x1800afcae  mov     rcx, rbx
0x1800afcb1  call    ?at@object@json@web@@QEAAAEAVvalue@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::object::at(std::wstring const &)
0x1800afcb6  mov     [rsp+180h+var_120], rax
0x1800afcbb  lea     rcx, [rbp+80h+var_C0]
0x1800afcbf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800afcc4  xor     r9d, r9d
0x1800afcc7  lea     r8, ?is_string@value@json@web@@QEBA_NXZ; web::json::value::is_string(void)
0x1800afcce  lea     rdx, aStatus; "status"
0x1800afcd5  mov     rbx, [rsp+180h+var_120]
0x1800afcda  mov     rcx, rbx
0x1800afcdd  call    ?JsonCheckFieldAndOptionallyThrow@DownloadInstance@Lpd@LPA@@CA_NAEAVvalue@json@web@@PEBGP8456@EBA_NXZ_N@Z; LPA::Lpd::DownloadInstance::JsonCheckFieldAndOptionallyThrow(web::json::value &,ushort const *,bool (web::json::value::*)(void),bool)
0x1800afce2  test    al, al
0x1800afce4  jz      loc_1800AFDAC
0x1800afcea  mov     rcx, rbx; this
0x1800afced  call    ?as_object@value@json@web@@QEBAAEBVobject@23@XZ; web::json::value::as_object(void)
0x1800afcf2  mov     rbx, rax
0x1800afcf5  lea     rdx, aStatus; "status"
0x1800afcfc  lea     rcx, [rbp+80h+var_E0]
0x1800afd00  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800afd05  nop
0x1800afd06  lea     rdx, [rbp+80h+var_E0]
0x1800afd0a  mov     rcx, rbx
0x1800afd0d  call    ?at@object@json@web@@QEAAAEAVvalue@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::object::at(std::wstring const &)
0x1800afd12  mov     rbx, rax
0x1800afd15  lea     rcx, [rbp+80h+var_E0]
0x1800afd19  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800afd1e  mov     rcx, rbx
0x1800afd21  call    ?as_string@value@json@web@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::json::value::as_string(void)
0x1800afd26  mov     r15, rax
0x1800afd29  mov     rcx, rax
0x1800afd2c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800afd31  lea     rdx, aExecutedSucces; "Executed-Success"
0x1800afd38  mov     rcx, rax
0x1800afd3b  call    cs:__imp__o__wcsicmp
0x1800afd41  test    eax, eax
0x1800afd43  jz      short loc_1800AFDA9
0x1800afd45  mov     rcx, r15
0x1800afd48  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800afd4d  lea     rdx, aExecutedWithwa; "Executed-WithWarning"
0x1800afd54  mov     rcx, rax
0x1800afd57  call    cs:__imp__o__wcsicmp
0x1800afd5d  test    eax, eax
0x1800afd5f  jz      short loc_1800AFDA9
0x1800afd61  mov     rcx, r15
0x1800afd64  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800afd69  lea     rdx, aFailed_0; "Failed"
0x1800afd70  mov     rcx, rax
0x1800afd73  call    cs:__imp__o__wcsicmp
0x1800afd79  test    eax, eax
0x1800afd7b  jnz     short loc_1800AFD85
0x1800afd7d  mov     r12d, 80004005h
0x1800afd83  jmp     short loc_1800AFDAC
0x1800afd85  mov     rcx, r15
0x1800afd88  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800afd8d  lea     rdx, aExpired; "Expired"
0x1800afd94  mov     rcx, rax
0x1800afd97  call    cs:__imp__o__wcsicmp
0x1800afd9d  test    eax, eax
0x1800afd9f  jnz     short loc_1800AFDAC
0x1800afda1  mov     r12d, 800705B4h
0x1800afda7  jmp     short loc_1800AFDAC
0x1800afda9  xor     r12d, r12d
0x1800afdac  xor     r9d, r9d
0x1800afdaf  lea     r8, ?is_object@value@json@web@@QEBA_NXZ; web::json::value::is_object(void)
0x1800afdb6  lea     rdx, aStatuscodedata; "statusCodeData"
0x1800afdbd  mov     rcx, [rsp+180h+var_120]
0x1800afdc2  call    ?JsonCheckFieldAndOptionallyThrow@DownloadInstance@Lpd@LPA@@CA_NAEAVvalue@json@web@@PEBGP8456@EBA_NXZ_N@Z; LPA::Lpd::DownloadInstance::JsonCheckFieldAndOptionallyThrow(web::json::value &,ushort const *,bool (web::json::value::*)(void),bool)
0x1800afdc7  test    al, al
0x1800afdc9  jz      loc_1800AFF34
0x1800afdcf  lea     rdx, aStatuscodedata; "statusCodeData"
0x1800afdd6  lea     rcx, [rbp+80h+var_E0]
0x1800afdda  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800afddf  nop
0x1800afde0  lea     rdx, [rbp+80h+var_E0]
0x1800afde4  mov     rcx, [rsp+180h+var_120]
0x1800afde9  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x1800afdee  mov     rbx, rax
0x1800afdf1  lea     rcx, [rbp+80h+var_E0]
0x1800afdf5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800afdfa  xor     r9d, r9d
0x1800afdfd  lea     r8, ?is_string@value@json@web@@QEBA_NXZ; web::json::value::is_string(void)
0x1800afe04  lea     rdx, aSubjectcode; "subjectCode"
0x1800afe0b  mov     rcx, rbx
0x1800afe0e  call    ?JsonCheckFieldAndOptionallyThrow@DownloadInstance@Lpd@LPA@@CA_NAEAVvalue@json@web@@PEBGP8456@EBA_NXZ_N@Z; LPA::Lpd::DownloadInstance::JsonCheckFieldAndOptionallyThrow(web::json::value &,ushort const *,bool (web::json::value::*)(void),bool)
0x1800afe13  test    al, al
0x1800afe15  jz      short loc_1800AFE48
0x1800afe17  lea     rdx, aSubjectcode; "subjectCode"
0x1800afe1e  lea     rcx, [rbp+80h+var_C0]
0x1800afe22  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800afe27  nop
0x1800afe28  lea     rdx, [rbp+80h+var_C0]
0x1800afe2c  mov     rcx, rbx
0x1800afe2f  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x1800afe34  mov     rcx, rax
0x1800afe37  call    ?as_string@value@json@web@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::json::value::as_string(void)
0x1800afe3c  mov     rsi, rax
0x1800afe3f  lea     rcx, [rbp+80h+var_C0]
0x1800afe43  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800afe48  xor     r9d, r9d
0x1800afe4b  lea     r8, ?is_string@value@json@web@@QEBA_NXZ; web::json::value::is_string(void)
0x1800afe52  lea     rdx, aReasoncode; "reasonCode"
0x1800afe59  mov     rcx, rbx
0x1800afe5c  call    ?JsonCheckFieldAndOptionallyThrow@DownloadInstance@Lpd@LPA@@CA_NAEAVvalue@json@web@@PEBGP8456@EBA_NXZ_N@Z; LPA::Lpd::DownloadInstance::JsonCheckFieldAndOptionallyThrow(web::json::value &,ushort const *,bool (web::json::value::*)(void),bool)
0x1800afe61  test    al, al
0x1800afe63  jz      short loc_1800AFE96
0x1800afe65  lea     rdx, aReasoncode; "reasonCode"
0x1800afe6c  lea     rcx, [rbp+80h+var_A0]
0x1800afe70  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800afe75  nop
0x1800afe76  lea     rdx, [rbp+80h+var_A0]
0x1800afe7a  mov     rcx, rbx
0x1800afe7d  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x1800afe82  mov     rcx, rax
0x1800afe85  call    ?as_string@value@json@web@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::json::value::as_string(void)
0x1800afe8a  mov     rdi, rax
0x1800afe8d  lea     rcx, [rbp+80h+var_A0]
0x1800afe91  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800afe96  xor     r9d, r9d
0x1800afe99  lea     r8, ?is_string@value@json@web@@QEBA_NXZ; web::json::value::is_string(void)
0x1800afea0  lea     rdx, aSubjectidentif; "subjectIdentifier"
0x1800afea7  mov     rcx, rbx
0x1800afeaa  call    ?JsonCheckFieldAndOptionallyThrow@DownloadInstance@Lpd@LPA@@CA_NAEAVvalue@json@web@@PEBGP8456@EBA_NXZ_N@Z; LPA::Lpd::DownloadInstance::JsonCheckFieldAndOptionallyThrow(web::json::value &,ushort const *,bool (web::json::value::*)(void),bool)
0x1800afeaf  test    al, al
0x1800afeb1  jz      short loc_1800AFEE6
0x1800afeb3  lea     rdx, aSubjectidentif; "subjectIdentifier"
0x1800afeba  lea     rcx, [rbp+80h+var_80]
0x1800afebe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800afec3  nop
0x1800afec4  lea     rdx, [rbp+80h+var_80]
0x1800afec8  mov     rcx, rbx
0x1800afecb  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x1800afed0  mov     rcx, rax
0x1800afed3  call    ?as_string@value@json@web@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::json::value::as_string(void)
0x1800afed8  mov     [rsp+180h+var_118], rax
0x1800afedd  lea     rcx, [rbp+80h+var_80]
0x1800afee1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800afee6  xor     r9d, r9d
0x1800afee9  lea     r8, ?is_string@value@json@web@@QEBA_NXZ; web::json::value::is_string(void)
0x1800afef0  lea     rdx, aMessage; "message"
0x1800afef7  mov     rcx, rbx
0x1800afefa  call    ?JsonCheckFieldAndOptionallyThrow@DownloadInstance@Lpd@LPA@@CA_NAEAVvalue@json@web@@PEBGP8456@EBA_NXZ_N@Z; LPA::Lpd::DownloadInstance::JsonCheckFieldAndOptionallyThrow(web::json::value &,ushort const *,bool (web::json::value::*)(void),bool)
0x1800afeff  test    al, al
0x1800aff01  jz      short loc_1800AFF34
0x1800aff03  lea     rdx, aMessage; "message"
0x1800aff0a  lea     rcx, [rbp+80h+var_60]
0x1800aff0e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800aff13  nop
0x1800aff14  lea     rdx, [rbp+80h+var_60]
0x1800aff18  mov     rcx, rbx
0x1800aff1b  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x1800aff20  mov     rcx, rax
0x1800aff23  call    ?as_string@value@json@web@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::json::value::as_string(void)
0x1800aff28  mov     r13, rax
0x1800aff2b  lea     rcx, [rbp+80h+var_60]
0x1800aff2f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aff34  mov     dword ptr [r14], 0Dh
0x1800aff3b  test    rsi, rsi
0x1800aff3e  jz      loc_1800B00D8
0x1800aff44  test    rdi, rdi
0x1800aff47  jz      loc_1800B00D8
0x1800aff4d  lea     rdx, a827; "8.2.7"
0x1800aff54  mov     rcx, rsi
0x1800aff57  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800aff5c  test    eax, eax
0x1800aff5e  jnz     short loc_1800AFFC1
0x1800aff60  lea     rdx, a38; "3.8"
0x1800aff67  mov     rcx, rdi
0x1800aff6a  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800aff6f  test    eax, eax
0x1800aff71  jnz     short loc_1800AFF7F
0x1800aff73  mov     dword ptr [r14], 2
0x1800aff7a  jmp     loc_1800B00D8
0x1800aff7f  lea     rdx, a64; "6.4"
0x1800aff86  mov     rcx, rdi
0x1800aff89  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800aff8e  test    eax, eax
0x1800aff90  jnz     short loc_1800AFF9E
0x1800aff92  mov     dword ptr [r14], 4
0x1800aff99  jmp     loc_1800B00D8
0x1800aff9e  lea     rdx, a22; "2.2"
0x1800affa5  mov     rcx, rdi
0x1800affa8  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800affad  test    eax, eax
0x1800affaf  jnz     loc_1800B00D8
0x1800affb5  mov     dword ptr [r14], 3
0x1800affbc  jmp     loc_1800B00D8
0x1800affc1  lea     rdx, a885; "8.8.5"
0x1800affc8  mov     rcx, rsi
0x1800affcb  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800affd0  test    eax, eax
0x1800affd2  jnz     short loc_1800AFFF7
0x1800affd4  lea     rdx, a64; "6.4"
0x1800affdb  mov     rcx, rdi
0x1800affde  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800affe3  test    eax, eax
0x1800affe5  jnz     loc_1800B00D8
0x1800affeb  mov     dword ptr [r14], 17h
0x1800afff2  jmp     loc_1800B00D8
0x1800afff7  lea     rdx, a811; "8.1.1"
0x1800afffe  mov     rcx, rsi
0x1800b0001  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800b0006  test    eax, eax
0x1800b0008  jnz     short loc_1800B002D
0x1800b000a  lea     rdx, a38; "3.8"
0x1800b0011  mov     rcx, rdi
0x1800b0014  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800b0019  test    eax, eax
0x1800b001b  jnz     loc_1800B00D8
0x1800b0021  mov     dword ptr [r14], 0Ah
0x1800b0028  jmp     loc_1800B00D8
0x1800b002d  lea     rdx, a826; "8.2.6"
0x1800b0034  mov     rcx, rsi
0x1800b0037  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800b003c  test    eax, eax
0x1800b003e  jnz     short loc_1800B0060
0x1800b0040  lea     rdx, a38; "3.8"
0x1800b0047  mov     rcx, rdi
0x1800b004a  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800b004f  test    eax, eax
0x1800b0051  jnz     loc_1800B00D8
0x1800b0057  mov     dword ptr [r14], 6
0x1800b005e  jmp     short loc_1800B00D8
0x1800b0060  lea     rdx, a82; "8.2"
0x1800b0067  mov     rcx, rsi
0x1800b006a  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800b006f  test    eax, eax
0x1800b0071  jnz     short loc_1800B00AB
0x1800b0073  lea     rdx, a12; "1.2"
0x1800b007a  mov     rcx, rdi
0x1800b007d  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800b0082  test    eax, eax
0x1800b0084  jnz     short loc_1800B008F
0x1800b0086  mov     dword ptr [r14], 0Ch
0x1800b008d  jmp     short loc_1800B00D8
0x1800b008f  lea     rdx, a37; "3.7"
0x1800b0096  mov     rcx, rdi
0x1800b0099  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800b009e  test    eax, eax
0x1800b00a0  jnz     short loc_1800B00D8
0x1800b00a2  mov     dword ptr [r14], 0Bh
0x1800b00a9  jmp     short loc_1800B00D8
0x1800b00ab  lea     rdx, a825; "8.2.5"
0x1800b00b2  mov     rcx, rsi
0x1800b00b5  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
  ... truncated ...
```
