# ClusNode::SetClusterServiceRegistries(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800474fc`
- end: `0x180047930`
- name: `?SetClusterServiceRegistries@ClusNode@@QEAAXAEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@1111@Z`
- size: `1076`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x1800791d0`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18001e5f0`
- `0x180028f30`
- `0x18003180c`
- `0x180046444`
- `0x1800474fc`
- `0x1800a2bb8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004764c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800476e0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004775a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800477d4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047850`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800478ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004764c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800476e0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004775a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800477d4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047850`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800478ca`

## string_xrefs

- `0x18004766f`: `Failed to set %ws value in registry on node %ws`
- `0x180047701`: `Failed to set %ws value in registry on node %ws`
- `0x18004777b`: `Failed to set %ws value in registry on node %ws`
- `0x1800477f5`: `Failed to set %ws value in registry on node %ws`
- `0x180047871`: `Failed to set %ws value in registry on node %ws`
- `0x1800478eb`: `Failed to set %ws value in registry on node %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall ClusNode::SetClusterServiceRegistries(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v7; // r15
  __int64 v8; // rdi
  __int64 v11; // r14
  __int64 v12; // rax
  const BYTE *lpData; // rax
  unsigned __int64 i; // rdi
  __int64 v15; // rdx
  __int64 v16; // rax
  int v17; // r15d
  __int64 v18; // rax
  LSTATUS v19; // edi
  __int64 v20; // rax
  const BYTE *v21; // rax
  int v22; // edi
  __int64 v23; // rax
  const BYTE *v24; // rax
  int v25; // edi
  __int64 v26; // rax
  const BYTE *v27; // rax
  int v28; // edi
  __int64 v29; // rax
  const BYTE *v30; // rax
  int v31; // edi
  __int64 v32; // rax
  const BYTE *v33; // rax
  int v34; // edi
  __int64 v35; // rax
  int v37; // [rsp+30h] [rbp-D0h] BYREF
  const BYTE *v38; // [rsp+38h] [rbp-C8h] BYREF
  const BYTE *v39; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+48h] [rbp-B8h]
  __int64 v41; // [rsp+50h] [rbp-B0h]
  __int64 v42; // [rsp+58h] [rbp-A8h]
  _BYTE pExceptionObject[272]; // [rsp+60h] [rbp-A0h] BYREF

  v7 = a4;
  v41 = a4;
  v8 = a3;
  v42 = a3;
  v11 = a5;
  v40 = a5;
  v12 = a2[1];
  if ( *a2 != v12 )
  {
    v37 = 0;
    lpData = 0;
    v39 = 0;
    for ( i = 0; ; ++i )
    {
      v15 = *a2;
      if ( i >= (a2[1] - *a2) >> 5 )
        break;
      v38 = lpData;
      v16 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(32 * i + v15);
      v17 = ClRtlMultiSzAppend(&v38, &v37, v16);
      if ( v17 )
      {
        v18 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(32 * i + *a2);
        ClusRtl::ExceptionMsg::ExceptionMsg(
          (ClusRtl::ExceptionMsg *)pExceptionObject,
          v17,
          L"Failed to add ip %ws to ip addresses ",
          v18);
        throw (ClusRtl::ExceptionMsg *)pExceptionObject;
      }
      v39 = 0;
      std::unique_ptr<wchar_t,LocalHeapFreer<wchar_t>>::operator=<LocalHeapFreer<wchar_t>,0>(&v39, &v38);
      std::unique_ptr<wchar_t,MIDLDeleter>::~unique_ptr<wchar_t,MIDLDeleter>(&v38);
      lpData = v39;
    }
    v19 = RegSetValueExW(*(HKEY *)(a1 + 232), L"IPAdresses", 0, 7u, lpData, 2 * v37);
    if ( v19 )
    {
      v20 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 48);
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)pExceptionObject,
        v19,
        L"Failed to set %ws value in registry on node %ws",
        L"IPAdresses",
        v20);
      throw (ClusRtl::ExceptionMsg *)pExceptionObject;
    }
    LODWORD(v12) = std::unique_ptr<wchar_t,MIDLDeleter>::~unique_ptr<wchar_t,MIDLDeleter>(&v39);
    v11 = v40;
    v7 = v41;
    v8 = v42;
  }
  if ( *(_QWORD *)(v8 + 16) )
  {
    v21 = (const BYTE *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v8);
    LODWORD(v12) = RegSetValueExW(*(HKEY *)(a1 + 232), L"NetNamePwd", 0, 1u, v21, 2 * *(_DWORD *)(v8 + 16));
    v22 = v12;
    if ( (_DWORD)v12 )
    {
      v23 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 48);
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)pExceptionObject,
        v22,
        L"Failed to set %ws value in registry on node %ws",
        L"NetNamePwd",
        v23);
      throw (ClusRtl::ExceptionMsg *)pExceptionObject;
    }
  }
  if ( *(_QWORD *)(v7 + 16) )
  {
    v24 = (const BYTE *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7);
    LODWORD(v12) = RegSetValueExW(*(HKEY *)(a1 + 232), L"DCName", 0, 1u, v24, 2 * *(_DWORD *)(v7 + 16));
    v25 = v12;
    if ( (_DWORD)v12 )
    {
      v26 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 48);
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)pExceptionObject,
        v25,
        L"Failed to set %ws value in registry on node %ws",
        L"DCName",
        v26);
      throw (ClusRtl::ExceptionMsg *)pExceptionObject;
    }
  }
  if ( *(_QWORD *)(v11 + 16) )
  {
    v27 = (const BYTE *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v11);
    LODWORD(v12) = RegSetValueExW(*(HKEY *)(a1 + 232), L"ClusterCNOGuid", 0, 1u, v27, 2 * *(_DWORD *)(v11 + 16));
    v28 = v12;
    if ( (_DWORD)v12 )
    {
      v29 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 48);
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)pExceptionObject,
        v28,
        L"Failed to set %ws value in registry on node %ws",
        L"ClusterCNOGuid",
        v29);
      throw (ClusRtl::ExceptionMsg *)pExceptionObject;
    }
  }
  if ( *(_QWORD *)(a6 + 16) )
  {
    v30 = (const BYTE *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a6);
    LODWORD(v12) = RegSetValueExW(*(HKEY *)(a1 + 232), L"OS", 0, 1u, v30, 2 * *(_DWORD *)(a6 + 16));
    v31 = v12;
    if ( (_DWORD)v12 )
    {
      v32 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 48);
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)pExceptionObject,
        v31,
        L"Failed to set %ws value in registry on node %ws",
        L"OS",
        v32);
      throw (ClusRtl::ExceptionMsg *)pExceptionObject;
    }
  }
  if ( *(_QWORD *)(a7 + 16) )
  {
    v33 = (const BYTE *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a7);
    LODWORD(v12) = RegSetValueExW(*(HKEY *)(a1 + 232), L"OSVersion", 0, 1u, v33, 2 * *(_DWORD *)(a7 + 16));
    v34 = v12;
    if ( (_DWORD)v12 )
    {
      v35 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 48);
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)pExceptionObject,
        v34,
        L"Failed to set %ws value in registry on node %ws",
        L"OSVersion",
        v35);
      throw (ClusRtl::ExceptionMsg *)pExceptionObject;
    }
  }
  return v12;
}

```

