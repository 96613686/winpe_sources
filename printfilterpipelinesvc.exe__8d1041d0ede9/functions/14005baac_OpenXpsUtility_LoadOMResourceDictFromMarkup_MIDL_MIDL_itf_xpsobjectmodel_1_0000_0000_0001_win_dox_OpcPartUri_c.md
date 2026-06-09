# OpenXpsUtility::LoadOMResourceDictFromMarkup(__MIDL___MIDL_itf_xpsobjectmodel_1_0000_0000_0001,win_dox::OpcPartUri const &,IStream * &)

- ea: `0x14005baac`
- end: `0x14005bc83`
- name: `?LoadOMResourceDictFromMarkup@OpenXpsUtility@@YA?AV?$scope@PEAUIXpsOMRemoteDictionaryResource1@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@W4__MIDL___MIDL_itf_xpsobjectmodel_1_0000_0000_0001@@AEBVOpcPartUri@win_dox@@AEAPEAUIStream@@@Z`
- size: `471`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14005a1a4`
- `0x14005b8c8`

## callees

- `0x140026400`
- `0x140041030`
- `0x14004650c`
- `0x14005a304`
- `0x14005baac`
- `0x140063010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14005bb04`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14005bb04`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall OpenXpsUtility::LoadOMResourceDictFromMarkup(_QWORD *a1, int a2, const char *a3, const char *a4)
{
  HRESULT v7; // eax
  int v8; // edx
  const char *v9; // r8
  unsigned int v10; // r9d
  __int64 v11; // rax
  int v12; // eax
  int v13; // edx
  const char *v14; // r8
  unsigned int v15; // r9d
  int v16; // eax
  int v17; // edx
  const char *v18; // r8
  unsigned int v19; // r9d
  int v20; // eax
  int v21; // edx
  const char *v22; // r8
  unsigned int v23; // r9d
  LPVOID v24; // rsi
  __int64 v25; // rbx
  __int64 (__fastcall *v26)(LPVOID, _QWORD, _QWORD, __int64 *, __int64 *); // rdi
  __int64 *v27; // rbx
  _QWORD *Interface; // rax
  int v29; // eax
  int v30; // edx
  const char *v31; // r8
  unsigned int v32; // r9d
  __int64 v33; // rax
  __int64 v35; // [rsp+38h] [rbp-18h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-10h] BYREF
  __int64 v37; // [rsp+48h] [rbp-8h] BYREF
  __int64 *v38; // [rsp+98h] [rbp+48h] BYREF

  if ( !*(_QWORD *)a4 )
    SplException::RealThrowFromHR((SplException *)0x80070057LL, a2, a3, (unsigned int)a4);
  ppv = 0;
  v7 = CoCreateInstance(
         &GUID_e974d26d_3d9b_4d47_88cc_3872f2dc3585,
         0,
         1u,
         &GUID_0a91b617_d612_4181_bf7c_be5824e9cc8f,
         &ppv);
  if ( v7 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v7, v8, v9, v10);
  v38 = 0;
  v11 = *(_QWORD *)ppv;
  v38 = 0;
  v12 = (*(__int64 (__fastcall **)(LPVOID, __int64 **))(v11 + 88))(ppv, &v38);
  if ( v12 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v12, v13, v14, v15);
  v37 = 0;
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)a4 + 40LL))(*(_QWORD *)a4, 0, 0, 0);
  if ( v16 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v16, v17, v18, v19);
  OpenXpsUtility::CreatePartResourcesFromMarkup(2, (__int64)a3, a4, &v38);
  v20 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**(_QWORD **)a4 + 40LL))(*(_QWORD *)a4, v37, 0, 0);
  if ( v20 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v20, v21, v22, v23);
  v35 = 0;
  v24 = ppv;
  v25 = *(_QWORD *)ppv;
  win_scope::detail::scope_helper<IOpcFactory *,win_scope::const_policies<win_scope::com_policies>>::reset(&v35, 0);
  v35 = 0;
  v26 = *(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int64 *, __int64 *))(v25 + 408);
  v27 = v38;
  Interface = (_QWORD *)win_dox::OpcPartUri::GetInterface(a3, &v37);
  v29 = v26(v24, *(_QWORD *)a4, *Interface, v27, &v35);
  if ( v29 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v29, v30, v31, v32);
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  v33 = v35;
  v35 = 0;
  *a1 = v33;
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64 *))(*v38 + 16))(v38);
    v38 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return a1;
}

