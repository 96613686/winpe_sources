# TMetabaseMetaXmlFile::AddColumnMetaViaReferenceToHeap(TElement const &)

- ea: `0x1800199c8`
- end: `0x180019f93`
- name: `?AddColumnMetaViaReferenceToHeap@TMetabaseMetaXmlFile@@AEAAXAEBUTElement@@@Z`
- size: `1483`
- prototype: `void __fastcall(TMetabaseMetaXmlFile *__hidden this, const struct TElement *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c240`

## callees

- `0x180001b78`
- `0x180001e88`
- `0x180002bc4`
- `0x180011b38`
- `0x180012734`
- `0x180017ad8`
- `0x180019128`
- `0x1800199c8`
- `0x18001bc88`
- `0x18001c814`
- `0x18002e0b2`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180019a4a`
- `msvcrt!wcsncpy_s` at `0x180019b1d`
- `msvcrt!wcsncpy_s` at `0x180019a4a`
- `msvcrt!wcsncpy_s` at `0x180019b1d`

## string_xrefs

- `0x180019cb4`: `IIsConfigObject`
- `0x180019ade`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180019bca`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180019bf1`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180019cfc`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180019d23`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180019f59`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180019f80`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180019bea`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x180019d1c`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x180019f79`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TMetabaseMetaXmlFile::AddColumnMetaViaReferenceToHeap(
        TMetabaseMetaXmlFile *this,
        const struct TElement *a2)
{
  const struct TMetabaseMetaXmlFile::TAttr *Attribute; // r15
  const wchar_t *v5; // r8
  __int64 v6; // rbx
  wchar_t **v7; // r8
  wchar_t *v8; // r12
  wchar_t **v9; // r8
  wchar_t *v10; // rax
  char v11; // si
  __int64 v12; // r12
  __int64 v13; // r9
  unsigned int v14; // ebx
  __int64 v15; // r9
  unsigned int v16; // r15d
  unsigned int i; // ebx
  __int64 v18; // rbx
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // [rsp+88h] [rbp-A8h]
  __int64 v22; // [rsp+90h] [rbp-A0h]
  _BYTE v23[8]; // [rsp+B0h] [rbp-80h] BYREF
  __int64 v24; // [rsp+B8h] [rbp-78h]
  wchar_t String[268]; // [rsp+C0h] [rbp-70h] BYREF
  int v26; // [rsp+2D8h] [rbp+1A8h]
  int v27; // [rsp+2DCh] [rbp+1ACh]
  wchar_t Destination[256]; // [rsp+2E0h] [rbp+1B0h] BYREF

  Attribute = TMetabaseMetaXmlFile::GetAttribute(this, a2, (TMetabaseMetaXmlFile *)((char *)this + 520));
  if ( !*((_QWORD *)Attribute + 1) )
  {
    if ( *((_DWORD *)a2 + 5) )
      v5 = (const wchar_t *)*((_QWORD *)a2 + 5);
    else
      v5 = &word_180034198;
    wcsncpy_s(Destination, 0x100u, v5, 0xFFu);
    Destination[255] = 0;
    v24 = 0;
    CErrorInterceptor::Init(
      (CErrorInterceptor *)v23,
      0,
      *((_QWORD *)this + 325),
      0x80210861,
      3u,
      -1073606449,
      L"InheritsPropertiesFrom",
      Destination,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0,
      v21,
      v22,
      -1,
      -1);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v23,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      912,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v23);
  }
  v6 = *((unsigned int *)Attribute + 4);
  if ( (unsigned int)v6 > 0x10F )
  {
    wcsncpy_s(String, 0x110u, *((const wchar_t **)Attribute + 3), 0x10Cu);
    v26 = 3014702;
    v27 = 46;
    v24 = 0;
    CErrorInterceptor::Init(
      (CErrorInterceptor *)v23,
      0,
      *((_QWORD *)this + 325),
      0x80210861,
      3u,
      -1073606448,
      L"InheritsPropertiesFrom",
      String,
      L"271",
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0,
      v21,
      v22,
      -1,
      -1);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v23,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      930,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v23);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0x3A2u,
      0);
  }
  memcpy_0(String, *((const void **)Attribute + 3), 2 * v6);
  if ( (unsigned __int64)(2 * v6) >= 0x220 )
    _report_rangecheckfailure();
  String[v6] = 0;
  v8 = wcstok_mvcrt_legacy_two_parameter_form(String, L":", v7);
  v10 = wcstok_mvcrt_legacy_two_parameter_form(0, L":", v9);
  if ( !v8 || !v10 )
  {
    memcpy_0(String, *((const void **)Attribute + 3), 2 * v6);
    String[v6] = 0;
    v24 = 0;
    CErrorInterceptor::Init(
      (CErrorInterceptor *)v23,
      0,
      *((_QWORD *)this + 325),
      0x80210861,
      3u,
      -1073606447,
      String,
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0,
      v21,
      v22,
      -1,
      -1);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v23,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      944,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v23);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0x3B0u,
      0);
  }
  if ( ((*v8 - 73) & 0xFFDF) != 0 )
  {
    v24 = 0;
    CErrorInterceptor::Init(
      (CErrorInterceptor *)v23,
      0,
      *((_QWORD *)this + 325),
      0x80210861,
      3u,
      -1073606446,
      v8,
      L"IIsConfigObject",
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0,
      v21,
      v22,
      -1,
      -1);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v23,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      951,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v23);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0x3B7u,
      0);
  }
  v11 = 1;
  v12 = (*(unsigned int (__fastcall **)(TMetabaseMetaXmlFile *, wchar_t *, _QWORD))(*(_QWORD *)this + 40LL))(
          this,
          v10,
          (unsigned int)v6 - (unsigned int)(v10 - v8) + 1);
  LOBYTE(v13) = 1;
  v14 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD, __int64, __int64))(*(_QWORD *)this + 376LL))(
          this,
          *((unsigned int *)this + 636),
          v12,
          v13);
  if ( v14 == -1 )
  {
    LOBYTE(v15) = 1;
    v16 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD, _QWORD, __int64))(*(_QWORD *)this + 376LL))(
            this,
            *((unsigned int *)this + 638),
            (unsigned int)v12,
            v15);
    if ( v16 == -1 )
      return;
    for ( i = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *))(*(_QWORD *)this + 264LL))(this) - 1;
          i
       && *(_DWORD *)(*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 176LL))(this, i) == *((_DWORD *)this + 636);
          --i )
    {
      if ( *(_DWORD *)((*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 176LL))(this, i) + 8) == (_DWORD)v12 )
        return;
    }
    v11 = 0;
    v14 = *((_DWORD *)this + 643);
    TMetabaseMetaXmlFile::AddColumnMetaByReference(this, v16);
  }
  TMetabaseMetaXmlFile::CheckForOverrridingColumnMeta(this, a2, v14);
  if ( !v11 && *((_DWORD *)this + 637) <= *((_DWORD *)this + 639) )
  {
    v18 = *(_QWORD *)this;
    v19 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *))(*(_QWORD *)this + 232LL))(this);
    v20 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(v18 + 152))(this, *(unsigned int *)(v19 + 40));
    LODWORD(v18) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(v18 + 16))(this, v20 | 0x100u);
    *(_DWORD *)((*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 232LL))(
                  this,
                  *((unsigned int *)this + 637))
              + 40) = v18;
  }
}

