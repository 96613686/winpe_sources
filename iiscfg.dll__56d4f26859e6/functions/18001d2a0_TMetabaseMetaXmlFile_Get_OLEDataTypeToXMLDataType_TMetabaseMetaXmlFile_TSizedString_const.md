# TMetabaseMetaXmlFile::Get_OLEDataTypeToXMLDataType(TMetabaseMetaXmlFile::TSizedString const &)

- ea: `0x18001d2a0`
- end: `0x18001d47f`
- name: `?Get_OLEDataTypeToXMLDataType@TMetabaseMetaXmlFile@@AEAAPEBUTOLEDataTypeToXMLDataType@@AEBUTSizedString@1@@Z`
- size: `479`
- prototype: `const struct TOLEDataTypeToXMLDataType *__fastcall(TMetabaseMetaXmlFile *__hidden this, const struct TMetabaseMetaXmlFile::TSizedString *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019554`

## callees

- `0x180001b78`
- `0x180002bc4`
- `0x180011b38`
- `0x180012734`
- `0x180017ad8`
- `0x18001d2a0`
- `0x18002e110`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001d36b`
- `msvcrt!memcpy_s` at `0x18001d36b`

## string_xrefs

- `0x18001d443`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001d472`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001d46b`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct TOLEDataTypeToXMLDataType near **__fastcall TMetabaseMetaXmlFile::Get_OLEDataTypeToXMLDataType(
        TMetabaseMetaXmlFile *this,
        const struct TMetabaseMetaXmlFile::TSizedString *a2)
{
  struct TOLEDataTypeToXMLDataType near **v3; // r8
  void *v4; // rsi
  __int64 v5; // rdi
  struct TOLEDataTypeToXMLDataType near *v6; // r9
  __int16 *v7; // rbx
  unsigned int i; // r10d
  __int16 v9; // r11
  __int16 v10; // dx
  __int16 v11; // cx
  __int64 v13; // rcx
  __int64 v14; // [rsp+88h] [rbp-860h]
  __int64 v15; // [rsp+90h] [rbp-858h]
  _BYTE v16[8]; // [rsp+B0h] [rbp-838h] BYREF
  __int64 v17; // [rsp+B8h] [rbp-830h]
  wchar_t Destination[1024]; // [rsp+C0h] [rbp-828h] BYREF

  v3 = &OLEDataTypeToXMLDataType;
  v4 = (void *)*((_QWORD *)a2 + 1);
  v5 = *(unsigned int *)a2;
LABEL_2:
  v6 = *v3;
  if ( !*v3 )
  {
    memcpy_s(Destination, 0x800u, v4, 2 * v5);
    if ( (unsigned int)v5 >= 0x3FF )
    {
      v13 = 1023;
    }
    else
    {
      v13 = v5;
      if ( (unsigned __int64)(2 * v5) >= 0x800 )
        _report_rangecheckfailure();
    }
    Destination[v13] = 0;
    v17 = 0;
    CErrorInterceptor::Init(
      (CErrorInterceptor *)v16,
      0,
      *((_QWORD *)this + 325),
      0x80210861,
      3u,
      -1073606444,
      Destination,
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
      v14,
      v15,
      -1,
      -1);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v16,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      1500,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v16);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0x5DCu,
      0);
  }
  v7 = (__int16 *)v4;
  for ( i = 0; ; ++i )
  {
    v9 = *(_WORD *)v6;
    if ( i >= (unsigned int)v5 )
      break;
    v10 = *v7 + 32;
    if ( (unsigned __int16)(*v7 - 65) > 0x19u )
      v10 = *v7;
    v11 = v9 + 32;
    if ( (unsigned __int16)(v9 - 65) > 0x19u )
      v11 = *(_WORD *)v6;
    if ( v11 != v10 )
    {
LABEL_12:
      v3 += 5;
      goto LABEL_2;
    }
    ++v7;
    v6 = (struct TOLEDataTypeToXMLDataType near *)((char *)v6 + 2);
  }
  if ( v9 )
    goto LABEL_12;
  return v3;
}

```

## disassembly

