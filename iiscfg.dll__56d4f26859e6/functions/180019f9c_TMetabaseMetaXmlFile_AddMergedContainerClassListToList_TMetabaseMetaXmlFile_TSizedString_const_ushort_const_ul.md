# TMetabaseMetaXmlFile::AddMergedContainerClassListToList(TMetabaseMetaXmlFile::TSizedString const *,ushort const *,ulong,bool &)

- ea: `0x180019f9c`
- end: `0x18001a2da`
- name: `?AddMergedContainerClassListToList@TMetabaseMetaXmlFile@@AEAAKPEBUTSizedString@1@PEBGKAEA_N@Z`
- size: `830`
- prototype: `unsigned int __usercall@<eax>(TMetabaseMetaXmlFile *__hidden this@<rcx>, const struct TMetabaseMetaXmlFile::TSizedString *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001aac4`

## callees

- `0x180001e88`
- `0x180002bc4`
- `0x180005870`
- `0x180011b38`
- `0x180012734`
- `0x180017ad8`
- `0x180019f9c`
- `0x18001b188`
- `0x18002e0a6`
- `0x18002e0b2`
- `0x180030010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18001a14d`
- `msvcrt!wcscpy_s` at `0x18001a14d`
- `msvcrt!wcsstr` at `0x18001a131`
- `msvcrt!wcsstr` at `0x18001a131`
- `ole32!CoTaskMemAlloc` at `0x18001a046`
- `ole32!CoTaskMemAlloc` at `0x18001a06b`
- `ole32!CoTaskMemAlloc` at `0x18001a046`
- `ole32!CoTaskMemAlloc` at `0x18001a06b`

## string_xrefs

- `0x18001a25f`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001a28e`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001a287`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned int __fastcall TMetabaseMetaXmlFile::AddMergedContainerClassListToList(
        TMetabaseMetaXmlFile *this,
        const struct TMetabaseMetaXmlFile::TSizedString *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        bool *a5)
{
  __int64 v5; // rbp
  TMetabaseMetaXmlFile *v8; // r14
  bool *v9; // r12
  const void *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // r13
  void *v13; // rbx
  wchar_t *v14; // rax
  wchar_t *v15; // rdi
  wchar_t **v16; // r8
  wchar_t *v17; // rdi
  int v18; // r14d
  __int64 v19; // rsi
  __int64 v20; // r15
  wchar_t **v21; // r8
  int v22; // ebx
  void *v24; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v25[8]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v26; // [rsp+C0h] [rbp-48h]
  wchar_t *v28; // [rsp+118h] [rbp+10h] BYREF

  v5 = a4;
  v8 = this;
  v9 = a5;
  *a5 = 0;
  if ( !a2 )
    return (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v8 + 40LL))(
             v8,
             a3,
             (unsigned int)v5);
  v10 = (const void *)*((_QWORD *)a2 + 1);
  if ( !v10 )
    return (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v8 + 40LL))(
             v8,
             a3,
             (unsigned int)v5);
  v11 = *(_DWORD *)a2;
  if ( !*(_DWORD *)a2 )
    return (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v8 + 40LL))(
             v8,
             a3,
             (unsigned int)v5);
  if ( !a4 || !a3 )
  {
    *v9 = 1;
    return TMetabaseMetaXmlFile::AddStringToHeap(v8, a2);
  }
  v12 = a4 - 1;
  if ( v11 == (_DWORD)v12 && !memcmp_0(v10, a3, 2LL * v11) )
    return (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v8 + 40LL))(
             v8,
             a3,
             (unsigned int)v5);
  LODWORD(a5) = v5 + v11 + 2;
  v13 = CoTaskMemAlloc(saturated_mul((unsigned int)a5, 2u));
  v24 = v13;
  v14 = (wchar_t *)CoTaskMemAlloc(saturated_mul((unsigned int)(*(_DWORD *)a2 + 2), 2u));
  v15 = v14;
  v28 = v14;
  if ( !v13 || !v14 )
  {
    v26 = 0;
    CErrorInterceptor::Init(
      v25,
      0,
      *((_QWORD *)v8 + 325),
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
      (CErrorInterceptor *)v25,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      1020,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v25);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0x3FCu,
      0);
  }
  memcpy_0(v14, *((const void **)a2 + 1), 2LL * *(unsigned int *)a2);
  v15[*(unsigned int *)a2] = 0;
  v15[*(_DWORD *)a2 + 1] = 0;
  memcpy_0(v13, a3, 2 * v5);
  *((_WORD *)v13 + v12) = 44;
  *((_WORD *)v13 + v5) = 0;
  v17 = wcstok_mvcrt_legacy_two_parameter_form(v15, L",", v16);
  if ( v17 )
  {
    v18 = (int)a5;
    do
    {
      v19 = -1;
      do
        ++v19;
      while ( v17[v19] );
      v20 = (unsigned int)(v19 + 1);
      LOWORD(a5) = v17[v20];
      v17[v20] = 0;
      v17[(unsigned int)v19] = 44;
      if ( !wcsstr((const wchar_t *)v13, v17) )
      {
        *v9 = 1;
        wcscpy_s((wchar_t *)v13 + v5, (unsigned int)(v18 - v5), v17);
        v5 = (unsigned int)(v19 + v5 + 1);
      }
      v17[v20] = (unsigned __int16)a5;
      v17[(unsigned int)v19] = 0;
      v17 = wcstok_mvcrt_legacy_two_parameter_form(0, L",", v21);
    }
    while ( v17 );
    v8 = this;
  }
  *((_WORD *)v13 + (unsigned int)(v5 - 1)) = 0;
  v22 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, void *, _QWORD))(*(_QWORD *)v8 + 40LL))(
          v8,
          v13,
          (unsigned int)v5);
  TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v28);
  TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v24);
  return v22;
}

