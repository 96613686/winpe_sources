# EnableTask(ushort const *)

- ea: `0x180027208`
- end: `0x18002769c`
- name: `?EnableTask@@YAXPEBG@Z`
- size: `1172`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180010b40`
- `0x180017938`

## callees

- `0x18001434c`
- `0x180017914`
- `0x18001b388`
- `0x18002072c`
- `0x180026248`
- `0x180027208`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002727c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002727c`
- `OLEAUT32!__imp_SysAllocString` at `0x180027392`
- `OLEAUT32!__imp_SysAllocString` at `0x1800273fa`
- `OLEAUT32!__imp_SysAllocString` at `0x180027392`
- `OLEAUT32!__imp_SysAllocString` at `0x1800273fa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800273d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002743d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800273d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002743d`
- `OLEAUT32!__imp_VariantInit` at `0x1800272a3`
- `OLEAUT32!__imp_VariantInit` at `0x1800272b9`
- `OLEAUT32!__imp_VariantInit` at `0x1800272d0`
- `OLEAUT32!__imp_VariantInit` at `0x1800272e6`
- `OLEAUT32!__imp_VariantInit` at `0x1800272a3`
- `OLEAUT32!__imp_VariantInit` at `0x1800272b9`
- `OLEAUT32!__imp_VariantInit` at `0x1800272d0`
- `OLEAUT32!__imp_VariantInit` at `0x1800272e6`
- `OLEAUT32!__imp_VariantClear` at `0x180027354`
- `OLEAUT32!__imp_VariantClear` at `0x180027360`
- `OLEAUT32!__imp_VariantClear` at `0x18002736b`
- `OLEAUT32!__imp_VariantClear` at `0x180027376`
- `OLEAUT32!__imp_VariantClear` at `0x180027354`
- `OLEAUT32!__imp_VariantClear` at `0x180027360`
- `OLEAUT32!__imp_VariantClear` at `0x18002736b`
- `OLEAUT32!__imp_VariantClear` at `0x180027376`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800274cd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800274cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027500`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027551`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027500`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027551`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027534`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027534`

## string_xrefs

