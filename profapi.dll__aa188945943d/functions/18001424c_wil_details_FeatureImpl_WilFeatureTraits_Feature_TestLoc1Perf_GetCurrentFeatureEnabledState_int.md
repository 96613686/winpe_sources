# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001424c`
- end: `0x180014333`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `231`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180013868`

## callees

- `0x180013228`
- `0x18001424c`
- `0x1800157f4`
- `0x180015a4c`

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
  __int64 v7; // rcx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // si
  wil::details *v13; // rcx
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF

  v15 = a1;
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
    LOBYTE(v7) = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_18;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(v7) )
  {
    v13 = (wil::details *)*(unsigned int *)Feature_Standalone_26_01_NonSec__descriptor;
    if ( ((unsigned __int8)v13 & 4) == 0 )
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
0x18001424c  mov     [rsp+arg_0], rcx
0x180014251  push    rbx
0x180014252  push    rbp
0x180014253  push    rsi
0x180014254  push    rdi
0x180014255  sub     rsp, 28h
0x180014259  mov     ecx, 38419ACh; this
0x18001425e  mov     rbx, rdx
0x180014261  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180014266  mov     edx, eax
0x180014268  mov     qword ptr [rbx], 0
0x18001426f  and     edx, 0FFFFFF3Fh
0x180014275  mov     ecx, eax
0x180014277  and     eax, 80h
0x18001427c  mov     r8d, edx
0x18001427f  and     r8d, 3
0x180014283  mov     ebp, 40h ; '@'
0x180014288  shl     r8d, 2
0x18001428c  and     ecx, ebp
0x18001428e  or      r8d, ecx
0x180014291  shl     r8d, 2
0x180014295  or      r8d, eax
0x180014298  shl     r8d, 3
0x18001429c  test    edx, edx
0x18001429e  jnz     short loc_1800142A6
0x1800142a0  mov     ecx, ebp
0x1800142a2  mov     edx, ebp
0x1800142a4  jmp     short loc_1800142B0
0x1800142a6  xor     ecx, ecx
0x1800142a8  cmp     edx, 2
0x1800142ab  cmovz   ecx, ebp
0x1800142ae  mov     edx, ecx
0x1800142b0  mov     eax, r8d
0x1800142b3  mov     edi, 1
0x1800142b8  or      eax, edx
0x1800142ba  or      r8d, ecx
0x1800142bd  mov     [rbx], eax
0x1800142bf  bt      r8d, 0Ah
0x1800142c4  jnb     short loc_1800142D4
0x1800142c6  cmp     r8d, 800h
0x1800142cd  jb      short loc_1800142D4
0x1800142cf  mov     sil, dil
0x1800142d2  jmp     short loc_1800142DE
0x1800142d4  xor     sil, sil
0x1800142d7  xor     cl, cl
0x1800142d9  test    bpl, r8b
0x1800142dc  jz      short loc_180014313
0x1800142de  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x1800142e3  test    al, al
0x1800142e5  jz      short loc_180014304
0x1800142e7  mov     rax, cs:Feature_Standalone_26_01_NonSec__descriptor
0x1800142ee  mov     ecx, [rax]
0x1800142f0  test    cl, 4
0x1800142f3  jnz     short loc_1800142FF
0x1800142f5  lea     rdx, [rsp+48h+arg_0]
0x1800142fa  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x1800142ff  mov     cl, dil
0x180014302  jmp     short loc_180014306
0x180014304  xor     cl, cl
0x180014306  test    sil, sil
0x180014309  jz      short loc_180014313
0x18001430b  test    cl, cl
0x18001430d  jnz     short loc_180014313
0x18001430f  btr     dword ptr [rbx], 0Ah
0x180014313  mov     eax, [rbx]
0x180014315  test    bpl, al
0x180014318  jz      short loc_18001431E
0x18001431a  test    cl, cl
0x18001431c  jnz     short loc_180014320
0x18001431e  xor     edi, edi
0x180014320  and     eax, 0FFFFFFFEh
0x180014323  or      eax, edi
0x180014325  mov     [rbx], eax
0x180014327  mov     rax, rbx
0x18001432a  add     rsp, 28h
0x18001432e  pop     rdi
0x18001432f  pop     rsi
0x180014330  pop     rbp
0x180014331  pop     rbx
0x180014332  retn
```
