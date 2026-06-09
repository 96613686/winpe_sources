# TMetabaseMetaXmlFile::StringToFlagValue(TMetabaseMetaXmlFile::TSizedString const &,ushort const *,ulong)

- ea: `0x18001dd08`
- end: `0x18001dff7`
- name: `?StringToFlagValue@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@PEBGK@Z`
- size: `751`
- prototype: `unsigned int __fastcall(TMetabaseMetaXmlFile *__hidden this, const struct TMetabaseMetaXmlFile::TSizedString *, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019554`
- `0x18001b354`
- `0x18001bc88`

## callees

- `0x180001e88`
- `0x180002bc4`
- `0x180005870`
- `0x180011b38`
- `0x180012734`
- `0x180017ad8`
- `0x18001dd08`
- `0x18002e0b2`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18001dd7d`
- `ole32!CoTaskMemAlloc` at `0x18001dd7d`

## string_xrefs

- `0x18001de1e`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001de45`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001df5f`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001de3e`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TMetabaseMetaXmlFile::StringToFlagValue(
        TMetabaseMetaXmlFile *this,
        const struct TMetabaseMetaXmlFile::TSizedString *a2,
        const unsigned __int16 *a3,
        int a4)
{
  __int64 v8; // rbx
  char *v9; // rdi
  size_t v10; // rbx
  unsigned int v11; // esi
  wchar_t **v12; // r8
  wchar_t *v13; // rbx
  wchar_t **v14; // r8
  __int64 v15; // [rsp+88h] [rbp-A8h]
  __int64 v16; // [rsp+90h] [rbp-A0h]
  unsigned int v17; // [rsp+B0h] [rbp-80h] BYREF
  int v18; // [rsp+B4h] [rbp-7Ch] BYREF
  _BYTE v19[8]; // [rsp+B8h] [rbp-78h] BYREF
  __int64 v20; // [rsp+C0h] [rbp-70h]
  _DWORD *i; // [rsp+C8h] [rbp-68h] BYREF
  char *v22; // [rsp+D0h] [rbp-60h] BYREF
  _QWORD v23[2]; // [rsp+D8h] [rbp-58h] BYREF
  wchar_t *v24; // [rsp+E8h] [rbp-48h]
  char v25; // [rsp+F0h] [rbp-40h] BYREF
  int v26; // [rsp+968h] [rbp+838h] BYREF

  v26 = a4;
  if ( !*((_QWORD *)a2 + 1) )
    return 0;
  v22 = 0;
  v8 = *(unsigned int *)a2;
  if ( (unsigned int)v8 < 0x400 )
  {
    v9 = &v25;
  }
  else
  {
    v9 = (char *)CoTaskMemAlloc(saturated_mul((unsigned int)(v8 + 1), 2u));
    v22 = v9;
    if ( !v9 )
    {
      v20 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v19,
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
        v15,
        v16,
        -1,
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v19,
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        1654,
        0x400000);
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v19);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
        0x676u,
        0);
    }
  }
  v10 = 2 * v8;
  memcpy_0(v9, *((const void **)a2 + 1), v10);
  *(_WORD *)&v9[v10] = 0;
  v11 = 0;
  v13 = wcstok_mvcrt_legacy_two_parameter_form((wchar_t *)v9, L" |,", v12);
  v17 = 0;
  v24 = 0;
  v23[0] = a3;
  v23[1] = &v26;
  v18 = 4;
  for ( i = 0; v13; v13 = wcstok_mvcrt_legacy_two_parameter_form(0, L" ,|", v14) )
  {
    v24 = v13;
    if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD *, unsigned int *))(**((_QWORD **)this + 326) + 24LL))(
           *((_QWORD *)this + 326),
           0,
           v23,
           &v17) >= 0 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64, int *, _QWORD, _DWORD **))(**((_QWORD **)this + 326) + 32LL))(
        *((_QWORD *)this + 326),
        v17,
        1,
        &v18,
        0,
        &i);
      v11 |= *i;
    }
    else
    {
      v20 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v19,
        0,
        *((_QWORD *)this + 325),
        0x80210861,
        3u,
        -2147348264,
        v13,
        a3,
        &word_180034198,
        &word_180034198,
        0,
        0,
        0,
        -1,
        -1,
        0,
        0,
        v15,
        v16,
        -1,
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v19,
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        1677,
        0x400000);
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v19);
    }
  }
  TSmartPointerArray<bool>::~TSmartPointerArray<bool>((LPVOID *)&v22);
  return v11;
}