- `0x180027639`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180027660`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x1800274dc`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800275fd`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x180027612`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x180027627`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x18002764e`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x180027675`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x18002768a`: `onecoreuap\admin\prov\lib\taskhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=58
void __fastcall EnableTask(const unsigned __int16 *a1)
{
  __int64 *v2; // rax
  HRESULT Instance; // eax
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v6; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v8; // xmm8
  IRecordInfo *v9; // xmm9_8
  __int128 v10; // xmm6
  __int64 v11; // xmm7_8
  int v12; // eax
  __int64 v13; // rdi
  __int64 v14; // r14
  BSTR v15; // rax
  const char *v16; // r9
  OLECHAR *v17; // rbx
  int v18; // edi
  _QWORD *v19; // rdi
  __int64 v20; // r14
  BSTR v21; // rax
  const char *v22; // r9
  OLECHAR *v23; // rbx
  int v24; // edi
  __int64 v25; // rbx
  int v26; // eax
  bool IsStateSeparationEnabled; // al
  const WCHAR *v28; // rdx
  unsigned int v29; // eax
  __int64 v30; // rdx
  int v31; // ebx
  __int64 v32; // rcx
  _QWORD *v33; // rcx
  __int64 v34; // rcx
  int ppv; // [rsp+28h] [rbp-E0h]
  unsigned int ppva; // [rsp+28h] [rbp-E0h]
  _QWORD *v37; // [rsp+58h] [rbp-B0h] BYREF
  VARIANTARG v38; // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG v39; // [rsp+78h] [rbp-90h] BYREF
  __int64 v40; // [rsp+90h] [rbp-78h]
  VARIANTARG v41; // [rsp+98h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-58h] BYREF
  int v43[4]; // [rsp+C8h] [rbp-40h] BYREF
  IRecordInfo *v44; // [rsp+D8h] [rbp-30h]
  __int128 v45; // [rsp+E8h] [rbp-20h] BYREF
  IRecordInfo *v46; // [rsp+F8h] [rbp-10h]
  __int128 v47; // [rsp+108h] [rbp+0h] BYREF
  __int64 v48; // [rsp+118h] [rbp+10h]
  __int128 v49; // [rsp+128h] [rbp+20h] BYREF
  __int64 v50; // [rsp+138h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+1D0h] [rbp+C8h]
  HKEY hKey; // [rsp+1E0h] [rbp+D8h] BYREF
  __int64 *v53; // [rsp+1E8h] [rbp+E0h] BYREF
  __int64 v54; // [rsp+1F0h] [rbp+E8h] BYREF

  LODWORD(hKey) = 0;
  v53 = 0;
  v2 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>((__int64 *)&v53);
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, (LPVOID *)v2);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  v4 = (__int64)v53;
  v5 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *))(*v53 + 80);
  VariantInit(&pvarg);
  v6 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v41);
  v8 = *(_OWORD *)&v41.vt;
  v9 = v41.pRecInfo;
  VariantInit((VARIANTARG *)&v39.decVal.8);
  v10 = *(_OWORD *)&v39.decVal.Lo32;
  v11 = v40;
  VariantInit((VARIANTARG *)&v38.decVal.8);
  *(_OWORD *)v43 = v6;
  v44 = pRecInfo;
  v45 = v8;
  v46 = v9;
  v47 = v10;
  v48 = v11;
  v49 = *(_OWORD *)&v38.decVal.Lo32;
  v50 = *(_QWORD *)&v39.vt;
  v12 = v5(v4, &v49, &v47, &v45);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v12,
      (int)v43);
  VariantClear((VARIANTARG *)&v38.decVal.8);
  VariantClear((VARIANTARG *)&v39.decVal.8);
  VariantClear(&v41);
  VariantClear(&pvarg);
  v37 = 0;
  v13 = (__int64)v53;
  v14 = *v53;
  v15 = SysAllocString(L"\\Microsoft\\Windows\\Management\\Provisioning");
  v17 = v15;
  *(_QWORD *)&v38.vt = v15;
  LODWORD(hKey) = 1;
  if ( !v15 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v16);
  v18 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD **))(v14 + 56))(v13, v15, &v37);
  SysFreeString(v17);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v18,
      (int)v43);
  v54 = 0;
  v19 = v37;
  v20 = *v37;
  v21 = SysAllocString(a1);
  v23 = v21;
  *(_QWORD *)&v38.vt = v21;
  LODWORD(hKey) = 2;
  if ( !v21 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v22);
  v24 = (*(__int64 (__fastcall **)(_QWORD *, BSTR, __int64 *))(v20 + 104))(v19, v21, &v54);
  SysFreeString(v23);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE9,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v24,
      (int)v43);
  v25 = -1;
  v26 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v54 + 88LL))(v54, 0xFFFFFFFFLL);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v26,
      (int)v43);
  hKey = 0;
  IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
  v28 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\PendingReboot";
  if ( !IsStateSeparationEnabled )
    v28 = L"SOFTWARE\\Microsoft\\Provisioning\\PendingReboot";
  v29 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v28, 0, 0, 1u, 2u, 0, &hKey, 0);
  if ( v29 )
  {
    v30 = 209;
    goto LABEL_12;
  }
  do
    ++v25;
  while ( a1[v25] );
  v29 = RegSetValueExW(hKey, 0, 0, 4u, (const BYTE *)a1, 2 * v25 + 2);
  if ( v29 )
  {
    v30 = 212;
LABEL_12:
    v31 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v30,
            (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
            (const char *)v29,
            ppva);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_20;
  }
  if ( hKey )
    RegCloseKey(hKey);
  v31 = 0;
LABEL_20:
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v31,
      ppva);
  v32 = v54;
  if ( v54 )
  {
    v54 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  v33 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v33 + 16LL))(v33);
  }
  v34 = (__int64)v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
}

```

## disassembly

