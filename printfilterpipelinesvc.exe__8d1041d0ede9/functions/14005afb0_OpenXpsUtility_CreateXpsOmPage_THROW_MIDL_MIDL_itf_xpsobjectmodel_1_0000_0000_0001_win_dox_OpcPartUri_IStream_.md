# OpenXpsUtility::CreateXpsOmPage_THROW(__MIDL___MIDL_itf_xpsobjectmodel_1_0000_0000_0001,win_dox::OpcPartUri &,IStream *,std::map<win_dox::OpcPartUri,IStream *,std::less<win_dox::OpcPartUri>,std::allocator<std::pair<win_dox::OpcPartUri const,IStream *>>> &)

- ea: `0x14005afb0`
- end: `0x14005b1ea`
- name: `?CreateXpsOmPage_THROW@OpenXpsUtility@@YA?AV?$scope@PEAUIXpsOMPage1@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@W4__MIDL___MIDL_itf_xpsobjectmodel_1_0000_0000_0001@@AEAVOpcPartUri@win_dox@@PEAUIStream@@AEAV?$map@VOpcPartUri@win_dox@@PEAUIStream@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@U?$pair@$$CBVOpcPartUri@win_dox@@PEAUIStream@@@std@@@5@@std@@@Z`
- size: `570`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14005a250`

## callees

- `0x140026400`
- `0x14004650c`
- `0x14005a304`
- `0x14005afb0`
- `0x14005b8c8`
- `0x140063010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14005b00c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14005b00c`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *OpenXpsUtility::CreateXpsOmPage_THROW(_QWORD *a1, int a2, const char *a3, ...)
{
  HRESULT v5; // eax
  int v6; // edx
  const char *v7; // r8
  unsigned int v8; // r9d
  __int64 v9; // rsi
  int v10; // eax
  int v11; // edx
  const char *v12; // r8
  unsigned int v13; // r9d
  int v14; // eax
  int v15; // edx
  __int64 *j; // rcx
  const char *v17; // r8
  unsigned int v18; // r9d
  __int64 **v19; // rsi
  __int64 *v20; // rbx
  int appended; // eax
  int v22; // edx
  const char *v23; // r8
  unsigned int v24; // r9d
  __int64 *i; // rax
  LPVOID v26; // rsi
  __int64 v27; // r14
  __int64 v28; // rcx
  __int64 *v29; // rbx
  _QWORD *Interface; // rax
  int v31; // eax
  int v32; // edx
  const char *v33; // r8
  unsigned int v34; // r9d
  __int64 v35; // rax
  __int64 *v37; // [rsp+48h] [rbp-28h] BYREF
  __int64 v38; // [rsp+50h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-18h] BYREF
  __int64 v40; // [rsp+60h] [rbp-10h] BYREF
  __int64 v41; // [rsp+B8h] [rbp+48h] BYREF
  va_list va; // [rsp+B8h] [rbp+48h]
  __int64 **v43; // [rsp+C0h] [rbp+50h]
  va_list va1; // [rsp+C8h] [rbp+58h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v41 = va_arg(va1, _QWORD);
  v43 = va_arg(va1, __int64 **);
  if ( !v41 )
    SplException::RealThrowFromHR((SplException *)0x80070057LL, a2, a3, 0);
  v37 = 0;
  ppv = 0;
  v5 = CoCreateInstance(
         &GUID_e974d26d_3d9b_4d47_88cc_3872f2dc3585,
         0,
         1u,
         &GUID_0a91b617_d612_4181_bf7c_be5824e9cc8f,
         &ppv);
  if ( v5 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v5, v6, v7, v8);
  v9 = *(_QWORD *)ppv;
  v37 = 0;
  v10 = (*(__int64 (__fastcall **)(LPVOID, __int64 **))(v9 + 88))(ppv, &v37);
  if ( v10 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v10, v11, v12, v13);
  OpenXpsUtility::CreatePartResourcesFromMarkup(2, (__int64)a3, va, &v37);
  v40 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v41 + 40LL))(v41, 0, 0, 0);
  if ( v14 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v14, v15, v17, v18);
  v38 = 0;
  v19 = v43;
  v20 = (__int64 *)**v43;
  while ( v20 != *v19 )
  {
    appended = OpenXpsUtility::LoadAndAppendResourceDictionary(j, v20 + 4, v20 + 7, &v37);
    if ( appended < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)appended, v22, v23, v24);
    j = (__int64 *)v20[2];
    if ( *((_BYTE *)j + 25) )
    {
      for ( i = (__int64 *)v20[1]; !*((_BYTE *)i + 25) && v20 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v20 = i;
      v20 = i;
    }
    else
    {
      v20 = (__int64 *)v20[2];
      for ( j = (__int64 *)*j; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v20 = j;
    }
  }
  v26 = ppv;
  v27 = *(_QWORD *)ppv;
  v28 = v38;
  v38 = 0;
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  v38 = 0;
  v29 = v37;
  Interface = (_QWORD *)win_dox::OpcPartUri::GetInterface(a3, &v40);
  v31 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, __int64 *, int, __int64 *))(v27 + 400))(
          v26,
          v41,
          *Interface,
          v29,
          1,
          &v38);
  if ( v31 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v31, v32, v33, v34);
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  v35 = v38;
  v38 = 0;
  *a1 = v35;
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
    v37 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return a1;
}

```

