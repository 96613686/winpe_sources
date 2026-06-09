# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180011e50`
- end: `0x180011fd4`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180011b3c`

## callees

- `0x1800119d8`
- `0x180011c24`
- `0x180011e50`
- `0x1800121d0`
- `0x180012420`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  __int64 v7; // rcx
  int v8; // edx
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  __int64 v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+20h] BYREF
  __int64 v17; // [rsp+68h] [rbp+28h] BYREF

  v16 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CA7, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( (FeatureEnabledState & 0xFFFFFF3F) == 2 )
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
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 || (LOBYTE(v7) = 0, (v11 & 0x40) != 0) )
  {
    v12 = *(_DWORD *)Feature_ValLabTest__descriptor;
    if ( (*(_DWORD *)Feature_ValLabTest__descriptor & 4) == 0 )
    {
      v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
                         v7,
                         &v17);
      v12 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_18001F840, 57048226, (v12 >> 10) & 1, (v12 >> 11) & 1, &v16, 1, 0);
    v14 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor & 4) == 0 )
    {
      v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
                         v13,
                         &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_18001F830, 45036792, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
    LOBYTE(v7) = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180011e50  mov     [rsp-18h+arg_10], rbx
0x180011e55  mov     [rsp-18h+arg_0], rcx
0x180011e5a  push    rbp
0x180011e5b  push    rdi
0x180011e5c  push    r14
0x180011e5e  mov     rbp, rsp
0x180011e61  sub     rsp, 40h
0x180011e65  mov     ecx, 3667CA7h; this
0x180011e6a  mov     rdi, rdx
0x180011e6d  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180011e72  mov     edx, eax
0x180011e74  mov     qword ptr [rdi], 0
0x180011e7b  and     edx, 0FFFFFF3Fh
0x180011e81  mov     ecx, eax
0x180011e83  and     eax, 80h
0x180011e88  mov     r8d, edx
0x180011e8b  and     r8d, 3
0x180011e8f  mov     r14d, 40h ; '@'
0x180011e95  shl     r8d, 2
0x180011e99  and     ecx, r14d
0x180011e9c  or      r8d, ecx
0x180011e9f  shl     r8d, 2
0x180011ea3  or      r8d, eax
0x180011ea6  shl     r8d, 3
0x180011eaa  test    edx, edx
0x180011eac  jnz     short loc_180011EB6
0x180011eae  mov     ecx, r14d
0x180011eb1  mov     edx, r14d
0x180011eb4  jmp     short loc_180011EC1
0x180011eb6  xor     ecx, ecx
0x180011eb8  cmp     edx, 2
0x180011ebb  cmovz   ecx, r14d
0x180011ebf  mov     edx, ecx
0x180011ec1  mov     eax, r8d
0x180011ec4  mov     ebx, 1
0x180011ec9  or      eax, edx
0x180011ecb  or      r8d, ecx
0x180011ece  mov     [rdi], eax
0x180011ed0  bt      r8d, 0Ah
0x180011ed5  jnb     short loc_180011EE0
0x180011ed7  cmp     r8d, 800h
0x180011ede  jnb     short loc_180011EEB
0x180011ee0  xor     cl, cl
0x180011ee2  test    r14b, r8b
0x180011ee5  jz      loc_180011FAF
0x180011eeb  mov     rax, cs:Feature_ValLabTest__descriptor
0x180011ef2  mov     r8d, [rax]
0x180011ef5  test    r8b, 4
0x180011ef9  jnz     short loc_180011F0E
0x180011efb  lea     rdx, [rbp+arg_8]
0x180011eff  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x180011f04  mov     rcx, [rax]
0x180011f07  mov     [rbp+arg_8], rcx
0x180011f0b  mov     r8d, ecx
0x180011f0e  xor     eax, eax
0x180011f10  mov     word ptr [rbp+arg_0+4], 3
0x180011f16  mov     r9d, r8d
0x180011f19  mov     [rsp+40h+var_10], eax
0x180011f1d  mov     dword ptr [rbp+arg_0], eax
0x180011f20  lea     rcx, qword_18001F840
0x180011f27  shr     r9d, 0Bh
0x180011f2b  lea     rax, [rbp+arg_0]
0x180011f2f  shr     r8d, 0Ah
0x180011f33  and     r9d, ebx
0x180011f36  and     r8d, ebx
0x180011f39  mov     [rsp+40h+var_18], ebx
0x180011f3d  mov     edx, 3667CA2h
0x180011f42  mov     [rsp+40h+var_20], rax
0x180011f47  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180011f4c  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180011f53  mov     r8d, [rax]
0x180011f56  test    r8b, 4
0x180011f5a  jnz     short loc_180011F6F
0x180011f5c  lea     rdx, [rbp+arg_8]
0x180011f60  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x180011f65  mov     rcx, [rax]
0x180011f68  mov     [rbp+arg_8], rcx
0x180011f6c  mov     r8d, ecx
0x180011f6f  xor     eax, eax
0x180011f71  mov     word ptr [rbp+arg_0+4], 3
0x180011f77  mov     r9d, r8d
0x180011f7a  mov     [rsp+40h+var_10], eax
0x180011f7e  mov     dword ptr [rbp+arg_0], eax
0x180011f81  lea     rcx, qword_18001F830
0x180011f88  shr     r9d, 0Bh
0x180011f8c  lea     rax, [rbp+arg_0]
0x180011f90  shr     r8d, 0Ah
0x180011f94  and     r9d, ebx
0x180011f97  and     r8d, ebx
0x180011f9a  mov     [rsp+40h+var_18], ebx
0x180011f9e  mov     edx, 2AF34F8h
0x180011fa3  mov     [rsp+40h+var_20], rax
0x180011fa8  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180011fad  mov     cl, bl
0x180011faf  mov     eax, [rdi]
0x180011fb1  test    r14b, al
0x180011fb4  jz      short loc_180011FBA
0x180011fb6  test    cl, cl
0x180011fb8  jnz     short loc_180011FBC
0x180011fba  xor     ebx, ebx
0x180011fbc  and     eax, 0FFFFFFFEh
0x180011fbf  or      eax, ebx
0x180011fc1  mov     rbx, [rsp+40h+arg_10]
0x180011fc6  mov     [rdi], eax
0x180011fc8  mov     rax, rdi
0x180011fcb  add     rsp, 40h
0x180011fcf  pop     r14
0x180011fd1  pop     rdi
0x180011fd2  pop     rbp
0x180011fd3  retn
```
