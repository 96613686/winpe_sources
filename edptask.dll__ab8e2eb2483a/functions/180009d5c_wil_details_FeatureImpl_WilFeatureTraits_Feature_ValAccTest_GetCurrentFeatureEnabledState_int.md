# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180009d5c`
- end: `0x180009f00`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `420`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800095d0`

## callees

- `0x180008d54`
- `0x1800096b0`
- `0x180009d5c`
- `0x180010330`
- `0x180014010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // edx
  int v8; // r8d
  int v9; // ebx
  int v10; // eax
  wil::details *v11; // rcx
  char v12; // dl
  unsigned int v13; // r8d
  wil::details *v14; // rcx
  unsigned int v15; // r8d
  __int64 v17; // [rsp+60h] [rbp+20h] BYREF
  __int64 v18; // [rsp+68h] [rbp+28h] BYREF

  v17 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(57048231, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( v5 == 2 )
      v7 = 64;
    v8 = v7;
  }
  else
  {
    v7 = 64;
    v8 = 64;
  }
  v9 = 1;
  v10 = v8 | v6;
  v11 = (wil::details *)(v7 | (unsigned int)v6);
  *(_DWORD *)a2 = v10;
  if ( ((unsigned __int16)v11 & 0x400) != 0 && (unsigned int)v11 >= 0x800
    || (v12 = 0, ((unsigned __int8)v11 & 0x40) != 0) )
  {
    v13 = *(_DWORD *)Feature_ValLabTest__descriptor;
    if ( (*(_DWORD *)Feature_ValLabTest__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(v11, &v18);
      v13 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_18001DCF0, 57048226, (v13 >> 10) & 1, (v13 >> 11) & 1, &v17, 1, 0);
    v15 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
               v14,
               &v18);
      v15 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_18001DD30, 45036792, (v15 >> 10) & 1, (v15 >> 11) & 1, &v17, 1, 0);
    v12 = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v12 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180009d5c  mov     [rsp-18h+arg_10], rbx
0x180009d61  mov     [rsp-18h+arg_0], rcx
0x180009d66  push    rbp
0x180009d67  push    rdi
0x180009d68  push    r14
0x180009d6a  mov     rbp, rsp
0x180009d6d  sub     rsp, 40h
0x180009d71  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180009d78  mov     rdi, rdx
0x180009d7b  test    rax, rax
0x180009d7e  jz      short loc_180009D93
0x180009d80  mov     edx, 3
0x180009d85  mov     ecx, 3667CA7h
0x180009d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d8f  mov     edx, eax
0x180009d91  jmp     short loc_180009DA1
0x180009d93  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180009d9a  test    rax, rax
0x180009d9d  jnz     short loc_180009D80
0x180009d9f  xor     edx, edx
0x180009da1  mov     r8d, edx
0x180009da4  mov     qword ptr [rdi], 0
0x180009dab  and     r8d, 0FFFFFF3Fh
0x180009db2  mov     eax, edx
0x180009db4  and     edx, 80h
0x180009dba  mov     ecx, r8d
0x180009dbd  and     ecx, 3
0x180009dc0  mov     r14d, 40h ; '@'
0x180009dc6  shl     ecx, 2
0x180009dc9  and     eax, r14d
0x180009dcc  or      ecx, eax
0x180009dce  shl     ecx, 2
0x180009dd1  or      ecx, edx
0x180009dd3  shl     ecx, 3
0x180009dd6  test    r8d, r8d
0x180009dd9  jnz     short loc_180009DE3
0x180009ddb  mov     edx, r14d
0x180009dde  mov     r8d, r14d
0x180009de1  jmp     short loc_180009DF0
0x180009de3  xor     edx, edx
0x180009de5  cmp     r8d, 2
0x180009de9  cmovz   edx, r14d
0x180009ded  mov     r8d, edx
0x180009df0  mov     eax, ecx
0x180009df2  mov     ebx, 1
0x180009df7  or      eax, r8d
0x180009dfa  or      ecx, edx
0x180009dfc  mov     [rdi], eax
0x180009dfe  bt      ecx, 0Ah
0x180009e02  jnb     short loc_180009E0C
0x180009e04  cmp     ecx, 800h
0x180009e0a  jnb     short loc_180009E17
0x180009e0c  xor     dl, dl
0x180009e0e  test    r14b, cl
0x180009e11  jz      loc_180009EDB
0x180009e17  mov     rax, cs:Feature_ValLabTest__descriptor
0x180009e1e  mov     r8d, [rax]
0x180009e21  test    r8b, 4
0x180009e25  jnz     short loc_180009E3A
0x180009e27  lea     rdx, [rbp+arg_8]
0x180009e2b  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x180009e30  mov     rcx, [rax]
0x180009e33  mov     [rbp+arg_8], rcx
0x180009e37  mov     r8d, ecx
0x180009e3a  xor     eax, eax
0x180009e3c  mov     word ptr [rbp+arg_0+4], 3
0x180009e42  mov     r9d, r8d
0x180009e45  mov     [rsp+40h+var_10], eax
0x180009e49  mov     dword ptr [rbp+arg_0], eax
0x180009e4c  lea     rcx, qword_18001DCF0
0x180009e53  shr     r9d, 0Bh
0x180009e57  lea     rax, [rbp+arg_0]
0x180009e5b  shr     r8d, 0Ah
0x180009e5f  and     r9d, ebx
0x180009e62  and     r8d, ebx
0x180009e65  mov     [rsp+40h+var_18], ebx
0x180009e69  mov     edx, 3667CA2h
0x180009e6e  mov     [rsp+40h+var_20], rax
0x180009e73  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180009e78  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180009e7f  mov     r8d, [rax]
0x180009e82  test    r8b, 4
0x180009e86  jnz     short loc_180009E9B
0x180009e88  lea     rdx, [rbp+arg_8]
0x180009e8c  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x180009e91  mov     rcx, [rax]
0x180009e94  mov     [rbp+arg_8], rcx
0x180009e98  mov     r8d, ecx
0x180009e9b  xor     eax, eax
0x180009e9d  mov     word ptr [rbp+arg_0+4], 3
0x180009ea3  mov     r9d, r8d
0x180009ea6  mov     [rsp+40h+var_10], eax
0x180009eaa  mov     dword ptr [rbp+arg_0], eax
0x180009ead  lea     rcx, qword_18001DD30
0x180009eb4  shr     r9d, 0Bh
0x180009eb8  lea     rax, [rbp+arg_0]
0x180009ebc  shr     r8d, 0Ah
0x180009ec0  and     r9d, ebx
0x180009ec3  and     r8d, ebx
0x180009ec6  mov     [rsp+40h+var_18], ebx
0x180009eca  mov     edx, 2AF34F8h
0x180009ecf  mov     [rsp+40h+var_20], rax
0x180009ed4  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180009ed9  mov     dl, bl
0x180009edb  mov     eax, [rdi]
0x180009edd  test    r14b, al
0x180009ee0  jz      short loc_180009EE6
0x180009ee2  test    dl, dl
0x180009ee4  jnz     short loc_180009EE8
0x180009ee6  xor     ebx, ebx
0x180009ee8  and     eax, 0FFFFFFFEh
0x180009eeb  or      eax, ebx
0x180009eed  mov     rbx, [rsp+40h+arg_10]
0x180009ef2  mov     [rdi], eax
0x180009ef4  mov     rax, rdi
0x180009ef7  add     rsp, 40h
0x180009efb  pop     r14
0x180009efd  pop     rdi
0x180009efe  pop     rbp
0x180009eff  retn
```