```asm
0x180027208  mov     rax, rsp
0x18002720b  mov     [rax+8], rbx
0x18002720f  push    rbp
0x180027210  push    rsi
0x180027211  push    rdi
0x180027212  push    r14
0x180027214  push    r15
0x180027216  lea     rbp, [rax-0C8h]
0x18002721d  sub     rsp, 1A0h
0x180027224  movaps  xmmword ptr [rax-38h], xmm6
0x180027228  movaps  xmmword ptr [rax-48h], xmm7
0x18002722c  movaps  xmmword ptr [rax-58h], xmm8
0x180027231  movaps  xmmword ptr [rax-68h], xmm9
0x180027236  movaps  xmmword ptr [rax-78h], xmm10
0x18002723b  movaps  xmmword ptr [rax-88h], xmm11
0x180027243  mov     rsi, rcx
0x180027246  xor     r15d, r15d
0x180027249  mov     dword ptr [rbp+0C0h+hKey], r15d
0x180027250  mov     [rbp+0C0h+arg_10], r15
0x180027257  lea     rcx, [rbp+0C0h+arg_10]
0x18002725e  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)
0x180027263  mov     [rsp+1C0h+ppv], rax; int
0x180027268  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18002726f  xor     edx, edx; pUnkOuter
0x180027271  lea     r8d, [r15+1]; dwClsContext
0x180027275  lea     rcx, CLSID_TaskScheduler; rclsid
0x18002727c  call    cs:__imp_CoCreateInstance
0x180027282  mov     rcx, [rbp+0C8h]; this
0x180027289  test    eax, eax
0x18002728b  js      loc_18002760F
0x180027291  mov     rdi, [rbp+0C0h+arg_10]
0x180027298  mov     rax, [rdi]
0x18002729b  mov     rbx, [rax+50h]
0x18002729f  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x1800272a3  call    cs:__imp_VariantInit
0x1800272a9  nop
0x1800272aa  movups  xmm10, xmmword ptr [rbp+0C0h+pvarg]
0x1800272af  movsd   xmm11, qword ptr [rbp+0C0h+pvarg+10h]
0x1800272b5  lea     rcx, [rbp+0C0h+var_130]; pvarg
0x1800272b9  call    cs:__imp_VariantInit
0x1800272bf  nop
0x1800272c0  movups  xmm8, xmmword ptr [rbp+0C0h+var_130]
0x1800272c5  movsd   xmm9, qword ptr [rbp+0C0h+var_130+10h]
0x1800272cb  lea     rcx, [rsp+1C0h+var_150+8]; pvarg
0x1800272d0  call    cs:__imp_VariantInit
0x1800272d6  nop
0x1800272d7  movups  xmm6, xmmword ptr [rsp+1C0h+var_150+8]
0x1800272dc  movsd   xmm7, [rbp+0C0h+var_138]
0x1800272e1  lea     rcx, [rsp+1C0h+var_168+8]; pvarg
0x1800272e6  call    cs:__imp_VariantInit
0x1800272ec  nop
0x1800272ed  movups  xmm0, xmmword ptr [rsp+1C0h+var_168+8]
0x1800272f2  movsd   xmm1, qword ptr [rsp+1C0h+var_150]
0x1800272f8  movaps  xmmword ptr [rbp+0C0h+var_100], xmm10
0x1800272fd  movsd   [rbp+0C0h+var_F0], xmm11
0x180027303  movaps  [rbp+0C0h+var_E0], xmm8
0x180027308  movsd   [rbp+0C0h+var_D0], xmm9
0x18002730e  movaps  [rbp+0C0h+var_C0], xmm6
0x180027312  movsd   [rbp+0C0h+var_B0], xmm7
0x180027317  movaps  [rbp+0C0h+var_A0], xmm0
0x18002731b  movsd   [rbp+0C0h+var_90], xmm1
0x180027320  lea     rax, [rbp+0C0h+var_100]
0x180027324  mov     [rsp+1C0h+ppv], rax; int
0x180027329  lea     r9, [rbp+0C0h+var_E0]
0x18002732d  lea     r8, [rbp+0C0h+var_C0]
0x180027331  lea     rdx, [rbp+0C0h+var_A0]
0x180027335  mov     rcx, rdi
0x180027338  mov     rax, rbx
0x18002733b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027340  mov     rcx, [rbp+0C8h]; this
0x180027347  test    eax, eax
0x180027349  js      loc_180027624
0x18002734f  lea     rcx, [rsp+1C0h+var_168+8]; pvarg
0x180027354  call    cs:__imp_VariantClear
0x18002735a  nop
0x18002735b  lea     rcx, [rsp+1C0h+var_150+8]; pvarg
0x180027360  call    cs:__imp_VariantClear
0x180027366  nop
0x180027367  lea     rcx, [rbp+0C0h+var_130]; pvarg
0x18002736b  call    cs:__imp_VariantClear
0x180027371  nop
0x180027372  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x180027376  call    cs:__imp_VariantClear
0x18002737c  mov     [rsp+1C0h+var_170], r15
0x180027381  mov     rdi, [rbp+0C0h+arg_10]
0x180027388  mov     r14, [rdi]
0x18002738b  lea     rcx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\Management\\Provi"...
0x180027392  call    cs:__imp_SysAllocString
0x180027398  mov     rbx, rax
0x18002739b  mov     qword ptr [rsp+1C0h+var_168], rax
0x1800273a0  mov     dword ptr [rbp+0C0h+hKey], 1
0x1800273aa  mov     rcx, [rbp+0C8h]; this
0x1800273b1  test    rax, rax
0x1800273b4  jz      loc_180027639
0x1800273ba  lea     r8, [rsp+1C0h+var_170]
0x1800273bf  mov     rdx, rax
0x1800273c2  mov     rcx, rdi
0x1800273c5  mov     rax, [r14+38h]
0x1800273c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273ce  mov     edi, eax
0x1800273d0  mov     rcx, rbx; bstrString
0x1800273d3  call    cs:__imp_SysFreeString
0x1800273d9  mov     rcx, [rbp+0C8h]; this
0x1800273e0  test    edi, edi
0x1800273e2  js      loc_18002764B
0x1800273e8  mov     [rbp+0C0h+arg_18], r15
0x1800273ef  mov     rdi, [rsp+1C0h+var_170]
0x1800273f4  mov     r14, [rdi]
0x1800273f7  mov     rcx, rsi; psz
0x1800273fa  call    cs:__imp_SysAllocString
0x180027400  mov     rbx, rax
0x180027403  mov     qword ptr [rsp+1C0h+var_168], rax
0x180027408  mov     dword ptr [rbp+0C0h+hKey], 2
0x180027412  mov     rcx, [rbp+0C8h]; this
0x180027419  test    rax, rax
0x18002741c  jz      loc_180027660
0x180027422  lea     r8, [rbp+0C0h+arg_18]
0x180027429  mov     rdx, rax
0x18002742c  mov     rcx, rdi
0x18002742f  mov     rax, [r14+68h]
0x180027433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027438  mov     edi, eax
0x18002743a  mov     rcx, rbx; bstrString
0x18002743d  call    cs:__imp_SysFreeString
0x180027443  mov     rcx, [rbp+0C8h]; this
0x18002744a  test    edi, edi
0x18002744c  js      loc_180027672
0x180027452  mov     rcx, [rbp+0C0h+arg_18]
0x180027459  mov     rax, [rcx]
0x18002745c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180027460  mov     edx, ebx
0x180027462  mov     rax, [rax+58h]
0x180027466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002746b  mov     rcx, [rbp+0C8h]; this
0x180027472  test    eax, eax
0x180027474  js      loc_180027687
0x18002747a  mov     [rbp+0C0h+hKey], r15
0x180027481  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x180027486  lea     rcx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Provisioning\\Pend"...
0x18002748d  lea     rdx, aOsdataSoftware_6; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x180027494  test    al, al
0x180027496  cmovz   rdx, rcx; lpSubKey
0x18002749a  mov     [rsp+1C0h+lpdwDisposition], r15; lpdwDisposition
0x18002749f  lea     rax, [rbp+0C0h+hKey]
0x1800274a6  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800274ab  mov     [rsp+1C0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800274b0  mov     [rsp+1C0h+samDesired], 2; samDesired
0x1800274b8  mov     dword ptr [rsp+1C0h+ppv], 1; unsigned int
0x1800274c0  xor     r9d, r9d; lpClass
0x1800274c3  xor     r8d, r8d; Reserved
0x1800274c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800274cd  call    cs:__imp_RegCreateKeyExW
0x1800274d3  test    eax, eax
0x1800274d5  jz      short loc_180027508
0x1800274d7  mov     edx, 0D1h; void *
0x1800274dc  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x1800274e3  mov     r9d, eax; char *
0x1800274e6  mov     rcx, [rbp+0C8h]; this
0x1800274ed  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800274f2  mov     ebx, eax
0x1800274f4  mov     rcx, [rbp+0C0h+hKey]; hKey
0x1800274fb  test    rcx, rcx
0x1800274fe  jz      short loc_18002755A
0x180027500  call    cs:__imp_RegCloseKey
0x180027506  jmp     short loc_18002755A
0x180027508  inc     rbx
0x18002750b  cmp     [rsi+rbx*2], r15w
0x180027510  jnz     short loc_180027508
0x180027512  lea     eax, ds:2[rbx*2]
0x180027519  mov     [rsp+1C0h+samDesired], eax; cbData
0x18002751d  mov     [rsp+1C0h+ppv], rsi; int
0x180027522  mov     r9d, 4; dwType
0x180027528  xor     r8d, r8d; Reserved
0x18002752b  xor     edx, edx; lpValueName
0x18002752d  mov     rcx, [rbp+0C0h+hKey]; hKey
0x180027534  call    cs:__imp_RegSetValueExW
0x18002753a  test    eax, eax
0x18002753c  jz      short loc_180027545
0x18002753e  mov     edx, 0D4h
0x180027543  jmp     short loc_1800274DC
0x180027545  mov     rcx, [rbp+0C0h+hKey]; hKey
0x18002754c  test    rcx, rcx
0x18002754f  jz      short loc_180027557
0x180027551  call    cs:__imp_RegCloseKey
0x180027557  mov     ebx, r15d
0x18002755a  mov     rcx, [rbp+0C8h]; this
0x180027561  test    ebx, ebx
0x180027563  js      loc_1800275FA
0x180027569  mov     rcx, [rbp+0C0h+arg_18]
0x180027570  test    rcx, rcx
0x180027573  jz      short loc_180027589
0x180027575  mov     [rbp+0C0h+arg_18], r15
0x18002757c  mov     rax, [rcx]
0x18002757f  mov     rax, [rax+10h]
0x180027583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027588  nop
0x180027589  mov     rcx, [rsp+1C0h+var_170]
0x18002758e  test    rcx, rcx
0x180027591  jz      short loc_1800275A5
0x180027593  mov     [rsp+1C0h+var_170], r15
0x180027598  mov     rax, [rcx]
0x18002759b  mov     rax, [rax+10h]
0x18002759f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275a4  nop
0x1800275a5  mov     rcx, [rbp+0C0h+arg_10]
0x1800275ac  test    rcx, rcx
0x1800275af  jz      short loc_1800275C5
0x1800275b1  mov     [rbp+0C0h+arg_10], r15
0x1800275b8  mov     rax, [rcx]
0x1800275bb  mov     rax, [rax+10h]
0x1800275bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275c4  nop
0x1800275c5  lea     r11, [rsp+1C0h+var_20]
0x1800275cd  mov     rbx, [r11+30h]
0x1800275d1  movaps  xmm6, xmmword ptr [r11-10h]
0x1800275d6  movaps  xmm7, xmmword ptr [r11-20h]
0x1800275db  movaps  xmm8, xmmword ptr [r11-30h]
0x1800275e0  movaps  xmm9, xmmword ptr [r11-40h]
0x1800275e5  movaps  xmm10, xmmword ptr [r11-50h]
0x1800275ea  movaps  xmm11, xmmword ptr [r11-60h]
0x1800275ef  mov     rsp, r11
0x1800275f2  pop     r15
0x1800275f4  pop     r14
0x1800275f6  pop     rdi
0x1800275f7  pop     rsi
0x1800275f8  pop     rbp
0x1800275f9  retn
0x1800275fa  mov     r9d, ebx; char *
0x1800275fd  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x180027604  mov     edx, 0EFh; void *
0x180027609  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002760f  mov     r9d, eax; char *
0x180027612  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x180027619  mov     edx, 0DEh; void *
0x18002761e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027624  mov     r9d, eax; char *
0x180027627  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x18002762e  mov     edx, 0E0h; void *
0x180027633  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027639  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180027640  mov     edx, 15F3h; void *
0x180027645  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18002764b  mov     r9d, edi; char *
0x18002764e  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x180027655  mov     edx, 0E5h; void *
0x18002765a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027660  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180027667  mov     edx, 15F3h; void *
0x18002766c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180027672  mov     r9d, edi; char *
0x180027675  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x18002767c  mov     edx, 0E9h; void *
0x180027681  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027687  mov     r9d, eax; char *
0x18002768a  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x180027691  mov     edx, 0ECh; void *
0x180027696  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
