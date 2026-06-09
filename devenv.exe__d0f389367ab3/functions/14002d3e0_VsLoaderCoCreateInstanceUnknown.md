# VsLoaderCoCreateInstanceUnknown

- ea: `0x14002d3e0`
- end: `0x14002d5d2`
- name: `VsLoaderCoCreateInstanceUnknown`
- size: `498`
- prototype: `__int64 __fastcall(IID *rclsid)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011150`
- `0x1400445f0`
- `0x14006af80`

## callees

- `0x140001020`
- `0x140016410`
- `0x14002d3e0`
- `0x14002d5e0`
- `0x14006abf0`
- `0x14006af80`

## import_xrefs

- `ole32!CoCreateInstance` at `0x14002d4f6`
- `ole32!CoCreateInstance` at `0x14002d551`
- `ole32!CoCreateInstance` at `0x14002d4f6`
- `ole32!CoCreateInstance` at `0x14002d551`
- `OLEAUT32!__imp_SysFreeString` at `0x14002d494`
- `OLEAUT32!__imp_SysFreeString` at `0x14002d49e`
- `OLEAUT32!__imp_SysFreeString` at `0x14002d4a8`
- `OLEAUT32!__imp_SysFreeString` at `0x14002d56d`
- `OLEAUT32!__imp_SysFreeString` at `0x14002d57e`
- `OLEAUT32!__imp_SysFreeString` at `0x14002d58f`
- `OLEAUT32!__imp_SysFreeString` at `0x14002d5a0`
- `OLEAUT32!__imp_SysFreeString` at `0x14002d494`
- `OLEAUT32!__imp_SysFreeString` at `0x14002d49e`
- `OLEAUT32!__imp_SysFreeString` at `0x14002d4a8`
- `OLEAUT32!__imp_SysFreeString` at `0x14002d56d`
- `OLEAUT32!__imp_SysFreeString` at `0x14002d57e`
- `OLEAUT32!__imp_SysFreeString` at `0x14002d58f`
- `OLEAUT32!__imp_SysFreeString` at `0x14002d5a0`

## pseudocode

```c
__int64 __fastcall VsLoaderCoCreateInstanceUnknown(IID *rclsid, IUnknown *a2, DWORD a3, LPVOID *a4)
{
  OLECHAR *v6; // rdi
  int AggregatedManagedObject; // ebx
  DWORD v8; // ebx
  HRESULT v9; // eax
  HRESULT Instance; // eax
  BSTR bstrString; // [rsp+30h] [rbp-50h] BYREF
  BSTR v13; // [rsp+38h] [rbp-48h] BYREF
  BSTR v14; // [rsp+40h] [rbp-40h] BYREF
  DWORD dwClsContext; // [rsp+48h] [rbp-38h]
  BSTR v16; // [rsp+50h] [rbp-30h] BYREF
  LPUNKNOWN pUnkOuter; // [rsp+58h] [rbp-28h]
  LPVOID ppv; // [rsp+60h] [rbp-20h] BYREF
  IID rclsida; // [rsp+68h] [rbp-18h] BYREF

  dwClsContext = a3;
  pUnkOuter = a2;
  v16 = 0;
  bstrString = 0;
  v13 = 0;
  v14 = 0;
  rclsida = GUID_NULL;
  ppv = 0;
  v6 = 0;
  if ( (unsigned int)GetManagedObjectInfo(rclsid, &bstrString, &v13, &v14) && (bstrString || v13) )
  {
    if ( v14 )
    {
      AggregatedManagedObject = VsCoCreateAggregatedManagedObject(
                                  bstrString,
                                  v13,
                                  v14,
                                  (__int64)&IID_IUnknown,
                                  (__int64)a4);
      if ( AggregatedManagedObject >= 0 )
      {
        if ( *a4 )
        {
          _mm_lfence();
          SysFreeString(bstrString);
          SysFreeString(v13);
          SysFreeString(v14);
          return (unsigned int)AggregatedManagedObject;
        }
      }
    }
  }
  AggregatedManagedObject = GetLoader(rclsid, &rclsida);
  if ( AggregatedManagedObject < 0 )
    goto LABEL_15;
  _mm_lfence();
  AggregatedManagedObject = GetModulePath(rclsid, &v16);
  if ( AggregatedManagedObject < 0 )
  {
    v6 = v16;
    goto LABEL_15;
  }
  v8 = dwClsContext;
  v9 = CoCreateInstance(&rclsida, 0, dwClsContext, &GUID_10e4254c_6d73_4c38_b011_e0049b2e0a0f, &ppv);
  v6 = v16;
  if ( v9 < 0 )
  {
    AggregatedManagedObject = -2147155456;
LABEL_15:
    _mm_lfence();
    Instance = CoCreateInstance(rclsid, pUnkOuter, dwClsContext, &IID_IUnknown, a4);
    if ( Instance >= 0 || AggregatedManagedObject != -2147155456 )
      AggregatedManagedObject = Instance;
    goto LABEL_18;
  }
  _mm_lfence();
  AggregatedManagedObject = (*(__int64 (__fastcall **)(LPVOID, BSTR, IID *, LPUNKNOWN, DWORD, LPVOID *))(*(_QWORD *)ppv + 56LL))(
                              ppv,
                              v16,
                              rclsid,
                              pUnkOuter,
                              v8,
                              a4);
  if ( AggregatedManagedObject < 0 )
    goto LABEL_15;
LABEL_18:
  if ( v6 )
    SysFreeString(v6);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v13 )
    SysFreeString(v13);
  if ( v14 )
    SysFreeString(v14);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)AggregatedManagedObject;
}

```

