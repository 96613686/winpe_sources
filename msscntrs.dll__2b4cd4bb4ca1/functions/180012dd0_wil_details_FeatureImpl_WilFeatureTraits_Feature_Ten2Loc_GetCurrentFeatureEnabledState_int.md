# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180012dd0`
- end: `0x180012f39`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800127f0`

## callees

- `0x18000d170`
- `0x18000fa2c`
- `0x180012dd0`
- `0x180013814`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(
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
    v4 = v2(58989002, 3);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_180022110, 58599550, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x180012dd0  mov     [rsp+arg_10], rbx
0x180012dd5  mov     [rsp+arg_0], rcx
0x180012dda  push    rbp
0x180012ddb  push    rsi
0x180012ddc  push    rdi
0x180012ddd  sub     rsp, 40h
0x180012de1  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012de8  mov     rbx, rdx
0x180012deb  test    rax, rax
0x180012dee  jz      short loc_180012E03
0x180012df0  mov     edx, 3
0x180012df5  mov     ecx, 38419CAh
0x180012dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dff  mov     edx, eax
0x180012e01  jmp     short loc_180012E11
0x180012e03  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012e0a  test    rax, rax
0x180012e0d  jnz     short loc_180012DF0
0x180012e0f  xor     edx, edx
0x180012e11  mov     r8d, edx
0x180012e14  mov     qword ptr [rbx], 0
0x180012e1b  and     r8d, 0FFFFFF3Fh
0x180012e22  mov     eax, edx
0x180012e24  and     edx, 80h
0x180012e2a  mov     ecx, r8d
0x180012e2d  and     ecx, 3
0x180012e30  mov     ebp, 40h ; '@'
0x180012e35  shl     ecx, 2
0x180012e38  and     eax, ebp
0x180012e3a  or      ecx, eax
0x180012e3c  shl     ecx, 2
0x180012e3f  or      ecx, edx
0x180012e41  shl     ecx, 3
0x180012e44  test    r8d, r8d
0x180012e47  jnz     short loc_180012E50
0x180012e49  mov     edx, ebp
0x180012e4b  mov     r8d, ebp
0x180012e4e  jmp     short loc_180012E5C
0x180012e50  xor     edx, edx
0x180012e52  cmp     r8d, 2
0x180012e56  cmovz   edx, ebp
0x180012e59  mov     r8d, edx
0x180012e5c  mov     eax, ecx
0x180012e5e  mov     edi, 1
0x180012e63  or      eax, r8d
0x180012e66  or      ecx, edx
0x180012e68  mov     [rbx], eax
0x180012e6a  bt      ecx, 0Ah
0x180012e6e  jnb     short loc_180012E7D
0x180012e70  cmp     ecx, 800h
0x180012e76  jb      short loc_180012E7D
0x180012e78  mov     sil, dil
0x180012e7b  jmp     short loc_180012E8B
0x180012e7d  xor     sil, sil
0x180012e80  xor     dl, dl
0x180012e82  test    bpl, cl
0x180012e85  jz      loc_180012F15
0x180012e8b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x180012e92  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x180012e97  test    al, al
0x180012e99  jz      short loc_180012F06
0x180012e9b  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180012ea2  mov     r8d, [rax]
0x180012ea5  test    r8b, 4
0x180012ea9  jnz     short loc_180012EC0
0x180012eab  lea     rdx, [rsp+58h+arg_8]
0x180012eb0  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x180012eb5  mov     rcx, [rax]
0x180012eb8  mov     [rsp+58h+arg_8], rcx
0x180012ebd  mov     r8d, ecx
0x180012ec0  xor     eax, eax
0x180012ec2  mov     word ptr [rsp+58h+arg_0+4], 3
0x180012ec9  mov     r9d, r8d
0x180012ecc  mov     [rsp+58h+var_28], eax
0x180012ed0  mov     dword ptr [rsp+58h+arg_0], eax
0x180012ed4  lea     rcx, qword_180022110
0x180012edb  shr     r9d, 0Bh
0x180012edf  lea     rax, [rsp+58h+arg_0]
0x180012ee4  shr     r8d, 0Ah
0x180012ee8  and     r9d, edi
0x180012eeb  and     r8d, edi
0x180012eee  mov     [rsp+58h+var_30], edi
0x180012ef2  mov     edx, 37E287Eh
0x180012ef7  mov     [rsp+58h+var_38], rax
0x180012efc  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180012f01  mov     dl, dil
0x180012f04  jmp     short loc_180012F08
0x180012f06  xor     dl, dl
0x180012f08  test    sil, sil
0x180012f0b  jz      short loc_180012F15
0x180012f0d  test    dl, dl
0x180012f0f  jnz     short loc_180012F15
0x180012f11  btr     dword ptr [rbx], 0Ah
0x180012f15  mov     eax, [rbx]
0x180012f17  test    bpl, al
0x180012f1a  jz      short loc_180012F20
0x180012f1c  test    dl, dl
0x180012f1e  jnz     short loc_180012F22
0x180012f20  xor     edi, edi
0x180012f22  and     eax, 0FFFFFFFEh
0x180012f25  or      eax, edi
0x180012f27  mov     [rbx], eax
0x180012f29  mov     rax, rbx
0x180012f2c  mov     rbx, [rsp+58h+arg_10]
0x180012f31  add     rsp, 40h
0x180012f35  pop     rdi
0x180012f36  pop     rsi
0x180012f37  pop     rbp
0x180012f38  retn
```
