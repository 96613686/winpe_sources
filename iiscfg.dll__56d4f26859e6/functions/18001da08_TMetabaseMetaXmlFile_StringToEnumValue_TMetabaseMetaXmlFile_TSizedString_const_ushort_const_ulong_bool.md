# TMetabaseMetaXmlFile::StringToEnumValue(TMetabaseMetaXmlFile::TSizedString const &,ushort const *,ulong,bool)

- ea: `0x18001da08`
- end: `0x18001dd00`
- name: `?StringToEnumValue@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@PEBGK_N@Z`
- size: `760`
- prototype: `unsigned int __fastcall(TMetabaseMetaXmlFile *__hidden this, const struct TMetabaseMetaXmlFile::TSizedString *, const unsigned __int16 *, unsigned int, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019554`

## callees

- `0x180002bc4`
- `0x180005870`
- `0x180011b38`
- `0x180012734`
- `0x180017ad8`
- `0x18001da08`
- `0x18002e0b2`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `msvcrt!wcstol` at `0x18001da6f`
- `msvcrt!wcstol` at `0x18001da6f`
- `ole32!CoTaskMemAlloc` at `0x18001daa1`
- `ole32!CoTaskMemAlloc` at `0x18001daa1`

## string_xrefs

- `0x18001db42`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001db69`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001dc5c`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001dc83`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001db62`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x18001dc7c`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall TMetabaseMetaXmlFile::StringToEnumValue(
        TMetabaseMetaXmlFile *this,
        const struct TMetabaseMetaXmlFile::TSizedString *a2,
        const unsigned __int16 *a3)
{
  const wchar_t *v5; // rcx
  unsigned __int16 v7; // ax
  size_t v8; // rbx
  wchar_t *v9; // rdi
  size_t v10; // rbx
  int v11; // ebx
  __int64 v12; // [rsp+88h] [rbp-A8h]
  __int64 v13; // [rsp+90h] [rbp-A0h]
  unsigned int v14; // [rsp+B0h] [rbp-80h] BYREF
  wchar_t *EndPtr; // [rsp+B8h] [rbp-78h] BYREF
  int v16; // [rsp+C0h] [rbp-70h] BYREF
  int v17; // [rsp+C8h] [rbp-68h] BYREF
  _BYTE v18[8]; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v19; // [rsp+D8h] [rbp-58h]
  int *v20; // [rsp+E0h] [rbp-50h] BYREF
  _QWORD v21[3]; // [rsp+E8h] [rbp-48h] BYREF
  char v22; // [rsp+100h] [rbp-30h] BYREF

  v16 = 14;
  v5 = (const wchar_t *)*((_QWORD *)a2 + 1);
  if ( !v5 )
    return 0;
  v7 = *v5 - 48;
  EndPtr = 0;
  if ( v7 <= 9u )
    return wcstol(v5, &EndPtr, 10);
  v8 = *(unsigned int *)a2;
  if ( (unsigned int)v8 < 0x400 )
  {
    v9 = (wchar_t *)&v22;
  }
  else
  {
    v9 = (wchar_t *)CoTaskMemAlloc(saturated_mul((unsigned int)(v8 + 1), 2u));
    EndPtr = v9;
    if ( !v9 )
    {
      v19 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v18,
        0,
        *((_QWORD *)this + 325),
        0x80210861,
        3u,
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
        0,
        v12,
        v13,
        -1,
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v18,
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        1611,
        0x400000);
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v18);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
        0x64Bu,
        0);
    }
  }
  v10 = v8;
  memcpy_0(v9, *((const void **)a2 + 1), v10 * 2);
  v9[v10] = 0;
  v14 = 0;
  v21[0] = L"COLUMNMETA";
  v21[1] = &v16;
  v21[2] = v9;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD *, unsigned int *))(**((_QWORD **)this + 326) + 24LL))(
         *((_QWORD *)this + 326),
         0,
         v21,
         &v14) < 0 )
  {
    v19 = 0;
    CErrorInterceptor::Init(
      (CErrorInterceptor *)v18,
      0,
      *((_QWORD *)this + 325),
      0x80210861,
      3u,
      -1073606441,
      v9,
      L"COLUMNMETA",
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0,
      v12,
      v13,
      -1,
      -1);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v18,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      1626,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v18);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0x65Au,
      0);
  }
  v20 = 0;
  v17 = 4;
  (*(void (__fastcall **)(_QWORD, _QWORD, __int64, int *, _QWORD, int **))(**((_QWORD **)this + 326) + 32LL))(
    *((_QWORD *)this + 326),
    v14,
    1,
    &v17,
    0,
    &v20);
  v11 = *v20;
  TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&EndPtr);
  return v11;
}

```

