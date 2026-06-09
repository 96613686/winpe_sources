# DisableTask(ushort const *)

- ea: `0x1800387b4`
- end: `0x180038b50`
- name: `?DisableTask@@YAXPEBG@Z`
- size: `924`
- prototype: `void __fastcall(OLECHAR *psz)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180018438`

## callees

- `0x180021cf4`
- `0x180021d14`
- `0x180038780`
- `0x1800387b4`
- `0x180047010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180038943`
- `OLEAUT32!__imp_SysAllocString` at `0x1800389af`
- `OLEAUT32!__imp_SysAllocString` at `0x180038943`
- `OLEAUT32!__imp_SysAllocString` at `0x1800389af`
- `OLEAUT32!__imp_SysFreeString` at `0x180038984`
- `OLEAUT32!__imp_SysFreeString` at `0x1800389f2`
- `OLEAUT32!__imp_SysFreeString` at `0x180038984`
- `OLEAUT32!__imp_SysFreeString` at `0x1800389f2`
- `OLEAUT32!__imp_VariantInit` at `0x18003884c`
- `OLEAUT32!__imp_VariantInit` at `0x180038863`
- `OLEAUT32!__imp_VariantInit` at `0x18003887b`
- `OLEAUT32!__imp_VariantInit` at `0x180038892`
- `OLEAUT32!__imp_VariantInit` at `0x18003884c`
- `OLEAUT32!__imp_VariantInit` at `0x180038863`
- `OLEAUT32!__imp_VariantInit` at `0x18003887b`
- `OLEAUT32!__imp_VariantInit` at `0x180038892`
- `OLEAUT32!__imp_VariantClear` at `0x180038900`
- `OLEAUT32!__imp_VariantClear` at `0x18003890c`
- `OLEAUT32!__imp_VariantClear` at `0x180038918`
- `OLEAUT32!__imp_VariantClear` at `0x180038923`
- `OLEAUT32!__imp_VariantClear` at `0x180038900`
- `OLEAUT32!__imp_VariantClear` at `0x18003890c`
- `OLEAUT32!__imp_VariantClear` at `0x180038918`
- `OLEAUT32!__imp_VariantClear` at `0x180038923`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038825`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038825`

## string_xrefs

- `0x180038b02`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180038b29`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180038ac6`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x180038adb`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x180038af0`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x180038b17`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x180038b3e`: `onecoreuap\admin\prov\lib\taskhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DisableTask(OLECHAR *psz)
{
  __int64 *v2; // rax
  HRESULT Instance; // eax
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v6; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v8; // xmm8
  IRecordInfo *v9; // xmm9_8
  __int128 v10; // xmm6
  IRecordInfo *v11; // xmm7_8
  int v12; // eax
  __int64 v13; // rdi
  __int64 v14; // rsi
  BSTR v15; // rax
  const char *v16; // r9
  OLECHAR *v17; // rbx
  int v18; // edi
  _QWORD *v19; // rdi
  __int64 v20; // rsi
  BSTR v21; // rax
  const char *v22; // r9
  OLECHAR *v23; // rbx
  int v24; // edi
  int v25; // eax
  __int64 v26; // rcx
  _QWORD *v27; // rcx
  __int64 v28; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  _QWORD *v30; // [rsp+30h] [rbp-D0h] BYREF
  BSTR v31; // [rsp+38h] [rbp-C8h]
  VARIANTARG v32; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG v33; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG v34; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  int v36[4]; // [rsp+A0h] [rbp-60h] BYREF
  IRecordInfo *v37; // [rsp+B0h] [rbp-50h]
  __int128 v38; // [rsp+C0h] [rbp-40h] BYREF
  IRecordInfo *v39; // [rsp+D0h] [rbp-30h]
  __int128 v40; // [rsp+E0h] [rbp-20h] BYREF
  IRecordInfo *v41; // [rsp+F0h] [rbp-10h]
  VARIANTARG v42; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]
  __int64 *v44; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v45; // [rsp+1C8h] [rbp+C8h] BYREF

  v44 = 0;
  v2 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>((__int64 *)&v44);
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, (LPVOID *)v2);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF7,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  v4 = (__int64)v44;
  v5 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, __int128 *, __int128 *))(*v44 + 80);
  VariantInit(&pvarg);
  v6 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v34);
  v8 = *(_OWORD *)&v34.vt;
  v9 = v34.pRecInfo;
  VariantInit(&v33);
  v10 = *(_OWORD *)&v33.vt;
  v11 = v33.pRecInfo;
  VariantInit(&v32);
  *(_OWORD *)v36 = v6;
  v37 = pRecInfo;
  v38 = v8;
  v39 = v9;
  v40 = v10;
  v41 = v11;
  v42 = v32;
  v12 = v5(v4, &v42, &v40, &v38);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v12,
      (int)v36);
  VariantClear(&v32);
  VariantClear(&v33);
  VariantClear(&v34);
  VariantClear(&pvarg);
  v30 = 0;
  v13 = (__int64)v44;
  v14 = *v44;
  v15 = SysAllocString(L"\\Microsoft\\Windows\\Management\\Provisioning");
  v17 = v15;
  v31 = v15;
  if ( !v15 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v16);
  v18 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD **))(v14 + 56))(v13, v15, &v30);
  SysFreeString(v17);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xFE,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v18,
      (int)v36);
  v45 = 0;
  v19 = v30;
  v20 = *v30;
  v21 = SysAllocString(psz);
  v23 = v21;
  v31 = v21;
  if ( !v21 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v22);
  v24 = (*(__int64 (__fastcall **)(_QWORD *, BSTR, __int64 *))(v20 + 104))(v19, v21, &v45);
  SysFreeString(v23);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v24,
      (int)v36);
  v25 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v45 + 88LL))(v45, 0);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x105,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v25,
      (int)v36);
  v26 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v27 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v27 + 16LL))(v27);
  }
  v28 = (__int64)v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
}

```

