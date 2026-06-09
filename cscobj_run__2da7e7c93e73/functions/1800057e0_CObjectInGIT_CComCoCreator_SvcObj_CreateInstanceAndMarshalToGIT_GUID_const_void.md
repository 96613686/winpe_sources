# CObjectInGIT<CComCoCreator_SvcObj>::CreateInstanceAndMarshalToGIT(_GUID const &,void * *)

- ea: `0x1800057e0`
- end: `0x180005b9f`
- name: `?CreateInstanceAndMarshalToGIT@?$CObjectInGIT@VCComCoCreator_SvcObj@@@@QEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `959`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009ac4`
- `0x180012380`
- `0x180012b48`
- `0x1800138b8`
- `0x180014a60`

## callees

- `0x1800057e0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x1800058d9`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x18000599c`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x1800058d9`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x18000599c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005a9b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005a9b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180005871`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180005871`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180005921`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800059df`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180005b32`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180005b7d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180005921`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800059df`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180005b32`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180005b7d`

## pseudocode

```c
__int64 __fastcall CObjectInGIT<CComCoCreator_SvcObj>::CreateInstanceAndMarshalToGIT(__int64 a1, void *a2, __int64 *a3)
{
  DWORD v4; // r8d
  const IID *v6; // rcx
  HRESULT v7; // ebx
  __int64 result; // rax
  IUnknown *pItf; // rdi
  HRESULT v10; // eax
  unsigned int v11; // esi
  struct IUnknownVtbl *lpVtbl; // rax
  IUnknown *v13; // r14
  HRESULT v14; // eax
  __int64 v15; // r14
  _QWORD *v16; // rcx
  __int64 v17; // rax
  DWORD pAuthnLevel; // [rsp+40h] [rbp-59h] BYREF
  IUnknown *pProxy; // [rsp+48h] [rbp-51h] BYREF
  MULTI_QI pResults; // [rsp+50h] [rbp-49h] BYREF
  _QWORD v21[2]; // [rsp+68h] [rbp-31h] BYREF
  int v22; // [rsp+78h] [rbp-21h]
  int v23; // [rsp+7Ch] [rbp-1Dh]
  __int64 v24; // [rsp+80h] [rbp-19h]
  __int64 v25; // [rsp+88h] [rbp-11h]
  COSERVERINFO pServerInfo; // [rsp+90h] [rbp-9h] BYREF
  DWORD pAuthzSvc; // [rsp+100h] [rbp+67h] BYREF
  LPVOID dwCapabilities; // [rsp+108h] [rbp+6Fh] BYREF
  DWORD pwAuthnSvc; // [rsp+110h] [rbp+77h] BYREF
  DWORD pImpLevel; // [rsp+118h] [rbp+7Fh] BYREF

  dwCapabilities = a2;
  v21[0] = -1;
  *a3 = 0;
  pServerInfo.pAuthInfo = (COAUTHINFO *)v21;
  v21[1] = 0;
  pResults.pIID = &GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce;
  v4 = *(_DWORD *)(a1 + 32);
  v6 = *(const IID **)(a1 + 24);
  v22 = 6;
  v23 = 3;
  v24 = 0;
  v25 = 0;
  *(_QWORD *)&pServerInfo.dwReserved1 = 0;
  pServerInfo.pwszName = 0;
  *(_QWORD *)&pServerInfo.dwReserved2 = 0;
  pResults.pItf = 0;
  *(_QWORD *)&pResults.hr = 0;
  v7 = CoCreateInstanceEx(v6, 0, v4, &pServerInfo, 1u, &pResults);
  if ( v7 < 0 )
    return (unsigned int)v7;
  pItf = pResults.pItf;
  pwAuthnSvc = 0;
  pAuthzSvc = 0;
  pAuthnLevel = 0;
  pImpLevel = 0;
  LODWORD(dwCapabilities) = 0;
  v10 = CoQueryProxyBlanket(
          pResults.pItf,
          &pwAuthnSvc,
          &pAuthzSvc,
          0,
          &pAuthnLevel,
          &pImpLevel,
          0,
          (DWORD *)&dwCapabilities);
  v11 = -2147467262;
  v7 = v10;
  if ( v10 != -2147467262 )
  {
    if ( v10 < 0 )
      goto LABEL_25;
    if ( CoSetProxyBlanket(pItf, pwAuthnSvc, pAuthzSvc, 0, 6u, 3u, 0, (unsigned int)dwCapabilities & 0xFFFFFF9F | 0x40) < 0 )
    {
      v7 = CoSetProxyBlanket(pItf, pwAuthnSvc, pAuthzSvc, 0, pAuthnLevel, pImpLevel, 0, (DWORD)dwCapabilities);
      if ( v7 < 0 )
        goto LABEL_25;
    }
  }
  lpVtbl = pItf->lpVtbl;
  pProxy = 0;
  v7 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))lpVtbl->QueryInterface)(pItf, &IID_IUnknown, &pProxy);
  if ( v7 < 0 )
    goto LABEL_25;
  v13 = pProxy;
  pwAuthnSvc = 0;
  pAuthzSvc = 0;
  pAuthnLevel = 0;
  pImpLevel = 0;
  LODWORD(dwCapabilities) = 0;
  v14 = CoQueryProxyBlanket(pProxy, &pwAuthnSvc, &pAuthzSvc, 0, &pAuthnLevel, &pImpLevel, 0, (DWORD *)&dwCapabilities);
  v7 = v14;
  if ( v14 == -2147467262 )
  {
    v7 = 0;
  }
  else if ( v14 >= 0 )
  {
    v7 = CoSetProxyBlanket(v13, pwAuthnSvc, pAuthzSvc, 0, 6u, 3u, 0, (unsigned int)dwCapabilities & 0xFFFFFF9F | 0x40);
    if ( v7 < 0 )
      v7 = CoSetProxyBlanket(v13, pwAuthnSvc, pAuthzSvc, 0, pAuthnLevel, pImpLevel, 0, (DWORD)dwCapabilities);
  }
  ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  if ( v7 < 0 )
  {
LABEL_25:
    ((void (__fastcall *)(IUnknown *))pItf->lpVtbl->Release)(pItf);
    return (unsigned int)v7;
  }
  v7 = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))pItf->lpVtbl->QueryInterface)(
         pItf,
         &GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce,
         a3);
  ((void (__fastcall *)(IUnknown *))pItf->lpVtbl->Release)(pItf);
  if ( v7 < 0 )
    return (unsigned int)v7;
  v15 = *a3;
  v7 = -2147024809;
  if ( *a3 )
  {
    v16 = *(_QWORD **)(a1 + 8);
    v17 = *(_QWORD *)&GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1 - *v16;
    if ( *(_QWORD *)&GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1 == *v16 )
      v17 = *(_QWORD *)GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data4 - v16[1];
    if ( v17 )
      goto LABEL_22;
    if ( *(_DWORD *)(a1 + 16) )
    {
      v11 = -2147467259;
      goto LABEL_22;
    }
    *(_DWORD *)(a1 + 16) = 0;
    dwCapabilities = 0;
    v7 = CoCreateInstance(
           &CLSID_StdGlobalInterfaceTable,
           0,
           1u,
           &GUID_00000146_0000_0000_c000_000000000046,
           &dwCapabilities);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, GUID *, __int64))(*(_QWORD *)dwCapabilities + 24LL))(
             dwCapabilities,
             v15,
             &GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce,
             a1 + 16);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)dwCapabilities + 16LL))(dwCapabilities);
    }
    if ( v7 < 0 )
    {
      *(_DWORD *)(a1 + 16) = 0;
      v11 = v7;
      goto LABEL_22;
    }
  }
  v11 = v7;
  if ( v7 >= 0 )
    return (unsigned int)v7;