## disassembly

```asm
0x14005afb0  mov     [rsp-28h+arg_0], rbx
0x14005afb5  mov     [rsp-28h+arg_8], rsi
0x14005afba  mov     [rsp-28h+arg_18], r9
0x14005afbf  push    rbp
0x14005afc0  push    rdi
0x14005afc1  push    r12
0x14005afc3  push    r14
0x14005afc5  push    r15
0x14005afc7  mov     rbp, rsp
0x14005afca  sub     rsp, 70h
0x14005afce  mov     r15, r8
0x14005afd1  mov     rdi, rcx
0x14005afd4  xor     r12d, r12d
0x14005afd7  test    r9, r9
0x14005afda  jnz     short loc_14005AFE7
0x14005afdc  mov     ecx, 80070057h; this
0x14005afe1  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14005afe7  mov     [rbp+var_28], r12
0x14005afeb  mov     [rbp+var_18], r12
0x14005afef  lea     rax, [rbp+var_18]
0x14005aff3  mov     [rsp+70h+ppv], rax; ppv
0x14005aff8  lea     r9, _GUID_0a91b617_d612_4181_bf7c_be5824e9cc8f; riid
0x14005afff  xor     edx, edx; pUnkOuter
0x14005b001  lea     r8d, [rdx+1]; dwClsContext
0x14005b005  lea     rcx, _GUID_e974d26d_3d9b_4d47_88cc_3872f2dc3585; rclsid
0x14005b00c  call    cs:__imp_CoCreateInstance
0x14005b012  test    eax, eax
0x14005b014  jns     short loc_14005B01E
0x14005b016  mov     ecx, eax; this
0x14005b018  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14005b01e  mov     rbx, [rbp+var_18]
0x14005b022  mov     rsi, [rbx]
0x14005b025  mov     rcx, [rbp+var_28]
0x14005b029  mov     [rbp+var_28], r12
0x14005b02d  test    rcx, rcx
0x14005b030  jz      short loc_14005B03F
0x14005b032  mov     rax, [rcx]
0x14005b035  mov     rax, [rax+10h]
0x14005b039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b03e  nop
0x14005b03f  mov     [rbp+var_28], r12
0x14005b043  lea     rdx, [rbp+var_28]
0x14005b047  mov     rcx, rbx
0x14005b04a  mov     rax, [rsi+58h]
0x14005b04e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b053  test    eax, eax
0x14005b055  jns     short loc_14005B05F
0x14005b057  mov     ecx, eax; this
0x14005b059  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14005b05f  lea     r9, [rbp+var_28]
0x14005b063  lea     r8, [rbp+arg_18]
0x14005b067  mov     rdx, r15
0x14005b06a  mov     ecx, 2
0x14005b06f  call    ?CreatePartResourcesFromMarkup@OpenXpsUtility@@YAXW4__MIDL___MIDL_itf_xpsobjectmodel_1_0000_0000_0001@@AEBVOpcPartUri@win_dox@@AEAPEAUIStream@@AEAV?$scope@PEAUIXpsOMPartResources@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@Z; OpenXpsUtility::CreatePartResourcesFromMarkup(__MIDL___MIDL_itf_xpsobjectmodel_1_0000_0000_0001,win_dox::OpcPartUri const &,IStream * &,win_scope::scope<IXpsOMPartResources *,win_scope::const_policies<win_scope::com_policies>> &)
0x14005b074  mov     [rbp+var_10], r12
0x14005b078  mov     rcx, [rbp+arg_18]
0x14005b07c  mov     rax, [rcx]
0x14005b07f  xor     r9d, r9d
0x14005b082  xor     r8d, r8d
0x14005b085  mov     rdx, r12
0x14005b088  mov     rax, [rax+28h]
0x14005b08c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b091  test    eax, eax
0x14005b093  jns     short loc_14005B09D
0x14005b095  mov     ecx, eax; this
0x14005b097  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14005b09d  mov     [rbp+var_20], r12
0x14005b0a1  mov     rsi, [rbp+arg_20]
0x14005b0a5  mov     rbx, [rsi]
0x14005b0a8  mov     rbx, [rbx]
0x14005b0ab  cmp     rbx, [rsi]
0x14005b0ae  jz      short loc_14005B112
0x14005b0b0  lea     r8, [rbx+38h]
0x14005b0b4  lea     rdx, [rbx+20h]
0x14005b0b8  lea     r9, [rbp+var_28]
0x14005b0bc  call    ?LoadAndAppendResourceDictionary@OpenXpsUtility@@YAJW4__MIDL___MIDL_itf_xpsobjectmodel_1_0000_0000_0001@@AEBVOpcPartUri@win_dox@@AEAPEAUIStream@@AEAV?$scope@PEAUIXpsOMPartResources@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@Z; OpenXpsUtility::LoadAndAppendResourceDictionary(__MIDL___MIDL_itf_xpsobjectmodel_1_0000_0000_0001,win_dox::OpcPartUri const &,IStream * &,win_scope::scope<IXpsOMPartResources *,win_scope::const_policies<win_scope::com_policies>> &)
0x14005b0c1  test    eax, eax
0x14005b0c3  js      short loc_14005B10A
0x14005b0c5  mov     rcx, [rbx+10h]
0x14005b0c9  cmp     [rcx+19h], r12b
0x14005b0cd  jz      short loc_14005B0ED
0x14005b0cf  mov     rax, [rbx+8]
0x14005b0d3  jmp     short loc_14005B0E2
0x14005b0d5  cmp     rbx, [rax+10h]
0x14005b0d9  jnz     short loc_14005B0E8
0x14005b0db  mov     rbx, rax
0x14005b0de  mov     rax, [rax+8]
0x14005b0e2  cmp     [rax+19h], r12b
0x14005b0e6  jz      short loc_14005B0D5
0x14005b0e8  mov     rbx, rax
0x14005b0eb  jmp     short loc_14005B0AB
0x14005b0ed  mov     rbx, rcx
0x14005b0f0  mov     rcx, [rcx]
0x14005b0f3  cmp     [rcx+19h], r12b
0x14005b0f7  jnz     short loc_14005B0AB
0x14005b0f9  mov     rbx, rcx
0x14005b0fc  mov     rax, [rcx]
0x14005b0ff  mov     rcx, rax
0x14005b102  cmp     [rax+19h], r12b
0x14005b106  jz      short loc_14005B0F9
0x14005b108  jmp     short loc_14005B0AB
0x14005b10a  mov     ecx, eax; this
0x14005b10c  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14005b112  mov     rsi, [rbp+var_18]
0x14005b116  mov     r14, [rsi]
0x14005b119  mov     rcx, [rbp+var_20]
0x14005b11d  mov     [rbp+var_20], r12
0x14005b121  test    rcx, rcx
0x14005b124  jz      short loc_14005B133
0x14005b126  mov     rax, [rcx]
0x14005b129  mov     rax, [rax+10h]
0x14005b12d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b132  nop
0x14005b133  mov     [rbp+var_20], r12
0x14005b137  mov     rbx, [rbp+var_28]
0x14005b13b  lea     rdx, [rbp+var_10]
0x14005b13f  mov     rcx, r15
0x14005b142  call    ?GetInterface@OpcPartUri@win_dox@@QEBA?AV?$scope@PEAUIOpcPartUri@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::OpcPartUri::GetInterface(void)
0x14005b147  nop
0x14005b148  lea     rcx, [rbp+var_20]
0x14005b14c  mov     [rsp+70h+var_48], rcx
0x14005b151  mov     dword ptr [rsp+70h+ppv], 1
0x14005b159  mov     r9, rbx
0x14005b15c  mov     r8, [rax]
0x14005b15f  mov     rdx, [rbp+arg_18]
0x14005b163  mov     rcx, rsi
0x14005b166  mov     rax, [r14+190h]
0x14005b16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b172  test    eax, eax
0x14005b174  jns     short loc_14005B17E
0x14005b176  mov     ecx, eax; this
0x14005b178  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14005b17e  mov     rcx, [rbp+var_10]
0x14005b182  test    rcx, rcx
0x14005b185  jz      short loc_14005B194
0x14005b187  mov     rax, [rcx]
0x14005b18a  mov     rax, [rax+10h]
0x14005b18e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b193  nop
0x14005b194  mov     rax, [rbp+var_20]
0x14005b198  mov     [rbp+var_20], r12
0x14005b19c  mov     [rdi], rax
0x14005b19f  mov     rcx, [rbp+var_28]
0x14005b1a3  test    rcx, rcx
0x14005b1a6  jz      short loc_14005B1B8
0x14005b1a8  mov     rax, [rcx]
0x14005b1ab  mov     rax, [rax+10h]
0x14005b1af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b1b4  mov     [rbp+var_28], r12
0x14005b1b8  mov     rcx, [rbp+var_18]
0x14005b1bc  test    rcx, rcx
0x14005b1bf  jz      short loc_14005B1CE
0x14005b1c1  mov     rax, [rcx]
0x14005b1c4  mov     rax, [rax+10h]
0x14005b1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b1cd  nop
0x14005b1ce  mov     rax, rdi
0x14005b1d1  lea     r11, [rsp+70h+var_s0]
0x14005b1d6  mov     rbx, [r11+30h]
0x14005b1da  mov     rsi, [r11+38h]
0x14005b1de  mov     rsp, r11
0x14005b1e1  pop     r15
0x14005b1e3  pop     r14
0x14005b1e5  pop     r12
0x14005b1e7  pop     rdi
0x14005b1e8  pop     rbp
0x14005b1e9  retn
```
