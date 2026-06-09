# TMetabaseMetaXmlFile::AddStringToHeap(TMetabaseMetaXmlFile::TSizedString const &)

- ea: `0x18001b188`
- end: `0x18001b34c`
- name: `?AddStringToHeap@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@@Z`
- size: `452`
- prototype: `unsigned int __fastcall(TMetabaseMetaXmlFile *__hidden this, const struct TMetabaseMetaXmlFile::TSizedString *)`
- caller_count: `6`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019554`
- `0x180019f9c`
- `0x18001b354`
- `0x18001b628`
- `0x18001c240`
- `0x18001c86c`

## callees

- `0x180002bc4`
- `0x180005870`
- `0x180011b38`
- `0x180012734`
- `0x180017ad8`
- `0x18001b188`
- `0x18002e0b2`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18001b1f8`
- `ole32!CoTaskMemAlloc` at `0x18001b1f8`

## string_xrefs

- `0x18001b2a2`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001b2d1`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001b2ca`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TMetabaseMetaXmlFile::AddStringToHeap(
        TMetabaseMetaXmlFile *this,
        const struct TMetabaseMetaXmlFile::TSizedString *a2)
{
  __int64 v5; // rbx
  unsigned int v6; // ebp
  char *v7; // rdi
  size_t v8; // rbx
  __int64 v9; // [rsp+88h] [rbp-870h]
  __int64 v10; // [rsp+90h] [rbp-868h]
  char *v11; // [rsp+B0h] [rbp-848h] BYREF
  _BYTE v12[8]; // [rsp+B8h] [rbp-840h] BYREF
  __int64 v13; // [rsp+C0h] [rbp-838h]
  char v14; // [rsp+D0h] [rbp-828h] BYREF

  if ( !*((_QWORD *)a2 + 1) )
    return 0;
  v11 = 0;
  v5 = *(unsigned int *)a2;
  v6 = v5 + 1;
  if ( (unsigned int)v5 < 0x400 )
  {
    v7 = &v14;
  }
  else
  {
    v7 = (char *)CoTaskMemAlloc(saturated_mul(v6, 2u));
    v11 = v7;
    if ( !v7 )
    {
      v13 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v12,
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
        v9,
        v10,
        -1,
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v12,
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        1277,
        0x400000);
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v12);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
        0x4FDu,
        0);
    }
  }
  v8 = 2 * v5;
  memcpy_0(v7, *((const void **)a2 + 1), v8);
  *(_WORD *)&v7[v8] = 0;
  LODWORD(v8) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, char *, _QWORD))(*(_QWORD *)this + 40LL))(
                  this,
                  v7,
                  v6);
  TSmartPointerArray<bool>::~TSmartPointerArray<bool>((LPVOID *)&v11);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001b188  mov     [rsp+arg_10], rbx