```asm
0x18001d2a0  mov     [rsp+arg_10], rbx
0x18001d2a5  push    rbp
0x18001d2a6  push    rsi
0x18001d2a7  push    rdi
0x18001d2a8  sub     rsp, 8D0h
0x18001d2af  mov     rax, cs:__security_cookie
0x18001d2b6  xor     rax, rsp
0x18001d2b9  mov     [rsp+8E8h+var_28], rax
0x18001d2c1  mov     rbp, rcx
0x18001d2c4  lea     r8, ?OLEDataTypeToXMLDataType@@3PAUTOLEDataTypeToXMLDataType@@A; TOLEDataTypeToXMLDataType near * OLEDataTypeToXMLDataType
0x18001d2cb  mov     rsi, [rdx+8]
0x18001d2cf  mov     edi, [rdx]
0x18001d2d1  mov     r9, [r8]
0x18001d2d4  test    r9, r9
0x18001d2d7  jz      short loc_18001D355
0x18001d2d9  mov     rbx, rsi
0x18001d2dc  xor     r10d, r10d
0x18001d2df  movzx   r11d, word ptr [r9]
0x18001d2e3  cmp     r10d, edi
0x18001d2e6  jnb     short loc_18001D321
0x18001d2e8  movzx   eax, word ptr [rbx]
0x18001d2eb  sub     ax, 41h ; 'A'
0x18001d2ef  movzx   edx, word ptr [rbx]
0x18001d2f2  add     dx, 20h ; ' '
0x18001d2f6  cmp     ax, 19h
0x18001d2fa  cmova   dx, [rbx]
0x18001d2fe  lea     eax, [r11-41h]
0x18001d302  lea     ecx, [r11+20h]
0x18001d306  cmp     ax, 19h
0x18001d30a  cmova   cx, r11w
0x18001d30f  cmp     cx, dx
0x18001d312  jnz     short loc_18001D329
0x18001d314  inc     r10d
0x18001d317  add     rbx, 2
0x18001d31b  add     r9, 2
0x18001d31f  jmp     short loc_18001D2DF
0x18001d321  xor     eax, eax
0x18001d323  cmp     ax, r11w
0x18001d327  jz      short loc_18001D32F
0x18001d329  add     r8, 28h ; '('
0x18001d32d  jmp     short loc_18001D2D1
0x18001d32f  mov     rax, r8
0x18001d332  mov     rcx, [rsp+8E8h+var_28]
0x18001d33a  xor     rcx, rsp; StackCookie
0x18001d33d  call    __security_check_cookie
0x18001d342  mov     rbx, [rsp+8E8h+arg_10]
0x18001d34a  add     rsp, 8D0h
0x18001d351  pop     rdi
0x18001d352  pop     rsi
0x18001d353  pop     rbp
0x18001d354  retn
0x18001d355  lea     r9, [rdi+rdi]; SourceSize
0x18001d359  mov     r8, rsi; Source
0x18001d35c  mov     esi, 800h
0x18001d361  mov     edx, esi; DestinationSize
0x18001d363  lea     rcx, [rsp+8E8h+Destination]; Destination
0x18001d36b  call    cs:__imp_memcpy_s
0x18001d371  cmp     edi, 3FFh
0x18001d377  jnb     short loc_18001D388
0x18001d379  lea     rcx, [rdi+rdi]
0x18001d37d  cmp     rcx, rsi
0x18001d380  jb      short loc_18001D38D
0x18001d382  call    __report_rangecheckfailure
0x18001d388  mov     ecx, 7FEh
0x18001d38d  xor     eax, eax
0x18001d38f  mov     [rsp+rcx+8E8h+Destination], ax
0x18001d397  mov     [rsp+8E8h+var_830], rax
0x18001d39f  or      eax, 0FFFFFFFFh
0x18001d3a2  mov     [rsp+8E8h+var_848], eax
0x18001d3a9  mov     [rsp+8E8h+var_850], eax
0x18001d3b0  mov     [rsp+8E8h+var_868], 0
0x18001d3bb  mov     [rsp+8E8h+var_870], 0
0x18001d3c4  mov     [rsp+8E8h+var_878], eax
0x18001d3c8  mov     [rsp+8E8h+var_880], eax
0x18001d3cc  mov     [rsp+8E8h+var_888], 0
0x18001d3d4  mov     [rsp+8E8h+var_890], 0
0x18001d3dd  mov     [rsp+8E8h+var_898], 0
0x18001d3e5  lea     rax, word_180034198
0x18001d3ec  mov     [rsp+8E8h+var_8A0], rax
0x18001d3f1  mov     [rsp+8E8h+var_8A8], rax
0x18001d3f6  mov     [rsp+8E8h+var_8B0], rax
0x18001d3fb  lea     rax, [rsp+8E8h+Destination]
0x18001d403  mov     [rsp+8E8h+var_8B8], rax
0x18001d408  mov     [rsp+8E8h+var_8C0], 0C00210D4h
0x18001d410  mov     [rsp+8E8h+var_8C8], 3
0x18001d418  mov     r9d, 80210861h
0x18001d41e  mov     r8, [rbp+0A28h]
0x18001d425  xor     edx, edx
0x18001d427  lea     rcx, [rsp+8E8h+var_838]
0x18001d42f  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001d434  nop
0x18001d435  mov     ebx, 5DCh
0x18001d43a  mov     r9d, 400000h; unsigned int
0x18001d440  mov     r8d, ebx; unsigned int
0x18001d443  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001d44a  lea     rcx, [rsp+8E8h+var_838]; this
0x18001d452  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001d457  nop
0x18001d458  lea     rcx, [rsp+8E8h+var_838]; this
0x18001d460  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18001d465  xor     r9d, r9d; unsigned int
0x18001d468  mov     r8d, ebx; unsigned int
0x18001d46b  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x18001d472  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001d479  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
```
