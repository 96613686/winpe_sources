# TMetabaseMetaXmlFile::GetDefaultValue(TElement const &,ColumnMeta &)

- ea: `0x18001c86c`
- end: `0x18001d297`
- name: `?GetDefaultValue@TMetabaseMetaXmlFile@@AEAAKAEBUTElement@@AEAUColumnMeta@@@Z`
- size: `2603`
- prototype: `unsigned int __fastcall(TMetabaseMetaXmlFile *__hidden this, const struct TElement *, struct ColumnMeta *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019554`

## callees

- `0x180001e88`
- `0x180002bc4`
- `0x180005870`
- `0x180011b38`
- `0x180012734`
- `0x180017ad8`
- `0x18001b188`
- `0x18001bd60`
- `0x18001c814`
- `0x18001c86c`
- `0x18002e0b2`
- `0x18002e0ca`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18001c9d9`
- `msvcrt!swprintf_s` at `0x18001cd00`
- `msvcrt!swprintf_s` at `0x18001c9d9`
- `msvcrt!swprintf_s` at `0x18001cd00`
- `msvcrt!wcscpy_s` at `0x18001d16e`
- `msvcrt!wcscpy_s` at `0x18001d16e`
- `msvcrt!_wtol` at `0x18001c947`
- `msvcrt!_wtol` at `0x18001c947`
- `ole32!CoTaskMemAlloc` at `0x18001caef`
- `ole32!CoTaskMemAlloc` at `0x18001ce19`
- `ole32!CoTaskMemAlloc` at `0x18001d0ce`
- `ole32!CoTaskMemAlloc` at `0x18001d0e8`
- `ole32!CoTaskMemAlloc` at `0x18001caef`
- `ole32!CoTaskMemAlloc` at `0x18001ce19`
- `ole32!CoTaskMemAlloc` at `0x18001d0ce`
- `ole32!CoTaskMemAlloc` at `0x18001d0e8`

## string_xrefs

- `0x18001ca91`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001cabb`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001cb8f`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001cbb6`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001cc64`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001cc8b`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001cdaa`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001cdd1`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001ceba`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001cee1`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001d059`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001d083`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001d263`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001d28a`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001cab4`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x18001cbaf`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x18001cc84`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x18001cdca`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x18001ceda`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x18001d07c`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x18001d283`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
int __fastcall TMetabaseMetaXmlFile::GetDefaultValue(
        TMetabaseMetaXmlFile *this,
        const struct TElement *a2,
        struct ColumnMeta *a3)
{
  const struct TMetabaseMetaXmlFile::TAttr *Attribute; // rax
  const void **v6; // r15
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  __int64 (__fastcall *v14)(TMetabaseMetaXmlFile *, _QWORD); // rbx
  const wchar_t *v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned __int64 v20; // r14
  bool v21; // cc
  __int64 (__fastcall *v22)(TMetabaseMetaXmlFile *, _QWORD); // rax
  unsigned int v23; // eax
  __int64 v24; // rbx
  __int64 v25; // rax
  unsigned int v26; // r14d
  _WORD *v27; // rax
  _WORD *v28; // rbx
  unsigned int v29; // r14d
  unsigned int v30; // eax
  __int64 v31; // rax
  unsigned int v32; // eax
  void *v33; // rbx
  unsigned int v34; // eax
  __int64 (__fastcall *v35)(TMetabaseMetaXmlFile *, void *, _QWORD); // r15
  int v36; // ebx
  __int64 v37; // rbx
  __int64 v38; // rax
  void *v39; // rdi
  _WORD *v40; // rax
  _WORD *v41; // rbx
  int v42; // r14d
  wchar_t **v43; // r8
  wchar_t *i; // rdi
  wchar_t **v45; // r8
  __int64 v46; // rax
  void *v47; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v48; // [rsp+B8h] [rbp-11h]
  _QWORD v49[2]; // [rsp+C0h] [rbp-9h] BYREF
  wchar_t Buffer[4]; // [rsp+D0h] [rbp+7h] BYREF
  __int64 v51; // [rsp+D8h] [rbp+Fh]

  Attribute = TMetabaseMetaXmlFile::GetAttribute(this, a2, (TMetabaseMetaXmlFile *)((char *)this + 392));
  v6 = (const void **)((char *)Attribute + 16);
  if ( !*((_QWORD *)Attribute + 3) )
    return 0;
  v8 = ((*(unsigned int (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 152LL))(
          this,
          *((unsigned int *)a3 + 12)) >> 2)
     & 0xF;
  if ( v8 > 7 )
  {
    v17 = v8 - 8;
    if ( v17 )
    {
      v18 = v17 - 1;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( !v19 )
        {
LABEL_22:
          v26 = *(_DWORD *)v6;
          if ( (*(_DWORD *)v6 & 1) != 0 )
          {
            v27 = CoTaskMemAlloc(saturated_mul(v26 + 1, 2u));
            v28 = v27;
            v47 = v27;
            if ( !v27 )
            {
              v51 = 0;
              CErrorInterceptor::Init(
                Buffer,
                0,
                *((_QWORD *)this + 325),
                2149648481LL,
                3,
                -1073606454,
                &word_180034198,
                &word_180034198,
                &word_180034198,
                &word_180034198,
                0,
                0,
                0,
                -1,
                -1,
                0,
                0);
              CErrorInterceptor::WriteToLog(
                (CErrorInterceptor *)Buffer,
                L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
                812,
                0x400000);
              CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)Buffer);
              ThrowException(
                L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
                L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
                0x32Cu,
                0);
            }
            memcpy_0(v27, v6[1], 2LL * *(unsigned int *)v6);
            v28[*(unsigned int *)v6] = 0;
            v51 = 0;
            CErrorInterceptor::Init(
              Buffer,
              0,
              *((_QWORD *)this + 325),
              2149648481LL,
              3,
              -2147348290,
              v28,
              &word_180034198,
              &word_180034198,
              &word_180034198,
              0,
              0,
              0,
              -1,
              -1,
              0,
              0);
            CErrorInterceptor::WriteToLog(
              (CErrorInterceptor *)Buffer,
              L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
              816,
              0x400000);
            CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)Buffer);
            ThrowException(
              L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
              L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
              0x330u,
              0);
          }
          v29 = v26 >> 1;
          if ( ((*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 152LL))(
                  this,
                  *((unsigned int *)a3 + 6))
              & 0x100000) != 0
            && v29 > (*(unsigned int (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 152LL))(
                       this,
                       *((unsigned int *)a3 + 5)) )
          {
            v30 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 152LL))(
                    this,
                    *((unsigned int *)a3 + 5));
            swprintf_s(Buffer, 0xCu, L"%d", v30);
            v31 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 144LL))(
                    this,
                    *((unsigned int *)a3 + 2));
            v48 = 0;
            CErrorInterceptor::Init(
              &v47,
              0,
              *((_QWORD *)this + 325),
              2149648481LL,
              3,
              -1073606451,
              Buffer,
              v31,
              &word_180034198,
              &word_180034198,
              0,
              0,
              0,
              -1,
              -1,
              0,
              0);
            CErrorInterceptor::WriteToLog(
              (CErrorInterceptor *)&v47,
              L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
              824,
              0x400000);
            CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v47);
            ThrowException(
              L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
              L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
              0x338u,
              0);
          }
          v49[0] = 0;
          if ( ((*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 152LL))(
                  this,
                  *((unsigned int *)a3 + 6))
              & 0x100000) != 0 )
            v32 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 152LL))(
                    this,
                    *((unsigned int *)a3 + 5));
          else
            v32 = v29;
          v33 = CoTaskMemAlloc(v32);
          v49[0] = v33;
          if ( !v33 )
          {
            v48 = 0;
            CErrorInterceptor::Init(
              &v47,
              0,
              *((_QWORD *)this + 325),
              2149648481LL,
              3,
              -1073606454,
              &word_180034198,
              &word_180034198,
              &word_180034198,
              &word_180034198,
              0,
              0,
              0,
              -1,
              -1,
              0,
              0);
            CErrorInterceptor::WriteToLog(
              (CErrorInterceptor *)&v47,
              L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
              831,
              0x400000);
            CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v47);
            ThrowException(
              L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
              L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
              0x33Fu,
              0);
          }
          if ( ((*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 152LL))(
                  this,
                  *((unsigned int *)a3 + 6))
              & 0x100000) != 0 )
            v34 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 152LL))(
                    this,
                    *((unsigned int *)a3 + 5));
          else
            v34 = v29;
          memset_0(v33, 0, v34);
          TMetabaseMetaXmlFile::ConvertWideCharsToBytes(
            this,
            (const unsigned __int16 *)v6[1],
            (unsigned __int8 *)v33,
            v29);
          v35 = **(__int64 (__fastcall ***)(TMetabaseMetaXmlFile *, void *, _QWORD))this;
          if ( ((*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 152LL))(
                  this,
                  *((unsigned int *)a3 + 6))
              & 0x100000) != 0 )
            v29 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 152LL))(
                    this,
                    *((unsigned int *)a3 + 5));
          v36 = v35(this, v33, v29);
          TSmartPointerArray<bool>::~TSmartPointerArray<bool>(v49);
          return v36;
        }
        if ( v19 - 1 > 1 )
          return 0;
      }
    }
LABEL_20:
    LODWORD(v49[0]) = *(_DWORD *)v6;
    v20 = (unsigned int)(LODWORD(v49[0]) + 2);
    v21 = 2 * v20 <= (*(unsigned int (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 152LL))(
                       this,
                       *((unsigned int *)a3 + 5));
    v22 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 152LL);
    if ( !v21 )
    {
      v23 = v22(this, *((unsigned int *)a3 + 5));
      swprintf_s(Buffer, 0xCu, L"%d", v23);
      v24 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 144LL))(
              this,
              *(unsigned int *)a3);
      v25 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 144LL))(
              this,
              *((unsigned int *)a3 + 2));
      v48 = 0;
      CErrorInterceptor::Init(
        &v47,
        0,
        *((_QWORD *)this + 325),
        2149648481LL,
        3,
        -1073606451,
        Buffer,
        v25,
        0,
        0,
        0,
        v24,
        0,
        -1,
        -1,
        0,
        0);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)&v47,
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        750,
        0x400000);
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v47);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
        0x2EFu,
        0);
    }
    if ( (v22(this, *((unsigned int *)a3 + 6)) & 0x100000) != 0 )
    {
      v37 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 144LL))(
              this,
              *(unsigned int *)a3);
      v38 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 144LL))(
              this,
              *((unsigned int *)a3 + 2));
      v48 = 0;
      CErrorInterceptor::Init(
        &v47,
        0,
        *((_QWORD *)this + 325),
        2149648481LL,
        3,
        -1073606450,
        v38,
        0,
        0,
        0,
        0,
        v37,
        0,
        -1,
        -1,
        0,
        0);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)&v47,
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        762,
        0x400000);
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v47);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
        0x2FBu,
        0);
    }
    if ( !LODWORD(v49[0]) )
    {
      LODWORD(v49[0]) = 0;
      return (**(__int64 (__fastcall ***)(TMetabaseMetaXmlFile *, _QWORD *, __int64))this)(this, v49, 4);
    }
    v39 = CoTaskMemAlloc(saturated_mul((unsigned int)(LODWORD(v49[0]) + 1), 2u));
    v47 = v39;
    v40 = CoTaskMemAlloc(saturated_mul(v20, 2u));
    v41 = v40;
    *(_QWORD *)Buffer = v40;
    v42 = 0;
    if ( !v39 || !v40 )
    {
      v49[1] = 0;
      CErrorInterceptor::Init(
        v49,
        0,
        *((_QWORD *)this + 325),
        2149648481LL,
        3,
        -1073606454,
        &word_180034198,
        &word_180034198,
        &word_180034198,
        &word_180034198,
        0,
        0,
        0,
        -1,
        -1,
        0,
        0);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v49,
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        777,
        0x400000);
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v49);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
        0x309u,
        0);
    }
    memcpy_0(v39, v6[1], 2LL * *(unsigned int *)v6);
    *((_WORD *)v39 + *(unsigned int *)v6) = 0;
    *v41 = 0;
    for ( i = wcstok_mvcrt_legacy_two_parameter_form((wchar_t *)v39, L"|\r\n", v43);
          i;
          i = wcstok_mvcrt_legacy_two_parameter_form(0, L"|\r\n", v45) )
    {
      while ( *i == 32 || *i == 9 )
        ++i;
      if ( !*i )
        break;
      wcscpy_s(&v41[v42], (unsigned int)(LODWORD(v49[0]) - v42 + 2), i);
      v46 = -1;
      do
        ++v46;
      while ( i[v46] );
      v42 += v46 + 1;
    }
    v41[v42] = 0;
    v36 = (**(__int64 (__fastcall ***)(TMetabaseMetaXmlFile *, _WORD *, __int64))this)(
            this,
            v41,
            2LL * (unsigned int)(v42 + 1));
    TSmartPointerArray<bool>::~TSmartPointerArray<bool>(Buffer);
    TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v47);
    return v36;
  }
  if ( v8 != 7 )
  {
    v9 = v8 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( !v10 )
        return TMetabaseMetaXmlFile::AddStringToHeap(this, (const struct TMetabaseMetaXmlFile::TSizedString *)v6);
      v11 = v10 - 1;
      if ( !v11 )
        return TMetabaseMetaXmlFile::AddStringToHeap(this, (const struct TMetabaseMetaXmlFile::TSizedString *)v6);
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          if ( v13 == 1 )
            goto LABEL_11;
          return 0;
        }
        goto LABEL_22;
      }
      goto LABEL_20;
    }
  }
LABEL_11:
  v14 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL);
  v15 = (const wchar_t *)v6[1];
  if ( v15 )
    v16 = _wtol(v15);
  else
    v16 = 0;
  return v14(this, v16);
}

```

