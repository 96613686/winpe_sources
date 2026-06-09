# _ReadHashConfiguration

- ea: `0x18002a854`
- end: `0x18002a98b`
- name: `_ReadHashConfiguration`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a79c`

## callees

- `0x18000d650`
- `0x18001722c`
- `0x18002a1a8`
- `0x18002a854`
- `0x18002dfd8`

## string_xrefs

- `0x18002a88a`: `security\WeakHashAlgUpgrade`
- `0x18002a8b1`: `security\DefaultHashAlgorithm`
- `0x18002a8c4`: `security\WeakHashAlgorithms`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 ReadHashConfiguration()
{
  __int64 v0; // rdx
  __int64 v1; // r8
  __int64 v2; // r9
  unsigned int v3; // ebx
  unsigned int *v4; // rax
  __int64 v5; // rcx
  int v7; // [rsp+30h] [rbp-30h] BYREF
  const wchar_t *v8; // [rsp+38h] [rbp-28h]
  __int64 v9; // [rsp+40h] [rbp-20h]
  int v10; // [rsp+48h] [rbp-18h]
  __int64 v11; // [rsp+50h] [rbp-10h]
  unsigned int v12; // [rsp+70h] [rbp+10h] BYREF
  __int64 v13; // [rsp+78h] [rbp+18h] BYREF

  LODWORD(v13) = 4;
  v12 = 4;
  GetFalconKeyValue(
    L"security\\WeakHashAlgUpgrade",
    (unsigned int *)&v13,
    &g_UpgradeHashAlg,
    &v12,
    &g_DefaultUpgradeHashAlg);
  GetFalconKeyValue(L"security\\DefaultHashAlgorithm", (unsigned int *)&v13, &g_HashAlg, &v12, &g_DefaultHashAlg);
  v7 = 0;
  v8 = L"security\\WeakHashAlgorithms";
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v13 = 0;
  v12 = 0;
  if ( (unsigned __int8)InternalQueryValueList<unsigned long>(&v7, &v13, &v12) )
  {
    v3 = v12;
    g_cWeakHashAlg = v12;
    v4 = (unsigned int *)MmAllocate(saturated_mul(v12, 4u));
    g_aWeakHashAlg = v4;
    v2 = 0;
    if ( v3 )
    {
      v5 = v13;
      do
      {
        v1 = (int)v2;
        v0 = *(unsigned int *)(v5 + 48LL * (int)v2 + 40);
        v4[(int)v2] = v0;
        v2 = (unsigned int)(v2 + 1);
      }
      while ( (unsigned int)v2 < v3 );
    }
  }
  else
  {
    g_cWeakHashAlg = 5;
    g_aWeakHashAlg = (unsigned int *)&g_DefaultWeakHashAlg;
  }
  return AP<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,unsigned long>>::~AP<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,unsigned long>>(
           &v13,
           v0,
           v1,
           v2);
}

```

## disassembly

```asm
0x18002a854  mov     [rsp-8+arg_10], rbx
0x18002a859  push    rbp
0x18002a85a  mov     rbp, rsp
0x18002a85d  sub     rsp, 60h
0x18002a861  mov     dword ptr [rbp+arg_8], 4
0x18002a868  mov     [rbp+arg_0], 4
0x18002a86f  lea     rax, ?g_DefaultUpgradeHashAlg@@3IA; uint g_DefaultUpgradeHashAlg
0x18002a876  mov     [rsp+60h+var_40], rax; wchar_t *
0x18002a87b  lea     r9, [rbp+arg_0]; unsigned int *
0x18002a87f  lea     r8, ?g_UpgradeHashAlg@@3IA; void *
0x18002a886  lea     rdx, [rbp+arg_8]; unsigned int *
0x18002a88a  lea     rcx, aSecurityWeakha; "security\\WeakHashAlgUpgrade"
0x18002a891  call    ?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18002a896  lea     rax, ?g_DefaultHashAlg@@3IA; uint g_DefaultHashAlg
0x18002a89d  mov     [rsp+60h+var_40], rax; wchar_t *
0x18002a8a2  lea     r9, [rbp+arg_0]; unsigned int *
0x18002a8a6  lea     r8, ?g_HashAlg@@3IA; void *
0x18002a8ad  lea     rdx, [rbp+arg_8]; unsigned int *
0x18002a8b1  lea     rcx, aSecurityDefaul; "security\\DefaultHashAlgorithm"
0x18002a8b8  call    ?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18002a8bd  mov     [rbp+var_30], 0
0x18002a8c4  lea     rax, aSecurityWeakha_0; "security\\WeakHashAlgorithms"
0x18002a8cb  mov     [rbp+var_28], rax
0x18002a8cf  mov     [rbp+var_20], 0
0x18002a8d7  mov     [rbp+var_18], 0
0x18002a8de  mov     [rbp+var_10], 0
0x18002a8e6  mov     [rbp+arg_8], 0
0x18002a8ee  mov     [rbp+arg_0], 0
0x18002a8f5  lea     r8, [rbp+arg_0]
0x18002a8f9  lea     rdx, [rbp+arg_8]
0x18002a8fd  lea     rcx, [rbp+var_30]
0x18002a901  call    ??$InternalQueryValueList@K@@YA_NAEAVRegEntry@@PEAPEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@K@std@@PEAK@Z; InternalQueryValueList<ulong>(RegEntry &,std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,ulong> * *,ulong *)
0x18002a906  test    al, al
0x18002a908  jz      short loc_18002A95C
0x18002a90a  mov     ebx, [rbp+arg_0]
0x18002a90d  mov     cs:?g_cWeakHashAlg@@3KA, ebx; ulong g_cWeakHashAlg
0x18002a913  mov     eax, 4
0x18002a918  mul     rbx
0x18002a91b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002a922  cmovb   rax, rcx
0x18002a926  mov     rcx, rax; unsigned __int64
0x18002a929  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18002a92e  mov     cs:?g_aWeakHashAlg@@3PEAIEA, rax; uint * g_aWeakHashAlg
0x18002a935  xor     r9d, r9d
0x18002a938  test    ebx, ebx
0x18002a93a  jz      short loc_18002A974
0x18002a93c  mov     rcx, [rbp+arg_8]
0x18002a940  movsxd  r8, r9d
0x18002a943  lea     rdx, [r8+r8*2]
0x18002a947  add     rdx, rdx
0x18002a94a  mov     edx, [rcx+rdx*8+28h]
0x18002a94e  mov     [rax+r8*4], edx
0x18002a952  inc     r9d
0x18002a955  cmp     r9d, ebx
0x18002a958  jb      short loc_18002A940
0x18002a95a  jmp     short loc_18002A974
0x18002a95c  mov     cs:?g_cWeakHashAlg@@3KA, 5; ulong g_cWeakHashAlg
0x18002a966  lea     rax, ?g_DefaultWeakHashAlg@@3PAIA; uint near * g_DefaultWeakHashAlg
0x18002a96d  mov     cs:?g_aWeakHashAlg@@3PEAIEA, rax; uint * g_aWeakHashAlg
0x18002a974  lea     rcx, [rbp+arg_8]
0x18002a978  call    ??1?$AP@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@K@std@@@@QEAA@XZ; AP<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,ulong>>::~AP<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,ulong>>(void)
0x18002a97d  mov     rbx, [rsp+60h+arg_10]
0x18002a985  add     rsp, 60h
0x18002a989  pop     rbp
0x18002a98a  retn
```
