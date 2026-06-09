# TMetabaseMetaXmlFile::ConvertWideCharsToBytes(ushort const *,uchar *,ulong)

- ea: `0x18001bd60`
- end: `0x18001c236`
- name: `?ConvertWideCharsToBytes@TMetabaseMetaXmlFile@@AEAAXPEBGPEAEK@Z`
- size: `1238`
- prototype: `void(TMetabaseMetaXmlFile *__hidden this, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001c86c`

## callees

- `0x180002bc4`
- `0x180011b38`
- `0x180012734`
- `0x180017ad8`
- `0x18001bd60`
- `0x18002e0b2`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18001bddb`
- `ole32!CoTaskMemAlloc` at `0x18001bfb9`
- `ole32!CoTaskMemAlloc` at `0x18001bddb`
- `ole32!CoTaskMemAlloc` at `0x18001bfb9`

## string_xrefs

- `0x18001be7d`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001bea4`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001bf55`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001bf7c`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001c05b`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001c082`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001c12e`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001c155`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001c1ee`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001c215`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001be9d`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x18001bf75`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x18001c07b`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x18001c14e`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x18001c20e`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall TMetabaseMetaXmlFile::ConvertWideCharsToBytes(
        TMetabaseMetaXmlFile *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  char v7; // cl
  const unsigned __int16 *v8; // rsi
  unsigned __int8 v9; // cl
  char v10; // dl
  void *v11; // rbx
  size_t v12; // rdi
  __int64 v13; // r14
  _WORD *v14; // rax
  _WORD *v15; // rbx
  char v16[8]; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v17; // [rsp+C0h] [rbp+7h]

  while ( a4 )
  {
    v7 = *((_BYTE *)qword_1800365F0 + (*a2 & 0x7F));
    if ( (v7 & 0xF0) != 0 )
    {
      v13 = 2 * a4;
      if ( (unsigned int)v13 >= a4 && (int)v13 + 1 >= (unsigned int)v13 )
      {
        v14 = CoTaskMemAlloc(saturated_mul((unsigned int)(v13 + 1), 2u));
        v15 = v14;
        if ( !v14 )
        {
          v17 = 0;
          CErrorInterceptor::Init(
            v16,
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
            (CErrorInterceptor *)v16,
            L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
            878,
            0x400000);
          CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v16);
          ThrowException(
            L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
            L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
            0x36Eu,
            0);
        }
        memcpy_0(v14, a2, (unsigned int)v13);
        v15[v13] = 0;
        v17 = 0;
        CErrorInterceptor::Init(
          v16,
          0,
          *((_QWORD *)this + 325),
          2149648481LL,
          3,
          -2147348289,
          v15,
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
          (CErrorInterceptor *)v16,
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
          882,
          0x400000);
        CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v16);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
          L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
          0x372u,
          0);
      }
      v17 = 0;
      CErrorInterceptor::Init(
        v16,
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
        (CErrorInterceptor *)v16,
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        872,
        0x400000);
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v16);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
        0x368u,
        0);
    }
    v8 = a2 + 1;
    v9 = 16 * v7;
    *a3 = v9;
    v10 = *((_BYTE *)qword_1800365F0 + (*v8 & 0x7F));
    if ( (v10 & 0xF0) != 0 )
    {
      v11 = CoTaskMemAlloc(2u);
      if ( !v11 )
      {
        v17 = 0;
        CErrorInterceptor::Init(
          v16,
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
          (CErrorInterceptor *)v16,
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
          891,
          0x400000);
        CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v16);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
          L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
          0x37Bu,
          0);
      }
      v12 = 2 * a4;
      memcpy_0(v11, v8, v12);
      *((_WORD *)v11 + v12) = 0;
      v17 = 0;
      CErrorInterceptor::Init(
        v16,
        0,
        *((_QWORD *)this + 325),
        2149648481LL,
        3,
        -2147348289,
        v11,
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
        (CErrorInterceptor *)v16,
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        896,
        0x400000);
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v16);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
        0x380u,
        0);
    }
    a2 = v8 + 1;
    *a3 = v9 | v10;
    --a4;
    ++a3;
  }
}

```

## disassembly

