# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14000d8dc`
- end: `0x14000d9bf`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `227`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000d064`

## callees

- `0x140009c64`
- `0x14000d8dc`
- `0x14000e674`
- `0x14000ec98`

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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419CA, 3u, a3, a4);
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
0x14000d8dc  push    rbx
0x14000d8de  push    rbp
0x14000d8df  push    rsi
0x14000d8e0  push    rdi
0x14000d8e1  sub     rsp, 28h
0x14000d8e5  mov     rbx, rdx
0x14000d8e8  mov     ecx, 38419CAh; this
0x14000d8ed  mov     edx, 3; unsigned int
0x14000d8f2  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14000d8f7  mov     edx, eax
0x14000d8f9  mov     qword ptr [rbx], 0
0x14000d900  and     edx, 0FFFFFF3Fh
0x14000d906  mov     ecx, eax
0x14000d908  and     eax, 80h
0x14000d90d  mov     r8d, edx
0x14000d910  and     r8d, 3
0x14000d914  mov     ebp, 40h ; '@'
0x14000d919  shl     r8d, 2
0x14000d91d  and     ecx, ebp
0x14000d91f  or      r8d, ecx
0x14000d922  shl     r8d, 2
0x14000d926  or      r8d, eax
0x14000d929  shl     r8d, 3
0x14000d92d  test    edx, edx
0x14000d92f  jnz     short loc_14000D937
0x14000d931  mov     ecx, ebp
0x14000d933  mov     edx, ebp
0x14000d935  jmp     short loc_14000D941
0x14000d937  xor     ecx, ecx
0x14000d939  cmp     edx, 2
0x14000d93c  cmovz   ecx, ebp
0x14000d93f  mov     edx, ecx
0x14000d941  mov     eax, r8d
0x14000d944  mov     edi, 1
0x14000d949  or      eax, edx
0x14000d94b  or      r8d, ecx
0x14000d94e  mov     [rbx], eax
0x14000d950  bt      r8d, 0Ah
0x14000d955  jnb     short loc_14000D965
0x14000d957  cmp     r8d, 800h
0x14000d95e  jb      short loc_14000D965
0x14000d960  mov     sil, dil
0x14000d963  jmp     short loc_14000D96F
0x14000d965  xor     sil, sil
0x14000d968  xor     cl, cl
0x14000d96a  test    bpl, r8b
0x14000d96d  jz      short loc_14000D99F
0x14000d96f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x14000d976  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x14000d97b  test    al, al
0x14000d97d  jz      short loc_14000D990
0x14000d97f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetImpl(void)'::`2'::impl
0x14000d986  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14000d98b  mov     cl, dil
0x14000d98e  jmp     short loc_14000D992
0x14000d990  xor     cl, cl
0x14000d992  test    sil, sil
0x14000d995  jz      short loc_14000D99F
0x14000d997  test    cl, cl
0x14000d999  jnz     short loc_14000D99F
0x14000d99b  btr     dword ptr [rbx], 0Ah
0x14000d99f  mov     eax, [rbx]
0x14000d9a1  test    bpl, al
0x14000d9a4  jz      short loc_14000D9AA
0x14000d9a6  test    cl, cl
0x14000d9a8  jnz     short loc_14000D9AC
0x14000d9aa  xor     edi, edi
0x14000d9ac  and     eax, 0FFFFFFFEh
0x14000d9af  or      eax, edi
0x14000d9b1  mov     [rbx], eax
0x14000d9b3  mov     rax, rbx
0x14000d9b6  add     rsp, 28h
0x14000d9ba  pop     rdi
0x14000d9bb  pop     rsi
0x14000d9bc  pop     rbp
0x14000d9bd  pop     rbx
0x14000d9be  retn
```