## disassembly

```asm
0x18001c86c  mov     [rsp-8+arg_18], rbx
0x18001c871  push    rbp
0x18001c872  push    rsi
0x18001c873  push    rdi
0x18001c874  push    r12
0x18001c876  push    r13
0x18001c878  push    r14
0x18001c87a  push    r15
0x18001c87c  lea     rbp, [rsp-27h]
0x18001c881  sub     rsp, 0F0h
0x18001c888  mov     rax, cs:__security_cookie
0x18001c88f  xor     rax, rsp
0x18001c892  mov     [rbp+57h+var_38], rax
0x18001c896  mov     rdi, r8
0x18001c899  mov     rsi, rcx
0x18001c89c  lea     r8, [rcx+188h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001c8a3  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001c8a8  lea     r15, [rax+10h]
0x18001c8ac  xor     r13d, r13d
0x18001c8af  cmp     [r15+8], r13
0x18001c8b3  jnz     short loc_18001C8DE
0x18001c8b5  xor     eax, eax
0x18001c8b7  mov     rcx, [rbp+57h+var_38]
0x18001c8bb  xor     rcx, rsp; StackCookie
0x18001c8be  call    __security_check_cookie
0x18001c8c3  mov     rbx, [rsp+120h+arg_18]
0x18001c8cb  add     rsp, 0F0h
0x18001c8d2  pop     r15
0x18001c8d4  pop     r14
0x18001c8d6  pop     r13
0x18001c8d8  pop     r12
0x18001c8da  pop     rdi
0x18001c8db  pop     rsi
0x18001c8dc  pop     rbp
0x18001c8dd  retn
0x18001c8de  mov     rax, [rsi]
0x18001c8e1  mov     edx, [rdi+30h]
0x18001c8e4  mov     rcx, rsi
0x18001c8e7  mov     rax, [rax+98h]
0x18001c8ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8f3  shr     eax, 2
0x18001c8f6  and     eax, 0Fh
0x18001c8f9  cmp     eax, 7
0x18001c8fc  ja      short loc_18001C95F
0x18001c8fe  jz      short loc_18001C922
0x18001c900  sub     eax, 1
0x18001c903  jz      short loc_18001C922
0x18001c905  sub     eax, 1
0x18001c908  jz      short loc_18001C937
0x18001c90a  sub     eax, 1
0x18001c90d  jz      short loc_18001C937
0x18001c90f  sub     eax, 1
0x18001c912  jz      short loc_18001C980
0x18001c914  sub     eax, 1
0x18001c917  jz      loc_18001CAC8
0x18001c91d  cmp     eax, 1
0x18001c920  jnz     short loc_18001C8B5
0x18001c922  mov     rax, [rsi]
0x18001c925  mov     rbx, [rax+10h]
0x18001c929  mov     rcx, [r15+8]; String
0x18001c92d  test    rcx, rcx
0x18001c930  jnz     short loc_18001C947
0x18001c932  mov     eax, r13d
0x18001c935  jmp     short loc_18001C94D
0x18001c937  mov     rdx, r15; struct TMetabaseMetaXmlFile::TSizedString *
0x18001c93a  mov     rcx, rsi; this
0x18001c93d  call    ?AddStringToHeap@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::AddStringToHeap(TMetabaseMetaXmlFile::TSizedString const &)
0x18001c942  jmp     loc_18001C8B7
0x18001c947  call    cs:__imp__wtol
0x18001c94d  mov     edx, eax
0x18001c94f  mov     rcx, rsi
0x18001c952  mov     rax, rbx
0x18001c955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c95a  jmp     loc_18001C8B7
0x18001c95f  sub     eax, 8
0x18001c962  jz      short loc_18001C980
0x18001c964  sub     eax, 1
0x18001c967  jz      short loc_18001C980
0x18001c969  sub     eax, 1
0x18001c96c  jz      loc_18001CAC8
0x18001c972  sub     eax, 1
0x18001c975  jz      short loc_18001C980
0x18001c977  cmp     eax, 1
0x18001c97a  jnz     loc_18001C8B5
0x18001c980  mov     ebx, [r15]
0x18001c983  mov     dword ptr [rbp+57h+var_60], ebx
0x18001c986  mov     rax, [rsi]
0x18001c989  mov     edx, [rdi+14h]
0x18001c98c  mov     rcx, rsi
0x18001c98f  mov     rax, [rax+98h]
0x18001c996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c99b  mov     ecx, eax
0x18001c99d  lea     r14d, [rbx+2]
0x18001c9a1  mov     rax, [rsi]
0x18001c9a4  mov     r8, [rax+98h]
0x18001c9ab  lea     rax, [r14+r14]
0x18001c9af  cmp     rax, rcx
0x18001c9b2  mov     rcx, rsi
0x18001c9b5  mov     rax, r8
0x18001c9b8  jbe     loc_18001CF99
0x18001c9be  mov     edx, [rdi+14h]
0x18001c9c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9c6  mov     r9d, eax
0x18001c9c9  lea     r8, aD; "%d"
0x18001c9d0  mov     edx, 0Ch; BufferCount
0x18001c9d5  lea     rcx, [rbp+57h+Buffer]; Buffer
0x18001c9d9  call    cs:__imp_swprintf_s
0x18001c9df  mov     rax, [rsi]
0x18001c9e2  mov     edx, [rdi]
0x18001c9e4  mov     rcx, rsi
0x18001c9e7  mov     rax, [rax+90h]
0x18001c9ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9f3  mov     rbx, rax
0x18001c9f6  mov     rcx, [rsi]
0x18001c9f9  mov     rax, [rcx+90h]
0x18001ca00  mov     edx, [rdi+8]
0x18001ca03  mov     rcx, rsi
0x18001ca06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca0b  mov     [rbp+57h+var_68], r13
0x18001ca0f  or      ecx, 0FFFFFFFFh
0x18001ca12  mov     [rsp+120h+var_80], ecx
0x18001ca19  mov     [rsp+120h+var_88], ecx
0x18001ca20  mov     [rsp+120h+var_A0], r13d
0x18001ca28  mov     [rsp+120h+var_A8], r13
0x18001ca2d  mov     [rsp+120h+var_B0], ecx
0x18001ca31  mov     [rsp+120h+var_B8], ecx
0x18001ca35  mov     [rsp+120h+var_C0], r13d
0x18001ca3a  mov     [rsp+120h+var_C8], rbx
0x18001ca3f  mov     [rsp+120h+var_D0], r13d
0x18001ca44  mov     [rsp+120h+var_D8], r13
0x18001ca49  mov     [rsp+120h+var_E0], r13
0x18001ca4e  mov     [rsp+120h+var_E8], rax
0x18001ca53  lea     rax, [rbp+57h+Buffer]
0x18001ca57  mov     [rsp+120h+var_F0], rax
0x18001ca5c  mov     [rsp+120h+var_F8], 0C00210CDh
0x18001ca64  mov     [rsp+120h+var_100], 3
0x18001ca6c  mov     r9d, 80210861h
0x18001ca72  mov     r8, [rsi+0A28h]
0x18001ca79  xor     edx, edx
0x18001ca7b  lea     rcx, [rbp+57h+var_70]
0x18001ca7f  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001ca84  nop
0x18001ca85  mov     r9d, 400000h; unsigned int
0x18001ca8b  mov     r8d, 2EEh; unsigned int
0x18001ca91  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001ca98  lea     rcx, [rbp+57h+var_70]; this
0x18001ca9c  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001caa1  nop
0x18001caa2  lea     rcx, [rbp+57h+var_70]; this
0x18001caa6  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18001caab  xor     r9d, r9d; unsigned int
0x18001caae  mov     r8d, 2EFh; unsigned int
0x18001cab4  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x18001cabb  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001cac2  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001cac8  mov     r14d, [r15]
0x18001cacb  test    r14b, 1
0x18001cacf  jz      loc_18001CC98
0x18001cad5  lea     ecx, [r14+1]
0x18001cad9  mov     eax, 2
0x18001cade  mul     rcx
0x18001cae1  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18001cae8  cmovb   rax, r13
0x18001caec  mov     rcx, rax; cb
0x18001caef  call    cs:__imp_CoTaskMemAlloc
0x18001caf5  mov     rbx, rax
0x18001caf8  mov     [rbp+57h+var_70], rax
0x18001cafc  xor     edi, edi
0x18001cafe  test    rax, rax
0x18001cb01  jnz     loc_18001CBC3
0x18001cb07  mov     [rbp+57h+var_48], rdi
0x18001cb0b  or      ecx, 0FFFFFFFFh
0x18001cb0e  mov     [rsp+120h+var_80], ecx
0x18001cb15  mov     [rsp+120h+var_88], ecx
0x18001cb1c  mov     [rsp+120h+var_A0], edi
0x18001cb23  mov     [rsp+120h+var_A8], rdi
0x18001cb28  mov     [rsp+120h+var_B0], ecx
0x18001cb2c  mov     [rsp+120h+var_B8], ecx
0x18001cb30  mov     [rsp+120h+var_C0], edi
0x18001cb34  mov     [rsp+120h+var_C8], rdi
0x18001cb39  mov     [rsp+120h+var_D0], edi
0x18001cb3d  lea     rcx, word_180034198
0x18001cb44  mov     [rsp+120h+var_D8], rcx
0x18001cb49  mov     [rsp+120h+var_E0], rcx
0x18001cb4e  mov     [rsp+120h+var_E8], rcx
0x18001cb53  mov     [rsp+120h+var_F0], rcx
0x18001cb58  mov     [rsp+120h+var_F8], 0C00210CAh
0x18001cb60  mov     [rsp+120h+var_100], 3
0x18001cb68  mov     r9d, 80210861h
0x18001cb6e  mov     r8, [rsi+0A28h]
0x18001cb75  xor     edx, edx
0x18001cb77  lea     rcx, [rbp+57h+Buffer]
0x18001cb7b  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001cb80  nop
0x18001cb81  mov     ebx, 32Ch
0x18001cb86  mov     r9d, 400000h; unsigned int
0x18001cb8c  mov     r8d, ebx; unsigned int
0x18001cb8f  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001cb96  lea     rcx, [rbp+57h+Buffer]; this
0x18001cb9a  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001cb9f  nop
0x18001cba0  lea     rcx, [rbp+57h+Buffer]; this
0x18001cba4  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18001cba9  xor     r9d, r9d; unsigned int
0x18001cbac  mov     r8d, ebx; unsigned int
0x18001cbaf  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x18001cbb6  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001cbbd  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001cbc3  mov     r8d, [r15]
0x18001cbc6  add     r8, r8; Size
0x18001cbc9  mov     rdx, [r15+8]; Src
0x18001cbcd  mov     rcx, rbx; void *
0x18001cbd0  call    memcpy_0
0x18001cbd5  mov     ecx, [r15]
0x18001cbd8  mov     [rbx+rcx*2], di
0x18001cbdc  mov     [rbp+57h+var_48], rdi
0x18001cbe0  or      ecx, 0FFFFFFFFh
0x18001cbe3  mov     [rsp+120h+var_80], ecx
0x18001cbea  mov     [rsp+120h+var_88], ecx
0x18001cbf1  mov     [rsp+120h+var_A0], edi
0x18001cbf8  mov     [rsp+120h+var_A8], rdi
0x18001cbfd  mov     [rsp+120h+var_B0], ecx
0x18001cc01  mov     [rsp+120h+var_B8], ecx
0x18001cc05  mov     [rsp+120h+var_C0], edi
0x18001cc09  mov     [rsp+120h+var_C8], rdi
0x18001cc0e  mov     [rsp+120h+var_D0], edi
0x18001cc12  lea     rcx, word_180034198
0x18001cc19  mov     [rsp+120h+var_D8], rcx
0x18001cc1e  mov     [rsp+120h+var_E0], rcx
0x18001cc23  mov     [rsp+120h+var_E8], rcx
0x18001cc28  mov     [rsp+120h+var_F0], rbx
0x18001cc2d  mov     [rsp+120h+var_F8], 800210BEh
0x18001cc35  mov     [rsp+120h+var_100], 3
0x18001cc3d  mov     r9d, 80210861h
0x18001cc43  mov     r8, [rsi+0A28h]
0x18001cc4a  xor     edx, edx
0x18001cc4c  lea     rcx, [rbp+57h+Buffer]
0x18001cc50  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001cc55  nop
0x18001cc56  mov     ebx, 330h
0x18001cc5b  mov     r9d, 400000h; unsigned int
0x18001cc61  mov     r8d, ebx; unsigned int
0x18001cc64  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001cc6b  lea     rcx, [rbp+57h+Buffer]; this
0x18001cc6f  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001cc74  nop
0x18001cc75  lea     rcx, [rbp+57h+Buffer]; this
0x18001cc79  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18001cc7e  xor     r9d, r9d; unsigned int
0x18001cc81  mov     r8d, ebx; unsigned int
0x18001cc84  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x18001cc8b  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001cc92  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001cc98  shr     r14d, 1
0x18001cc9b  mov     rax, [rsi]
0x18001cc9e  mov     edx, [rdi+18h]
0x18001cca1  mov     rcx, rsi
0x18001cca4  mov     rax, [rax+98h]
0x18001ccab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccb0  bt      eax, 14h
0x18001ccb4  jnb     loc_18001CDDE
0x18001ccba  mov     rax, [rsi]
0x18001ccbd  mov     edx, [rdi+14h]
0x18001ccc0  mov     rcx, rsi
0x18001ccc3  mov     rax, [rax+98h]
0x18001ccca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cccf  cmp     r14d, eax
0x18001ccd2  jbe     loc_18001CDDE
0x18001ccd8  mov     rax, [rsi]
0x18001ccdb  mov     edx, [rdi+14h]
0x18001ccde  mov     rcx, rsi
0x18001cce1  mov     rax, [rax+98h]
0x18001cce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cced  mov     r9d, eax
0x18001ccf0  lea     r8, aD; "%d"
0x18001ccf7  mov     edx, 0Ch; BufferCount
0x18001ccfc  lea     rcx, [rbp+57h+Buffer]; Buffer
0x18001cd00  call    cs:__imp_swprintf_s
0x18001cd06  mov     rax, [rsi]
0x18001cd09  mov     edx, [rdi+8]
0x18001cd0c  mov     rcx, rsi
0x18001cd0f  mov     rax, [rax+90h]
0x18001cd16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd1b  mov     [rbp+57h+var_68], r13
0x18001cd1f  or      ecx, 0FFFFFFFFh
0x18001cd22  mov     [rsp+120h+var_80], ecx
0x18001cd29  mov     [rsp+120h+var_88], ecx
0x18001cd30  mov     [rsp+120h+var_A0], r13d
0x18001cd38  mov     [rsp+120h+var_A8], r13
0x18001cd3d  mov     [rsp+120h+var_B0], ecx
0x18001cd41  mov     [rsp+120h+var_B8], ecx
0x18001cd45  mov     [rsp+120h+var_C0], r13d
0x18001cd4a  mov     [rsp+120h+var_C8], r13
0x18001cd4f  mov     [rsp+120h+var_D0], r13d
0x18001cd54  lea     rcx, word_180034198
0x18001cd5b  mov     [rsp+120h+var_D8], rcx
0x18001cd60  mov     [rsp+120h+var_E0], rcx
0x18001cd65  mov     [rsp+120h+var_E8], rax
0x18001cd6a  lea     rax, [rbp+57h+Buffer]
0x18001cd6e  mov     [rsp+120h+var_F0], rax
  ... truncated ...
```