```

## disassembly

```asm
0x1800199c8  mov     [rsp-8+arg_10], rbx
0x1800199cd  push    rbp
0x1800199ce  push    rsi
0x1800199cf  push    rdi
0x1800199d0  push    r12
0x1800199d2  push    r13
0x1800199d4  push    r14
0x1800199d6  push    r15
0x1800199d8  lea     rbp, [rsp-3C0h]
0x1800199e0  sub     rsp, 4F0h
0x1800199e7  mov     rax, cs:__security_cookie
0x1800199ee  xor     rax, rsp
0x1800199f1  mov     [rbp+3F0h+var_40], rax
0x1800199f8  mov     r14, rdx
0x1800199fb  mov     rdi, rcx
0x1800199fe  lea     r8, [rcx+208h]; struct TMetabaseMetaXmlFile::TSizedString *
0x180019a05  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x180019a0a  mov     r15, rax
0x180019a0d  lea     r12, word_180034198
0x180019a14  or      esi, 0FFFFFFFFh
0x180019a17  lea     rbx, aInheritsproper; "InheritsPropertiesFrom"
0x180019a1e  xor     r13d, r13d
0x180019a21  cmp     [rax+8], r13
0x180019a25  jnz     loc_180019AF8
0x180019a2b  cmp     [r14+14h], r13d
0x180019a2f  jbe     short loc_180019A37
0x180019a31  mov     r8, [r14+28h]
0x180019a35  jmp     short loc_180019A3A
0x180019a37  mov     r8, r12; Source
0x180019a3a  mov     edx, 100h; SizeInWords
0x180019a3f  lea     r9d, [rdx-1]; MaxCount
0x180019a43  lea     rcx, [rbp+3F0h+Destination]; Destination
0x180019a4a  call    cs:__imp_wcsncpy_s
0x180019a50  mov     [rbp+3F0h+var_42], r13w
0x180019a58  mov     [rbp+3F0h+var_468], r13
0x180019a5c  mov     [rsp+520h+var_480], esi
0x180019a63  mov     [rsp+520h+var_488], esi
0x180019a6a  mov     [rsp+520h+var_4A0], r13d
0x180019a72  mov     [rsp+520h+var_4A8], r13
0x180019a77  mov     [rsp+520h+var_4B0], esi
0x180019a7b  mov     [rsp+520h+var_4B8], esi
0x180019a7f  mov     [rsp+520h+var_4C0], r13d
0x180019a84  mov     [rsp+520h+var_4C8], r13
0x180019a89  mov     [rsp+520h+var_4D0], r13d
0x180019a8e  mov     [rsp+520h+var_4D8], r12
0x180019a93  mov     [rsp+520h+var_4E0], r12
0x180019a98  lea     rax, [rbp+3F0h+Destination]
0x180019a9f  mov     [rsp+520h+var_4E8], rax
0x180019aa4  mov     [rsp+520h+var_4F0], rbx
0x180019aa9  mov     [rsp+520h+var_4F8], 0C00210CFh
0x180019ab1  mov     [rsp+520h+var_500], 3
0x180019ab9  mov     r9d, 80210861h
0x180019abf  mov     r8, [rdi+0A28h]
0x180019ac6  xor     edx, edx
0x180019ac8  lea     rcx, [rbp+3F0h+var_470]
0x180019acc  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x180019ad1  nop
0x180019ad2  mov     r9d, 400000h; unsigned int
0x180019ad8  mov     r8d, 390h; unsigned int
0x180019ade  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180019ae5  lea     rcx, [rbp+3F0h+var_470]; this
0x180019ae9  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x180019aee  nop
0x180019aef  lea     rcx, [rbp+3F0h+var_470]; this
0x180019af3  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x180019af8  mov     ebx, [r15+10h]
0x180019afc  mov     rdx, [r15+18h]; Src
0x180019b00  lea     rcx, [rbp+3F0h+String]; Destination
0x180019b04  cmp     ebx, 10Fh
0x180019b0a  jbe     loc_180019BFE
0x180019b10  mov     r9d, 10Ch; MaxCount
0x180019b16  mov     r8, rdx; Source
0x180019b19  lea     edx, [r9+4]; SizeInWords
0x180019b1d  call    cs:__imp_wcsncpy_s
0x180019b23  mov     [rbp+3F0h+var_248], 2E002Eh
0x180019b2d  mov     [rbp+3F0h+var_244], 2Eh ; '.'
0x180019b37  mov     [rbp+3F0h+var_468], r13
0x180019b3b  mov     [rsp+520h+var_480], esi
0x180019b42  mov     [rsp+520h+var_488], esi
0x180019b49  mov     [rsp+520h+var_4A0], r13d
0x180019b51  mov     [rsp+520h+var_4A8], r13
0x180019b56  mov     [rsp+520h+var_4B0], esi
0x180019b5a  mov     [rsp+520h+var_4B8], esi
0x180019b5e  mov     [rsp+520h+var_4C0], r13d
0x180019b63  mov     [rsp+520h+var_4C8], r13
0x180019b68  mov     [rsp+520h+var_4D0], r13d
0x180019b6d  mov     [rsp+520h+var_4D8], r12
0x180019b72  lea     rax, a271; "271"
0x180019b79  mov     [rsp+520h+var_4E0], rax
0x180019b7e  lea     rax, [rbp+3F0h+String]
0x180019b82  mov     [rsp+520h+var_4E8], rax
0x180019b87  lea     rax, aInheritsproper; "InheritsPropertiesFrom"
0x180019b8e  mov     [rsp+520h+var_4F0], rax
0x180019b93  mov     [rsp+520h+var_4F8], 0C00210D0h
0x180019b9b  mov     [rsp+520h+var_500], 3
0x180019ba3  mov     r9d, 80210861h
0x180019ba9  mov     r8, [rdi+0A28h]
0x180019bb0  xor     edx, edx
0x180019bb2  lea     rcx, [rbp+3F0h+var_470]
0x180019bb6  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x180019bbb  nop
0x180019bbc  mov     ebx, 3A2h
0x180019bc1  mov     r9d, 400000h; unsigned int
0x180019bc7  mov     r8d, ebx; unsigned int
0x180019bca  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180019bd1  lea     rcx, [rbp+3F0h+var_470]; this
0x180019bd5  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x180019bda  nop
0x180019bdb  lea     rcx, [rbp+3F0h+var_470]; this
0x180019bdf  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x180019be4  xor     r9d, r9d; unsigned int
0x180019be7  mov     r8d, ebx; unsigned int
0x180019bea  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x180019bf1  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180019bf8  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180019bfe  lea     rsi, [rbx+rbx]
0x180019c02  mov     r8, rsi; Size
0x180019c05  call    memcpy_0
0x180019c0a  cmp     rsi, 220h
0x180019c11  jnb     loc_180019F8D
0x180019c17  mov     [rbp+rsi+3F0h+String], r13w
0x180019c1d  lea     rdx, asc_1800363D0; ":"
0x180019c24  lea     rcx, [rbp+3F0h+String]; String
0x180019c28  call    wcstok_mvcrt_legacy_two_parameter_form
0x180019c2d  mov     r12, rax
0x180019c30  lea     rdx, asc_1800363D0; ":"
0x180019c37  xor     ecx, ecx; String
0x180019c39  call    wcstok_mvcrt_legacy_two_parameter_form
0x180019c3e  mov     rdx, rax
0x180019c41  test    r12, r12
0x180019c44  jz      loc_180019EB4
0x180019c4a  test    rax, rax
0x180019c4d  jz      loc_180019EB4
0x180019c53  movzx   ecx, word ptr [r12]
0x180019c58  sub     cx, 49h ; 'I'
0x180019c5c  mov     eax, 0FFDFh
0x180019c61  test    ax, cx
0x180019c64  jz      loc_180019D30
0x180019c6a  mov     [rbp+3F0h+var_468], r13
0x180019c6e  or      eax, 0FFFFFFFFh
0x180019c71  mov     [rsp+520h+var_480], eax
0x180019c78  mov     [rsp+520h+var_488], eax
0x180019c7f  mov     [rsp+520h+var_4A0], r13d
0x180019c87  mov     [rsp+520h+var_4A8], r13
0x180019c8c  mov     [rsp+520h+var_4B0], eax
0x180019c90  mov     [rsp+520h+var_4B8], eax
0x180019c94  mov     [rsp+520h+var_4C0], r13d
0x180019c99  mov     [rsp+520h+var_4C8], r13
0x180019c9e  mov     [rsp+520h+var_4D0], r13d
0x180019ca3  lea     rax, word_180034198
0x180019caa  mov     [rsp+520h+var_4D8], rax
0x180019caf  mov     [rsp+520h+var_4E0], rax
0x180019cb4  lea     rax, aIisconfigobjec; "IIsConfigObject"
0x180019cbb  mov     [rsp+520h+var_4E8], rax
0x180019cc0  mov     [rsp+520h+var_4F0], r12
0x180019cc5  mov     [rsp+520h+var_4F8], 0C00210D2h
0x180019ccd  mov     [rsp+520h+var_500], 3
0x180019cd5  mov     r9d, 80210861h
0x180019cdb  mov     r8, [rdi+0A28h]
0x180019ce2  xor     edx, edx
0x180019ce4  lea     rcx, [rbp+3F0h+var_470]
0x180019ce8  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x180019ced  nop
0x180019cee  mov     ebx, 3B7h
0x180019cf3  mov     r9d, 400000h; unsigned int
0x180019cf9  mov     r8d, ebx; unsigned int
0x180019cfc  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180019d03  lea     rcx, [rbp+3F0h+var_470]; this
0x180019d07  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x180019d0c  nop
0x180019d0d  lea     rcx, [rbp+3F0h+var_470]; this
0x180019d11  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x180019d16  xor     r9d, r9d; unsigned int
0x180019d19  mov     r8d, ebx; unsigned int
0x180019d1c  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x180019d23  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180019d2a  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180019d30  mov     r9, [rdi]
0x180019d33  mov     rax, rdx
0x180019d36  sub     rax, r12
0x180019d39  sar     rax, 1
0x180019d3c  sub     ebx, eax
0x180019d3e  mov     esi, 1
0x180019d43  lea     r8d, [rsi+rbx]
0x180019d47  mov     rcx, rdi
0x180019d4a  mov     rax, [r9+28h]
0x180019d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d53  mov     r12d, eax
0x180019d56  mov     rcx, [rdi]
0x180019d59  mov     rax, [rcx+178h]
0x180019d60  mov     r9b, sil
0x180019d63  mov     r8d, r12d
0x180019d66  mov     edx, [rdi+9F0h]
0x180019d6c  mov     rcx, rdi
0x180019d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d74  mov     ebx, eax
0x180019d76  cmp     eax, 0FFFFFFFFh
0x180019d79  jnz     loc_180019E16
0x180019d7f  mov     rax, [rdi]
0x180019d82  mov     r9b, sil
0x180019d85  mov     r8d, r12d
0x180019d88  mov     edx, [rdi+9F8h]
0x180019d8e  mov     rcx, rdi
0x180019d91  mov     rax, [rax+178h]
0x180019d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d9d  mov     r15d, eax
0x180019da0  cmp     eax, ebx
0x180019da2  jz      loc_180019E8A
0x180019da8  mov     rcx, [rdi]
0x180019dab  mov     rax, [rcx+108h]
0x180019db2  mov     rcx, rdi
0x180019db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dba  mov     ebx, eax
0x180019dbc  sub     ebx, esi
0x180019dbe  test    ebx, ebx
0x180019dc0  jz      short loc_180019E02
0x180019dc2  mov     rcx, [rdi]
0x180019dc5  mov     rax, [rcx+0B0h]
0x180019dcc  mov     edx, ebx
0x180019dce  mov     rcx, rdi
0x180019dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dd6  mov     ecx, [rdi+9F0h]
0x180019ddc  cmp     [rax], ecx
0x180019dde  jnz     short loc_180019E02
0x180019de0  mov     rax, [rdi]
0x180019de3  mov     edx, ebx
0x180019de5  mov     rcx, rdi
0x180019de8  mov     rax, [rax+0B0h]
0x180019def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019df4  cmp     [rax+8], r12d
0x180019df8  jz      loc_180019E8A
0x180019dfe  dec     ebx
0x180019e00  jmp     short loc_180019DBE
0x180019e02  mov     sil, r13b
0x180019e05  mov     ebx, [rdi+0A0Ch]
0x180019e0b  mov     edx, r15d; unsigned int
0x180019e0e  mov     rcx, rdi; this
0x180019e11  call    ?AddColumnMetaByReference@TMetabaseMetaXmlFile@@AEAAXK@Z; TMetabaseMetaXmlFile::AddColumnMetaByReference(ulong)
0x180019e16  mov     r8d, ebx; unsigned int
0x180019e19  mov     rdx, r14; struct TElement *
0x180019e1c  mov     rcx, rdi; this
0x180019e1f  call    ?CheckForOverrridingColumnMeta@TMetabaseMetaXmlFile@@AEAAXAEBUTElement@@K@Z; TMetabaseMetaXmlFile::CheckForOverrridingColumnMeta(TElement const &,ulong)
0x180019e24  test    sil, sil
0x180019e27  jnz     short loc_180019E8A
0x180019e29  mov     edx, [rdi+9F4h]
0x180019e2f  cmp     edx, [rdi+9FCh]
0x180019e35  ja      short loc_180019E8A
0x180019e37  mov     rbx, [rdi]
0x180019e3a  mov     rcx, rdi
0x180019e3d  mov     rax, [rbx+0E8h]
0x180019e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e49  mov     edx, [rax+28h]
0x180019e4c  mov     rcx, rdi
0x180019e4f  mov     rax, [rbx+98h]
0x180019e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e5b  bts     eax, 8
0x180019e5f  mov     edx, eax
0x180019e61  mov     rcx, rdi
0x180019e64  mov     rax, [rbx+10h]
0x180019e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e6d  mov     ebx, eax
0x180019e6f  mov     rdx, [rdi]
0x180019e72  mov     rax, [rdx+0E8h]
0x180019e79  mov     edx, [rdi+9F4h]
0x180019e7f  mov     rcx, rdi
0x180019e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e87  mov     [rax+28h], ebx
0x180019e8a  mov     rcx, [rbp+3F0h+var_40]
0x180019e91  xor     rcx, rsp; StackCookie
0x180019e94  call    __security_check_cookie
0x180019e99  mov     rbx, [rsp+520h+arg_10]
0x180019ea1  add     rsp, 4F0h
0x180019ea8  pop     r15
0x180019eaa  pop     r14
0x180019eac  pop     r13
0x180019eae  pop     r12
0x180019eb0  pop     rdi
0x180019eb1  pop     rsi
0x180019eb2  pop     rbp
0x180019eb3  retn
0x180019eb4  mov     r8, rsi; Size
0x180019eb7  mov     rdx, [r15+18h]; Src
0x180019ebb  lea     rcx, [rbp+3F0h+String]; void *
0x180019ebf  call    memcpy_0
0x180019ec4  mov     [rbp+rsi+3F0h+String], r13w
0x180019eca  mov     [rbp+3F0h+var_468], r13
0x180019ece  or      eax, 0FFFFFFFFh
0x180019ed1  mov     [rsp+520h+var_480], eax
0x180019ed8  mov     [rsp+520h+var_488], eax
0x180019edf  mov     [rsp+520h+var_4A0], r13d
0x180019ee7  mov     [rsp+520h+var_4A8], r13
0x180019eec  mov     [rsp+520h+var_4B0], eax
0x180019ef0  mov     [rsp+520h+var_4B8], eax
0x180019ef4  mov     [rsp+520h+var_4C0], r13d
0x180019ef9  mov     [rsp+520h+var_4C8], r13
0x180019efe  mov     [rsp+520h+var_4D0], r13d
0x180019f03  lea     rax, word_180034198
0x180019f0a  mov     [rsp+520h+var_4D8], rax
0x180019f0f  mov     [rsp+520h+var_4E0], rax
0x180019f14  mov     [rsp+520h+var_4E8], rax
  ... truncated ...
```
