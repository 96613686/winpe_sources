# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180009934`
- end: `0x180009a9d`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180009330`

## callees

- `0x180008ec8`
- `0x180009934`
- `0x180010330`
- `0x180012304`
- `0x180014010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  __int64 v7; // rdx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // ecx
  char v12; // si
  wil::details *v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(57048237, 3);
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
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    LOBYTE(v7) = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_18001DD20, 45036797, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
    LOBYTE(v7) = 1;
  }
  else
  {
    LOBYTE(v7) = 0;
  }
  if ( v12 && !(_BYTE)v7 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_22:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180009934  mov     [rsp+arg_10], rbx
0x180009939  mov     [rsp+arg_0], rcx
0x18000993e  push    rbp
0x18000993f  push    rsi
0x180009940  push    rdi
0x180009941  sub     rsp, 40h
0x180009945  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000994c  mov     rbx, rdx
0x18000994f  test    rax, rax
0x180009952  jz      short loc_180009967
0x180009954  mov     edx, 3
0x180009959  mov     ecx, 3667CADh
0x18000995e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009963  mov     edx, eax
0x180009965  jmp     short loc_180009975
0x180009967  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000996e  test    rax, rax
0x180009971  jnz     short loc_180009954
0x180009973  xor     edx, edx
0x180009975  mov     r8d, edx
0x180009978  mov     qword ptr [rbx], 0
0x18000997f  and     r8d, 0FFFFFF3Fh
0x180009986  mov     eax, edx
0x180009988  and     edx, 80h
0x18000998e  mov     ecx, r8d
0x180009991  and     ecx, 3
0x180009994  mov     ebp, 40h ; '@'
0x180009999  shl     ecx, 2
0x18000999c  and     eax, ebp
0x18000999e  or      ecx, eax
0x1800099a0  shl     ecx, 2
0x1800099a3  or      ecx, edx
0x1800099a5  shl     ecx, 3
0x1800099a8  test    r8d, r8d
0x1800099ab  jnz     short loc_1800099B4
0x1800099ad  mov     edx, ebp
0x1800099af  mov     r8d, ebp
0x1800099b2  jmp     short loc_1800099C0
0x1800099b4  xor     edx, edx
0x1800099b6  cmp     r8d, 2
0x1800099ba  cmovz   edx, ebp
0x1800099bd  mov     r8d, edx
0x1800099c0  mov     eax, ecx
0x1800099c2  mov     edi, 1
0x1800099c7  or      eax, r8d
0x1800099ca  or      ecx, edx
0x1800099cc  mov     [rbx], eax
0x1800099ce  bt      ecx, 0Ah
0x1800099d2  jnb     short loc_1800099E1
0x1800099d4  cmp     ecx, 800h
0x1800099da  jb      short loc_1800099E1
0x1800099dc  mov     sil, dil
0x1800099df  jmp     short loc_1800099EF
0x1800099e1  xor     sil, sil
0x1800099e4  xor     dl, dl
0x1800099e6  test    bpl, cl
0x1800099e9  jz      loc_180009A79
0x1800099ef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x1800099f6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x1800099fb  test    al, al
0x1800099fd  jz      short loc_180009A6A
0x1800099ff  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180009a06  mov     r8d, [rax]
0x180009a09  test    r8b, 4
0x180009a0d  jnz     short loc_180009A24
0x180009a0f  lea     rdx, [rsp+58h+arg_8]
0x180009a14  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x180009a19  mov     rcx, [rax]
0x180009a1c  mov     [rsp+58h+arg_8], rcx
0x180009a21  mov     r8d, ecx
0x180009a24  xor     eax, eax
0x180009a26  mov     word ptr [rsp+58h+arg_0+4], 3
0x180009a2d  mov     r9d, r8d
0x180009a30  mov     [rsp+58h+var_28], eax
0x180009a34  mov     dword ptr [rsp+58h+arg_0], eax
0x180009a38  lea     rcx, qword_18001DD20
0x180009a3f  shr     r9d, 0Bh
0x180009a43  lea     rax, [rsp+58h+arg_0]
0x180009a48  shr     r8d, 0Ah
0x180009a4c  and     r9d, edi
0x180009a4f  and     r8d, edi
0x180009a52  mov     [rsp+58h+var_30], edi
0x180009a56  mov     edx, 2AF34FDh
0x180009a5b  mov     [rsp+58h+var_38], rax
0x180009a60  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180009a65  mov     dl, dil
0x180009a68  jmp     short loc_180009A6C
0x180009a6a  xor     dl, dl
0x180009a6c  test    sil, sil
0x180009a6f  jz      short loc_180009A79
0x180009a71  test    dl, dl
0x180009a73  jnz     short loc_180009A79
0x180009a75  btr     dword ptr [rbx], 0Ah
0x180009a79  mov     eax, [rbx]
0x180009a7b  test    bpl, al
0x180009a7e  jz      short loc_180009A84
0x180009a80  test    dl, dl
0x180009a82  jnz     short loc_180009A86
0x180009a84  xor     edi, edi
0x180009a86  and     eax, 0FFFFFFFEh
0x180009a89  or      eax, edi
0x180009a8b  mov     [rbx], eax
0x180009a8d  mov     rax, rbx
0x180009a90  mov     rbx, [rsp+58h+arg_10]
0x180009a95  add     rsp, 40h
0x180009a99  pop     rdi
0x180009a9a  pop     rsi
0x180009a9b  pop     rbp
0x180009a9c  retn
```