## disassembly

```asm
0x18001da08  mov     [rsp-8+arg_10], rbx
0x18001da0d  push    rbp
0x18001da0e  push    rsi
0x18001da0f  push    rdi
0x18001da10  push    r14
0x18001da12  push    r15
0x18001da14  lea     rbp, [rsp-7E0h]
0x18001da1c  sub     rsp, 910h
0x18001da23  mov     rax, cs:__security_cookie
0x18001da2a  xor     rax, rsp
0x18001da2d  mov     [rbp+800h+var_30], rax
0x18001da34  mov     rsi, rdx
0x18001da37  mov     r14, rcx
0x18001da3a  mov     [rbp+800h+var_870], 0Eh
0x18001da41  mov     rcx, [rdx+8]; String
0x18001da45  xor     r15d, r15d
0x18001da48  test    rcx, rcx
0x18001da4b  jnz     short loc_18001DA54
0x18001da4d  xor     eax, eax
0x18001da4f  jmp     loc_18001DCDA
0x18001da54  movzx   eax, word ptr [rcx]
0x18001da57  sub     ax, 30h ; '0'
0x18001da5b  mov     [rbp+800h+EndPtr], r15
0x18001da5f  cmp     ax, 9
0x18001da63  ja      short loc_18001DA7A
0x18001da65  mov     r8d, 0Ah; Radix
0x18001da6b  lea     rdx, [rbp+800h+EndPtr]; EndPtr
0x18001da6f  call    cs:__imp_wcstol
0x18001da75  jmp     loc_18001DCDA
0x18001da7a  mov     ebx, [rdx]
0x18001da7c  cmp     ebx, 400h
0x18001da82  jb      loc_18001DB76
0x18001da88  lea     ecx, [rbx+1]
0x18001da8b  mov     eax, 2
0x18001da90  mul     rcx
0x18001da93  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001da9a  cmovb   rax, rcx
0x18001da9e  mov     rcx, rax; cb
0x18001daa1  call    cs:__imp_CoTaskMemAlloc
0x18001daa7  mov     rdi, rax
0x18001daaa  mov     [rbp+800h+EndPtr], rax
0x18001daae  test    rax, rax
0x18001dab1  jnz     loc_18001DB7A
0x18001dab7  mov     [rbp+800h+var_858], r15
0x18001dabb  or      eax, 0FFFFFFFFh
0x18001dabe  mov     [rsp+930h+var_890], eax
0x18001dac5  mov     [rsp+930h+var_898], eax
0x18001dacc  mov     [rsp+930h+var_8B0], r15d
0x18001dad4  mov     [rsp+930h+var_8B8], r15
0x18001dad9  mov     [rsp+930h+var_8C0], eax
0x18001dadd  mov     [rsp+930h+var_8C8], eax
0x18001dae1  mov     [rsp+930h+var_8D0], r15d
0x18001dae6  mov     [rsp+930h+var_8D8], r15
0x18001daeb  mov     [rsp+930h+var_8E0], r15d
0x18001daf0  lea     rax, word_180034198
0x18001daf7  mov     [rsp+930h+var_8E8], rax
0x18001dafc  mov     [rsp+930h+var_8F0], rax
0x18001db01  mov     [rsp+930h+var_8F8], rax
0x18001db06  mov     [rsp+930h+var_900], rax
0x18001db0b  mov     dword ptr [rsp+930h+var_908], 0C00210CAh
0x18001db13  mov     dword ptr [rsp+930h+var_910], 3
0x18001db1b  mov     r9d, 80210861h
0x18001db21  mov     r8, [r14+0A28h]
0x18001db28  xor     edx, edx
0x18001db2a  lea     rcx, [rbp+800h+var_860]
0x18001db2e  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001db33  nop
0x18001db34  mov     ebx, 64Bh
0x18001db39  mov     r9d, 400000h; unsigned int
0x18001db3f  mov     r8d, ebx; unsigned int
0x18001db42  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001db49  lea     rcx, [rbp+800h+var_860]; this
0x18001db4d  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001db52  nop
0x18001db53  lea     rcx, [rbp+800h+var_860]; this
0x18001db57  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18001db5c  xor     r9d, r9d; unsigned int
0x18001db5f  mov     r8d, ebx; unsigned int
0x18001db62  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x18001db69  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001db70  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001db76  lea     rdi, [rbp+800h+var_830]
0x18001db7a  add     rbx, rbx
0x18001db7d  mov     r8, rbx; Size
0x18001db80  mov     rdx, [rsi+8]; Src
0x18001db84  mov     rcx, rdi; void *
0x18001db87  call    memcpy_0
0x18001db8c  mov     [rbx+rdi], r15w
0x18001db91  mov     [rbp+800h+var_880], r15d
0x18001db95  lea     rbx, aColumnmeta; "COLUMNMETA"
0x18001db9c  mov     [rbp+800h+var_848], rbx
0x18001dba0  lea     rax, [rbp+800h+var_870]
0x18001dba4  mov     [rbp+800h+var_840], rax
0x18001dba8  mov     [rbp+800h+var_838], rdi
0x18001dbac  mov     rcx, [r14+0A30h]
0x18001dbb3  mov     rax, [rcx]
0x18001dbb6  lea     r9, [rbp+800h+var_880]
0x18001dbba  lea     r8, [rbp+800h+var_848]
0x18001dbbe  xor     edx, edx
0x18001dbc0  mov     rax, [rax+18h]
0x18001dbc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbc9  test    eax, eax
0x18001dbcb  jns     loc_18001DC90
0x18001dbd1  mov     [rbp+800h+var_858], r15
0x18001dbd5  or      eax, 0FFFFFFFFh
0x18001dbd8  mov     [rsp+930h+var_890], eax
0x18001dbdf  mov     [rsp+930h+var_898], eax
0x18001dbe6  mov     [rsp+930h+var_8B0], r15d
0x18001dbee  mov     [rsp+930h+var_8B8], r15
0x18001dbf3  mov     [rsp+930h+var_8C0], eax
0x18001dbf7  mov     [rsp+930h+var_8C8], eax
0x18001dbfb  mov     [rsp+930h+var_8D0], r15d
0x18001dc00  mov     [rsp+930h+var_8D8], r15
0x18001dc05  mov     [rsp+930h+var_8E0], r15d
0x18001dc0a  lea     rax, word_180034198
0x18001dc11  mov     [rsp+930h+var_8E8], rax
0x18001dc16  mov     [rsp+930h+var_8F0], rax
0x18001dc1b  mov     [rsp+930h+var_8F8], rbx
0x18001dc20  mov     [rsp+930h+var_900], rdi
0x18001dc25  mov     dword ptr [rsp+930h+var_908], 0C00210D7h
0x18001dc2d  mov     dword ptr [rsp+930h+var_910], 3
0x18001dc35  mov     r9d, 80210861h
0x18001dc3b  mov     r8, [r14+0A28h]
0x18001dc42  xor     edx, edx
0x18001dc44  lea     rcx, [rbp+800h+var_860]
0x18001dc48  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001dc4d  nop
0x18001dc4e  mov     ebx, 65Ah
0x18001dc53  mov     r9d, 400000h; unsigned int
0x18001dc59  mov     r8d, ebx; unsigned int
0x18001dc5c  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001dc63  lea     rcx, [rbp+800h+var_860]; this
0x18001dc67  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001dc6c  nop
0x18001dc6d  lea     rcx, [rbp+800h+var_860]; this
0x18001dc71  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18001dc76  xor     r9d, r9d; unsigned int
0x18001dc79  mov     r8d, ebx; unsigned int
0x18001dc7c  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x18001dc83  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001dc8a  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001dc90  mov     [rbp+800h+var_850], r15
0x18001dc94  mov     [rbp+800h+var_868], 4
0x18001dc9b  mov     rcx, [r14+0A30h]
0x18001dca2  mov     rax, [rcx]
0x18001dca5  lea     rdx, [rbp+800h+var_850]
0x18001dca9  mov     [rsp+930h+var_908], rdx
0x18001dcae  mov     [rsp+930h+var_910], r15
0x18001dcb3  lea     r9, [rbp+800h+var_868]
0x18001dcb7  mov     r8d, 1
0x18001dcbd  mov     edx, [rbp+800h+var_880]
0x18001dcc0  mov     rax, [rax+20h]
0x18001dcc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcc9  mov     rax, [rbp+800h+var_850]
0x18001dccd  mov     ebx, [rax]
0x18001dccf  lea     rcx, [rbp+800h+EndPtr]; void *
0x18001dcd3  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x18001dcd8  mov     eax, ebx
0x18001dcda  mov     rcx, [rbp+800h+var_30]
0x18001dce1  xor     rcx, rsp; StackCookie
0x18001dce4  call    __security_check_cookie
0x18001dce9  mov     rbx, [rsp+930h+arg_10]
0x18001dcf1  add     rsp, 910h
0x18001dcf8  pop     r15
0x18001dcfa  pop     r14
0x18001dcfc  pop     rdi
0x18001dcfd  pop     rsi
0x18001dcfe  pop     rbp
0x18001dcff  retn
```
