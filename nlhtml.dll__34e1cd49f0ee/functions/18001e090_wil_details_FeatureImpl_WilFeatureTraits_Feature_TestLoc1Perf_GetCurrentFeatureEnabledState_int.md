# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001e090`
- end: `0x18001e16e`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001d79c`

## callees

- `0x18001beec`
- `0x18001e090`
- `0x18001ea14`
- `0x18001ef8c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  int v7; // ecx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // si
  char v13; // cl

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419AC, (unsigned int)a2, a3, a4);
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
    v13 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_16;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl'::`2'::impl);
    v13 = 1;
  }
  else
  {
    v13 = 0;
  }
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_16:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18001e090  push    rbx
0x18001e092  push    rbp
0x18001e093  push    rsi
0x18001e094  push    rdi
0x18001e095  sub     rsp, 28h
0x18001e099  mov     ecx, 38419ACh; this
0x18001e09e  mov     rbx, rdx
0x18001e0a1  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001e0a6  mov     edx, eax
0x18001e0a8  mov     qword ptr [rbx], 0
0x18001e0af  and     edx, 0FFFFFF3Fh
0x18001e0b5  mov     ecx, eax
0x18001e0b7  and     eax, 80h
0x18001e0bc  mov     r8d, edx
0x18001e0bf  and     r8d, 3
0x18001e0c3  mov     ebp, 40h ; '@'
0x18001e0c8  shl     r8d, 2
0x18001e0cc  and     ecx, ebp
0x18001e0ce  or      r8d, ecx
0x18001e0d1  shl     r8d, 2
0x18001e0d5  or      r8d, eax
0x18001e0d8  shl     r8d, 3
0x18001e0dc  test    edx, edx
0x18001e0de  jnz     short loc_18001E0E6
0x18001e0e0  mov     ecx, ebp
0x18001e0e2  mov     edx, ebp
0x18001e0e4  jmp     short loc_18001E0F0
0x18001e0e6  xor     ecx, ecx
0x18001e0e8  cmp     edx, 2
0x18001e0eb  cmovz   ecx, ebp
0x18001e0ee  mov     edx, ecx
0x18001e0f0  mov     eax, r8d
0x18001e0f3  mov     edi, 1
0x18001e0f8  or      eax, edx
0x18001e0fa  or      r8d, ecx
0x18001e0fd  mov     [rbx], eax
0x18001e0ff  bt      r8d, 0Ah
0x18001e104  jnb     short loc_18001E114
0x18001e106  cmp     r8d, 800h
0x18001e10d  jb      short loc_18001E114
0x18001e10f  mov     sil, dil
0x18001e112  jmp     short loc_18001E11E
0x18001e114  xor     sil, sil
0x18001e117  xor     cl, cl
0x18001e119  test    bpl, r8b
0x18001e11c  jz      short loc_18001E14E
0x18001e11e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x18001e125  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x18001e12a  test    al, al
0x18001e12c  jz      short loc_18001E13F
0x18001e12e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl(void)'::`2'::impl
0x18001e135  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001e13a  mov     cl, dil
0x18001e13d  jmp     short loc_18001E141
0x18001e13f  xor     cl, cl
0x18001e141  test    sil, sil
0x18001e144  jz      short loc_18001E14E
0x18001e146  test    cl, cl
0x18001e148  jnz     short loc_18001E14E
0x18001e14a  btr     dword ptr [rbx], 0Ah
0x18001e14e  mov     eax, [rbx]
0x18001e150  test    bpl, al
0x18001e153  jz      short loc_18001E159
0x18001e155  test    cl, cl
0x18001e157  jnz     short loc_18001E15B
0x18001e159  xor     edi, edi
0x18001e15b  and     eax, 0FFFFFFFEh
0x18001e15e  or      eax, edi
0x18001e160  mov     [rbx], eax
0x18001e162  mov     rax, rbx
0x18001e165  add     rsp, 28h
0x18001e169  pop     rdi
0x18001e16a  pop     rsi
0x18001e16b  pop     rbp
0x18001e16c  pop     rbx
0x18001e16d  retn
```
