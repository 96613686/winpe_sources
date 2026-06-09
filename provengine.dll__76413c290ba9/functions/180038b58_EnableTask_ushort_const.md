# EnableTask(ushort const *)

- ea: `0x180038b58`
- end: `0x180039007`
- name: `?EnableTask@@YAXPEBG@Z`
- size: `1199`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001b700`

## callees

- `0x1800092dc`
- `0x180009900`
- `0x180021cf4`
- `0x180021d14`
- `0x180038780`
- `0x180038b58`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038e95`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038e95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038e6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038eb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038e6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038eb2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038e3b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038e3b`
- `OLEAUT32!__imp_SysAllocString` at `0x180038ce8`
- `OLEAUT32!__imp_SysAllocString` at `0x180038d5f`
- `OLEAUT32!__imp_SysAllocString` at `0x180038ce8`
- `OLEAUT32!__imp_SysAllocString` at `0x180038d5f`
- `OLEAUT32!__imp_SysFreeString` at `0x180038d2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180038da2`
- `OLEAUT32!__imp_SysFreeString` at `0x180038d2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180038da2`
- `OLEAUT32!__imp_VariantInit` at `0x180038bf3`
- `OLEAUT32!__imp_VariantInit` at `0x180038c09`
- `OLEAUT32!__imp_VariantInit` at `0x180038c20`
- `OLEAUT32!__imp_VariantInit` at `0x180038c36`
- `OLEAUT32!__imp_VariantInit` at `0x180038bf3`
- `OLEAUT32!__imp_VariantInit` at `0x180038c09`
- `OLEAUT32!__imp_VariantInit` at `0x180038c20`
- `OLEAUT32!__imp_VariantInit` at `0x180038c36`
- `OLEAUT32!__imp_VariantClear` at `0x180038ca4`
- `OLEAUT32!__imp_VariantClear` at `0x180038cb0`
- `OLEAUT32!__imp_VariantClear` at `0x180038cbb`
- `OLEAUT32!__imp_VariantClear` at `0x180038cc6`
- `OLEAUT32!__imp_VariantClear` at `0x180038ca4`
- `OLEAUT32!__imp_VariantClear` at `0x180038cb0`
- `OLEAUT32!__imp_VariantClear` at `0x180038cbb`
- `OLEAUT32!__imp_VariantClear` at `0x180038cc6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038bcc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038bcc`

## string_xrefs

- `0x180038fa4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180038fcb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180038e4a`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x180038f68`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x180038f7d`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x180038f92`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x180038fb9`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x180038fe0`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x180038ff5`: `onecoreuap\admin\prov\lib\taskhelper.cpp`

## pseudocode

```c
void __fastcall EnableTask(const unsigned __int16 *a1)
{
  __int64 *v1; // rax
  HRESULT Instance; // eax
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v5; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v7; // xmm8
  IRecordInfo *v8; // xmm9_8
  __int128 v9; // xmm6
  __int64 v10; // xmm7_8
  int v11; // eax
  __int64 v12; // rdi
  __int64 v13; // rsi
  BSTR v14; // rax
  const char *v15; // r9
  OLECHAR *v16; // rbx
  int v17; // edi
  _QWORD *v18; // rdi
  __int64 v19; // rsi
  BSTR v20; // rax
  const char *v21; // r9
  OLECHAR *v22; // rbx
  int v23; // edi
  int v24; // eax
  bool IsStateSeparationEnabled; // al
  const WCHAR *v26; // rdx
  unsigned int v27; // eax
  __int64 v28; // rdx
  int v29; // ebx
  __int64 v30; // rcx
  _QWORD *v31; // rcx
  __int64 v32; // rcx
  int ppv; // [rsp+28h] [rbp-E0h]
  unsigned int ppva; // [rsp+28h] [rbp-E0h]
  VARIANTARG v35; // [rsp+58h] [rbp-B0h] BYREF
  VARIANTARG v36; // [rsp+70h] [rbp-98h] BYREF
  __int64 v37; // [rsp+88h] [rbp-80h]
  VARIANTARG v38; // [rsp+90h] [rbp-78h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-60h] BYREF
  int v40[4]; // [rsp+C8h] [rbp-40h] BYREF
  IRecordInfo *v41; // [rsp+D8h] [rbp-30h]
  __int128 v42; // [rsp+E8h] [rbp-20h] BYREF
  IRecordInfo *v43; // [rsp+F8h] [rbp-10h]
  __int128 v44; // [rsp+108h] [rbp+0h] BYREF
  __int64 v45; // [rsp+118h] [rbp+10h]
  __int128 v46; // [rsp+128h] [rbp+20h] BYREF
  __int64 v47; // [rsp+138h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+1D0h] [rbp+C8h]
  HKEY hKey; // [rsp+1D8h] [rbp+D0h] BYREF
  __int64 *v50; // [rsp+1E0h] [rbp+D8h] BYREF
  __int64 v51; // [rsp+1E8h] [rbp+E0h] BYREF
  _QWORD *v52; // [rsp+1F0h] [rbp+E8h] BYREF

  HIDWORD(hKey) = HIDWORD(a1);
  LODWORD(hKey) = 0;
  v50 = 0;
  v1 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>((__int64 *)&v50);
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, (LPVOID *)v1);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  v3 = (__int64)v50;
  v4 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *))(*v50 + 80);
  VariantInit(&pvarg);
  v5 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v38);
  v7 = *(_OWORD *)&v38.vt;
  v8 = v38.pRecInfo;
  VariantInit((VARIANTARG *)&v36.decVal.8);
  v9 = *(_OWORD *)&v36.decVal.Lo32;
  v10 = v37;
  VariantInit((VARIANTARG *)&v35.decVal.8);
  *(_OWORD *)v40 = v5;
  v41 = pRecInfo;
  v42 = v7;
  v43 = v8;
  v44 = v9;
  v45 = v10;
  v46 = *(_OWORD *)&v35.decVal.Lo32;
  v47 = *(_QWORD *)&v36.vt;
  v11 = v4(v3, &v46, &v44, &v42);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v11,
      (int)v40);
  VariantClear((VARIANTARG *)&v35.decVal.8);
  VariantClear((VARIANTARG *)&v36.decVal.8);
  VariantClear(&v38);
  VariantClear(&pvarg);
  v52 = 0;
  v12 = (__int64)v50;
  v13 = *v50;
  v14 = SysAllocString(L"\\Microsoft\\Windows\\Management\\Provisioning");
  v16 = v14;
  LODWORD(hKey) = 1;
  if ( !v14 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v15);
  v17 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD **))(v13 + 56))(v12, v14, &v52);
  SysFreeString(v16);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v17,
      (int)v40);
  v51 = 0;
  v18 = v52;
  v19 = *v52;
  v20 = SysAllocString(L"RunOnReboot");
  v22 = v20;
  LODWORD(hKey) = 2;
  if ( !v20 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v21);
  v23 = (*(__int64 (__fastcall **)(_QWORD *, BSTR, __int64 *))(v19 + 104))(v18, v20, &v51);
  SysFreeString(v22);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE9,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v23,
      (int)v40);
  v24 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v51 + 88LL))(v51, 0xFFFFFFFFLL);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v24,
      (int)v40);
  hKey = 0;
  IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
  v26 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\PendingReboot";
  if ( !IsStateSeparationEnabled )
    v26 = L"SOFTWARE\\Microsoft\\Provisioning\\PendingReboot";
  v27 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v26, 0, 0, 1u, 2u, 0, &hKey, 0);
  if ( v27 )
  {
    v28 = 209;
    goto LABEL_12;
  }
  v27 = RegSetValueExW(hKey, 0, 0, 4u, (const BYTE *)L"RunOnReboot", 0x18u);
  if ( v27 )
  {
    v28 = 212;
LABEL_12:
    v29 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v28,
            (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
            (const char *)v27,
            ppva);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_19;
  }
  if ( hKey )
    RegCloseKey(hKey);
  v29 = 0;
