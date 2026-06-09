# VerifyTrust(LoadInfo *)

- ea: `0x180058f90`
- end: `0x1800590b8`
- name: `?VerifyTrust@@YAJPEAULoadInfo@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(struct LoadInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180044c0c`

## callees

- `0x1800161b8`
- `0x180057e0c`
- `0x180058e00`
- `0x180058e8c`
- `0x180058f90`
- `0x180068160`

## import_xrefs

- `ntdll!NtGetCachedSigningLevel` at `0x18005901e`
- `ntdll!NtGetCachedSigningLevel` at `0x18005901e`
- `ntdll!NtSetCachedSigningLevel` at `0x18005905e`
- `ntdll!NtSetCachedSigningLevel` at `0x18005905e`
- `ntdll!NtCompareSigningLevels` at `0x18005903a`
- `ntdll!NtCompareSigningLevels` at `0x18005903a`

## string_xrefs

- `0x180058fd4`: `mincore\com\oleaut32\typelib\tlibapi.cpp`

## pseudocode

```c
int __fastcall VerifyTrust(struct LoadInfo *a1)
{
  int v2; // eax
  int v3; // ebx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  int CachedSigningLevel; // ebx
  int v9; // edi
  int v10; // r8d
  __int64 v11; // rdx
  void *v12; // rdx
  unsigned int v13; // r8d
  int v14; // [rsp+20h] [rbp-20h]
  int v15; // [rsp+20h] [rbp-20h]
  int v16; // [rsp+30h] [rbp-10h] BYREF
  __int64 v17; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  unsigned __int8 v19; // [rsp+68h] [rbp+28h] BYREF
  bool v20; // [rsp+70h] [rbp+30h] BYREF
  char v21; // [rsp+78h] [rbp+38h] BYREF

  v21 = 0;
  v20 = 0;
  v17 = -1;
  v16 = 1;
  v19 = 0;
  v2 = CheckProtectedProcessForHardening(&v20, (struct _PS_PROTECTION *)&v21);
  v3 = v2;
  if ( v2 >= 0 )
  {
    if ( !v20 )
      return 0;
    v5 = *((int *)a1 + 2);
    v17 = v5;
    CachedSigningLevel = NtGetCachedSigningLevel(v5, &v16, &v19, 0, 0, 0);
    if ( CachedSigningLevel < 0
      || (v16 & 0x182) == 0
      || (LOBYTE(v7) = v19, LOBYTE(v6) = 12, v9 = 0, (int)NtCompareSigningLevels(v7, v6) < 0) )
    {
      LOBYTE(v6) = 12;
      CachedSigningLevel = NtSetCachedSigningLevel(2052, v6, &v17, 1, v17);
      v9 = 1;
    }
    LOBYTE(v10) = v21;
    TraceTypeLibVerifyTrust(CachedSigningLevel, *(_QWORD *)a1, v10, v19, v16, v9);
    LOBYTE(v11) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RequireValidatedTypeLibForPp>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_RequireValidatedTypeLibForPp>::GetImpl'::`2'::impl,
      v11);
    if ( CachedSigningLevel < 0 )
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               v12,
               v13,
               (const char *)(unsigned int)CachedSigningLevel,
               v15);
    else
      return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B8,
      (unsigned int)"mincore\\com\\oleaut32\\typelib\\tlibapi.cpp",
      (const char *)(unsigned int)v2,
      v14);
    return v3;
  }
}