```

## disassembly

```asm
0x14005baac  mov     [rsp-28h+arg_0], rbx
0x14005bab1  mov     [rsp-28h+arg_8], rsi
0x14005bab6  push    rbp
0x14005bab7  push    rdi
0x14005bab8  push    r12
0x14005baba  push    r14
0x14005babc  push    r15
0x14005babe  mov     rbp, rsp
0x14005bac1  sub     rsp, 50h
0x14005bac5  mov     r15, r9
0x14005bac8  mov     r12, r8
0x14005bacb  mov     r14, rcx
0x14005bace  cmp     qword ptr [r9], 0
0x14005bad2  jnz     short loc_14005BADF
0x14005bad4  mov     ecx, 80070057h; this
0x14005bad9  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14005badf  mov     [rbp+var_10], 0
0x14005bae7  lea     rax, [rbp+var_10]
0x14005baeb  mov     [rsp+50h+ppv], rax; ppv
0x14005baf0  lea     r9, _GUID_0a91b617_d612_4181_bf7c_be5824e9cc8f; riid
0x14005baf7  xor     edx, edx; pUnkOuter
0x14005baf9  lea     r8d, [rdx+1]; dwClsContext
0x14005bafd  lea     rcx, _GUID_e974d26d_3d9b_4d47_88cc_3872f2dc3585; rclsid
0x14005bb04  call    cs:__imp_CoCreateInstance
0x14005bb0a  test    eax, eax
0x14005bb0c  jns     short loc_14005BB16
0x14005bb0e  mov     ecx, eax; this
0x14005bb10  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14005bb16  mov     [rbp+arg_18], 0
0x14005bb1e  mov     rcx, [rbp+var_10]
0x14005bb22  mov     rax, [rcx]
0x14005bb25  mov     [rbp+arg_18], 0
0x14005bb2d  lea     rdx, [rbp+arg_18]
0x14005bb31  mov     rax, [rax+58h]
0x14005bb35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005bb3a  test    eax, eax
0x14005bb3c  jns     short loc_14005BB46
0x14005bb3e  mov     ecx, eax; this
0x14005bb40  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14005bb46  mov     [rbp+var_8], 0
0x14005bb4e  mov     rcx, [r15]
0x14005bb51  mov     rax, [rcx]
0x14005bb54  xor     r9d, r9d
0x14005bb57  xor     r8d, r8d
0x14005bb5a  mov     rdx, [rbp+var_8]
0x14005bb5e  mov     rax, [rax+28h]
0x14005bb62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005bb67  test    eax, eax
0x14005bb69  jns     short loc_14005BB73
0x14005bb6b  mov     ecx, eax; this
0x14005bb6d  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14005bb73  lea     r9, [rbp+arg_18]
0x14005bb77  mov     r8, r15
0x14005bb7a  mov     rdx, r12
0x14005bb7d  mov     ecx, 2
0x14005bb82  call    ?CreatePartResourcesFromMarkup@OpenXpsUtility@@YAXW4__MIDL___MIDL_itf_xpsobjectmodel_1_0000_0000_0001@@AEBVOpcPartUri@win_dox@@AEAPEAUIStream@@AEAV?$scope@PEAUIXpsOMPartResources@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@Z; OpenXpsUtility::CreatePartResourcesFromMarkup(__MIDL___MIDL_itf_xpsobjectmodel_1_0000_0000_0001,win_dox::OpcPartUri const &,IStream * &,win_scope::scope<IXpsOMPartResources *,win_scope::const_policies<win_scope::com_policies>> &)
0x14005bb87  mov     rcx, [r15]
0x14005bb8a  mov     rax, [rcx]
0x14005bb8d  xor     r9d, r9d
0x14005bb90  xor     r8d, r8d
0x14005bb93  mov     rdx, [rbp+var_8]
0x14005bb97  mov     rax, [rax+28h]
0x14005bb9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005bba0  test    eax, eax
0x14005bba2  jns     short loc_14005BBAC
0x14005bba4  mov     ecx, eax; this
0x14005bba6  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14005bbac  mov     [rbp+var_18], 0
0x14005bbb4  mov     rsi, [rbp+var_10]
0x14005bbb8  mov     rbx, [rsi]
0x14005bbbb  xor     edx, edx
0x14005bbbd  lea     rcx, [rbp+var_18]
0x14005bbc1  call    ?reset@?$scope_helper@PEAUIOpcFactory@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIOpcFactory@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIOpcFactory@@@Z; win_scope::detail::scope_helper<IOpcFactory *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IOpcFactory *,win_scope::const_policies<win_scope::com_policies>> &,IOpcFactory *)
0x14005bbc6  mov     [rbp+var_18], 0
0x14005bbce  mov     rdi, [rbx+198h]
0x14005bbd5  mov     rbx, [rbp+arg_18]
0x14005bbd9  lea     rdx, [rbp+var_8]
0x14005bbdd  mov     rcx, r12
0x14005bbe0  call    ?GetInterface@OpcPartUri@win_dox@@QEBA?AV?$scope@PEAUIOpcPartUri@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::OpcPartUri::GetInterface(void)
0x14005bbe5  nop
0x14005bbe6  lea     rcx, [rbp+var_18]
0x14005bbea  mov     [rsp+50h+ppv], rcx
0x14005bbef  mov     r9, rbx
0x14005bbf2  mov     r8, [rax]
0x14005bbf5  mov     rdx, [r15]
0x14005bbf8  mov     rcx, rsi
0x14005bbfb  mov     rax, rdi
0x14005bbfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005bc03  test    eax, eax
0x14005bc05  jns     short loc_14005BC0F
0x14005bc07  mov     ecx, eax; this
0x14005bc09  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14005bc0f  mov     rcx, [rbp+var_8]
0x14005bc13  test    rcx, rcx
0x14005bc16  jz      short loc_14005BC25
0x14005bc18  mov     rax, [rcx]
0x14005bc1b  mov     rax, [rax+10h]
0x14005bc1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005bc24  nop
0x14005bc25  mov     rax, [rbp+var_18]
0x14005bc29  mov     [rbp+var_18], 0
0x14005bc31  mov     [r14], rax
0x14005bc34  mov     rcx, [rbp+arg_18]
0x14005bc38  test    rcx, rcx
0x14005bc3b  jz      short loc_14005BC51
0x14005bc3d  mov     rax, [rcx]
0x14005bc40  mov     rax, [rax+10h]
0x14005bc44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005bc49  mov     [rbp+arg_18], 0
0x14005bc51  mov     rcx, [rbp+var_10]
0x14005bc55  test    rcx, rcx
0x14005bc58  jz      short loc_14005BC67
0x14005bc5a  mov     rax, [rcx]
0x14005bc5d  mov     rax, [rax+10h]
0x14005bc61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005bc66  nop
0x14005bc67  mov     rax, r14
0x14005bc6a  lea     r11, [rsp+50h+var_s0]
0x14005bc6f  mov     rbx, [r11+30h]
0x14005bc73  mov     rsi, [r11+38h]
0x14005bc77  mov     rsp, r11
0x14005bc7a  pop     r15
0x14005bc7c  pop     r14
0x14005bc7e  pop     r12
0x14005bc80  pop     rdi
0x14005bc81  pop     rbp
0x14005bc82  retn
```
