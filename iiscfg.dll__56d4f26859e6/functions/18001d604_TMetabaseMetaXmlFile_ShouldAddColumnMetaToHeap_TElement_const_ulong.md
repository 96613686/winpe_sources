# TMetabaseMetaXmlFile::ShouldAddColumnMetaToHeap(TElement const &,ulong)

- ea: `0x18001d604`
- end: `0x18001da02`
- name: `?ShouldAddColumnMetaToHeap@TMetabaseMetaXmlFile@@AEAA_NAEBUTElement@@K@Z`
- size: `1022`
- prototype: `bool(TMetabaseMetaXmlFile *__hidden this, const struct TElement *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18001c240`

## callees

- `0x180002bc4`
- `0x180011b38`
- `0x180012734`
- `0x180015990`
- `0x180016db0`
- `0x18001c814`
- `0x18001d604`
- `0x18002e0ca`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18001d7a8`
- `msvcrt!swprintf_s` at `0x18001d920`
- `msvcrt!swprintf_s` at `0x18001d7a8`
- `msvcrt!swprintf_s` at `0x18001d920`
- `msvcrt!wcsncpy_s` at `0x18001d786`
- `msvcrt!wcsncpy_s` at `0x18001d8fe`
- `msvcrt!wcsncpy_s` at `0x18001d786`
- `msvcrt!wcsncpy_s` at `0x18001d8fe`
- `msvcrt!_wtol` at `0x18001d6db`
- `msvcrt!_wtol` at `0x18001d6db`

## string_xrefs

- `0x18001d64a`: `IIsConfigObject`
- `0x18001d84a`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001d9be`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall TMetabaseMetaXmlFile::ShouldAddColumnMetaToHeap(
        TMetabaseMetaXmlFile *this,
        const struct TElement *a2,
        unsigned int a3)
{
  TMetabaseMetaXmlFile *v6; // rcx
  const wchar_t *v8; // rcx
  int v9; // eax
  const wchar_t *v10; // rbx
  unsigned int MatchingHeapEntry; // eax
  const wchar_t *v12; // r8
  __int64 v13; // [rsp+88h] [rbp-A8h]
  __int64 v14; // [rsp+90h] [rbp-A0h]
  unsigned int v15; // [rsp+B0h] [rbp-80h] BYREF
  unsigned __int8 v16[8]; // [rsp+B8h] [rbp-78h] BYREF
  unsigned int v17; // [rsp+C0h] [rbp-70h] BYREF
  int v18; // [rsp+C8h] [rbp-68h] BYREF
  int v19; // [rsp+CCh] [rbp-64h]
  char v20[8]; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+D8h] [rbp-58h]
  const wchar_t *v22; // [rsp+E0h] [rbp-50h] BYREF
  const wchar_t *v23; // [rsp+F0h] [rbp-40h] BYREF
  char v24[8]; // [rsp+F8h] [rbp-38h] BYREF
  const wchar_t *v25; // [rsp+100h] [rbp-30h]
  unsigned int *v26; // [rsp+158h] [rbp+28h]
  wchar_t Buffer[16]; // [rsp+180h] [rbp+50h] BYREF
  wchar_t Destination[255]; // [rsp+1A0h] [rbp+70h] BYREF
  __int16 v29; // [rsp+39Eh] [rbp+26Eh]

  memset_0(v24, 0, 0x88u);
  v23 = L"IIsConfigObject";
  v25 = (const wchar_t *)(*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 144LL))(this, a3);
  v18 = 0;
  v19 = 2;
  v17 = 0;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, __int64, int *, _QWORD, const wchar_t **, unsigned int *))(**((_QWORD **)this + 327) + 56LL))(
         *((_QWORD *)this + 327),
         0,
         2,
         &v18,
         0,
         &v23,
         &v17) >= 0 )
    return 0;
  v8 = (const wchar_t *)*((_QWORD *)TMetabaseMetaXmlFile::GetAttribute(
                                      v6,
                                      a2,
                                      (TMetabaseMetaXmlFile *)((char *)this + 488))
                        + 3);
  if ( v8 )
    v9 = _wtol(v8);
  else
    v9 = 0;
  v15 = v9;
  v26 = &v15;
  v19 = 13;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, __int64, int *, _QWORD, const wchar_t **, unsigned int *))(**((_QWORD **)this + 328) + 56LL))(
         *((_QWORD *)this + 328),
         0,
         2,
         &v18,
         0,
         &v23,
         &v17) >= 0 )
  {
    v10 = &word_180034198;
    v22 = &word_180034198;
    *(_DWORD *)v16 = 2;
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, unsigned __int8 *, _QWORD, const wchar_t **))(**((_QWORD **)this + 328)
                                                                                                 + 32LL))(
      *((_QWORD *)this + 328),
      v17,
      1,
      v16,
      0,
      &v22);
    if ( *((_DWORD *)a2 + 5) )
      v10 = (const wchar_t *)*((_QWORD *)a2 + 5);
    wcsncpy_s(Destination, 0x100u, v10, 0xFFu);
    v29 = 0;
    swprintf_s(Buffer, 0xCu, L"%d", v15);
    v21 = 0;
    CErrorInterceptor::Init(
      (CErrorInterceptor *)v20,
      0,
      *((_QWORD *)this + 325),
      0x80210863,
      3u,
      -2147348244,
      v25,
      Buffer,
      v22,
      Destination,
      0,
      0,
      1,
      -1,
      -1,
      *((_QWORD *)this + 335),
      2,
      v13,
      v14,
      -1,
      -1);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v20,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      1562,
      0x400000);