```

## disassembly

```asm
0x180019f9c  mov     [rsp+arg_10], rbx
0x180019fa1  mov     [rsp+arg_0], rcx
0x180019fa6  push    rbp
0x180019fa7  push    rsi
0x180019fa8  push    rdi
0x180019fa9  push    r12
0x180019fab  push    r13
0x180019fad  push    r14
0x180019faf  push    r15
0x180019fb1  sub     rsp, 0D0h
0x180019fb8  mov     ebp, r9d
0x180019fbb  mov     r15, r8
0x180019fbe  mov     rsi, rdx
0x180019fc1  mov     r14, rcx
0x180019fc4  xor     edi, edi
0x180019fc6  mov     r12, [rsp+108h+arg_20]
0x180019fce  mov     [r12], dil
0x180019fd2  test    rdx, rdx
0x180019fd5  jz      loc_18001A2AA
0x180019fdb  mov     rcx, [rdx+8]; Buf1
0x180019fdf  test    rcx, rcx
0x180019fe2  jz      loc_18001A2AA
0x180019fe8  mov     ebx, [rdx]
0x180019fea  test    ebx, ebx
0x180019fec  jz      loc_18001A2AA
0x180019ff2  test    r9d, r9d
0x180019ff5  jz      loc_18001A29B
0x180019ffb  test    r8, r8
0x180019ffe  jz      loc_18001A29B
0x18001a004  lea     r13d, [rbp-1]
0x18001a008  cmp     ebx, r13d
0x18001a00b  jnz     short loc_18001A023
0x18001a00d  mov     r8d, ebx
0x18001a010  add     r8, r8; Size
0x18001a013  mov     rdx, r15; Buf2
0x18001a016  call    memcmp_0
0x18001a01b  test    eax, eax
0x18001a01d  jz      loc_18001A2AA
0x18001a023  lea     eax, [rbx+2]
0x18001a026  add     eax, ebp
0x18001a028  mov     dword ptr [rsp+108h+arg_20], eax
0x18001a02f  mov     ecx, eax
0x18001a031  mov     edi, 2
0x18001a036  mov     eax, edi
0x18001a038  mul     rcx
0x18001a03b  lea     rcx, [rdi-3]
0x18001a03f  cmovb   rax, rcx
0x18001a043  mov     rcx, rax; cb
0x18001a046  call    cs:__imp_CoTaskMemAlloc
0x18001a04c  mov     rbx, rax
0x18001a04f  mov     [rsp+108h+var_58], rax
0x18001a057  mov     edx, [rsi]
0x18001a059  add     edx, edi
0x18001a05b  mov     eax, edi
0x18001a05d  mul     rdx
0x18001a060  lea     rcx, [rdi-3]
0x18001a064  cmovb   rax, rcx
0x18001a068  mov     rcx, rax; cb
0x18001a06b  call    cs:__imp_CoTaskMemAlloc
0x18001a071  mov     rdi, rax
0x18001a074  mov     [rsp+108h+arg_8], rax
0x18001a07c  xor     ecx, ecx
0x18001a07e  test    rbx, rbx
0x18001a081  jz      loc_18001A1CF
0x18001a087  test    rax, rax
0x18001a08a  jz      loc_18001A1CF
0x18001a090  mov     r8d, [rsi]
0x18001a093  add     r8, r8; Size
0x18001a096  mov     rdx, [rsi+8]; Src
0x18001a09a  mov     rcx, rax; void *
0x18001a09d  call    memcpy_0
0x18001a0a2  mov     ecx, [rsi]
0x18001a0a4  xor     edx, edx
0x18001a0a6  mov     [rdi+rcx*2], dx
0x18001a0aa  mov     eax, [rsi]
0x18001a0ac  inc     eax
0x18001a0ae  mov     [rdi+rax*2], dx
0x18001a0b2  lea     rsi, ds:0[rbp*2]
0x18001a0ba  mov     r8, rsi; Size
0x18001a0bd  mov     rdx, r15; Src
0x18001a0c0  mov     rcx, rbx; void *
0x18001a0c3  call    memcpy_0
0x18001a0c8  mov     word ptr [rbx+r13*2], 2Ch ; ','
0x18001a0cf  xor     r15d, r15d
0x18001a0d2  mov     [rsi+rbx], r15w
0x18001a0d7  lea     rdx, asc_1800363D4; ","
0x18001a0de  mov     rcx, rdi; String
0x18001a0e1  call    wcstok_mvcrt_legacy_two_parameter_form
0x18001a0e6  mov     rdi, rax
0x18001a0e9  test    rax, rax
0x18001a0ec  jz      loc_18001A18E
0x18001a0f2  mov     r14d, dword ptr [rsp+108h+arg_20]
0x18001a0fa  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001a0fe  inc     rsi
0x18001a101  cmp     [rdi+rsi*2], r15w
0x18001a106  jnz     short loc_18001A0FE
0x18001a108  lea     eax, [rsi+1]
0x18001a10b  mov     r15d, eax
0x18001a10e  movzx   eax, word ptr [rdi+rax*2]
0x18001a112  mov     word ptr [rsp+108h+arg_20], ax
0x18001a11a  xor     eax, eax
0x18001a11c  mov     [rdi+r15*2], ax
0x18001a121  mov     r13d, esi
0x18001a124  mov     word ptr [rdi+r13*2], 2Ch ; ','
0x18001a12b  mov     rdx, rdi; SubStr
0x18001a12e  mov     rcx, rbx; Str
0x18001a131  call    cs:__imp_wcsstr
0x18001a137  test    rax, rax
0x18001a13a  jnz     short loc_18001A157
0x18001a13c  mov     byte ptr [r12], 1
0x18001a141  mov     edx, r14d
0x18001a144  sub     edx, ebp; SizeInWords
0x18001a146  lea     rcx, [rbx+rbp*2]; Destination
0x18001a14a  mov     r8, rdi; Source
0x18001a14d  call    cs:__imp_wcscpy_s
0x18001a153  inc     ebp
0x18001a155  add     ebp, esi
0x18001a157  movzx   eax, word ptr [rsp+108h+arg_20]
0x18001a15f  mov     [rdi+r15*2], ax
0x18001a164  xor     r15d, r15d
0x18001a167  mov     [rdi+r13*2], r15w
0x18001a16c  lea     rdx, asc_1800363D4; ","
0x18001a173  xor     ecx, ecx; String
0x18001a175  call    wcstok_mvcrt_legacy_two_parameter_form
0x18001a17a  mov     rdi, rax
0x18001a17d  test    rax, rax
0x18001a180  jnz     loc_18001A0FA
0x18001a186  mov     r14, [rsp+108h+arg_0]
0x18001a18e  lea     eax, [rbp-1]
0x18001a191  mov     [rbx+rax*2], r15w
0x18001a196  mov     rax, [r14]
0x18001a199  mov     r8d, ebp
0x18001a19c  mov     rdx, rbx
0x18001a19f  mov     rcx, r14
0x18001a1a2  mov     rax, [rax+28h]
0x18001a1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1ab  mov     ebx, eax
0x18001a1ad  lea     rcx, [rsp+108h+arg_8]; void *
0x18001a1b5  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x18001a1ba  nop
0x18001a1bb  lea     rcx, [rsp+108h+var_58]; void *
0x18001a1c3  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x18001a1c8  mov     eax, ebx
0x18001a1ca  jmp     loc_18001A2BF
0x18001a1cf  mov     [rsp+108h+var_48], rcx
0x18001a1d7  or      eax, 0FFFFFFFFh
0x18001a1da  mov     [rsp+108h+var_68], eax
0x18001a1e1  mov     [rsp+108h+var_70], eax
0x18001a1e8  mov     [rsp+108h+var_88], ecx
0x18001a1ef  mov     [rsp+108h+var_90], rcx
0x18001a1f4  mov     [rsp+108h+var_98], eax
0x18001a1f8  mov     [rsp+108h+var_A0], eax
0x18001a1fc  mov     [rsp+108h+var_A8], ecx
0x18001a200  mov     [rsp+108h+var_B0], rcx
0x18001a205  mov     [rsp+108h+var_B8], ecx
0x18001a209  lea     rax, word_180034198
0x18001a210  mov     [rsp+108h+var_C0], rax
0x18001a215  mov     [rsp+108h+var_C8], rax
0x18001a21a  mov     [rsp+108h+var_D0], rax
0x18001a21f  mov     [rsp+108h+var_D8], rax
0x18001a224  mov     [rsp+108h+var_E0], 0C00210CAh
0x18001a22c  mov     [rsp+108h+var_E8], 3
0x18001a234  mov     r9d, 80210861h
0x18001a23a  mov     r8, [r14+0A28h]
0x18001a241  xor     edx, edx
0x18001a243  lea     rcx, [rsp+108h+var_50]
0x18001a24b  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001a250  nop
0x18001a251  mov     ebx, 3FCh
0x18001a256  mov     r9d, 400000h; unsigned int
0x18001a25c  mov     r8d, ebx; unsigned int
0x18001a25f  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001a266  lea     rcx, [rsp+108h+var_50]; this
0x18001a26e  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001a273  nop
0x18001a274  lea     rcx, [rsp+108h+var_50]; this
0x18001a27c  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18001a281  xor     r9d, r9d; unsigned int
0x18001a284  mov     r8d, ebx; unsigned int
0x18001a287  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x18001a28e  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001a295  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001a29b  mov     byte ptr [r12], 1
0x18001a2a0  mov     rcx, r14; this
0x18001a2a3  call    ?AddStringToHeap@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::AddStringToHeap(TMetabaseMetaXmlFile::TSizedString const &)
0x18001a2a8  jmp     short loc_18001A2BF
0x18001a2aa  mov     rax, [r14]
0x18001a2ad  mov     r8d, ebp
0x18001a2b0  mov     rdx, r15
0x18001a2b3  mov     rcx, r14
0x18001a2b6  mov     rax, [rax+28h]
0x18001a2ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2bf  mov     rbx, [rsp+108h+arg_10]
0x18001a2c7  add     rsp, 0D0h
0x18001a2ce  pop     r15
0x18001a2d0  pop     r14
0x18001a2d2  pop     r13
0x18001a2d4  pop     r12
0x18001a2d6  pop     rdi
0x18001a2d7  pop     rsi
0x18001a2d8  pop     rbp
0x18001a2d9  retn
```
