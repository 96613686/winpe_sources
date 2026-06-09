# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180012f48`
- end: `0x1800130ec`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `420`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180012b88`

## callees

- `0x180006184`
- `0x180009670`
- `0x18001256c`
- `0x180012f48`
- `0x180015010`

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
    wil::details::ReportUsageToService(&qword_18001EA58, 57048226, (v13 >> 10) & 1, (v13 >> 11) & 1, &v17, 1, 0);
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
    wil::details::ReportUsageToService(&qword_180022F98, 45036792, (v15 >> 10) & 1, (v15 >> 11) & 1, &v17, 1, 0);
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
0x180012f48  mov     [rsp-18h+arg_10], rbx
0x180012f4d  mov     [rsp-18h+arg_0], rcx
0x180012f52  push    rbp
0x180012f53  push    rdi
0x180012f54  push    r14
0x180012f56  mov     rbp, rsp
0x180012f59  sub     rsp, 40h
0x180012f5d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012f64  mov     rdi, rdx
0x180012f67  test    rax, rax
0x180012f6a  jz      short loc_180012F7F
0x180012f6c  mov     edx, 3
0x180012f71  mov     ecx, 3667CA7h
0x180012f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f7b  mov     edx, eax
0x180012f7d  jmp     short loc_180012F8D
0x180012f7f  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012f86  test    rax, rax
0x180012f89  jnz     short loc_180012F6C
0x180012f8b  xor     edx, edx
0x180012f8d  mov     r8d, edx
0x180012f90  mov     qword ptr [rdi], 0
0x180012f97  and     r8d, 0FFFFFF3Fh
0x180012f9e  mov     eax, edx
0x180012fa0  and     edx, 80h
0x180012fa6  mov     ecx, r8d
0x180012fa9  and     ecx, 3
0x180012fac  mov     r14d, 40h ; '@'
0x180012fb2  shl     ecx, 2
0x180012fb5  and     eax, r14d
0x180012fb8  or      ecx, eax
0x180012fba  shl     ecx, 2
0x180012fbd  or      ecx, edx
0x180012fbf  shl     ecx, 3
0x180012fc2  test    r8d, r8d
0x180012fc5  jnz     short loc_180012FCF
0x180012fc7  mov     edx, r14d
0x180012fca  mov     r8d, r14d
0x180012fcd  jmp     short loc_180012FDC
0x180012fcf  xor     edx, edx
0x180012fd1  cmp     r8d, 2
0x180012fd5  cmovz   edx, r14d
0x180012fd9  mov     r8d, edx
0x180012fdc  mov     eax, ecx
0x180012fde  mov     ebx, 1
0x180012fe3  or      eax, r8d
0x180012fe6  or      ecx, edx
0x180012fe8  mov     [rdi], eax
0x180012fea  bt      ecx, 0Ah
0x180012fee  jnb     short loc_180012FF8
0x180012ff0  cmp     ecx, 800h
0x180012ff6  jnb     short loc_180013003
0x180012ff8  xor     dl, dl
0x180012ffa  test    r14b, cl
0x180012ffd  jz      loc_1800130C7
0x180013003  mov     rax, cs:Feature_ValLabTest__descriptor
0x18001300a  mov     r8d, [rax]
0x18001300d  test    r8b, 4
0x180013011  jnz     short loc_180013026
0x180013013  lea     rdx, [rbp+arg_8]
0x180013017  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x18001301c  mov     rcx, [rax]
0x18001301f  mov     [rbp+arg_8], rcx
0x180013023  mov     r8d, ecx
0x180013026  xor     eax, eax
0x180013028  mov     word ptr [rbp+arg_0+4], 3
0x18001302e  mov     r9d, r8d
0x180013031  mov     [rsp+40h+var_10], eax
0x180013035  mov     dword ptr [rbp+arg_0], eax
0x180013038  lea     rcx, qword_18001EA58
0x18001303f  shr     r9d, 0Bh
0x180013043  lea     rax, [rbp+arg_0]
0x180013047  shr     r8d, 0Ah
0x18001304b  and     r9d, ebx
0x18001304e  and     r8d, ebx
0x180013051  mov     [rsp+40h+var_18], ebx
0x180013055  mov     edx, 3667CA2h
0x18001305a  mov     [rsp+40h+var_20], rax
0x18001305f  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180013064  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18001306b  mov     r8d, [rax]
0x18001306e  test    r8b, 4
0x180013072  jnz     short loc_180013087
0x180013074  lea     rdx, [rbp+arg_8]
0x180013078  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x18001307d  mov     rcx, [rax]
0x180013080  mov     [rbp+arg_8], rcx
0x180013084  mov     r8d, ecx
0x180013087  xor     eax, eax
0x180013089  mov     word ptr [rbp+arg_0+4], 3
0x18001308f  mov     r9d, r8d
0x180013092  mov     [rsp+40h+var_10], eax
0x180013096  mov     dword ptr [rbp+arg_0], eax
0x180013099  lea     rcx, qword_180022F98
0x1800130a0  shr     r9d, 0Bh
0x1800130a4  lea     rax, [rbp+arg_0]
0x1800130a8  shr     r8d, 0Ah
0x1800130ac  and     r9d, ebx
0x1800130af  and     r8d, ebx
0x1800130b2  mov     [rsp+40h+var_18], ebx
0x1800130b6  mov     edx, 2AF34F8h
0x1800130bb  mov     [rsp+40h+var_20], rax
0x1800130c0  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800130c5  mov     dl, bl
0x1800130c7  mov     eax, [rdi]
0x1800130c9  test    r14b, al
0x1800130cc  jz      short loc_1800130D2
0x1800130ce  test    dl, dl
0x1800130d0  jnz     short loc_1800130D4
0x1800130d2  xor     ebx, ebx
0x1800130d4  and     eax, 0FFFFFFFEh
0x1800130d7  or      eax, ebx
0x1800130d9  mov     rbx, [rsp+40h+arg_10]
0x1800130de  mov     [rdi], eax
0x1800130e0  mov     rax, rdi
0x1800130e3  add     rsp, 40h
0x1800130e7  pop     r14
0x1800130e9  pop     rdi
0x1800130ea  pop     rbp
0x1800130eb  retn
```
