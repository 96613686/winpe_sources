# UtilsRemakeSCEPInstallationTask(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x180025b20`
- end: `0x1800261ca`
- name: `?UtilsRemakeSCEPInstallationTask@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `1706`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800261d0`

## callees

- `0x1800039f0`
- `0x1800043a8`
- `0x18000604c`
- `0x1800064ae`
- `0x18000bab4`
- `0x18000c63c`
- `0x180010c8c`
- `0x180010f74`
- `0x180012314`
- `0x1800245d0`
- `0x180025b20`
- `0x1800388e0`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025f92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025f92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025c9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025ed0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025f8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026139`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025c9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025ed0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025f8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026139`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180025c70`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180025dd5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180025e27`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180025e41`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180025e6f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180025f5b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180025fdf`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180026048`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180026077`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180025c70`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180025dd5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180025e27`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180025e41`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180025e6f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180025f5b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180025fdf`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180026048`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180026077`
- `DMCmnUtils!DmImpersonate` at `0x180025c20`
- `DMCmnUtils!DmImpersonate` at `0x180025f0a`
- `DMCmnUtils!DmImpersonate` at `0x180025c20`
- `DMCmnUtils!DmImpersonate` at `0x180025f0a`
- `DMCmnUtils!DmRevertToSelf` at `0x180025c68`
- `DMCmnUtils!DmRevertToSelf` at `0x180025d92`
- `DMCmnUtils!DmRevertToSelf` at `0x180025dcd`
- `DMCmnUtils!DmRevertToSelf` at `0x180025e1f`
- `DMCmnUtils!DmRevertToSelf` at `0x180025e67`
- `DMCmnUtils!DmRevertToSelf` at `0x180025f53`
- `DMCmnUtils!DmRevertToSelf` at `0x180025fd7`
- `DMCmnUtils!DmRevertToSelf` at `0x180026040`
- `DMCmnUtils!DmRevertToSelf` at `0x18002606f`
- `DMCmnUtils!DmRevertToSelf` at `0x180025c68`
- `DMCmnUtils!DmRevertToSelf` at `0x180025d92`
- `DMCmnUtils!DmRevertToSelf` at `0x180025dcd`
- `DMCmnUtils!DmRevertToSelf` at `0x180025e1f`
- `DMCmnUtils!DmRevertToSelf` at `0x180025e67`
- `DMCmnUtils!DmRevertToSelf` at `0x180025f53`
- `DMCmnUtils!DmRevertToSelf` at `0x180025fd7`
- `DMCmnUtils!DmRevertToSelf` at `0x180026040`
- `DMCmnUtils!DmRevertToSelf` at `0x18002606f`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x180025fa2`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x180025fa2`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180025cd1`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180025d01`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180025cd1`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180025d01`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UtilsRemakeSCEPInstallationTask(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  _QWORD *v7; // rsi
  char v8; // di
  char v9; // bl
  int v10; // eax
  unsigned int v11; // r14d
  int DWORD; // eax
  int v14; // eax
  const wchar_t *v15; // rax
  int v16; // eax
  void *v17; // rdx
  unsigned int v18; // r8d
  void *v19; // rdx
  unsigned int v20; // r8d
  HRESULT v21; // eax
  void *v22; // rdx
  unsigned int v23; // r8d
  HRESULT v24; // eax
  void *v25; // rdx
  unsigned int v26; // r8d
  HRESULT v27; // eax
  HRESULT v28; // eax
  int v29; // ebx
  __int64 v30; // rdx
  char v31; // r14
  char v32; // di
  int v33; // eax
  int CurrentUserSid; // eax
  void *v35; // rdx
  unsigned int v36; // r8d
  HRESULT v37; // eax
  int v38; // eax
  void *v39; // rdx
  __int64 v40; // r8
  void *v41; // rdx
  unsigned int v42; // r8d
  HRESULT v43; // eax
  HRESULT v44; // eax
  unsigned __int64 v45; // rdx
  void **v46; // rdi
  __int64 v47; // rbx
  void **v48; // rdx
  int v49; // [rsp+20h] [rbp-E0h]
  int v50; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v52; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v53; // [rsp+3Ch] [rbp-C4h] BYREF
  char v54; // [rsp+40h] [rbp-C0h]
  char v55; // [rsp+42h] [rbp-BEh]
  HKEY v56; // [rsp+50h] [rbp-B0h]
  _QWORD *v57; // [rsp+58h] [rbp-A8h]
  void *Src[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v59; // [rsp+70h] [rbp-90h]
  unsigned __int64 v60; // [rsp+78h] [rbp-88h]
  unsigned __int16 v61[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v62[30]; // [rsp+90h] [rbp-70h]
  _BYTE v63[2514]; // [rsp+AEh] [rbp-52h] BYREF
  unsigned __int16 v64[2]; // [rsp+A80h] [rbp+980h] BYREF
  _BYTE v65[2556]; // [rsp+A84h] [rbp+984h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+14D8h] [rbp+13D8h]

  v56 = a1;
  *(_OWORD *)v61 = *(_OWORD *)L"-s -k \"%s\" -h %s -t %s";
  *(_OWORD *)v62 = *(_OWORD *)L"s\" -h %s -t %s";
  *(_OWORD *)&v62[14] = *(_OWORD *)L"s -t %s";
  memset_0(v63, 0, 0x9D0u);
  *(_DWORD *)v64 = 0;
  memset_0(v65, 0, 0x9FAu);
  v7 = operator new(0x20u);
  *v7 = &SCEPTaskSchedulerImpl::`vftable';
  v7[1] = 0;
  v7[2] = 0;
  v7[3] = 0;
  v57 = v7;
  v53 = 1;
  v52 = 1;
  hMem = 0;
  *(_OWORD *)Src = 0;
  v59 = 0;
  v60 = 7;
  LOWORD(Src[0]) = 0;
  v8 = 0;
  v54 = 0;
  v9 = 0;
  v55 = 0;
  if ( a4 )
  {
    v10 = DmImpersonate(a4);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC43,
        (int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
        (const char *)(unsigned int)v10);
LABEL_5:
      std::wstring::~wstring((char **)Src);
      (*(void (__fastcall **)(_QWORD *, __int64))(*v7 + 32LL))(v7, 1);
      return v11;
    }
    v8 = 1;
    v54 = 1;
    v9 = 1;
    v55 = 1;
  }
  DWORD = OmaDmRegistryGetDWORD(v56, a2, L"RetryDelay", &v52);
  v11 = DWORD;
  if ( DWORD == -2147024894 )
  {
    v52 = 5;
  }
  else if ( DWORD < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4E,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
      (const char *)(unsigned int)DWORD);
    v24 = 0;
    if ( v8 )
    {
      if ( v9 )
        v24 = DmRevertToSelf();
      else
        v24 = CoRevertToSelf();
    }
    if ( v24 < 0 )
      wil::details::in1diag3::_FailFast_Hr(retaddr, v22, v23, (const char *)(unsigned int)v24, v49);
    goto LABEL_5;
  }
  v14 = OmaDmRegistryGetDWORD(v56, a2, L"RetryCount", &v53);
  v11 = v14;
  if ( v14 == -2147024894 )
  {
    v53 = 3;
  }
  else if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC58,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
      (const char *)(unsigned int)v14);
    v27 = 0;
    if ( v8 )
    {
      if ( v9 )
        v27 = DmRevertToSelf();
      else
        v27 = CoRevertToSelf();
    }
    if ( v27 < 0 )
      wil::details::in1diag3::_FailFast_Hr(retaddr, v25, v26, (const char *)(unsigned int)v27, v49);
    goto LABEL_5;
  }
  v15 = L"HKCU";
  if ( !a4 )
    v15 = (const wchar_t *)L"HKLM";
  v16 = StringCchPrintfW(v64, 0x4FFu, v61, a2, v15, a3);
  v11 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5A,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
      (const char *)(unsigned int)v16);
    v21 = 0;
    if ( v8 )
    {
      if ( v9 )
        v21 = DmRevertToSelf();
      else
        v21 = CoRevertToSelf();
    }
    if ( v21 < 0 )
      wil::details::in1diag3::_FailFast_Hr(retaddr, v19, v20, (const char *)(unsigned int)v21, v50);
    goto LABEL_5;
  }
  v28 = 0;
  if ( v8 )
  {
    if ( v9 )
      v28 = DmRevertToSelf();
    else
      v28 = CoRevertToSelf();
  }
  if ( v28 < 0 )
    wil::details::in1diag3::_FailFast_Hr(retaddr, v17, v18, (const char *)(unsigned int)v28, v50);
  v29 = (*(__int64 (__fastcall **)(_QWORD *, unsigned __int16 *))*v7)(v7, v64);
  if ( v29 < 0 )
  {
    v30 = 3166;
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
      (const char *)(unsigned int)v29);
LABEL_41:
    std::wstring::~wstring((char **)Src);
    if ( hMem )
      LocalFree(hMem);
    (*(void (__fastcall **)(_QWORD *, __int64))(*v7 + 32LL))(v7, 1);
    return (unsigned int)v29;
  }
  v31 = 0;
  v54 = 0;
  v32 = 0;
  v55 = 0;
  if ( a4 )
  {
    v33 = DmImpersonate(a4);
    v29 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC69,
        (int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
        (const char *)(unsigned int)v33);
      goto LABEL_41;
    }
    v31 = 1;
    v54 = 1;
    v32 = 1;
    v55 = 1;
  }
  hMem = 0;
  CurrentUserSid = DmGetCurrentUserSid((unsigned __int16 **)&hMem);
  v29 = CurrentUserSid;
  if ( CurrentUserSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC6B,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
      (const char *)(unsigned int)CurrentUserSid);
    v37 = 0;
    if ( v31 )
    {
      if ( v32 )
        v37 = DmRevertToSelf();
      else
        v37 = CoRevertToSelf();
    }
    if ( v37 < 0 )
      wil::details::in1diag3::_FailFast_Hr(retaddr, v35, v36, (const char *)(unsigned int)v37, v50);
    goto LABEL_41;
  }
  v38 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD))(*v7 + 8LL))(v7, v53, v52);
  v29 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC6E,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\sceputils.cpp",
      (const char *)(unsigned int)v38);
    v43 = 0;
    if ( v31 )
    {
      if ( v32 )
        v43 = DmRevertToSelf();
      else
        v43 = CoRevertToSelf();
    }
    if ( v43 < 0 )
      wil::details::in1diag3::_FailFast_Hr(retaddr, v41, v42, (const char *)(unsigned int)v43, v50);
    goto LABEL_41;
  }
  v44 = 0;
  if ( v31 )
  {
    if ( v32 )
      v44 = DmRevertToSelf();
    else
      v44 = CoRevertToSelf();
  }
  if ( v44 < 0 )
    wil::details::in1diag3::_FailFast_Hr(retaddr, v39, v40, (const char *)(unsigned int)v44, v50);
  v45 = -1;
  do
    ++v45;
  while ( a3[v45] );
  if ( v45 > v60 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(Src, v45, v40, a3);
  }
  else
  {
    v46 = Src;
    if ( v60 > 7 )
      v46 = (void **)Src[0];
    v59 = v45;
    v47 = 2 * v45;
    memmove_0(v46, a3, 2 * v45);
    *(_WORD *)((char *)v46 + v47) = 0;
  }
  std::wstring::append(Src, hMem);
  v48 = Src;
  if ( v60 > 7 )
    v48 = (void **)Src[0];
  v29 = (*(__int64 (__fastcall **)(_QWORD *, void **, HLOCAL, _QWORD))(*v7 + 24LL))(v7, v48, hMem, 0);
  if ( v29 < 0 )
  {
    v30 = 3191;
    goto LABEL_40;
  }
  std::wstring::~wstring((char **)Src);
  if ( hMem )
    LocalFree(hMem);
  (*(void (__fastcall **)(_QWORD *, __int64))(*v7 + 32LL))(v7, 1);
  return 0;
}

```

## disassembly

```asm
0x180025b20  push    rbp
0x180025b22  push    rbx
0x180025b23  push    rsi
0x180025b24  push    rdi
0x180025b25  push    r12
0x180025b27  push    r13
0x180025b29  push    r14
0x180025b2b  push    r15
0x180025b2d  lea     rbp, [rsp-1398h]
0x180025b35  mov     eax, 1498h
0x180025b3a  call    _alloca_probe
0x180025b3f  sub     rsp, rax
0x180025b42  mov     rax, cs:__security_cookie
0x180025b49  xor     rax, rsp
0x180025b4c  mov     [rbp+13D0h+var_50], rax
0x180025b53  mov     r15, r9
0x180025b56  mov     r12, r8
0x180025b59  mov     r13, rdx
0x180025b5c  mov     [rsp+14D0h+var_1480], rcx
0x180025b61  movups  xmm0, xmmword ptr cs:aSKSHSTS; "-s -k \"%s\" -h %s -t %s"
0x180025b68  movaps  xmmword ptr [rbp+13D0h+var_1450], xmm0
0x180025b6c  movups  xmm1, xmmword ptr cs:aSKSHSTS+10h; "s\" -h %s -t %s"
0x180025b73  movaps  xmmword ptr [rbp+13D0h+var_1440], xmm1
0x180025b77  movups  xmm0, xmmword ptr cs:aSKSHSTS+1Eh; "s -t %s"
0x180025b7e  movups  xmmword ptr [rbp+13D0h+var_1440+0Eh], xmm0
0x180025b82  xor     edx, edx; Val
0x180025b84  mov     r8d, 9D0h; Size
0x180025b8a  lea     rcx, [rbp+13D0h+var_1422]; void *
0x180025b8e  call    memset_0
0x180025b93  xor     r14d, r14d
0x180025b96  mov     dword ptr [rbp+13D0h+var_A50], r14d
0x180025b9d  xor     edx, edx; Val
0x180025b9f  mov     r8d, 9FAh; Size
0x180025ba5  lea     rcx, [rbp+13D0h+var_A4C]; void *
0x180025bac  call    memset_0
0x180025bb1  lea     ecx, [r14+20h]; Size
0x180025bb5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025bba  mov     rsi, rax
0x180025bbd  lea     rax, ??_7SCEPTaskSchedulerImpl@@6B@; const SCEPTaskSchedulerImpl::`vftable'
0x180025bc4  mov     [rsi], rax
0x180025bc7  mov     [rsi+8], r14
0x180025bcb  mov     [rsi+10h], r14
0x180025bcf  mov     [rsi+18h], r14
0x180025bd3  mov     [rsp+14D0h+var_1478], rsi
0x180025bd8  lea     eax, [r14+1]
0x180025bdc  mov     [rsp+14D0h+var_1494], eax
0x180025be0  mov     [rsp+14D0h+var_1498], eax
0x180025be4  mov     [rsp+14D0h+hMem], r14
0x180025be9  xorps   xmm0, xmm0
0x180025bec  movups  xmmword ptr [rsp+14D0h+Src], xmm0
0x180025bf1  mov     [rsp+14D0h+var_1460], r14
0x180025bf6  mov     [rsp+14D0h+var_1458], 7
0x180025bff  mov     word ptr [rsp+14D0h+Src], r14w
0x180025c05  mov     dil, r14b
0x180025c08  mov     [rsp+14D0h+var_1490], r14b
0x180025c0d  mov     bl, r14b
0x180025c10  mov     [rsp+14D0h+var_148E], bl
0x180025c14  test    r15, r15
0x180025c17  jz      loc_180025CBD
0x180025c1d  mov     rcx, r15
0x180025c20  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x180025c26  mov     r14d, eax
0x180025c29  test    eax, eax
0x180025c2b  js      short loc_180025C3C
0x180025c2d  mov     dil, 1
0x180025c30  mov     [rsp+14D0h+var_1490], dil
0x180025c35  mov     bl, dil
0x180025c38  mov     [rsp+14D0h+var_148E], bl
0x180025c3c  test    r14d, r14d
0x180025c3f  jns     short loc_180025CBD
0x180025c41  mov     rcx, [rbp+13D8h]; this
0x180025c48  mov     r9d, r14d; char *
0x180025c4b  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180025c52  mov     edx, 0C43h; void *
0x180025c57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025c5c  nop
0x180025c5d  xor     eax, eax
0x180025c5f  test    dil, dil
0x180025c62  jz      short loc_180025C76
0x180025c64  test    bl, bl
0x180025c66  jz      short loc_180025C70
0x180025c68  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180025c6e  jmp     short loc_180025C76
0x180025c70  call    cs:__imp_CoRevertToSelf
0x180025c76  mov     rcx, [rbp+13D8h]; this
0x180025c7d  test    eax, eax
0x180025c7f  js      loc_180026182
0x180025c85  lea     rcx, [rsp+14D0h+Src]
0x180025c8a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025c8f  nop
0x180025c90  mov     rcx, [rsp+14D0h+hMem]; hMem
0x180025c95  test    rcx, rcx
0x180025c98  jz      short loc_180025CA1
0x180025c9a  call    cs:__imp_LocalFree
0x180025ca0  nop
0x180025ca1  mov     rax, [rsi]
0x180025ca4  mov     edx, 1
0x180025ca9  mov     rcx, rsi
0x180025cac  mov     rax, [rax+20h]
0x180025cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cb5  mov     eax, r14d
0x180025cb8  jmp     loc_180026156
0x180025cbd  lea     r9, [rsp+14D0h+var_1498]
0x180025cc2  lea     r8, aRetrydelay_0; "RetryDelay"
0x180025cc9  mov     rdx, r13
0x180025ccc  mov     rcx, [rsp+14D0h+var_1480]
0x180025cd1  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180025cd7  mov     r14d, eax
0x180025cda  cmp     eax, 80070002h
0x180025cdf  jnz     loc_180025D9D
0x180025ce5  mov     [rsp+14D0h+var_1498], 5
0x180025ced  lea     r9, [rsp+14D0h+var_1494]
0x180025cf2  lea     r8, aRetrycount_0; "RetryCount"
0x180025cf9  mov     rdx, r13
0x180025cfc  mov     rcx, [rsp+14D0h+var_1480]
0x180025d01  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180025d07  mov     r14d, eax
0x180025d0a  cmp     eax, 80070002h
0x180025d0f  jnz     loc_180025DEF
0x180025d15  mov     [rsp+14D0h+var_1494], 3
0x180025d1d  lea     rcx, aHklm; "HKLM"
0x180025d24  lea     rax, aHkcu; "HKCU"
0x180025d2b  test    r15, r15
0x180025d2e  cmovz   rax, rcx
0x180025d32  mov     [rsp+14D0h+var_14A8], r12
0x180025d37  mov     qword ptr [rsp+14D0h+var_14B0], rax; int
0x180025d3c  mov     r9, r13
0x180025d3f  lea     r8, [rbp+13D0h+var_1450]; unsigned __int16 *
0x180025d43  mov     edx, 4FFh; unsigned __int64
0x180025d48  lea     rcx, [rbp+13D0h+var_A50]; unsigned __int16 *
0x180025d4f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025d54  mov     r14d, eax
0x180025d57  xor     r13d, r13d
0x180025d5a  test    eax, eax
0x180025d5c  jns     loc_180025E5B
0x180025d62  mov     rcx, [rbp+13D8h]; this
0x180025d69  mov     r9d, eax; char *
0x180025d6c  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180025d73  mov     edx, 0C5Ah; void *
0x180025d78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025d7d  nop
0x180025d7e  mov     eax, r13d
0x180025d81  test    dil, dil
0x180025d84  jz      loc_180025E47
0x180025d8a  test    bl, bl
0x180025d8c  jz      loc_180025E41
0x180025d92  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180025d98  jmp     loc_180025E47
0x180025d9d  test    r14d, r14d
0x180025da0  jns     loc_180025CED
0x180025da6  mov     rcx, [rbp+13D8h]; this
0x180025dad  mov     r9d, r14d; char *
0x180025db0  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180025db7  mov     edx, 0C4Eh; void *
0x180025dbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025dc1  nop
0x180025dc2  xor     eax, eax
0x180025dc4  test    dil, dil
0x180025dc7  jz      short loc_180025DDB
0x180025dc9  test    bl, bl
0x180025dcb  jz      short loc_180025DD5
0x180025dcd  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180025dd3  jmp     short loc_180025DDB
0x180025dd5  call    cs:__imp_CoRevertToSelf
0x180025ddb  mov     rcx, [rbp+13D8h]; this
0x180025de2  test    eax, eax
0x180025de4  js      loc_18002618B
0x180025dea  jmp     loc_180025C85
0x180025def  test    r14d, r14d
0x180025df2  jns     loc_180025D1D
0x180025df8  mov     rcx, [rbp+13D8h]; this
0x180025dff  mov     r9d, r14d; char *
0x180025e02  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180025e09  mov     edx, 0C58h; void *
0x180025e0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025e13  nop
0x180025e14  xor     eax, eax
0x180025e16  test    dil, dil
0x180025e19  jz      short loc_180025E2D
0x180025e1b  test    bl, bl
0x180025e1d  jz      short loc_180025E27
0x180025e1f  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180025e25  jmp     short loc_180025E2D
0x180025e27  call    cs:__imp_CoRevertToSelf
0x180025e2d  mov     rcx, [rbp+13D8h]; this
0x180025e34  test    eax, eax
0x180025e36  js      loc_180026194
0x180025e3c  jmp     loc_180025C85
0x180025e41  call    cs:__imp_CoRevertToSelf
0x180025e47  mov     rcx, [rbp+13D8h]; this
0x180025e4e  test    eax, eax
0x180025e50  js      loc_18002619D
0x180025e56  jmp     loc_180025C85
0x180025e5b  mov     eax, r13d
0x180025e5e  test    dil, dil
0x180025e61  jz      short loc_180025E75
0x180025e63  test    bl, bl
0x180025e65  jz      short loc_180025E6F
0x180025e67  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180025e6d  jmp     short loc_180025E75
0x180025e6f  call    cs:__imp_CoRevertToSelf
0x180025e75  mov     rcx, [rbp+13D8h]; this
0x180025e7c  test    eax, eax
0x180025e7e  js      loc_1800261A6
0x180025e84  mov     rax, [rsi]
0x180025e87  lea     rdx, [rbp+13D0h+var_A50]
0x180025e8e  mov     rcx, rsi
0x180025e91  mov     rax, [rax]
0x180025e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e99  mov     ebx, eax
0x180025e9b  test    eax, eax
0x180025e9d  jns     short loc_180025EF2
0x180025e9f  mov     edx, 0C5Eh; void *
0x180025ea4  mov     r9d, ebx; char *
0x180025ea7  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180025eae  mov     rcx, [rbp+13D8h]; this
0x180025eb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025eba  nop
0x180025ebb  lea     rcx, [rsp+14D0h+Src]
0x180025ec0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025ec5  nop
0x180025ec6  mov     rcx, [rsp+14D0h+hMem]; hMem
0x180025ecb  test    rcx, rcx
0x180025ece  jz      short loc_180025ED7
0x180025ed0  call    cs:__imp_LocalFree
0x180025ed6  nop
0x180025ed7  mov     rax, [rsi]
0x180025eda  mov     edx, 1
0x180025edf  mov     rcx, rsi
0x180025ee2  mov     rax, [rax+20h]
0x180025ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025eeb  mov     eax, ebx
0x180025eed  jmp     loc_180026156
0x180025ef2  mov     r14b, r13b
0x180025ef5  mov     [rsp+14D0h+var_1490], r13b
0x180025efa  mov     dil, r13b
0x180025efd  mov     [rsp+14D0h+var_148E], r13b
0x180025f02  test    r15, r15
0x180025f05  jz      short loc_180025F75
0x180025f07  mov     rcx, r15
0x180025f0a  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x180025f10  mov     ebx, eax
0x180025f12  test    eax, eax
0x180025f14  js      short loc_180025F26
0x180025f16  mov     r14b, 1
0x180025f19  mov     [rsp+14D0h+var_1490], r14b
0x180025f1e  mov     dil, r14b
0x180025f21  mov     [rsp+14D0h+var_148E], r14b
0x180025f26  test    ebx, ebx
0x180025f28  jns     short loc_180025F75
0x180025f2a  mov     rcx, [rbp+13D8h]; this
0x180025f31  mov     r9d, ebx; char *
0x180025f34  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180025f3b  mov     edx, 0C69h; void *
0x180025f40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025f45  nop
0x180025f46  mov     eax, r13d
0x180025f49  test    r14b, r14b
0x180025f4c  jz      short loc_180025F61
0x180025f4e  test    dil, dil
0x180025f51  jz      short loc_180025F5B
0x180025f53  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180025f59  jmp     short loc_180025F61
0x180025f5b  call    cs:__imp_CoRevertToSelf
0x180025f61  mov     rcx, [rbp+13D8h]; this
0x180025f68  test    eax, eax
0x180025f6a  js      loc_1800261AF
0x180025f70  jmp     loc_180025EBB
0x180025f75  mov     r15, [rsp+14D0h+hMem]
0x180025f7a  test    r15, r15
0x180025f7d  jz      short loc_180025F98
0x180025f7f  call    cs:__imp_GetLastError
0x180025f85  mov     ebx, eax
0x180025f87  mov     rcx, r15; hMem
0x180025f8a  call    cs:__imp_LocalFree
0x180025f90  mov     ecx, ebx; dwErrCode
0x180025f92  call    cs:__imp_SetLastError
0x180025f98  mov     [rsp+14D0h+hMem], r13
0x180025f9d  lea     rcx, [rsp+14D0h+hMem]
0x180025fa2  call    cs:__imp_?DmGetCurrentUserSid@@YAJPEAPEAG@Z; DmGetCurrentUserSid(ushort * *)
0x180025fa8  mov     ebx, eax
0x180025faa  test    eax, eax
0x180025fac  jns     short loc_180025FF9
0x180025fae  mov     rcx, [rbp+13D8h]; this
0x180025fb5  mov     r9d, eax; char *
0x180025fb8  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180025fbf  mov     edx, 0C6Bh; void *
0x180025fc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025fc9  nop
0x180025fca  mov     eax, r13d
0x180025fcd  test    r14b, r14b
0x180025fd0  jz      short loc_180025FE5
0x180025fd2  test    dil, dil
0x180025fd5  jz      short loc_180025FDF
0x180025fd7  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180025fdd  jmp     short loc_180025FE5
0x180025fdf  call    cs:__imp_CoRevertToSelf
0x180025fe5  mov     rcx, [rbp+13D8h]; this
0x180025fec  test    eax, eax
0x180025fee  js      loc_1800261B8
  ... truncated ...
```
