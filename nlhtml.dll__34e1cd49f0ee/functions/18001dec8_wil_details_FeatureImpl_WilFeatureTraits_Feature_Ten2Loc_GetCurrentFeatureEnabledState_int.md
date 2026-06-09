# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001dec8`
- end: `0x18001dfa6`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001d5dc`

## callees

- `0x18001beec`
- `0x18001dec8`
- `0x18001ea98`
- `0x18001efc8`

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
  int v7; // ecx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // si
  char v13; // cl

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
    v13 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_16;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetImpl'::`2'::impl);
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
0x18001dec8  push    rbx
0x18001deca  push    rbp
0x18001decb  push    rsi
0x18001decc  push    rdi
0x18001decd  sub     rsp, 28h
0x18001ded1  mov     ecx, 38419CAh; this
0x18001ded6  mov     rbx, rdx
0x18001ded9  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001dede  mov     edx, eax
0x18001dee0  mov     qword ptr [rbx], 0
0x18001dee7  and     edx, 0FFFFFF3Fh
0x18001deed  mov     ecx, eax
0x18001deef  and     eax, 80h
0x18001def4  mov     r8d, edx
0x18001def7  and     r8d, 3
0x18001defb  mov     ebp, 40h ; '@'
0x18001df00  shl     r8d, 2
0x18001df04  and     ecx, ebp
0x18001df06  or      r8d, ecx
0x18001df09  shl     r8d, 2
0x18001df0d  or      r8d, eax
0x18001df10  shl     r8d, 3
0x18001df14  test    edx, edx
0x18001df16  jnz     short loc_18001DF1E
0x18001df18  mov     ecx, ebp
0x18001df1a  mov     edx, ebp
0x18001df1c  jmp     short loc_18001DF28
0x18001df1e  xor     ecx, ecx
0x18001df20  cmp     edx, 2
0x18001df23  cmovz   ecx, ebp
0x18001df26  mov     edx, ecx
0x18001df28  mov     eax, r8d
0x18001df2b  mov     edi, 1
0x18001df30  or      eax, edx
0x18001df32  or      r8d, ecx
0x18001df35  mov     [rbx], eax
0x18001df37  bt      r8d, 0Ah
0x18001df3c  jnb     short loc_18001DF4C
0x18001df3e  cmp     r8d, 800h
0x18001df45  jb      short loc_18001DF4C
0x18001df47  mov     sil, dil
0x18001df4a  jmp     short loc_18001DF56
0x18001df4c  xor     sil, sil
0x18001df4f  xor     cl, cl
0x18001df51  test    bpl, r8b
0x18001df54  jz      short loc_18001DF86
0x18001df56  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x18001df5d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x18001df62  test    al, al
0x18001df64  jz      short loc_18001DF77
0x18001df66  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetImpl(void)'::`2'::impl
0x18001df6d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001df72  mov     cl, dil
0x18001df75  jmp     short loc_18001DF79
0x18001df77  xor     cl, cl
0x18001df79  test    sil, sil
0x18001df7c  jz      short loc_18001DF86
0x18001df7e  test    cl, cl
0x18001df80  jnz     short loc_18001DF86
0x18001df82  btr     dword ptr [rbx], 0Ah
0x18001df86  mov     eax, [rbx]
0x18001df88  test    bpl, al
0x18001df8b  jz      short loc_18001DF91
0x18001df8d  test    cl, cl
0x18001df8f  jnz     short loc_18001DF93
0x18001df91  xor     edi, edi
0x18001df93  and     eax, 0FFFFFFFEh
0x18001df96  or      eax, edi
0x18001df98  mov     [rbx], eax
0x18001df9a  mov     rax, rbx
0x18001df9d  add     rsp, 28h
0x18001dfa1  pop     rdi
0x18001dfa2  pop     rsi
0x18001dfa3  pop     rbp
0x18001dfa4  pop     rbx
0x18001dfa5  retn
```