## disassembly

```asm
0x1800387b4  mov     rax, rsp
0x1800387b7  push    rbp
0x1800387b8  push    rbx
0x1800387b9  push    rsi
0x1800387ba  push    rdi
0x1800387bb  push    r14
0x1800387bd  lea     rbp, [rsp-80h]
0x1800387c2  sub     rsp, 180h
0x1800387c9  movaps  xmmword ptr [rax-38h], xmm6
0x1800387cd  movaps  xmmword ptr [rax-48h], xmm7
0x1800387d1  movaps  xmmword ptr [rax-58h], xmm8
0x1800387d6  movaps  xmmword ptr [rax-68h], xmm9
0x1800387db  movaps  xmmword ptr [rax-78h], xmm10
0x1800387e0  movaps  xmmword ptr [rax-88h], xmm11
0x1800387e8  mov     r14, rcx
0x1800387eb  mov     [rbp+0A0h+arg_8], 0
0x1800387f5  mov     [rbp+0A0h+arg_10], 0
0x180038800  lea     rcx, [rbp+0A0h+arg_10]
0x180038807  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)
0x18003880c  mov     qword ptr [rsp+1A0h+ppv], rax; int
0x180038811  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180038818  xor     edx, edx; pUnkOuter
0x18003881a  lea     r8d, [rdx+1]; dwClsContext
0x18003881e  lea     rcx, CLSID_TaskScheduler; rclsid
0x180038825  call    cs:__imp_CoCreateInstance
0x18003882b  mov     rcx, [rbp+0A8h]; this
0x180038832  test    eax, eax
0x180038834  js      loc_180038AD8
0x18003883a  mov     rdi, [rbp+0A0h+arg_10]
0x180038841  mov     rax, [rdi]
0x180038844  mov     rbx, [rax+50h]
0x180038848  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x18003884c  call    cs:__imp_VariantInit
0x180038852  nop
0x180038853  movups  xmm10, xmmword ptr [rbp+0A0h+pvarg]
0x180038858  movsd   xmm11, qword ptr [rbp+0A0h+pvarg+10h]
0x18003885e  lea     rcx, [rsp+1A0h+var_130]; pvarg
0x180038863  call    cs:__imp_VariantInit
0x180038869  nop
0x18003886a  movups  xmm8, xmmword ptr [rsp+1A0h+var_130]
0x180038870  movsd   xmm9, qword ptr [rbp+0A0h+var_130+10h]
0x180038876  lea     rcx, [rsp+1A0h+var_148]; pvarg
0x18003887b  call    cs:__imp_VariantInit
0x180038881  nop
0x180038882  movups  xmm6, xmmword ptr [rsp+1A0h+var_148]
0x180038887  movsd   xmm7, qword ptr [rsp+1A0h+var_148+10h]
0x18003888d  lea     rcx, [rsp+1A0h+var_160]; pvarg
0x180038892  call    cs:__imp_VariantInit
0x180038898  nop
0x180038899  movups  xmm0, xmmword ptr [rsp+1A0h+var_160]
0x18003889e  movsd   xmm1, qword ptr [rsp+1A0h+var_160+10h]
0x1800388a4  movaps  xmmword ptr [rbp+0A0h+var_100], xmm10
0x1800388a9  movsd   [rbp+0A0h+var_F0], xmm11
0x1800388af  movaps  [rbp+0A0h+var_E0], xmm8
0x1800388b4  movsd   [rbp+0A0h+var_D0], xmm9
0x1800388ba  movaps  [rbp+0A0h+var_C0], xmm6
0x1800388be  movsd   [rbp+0A0h+var_B0], xmm7
0x1800388c3  movaps  [rbp+0A0h+var_A0], xmm0
0x1800388c7  movsd   [rbp+0A0h+var_90], xmm1
0x1800388cc  lea     rax, [rbp+0A0h+var_100]
0x1800388d0  mov     qword ptr [rsp+1A0h+ppv], rax; int
0x1800388d5  lea     r9, [rbp+0A0h+var_E0]
0x1800388d9  lea     r8, [rbp+0A0h+var_C0]
0x1800388dd  lea     rdx, [rbp+0A0h+var_A0]
0x1800388e1  mov     rcx, rdi
0x1800388e4  mov     rax, rbx
0x1800388e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388ec  mov     rcx, [rbp+0A8h]; this
0x1800388f3  test    eax, eax
0x1800388f5  js      loc_180038AED
0x1800388fb  lea     rcx, [rsp+1A0h+var_160]; pvarg
0x180038900  call    cs:__imp_VariantClear
0x180038906  nop
0x180038907  lea     rcx, [rsp+1A0h+var_148]; pvarg
0x18003890c  call    cs:__imp_VariantClear
0x180038912  nop
0x180038913  lea     rcx, [rsp+1A0h+var_130]; pvarg
0x180038918  call    cs:__imp_VariantClear
0x18003891e  nop
0x18003891f  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x180038923  call    cs:__imp_VariantClear
0x180038929  mov     [rsp+1A0h+var_170], 0
0x180038932  mov     rdi, [rbp+0A0h+arg_10]
0x180038939  mov     rsi, [rdi]
0x18003893c  lea     rcx, psz; "\\Microsoft\\Windows\\Management\\Provi"...
0x180038943  call    cs:__imp_SysAllocString
0x180038949  mov     rbx, rax
0x18003894c  mov     [rsp+1A0h+var_168], rax
0x180038951  mov     [rbp+0A0h+arg_8], 1
0x18003895b  mov     rcx, [rbp+0A8h]; this
0x180038962  test    rax, rax
0x180038965  jz      loc_180038B02
0x18003896b  lea     r8, [rsp+1A0h+var_170]
0x180038970  mov     rdx, rax
0x180038973  mov     rcx, rdi
0x180038976  mov     rax, [rsi+38h]
0x18003897a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003897f  mov     edi, eax
0x180038981  mov     rcx, rbx; bstrString
0x180038984  call    cs:__imp_SysFreeString
0x18003898a  mov     rcx, [rbp+0A8h]; this
0x180038991  test    edi, edi
0x180038993  js      loc_180038B14
0x180038999  mov     [rbp+0A0h+arg_18], 0
0x1800389a4  mov     rdi, [rsp+1A0h+var_170]
0x1800389a9  mov     rsi, [rdi]
0x1800389ac  mov     rcx, r14; psz
0x1800389af  call    cs:__imp_SysAllocString
0x1800389b5  mov     rbx, rax
0x1800389b8  mov     [rsp+1A0h+var_168], rax
0x1800389bd  mov     [rbp+0A0h+arg_8], 2
0x1800389c7  mov     rcx, [rbp+0A8h]; this
0x1800389ce  test    rax, rax
0x1800389d1  jz      loc_180038B29
0x1800389d7  lea     r8, [rbp+0A0h+arg_18]
0x1800389de  mov     rdx, rax
0x1800389e1  mov     rcx, rdi
0x1800389e4  mov     rax, [rsi+68h]
0x1800389e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800389ed  mov     edi, eax
0x1800389ef  mov     rcx, rbx; bstrString
0x1800389f2  call    cs:__imp_SysFreeString
0x1800389f8  mov     rcx, [rbp+0A8h]; this
0x1800389ff  test    edi, edi
0x180038a01  js      loc_180038B3B
0x180038a07  mov     rcx, [rbp+0A0h+arg_18]
0x180038a0e  mov     rax, [rcx]
0x180038a11  xor     edx, edx
0x180038a13  mov     rax, [rax+58h]
0x180038a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a1c  mov     rcx, [rbp+0A8h]; this
0x180038a23  test    eax, eax
0x180038a25  js      loc_180038AC3
0x180038a2b  mov     rcx, [rbp+0A0h+arg_18]
0x180038a32  test    rcx, rcx
0x180038a35  jz      short loc_180038A4F
0x180038a37  mov     [rbp+0A0h+arg_18], 0
0x180038a42  mov     rax, [rcx]
0x180038a45  mov     rax, [rax+10h]
0x180038a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a4e  nop
0x180038a4f  mov     rcx, [rsp+1A0h+var_170]
0x180038a54  test    rcx, rcx
0x180038a57  jz      short loc_180038A6F
0x180038a59  mov     [rsp+1A0h+var_170], 0
0x180038a62  mov     rax, [rcx]
0x180038a65  mov     rax, [rax+10h]
0x180038a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a6e  nop
0x180038a6f  mov     rcx, [rbp+0A0h+arg_10]
0x180038a76  test    rcx, rcx
0x180038a79  jz      short loc_180038A93
0x180038a7b  mov     [rbp+0A0h+arg_10], 0
0x180038a86  mov     rax, [rcx]
0x180038a89  mov     rax, [rax+10h]
0x180038a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a92  nop
0x180038a93  lea     r11, [rsp+1A0h+var_20]
0x180038a9b  movaps  xmm6, xmmword ptr [r11-10h]
0x180038aa0  movaps  xmm7, xmmword ptr [r11-20h]
0x180038aa5  movaps  xmm8, xmmword ptr [r11-30h]
0x180038aaa  movaps  xmm9, xmmword ptr [r11-40h]
0x180038aaf  movaps  xmm10, xmmword ptr [r11-50h]
0x180038ab4  movaps  xmm11, xmmword ptr [r11-60h]
0x180038ab9  mov     rsp, r11
0x180038abc  pop     r14
0x180038abe  pop     rdi
0x180038abf  pop     rsi
0x180038ac0  pop     rbx
0x180038ac1  pop     rbp
0x180038ac2  retn
0x180038ac3  mov     r9d, eax; char *
0x180038ac6  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x180038acd  mov     edx, 105h; void *
0x180038ad2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038ad8  mov     r9d, eax; char *
0x180038adb  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x180038ae2  mov     edx, 0F7h; void *
0x180038ae7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038aed  mov     r9d, eax; char *
0x180038af0  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x180038af7  mov     edx, 0F9h; void *
0x180038afc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038b02  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180038b09  mov     edx, 15F3h; void *
0x180038b0e  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180038b14  mov     r9d, edi; char *
0x180038b17  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x180038b1e  mov     edx, 0FEh; void *
0x180038b23  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038b29  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180038b30  mov     edx, 15F3h; void *
0x180038b35  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180038b3b  mov     r9d, edi; char *
0x180038b3e  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x180038b45  mov     edx, 102h; void *
0x180038b4a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