```

## disassembly

```asm
0x18001dd08  mov     [rsp-8+arg_18], r9d
0x18001dd0d  push    rbp
0x18001dd0e  push    rbx
0x18001dd0f  push    rsi
0x18001dd10  push    rdi
0x18001dd11  push    r12
0x18001dd13  push    r13
0x18001dd15  push    r14
0x18001dd17  push    r15
0x18001dd19  lea     rbp, [rsp-7D8h]
0x18001dd21  sub     rsp, 908h
0x18001dd28  mov     rax, cs:__security_cookie
0x18001dd2f  xor     rax, rsp
0x18001dd32  mov     [rbp+810h+var_50], rax
0x18001dd39  mov     r12, r8
0x18001dd3c  mov     rsi, rdx
0x18001dd3f  mov     r15, rcx
0x18001dd42  xor     r13d, r13d
0x18001dd45  cmp     [rdx+8], r13
0x18001dd49  jnz     short loc_18001DD52
0x18001dd4b  xor     eax, eax
0x18001dd4d  jmp     loc_18001DFD4
0x18001dd52  mov     [rbp+810h+var_870], r13
0x18001dd56  mov     ebx, [rdx]
0x18001dd58  cmp     ebx, 400h
0x18001dd5e  jb      loc_18001DE52
0x18001dd64  lea     ecx, [rbx+1]
0x18001dd67  mov     eax, 2
0x18001dd6c  mul     rcx
0x18001dd6f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001dd76  cmovb   rax, rcx
0x18001dd7a  mov     rcx, rax; cb
0x18001dd7d  call    cs:__imp_CoTaskMemAlloc
0x18001dd83  mov     rdi, rax
0x18001dd86  mov     [rbp+810h+var_870], rax
0x18001dd8a  test    rax, rax
0x18001dd8d  jnz     loc_18001DE56
0x18001dd93  mov     [rbp+810h+var_880], r13
0x18001dd97  or      edi, 0FFFFFFFFh
0x18001dd9a  mov     [rsp+940h+var_8A0], edi
0x18001dda1  mov     [rsp+940h+var_8A8], edi
0x18001dda8  mov     [rsp+940h+var_8C0], r13d
0x18001ddb0  mov     [rsp+940h+var_8C8], r13
0x18001ddb5  mov     [rsp+940h+var_8D0], edi
0x18001ddb9  mov     [rsp+940h+var_8D8], edi
0x18001ddbd  mov     [rsp+940h+var_8E0], r13d
0x18001ddc2  mov     [rsp+940h+var_8E8], r13
0x18001ddc7  mov     [rsp+940h+var_8F0], r13d
0x18001ddcc  lea     r14, word_180034198
0x18001ddd3  mov     [rsp+940h+var_8F8], r14
0x18001ddd8  mov     [rsp+940h+var_900], r14
0x18001dddd  mov     [rsp+940h+var_908], r14
0x18001dde2  mov     [rsp+940h+var_910], r14
0x18001dde7  mov     dword ptr [rsp+940h+var_918], 0C00210CAh
0x18001ddef  mov     dword ptr [rsp+940h+var_920], 3
0x18001ddf7  mov     r9d, 80210861h
0x18001ddfd  mov     r8, [r15+0A28h]
0x18001de04  xor     edx, edx
0x18001de06  lea     rcx, [rbp+810h+var_888]
0x18001de0a  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001de0f  nop
0x18001de10  mov     ebx, 676h
0x18001de15  mov     r9d, 400000h; unsigned int
0x18001de1b  mov     r8d, ebx; unsigned int
0x18001de1e  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001de25  lea     rcx, [rbp+810h+var_888]; this
0x18001de29  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001de2e  nop
0x18001de2f  lea     rcx, [rbp+810h+var_888]; this
0x18001de33  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18001de38  xor     r9d, r9d; unsigned int
0x18001de3b  mov     r8d, ebx; unsigned int
0x18001de3e  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x18001de45  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001de4c  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001de52  lea     rdi, [rbp+810h+var_850]
0x18001de56  add     rbx, rbx
0x18001de59  mov     r8, rbx; Size
0x18001de5c  mov     rdx, [rsi+8]; Src
0x18001de60  mov     rcx, rdi; void *
0x18001de63  call    memcpy_0
0x18001de68  mov     [rbx+rdi], r13w
0x18001de6d  mov     esi, r13d
0x18001de70  lea     rdx, asc_1800365D8; " |,"
0x18001de77  mov     rcx, rdi; String
0x18001de7a  call    wcstok_mvcrt_legacy_two_parameter_form
0x18001de7f  mov     rbx, rax
0x18001de82  mov     [rbp+810h+var_890], r13d
0x18001de86  mov     [rbp+810h+var_858], r13
0x18001de8a  mov     [rbp+810h+var_868], r12
0x18001de8e  lea     rax, [rbp+810h+arg_18]
0x18001de95  mov     [rbp+810h+var_860], rax
0x18001de99  mov     [rbp+810h+var_88C], 4
0x18001dea0  mov     [rbp+810h+var_878], r13
0x18001dea4  test    rbx, rbx
0x18001dea7  jz      loc_18001DFC9
0x18001dead  or      edi, 0FFFFFFFFh
0x18001deb0  lea     r14, word_180034198
0x18001deb7  mov     [rbp+810h+var_858], rbx
0x18001debb  mov     rcx, [r15+0A30h]
0x18001dec2  mov     rax, [rcx]
0x18001dec5  lea     r9, [rbp+810h+var_890]
0x18001dec9  lea     r8, [rbp+810h+var_868]
0x18001decd  xor     edx, edx
0x18001decf  mov     rax, [rax+18h]
0x18001ded3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ded8  test    eax, eax
0x18001deda  jns     loc_18001DF7B
0x18001dee0  mov     [rbp+810h+var_880], r13
0x18001dee4  mov     [rsp+940h+var_8A0], edi
0x18001deeb  mov     [rsp+940h+var_8A8], edi
0x18001def2  mov     [rsp+940h+var_8C0], r13d
0x18001defa  mov     [rsp+940h+var_8C8], r13
0x18001deff  mov     [rsp+940h+var_8D0], edi
0x18001df03  mov     [rsp+940h+var_8D8], edi
0x18001df07  mov     [rsp+940h+var_8E0], r13d
0x18001df0c  mov     [rsp+940h+var_8E8], r13
0x18001df11  mov     [rsp+940h+var_8F0], r13d
0x18001df16  mov     [rsp+940h+var_8F8], r14
0x18001df1b  mov     [rsp+940h+var_900], r14
0x18001df20  mov     [rsp+940h+var_908], r12
0x18001df25  mov     [rsp+940h+var_910], rbx
0x18001df2a  mov     dword ptr [rsp+940h+var_918], 800210D8h
0x18001df32  mov     dword ptr [rsp+940h+var_920], 3
0x18001df3a  mov     r9d, 80210861h
0x18001df40  mov     r8, [r15+0A28h]
0x18001df47  xor     edx, edx
0x18001df49  lea     rcx, [rbp+810h+var_888]
0x18001df4d  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001df52  nop
0x18001df53  mov     r9d, 400000h; unsigned int
0x18001df59  mov     r8d, 68Dh; unsigned int
0x18001df5f  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001df66  lea     rcx, [rbp+810h+var_888]; this
0x18001df6a  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001df6f  nop
0x18001df70  lea     rcx, [rbp+810h+var_888]; this
0x18001df74  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18001df79  jmp     short loc_18001DFAF
0x18001df7b  mov     rcx, [r15+0A30h]
0x18001df82  mov     rax, [rcx]
0x18001df85  lea     rdx, [rbp+810h+var_878]
0x18001df89  mov     [rsp+940h+var_918], rdx
0x18001df8e  mov     [rsp+940h+var_920], r13
0x18001df93  lea     r9, [rbp+810h+var_88C]
0x18001df97  mov     r8d, 1
0x18001df9d  mov     edx, [rbp+810h+var_890]
0x18001dfa0  mov     rax, [rax+20h]
0x18001dfa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfa9  mov     rax, [rbp+810h+var_878]
0x18001dfad  or      esi, [rax]
0x18001dfaf  lea     rdx, asc_1800365E0; " ,|"
0x18001dfb6  xor     ecx, ecx; String
0x18001dfb8  call    wcstok_mvcrt_legacy_two_parameter_form
0x18001dfbd  mov     rbx, rax
0x18001dfc0  test    rax, rax
0x18001dfc3  jnz     loc_18001DEB7
0x18001dfc9  lea     rcx, [rbp+810h+var_870]; void *
0x18001dfcd  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x18001dfd2  mov     eax, esi
0x18001dfd4  mov     rcx, [rbp+810h+var_50]
0x18001dfdb  xor     rcx, rsp; StackCookie
0x18001dfde  call    __security_check_cookie
0x18001dfe3  add     rsp, 908h
0x18001dfea  pop     r15
0x18001dfec  pop     r14
0x18001dfee  pop     r13
0x18001dff0  pop     r12
0x18001dff2  pop     rdi
0x18001dff3  pop     rsi
0x18001dff4  pop     rbx
0x18001dff5  pop     rbp
0x18001dff6  retn
```