## disassembly

```asm
0x14002d3e0  push    rbp
0x14002d3e2  push    rbx
0x14002d3e3  push    rdi
0x14002d3e4  push    r12
0x14002d3e6  push    r13
0x14002d3e8  mov     rbp, rsp
0x14002d3eb  sub     rsp, 80h
0x14002d3f2  mov     rax, cs:__security_cookie
0x14002d3f9  xor     rax, rsp
0x14002d3fc  mov     [rbp+var_8], rax
0x14002d400  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14002d407  xor     eax, eax
0x14002d409  mov     [rbp+dwClsContext], r8d
0x14002d40d  mov     r13, r9
0x14002d410  mov     [rbp+pUnkOuter], rdx
0x14002d414  mov     rbx, rdx
0x14002d417  mov     [rbp+var_30], rax
0x14002d41b  lea     r9, [rbp+var_40]; unsigned __int16 **
0x14002d41f  mov     [rbp+bstrString], rax
0x14002d423  lea     r8, [rbp+var_48]; unsigned __int16 **
0x14002d427  mov     [rbp+var_48], rax
0x14002d42b  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x14002d42f  mov     [rbp+var_40], rax
0x14002d433  movdqu  xmmword ptr [rbp+rclsid.Data1], xmm0
0x14002d438  mov     r12, rcx
0x14002d43b  mov     [rbp+var_20], rax
0x14002d43f  mov     edi, eax
0x14002d441  call    ?GetManagedObjectInfo@@YAHAEBU_GUID@@PEAPEAG11@Z; GetManagedObjectInfo(_GUID const &,ushort * *,ushort * *,ushort * *)
0x14002d446  lea     rcx, IID_IUnknown
0x14002d44d  test    eax, eax
0x14002d44f  jz      short loc_14002D4B3
0x14002d451  cmp     [rbp+bstrString], rdi
0x14002d455  jnz     short loc_14002D45D
0x14002d457  cmp     [rbp+var_48], rdi
0x14002d45b  jz      short loc_14002D4B3
0x14002d45d  cmp     [rbp+var_40], rdi
0x14002d461  jz      short loc_14002D4B3
0x14002d463  mov     r8, [rbp+var_40]; OLECHAR *
0x14002d467  mov     r9, rbx
0x14002d46a  mov     rdx, [rbp+var_48]; OLECHAR *
0x14002d46e  mov     [rsp+80h+var_58], r13; __int64
0x14002d473  mov     [rsp+80h+ppv], rcx; __int64
0x14002d478  mov     rcx, [rbp+bstrString]; psz
0x14002d47c  call    VsCoCreateAggregatedManagedObject
0x14002d481  mov     ebx, eax
0x14002d483  test    eax, eax
0x14002d485  js      short loc_14002D4B3
0x14002d487  cmp     [r13+0], rdi
0x14002d48b  jz      short loc_14002D4B3
0x14002d48d  lfence
0x14002d490  mov     rcx, [rbp+bstrString]; bstrString
0x14002d494  call    cs:__imp_SysFreeString
0x14002d49a  mov     rcx, [rbp+var_48]; bstrString
0x14002d49e  call    cs:__imp_SysFreeString
0x14002d4a4  mov     rcx, [rbp+var_40]; bstrString
0x14002d4a8  call    cs:__imp_SysFreeString
0x14002d4ae  jmp     loc_14002D5B5
0x14002d4b3  lea     rdx, [rbp+rclsid]; struct _GUID *
0x14002d4b7  mov     rcx, r12; rclsid
0x14002d4ba  call    ?GetLoader@@YAJAEBU_GUID@@PEAU1@@Z; GetLoader(_GUID const &,_GUID *)
0x14002d4bf  mov     ebx, eax
0x14002d4c1  test    eax, eax
0x14002d4c3  js      short loc_14002D537
0x14002d4c5  lfence
0x14002d4c8  lea     rdx, [rbp+var_30]; unsigned __int16 **
0x14002d4cc  mov     rcx, r12; rclsid
0x14002d4cf  call    ?GetModulePath@@YAJAEBU_GUID@@PEAPEAG@Z; GetModulePath(_GUID const &,ushort * *)
0x14002d4d4  mov     ebx, eax
0x14002d4d6  test    eax, eax
0x14002d4d8  js      short loc_14002D533
0x14002d4da  mov     ebx, [rbp+dwClsContext]
0x14002d4dd  lea     rax, [rbp+var_20]
0x14002d4e1  mov     r8d, ebx; dwClsContext
0x14002d4e4  mov     [rsp+80h+ppv], rax; ppv
0x14002d4e9  lea     r9, _GUID_10e4254c_6d73_4c38_b011_e0049b2e0a0f; riid
0x14002d4f0  xor     edx, edx; pUnkOuter
0x14002d4f2  lea     rcx, [rbp+rclsid]; rclsid
0x14002d4f6  call    cs:__imp_CoCreateInstance
0x14002d4fc  mov     rdi, [rbp+var_30]
0x14002d500  test    eax, eax
0x14002d502  jns     short loc_14002D50B
0x14002d504  mov     ebx, 80050200h
0x14002d509  jmp     short loc_14002D537
0x14002d50b  lfence
0x14002d50e  mov     rcx, [rbp+var_20]
0x14002d512  mov     r8, r12
0x14002d515  mov     r9, [rbp+pUnkOuter]
0x14002d519  mov     rdx, rdi
0x14002d51c  mov     [rsp+80h+var_58], r13
0x14002d521  mov     dword ptr [rsp+80h+ppv], ebx
0x14002d525  mov     rax, [rcx]
0x14002d528  call    qword ptr [rax+38h]
0x14002d52b  mov     ebx, eax
0x14002d52d  test    eax, eax
0x14002d52f  jns     short loc_14002D565
0x14002d531  jmp     short loc_14002D537
0x14002d533  mov     rdi, [rbp+var_30]
0x14002d537  lfence
0x14002d53a  mov     r8d, [rbp+dwClsContext]; dwClsContext
0x14002d53e  lea     r9, IID_IUnknown; riid
0x14002d545  mov     rdx, [rbp+pUnkOuter]; pUnkOuter
0x14002d549  mov     rcx, r12; rclsid
0x14002d54c  mov     [rsp+80h+ppv], r13; ppv
0x14002d551  call    cs:__imp_CoCreateInstance
0x14002d557  test    eax, eax
0x14002d559  jns     short loc_14002D563
0x14002d55b  cmp     ebx, 80050200h
0x14002d561  jz      short loc_14002D565
0x14002d563  mov     ebx, eax
0x14002d565  test    rdi, rdi
0x14002d568  jz      short loc_14002D573
0x14002d56a  mov     rcx, rdi; bstrString
0x14002d56d  call    cs:__imp_SysFreeString
0x14002d573  cmp     [rbp+bstrString], 0
0x14002d578  jz      short loc_14002D584
0x14002d57a  mov     rcx, [rbp+bstrString]; bstrString
0x14002d57e  call    cs:__imp_SysFreeString
0x14002d584  cmp     [rbp+var_48], 0
0x14002d589  jz      short loc_14002D595
0x14002d58b  mov     rcx, [rbp+var_48]; bstrString
0x14002d58f  call    cs:__imp_SysFreeString
0x14002d595  cmp     [rbp+var_40], 0
0x14002d59a  jz      short loc_14002D5A6
0x14002d59c  mov     rcx, [rbp+var_40]; bstrString
0x14002d5a0  call    cs:__imp_SysFreeString
0x14002d5a6  mov     rcx, [rbp+var_20]
0x14002d5aa  test    rcx, rcx
0x14002d5ad  jz      short loc_14002D5B5
0x14002d5af  mov     rax, [rcx]
0x14002d5b2  call    qword ptr [rax+10h]
0x14002d5b5  mov     eax, ebx
0x14002d5b7  mov     rcx, [rbp+var_8]
0x14002d5bb  xor     rcx, rsp; StackCookie
0x14002d5be  call    __security_check_cookie
0x14002d5c3  add     rsp, 80h
0x14002d5ca  pop     r13
0x14002d5cc  pop     r12
0x14002d5ce  pop     rdi
0x14002d5cf  pop     rbx
0x14002d5d0  pop     rbp
0x14002d5d1  retn
```