LABEL_10:
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v20);
    return 0;
  }
  *(_DWORD *)v16 = v15;
  MatchingHeapEntry = TPooledHeap::FindMatchingHeapEntry((TMetabaseMetaXmlFile *)((char *)this + 2640), v16, 4u);
  if ( !MatchingHeapEntry )
  {
    if ( (unsigned int)(*((_DWORD *)this + 664) - *((_DWORD *)this + 665)) < 4 )
      (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 330) + 8LL))((char *)this + 2640, 4);
    *(_DWORD *)(*((unsigned int *)this + 665) + *((_QWORD *)this + 331)) = 4;
    *((_DWORD *)this + 665) += 4;
    MatchingHeapEntry = THeap<unsigned long>::AddItemToHeap((char *)this + 2640, v16, 4);
  }
  if ( MatchingHeapEntry <= *((_DWORD *)this + 668) )
  {
    if ( *((_DWORD *)a2 + 5) )
      v12 = (const wchar_t *)*((_QWORD *)a2 + 5);
    else
      v12 = &word_180034198;
    wcsncpy_s(Destination, 0x100u, v12, 0xFFu);
    v29 = 0;
    swprintf_s(Buffer, 0xCu, L"%d", v15);
    v21 = 0;
    CErrorInterceptor::Init(
      (CErrorInterceptor *)v20,
      0,
      *((_QWORD *)this + 325),
      0x80210863,
      3u,
      -2147348243,
      v25,
      Buffer,
      Destination,
      &word_180034198,
      0,
      0,
      1,
      -1,
      -1,
      *((_QWORD *)this + 335),
      2,
      v13,
      v14,
      -1,
      -1);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v20,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      1578,
      0x400000);
    goto LABEL_10;
  }
  *((_DWORD *)this + 668) = MatchingHeapEntry;
  return 1;
}

