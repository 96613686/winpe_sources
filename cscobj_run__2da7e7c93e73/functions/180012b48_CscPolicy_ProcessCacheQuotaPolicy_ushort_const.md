# CscPolicy_ProcessCacheQuotaPolicy(ushort const *)

- ea: `0x180012b48`
- end: `0x180012d9b`
- name: `?CscPolicy_ProcessCacheQuotaPolicy@@YAJPEBG@Z`
- size: `595`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180012120`

## callees

- `0x180002040`
- `0x1800057e0`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x180011fd0`
- `0x180012b48`
- `0x180013138`
- `0x180013714`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012d59`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012d59`

## pseudocode

```c
__int64 __fastcall CscPolicy_ProcessCacheQuotaPolicy(LPCWSTR lpSubKey, const struct _GUID *a2)
{
  void *v3; // rdx
  int InstanceAndMarshalToGIT; // eax
  int v5; // ebx
  int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // edi
  unsigned __int64 v11; // [rsp+40h] [rbp-19h] BYREF
  unsigned __int64 v12; // [rsp+48h] [rbp-11h] BYREF
  unsigned __int64 v13; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int64 v14; // [rsp+58h] [rbp-1h] BYREF
  unsigned __int64 v15; // [rsp+60h] [rbp+7h] BYREF
  __int64 v16; // [rsp+68h] [rbp+Fh] BYREF
  _QWORD v17[2]; // [rsp+70h] [rbp+17h] BYREF
  unsigned int v18; // [rsp+80h] [rbp+27h]
  struct IOfflineFilesService *v19; // [rsp+C8h] [rbp+6Fh] BYREF
  LPVOID ppv; // [rsp+D0h] [rbp+77h] BYREF
  unsigned __int64 hKey; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(char *)(WPP_GLOBAL_Control + 28LL) < 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 46, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids);
  CObjectInGIT_SvcObj::CObjectInGIT_SvcObj((CObjectInGIT_SvcObj *)v17, a2);
  v19 = 0;
  InstanceAndMarshalToGIT = CObjectInGIT<CComCoCreator_SvcObj>::CreateInstanceAndMarshalToGIT(
                              (__int64)v17,
                              v3,
                              (__int64 *)&v19);
  v5 = InstanceAndMarshalToGIT;
  if ( InstanceAndMarshalToGIT >= 0 )
  {
    v14 = 0;
    ppv = 0;
    v16 = 0;
    v13 = 0;
    v12 = 0;
    v6 = (*(__int64 (__fastcall **)(struct IOfflineFilesService *, unsigned __int64 *, unsigned __int64 *, LPVOID *, unsigned __int64 *, __int64 *))(*(_QWORD *)v19 + 176LL))(
           v19,
           &v14,
           &v13,
           &ppv,
           &v12,
           &v16);
    v5 = v6;
    if ( v6 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_16;
      v8 = 48;
    }
    else
    {
      v11 = 0;
      hKey = 0;
      v6 = CscPolicy_QueryCacheQuotaPolicy(lpSubKey, v13, &v11, v12, (HKEY)&hKey);
      v5 = v6;
      if ( v6 >= 0 )
      {
        v15 = 0;
        v5 = CscPolicy_AdjustQuotaPolicyValuesIfNecessary(v19, v14, (unsigned __int64)ppv, &v11, &hKey, &v15);
        if ( v5 >= 0 )
          v5 = CscPolicy_SetQuotaLimits(v19, v11, hKey, (unsigned __int64)ppv, v15);
        goto LABEL_16;
      }
      v7 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      {
LABEL_16:
        (*(void (__fastcall **)(struct IOfflineFilesService *))(*(_QWORD *)v19 + 16LL))(v19);
        goto LABEL_20;
      }
      v8 = 47;
    }
    WPP_SF_d(*(_QWORD *)(v7 + 16), v8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, (unsigned int)v6);
    goto LABEL_16;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      49,
      WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
      (unsigned int)InstanceAndMarshalToGIT);
LABEL_20:
  v9 = v18;
  v17[0] = &CInterfaceInGITBase::`vftable';
  if ( v18 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, v9);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180012b48  mov     [rsp-8+arg_0], rbx
