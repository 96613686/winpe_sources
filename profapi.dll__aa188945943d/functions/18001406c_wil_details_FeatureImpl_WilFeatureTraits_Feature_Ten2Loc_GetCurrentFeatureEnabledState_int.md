# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001406c`
- end: `0x180014153`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `231`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800135e8`

## callees

- `0x180013368`
- `0x18001406c`
- `0x1800157f4`
- `0x180015a78`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  __int64 v7; // rcx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // si
  wil::details *v13; // rcx
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF

  v15 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419CA, (unsigned int)a2, a3, a4);
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
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    LOBYTE(v7) = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_18;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(v7) )
  {
    v13 = (wil::details *)*(unsigned int *)Feature_Standalone_26_02_NonSec__descriptor;
    if ( ((unsigned __int8)v13 & 4) == 0 )
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
        v13,
        &v15);
    LOBYTE(v7) = 1;
  }
  else
  {
    LOBYTE(v7) = 0;
  }
  if ( v12 && !(_BYTE)v7 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_18:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18001406c  mov     [rsp+arg_0], rcx
0x180014071  push    rbx
0x180014072  push    rbp
0x180014073  push    rsi
0x180014074  push    rdi
0x180014075  sub     rsp, 28h
0x180014079  mov     ecx, 38419CAh; this
0x18001407e  mov     rbx, rdx
0x180014081  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180014086  mov     edx, eax
0x180014088  mov     qword ptr [rbx], 0
0x18001408f  and     edx, 0FFFFFF3Fh
0x180014095  mov     ecx, eax
0x180014097  and     eax, 80h
0x18001409c  mov     r8d, edx
0x18001409f  and     r8d, 3
0x1800140a3  mov     ebp, 40h ; '@'
0x1800140a8  shl     r8d, 2
0x1800140ac  and     ecx, ebp
0x1800140ae  or      r8d, ecx
0x1800140b1  shl     r8d, 2
0x1800140b5  or      r8d, eax
0x1800140b8  shl     r8d, 3
0x1800140bc  test    edx, edx
0x1800140be  jnz     short loc_1800140C6
0x1800140c0  mov     ecx, ebp
0x1800140c2  mov     edx, ebp
0x1800140c4  jmp     short loc_1800140D0
0x1800140c6  xor     ecx, ecx
0x1800140c8  cmp     edx, 2
0x1800140cb  cmovz   ecx, ebp
0x1800140ce  mov     edx, ecx
0x1800140d0  mov     eax, r8d
0x1800140d3  mov     edi, 1
0x1800140d8  or      eax, edx
0x1800140da  or      r8d, ecx
0x1800140dd  mov     [rbx], eax
0x1800140df  bt      r8d, 0Ah
0x1800140e4  jnb     short loc_1800140F4
0x1800140e6  cmp     r8d, 800h
0x1800140ed  jb      short loc_1800140F4
0x1800140ef  mov     sil, dil
0x1800140f2  jmp     short loc_1800140FE
0x1800140f4  xor     sil, sil
0x1800140f7  xor     cl, cl
0x1800140f9  test    bpl, r8b
0x1800140fc  jz      short loc_180014133
0x1800140fe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x180014103  test    al, al
0x180014105  jz      short loc_180014124
0x180014107  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18001410e  mov     ecx, [rax]
0x180014110  test    cl, 4
0x180014113  jnz     short loc_18001411F
0x180014115  lea     rdx, [rsp+48h+arg_0]
0x18001411a  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x18001411f  mov     cl, dil
0x180014122  jmp     short loc_180014126
0x180014124  xor     cl, cl
0x180014126  test    sil, sil
0x180014129  jz      short loc_180014133
0x18001412b  test    cl, cl
0x18001412d  jnz     short loc_180014133
0x18001412f  btr     dword ptr [rbx], 0Ah
0x180014133  mov     eax, [rbx]
0x180014135  test    bpl, al
0x180014138  jz      short loc_18001413E
0x18001413a  test    cl, cl
0x18001413c  jnz     short loc_180014140
0x18001413e  xor     edi, edi
0x180014140  and     eax, 0FFFFFFFEh
0x180014143  or      eax, edi
0x180014145  mov     [rbx], eax
0x180014147  mov     rax, rbx
0x18001414a  add     rsp, 28h
0x18001414e  pop     rdi
0x18001414f  pop     rsi
0x180014150  pop     rbp
0x180014151  pop     rbx
0x180014152  retn
```
