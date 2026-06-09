# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18002764c`
- end: `0x1800277d1`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `389`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180026d88`

## callees

- `0x1800188c4`
- `0x18002331c`
- `0x180026568`
- `0x180026e68`
- `0x18002764c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // edx
  __int64 v7; // rcx
  int v8; // r8d
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // edx
  unsigned int v12; // r8d
  wil::details *v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+20h] BYREF
  __int64 v17; // [rsp+68h] [rbp+28h] BYREF

  v16 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CA7, 3u, a3, a4);
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
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
               (wil::details *)v7,
               &v17);
      v12 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_18003E430, 57048226, (v12 >> 10) & 1, (v12 >> 11) & 1, &v16, 1, 0);
    v14 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_18003E3E0, 45036792, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x18002764c  mov     [rsp-18h+arg_10], rbx
0x180027651  mov     [rsp-18h+arg_0], rcx
0x180027656  push    rbp
0x180027657  push    rdi
0x180027658  push    r14
0x18002765a  mov     rbp, rsp
0x18002765d  sub     rsp, 40h
0x180027661  mov     rdi, rdx
0x180027664  mov     ecx, 3667CA7h; this
0x180027669  mov     edx, 3; unsigned int
0x18002766e  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180027673  mov     r8d, eax
0x180027676  mov     qword ptr [rdi], 0
0x18002767d  and     r8d, 0FFFFFF3Fh
0x180027684  mov     ecx, eax
0x180027686  and     eax, 80h
0x18002768b  mov     edx, r8d
0x18002768e  and     edx, 3
0x180027691  mov     r14d, 40h ; '@'
0x180027697  shl     edx, 2
0x18002769a  and     ecx, r14d
0x18002769d  or      edx, ecx
0x18002769f  shl     edx, 2
0x1800276a2  or      edx, eax
0x1800276a4  shl     edx, 3
0x1800276a7  test    r8d, r8d
0x1800276aa  jnz     short loc_1800276B4
0x1800276ac  mov     ecx, r14d
0x1800276af  mov     r8d, r14d
0x1800276b2  jmp     short loc_1800276C1
0x1800276b4  xor     ecx, ecx
0x1800276b6  cmp     r8d, 2
0x1800276ba  cmovz   ecx, r14d
0x1800276be  mov     r8d, ecx
0x1800276c1  mov     eax, edx
0x1800276c3  mov     ebx, 1
0x1800276c8  or      eax, r8d
0x1800276cb  or      edx, ecx
0x1800276cd  mov     [rdi], eax
0x1800276cf  bt      edx, 0Ah
0x1800276d3  jnb     short loc_1800276DD
0x1800276d5  cmp     edx, 800h
0x1800276db  jnb     short loc_1800276E8
0x1800276dd  xor     cl, cl
0x1800276df  test    r14b, dl
0x1800276e2  jz      loc_1800277AC
0x1800276e8  mov     rax, cs:Feature_ValLabTest__descriptor
0x1800276ef  mov     r8d, [rax]
0x1800276f2  test    r8b, 4
0x1800276f6  jnz     short loc_18002770B
0x1800276f8  lea     rdx, [rbp+arg_8]
0x1800276fc  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x180027701  mov     rcx, [rax]
0x180027704  mov     [rbp+arg_8], rcx
0x180027708  mov     r8d, ecx
0x18002770b  xor     eax, eax
0x18002770d  mov     word ptr [rbp+arg_0+4], 3
0x180027713  mov     r9d, r8d
0x180027716  mov     [rsp+40h+var_10], eax
0x18002771a  mov     dword ptr [rbp+arg_0], eax
0x18002771d  lea     rcx, qword_18003E430
0x180027724  shr     r9d, 0Bh
0x180027728  lea     rax, [rbp+arg_0]
0x18002772c  shr     r8d, 0Ah
0x180027730  and     r9d, ebx
0x180027733  and     r8d, ebx
0x180027736  mov     [rsp+40h+var_18], ebx
0x18002773a  mov     edx, 3667CA2h
0x18002773f  mov     [rsp+40h+var_20], rax
0x180027744  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180027749  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180027750  mov     r8d, [rax]
0x180027753  test    r8b, 4
0x180027757  jnz     short loc_18002776C
0x180027759  lea     rdx, [rbp+arg_8]
0x18002775d  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x180027762  mov     rcx, [rax]
0x180027765  mov     [rbp+arg_8], rcx
0x180027769  mov     r8d, ecx
0x18002776c  xor     eax, eax
0x18002776e  mov     word ptr [rbp+arg_0+4], 3
0x180027774  mov     r9d, r8d
0x180027777  mov     [rsp+40h+var_10], eax
0x18002777b  mov     dword ptr [rbp+arg_0], eax
0x18002777e  lea     rcx, qword_18003E3E0
0x180027785  shr     r9d, 0Bh
0x180027789  lea     rax, [rbp+arg_0]
0x18002778d  shr     r8d, 0Ah
0x180027791  and     r9d, ebx
0x180027794  and     r8d, ebx
0x180027797  mov     [rsp+40h+var_18], ebx
0x18002779b  mov     edx, 2AF34F8h
0x1800277a0  mov     [rsp+40h+var_20], rax
0x1800277a5  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800277aa  mov     cl, bl
0x1800277ac  mov     eax, [rdi]
0x1800277ae  test    r14b, al
0x1800277b1  jz      short loc_1800277B7
0x1800277b3  test    cl, cl
0x1800277b5  jnz     short loc_1800277B9
0x1800277b7  xor     ebx, ebx
0x1800277b9  and     eax, 0FFFFFFFEh
0x1800277bc  or      eax, ebx
0x1800277be  mov     rbx, [rsp+40h+arg_10]
0x1800277c3  mov     [rdi], eax
0x1800277c5  mov     rax, rdi
0x1800277c8  add     rsp, 40h
0x1800277cc  pop     r14
0x1800277ce  pop     rdi
0x1800277cf  pop     rbp
0x1800277d0  retn
```
