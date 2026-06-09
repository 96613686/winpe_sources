# CscPolicyp_GetServiceActivePolicyAuthority(POLICY_AUTHORITY *)

- ea: `0x1800138b8`
- end: `0x180013990`
- name: `?CscPolicyp_GetServiceActivePolicyAuthority@@YAJPEAW4POLICY_AUTHORITY@@@Z`
- size: `216`
- prototype: `__int64 __fastcall(enum POLICY_AUTHORITY *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180012120`
- `0x1800124c4`

## callees

- `0x180002040`
- `0x1800057e0`
- `0x1800138b8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013950`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013950`

## pseudocode

```c
__int64 __fastcall CscPolicyp_GetServiceActivePolicyAuthority(enum POLICY_AUTHORITY *a1, const struct _GUID *a2)
{
  void *v3; // rdx
  int v4; // ebx
  unsigned int v5; // edi
  _QWORD v7[2]; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v8; // [rsp+40h] [rbp-20h]
  __int64 v9; // [rsp+78h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+20h] BYREF

  CObjectInGIT_SvcObj::CObjectInGIT_SvcObj((CObjectInGIT_SvcObj *)v7, a2);
  v9 = 0;
  v4 = CObjectInGIT<CComCoCreator_SvcObj>::CreateInstanceAndMarshalToGIT((__int64)v7, v3, &v9);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, enum POLICY_AUTHORITY *))(*(_QWORD *)v9 + 512LL))(v9, a1);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v5 = v8;
  v7[0] = &CInterfaceInGITBase::`vftable';
  if ( v8 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, v5);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800138b8  mov     [rsp-8+arg_0], rbx
0x1800138bd  mov     [rsp-8+arg_18], rdi
0x1800138c2  push    rbp
0x1800138c3  mov     rbp, rsp
0x1800138c6  sub     rsp, 60h
0x1800138ca  mov     rdi, rcx
0x1800138cd  lea     rcx, [rbp+var_30]; this
0x1800138d1  call    ??0CObjectInGIT_SvcObj@@QEAA@AEBU_GUID@@@Z; CObjectInGIT_SvcObj::CObjectInGIT_SvcObj(_GUID const &)
0x1800138d6  lea     r8, [rbp+arg_8]
0x1800138da  mov     [rbp+arg_8], 0
0x1800138e2  lea     rcx, [rbp+var_30]
0x1800138e6  call    ?CreateInstanceAndMarshalToGIT@?$CObjectInGIT@VCComCoCreator_SvcObj@@@@QEAAJAEBU_GUID@@PEAPEAX@Z; CObjectInGIT<CComCoCreator_SvcObj>::CreateInstanceAndMarshalToGIT(_GUID const &,void * *)
0x1800138eb  mov     ebx, eax
0x1800138ed  test    eax, eax
0x1800138ef  js      short loc_180013919
0x1800138f1  mov     rcx, [rbp+arg_8]
0x1800138f5  mov     rdx, rdi
0x1800138f8  mov     rax, [rcx]
0x1800138fb  mov     rax, [rax+200h]
0x180013902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013907  mov     rcx, [rbp+arg_8]
0x18001390b  mov     ebx, eax
0x18001390d  mov     rax, [rcx]
0x180013910  mov     rax, [rax+10h]
0x180013914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013919  mov     edi, [rbp+var_20]
0x18001391c  lea     rax, ??_7CInterfaceInGITBase@@6B@; const CInterfaceInGITBase::`vftable'
0x180013923  mov     [rbp+var_30], rax
0x180013927  test    edi, edi
0x180013929  jz      short loc_18001397C
0x18001392b  xor     edx, edx; pUnkOuter
0x18001392d  mov     [rbp+arg_10], 0
0x180013935  lea     rax, [rbp+arg_10]
0x180013939  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180013940  mov     [rsp+60h+ppv], rax; ppv
0x180013945  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18001394c  lea     r8d, [rdx+1]; dwClsContext
0x180013950  call    cs:__imp_CoCreateInstance
0x180013956  test    eax, eax
0x180013958  js      short loc_18001397C
0x18001395a  mov     rcx, [rbp+arg_10]
0x18001395e  mov     edx, edi
0x180013960  mov     rax, [rcx]
0x180013963  mov     rax, [rax+20h]
0x180013967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001396c  mov     rcx, [rbp+arg_10]
0x180013970  mov     rax, [rcx]
0x180013973  mov     rax, [rax+10h]
0x180013977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001397c  lea     r11, [rsp+60h+var_s0]
0x180013981  mov     eax, ebx
0x180013983  mov     rbx, [r11+10h]
0x180013987  mov     rdi, [r11+28h]
0x18001398b  mov     rsp, r11
0x18001398e  pop     rbp
0x18001398f  retn
```
