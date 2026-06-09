# DCCheckScheduleTaskExist(ushort const *,ushort const *)

- ea: `0x14005707c`
- end: `0x1400575ea`
- name: `?DCCheckScheduleTaskExist@@YAHPEBG0@Z`
- size: `1390`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14004b5a0`

## callees

- `0x140003450`
- `0x14000bf50`
- `0x14001173c`
- `0x1400564cc`
- `0x140056a5c`
- `0x14005707c`
- `0x140065274`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400570f9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400570f9`
- `OLEAUT32!__imp_VariantInit` at `0x140057169`
- `OLEAUT32!__imp_VariantInit` at `0x140057191`
- `OLEAUT32!__imp_VariantInit` at `0x1400571b6`
- `OLEAUT32!__imp_VariantInit` at `0x1400571d3`
- `OLEAUT32!__imp_VariantInit` at `0x140057169`
- `OLEAUT32!__imp_VariantInit` at `0x140057191`
- `OLEAUT32!__imp_VariantInit` at `0x1400571b6`
- `OLEAUT32!__imp_VariantInit` at `0x1400571d3`
- `OLEAUT32!__imp_VariantClear` at `0x14005726a`
- `OLEAUT32!__imp_VariantClear` at `0x140057283`
- `OLEAUT32!__imp_VariantClear` at `0x14005729f`
- `OLEAUT32!__imp_VariantClear` at `0x1400572bb`
- `OLEAUT32!__imp_VariantClear` at `0x14005726a`
- `OLEAUT32!__imp_VariantClear` at `0x140057283`
- `OLEAUT32!__imp_VariantClear` at `0x14005729f`
- `OLEAUT32!__imp_VariantClear` at `0x1400572bb`

## string_xrefs