```

## disassembly

```asm
0x18001d604  mov     [rsp-8+arg_18], rbx
0x18001d609  push    rbp
0x18001d60a  push    rsi
0x18001d60b  push    rdi
0x18001d60c  push    r12
0x18001d60e  push    r14
0x18001d610  lea     rbp, [rsp-280h]
0x18001d618  sub     rsp, 3B0h
0x18001d61f  mov     rax, cs:__security_cookie
0x18001d626  xor     rax, rsp
0x18001d629  mov     [rbp+2A0h+var_30], rax
0x18001d630  mov     ebx, r8d
0x18001d633  mov     rsi, rdx
0x18001d636  mov     rdi, rcx
0x18001d639  xor     edx, edx; Val
0x18001d63b  mov     r8d, 88h; Size
0x18001d641  lea     rcx, [rbp+2A0h+var_2D8]; void *
0x18001d645  call    memset_0
0x18001d64a  lea     rax, aIisconfigobjec; "IIsConfigObject"
0x18001d651  mov     [rbp+2A0h+var_2E0], rax
0x18001d655  mov     rax, [rdi]
0x18001d658  mov     edx, ebx
0x18001d65a  mov     rcx, rdi
0x18001d65d  mov     rax, [rax+90h]
0x18001d664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d669  mov     [rbp+2A0h+var_2D0], rax
0x18001d66d  xor     r14d, r14d
0x18001d670  mov     [rbp+2A0h+var_308], r14d
0x18001d674  lea     r12d, [r14+2]
0x18001d678  mov     [rbp+2A0h+var_304], r12d
0x18001d67c  mov     [rbp+2A0h+var_310], r14d
0x18001d680  mov     rcx, [rdi+0A38h]
0x18001d687  mov     rax, [rcx]
0x18001d68a  lea     rdx, [rbp+2A0h+var_310]
0x18001d68e  mov     [rsp+3D0h+var_3A0], rdx
0x18001d693  lea     rdx, [rbp+2A0h+var_2E0]
0x18001d697  mov     [rsp+3D0h+var_3A8], rdx
0x18001d69c  mov     [rsp+3D0h+var_3B0], r14
0x18001d6a1  lea     r9, [rbp+2A0h+var_308]
0x18001d6a5  mov     r8d, r12d
0x18001d6a8  xor     edx, edx
0x18001d6aa  mov     rax, [rax+38h]
0x18001d6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6b3  test    eax, eax
0x18001d6b5  js      short loc_18001D6BE
0x18001d6b7  xor     al, al
0x18001d6b9  jmp     loc_18001D9DC
0x18001d6be  lea     r8, [rdi+1E8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001d6c5  mov     rdx, rsi; struct TElement *
0x18001d6c8  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001d6cd  mov     rcx, [rax+18h]; String
0x18001d6d1  test    rcx, rcx
0x18001d6d4  jnz     short loc_18001D6DB
0x18001d6d6  mov     eax, r14d
0x18001d6d9  jmp     short loc_18001D6E1
0x18001d6db  call    cs:__imp__wtol
0x18001d6e1  mov     [rbp+2A0h+var_320], eax
0x18001d6e4  lea     rax, [rbp+2A0h+var_320]
0x18001d6e8  mov     [rbp+2A0h+var_278], rax
0x18001d6ec  mov     [rbp+2A0h+var_304], 0Dh
0x18001d6f3  mov     rcx, [rdi+0A40h]
0x18001d6fa  mov     rax, [rcx]
0x18001d6fd  lea     rdx, [rbp+2A0h+var_310]
0x18001d701  mov     [rsp+3D0h+var_3A0], rdx
0x18001d706  lea     rdx, [rbp+2A0h+var_2E0]
0x18001d70a  mov     [rsp+3D0h+var_3A8], rdx
0x18001d70f  mov     [rsp+3D0h+var_3B0], r14
0x18001d714  lea     r9, [rbp+2A0h+var_308]
0x18001d718  mov     r8d, r12d
0x18001d71b  xor     edx, edx
0x18001d71d  mov     rax, [rax+38h]
0x18001d721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d726  test    eax, eax
0x18001d728  js      loc_18001D869
0x18001d72e  lea     rbx, word_180034198
0x18001d735  mov     [rbp+2A0h+var_2F0], rbx
0x18001d739  mov     dword ptr [rbp+2A0h+var_318], r12d
0x18001d73d  mov     rcx, [rdi+0A40h]
0x18001d744  mov     rax, [rcx]
0x18001d747  lea     rdx, [rbp+2A0h+var_2F0]
0x18001d74b  mov     [rsp+3D0h+var_3A8], rdx
0x18001d750  mov     [rsp+3D0h+var_3B0], r14
0x18001d755  lea     r9, [rbp+2A0h+var_318]
0x18001d759  mov     r8d, 1
0x18001d75f  mov     edx, [rbp+2A0h+var_310]
0x18001d762  mov     rax, [rax+20h]
0x18001d766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d76b  cmp     [rsi+14h], r14d
0x18001d76f  jbe     short loc_18001D775
0x18001d771  mov     rbx, [rsi+28h]
0x18001d775  mov     r9d, 0FFh; MaxCount
0x18001d77b  mov     r8, rbx; Source
0x18001d77e  lea     edx, [r9+1]; SizeInWords
0x18001d782  lea     rcx, [rbp+2A0h+Destination]; Destination
0x18001d786  call    cs:__imp_wcsncpy_s
0x18001d78c  mov     [rbp+2A0h+var_32], r14w
0x18001d794  mov     r9d, [rbp+2A0h+var_320]
0x18001d798  lea     r8, aD; "%d"
0x18001d79f  mov     edx, 0Ch; BufferCount
0x18001d7a4  lea     rcx, [rbp+2A0h+Buffer]; Buffer
0x18001d7a8  call    cs:__imp_swprintf_s
0x18001d7ae  mov     [rbp+2A0h+var_2F8], r14
0x18001d7b2  or      ecx, 0FFFFFFFFh
0x18001d7b5  mov     [rsp+3D0h+var_330], ecx
0x18001d7bc  mov     [rsp+3D0h+var_338], ecx
0x18001d7c3  mov     [rsp+3D0h+var_350], r12d
0x18001d7cb  mov     rax, [rdi+0A78h]
0x18001d7d2  mov     [rsp+3D0h+var_358], rax
0x18001d7d7  mov     [rsp+3D0h+var_360], ecx
0x18001d7db  mov     [rsp+3D0h+var_368], ecx
0x18001d7df  mov     [rsp+3D0h+var_370], 1
0x18001d7e7  mov     [rsp+3D0h+var_378], r14
0x18001d7ec  mov     [rsp+3D0h+var_380], r14d
0x18001d7f1  lea     rax, [rbp+2A0h+Destination]
0x18001d7f5  mov     [rsp+3D0h+var_388], rax
0x18001d7fa  mov     rax, [rbp+2A0h+var_2F0]
0x18001d7fe  mov     [rsp+3D0h+var_390], rax
0x18001d803  lea     rax, [rbp+2A0h+Buffer]
0x18001d807  mov     [rsp+3D0h+var_398], rax
0x18001d80c  mov     rax, [rbp+2A0h+var_2D0]
0x18001d810  mov     [rsp+3D0h+var_3A0], rax
0x18001d815  mov     dword ptr [rsp+3D0h+var_3A8], 800210ECh
0x18001d81d  mov     dword ptr [rsp+3D0h+var_3B0], 3
0x18001d825  mov     r9d, 80210863h
0x18001d82b  mov     r8, [rdi+0A28h]
0x18001d832  xor     edx, edx
0x18001d834  lea     rcx, [rbp+2A0h+var_300]
0x18001d838  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001d83d  nop
0x18001d83e  mov     r9d, 400000h; unsigned int
0x18001d844  mov     r8d, 61Ah; unsigned int
0x18001d84a  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001d851  lea     rcx, [rbp+2A0h+var_300]; this
0x18001d855  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001d85a  nop
0x18001d85b  lea     rcx, [rbp+2A0h+var_300]; this
0x18001d85f  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18001d864  jmp     loc_18001D6B7
0x18001d869  mov     eax, [rbp+2A0h+var_320]
0x18001d86c  mov     dword ptr [rbp+2A0h+var_318], eax
0x18001d86f  lea     rbx, [rdi+0A50h]
0x18001d876  mov     r8d, 4; unsigned int
0x18001d87c  lea     rdx, [rbp+2A0h+var_318]; unsigned __int8 *
0x18001d880  mov     rcx, rbx; this
0x18001d883  call    ?FindMatchingHeapEntry@TPooledHeap@@QEBAKPEBEK@Z; TPooledHeap::FindMatchingHeapEntry(uchar const *,ulong)
0x18001d888  test    eax, eax
0x18001d88a  jnz     short loc_18001D8CF
0x18001d88c  mov     eax, [rbx+10h]
0x18001d88f  sub     eax, [rbx+14h]
0x18001d892  cmp     eax, 4
0x18001d895  jnb     short loc_18001D8AB
0x18001d897  mov     rax, [rbx]
0x18001d89a  mov     edx, 4
0x18001d89f  mov     rcx, rbx
0x18001d8a2  mov     rax, [rax+8]
0x18001d8a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8ab  mov     edx, [rbx+14h]
0x18001d8ae  mov     rax, [rbx+8]
0x18001d8b2  mov     dword ptr [rdx+rax], 4
0x18001d8b9  add     dword ptr [rbx+14h], 4
0x18001d8bd  mov     r8d, 4
0x18001d8c3  lea     rdx, [rbp+2A0h+var_318]
0x18001d8c7  mov     rcx, rbx
0x18001d8ca  call    ?AddItemToHeap@?$THeap@K@@QEAAKPEBEK@Z; THeap<ulong>::AddItemToHeap(uchar const *,ulong)
0x18001d8cf  cmp     eax, [rdi+0A70h]
0x18001d8d5  ja      loc_18001D9D4
0x18001d8db  lea     rbx, word_180034198
0x18001d8e2  cmp     [rsi+14h], r14d
0x18001d8e6  jbe     short loc_18001D8EE
0x18001d8e8  mov     r8, [rsi+28h]
0x18001d8ec  jmp     short loc_18001D8F1
0x18001d8ee  mov     r8, rbx; Source
0x18001d8f1  mov     edx, 100h; SizeInWords
0x18001d8f6  lea     r9d, [rdx-1]; MaxCount
0x18001d8fa  lea     rcx, [rbp+2A0h+Destination]; Destination
0x18001d8fe  call    cs:__imp_wcsncpy_s
0x18001d904  mov     [rbp+2A0h+var_32], r14w
0x18001d90c  mov     r9d, [rbp+2A0h+var_320]
0x18001d910  lea     r8, aD; "%d"
0x18001d917  mov     edx, 0Ch; BufferCount
0x18001d91c  lea     rcx, [rbp+2A0h+Buffer]; Buffer
0x18001d920  call    cs:__imp_swprintf_s
0x18001d926  mov     [rbp+2A0h+var_2F8], r14
0x18001d92a  or      ecx, 0FFFFFFFFh
0x18001d92d  mov     [rsp+3D0h+var_330], ecx
0x18001d934  mov     [rsp+3D0h+var_338], ecx
0x18001d93b  mov     [rsp+3D0h+var_350], r12d
0x18001d943  mov     rax, [rdi+0A78h]
0x18001d94a  mov     [rsp+3D0h+var_358], rax
0x18001d94f  mov     [rsp+3D0h+var_360], ecx
0x18001d953  mov     [rsp+3D0h+var_368], ecx
0x18001d957  mov     [rsp+3D0h+var_370], 1
0x18001d95f  mov     [rsp+3D0h+var_378], r14
0x18001d964  mov     [rsp+3D0h+var_380], r14d
0x18001d969  mov     [rsp+3D0h+var_388], rbx
0x18001d96e  lea     rax, [rbp+2A0h+Destination]
0x18001d972  mov     [rsp+3D0h+var_390], rax
0x18001d977  lea     rax, [rbp+2A0h+Buffer]
0x18001d97b  mov     [rsp+3D0h+var_398], rax
0x18001d980  mov     rax, [rbp+2A0h+var_2D0]
0x18001d984  mov     [rsp+3D0h+var_3A0], rax
0x18001d989  mov     dword ptr [rsp+3D0h+var_3A8], 800210EDh
0x18001d991  mov     dword ptr [rsp+3D0h+var_3B0], 3
0x18001d999  mov     r9d, 80210863h
0x18001d99f  mov     r8, [rdi+0A28h]
0x18001d9a6  xor     edx, edx
0x18001d9a8  lea     rcx, [rbp+2A0h+var_300]
0x18001d9ac  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001d9b1  nop
0x18001d9b2  mov     r9d, 400000h; unsigned int
0x18001d9b8  mov     r8d, 62Ah; unsigned int
0x18001d9be  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001d9c5  lea     rcx, [rbp+2A0h+var_300]; this
0x18001d9c9  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18001d9ce  nop
0x18001d9cf  jmp     loc_18001D85B
0x18001d9d4  mov     [rdi+0A70h], eax
0x18001d9da  mov     al, 1
0x18001d9dc  mov     rcx, [rbp+2A0h+var_30]
0x18001d9e3  xor     rcx, rsp; StackCookie
0x18001d9e6  call    __security_check_cookie
0x18001d9eb  mov     rbx, [rsp+3D0h+arg_18]
0x18001d9f3  add     rsp, 3B0h
0x18001d9fa  pop     r14
0x18001d9fc  pop     r12
0x18001d9fe  pop     rdi
0x18001d9ff  pop     rsi
0x18001da00  pop     rbp
0x18001da01  retn
```