```asm
0x18001bd60  push    rbp
0x18001bd62  push    rbx
0x18001bd63  push    rsi
0x18001bd64  push    rdi
0x18001bd65  push    r12
0x18001bd67  push    r13
0x18001bd69  push    r14
0x18001bd6b  push    r15
0x18001bd6d  lea     rbp, [rsp-1Fh]
0x18001bd72  sub     rsp, 0D8h
0x18001bd79  mov     edi, r9d
0x18001bd7c  mov     rsi, rdx
0x18001bd7f  mov     r15, rcx
0x18001bd82  xor     r12d, r12d
0x18001bd85  lea     r10, qword_1800365F0
0x18001bd8c  lea     r9d, [r12+2]
0x18001bd91  or      r13d, 0FFFFFFFFh
0x18001bd95  test    edi, edi
0x18001bd97  jz      loc_18001C222
0x18001bd9d  movzx   eax, word ptr [rsi]
0x18001bda0  and     eax, 7Fh
0x18001bda3  mov     cl, [rax+r10]
0x18001bda7  test    cl, 0F0h
0x18001bdaa  jnz     loc_18001BF89
0x18001bdb0  add     rsi, r9
0x18001bdb3  shl     cl, 4
0x18001bdb6  mov     [r8], cl
0x18001bdb9  movzx   eax, word ptr [rsi]
0x18001bdbc  and     eax, 7Fh
0x18001bdbf  mov     dl, [rax+r10]
0x18001bdc3  test    dl, 0F0h
0x18001bdc6  jnz     short loc_18001BDD8
0x18001bdc8  add     rsi, r9
0x18001bdcb  or      dl, cl
0x18001bdcd  mov     [r8], dl
0x18001bdd0  add     edi, r13d
0x18001bdd3  inc     r8
0x18001bdd6  jmp     short loc_18001BD95
0x18001bdd8  mov     rcx, r9; cb
0x18001bddb  call    cs:__imp_CoTaskMemAlloc
0x18001bde1  mov     rbx, rax
0x18001bde4  mov     [rbp+57h+var_60], rax
0x18001bde8  test    rax, rax
0x18001bdeb  jnz     loc_18001BEB1
0x18001bdf1  mov     [rbp+57h+var_50], r12
0x18001bdf5  mov     [rsp+110h+var_70], r13d
0x18001bdfd  mov     [rsp+110h+var_78], r13d
0x18001be05  mov     [rsp+110h+var_90], r12d
0x18001be0d  mov     [rsp+110h+var_98], r12
0x18001be12  mov     [rsp+110h+var_A0], r13d
0x18001be17  mov     [rsp+110h+var_A8], r13d
0x18001be1c  mov     [rsp+110h+var_B0], r12d
0x18001be21  mov     [rsp+110h+var_B8], r12
0x18001be26  mov     [rsp+110h+var_C0], r12d
0x18001be2b  lea     rax, word_180034198
0x18001be32  mov     [rsp+110h+var_C8], rax
0x18001be37  mov     [rsp+110h+var_D0], rax
0x18001be3c  mov     [rsp+110h+var_D8], rax
0x18001be41  mov     [rsp+110h+var_E0], rax
0x18001be46  mov     [rsp+110h+var_E8], 0C00210CAh
0x18001be4e  mov     [rsp+110h+var_F0], 3
0x18001be56  mov     r9d, 80210861h
0x18001be5c  mov     r8, [r15+0A28h]
0x18001be63  xor     edx, edx
0x18001be65  lea     rcx, [rbp+57h+var_58]
0x18001be69  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001be6e  nop
0x18001be6f  mov     ebx, 37Bh
0x18001be74  mov     r9d, 400000h; unsigned int
0x18001be7a  mov     r8d, ebx; unsigned int
0x18001be7d  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001be84  lea     rcx, [rbp+57h+var_58]; this
0x18001be88  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001be8d  nop
0x18001be8e  lea     rcx, [rbp+57h+var_58]; this
0x18001be92  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18001be97  xor     r9d, r9d; unsigned int
0x18001be9a  mov     r8d, ebx; unsigned int
0x18001be9d  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x18001bea4  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001beab  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001beb1  lea     eax, [rdi+rdi]
0x18001beb4  mov     edi, eax
0x18001beb6  mov     r8d, eax; Size
0x18001beb9  mov     rdx, rsi; Src
0x18001bebc  mov     rcx, rbx; void *
0x18001bebf  call    memcpy_0
0x18001bec4  mov     [rbx+rdi*2], r12w
0x18001bec9  mov     [rbp+57h+var_50], r12
0x18001becd  mov     [rsp+110h+var_70], r13d
0x18001bed5  mov     [rsp+110h+var_78], r13d
0x18001bedd  mov     [rsp+110h+var_90], r12d
0x18001bee5  mov     [rsp+110h+var_98], r12
0x18001beea  mov     [rsp+110h+var_A0], r13d
0x18001beef  mov     [rsp+110h+var_A8], r13d
0x18001bef4  mov     [rsp+110h+var_B0], r12d
0x18001bef9  mov     [rsp+110h+var_B8], r12
0x18001befe  mov     [rsp+110h+var_C0], r12d
0x18001bf03  lea     rax, word_180034198
0x18001bf0a  mov     [rsp+110h+var_C8], rax
0x18001bf0f  mov     [rsp+110h+var_D0], rax
0x18001bf14  mov     [rsp+110h+var_D8], rax
0x18001bf19  mov     [rsp+110h+var_E0], rbx
0x18001bf1e  mov     [rsp+110h+var_E8], 800210BFh
0x18001bf26  mov     [rsp+110h+var_F0], 3
0x18001bf2e  mov     r9d, 80210861h
0x18001bf34  mov     r8, [r15+0A28h]
0x18001bf3b  xor     edx, edx
0x18001bf3d  lea     rcx, [rbp+57h+var_58]
0x18001bf41  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001bf46  nop
0x18001bf47  mov     ebx, 380h
0x18001bf4c  mov     r9d, 400000h; unsigned int
0x18001bf52  mov     r8d, ebx; unsigned int
0x18001bf55  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001bf5c  lea     rcx, [rbp+57h+var_58]; this
0x18001bf60  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001bf65  nop
0x18001bf66  lea     rcx, [rbp+57h+var_58]; this
0x18001bf6a  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18001bf6f  xor     r9d, r9d; unsigned int
0x18001bf72  mov     r8d, ebx; unsigned int
0x18001bf75  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x18001bf7c  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001bf83  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001bf89  lea     r14d, [rdi+rdi]
0x18001bf8d  cmp     r14d, edi
0x18001bf90  jb      loc_18001C162
0x18001bf96  lea     eax, [r14+1]
0x18001bf9a  cmp     eax, r14d
0x18001bf9d  jb      loc_18001C162
0x18001bfa3  mov     ecx, eax
0x18001bfa5  mov     rax, r9
0x18001bfa8  mul     rcx
0x18001bfab  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001bfb2  cmovb   rax, rcx
0x18001bfb6  mov     rcx, rax; cb
0x18001bfb9  call    cs:__imp_CoTaskMemAlloc
0x18001bfbf  mov     rbx, rax
0x18001bfc2  mov     [rbp+57h+var_60], rax
0x18001bfc6  test    rax, rax
0x18001bfc9  jnz     loc_18001C08F
0x18001bfcf  mov     [rbp+57h+var_50], r12
0x18001bfd3  mov     [rsp+110h+var_70], r13d
0x18001bfdb  mov     [rsp+110h+var_78], r13d
0x18001bfe3  mov     [rsp+110h+var_90], r12d
0x18001bfeb  mov     [rsp+110h+var_98], r12
0x18001bff0  mov     [rsp+110h+var_A0], r13d
0x18001bff5  mov     [rsp+110h+var_A8], r13d
0x18001bffa  mov     [rsp+110h+var_B0], r12d
0x18001bfff  mov     [rsp+110h+var_B8], r12
0x18001c004  mov     [rsp+110h+var_C0], r12d
0x18001c009  lea     rax, word_180034198
0x18001c010  mov     [rsp+110h+var_C8], rax
0x18001c015  mov     [rsp+110h+var_D0], rax
0x18001c01a  mov     [rsp+110h+var_D8], rax
0x18001c01f  mov     [rsp+110h+var_E0], rax
0x18001c024  mov     [rsp+110h+var_E8], 0C00210CAh
0x18001c02c  mov     [rsp+110h+var_F0], 3
0x18001c034  mov     r9d, 80210861h
0x18001c03a  mov     r8, [r15+0A28h]
0x18001c041  xor     edx, edx
0x18001c043  lea     rcx, [rbp+57h+var_58]
0x18001c047  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001c04c  nop
0x18001c04d  mov     ebx, 36Eh
0x18001c052  mov     r9d, 400000h; unsigned int
0x18001c058  mov     r8d, ebx; unsigned int
0x18001c05b  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001c062  lea     rcx, [rbp+57h+var_58]; this
0x18001c066  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001c06b  nop
0x18001c06c  lea     rcx, [rbp+57h+var_58]; this
0x18001c070  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18001c075  xor     r9d, r9d; unsigned int
0x18001c078  mov     r8d, ebx; unsigned int
0x18001c07b  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x18001c082  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001c089  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001c08f  mov     r8d, r14d; Size
0x18001c092  mov     rdx, rsi; Src
0x18001c095  mov     rcx, rbx; void *
0x18001c098  call    memcpy_0
0x18001c09d  mov     [rbx+r14*2], r12w
0x18001c0a2  mov     [rbp+57h+var_50], r12
0x18001c0a6  mov     [rsp+110h+var_70], r13d
0x18001c0ae  mov     [rsp+110h+var_78], r13d
0x18001c0b6  mov     [rsp+110h+var_90], r12d
0x18001c0be  mov     [rsp+110h+var_98], r12
0x18001c0c3  mov     [rsp+110h+var_A0], r13d
0x18001c0c8  mov     [rsp+110h+var_A8], r13d
0x18001c0cd  mov     [rsp+110h+var_B0], r12d
0x18001c0d2  mov     [rsp+110h+var_B8], r12
0x18001c0d7  mov     [rsp+110h+var_C0], r12d
0x18001c0dc  lea     rax, word_180034198
0x18001c0e3  mov     [rsp+110h+var_C8], rax
0x18001c0e8  mov     [rsp+110h+var_D0], rax
0x18001c0ed  mov     [rsp+110h+var_D8], rax
0x18001c0f2  mov     [rsp+110h+var_E0], rbx
0x18001c0f7  mov     [rsp+110h+var_E8], 800210BFh
0x18001c0ff  mov     [rsp+110h+var_F0], 3
0x18001c107  mov     r9d, 80210861h
0x18001c10d  mov     r8, [r15+0A28h]
0x18001c114  xor     edx, edx
0x18001c116  lea     rcx, [rbp+57h+var_58]
0x18001c11a  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001c11f  nop
0x18001c120  mov     ebx, 372h
0x18001c125  mov     r9d, 400000h; unsigned int
0x18001c12b  mov     r8d, ebx; unsigned int
0x18001c12e  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001c135  lea     rcx, [rbp+57h+var_58]; this
0x18001c139  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001c13e  nop
0x18001c13f  lea     rcx, [rbp+57h+var_58]; this
0x18001c143  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18001c148  xor     r9d, r9d; unsigned int
0x18001c14b  mov     r8d, ebx; unsigned int
0x18001c14e  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x18001c155  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001c15c  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001c162  mov     [rbp+57h+var_50], r12
0x18001c166  mov     [rsp+110h+var_70], r13d
0x18001c16e  mov     [rsp+110h+var_78], r13d
0x18001c176  mov     [rsp+110h+var_90], r12d
0x18001c17e  mov     [rsp+110h+var_98], r12
0x18001c183  mov     [rsp+110h+var_A0], r13d
0x18001c188  mov     [rsp+110h+var_A8], r13d
0x18001c18d  mov     [rsp+110h+var_B0], r12d
0x18001c192  mov     [rsp+110h+var_B8], r12
0x18001c197  mov     [rsp+110h+var_C0], r12d
0x18001c19c  lea     rax, word_180034198
0x18001c1a3  mov     [rsp+110h+var_C8], rax
0x18001c1a8  mov     [rsp+110h+var_D0], rax
0x18001c1ad  mov     [rsp+110h+var_D8], rax
0x18001c1b2  mov     [rsp+110h+var_E0], rax
0x18001c1b7  mov     [rsp+110h+var_E8], 0C00210CAh
0x18001c1bf  mov     [rsp+110h+var_F0], 3
0x18001c1c7  mov     r9d, 80210861h
0x18001c1cd  mov     r8, [r15+0A28h]
0x18001c1d4  xor     edx, edx
0x18001c1d6  lea     rcx, [rbp+57h+var_58]
0x18001c1da  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001c1df  nop
0x18001c1e0  mov     ebx, 368h
0x18001c1e5  mov     r9d, 400000h; unsigned int
0x18001c1eb  mov     r8d, ebx; unsigned int
0x18001c1ee  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001c1f5  lea     rcx, [rbp+57h+var_58]; this
0x18001c1f9  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001c1fe  nop
0x18001c1ff  lea     rcx, [rbp+57h+var_58]; this
0x18001c203  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18001c208  xor     r9d, r9d; unsigned int
0x18001c20b  mov     r8d, ebx; unsigned int
0x18001c20e  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x18001c215  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001c21c  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001c222  add     rsp, 0D8h
0x18001c229  pop     r15
0x18001c22b  pop     r14
0x18001c22d  pop     r13
0x18001c22f  pop     r12
0x18001c231  pop     rdi
0x18001c232  pop     rsi
0x18001c233  pop     rbx
0x18001c234  pop     rbp
0x18001c235  retn
```