- `0x140057433`: `Refresh schedule created by Declared Configuration to refresh any settings changed on the device`
- `0x140057526`: `CheckScheduleTaskExist`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall DCCheckScheduleTaskExist(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HRESULT v3; // eax
  wil *v4; // rcx
  __int64 result; // rax
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v8; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v10; // xmm8
  IRecordInfo *v11; // xmm9_8
  __int128 v12; // xmm6
  IRecordInfo *v13; // xmm7_8
  int v14; // ebx
  HRESULT v15; // eax
  HRESULT v16; // eax
  HRESULT v17; // eax
  HRESULT v18; // eax
  int v19; // ecx
  LPVOID v20; // rbx
  __int64 v21; // rdi
  __int64 *v22; // rax
  __int64 v23; // rdx
  int v24; // ebx
  __int64 *v25; // rbx
  __int64 v26; // rdi
  __int64 *v27; // rax
  __int64 v28; // rdx
  int v29; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-388h] BYREF
  __int64 *v31; // [rsp+38h] [rbp-380h] BYREF
  __int64 v32; // [rsp+40h] [rbp-378h] BYREF
  _BYTE v33[8]; // [rsp+48h] [rbp-370h] BYREF
  VARIANTARG v34; // [rsp+50h] [rbp-368h] BYREF
  VARIANTARG v35; // [rsp+68h] [rbp-350h] BYREF
  VARIANTARG v36; // [rsp+80h] [rbp-338h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-320h] BYREF
  __int128 v38; // [rsp+B0h] [rbp-308h] BYREF
  IRecordInfo *v39; // [rsp+C0h] [rbp-2F8h]
  __int128 v40; // [rsp+D0h] [rbp-2E8h] BYREF
  IRecordInfo *v41; // [rsp+E0h] [rbp-2D8h]
  __int128 v42; // [rsp+F0h] [rbp-2C8h] BYREF
  IRecordInfo *v43; // [rsp+100h] [rbp-2B8h]
  VARIANTARG v44; // [rsp+110h] [rbp-2A8h] BYREF
  unsigned __int16 v45[264]; // [rsp+130h] [rbp-288h] BYREF

  ppv = 0;
  v31 = 0;
  v32 = 0;
  v3 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  try
  {
    if ( v3 >= 0 )
    {
      v6 = ppv;
      v7 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL);
      VariantInit(&pvarg);
      v8 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit(&v36);
      v10 = *(_OWORD *)&v36.vt;
      v11 = v36.pRecInfo;
      VariantInit(&v35);
      v12 = *(_OWORD *)&v35.vt;
      v13 = v35.pRecInfo;
      VariantInit(&v34);
      v38 = v8;
      v39 = pRecInfo;
      v40 = v10;
      v41 = v11;
      v42 = v12;
      v43 = v13;
      v44 = v34;
      v14 = v7(v6, &v44, &v42, &v40, &v38);
      v15 = VariantClear(&v34);
      if ( v15 < 0 )
        _com_issue_error(v15);
      v16 = VariantClear(&v35);
      if ( v16 < 0 )
        _com_issue_error(v16);
      v17 = VariantClear(&v36);
      if ( v17 < 0 )
        _com_issue_error(v17);
      v18 = VariantClear(&pvarg);
      if ( v18 < 0 )
        _com_issue_error(v18);
      if ( v14 >= 0 )
      {
        if ( a2 )
        {
          if ( (int)StringCchPrintfW(v45, 0x104u, L"\\Microsoft\\Windows\\EnterpriseMgmt\\%s", a2) >= 0 )
          {
            v20 = ppv;
            v21 = *(_QWORD *)ppv;
            v22 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)v33, v45);
            if ( v22 )
              v23 = *v22;
            else
              v23 = 0;
            v24 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 **))(v21 + 56))(v20, v23, &v31);
            _bstr_t::~_bstr_t((_bstr_t *)v33);
            if ( v24 >= 0 )
            {
              v25 = v31;
              v26 = *v31;
              v27 = *(__int64 **)_bstr_t::_bstr_t(
                                   (_bstr_t *)v33,
                                   L"Refresh schedule created by Declared Configuration to refresh any settings changed on the device");
              if ( v27 )
                v28 = *v27;
              else
                v28 = 0;
              v29 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v26 + 104))(v25, v28, &v32);
              _bstr_t::~_bstr_t((_bstr_t *)v33);
              if ( v29 < 0 )
              {
                if ( v32 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                if ( v31 )
                  (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
                v4 = (wil *)ppv;
                if ( ppv )
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                result = 0;
              }
              else
              {
                if ( v32 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                if ( v31 )
                  (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
                v4 = (wil *)ppv;
                if ( ppv )
                  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 16LL))(ppv, *(_QWORD *)ppv);
                result = 1;
              }
            }
            else
            {
              if ( v32 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
              if ( v31 )
                (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
              v4 = (wil *)ppv;
              if ( ppv )
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
              result = 0;
            }
          }
          else
          {
            if ( v32 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
            if ( v31 )
              (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
            v4 = (wil *)ppv;
            if ( ppv )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
            result = 0;
          }
        }
        else
        {
          if ( byte_140084F41 < 0 )
            McTemplateU0zzd_EventWriteTransfer(
              v19,
              (unsigned int)OrchestratorGenericFailure,
              (unsigned int)L"CheckScheduleTaskExist",
              (unsigned int)L"enrollmentId should not null",
              87);
          if ( v32 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
          if ( v31 )
            (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
          v4 = (wil *)ppv;
          if ( ppv )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          result = 0;
        }
      }
      else
      {
        if ( v32 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        if ( v31 )
          (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
        v4 = (wil *)ppv;
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        result = 0;
      }
    }
    else
    {
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      if ( v31 )
        (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
      v4 = (wil *)ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      result = 0;
    }
  }
  catch ( ... )
  {
    wil::ResultFromCaughtException(v4);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14005707c  mov     rax, rsp
0x14005707f  mov     [rax+8], rbx
0x140057083  mov     [rax+18h], rsi
0x140057087  push    rdi
0x140057088  sub     rsp, 3B0h
0x14005708f  movaps  xmmword ptr [rax-18h], xmm6
0x140057093  movaps  xmmword ptr [rax-28h], xmm7
0x140057097  movaps  xmmword ptr [rax-38h], xmm8
0x14005709c  movaps  xmmword ptr [rax-48h], xmm9
0x1400570a1  movaps  xmmword ptr [rax-58h], xmm10
0x1400570a6  movaps  xmmword ptr [rax-68h], xmm11
0x1400570ab  mov     rax, cs:__security_cookie
0x1400570b2  xor     rax, rsp
0x1400570b5  mov     [rsp+3B8h+var_78], rax
0x1400570bd  mov     rsi, rdx
0x1400570c0  mov     [rsp+3B8h+var_388], 0
0x1400570c9  mov     [rsp+3B8h+var_380], 0
0x1400570d2  mov     [rsp+3B8h+var_378], 0
0x1400570db  lea     rax, [rsp+3B8h+var_388]
0x1400570e0  mov     [rsp+3B8h+ppv], rax; ppv
0x1400570e5  lea     r9, IID_ITaskService; riid
0x1400570ec  xor     edx, edx; pUnkOuter
0x1400570ee  lea     r8d, [rdx+1]; dwClsContext
0x1400570f2  lea     rcx, CLSID_TaskScheduler; rclsid
0x1400570f9  call    cs:__imp_CoCreateInstance
0x140057100  nop     dword ptr [rax+rax+00h]
0x140057105  test    eax, eax
0x140057107  jns     short loc_140057155
0x140057109  mov     rcx, [rsp+3B8h+var_378]
0x14005710e  test    rcx, rcx
0x140057111  jz      short loc_140057120
0x140057113  mov     rax, [rcx]
0x140057116  mov     rax, [rax+10h]
0x14005711a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005711f  nop
0x140057120  mov     rcx, [rsp+3B8h+var_380]
0x140057125  test    rcx, rcx
0x140057128  jz      short loc_140057137
0x14005712a  mov     rax, [rcx]
0x14005712d  mov     rax, [rax+10h]
0x140057131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057136  nop
0x140057137  mov     rcx, [rsp+3B8h+var_388]
0x14005713c  test    rcx, rcx
0x14005713f  jz      short loc_14005714E
0x140057141  mov     rax, [rcx]
0x140057144  mov     rax, [rax+10h]
0x140057148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005714d  nop
0x14005714e  xor     eax, eax
0x140057150  jmp     loc_140057585
0x140057155  mov     rdi, [rsp+3B8h+var_388]
0x14005715a  mov     rax, [rdi]
0x14005715d  mov     rbx, [rax+50h]
0x140057161  lea     rcx, [rsp+3B8h+pvarg]; pvarg
0x140057169  call    cs:__imp_VariantInit
0x140057170  nop     dword ptr [rax+rax+00h]
0x140057175  nop
0x140057176  movups  xmm10, xmmword ptr [rsp+3B8h+pvarg]
0x14005717f  movsd   xmm11, qword ptr [rsp+3B8h+pvarg+10h]
0x140057189  lea     rcx, [rsp+3B8h+var_338]; pvarg
0x140057191  call    cs:__imp_VariantInit
0x140057198  nop     dword ptr [rax+rax+00h]
0x14005719d  nop
0x14005719e  movups  xmm8, xmmword ptr [rsp+3B8h+var_338]
0x1400571a7  movsd   xmm9, qword ptr [rsp+3B8h+var_338+10h]
0x1400571b1  lea     rcx, [rsp+3B8h+var_350]; pvarg
0x1400571b6  call    cs:__imp_VariantInit
0x1400571bd  nop     dword ptr [rax+rax+00h]
0x1400571c2  nop
0x1400571c3  movups  xmm6, xmmword ptr [rsp+3B8h+var_350]
0x1400571c8  movsd   xmm7, qword ptr [rsp+3B8h+var_350+10h]
0x1400571ce  lea     rcx, [rsp+3B8h+var_368]; pvarg
0x1400571d3  call    cs:__imp_VariantInit
0x1400571da  nop     dword ptr [rax+rax+00h]
0x1400571df  nop
0x1400571e0  movups  xmm0, xmmword ptr [rsp+3B8h+var_368]
0x1400571e5  movsd   xmm1, qword ptr [rsp+3B8h+var_368+10h]
0x1400571eb  movaps  [rsp+3B8h+var_308], xmm10
0x1400571f4  movsd   [rsp+3B8h+var_2F8], xmm11
0x1400571fe  movaps  [rsp+3B8h+var_2E8], xmm8
0x140057207  movsd   [rsp+3B8h+var_2D8], xmm9
0x140057211  movaps  [rsp+3B8h+var_2C8], xmm6
0x140057219  movsd   [rsp+3B8h+var_2B8], xmm7
0x140057222  movaps  [rsp+3B8h+var_2A8], xmm0
0x14005722a  movsd   [rsp+3B8h+var_298], xmm1
0x140057233  lea     rax, [rsp+3B8h+var_308]
0x14005723b  mov     [rsp+3B8h+ppv], rax
0x140057240  lea     r9, [rsp+3B8h+var_2E8]
0x140057248  lea     r8, [rsp+3B8h+var_2C8]
0x140057250  lea     rdx, [rsp+3B8h+var_2A8]
0x140057258  mov     rcx, rdi
0x14005725b  mov     rax, rbx
0x14005725e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057263  mov     ebx, eax
0x140057265  lea     rcx, [rsp+3B8h+var_368]; pvarg
0x14005726a  call    cs:__imp_VariantClear
0x140057271  nop     dword ptr [rax+rax+00h]
0x140057276  test    eax, eax
0x140057278  js      loc_1400575C9
0x14005727e  lea     rcx, [rsp+3B8h+var_350]; pvarg
0x140057283  call    cs:__imp_VariantClear
0x14005728a  nop     dword ptr [rax+rax+00h]
0x14005728f  test    eax, eax
0x140057291  js      loc_1400575D1
0x140057297  lea     rcx, [rsp+3B8h+var_338]; pvarg
0x14005729f  call    cs:__imp_VariantClear
0x1400572a6  nop     dword ptr [rax+rax+00h]
0x1400572ab  test    eax, eax
0x1400572ad  js      loc_1400575D9
0x1400572b3  lea     rcx, [rsp+3B8h+pvarg]; pvarg
0x1400572bb  call    cs:__imp_VariantClear
0x1400572c2  nop     dword ptr [rax+rax+00h]
0x1400572c7  test    eax, eax
0x1400572c9  js      loc_1400575E1
0x1400572cf  test    ebx, ebx
0x1400572d1  jns     short loc_14005731F
0x1400572d3  mov     rcx, [rsp+3B8h+var_378]
0x1400572d8  test    rcx, rcx
0x1400572db  jz      short loc_1400572EA
0x1400572dd  mov     rax, [rcx]
0x1400572e0  mov     rax, [rax+10h]
0x1400572e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400572e9  nop
0x1400572ea  mov     rcx, [rsp+3B8h+var_380]
0x1400572ef  test    rcx, rcx
0x1400572f2  jz      short loc_140057301
0x1400572f4  mov     rax, [rcx]
0x1400572f7  mov     rax, [rax+10h]
0x1400572fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057300  nop
0x140057301  mov     rcx, [rsp+3B8h+var_388]
0x140057306  test    rcx, rcx
0x140057309  jz      short loc_140057318
0x14005730b  mov     rax, [rcx]
0x14005730e  mov     rax, [rax+10h]
0x140057312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057317  nop
0x140057318  xor     eax, eax
0x14005731a  jmp     loc_140057585
0x14005731f  test    rsi, rsi
0x140057322  jz      loc_14005750E
0x140057328  mov     r9, rsi
0x14005732b  lea     r8, aMicrosoftWindo; "\\Microsoft\\Windows\\EnterpriseMgmt\\%"...
0x140057332  mov     edx, 104h; unsigned __int64
0x140057337  lea     rcx, [rsp+3B8h+var_288]; unsigned __int16 *
0x14005733f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140057344  test    eax, eax
0x140057346  jns     short loc_140057394
0x140057348  mov     rcx, [rsp+3B8h+var_378]
0x14005734d  test    rcx, rcx
0x140057350  jz      short loc_14005735F
0x140057352  mov     rax, [rcx]
0x140057355  mov     rax, [rax+10h]
0x140057359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005735e  nop
0x14005735f  mov     rcx, [rsp+3B8h+var_380]
0x140057364  test    rcx, rcx
0x140057367  jz      short loc_140057376
0x140057369  mov     rax, [rcx]
0x14005736c  mov     rax, [rax+10h]
0x140057370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057375  nop
0x140057376  mov     rcx, [rsp+3B8h+var_388]
0x14005737b  test    rcx, rcx
0x14005737e  jz      short loc_14005738D
0x140057380  mov     rax, [rcx]
0x140057383  mov     rax, [rax+10h]
0x140057387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005738c  nop
0x14005738d  xor     eax, eax
0x14005738f  jmp     loc_140057585
0x140057394  mov     rbx, [rsp+3B8h+var_388]
0x140057399  mov     rdi, [rbx]
0x14005739c  lea     rdx, [rsp+3B8h+var_288]; unsigned __int16 *
0x1400573a4  lea     rcx, [rsp+3B8h+var_370]; this
0x1400573a9  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1400573ae  nop
0x1400573af  mov     rax, [rax]
0x1400573b2  test    rax, rax
0x1400573b5  jz      short loc_1400573BC
0x1400573b7  mov     rdx, [rax]
0x1400573ba  jmp     short loc_1400573BE
0x1400573bc  xor     edx, edx
0x1400573be  lea     r8, [rsp+3B8h+var_380]
0x1400573c3  mov     rcx, rbx
0x1400573c6  mov     rax, [rdi+38h]
0x1400573ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400573cf  mov     ebx, eax
0x1400573d1  lea     rcx, [rsp+3B8h+var_370]; this
0x1400573d6  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1400573db  test    ebx, ebx
0x1400573dd  jns     short loc_14005742B
0x1400573df  mov     rcx, [rsp+3B8h+var_378]
0x1400573e4  test    rcx, rcx
0x1400573e7  jz      short loc_1400573F6
0x1400573e9  mov     rax, [rcx]
0x1400573ec  mov     rax, [rax+10h]
0x1400573f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400573f5  nop
0x1400573f6  mov     rcx, [rsp+3B8h+var_380]
0x1400573fb  test    rcx, rcx
0x1400573fe  jz      short loc_14005740D
0x140057400  mov     rax, [rcx]
0x140057403  mov     rax, [rax+10h]
0x140057407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005740c  nop
0x14005740d  mov     rcx, [rsp+3B8h+var_388]
0x140057412  test    rcx, rcx
0x140057415  jz      short loc_140057424
0x140057417  mov     rax, [rcx]
0x14005741a  mov     rax, [rax+10h]
0x14005741e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057423  nop
0x140057424  xor     eax, eax
0x140057426  jmp     loc_140057585
0x14005742b  mov     rbx, [rsp+3B8h+var_380]
0x140057430  mov     rdi, [rbx]
0x140057433  lea     rdx, aRefreshSchedul; "Refresh schedule created by Declared Co"...
0x14005743a  lea     rcx, [rsp+3B8h+var_370]; this
0x14005743f  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140057444  nop
0x140057445  mov     rax, [rax]
0x140057448  test    rax, rax
0x14005744b  jz      short loc_140057452
0x14005744d  mov     rdx, [rax]
0x140057450  jmp     short loc_140057454
0x140057452  xor     edx, edx
0x140057454  lea     r8, [rsp+3B8h+var_378]
0x140057459  mov     rcx, rbx
0x14005745c  mov     rax, [rdi+68h]
0x140057460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057465  mov     ebx, eax
0x140057467  lea     rcx, [rsp+3B8h+var_370]; this
0x14005746c  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x140057471  nop
0x140057472  test    ebx, ebx
0x140057474  js      short loc_1400574C5
0x140057476  mov     rcx, [rsp+3B8h+var_378]
0x14005747b  test    rcx, rcx
0x14005747e  jz      short loc_14005748D
0x140057480  mov     rax, [rcx]
0x140057483  mov     rax, [rax+10h]
0x140057487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005748c  nop
0x14005748d  mov     rcx, [rsp+3B8h+var_380]
0x140057492  test    rcx, rcx
0x140057495  jz      short loc_1400574A4
0x140057497  mov     rax, [rcx]
0x14005749a  mov     rax, [rax+10h]
0x14005749e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400574a3  nop
0x1400574a4  mov     rcx, [rsp+3B8h+var_388]
0x1400574a9  test    rcx, rcx
0x1400574ac  jz      short loc_1400574BB
0x1400574ae  mov     rdx, [rcx]
0x1400574b1  mov     rax, [rdx+10h]
0x1400574b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400574ba  nop
0x1400574bb  mov     eax, 1
0x1400574c0  jmp     loc_140057585
0x1400574c5  mov     rcx, [rsp+3B8h+var_378]
0x1400574ca  test    rcx, rcx
0x1400574cd  jz      short loc_1400574DC
0x1400574cf  mov     rax, [rcx]
0x1400574d2  mov     rax, [rax+10h]
0x1400574d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400574db  nop
0x1400574dc  mov     rcx, [rsp+3B8h+var_380]
0x1400574e1  test    rcx, rcx
0x1400574e4  jz      short loc_1400574F3
0x1400574e6  mov     rax, [rcx]
0x1400574e9  mov     rax, [rax+10h]
0x1400574ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400574f2  nop
0x1400574f3  mov     rcx, [rsp+3B8h+var_388]
0x1400574f8  test    rcx, rcx
0x1400574fb  jz      short loc_14005750A
0x1400574fd  mov     rax, [rcx]
0x140057500  mov     rax, [rax+10h]
0x140057504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057509  nop
0x14005750a  xor     eax, eax
0x14005750c  jmp     short loc_140057585
0x14005750e  cmp     cs:byte_140084F41, 0
0x140057515  jge     short loc_14005753A
0x140057517  mov     dword ptr [rsp+3B8h+ppv], 80070057h
0x14005751f  lea     r9, aEnrollmentidSh; "enrollmentId should not null"
0x140057526  lea     r8, aCheckschedulet; "CheckScheduleTaskExist"
0x14005752d  lea     rdx, OrchestratorGenericFailure
0x140057534  call    McTemplateU0zzd_EventWriteTransfer
0x140057539  nop
0x14005753a  mov     rcx, [rsp+3B8h+var_378]
0x14005753f  test    rcx, rcx
0x140057542  jz      short loc_140057551
0x140057544  mov     rax, [rcx]
0x140057547  mov     rax, [rax+10h]
0x14005754b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057550  nop
0x140057551  mov     rcx, [rsp+3B8h+var_380]
  ... truncated ...
```
