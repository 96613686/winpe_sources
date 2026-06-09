# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180012dd8`
- end: `0x180012f41`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180012aa8`

## callees

- `0x180009670`
- `0x180012854`
- `0x180012dd8`
- `0x180013aa4`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(
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
    v4 = v2(58988972, 3);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_180022F78, 58599532, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x180012dd8  mov     [rsp+arg_10], rbx
0x180012ddd  mov     [rsp+arg_0], rcx
0x180012de2  push    rbp
0x180012de3  push    rsi
0x180012de4  push    rdi
0x180012de5  sub     rsp, 40h
0x180012de9  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012df0  mov     rbx, rdx
0x180012df3  test    rax, rax
0x180012df6  jz      short loc_180012E0B
0x180012df8  mov     edx, 3
0x180012dfd  mov     ecx, 38419ACh
0x180012e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e07  mov     edx, eax
0x180012e09  jmp     short loc_180012E19
0x180012e0b  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012e12  test    rax, rax
0x180012e15  jnz     short loc_180012DF8
0x180012e17  xor     edx, edx
0x180012e19  mov     r8d, edx
0x180012e1c  mov     qword ptr [rbx], 0
0x180012e23  and     r8d, 0FFFFFF3Fh
0x180012e2a  mov     eax, edx
0x180012e2c  and     edx, 80h
0x180012e32  mov     ecx, r8d
0x180012e35  and     ecx, 3
0x180012e38  mov     ebp, 40h ; '@'
0x180012e3d  shl     ecx, 2
0x180012e40  and     eax, ebp
0x180012e42  or      ecx, eax
0x180012e44  shl     ecx, 2
0x180012e47  or      ecx, edx
0x180012e49  shl     ecx, 3
0x180012e4c  test    r8d, r8d
0x180012e4f  jnz     short loc_180012E58
0x180012e51  mov     edx, ebp
0x180012e53  mov     r8d, ebp
0x180012e56  jmp     short loc_180012E64
0x180012e58  xor     edx, edx
0x180012e5a  cmp     r8d, 2
0x180012e5e  cmovz   edx, ebp
0x180012e61  mov     r8d, edx
0x180012e64  mov     eax, ecx
0x180012e66  mov     edi, 1
0x180012e6b  or      eax, r8d
0x180012e6e  or      ecx, edx
0x180012e70  mov     [rbx], eax
0x180012e72  bt      ecx, 0Ah
0x180012e76  jnb     short loc_180012E85
0x180012e78  cmp     ecx, 800h
0x180012e7e  jb      short loc_180012E85
0x180012e80  mov     sil, dil
0x180012e83  jmp     short loc_180012E93
0x180012e85  xor     sil, sil
0x180012e88  xor     dl, dl
0x180012e8a  test    bpl, cl
0x180012e8d  jz      loc_180012F1D
0x180012e93  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x180012e9a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x180012e9f  test    al, al
0x180012ea1  jz      short loc_180012F0E
0x180012ea3  mov     rax, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180012eaa  mov     r8d, [rax]
0x180012ead  test    r8b, 4
0x180012eb1  jnz     short loc_180012EC8
0x180012eb3  lea     rdx, [rsp+58h+arg_8]
0x180012eb8  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x180012ebd  mov     rcx, [rax]
0x180012ec0  mov     [rsp+58h+arg_8], rcx
0x180012ec5  mov     r8d, ecx
0x180012ec8  xor     eax, eax
0x180012eca  mov     word ptr [rsp+58h+arg_0+4], 3
0x180012ed1  mov     r9d, r8d
0x180012ed4  mov     [rsp+58h+var_28], eax
0x180012ed8  mov     dword ptr [rsp+58h+arg_0], eax
0x180012edc  lea     rcx, qword_180022F78
0x180012ee3  shr     r9d, 0Bh
0x180012ee7  lea     rax, [rsp+58h+arg_0]
0x180012eec  shr     r8d, 0Ah
0x180012ef0  and     r9d, edi
0x180012ef3  and     r8d, edi
0x180012ef6  mov     [rsp+58h+var_30], edi
0x180012efa  mov     edx, 37E286Ch
0x180012eff  mov     [rsp+58h+var_38], rax
0x180012f04  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180012f09  mov     dl, dil
0x180012f0c  jmp     short loc_180012F10
0x180012f0e  xor     dl, dl
0x180012f10  test    sil, sil
0x180012f13  jz      short loc_180012F1D
0x180012f15  test    dl, dl
0x180012f17  jnz     short loc_180012F1D
0x180012f19  btr     dword ptr [rbx], 0Ah
0x180012f1d  mov     eax, [rbx]
0x180012f1f  test    bpl, al
0x180012f22  jz      short loc_180012F28
0x180012f24  test    dl, dl
0x180012f26  jnz     short loc_180012F2A
0x180012f28  xor     edi, edi
0x180012f2a  and     eax, 0FFFFFFFEh
0x180012f2d  or      eax, edi
0x180012f2f  mov     [rbx], eax
0x180012f31  mov     rax, rbx
0x180012f34  mov     rbx, [rsp+58h+arg_10]
0x180012f39  add     rsp, 40h
0x180012f3d  pop     rdi
0x180012f3e  pop     rsi
0x180012f3f  pop     rbp
0x180012f40  retn
```
