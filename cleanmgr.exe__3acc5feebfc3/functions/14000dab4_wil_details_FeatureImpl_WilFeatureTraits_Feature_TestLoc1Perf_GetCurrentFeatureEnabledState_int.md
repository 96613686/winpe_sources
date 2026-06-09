# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14000dab4`
- end: `0x14000db97`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `227`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000d224`

## callees

- `0x140009c64`
- `0x14000dab4`
- `0x14000e5f0`
- `0x14000ec5c`

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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419AC, 3u, a3, a4);
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
0x14000dab4  push    rbx
0x14000dab6  push    rbp
0x14000dab7  push    rsi
0x14000dab8  push    rdi
0x14000dab9  sub     rsp, 28h
0x14000dabd  mov     rbx, rdx
0x14000dac0  mov     ecx, 38419ACh; this
0x14000dac5  mov     edx, 3; unsigned int
0x14000daca  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14000dacf  mov     edx, eax
0x14000dad1  mov     qword ptr [rbx], 0
0x14000dad8  and     edx, 0FFFFFF3Fh
0x14000dade  mov     ecx, eax
0x14000dae0  and     eax, 80h
0x14000dae5  mov     r8d, edx
0x14000dae8  and     r8d, 3
0x14000daec  mov     ebp, 40h ; '@'
0x14000daf1  shl     r8d, 2
0x14000daf5  and     ecx, ebp
0x14000daf7  or      r8d, ecx
0x14000dafa  shl     r8d, 2
0x14000dafe  or      r8d, eax
0x14000db01  shl     r8d, 3
0x14000db05  test    edx, edx
0x14000db07  jnz     short loc_14000DB0F
0x14000db09  mov     ecx, ebp
0x14000db0b  mov     edx, ebp
0x14000db0d  jmp     short loc_14000DB19
0x14000db0f  xor     ecx, ecx
0x14000db11  cmp     edx, 2
0x14000db14  cmovz   ecx, ebp
0x14000db17  mov     edx, ecx
0x14000db19  mov     eax, r8d
0x14000db1c  mov     edi, 1
0x14000db21  or      eax, edx
0x14000db23  or      r8d, ecx
0x14000db26  mov     [rbx], eax
0x14000db28  bt      r8d, 0Ah
0x14000db2d  jnb     short loc_14000DB3D
0x14000db2f  cmp     r8d, 800h
0x14000db36  jb      short loc_14000DB3D
0x14000db38  mov     sil, dil
0x14000db3b  jmp     short loc_14000DB47
0x14000db3d  xor     sil, sil
0x14000db40  xor     cl, cl
0x14000db42  test    bpl, r8b
0x14000db45  jz      short loc_14000DB77
0x14000db47  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x14000db4e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x14000db53  test    al, al
0x14000db55  jz      short loc_14000DB68
0x14000db57  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl(void)'::`2'::impl
0x14000db5e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14000db63  mov     cl, dil
0x14000db66  jmp     short loc_14000DB6A
0x14000db68  xor     cl, cl
0x14000db6a  test    sil, sil
0x14000db6d  jz      short loc_14000DB77
0x14000db6f  test    cl, cl
0x14000db71  jnz     short loc_14000DB77
0x14000db73  btr     dword ptr [rbx], 0Ah
0x14000db77  mov     eax, [rbx]
0x14000db79  test    bpl, al
0x14000db7c  jz      short loc_14000DB82
0x14000db7e  test    cl, cl
0x14000db80  jnz     short loc_14000DB84
0x14000db82  xor     edi, edi
0x14000db84  and     eax, 0FFFFFFFEh
0x14000db87  or      eax, edi
0x14000db89  mov     [rbx], eax
0x14000db8b  mov     rax, rbx
0x14000db8e  add     rsp, 28h
0x14000db92  pop     rdi
0x14000db93  pop     rsi
0x14000db94  pop     rbp
0x14000db95  pop     rbx
0x14000db96  retn
```