## disassembly

```asm
0x1800474fc  push    rbp
0x1800474fe  push    rbx
0x1800474ff  push    rsi
0x180047500  push    rdi
0x180047501  push    r12
0x180047503  push    r13
0x180047505  push    r14
0x180047507  push    r15
0x180047509  lea     rbp, [rsp-88h]
0x180047511  sub     rsp, 188h
0x180047518  mov     rax, cs:__security_cookie
0x18004751f  xor     rax, rsp
0x180047522  mov     [rbp+0C0h+var_50], rax
0x180047526  mov     r15, r9
0x180047529  mov     [rsp+1C0h+var_170], r9
0x18004752e  mov     rdi, r8
0x180047531  mov     [rsp+1C0h+var_168], r8
0x180047536  mov     rsi, rdx
0x180047539  mov     rbx, rcx
0x18004753c  mov     r13, [rbp+0C0h+arg_30]
0x180047543  mov     r12, [rbp+0C0h+arg_28]
0x18004754a  mov     r14, [rbp+0C0h+arg_20]
0x180047551  mov     [rsp+1C0h+var_178], r14
0x180047556  mov     rax, [rdx+8]
0x18004755a  cmp     [rdx], rax
0x18004755d  jnz     short loc_180047566
0x18004755f  xor     esi, esi
0x180047561  jmp     loc_1800476AD
0x180047566  mov     [rsp+1C0h+var_190], 0
0x18004756e  xor     eax, eax
0x180047570  mov     [rsp+1C0h+var_180], rax
0x180047575  xor     edi, edi
0x180047577  mov     rdx, [rsi]
0x18004757a  mov     rcx, [rsi+8]
0x18004757e  sub     rcx, rdx
0x180047581  sar     rcx, 5
0x180047585  cmp     rdi, rcx
0x180047588  jnb     loc_180047626
0x18004758e  mov     [rsp+1C0h+var_188], rax
0x180047593  mov     r14, rdi
0x180047596  shl     r14, 5
0x18004759a  lea     rcx, [r14+rdx]
0x18004759e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800475a3  mov     r8, rax
0x1800475a6  lea     rdx, [rsp+1C0h+var_190]
0x1800475ab  lea     rcx, [rsp+1C0h+var_188]
0x1800475b0  call    ClRtlMultiSzAppend
0x1800475b5  mov     r15d, eax
0x1800475b8  test    eax, eax
0x1800475ba  jnz     short loc_1800475F2
0x1800475bc  mov     [rsp+1C0h+var_180], 0
0x1800475c5  mov     rax, [rsp+1C0h+var_188]
0x1800475ca  mov     [rsp+1C0h+var_188], rax
0x1800475cf  lea     rdx, [rsp+1C0h+var_188]
0x1800475d4  lea     rcx, [rsp+1C0h+var_180]
0x1800475d9  call    ??$?4U?$LocalHeapFreer@_W@@$0A@@?$unique_ptr@_WU?$LocalHeapFreer@_W@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<wchar_t,LocalHeapFreer<wchar_t>>::operator=<LocalHeapFreer<wchar_t>,0>(std::unique_ptr<wchar_t,LocalHeapFreer<wchar_t>> &&)
0x1800475de  lea     rcx, [rsp+1C0h+var_188]
0x1800475e3  call    ??1?$unique_ptr@_WUMIDLDeleter@@@std@@QEAA@XZ; std::unique_ptr<wchar_t,MIDLDeleter>::~unique_ptr<wchar_t,MIDLDeleter>(void)
0x1800475e8  inc     rdi
0x1800475eb  mov     rax, [rsp+1C0h+var_180]
0x1800475f0  jmp     short loc_180047577
0x1800475f2  mov     rcx, [rsi]
0x1800475f5  add     rcx, r14
0x1800475f8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800475fd  mov     r9, rax
0x180047600  lea     r8, aFailedToAddIpW; "Failed to add ip %ws to ip addresses "
0x180047607  mov     edx, r15d; int
0x18004760a  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x18004760f  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180047614  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18004761b  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x180047620  call    _CxxThrowException_0
0x180047626  mov     ecx, [rsp+1C0h+var_190]
0x18004762a  add     ecx, ecx
0x18004762c  mov     [rsp+1C0h+cbData], ecx; cbData
0x180047630  mov     [rsp+1C0h+lpData], rax; lpData
0x180047635  mov     r9d, 7; dwType
0x18004763b  xor     r8d, r8d; Reserved
0x18004763e  lea     rdx, aIpadresses; "IPAdresses"
0x180047645  mov     rcx, [rbx+0E8h]; hKey
0x18004764c  call    cs:__imp_RegSetValueExW
0x180047652  mov     edi, eax
0x180047654  xor     esi, esi
0x180047656  test    eax, eax
0x180047658  jz      short loc_180047694
0x18004765a  lea     rcx, [rbx+30h]
0x18004765e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180047663  mov     [rsp+1C0h+lpData], rax
0x180047668  lea     r9, aIpadresses; "IPAdresses"
0x18004766f  lea     r8, aFailedToSetWsV; "Failed to set %ws value in registry on "...
0x180047676  mov     edx, edi; int
0x180047678  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x18004767d  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180047682  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180047689  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x18004768e  call    _CxxThrowException_0
0x180047694  lea     rcx, [rsp+1C0h+var_180]
0x180047699  call    ??1?$unique_ptr@_WUMIDLDeleter@@@std@@QEAA@XZ; std::unique_ptr<wchar_t,MIDLDeleter>::~unique_ptr<wchar_t,MIDLDeleter>(void)
0x18004769e  mov     r14, [rsp+1C0h+var_178]
0x1800476a3  mov     r15, [rsp+1C0h+var_170]
0x1800476a8  mov     rdi, [rsp+1C0h+var_168]
0x1800476ad  cmp     [rdi+10h], rsi
0x1800476b1  jz      short loc_180047726
0x1800476b3  mov     rcx, rdi
0x1800476b6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800476bb  mov     ecx, [rdi+10h]
0x1800476be  add     ecx, ecx
0x1800476c0  mov     [rsp+1C0h+cbData], ecx; cbData
0x1800476c4  mov     [rsp+1C0h+lpData], rax; lpData
0x1800476c9  mov     r9d, 1; dwType
0x1800476cf  xor     r8d, r8d; Reserved
0x1800476d2  lea     rdx, aNetnamepwd; "NetNamePwd"
0x1800476d9  mov     rcx, [rbx+0E8h]; hKey
0x1800476e0  call    cs:__imp_RegSetValueExW
0x1800476e6  mov     edi, eax
0x1800476e8  test    eax, eax
0x1800476ea  jz      short loc_180047726
0x1800476ec  lea     rcx, [rbx+30h]
0x1800476f0  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800476f5  mov     [rsp+1C0h+lpData], rax
0x1800476fa  lea     r9, aNetnamepwd; "NetNamePwd"
0x180047701  lea     r8, aFailedToSetWsV; "Failed to set %ws value in registry on "...
0x180047708  mov     edx, edi; int
0x18004770a  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x18004770f  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180047714  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18004771b  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x180047720  call    _CxxThrowException_0
0x180047726  cmp     [r15+10h], rsi
0x18004772a  jz      short loc_1800477A0
0x18004772c  mov     rcx, r15
0x18004772f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180047734  mov     ecx, [r15+10h]
0x180047738  add     ecx, ecx
0x18004773a  mov     [rsp+1C0h+cbData], ecx; cbData
0x18004773e  mov     [rsp+1C0h+lpData], rax; lpData
0x180047743  mov     r9d, 1; dwType
0x180047749  xor     r8d, r8d; Reserved
0x18004774c  lea     rdx, aDcname; "DCName"
0x180047753  mov     rcx, [rbx+0E8h]; hKey
0x18004775a  call    cs:__imp_RegSetValueExW
0x180047760  mov     edi, eax
0x180047762  test    eax, eax
0x180047764  jz      short loc_1800477A0
0x180047766  lea     rcx, [rbx+30h]
0x18004776a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004776f  mov     [rsp+1C0h+lpData], rax
0x180047774  lea     r9, aDcname; "DCName"
0x18004777b  lea     r8, aFailedToSetWsV; "Failed to set %ws value in registry on "...
0x180047782  mov     edx, edi; int
0x180047784  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x180047789  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x18004778e  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180047795  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x18004779a  call    _CxxThrowException_0
0x1800477a0  cmp     [r14+10h], rsi
0x1800477a4  jz      short loc_18004781A
0x1800477a6  mov     rcx, r14
0x1800477a9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800477ae  mov     ecx, [r14+10h]
0x1800477b2  add     ecx, ecx
0x1800477b4  mov     [rsp+1C0h+cbData], ecx; cbData
0x1800477b8  mov     [rsp+1C0h+lpData], rax; lpData
0x1800477bd  mov     r9d, 1; dwType
0x1800477c3  xor     r8d, r8d; Reserved
0x1800477c6  lea     rdx, aClustercnoguid; "ClusterCNOGuid"
0x1800477cd  mov     rcx, [rbx+0E8h]; hKey
0x1800477d4  call    cs:__imp_RegSetValueExW
0x1800477da  mov     edi, eax
0x1800477dc  test    eax, eax
0x1800477de  jz      short loc_18004781A
0x1800477e0  lea     rcx, [rbx+30h]
0x1800477e4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800477e9  mov     [rsp+1C0h+lpData], rax
0x1800477ee  lea     r9, aClustercnoguid; "ClusterCNOGuid"
0x1800477f5  lea     r8, aFailedToSetWsV; "Failed to set %ws value in registry on "...
0x1800477fc  mov     edx, edi; int
0x1800477fe  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x180047803  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180047808  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18004780f  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x180047814  call    _CxxThrowException_0
0x18004781a  cmp     [r12+10h], rsi
0x18004781f  jz      short loc_180047896
0x180047821  mov     rcx, r12
0x180047824  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180047829  mov     ecx, [r12+10h]
0x18004782e  add     ecx, ecx
0x180047830  mov     [rsp+1C0h+cbData], ecx; cbData
0x180047834  mov     [rsp+1C0h+lpData], rax; lpData
0x180047839  mov     r9d, 1; dwType
0x18004783f  xor     r8d, r8d; Reserved
0x180047842  lea     rdx, aOs; "OS"
0x180047849  mov     rcx, [rbx+0E8h]; hKey
0x180047850  call    cs:__imp_RegSetValueExW
0x180047856  mov     edi, eax
0x180047858  test    eax, eax
0x18004785a  jz      short loc_180047896
0x18004785c  lea     rcx, [rbx+30h]
0x180047860  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180047865  mov     [rsp+1C0h+lpData], rax
0x18004786a  lea     r9, aOs; "OS"
0x180047871  lea     r8, aFailedToSetWsV; "Failed to set %ws value in registry on "...
0x180047878  mov     edx, edi; int
0x18004787a  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x18004787f  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180047884  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18004788b  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x180047890  call    _CxxThrowException_0
0x180047896  cmp     [r13+10h], rsi
0x18004789a  jz      short loc_180047910
0x18004789c  mov     rcx, r13
0x18004789f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800478a4  mov     ecx, [r13+10h]
0x1800478a8  add     ecx, ecx
0x1800478aa  mov     [rsp+1C0h+cbData], ecx; cbData
0x1800478ae  mov     [rsp+1C0h+lpData], rax; lpData
0x1800478b3  mov     r9d, 1; dwType
0x1800478b9  xor     r8d, r8d; Reserved
0x1800478bc  lea     rdx, aOsversion; "OSVersion"
0x1800478c3  mov     rcx, [rbx+0E8h]; hKey
0x1800478ca  call    cs:__imp_RegSetValueExW
0x1800478d0  mov     edi, eax
0x1800478d2  test    eax, eax
0x1800478d4  jz      short loc_180047910
0x1800478d6  lea     rcx, [rbx+30h]
0x1800478da  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800478df  mov     [rsp+1C0h+lpData], rax
0x1800478e4  lea     r9, aOsversion; "OSVersion"
0x1800478eb  lea     r8, aFailedToSetWsV; "Failed to set %ws value in registry on "...
0x1800478f2  mov     edx, edi; int
0x1800478f4  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x1800478f9  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x1800478fe  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180047905  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x18004790a  call    _CxxThrowException_0
0x180047910  mov     rcx, [rbp+0C0h+var_50]
0x180047914  xor     rcx, rsp; StackCookie
0x180047917  call    __security_check_cookie
0x18004791c  add     rsp, 188h
0x180047923  pop     r15
0x180047925  pop     r14
0x180047927  pop     r13
0x180047929  pop     r12
0x18004792b  pop     rdi
0x18004792c  pop     rsi
0x18004792d  pop     rbx
0x18004792e  pop     rbp
0x18004792f  retn
```