0x18001b18d  mov     [rsp+arg_18], rbp
0x18001b192  push    rsi
0x18001b193  push    rdi
0x18001b194  push    r14
0x18001b196  sub     rsp, 8E0h
0x18001b19d  mov     rax, cs:__security_cookie
0x18001b1a4  xor     rax, rsp
0x18001b1a7  mov     [rsp+8F8h+var_28], rax
0x18001b1af  mov     rsi, rdx
0x18001b1b2  mov     r14, rcx
0x18001b1b5  cmp     qword ptr [rdx+8], 0
0x18001b1ba  jnz     short loc_18001B1C3
0x18001b1bc  xor     eax, eax
0x18001b1be  jmp     loc_18001B324
0x18001b1c3  mov     [rsp+8F8h+var_848], 0
0x18001b1cf  mov     ebx, [rdx]
0x18001b1d1  lea     ebp, [rbx+1]
0x18001b1d4  cmp     ebx, 400h
0x18001b1da  jb      loc_18001B2DE
0x18001b1e0  mov     ecx, ebp
0x18001b1e2  mov     eax, 2
0x18001b1e7  mul     rcx
0x18001b1ea  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001b1f1  cmovb   rax, rcx
0x18001b1f5  mov     rcx, rax; cb
0x18001b1f8  call    cs:__imp_CoTaskMemAlloc
0x18001b1fe  mov     rdi, rax
0x18001b201  mov     [rsp+8F8h+var_848], rax
0x18001b209  test    rax, rax
0x18001b20c  jnz     loc_18001B2E6
0x18001b212  mov     [rsp+8F8h+var_838], rax
0x18001b21a  or      eax, 0FFFFFFFFh
0x18001b21d  mov     [rsp+8F8h+var_858], eax
0x18001b224  mov     [rsp+8F8h+var_860], eax
0x18001b22b  mov     [rsp+8F8h+var_878], edi
0x18001b232  mov     [rsp+8F8h+var_880], rdi
0x18001b237  mov     [rsp+8F8h+var_888], eax
0x18001b23b  mov     [rsp+8F8h+var_890], eax
0x18001b23f  mov     [rsp+8F8h+var_898], edi
0x18001b243  mov     [rsp+8F8h+var_8A0], rdi
0x18001b248  mov     [rsp+8F8h+var_8A8], edi
0x18001b24c  lea     rax, word_180034198
0x18001b253  mov     [rsp+8F8h+var_8B0], rax
0x18001b258  mov     [rsp+8F8h+var_8B8], rax
0x18001b25d  mov     [rsp+8F8h+var_8C0], rax
0x18001b262  mov     [rsp+8F8h+var_8C8], rax
0x18001b267  mov     [rsp+8F8h+var_8D0], 0C00210CAh
0x18001b26f  mov     [rsp+8F8h+var_8D8], 3
0x18001b277  mov     r9d, 80210861h
0x18001b27d  mov     r8, [r14+0A28h]
0x18001b284  xor     edx, edx
0x18001b286  lea     rcx, [rsp+8F8h+var_840]
0x18001b28e  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001b293  nop
0x18001b294  mov     ebx, 4FDh
0x18001b299  mov     r9d, 400000h; unsigned int
0x18001b29f  mov     r8d, ebx; unsigned int
0x18001b2a2  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001b2a9  lea     rcx, [rsp+8F8h+var_840]; this
0x18001b2b1  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001b2b6  nop
0x18001b2b7  lea     rcx, [rsp+8F8h+var_840]; this
0x18001b2bf  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18001b2c4  xor     r9d, r9d; unsigned int
0x18001b2c7  mov     r8d, ebx; unsigned int
0x18001b2ca  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x18001b2d1  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001b2d8  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001b2de  lea     rdi, [rsp+8F8h+var_828]
0x18001b2e6  add     rbx, rbx
0x18001b2e9  mov     r8, rbx; Size
0x18001b2ec  mov     rdx, [rsi+8]; Src
0x18001b2f0  mov     rcx, rdi; void *
0x18001b2f3  call    memcpy_0
0x18001b2f8  xor     eax, eax
0x18001b2fa  mov     [rbx+rdi], ax
0x18001b2fe  mov     rax, [r14]
0x18001b301  mov     r8d, ebp
0x18001b304  mov     rdx, rdi
0x18001b307  mov     rcx, r14
0x18001b30a  mov     rax, [rax+28h]
0x18001b30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b313  mov     ebx, eax
0x18001b315  lea     rcx, [rsp+8F8h+var_848]; void *
0x18001b31d  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x18001b322  mov     eax, ebx
0x18001b324  mov     rcx, [rsp+8F8h+var_28]
0x18001b32c  xor     rcx, rsp; StackCookie
0x18001b32f  call    __security_check_cookie
0x18001b334  lea     r11, [rsp+8F8h+var_18]
0x18001b33c  mov     rbx, [r11+30h]
0x18001b340  mov     rbp, [r11+38h]
0x18001b344  mov     rsp, r11
0x18001b347  pop     r14
0x18001b349  pop     rdi
0x18001b34a  pop     rsi
0x18001b34b  retn
```