0x180012b4d  push    rbp
0x180012b4e  push    rdi
0x180012b4f  push    r14
0x180012b51  lea     rbp, [rsp-47h]
0x180012b56  sub     rsp, 0A0h
0x180012b5d  mov     rdi, rcx
0x180012b60  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b67  lea     r14, WPP_GLOBAL_Control
0x180012b6e  cmp     rcx, r14
0x180012b71  jz      short loc_180012B8E
0x180012b73  test    byte ptr [rcx+1Ch], 80h
0x180012b77  jz      short loc_180012B8E
0x180012b79  mov     rcx, [rcx+10h]
0x180012b7d  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x180012b84  mov     edx, 2Eh ; '.'
0x180012b89  call    WPP_SF_
0x180012b8e  lea     rcx, [rbp+57h+var_40]; this
0x180012b92  call    ??0CObjectInGIT_SvcObj@@QEAA@AEBU_GUID@@@Z; CObjectInGIT_SvcObj::CObjectInGIT_SvcObj(_GUID const &)
0x180012b97  lea     r8, [rbp+57h+arg_8]
0x180012b9b  mov     [rbp+57h+arg_8], 0
0x180012ba3  lea     rcx, [rbp+57h+var_40]
0x180012ba7  call    ?CreateInstanceAndMarshalToGIT@?$CObjectInGIT@VCComCoCreator_SvcObj@@@@QEAAJAEBU_GUID@@PEAPEAX@Z; CObjectInGIT<CComCoCreator_SvcObj>::CreateInstanceAndMarshalToGIT(_GUID const &,void * *)
0x180012bac  mov     ebx, eax
0x180012bae  test    eax, eax
0x180012bb0  js      loc_180012CF8
0x180012bb6  mov     rcx, [rbp+57h+arg_8]
0x180012bba  lea     rdx, [rbp+57h+var_48]
0x180012bbe  mov     [rsp+0B0h+var_88], rdx
0x180012bc3  lea     r9, [rbp+57h+arg_10]
0x180012bc7  mov     [rbp+57h+var_58], 0
0x180012bcf  lea     rdx, [rbp+57h+var_68]
0x180012bd3  mov     [rbp+57h+arg_10], 0
0x180012bdb  lea     r8, [rbp+57h+var_60]
0x180012bdf  mov     [rbp+57h+var_48], 0
0x180012be7  mov     [rbp+57h+var_60], 0
0x180012bef  mov     [rbp+57h+var_68], 0
0x180012bf7  mov     rax, [rcx]
0x180012bfa  mov     [rsp+0B0h+ppv], rdx
0x180012bff  lea     rdx, [rbp+57h+var_58]
0x180012c03  mov     rax, [rax+0B0h]
0x180012c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c0f  mov     ebx, eax
0x180012c11  test    eax, eax
0x180012c13  js      loc_180012CBC
0x180012c19  mov     r9, [rbp+57h+var_68]; unsigned __int64
0x180012c1d  lea     rax, [rbp+57h+hKey]
0x180012c21  mov     rdx, [rbp+57h+var_60]; unsigned __int64
0x180012c25  lea     r8, [rbp+57h+var_70]; unsigned __int64 *
0x180012c29  mov     rcx, rdi; lpSubKey
0x180012c2c  mov     [rsp+0B0h+ppv], rax; hKey
0x180012c31  mov     [rbp+57h+var_70], 0
0x180012c39  mov     [rbp+57h+hKey], 0
0x180012c41  call    ?CscPolicy_QueryCacheQuotaPolicy@@YAJPEBG_KPEA_K12@Z; CscPolicy_QueryCacheQuotaPolicy(ushort const *,unsigned __int64,unsigned __int64 *,unsigned __int64,unsigned __int64 *)
0x180012c46  mov     ebx, eax
0x180012c48  test    eax, eax
0x180012c4a  js      short loc_180012CA3
0x180012c4c  mov     r8, [rbp+57h+arg_10]; unsigned __int64
0x180012c50  lea     rax, [rbp+57h+var_50]
0x180012c54  mov     rdx, [rbp+57h+var_58]; unsigned __int64
0x180012c58  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x180012c5c  mov     rcx, [rbp+57h+arg_8]; struct IOfflineFilesService *
0x180012c60  mov     [rsp+0B0h+var_88], rax; unsigned __int64 *
0x180012c65  lea     rax, [rbp+57h+hKey]
0x180012c69  mov     [rsp+0B0h+ppv], rax; unsigned __int64 *
0x180012c6e  mov     [rbp+57h+var_50], 0
0x180012c76  call    ?CscPolicy_AdjustQuotaPolicyValuesIfNecessary@@YAJPEAUIOfflineFilesService@@_K1PEA_K22@Z; CscPolicy_AdjustQuotaPolicyValuesIfNecessary(IOfflineFilesService *,unsigned __int64,unsigned __int64,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)
0x180012c7b  mov     ebx, eax
0x180012c7d  test    eax, eax
0x180012c7f  js      short loc_180012CE6
0x180012c81  mov     rax, [rbp+57h+var_50]
0x180012c85  mov     r9, [rbp+57h+arg_10]; unsigned __int64
0x180012c89  mov     r8, [rbp+57h+hKey]; unsigned __int64
0x180012c8d  mov     rdx, [rbp+57h+var_70]; unsigned __int64
0x180012c91  mov     rcx, [rbp+57h+arg_8]; struct IOfflineFilesService *
0x180012c95  mov     [rsp+0B0h+ppv], rax; unsigned __int64
0x180012c9a  call    ?CscPolicy_SetQuotaLimits@@YAJPEAUIOfflineFilesService@@_K111@Z; CscPolicy_SetQuotaLimits(IOfflineFilesService *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)
0x180012c9f  mov     ebx, eax
0x180012ca1  jmp     short loc_180012CE6
0x180012ca3  mov     rcx, cs:WPP_GLOBAL_Control
0x180012caa  cmp     rcx, r14
0x180012cad  jz      short loc_180012CE6
0x180012caf  test    byte ptr [rcx+1Ch], 2
0x180012cb3  jz      short loc_180012CE6
0x180012cb5  mov     edx, 2Fh ; '/'
0x180012cba  jmp     short loc_180012CD3
0x180012cbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180012cc3  cmp     rcx, r14
0x180012cc6  jz      short loc_180012CE6
0x180012cc8  test    byte ptr [rcx+1Ch], 2
0x180012ccc  jz      short loc_180012CE6
0x180012cce  mov     edx, 30h ; '0'
0x180012cd3  mov     rcx, [rcx+10h]
0x180012cd7  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x180012cde  mov     r9d, eax
0x180012ce1  call    WPP_SF_d
0x180012ce6  mov     rcx, [rbp+57h+arg_8]
0x180012cea  mov     rax, [rcx]
0x180012ced  mov     rax, [rax+10h]
0x180012cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cf6  jmp     short loc_180012D22
0x180012cf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180012cff  cmp     rcx, r14
0x180012d02  jz      short loc_180012D22
0x180012d04  test    byte ptr [rcx+1Ch], 2
0x180012d08  jz      short loc_180012D22
0x180012d0a  mov     rcx, [rcx+10h]
0x180012d0e  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x180012d15  mov     edx, 31h ; '1'
0x180012d1a  mov     r9d, eax
0x180012d1d  call    WPP_SF_d
0x180012d22  mov     edi, [rbp+57h+var_30]
0x180012d25  lea     rax, ??_7CInterfaceInGITBase@@6B@; const CInterfaceInGITBase::`vftable'
0x180012d2c  mov     [rbp+57h+var_40], rax
0x180012d30  test    edi, edi
0x180012d32  jz      short loc_180012D85
0x180012d34  xor     edx, edx; pUnkOuter
0x180012d36  mov     [rbp+57h+arg_10], 0
0x180012d3e  lea     rax, [rbp+57h+arg_10]
0x180012d42  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180012d49  mov     [rsp+0B0h+ppv], rax; ppv
0x180012d4e  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180012d55  lea     r8d, [rdx+1]; dwClsContext
0x180012d59  call    cs:__imp_CoCreateInstance
0x180012d5f  test    eax, eax
0x180012d61  js      short loc_180012D85
0x180012d63  mov     rcx, [rbp+57h+arg_10]
0x180012d67  mov     edx, edi
0x180012d69  mov     rax, [rcx]
0x180012d6c  mov     rax, [rax+20h]
0x180012d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d75  mov     rcx, [rbp+57h+arg_10]
0x180012d79  mov     rax, [rcx]
0x180012d7c  mov     rax, [rax+10h]
0x180012d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d85  mov     eax, ebx
0x180012d87  mov     rbx, [rsp+0B0h+arg_0]
0x180012d8f  add     rsp, 0A0h
0x180012d96  pop     r14
0x180012d98  pop     rdi
0x180012d99  pop     rbp
0x180012d9a  retn
```