LABEL_19:
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v29,
      ppva);
  v30 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
  }
  v32 = (__int64)v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
}

```

## disassembly

```asm
0x180038b58  mov     rax, rsp
0x180038b5b  mov     [rax+8], rcx
0x180038b5f  push    rbp
0x180038b60  push    rbx
0x180038b61  push    rsi
0x180038b62  push    rdi
0x180038b63  push    r12
0x180038b65  lea     rbp, [rax-0C8h]
0x180038b6c  sub     rsp, 1A0h
0x180038b73  movaps  xmmword ptr [rax-38h], xmm6
0x180038b77  movaps  xmmword ptr [rax-48h], xmm7
0x180038b7b  movaps  xmmword ptr [rax-58h], xmm8
0x180038b80  movaps  xmmword ptr [rax-68h], xmm9
0x180038b85  movaps  xmmword ptr [rax-78h], xmm10
0x180038b8a  movaps  xmmword ptr [rax-88h], xmm11
0x180038b92  mov     dword ptr [rbp+0C0h+hKey], 0
0x180038b9c  mov     [rbp+0C0h+arg_8], 0
0x180038ba7  lea     rcx, [rbp+0C0h+arg_8]
0x180038bae  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)
0x180038bb3  mov     [rsp+1C0h+ppv], rax; int
0x180038bb8  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180038bbf  xor     edx, edx; pUnkOuter
0x180038bc1  lea     r8d, [rdx+1]; dwClsContext
0x180038bc5  lea     rcx, CLSID_TaskScheduler; rclsid
0x180038bcc  call    cs:__imp_CoCreateInstance
0x180038bd2  mov     rcx, [rbp+0C8h]; this
0x180038bd9  test    eax, eax
0x180038bdb  js      loc_180038F7A
0x180038be1  mov     rdi, [rbp+0C0h+arg_8]
0x180038be8  mov     rax, [rdi]
0x180038beb  mov     rbx, [rax+50h]
0x180038bef  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x180038bf3  call    cs:__imp_VariantInit
0x180038bf9  nop
0x180038bfa  movups  xmm10, xmmword ptr [rbp+0C0h+pvarg]
0x180038bff  movsd   xmm11, qword ptr [rbp+0C0h+pvarg+10h]
0x180038c05  lea     rcx, [rbp+0C0h+var_138]; pvarg
0x180038c09  call    cs:__imp_VariantInit
0x180038c0f  nop
0x180038c10  movups  xmm8, xmmword ptr [rbp+0C0h+var_138]
0x180038c15  movsd   xmm9, qword ptr [rbp+0C0h+var_138+10h]
0x180038c1b  lea     rcx, [rsp+1C0h+var_158+8]; pvarg
0x180038c20  call    cs:__imp_VariantInit
0x180038c26  nop
0x180038c27  movups  xmm6, xmmword ptr [rsp+1C0h+var_158+8]
0x180038c2c  movsd   xmm7, [rbp+0C0h+var_140]
0x180038c31  lea     rcx, [rsp+1C0h+var_170+8]; pvarg
0x180038c36  call    cs:__imp_VariantInit
0x180038c3c  nop
0x180038c3d  movups  xmm0, xmmword ptr [rsp+1C0h+var_170+8]
0x180038c42  movsd   xmm1, qword ptr [rsp+1C0h+var_158]
0x180038c48  movaps  xmmword ptr [rbp+0C0h+var_100], xmm10
0x180038c4d  movsd   [rbp+0C0h+var_F0], xmm11
0x180038c53  movaps  [rbp+0C0h+var_E0], xmm8
0x180038c58  movsd   [rbp+0C0h+var_D0], xmm9
0x180038c5e  movaps  [rbp+0C0h+var_C0], xmm6
0x180038c62  movsd   [rbp+0C0h+var_B0], xmm7
0x180038c67  movaps  [rbp+0C0h+var_A0], xmm0
0x180038c6b  movsd   [rbp+0C0h+var_90], xmm1
0x180038c70  lea     rax, [rbp+0C0h+var_100]
0x180038c74  mov     [rsp+1C0h+ppv], rax; int
0x180038c79  lea     r9, [rbp+0C0h+var_E0]
0x180038c7d  lea     r8, [rbp+0C0h+var_C0]
0x180038c81  lea     rdx, [rbp+0C0h+var_A0]
0x180038c85  mov     rcx, rdi
0x180038c88  mov     rax, rbx
0x180038c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c90  mov     rcx, [rbp+0C8h]; this
0x180038c97  test    eax, eax
0x180038c99  js      loc_180038F8F
0x180038c9f  lea     rcx, [rsp+1C0h+var_170+8]; pvarg
0x180038ca4  call    cs:__imp_VariantClear
0x180038caa  nop
0x180038cab  lea     rcx, [rsp+1C0h+var_158+8]; pvarg
0x180038cb0  call    cs:__imp_VariantClear
0x180038cb6  nop
0x180038cb7  lea     rcx, [rbp+0C0h+var_138]; pvarg
0x180038cbb  call    cs:__imp_VariantClear
0x180038cc1  nop
0x180038cc2  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x180038cc6  call    cs:__imp_VariantClear
0x180038ccc  mov     [rbp+0C0h+arg_18], 0
0x180038cd7  mov     rdi, [rbp+0C0h+arg_8]
0x180038cde  mov     rsi, [rdi]
0x180038ce1  lea     rcx, psz; "\\Microsoft\\Windows\\Management\\Provi"...
0x180038ce8  call    cs:__imp_SysAllocString
0x180038cee  mov     rbx, rax
0x180038cf1  mov     qword ptr [rsp+1C0h+var_170], rax
0x180038cf6  mov     dword ptr [rbp+0C0h+hKey], 1
0x180038d00  mov     rcx, [rbp+0C8h]; this
0x180038d07  test    rax, rax
0x180038d0a  jz      loc_180038FA4
0x180038d10  lea     r8, [rbp+0C0h+arg_18]
0x180038d17  mov     rdx, rax
0x180038d1a  mov     rcx, rdi
0x180038d1d  mov     rax, [rsi+38h]
0x180038d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d26  mov     edi, eax
0x180038d28  mov     rcx, rbx; bstrString
0x180038d2b  call    cs:__imp_SysFreeString
0x180038d31  mov     rcx, [rbp+0C8h]; this
0x180038d38  test    edi, edi
0x180038d3a  js      loc_180038FB6
0x180038d40  mov     [rbp+0C0h+arg_10], 0
0x180038d4b  mov     rdi, [rbp+0C0h+arg_18]
0x180038d52  mov     rsi, [rdi]
0x180038d55  lea     r12, aRunonreboot; "RunOnReboot"
0x180038d5c  mov     rcx, r12; psz
0x180038d5f  call    cs:__imp_SysAllocString
0x180038d65  mov     rbx, rax
0x180038d68  mov     qword ptr [rsp+1C0h+var_170], rax
0x180038d6d  mov     dword ptr [rbp+0C0h+hKey], 2
0x180038d77  mov     rcx, [rbp+0C8h]; this
0x180038d7e  test    rax, rax
0x180038d81  jz      loc_180038FCB
0x180038d87  lea     r8, [rbp+0C0h+arg_10]
0x180038d8e  mov     rdx, rax
0x180038d91  mov     rcx, rdi
0x180038d94  mov     rax, [rsi+68h]
0x180038d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d9d  mov     edi, eax
0x180038d9f  mov     rcx, rbx; bstrString
0x180038da2  call    cs:__imp_SysFreeString
0x180038da8  mov     rcx, [rbp+0C8h]; this
0x180038daf  test    edi, edi
0x180038db1  js      loc_180038FDD
0x180038db7  mov     rcx, [rbp+0C0h+arg_10]
0x180038dbe  mov     rax, [rcx]
0x180038dc1  or      edx, 0FFFFFFFFh
0x180038dc4  mov     rax, [rax+58h]
0x180038dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038dcd  mov     rcx, [rbp+0C8h]; this
0x180038dd4  test    eax, eax
0x180038dd6  js      loc_180038FF2
0x180038ddc  mov     [rbp+0C0h+hKey], 0
0x180038de7  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x180038dec  lea     rcx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Provisioning\\Pend"...
0x180038df3  lea     rdx, aOsdataSoftware_9; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x180038dfa  test    al, al
0x180038dfc  cmovz   rdx, rcx; lpSubKey
0x180038e00  mov     [rsp+1C0h+lpdwDisposition], 0; lpdwDisposition
0x180038e09  lea     rax, [rbp+0C0h+hKey]
0x180038e10  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180038e15  mov     [rsp+1C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180038e1e  mov     [rsp+1C0h+samDesired], 2; samDesired
0x180038e26  mov     dword ptr [rsp+1C0h+ppv], 1; unsigned int
0x180038e2e  xor     r9d, r9d; lpClass
0x180038e31  xor     r8d, r8d; Reserved
0x180038e34  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180038e3b  call    cs:__imp_RegCreateKeyExW
0x180038e41  test    eax, eax
0x180038e43  jz      short loc_180038E76
0x180038e45  mov     edx, 0D1h; void *
0x180038e4a  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x180038e51  mov     r9d, eax; char *
0x180038e54  mov     rcx, [rbp+0C8h]; this
0x180038e5b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180038e60  mov     ebx, eax
0x180038e62  mov     rcx, [rbp+0C0h+hKey]; hKey
0x180038e69  test    rcx, rcx
0x180038e6c  jz      short loc_180038EBA
0x180038e6e  call    cs:__imp_RegCloseKey
0x180038e74  jmp     short loc_180038EBA
0x180038e76  mov     [rsp+1C0h+samDesired], 18h; cbData
0x180038e7e  mov     [rsp+1C0h+ppv], r12; int
0x180038e83  mov     r9d, 4; dwType
0x180038e89  xor     r8d, r8d; Reserved
0x180038e8c  xor     edx, edx; lpValueName
0x180038e8e  mov     rcx, [rbp+0C0h+hKey]; hKey
0x180038e95  call    cs:__imp_RegSetValueExW
0x180038e9b  test    eax, eax
0x180038e9d  jz      short loc_180038EA6
0x180038e9f  mov     edx, 0D4h
0x180038ea4  jmp     short loc_180038E4A
0x180038ea6  mov     rcx, [rbp+0C0h+hKey]; hKey
0x180038ead  test    rcx, rcx
0x180038eb0  jz      short loc_180038EB8
0x180038eb2  call    cs:__imp_RegCloseKey
0x180038eb8  xor     ebx, ebx
0x180038eba  mov     rcx, [rbp+0C8h]; this
0x180038ec1  test    ebx, ebx
0x180038ec3  js      loc_180038F65
0x180038ec9  mov     rcx, [rbp+0C0h+arg_10]
0x180038ed0  test    rcx, rcx
0x180038ed3  jz      short loc_180038EED
0x180038ed5  mov     [rbp+0C0h+arg_10], 0
0x180038ee0  mov     rax, [rcx]
0x180038ee3  mov     rax, [rax+10h]
0x180038ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038eec  nop
0x180038eed  mov     rcx, [rbp+0C0h+arg_18]
0x180038ef4  test    rcx, rcx
0x180038ef7  jz      short loc_180038F11
0x180038ef9  mov     [rbp+0C0h+arg_18], 0
0x180038f04  mov     rax, [rcx]
0x180038f07  mov     rax, [rax+10h]
0x180038f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f10  nop
0x180038f11  mov     rcx, [rbp+0C0h+arg_8]
0x180038f18  test    rcx, rcx
0x180038f1b  jz      short loc_180038F35
0x180038f1d  mov     [rbp+0C0h+arg_8], 0
0x180038f28  mov     rax, [rcx]
0x180038f2b  mov     rax, [rax+10h]
0x180038f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f34  nop
0x180038f35  lea     r11, [rsp+1C0h+var_20]
0x180038f3d  movaps  xmm6, xmmword ptr [r11-10h]
0x180038f42  movaps  xmm7, xmmword ptr [r11-20h]
0x180038f47  movaps  xmm8, xmmword ptr [r11-30h]
0x180038f4c  movaps  xmm9, xmmword ptr [r11-40h]
0x180038f51  movaps  xmm10, xmmword ptr [r11-50h]
0x180038f56  movaps  xmm11, xmmword ptr [r11-60h]
0x180038f5b  mov     rsp, r11
0x180038f5e  pop     r12
0x180038f60  pop     rdi
0x180038f61  pop     rsi
0x180038f62  pop     rbx
0x180038f63  pop     rbp
0x180038f64  retn
0x180038f65  mov     r9d, ebx; char *
0x180038f68  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x180038f6f  mov     edx, 0EFh; void *
0x180038f74  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038f7a  mov     r9d, eax; char *
0x180038f7d  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x180038f84  mov     edx, 0DEh; void *
0x180038f89  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038f8f  mov     r9d, eax; char *
0x180038f92  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x180038f99  mov     edx, 0E0h; void *
0x180038f9e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038fa4  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180038fab  mov     edx, 15F3h; void *
0x180038fb0  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180038fb6  mov     r9d, edi; char *
0x180038fb9  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x180038fc0  mov     edx, 0E5h; void *
0x180038fc5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038fcb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180038fd2  mov     edx, 15F3h; void *
0x180038fd7  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180038fdd  mov     r9d, edi; char *
0x180038fe0  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x180038fe7  mov     edx, 0E9h; void *
0x180038fec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038ff2  mov     r9d, eax; char *
0x180038ff5  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x180038ffc  mov     edx, 0ECh; void *
0x180039001  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