LABEL_22:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  result = v11;
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x1800057e0  mov     [rsp-8+dwCapabilities], rdx
0x1800057e5  push    rbp
0x1800057e6  push    rbx
0x1800057e7  push    rsi
0x1800057e8  push    rdi
0x1800057e9  push    r12
0x1800057eb  push    r13
0x1800057ed  push    r14
0x1800057ef  push    r15
0x1800057f1  lea     rbp, [rsp-1Fh]
0x1800057f6  sub     rsp, 0B8h
0x1800057fd  xor     r13d, r13d
0x180005800  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFFh
0x180005808  mov     [r8], r13
0x18000580b  lea     rax, [rbp+57h+var_88]
0x18000580f  mov     [rbp+57h+pServerInfo.pAuthInfo], rax
0x180005813  lea     r9, [rbp+57h+pServerInfo]; pServerInfo
0x180005817  lea     rax, _GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce
0x18000581e  mov     [rbp+57h+var_80], r13
0x180005822  mov     [rbp+57h+var_A0.pIID], rax
0x180005826  mov     r12, r8
0x180005829  mov     r8d, [rcx+20h]; dwClsCtx
0x18000582d  lea     rax, [rbp+57h+var_A0]
0x180005831  mov     r15, rcx
0x180005834  mov     [rsp+0F0h+pResults], rax; pResults
0x180005839  mov     rcx, [rcx+18h]; Clsid
0x18000583d  xor     edx, edx; punkOuter
0x18000583f  mov     [rsp+0F0h+dwCount], 1; dwCount
0x180005847  mov     [rbp+57h+var_78], 6
0x18000584e  mov     [rbp+57h+var_74], 3
0x180005855  mov     [rbp+57h+var_70], r13
0x180005859  mov     [rbp+57h+var_68], r13
0x18000585d  mov     qword ptr [rbp+57h+pServerInfo.dwReserved1], r13
0x180005861  mov     [rbp+57h+pServerInfo.pwszName], r13
0x180005865  mov     qword ptr [rbp+57h+pServerInfo.dwReserved2], r13
0x180005869  mov     [rbp+57h+var_A0.pItf], r13
0x18000586d  mov     qword ptr [rbp+57h+var_A0.hr], r13
0x180005871  call    cs:__imp_CoCreateInstanceEx
0x180005877  mov     ebx, eax
0x180005879  test    eax, eax
0x18000587b  jns     short loc_180005893
0x18000587d  mov     eax, ebx
0x18000587f  add     rsp, 0B8h
0x180005886  pop     r15
0x180005888  pop     r14
0x18000588a  pop     r13
0x18000588c  pop     r12
0x18000588e  pop     rdi
0x18000588f  pop     rsi
0x180005890  pop     rbx
0x180005891  pop     rbp
0x180005892  retn
0x180005893  mov     rdi, [rbp+57h+var_A0.pItf]
0x180005897  lea     rax, [rbp+57h+dwCapabilities]
0x18000589b  mov     [rsp+0F0h+pCapabilites], rax; pCapabilites
0x1800058a0  lea     r8, [rbp+57h+pAuthzSvc]; pAuthzSvc
0x1800058a4  lea     rax, [rbp+57h+pImpLevel]
0x1800058a8  mov     [rsp+0F0h+pAuthInfo], r13; pAuthInfo
0x1800058ad  mov     [rsp+0F0h+pResults], rax; pImpLevel
0x1800058b2  lea     rdx, [rbp+57h+pwAuthnSvc]; pwAuthnSvc
0x1800058b6  lea     rax, [rbp+57h+pAuthnLevel]
0x1800058ba  mov     [rbp+57h+pwAuthnSvc], r13d
0x1800058be  xor     r9d, r9d; pServerPrincName
0x1800058c1  mov     qword ptr [rsp+0F0h+dwCount], rax; pAuthnLevel
0x1800058c6  mov     rcx, rdi; pProxy
0x1800058c9  mov     [rbp+57h+pAuthzSvc], r13d
0x1800058cd  mov     [rbp+57h+pAuthnLevel], r13d
0x1800058d1  mov     [rbp+57h+pImpLevel], r13d
0x1800058d5  mov     dword ptr [rbp+57h+dwCapabilities], r13d
0x1800058d9  call    cs:__imp_CoQueryProxyBlanket
0x1800058df  mov     esi, 80004002h
0x1800058e4  mov     ebx, eax
0x1800058e6  cmp     eax, esi
0x1800058e8  jz      short loc_18000592F
0x1800058ea  test    eax, eax
0x1800058ec  js      loc_180005B42
0x1800058f2  mov     eax, dword ptr [rbp+57h+dwCapabilities]
0x1800058f5  xor     r9d, r9d; pServerPrincName
0x1800058f8  mov     r8d, [rbp+57h+pAuthzSvc]; dwAuthzSvc
0x1800058fc  and     eax, 0FFFFFFDFh
0x1800058ff  mov     edx, [rbp+57h+pwAuthnSvc]; dwAuthnSvc
0x180005902  or      eax, 40h
0x180005905  mov     dword ptr [rsp+0F0h+pCapabilites], eax; dwCapabilities
0x180005909  mov     rcx, rdi; pProxy
0x18000590c  mov     [rsp+0F0h+pAuthInfo], r13; pAuthInfo
0x180005911  mov     dword ptr [rsp+0F0h+pResults], 3; dwImpLevel
0x180005919  mov     [rsp+0F0h+dwCount], 6; dwAuthnLevel
0x180005921  call    cs:__imp_CoSetProxyBlanket
0x180005927  test    eax, eax
0x180005929  js      loc_180005B0B
0x18000592f  mov     rax, [rdi]
0x180005932  lea     r8, [rbp+57h+pProxy]
0x180005936  lea     rdx, IID_IUnknown
0x18000593d  mov     [rbp+57h+pProxy], r13
0x180005941  mov     rcx, rdi
0x180005944  mov     rax, [rax]
0x180005947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000594c  mov     ebx, eax
0x18000594e  test    eax, eax
0x180005950  js      loc_180005B42
0x180005956  mov     r14, [rbp+57h+pProxy]
0x18000595a  lea     rax, [rbp+57h+dwCapabilities]
0x18000595e  mov     [rsp+0F0h+pCapabilites], rax; pCapabilites
0x180005963  lea     r8, [rbp+57h+pAuthzSvc]; pAuthzSvc
0x180005967  lea     rax, [rbp+57h+pImpLevel]
0x18000596b  mov     [rsp+0F0h+pAuthInfo], r13; pAuthInfo
0x180005970  mov     [rsp+0F0h+pResults], rax; pImpLevel
0x180005975  lea     rdx, [rbp+57h+pwAuthnSvc]; pwAuthnSvc
0x180005979  lea     rax, [rbp+57h+pAuthnLevel]
0x18000597d  mov     [rbp+57h+pwAuthnSvc], r13d
0x180005981  xor     r9d, r9d; pServerPrincName
0x180005984  mov     qword ptr [rsp+0F0h+dwCount], rax; pAuthnLevel
0x180005989  mov     rcx, r14; pProxy
0x18000598c  mov     [rbp+57h+pAuthzSvc], r13d
0x180005990  mov     [rbp+57h+pAuthnLevel], r13d
0x180005994  mov     [rbp+57h+pImpLevel], r13d
0x180005998  mov     dword ptr [rbp+57h+dwCapabilities], r13d
0x18000599c  call    cs:__imp_CoQueryProxyBlanket
0x1800059a2  mov     ebx, eax
0x1800059a4  cmp     eax, esi
0x1800059a6  jz      loc_180005B03
0x1800059ac  test    eax, eax
0x1800059ae  js      short loc_1800059EF
0x1800059b0  mov     eax, dword ptr [rbp+57h+dwCapabilities]
0x1800059b3  xor     r9d, r9d; pServerPrincName
0x1800059b6  mov     r8d, [rbp+57h+pAuthzSvc]; dwAuthzSvc
0x1800059ba  and     eax, 0FFFFFFDFh
0x1800059bd  mov     edx, [rbp+57h+pwAuthnSvc]; dwAuthnSvc
0x1800059c0  or      eax, 40h
0x1800059c3  mov     dword ptr [rsp+0F0h+pCapabilites], eax; dwCapabilities
0x1800059c7  mov     rcx, r14; pProxy
0x1800059ca  mov     [rsp+0F0h+pAuthInfo], r13; pAuthInfo
0x1800059cf  mov     dword ptr [rsp+0F0h+pResults], 3; dwImpLevel
0x1800059d7  mov     [rsp+0F0h+dwCount], 6; dwAuthnLevel
0x1800059df  call    cs:__imp_CoSetProxyBlanket
0x1800059e5  mov     ebx, eax
0x1800059e7  test    eax, eax
0x1800059e9  js      loc_180005B56
0x1800059ef  mov     rcx, [rbp+57h+pProxy]
0x1800059f3  mov     rax, [rcx]
0x1800059f6  mov     rax, [rax+10h]
0x1800059fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059ff  test    ebx, ebx
0x180005a01  js      loc_180005B42
0x180005a07  mov     rax, [rdi]
0x180005a0a  lea     rdx, _GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce
0x180005a11  mov     r8, r12
0x180005a14  mov     rcx, rdi
0x180005a17  mov     rax, [rax]
0x180005a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a1f  mov     ebx, eax
0x180005a21  mov     rcx, rdi
0x180005a24  mov     rax, [rdi]
0x180005a27  mov     rax, [rax+10h]
0x180005a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a30  test    ebx, ebx
0x180005a32  js      loc_18000587D
0x180005a38  mov     r14, [r12]
0x180005a3c  mov     ebx, 80070057h
0x180005a41  test    r14, r14
0x180005a44  jz      loc_180005ADF
0x180005a4a  mov     rcx, [r15+8]
0x180005a4e  mov     rax, qword ptr cs:_GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1
0x180005a55  sub     rax, [rcx]
0x180005a58  jnz     short loc_180005A65
0x180005a5a  mov     rax, qword ptr cs:_GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data4
0x180005a61  sub     rax, [rcx+8]
0x180005a65  test    rax, rax
0x180005a68  jnz     short loc_180005AE9
0x180005a6a  cmp     [r15+10h], r13d
0x180005a6e  jnz     loc_180005B8A
0x180005a74  lea     rax, [rbp+57h+dwCapabilities]
0x180005a78  mov     [r15+10h], r13d
0x180005a7c  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180005a83  mov     qword ptr [rsp+0F0h+dwCount], rax; ppv
0x180005a88  xor     edx, edx; pUnkOuter
0x180005a8a  mov     [rbp+57h+dwCapabilities], r13
0x180005a8e  mov     r8d, 1; dwClsContext
0x180005a94  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180005a9b  call    cs:__imp_CoCreateInstance
0x180005aa1  mov     ebx, eax
0x180005aa3  test    eax, eax
0x180005aa5  js      short loc_180005AD7
0x180005aa7  mov     rcx, [rbp+57h+dwCapabilities]
0x180005aab  lea     r9, [r15+10h]
0x180005aaf  lea     r8, _GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce
0x180005ab6  mov     rdx, r14
0x180005ab9  mov     rax, [rcx]
0x180005abc  mov     rax, [rax+18h]
0x180005ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ac5  mov     rcx, [rbp+57h+dwCapabilities]
0x180005ac9  mov     ebx, eax
0x180005acb  mov     rax, [rcx]
0x180005ace  mov     rax, [rax+10h]
0x180005ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad7  test    ebx, ebx
0x180005ad9  js      loc_180005B94
0x180005adf  mov     esi, ebx
0x180005ae1  test    ebx, ebx
0x180005ae3  jns     loc_18000587D
0x180005ae9  mov     rdx, [r14]
0x180005aec  mov     rcx, r14
0x180005aef  mov     rax, [rdx+10h]
0x180005af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005af8  mov     eax, esi
0x180005afa  mov     [r12], r13
0x180005afe  jmp     loc_18000587F
0x180005b03  mov     ebx, r13d
0x180005b06  jmp     loc_1800059EF
0x180005b0b  mov     eax, dword ptr [rbp+57h+dwCapabilities]
0x180005b0e  xor     r9d, r9d; pServerPrincName
0x180005b11  mov     r8d, [rbp+57h+pAuthzSvc]; dwAuthzSvc
0x180005b15  mov     rcx, rdi; pProxy
0x180005b18  mov     edx, [rbp+57h+pwAuthnSvc]; dwAuthnSvc
0x180005b1b  mov     dword ptr [rsp+0F0h+pCapabilites], eax; dwCapabilities
0x180005b1f  mov     eax, [rbp+57h+pImpLevel]
0x180005b22  mov     [rsp+0F0h+pAuthInfo], r13; pAuthInfo
0x180005b27  mov     dword ptr [rsp+0F0h+pResults], eax; dwImpLevel
0x180005b2b  mov     eax, [rbp+57h+pAuthnLevel]
0x180005b2e  mov     [rsp+0F0h+dwCount], eax; dwAuthnLevel
0x180005b32  call    cs:__imp_CoSetProxyBlanket
0x180005b38  mov     ebx, eax
0x180005b3a  test    eax, eax
0x180005b3c  jns     loc_18000592F
0x180005b42  mov     rax, [rdi]
0x180005b45  mov     rcx, rdi
0x180005b48  mov     rax, [rax+10h]
0x180005b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b51  jmp     loc_18000587D
0x180005b56  mov     eax, dword ptr [rbp+57h+dwCapabilities]
0x180005b59  xor     r9d, r9d; pServerPrincName
0x180005b5c  mov     r8d, [rbp+57h+pAuthzSvc]; dwAuthzSvc
0x180005b60  mov     rcx, r14; pProxy
0x180005b63  mov     edx, [rbp+57h+pwAuthnSvc]; dwAuthnSvc
0x180005b66  mov     dword ptr [rsp+0F0h+pCapabilites], eax; dwCapabilities
0x180005b6a  mov     eax, [rbp+57h+pImpLevel]
0x180005b6d  mov     [rsp+0F0h+pAuthInfo], r13; pAuthInfo
0x180005b72  mov     dword ptr [rsp+0F0h+pResults], eax; dwImpLevel
0x180005b76  mov     eax, [rbp+57h+pAuthnLevel]
0x180005b79  mov     [rsp+0F0h+dwCount], eax; dwAuthnLevel
0x180005b7d  call    cs:__imp_CoSetProxyBlanket
0x180005b83  mov     ebx, eax
0x180005b85  jmp     loc_1800059EF
0x180005b8a  mov     esi, 80004005h
0x180005b8f  jmp     loc_180005AE9
0x180005b94  mov     [r15+10h], r13d
0x180005b98  mov     esi, ebx
0x180005b9a  jmp     loc_180005AE9
```