```

## disassembly

```asm
0x180058f90  mov     [rsp-18h+arg_0], rbx
0x180058f95  push    rbp
0x180058f96  push    rsi
0x180058f97  push    rdi
0x180058f98  mov     rbp, rsp
0x180058f9b  sub     rsp, 40h
0x180058f9f  mov     rsi, rcx
0x180058fa2  mov     [rbp+arg_18], 0
0x180058fa6  lea     rcx, [rbp+arg_10]; bool *
0x180058faa  mov     [rbp+arg_10], 0
0x180058fae  lea     rdx, [rbp+arg_18]; struct _PS_PROTECTION *
0x180058fb2  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFFh
0x180058fba  mov     [rbp+var_10], 1
0x180058fc1  mov     [rbp+arg_8], 0
0x180058fc5  call    ?CheckProtectedProcessForHardening@@YAJPEA_NPEAU_PS_PROTECTION@@@Z; CheckProtectedProcessForHardening(bool *,_PS_PROTECTION *)
0x180058fca  mov     ebx, eax
0x180058fcc  test    eax, eax
0x180058fce  jns     short loc_180058FEF
0x180058fd0  mov     rcx, [rbp+18h]; this
0x180058fd4  lea     r8, aMincoreComOlea_3; "mincore\\com\\oleaut32\\typelib\\tlibap"...
0x180058fdb  mov     r9d, eax; char *
0x180058fde  mov     edx, 3B8h; void *
0x180058fe3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058fe8  mov     eax, ebx
0x180058fea  jmp     loc_1800590AB
0x180058fef  cmp     [rbp+arg_10], 0
0x180058ff3  jz      loc_1800590A9
0x180058ff9  movsxd  rcx, dword ptr [rsi+8]
0x180058ffd  lea     r8, [rbp+arg_8]
0x180059001  mov     [rsp+40h+var_18], 0
0x18005900a  lea     rdx, [rbp+var_10]
0x18005900e  xor     r9d, r9d
0x180059011  mov     [rbp+var_8], rcx
0x180059015  mov     qword ptr [rsp+40h+var_20], 0
0x18005901e  call    cs:__imp_NtGetCachedSigningLevel
0x180059024  mov     ebx, eax
0x180059026  test    eax, eax
0x180059028  js      short loc_180059044
0x18005902a  test    [rbp+var_10], 182h
0x180059031  jz      short loc_180059044
0x180059033  mov     cl, [rbp+arg_8]
0x180059036  mov     dl, 0Ch
0x180059038  xor     edi, edi
0x18005903a  call    cs:__imp_NtCompareSigningLevels
0x180059040  test    eax, eax
0x180059042  jns     short loc_18005906B
0x180059044  mov     rax, [rbp+var_8]
0x180059048  lea     r8, [rbp+var_8]
0x18005904c  mov     r9d, 1
0x180059052  mov     qword ptr [rsp+40h+var_20], rax
0x180059057  mov     dl, 0Ch
0x180059059  mov     ecx, 804h
0x18005905e  call    cs:__imp_NtSetCachedSigningLevel
0x180059064  mov     ebx, eax
0x180059066  mov     edi, 1
0x18005906b  mov     eax, [rbp+var_10]
0x18005906e  mov     ecx, ebx
0x180059070  movzx   r9d, [rbp+arg_8]
0x180059075  mov     r8b, [rbp+arg_18]
0x180059079  mov     rdx, [rsi]
0x18005907c  mov     dword ptr [rsp+40h+var_18], edi
0x180059080  mov     [rsp+40h+var_20], eax; int
0x180059084  call    TraceTypeLibVerifyTrust
0x180059089  mov     dl, 1
0x18005908b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RequireValidatedTypeLibForPp@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RequireValidatedTypeLibForPp@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RequireValidatedTypeLibForPp> `wil::Feature<__WilFeatureTraits_Feature_RequireValidatedTypeLibForPp>::GetImpl(void)'::`2'::impl
0x180059092  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RequireValidatedTypeLibForPp@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RequireValidatedTypeLibForPp>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180059097  test    ebx, ebx
0x180059099  jns     short loc_1800590A9
0x18005909b  mov     rcx, [rbp+18h]; this
0x18005909f  mov     r9d, ebx; char *
0x1800590a2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800590a7  jmp     short loc_1800590AB
0x1800590a9  xor     eax, eax
0x1800590ab  mov     rbx, [rsp+40h+arg_0]
0x1800590b0  add     rsp, 40h
0x1800590b4  pop     rdi
0x1800590b5  pop     rsi
0x1800590b6  pop     rbp
0x1800590b7  retn
```
