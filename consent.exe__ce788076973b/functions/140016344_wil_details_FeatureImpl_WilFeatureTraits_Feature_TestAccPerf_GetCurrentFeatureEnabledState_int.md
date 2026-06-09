# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x140016344`
- end: `0x140016422`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140015638`

## callees

- `0x140016344`
- `0x14001740c`
- `0x140017d24`
- `0x140017ff4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CAD, (unsigned int)a2, a3, a4);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetImpl'::`2'::impl);
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
0x140016344  push    rbx
0x140016346  push    rbp
0x140016347  push    rsi
0x140016348  push    rdi
0x140016349  sub     rsp, 28h
0x14001634d  mov     ecx, 3667CADh; this
0x140016352  mov     rbx, rdx
0x140016355  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14001635a  mov     edx, eax
0x14001635c  mov     qword ptr [rbx], 0
0x140016363  and     edx, 0FFFFFF3Fh
0x140016369  mov     ecx, eax
0x14001636b  and     eax, 80h
0x140016370  mov     r8d, edx
0x140016373  and     r8d, 3
0x140016377  mov     ebp, 40h ; '@'
0x14001637c  shl     r8d, 2
0x140016380  and     ecx, ebp
0x140016382  or      r8d, ecx
0x140016385  shl     r8d, 2
0x140016389  or      r8d, eax
0x14001638c  shl     r8d, 3
0x140016390  test    edx, edx
0x140016392  jnz     short loc_14001639A
0x140016394  mov     ecx, ebp
0x140016396  mov     edx, ebp
0x140016398  jmp     short loc_1400163A4
0x14001639a  xor     ecx, ecx
0x14001639c  cmp     edx, 2
0x14001639f  cmovz   ecx, ebp
0x1400163a2  mov     edx, ecx
0x1400163a4  mov     eax, r8d
0x1400163a7  mov     edi, 1
0x1400163ac  or      eax, edx
0x1400163ae  or      r8d, ecx
0x1400163b1  mov     [rbx], eax
0x1400163b3  bt      r8d, 0Ah
0x1400163b8  jnb     short loc_1400163C8
0x1400163ba  cmp     r8d, 800h
0x1400163c1  jb      short loc_1400163C8
0x1400163c3  mov     sil, dil
0x1400163c6  jmp     short loc_1400163D2
0x1400163c8  xor     sil, sil
0x1400163cb  xor     cl, cl
0x1400163cd  test    bpl, r8b
0x1400163d0  jz      short loc_140016402
0x1400163d2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x1400163d9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x1400163de  test    al, al
0x1400163e0  jz      short loc_1400163F3
0x1400163e2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetImpl(void)'::`2'::impl
0x1400163e9  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1400163ee  mov     cl, dil
0x1400163f1  jmp     short loc_1400163F5
0x1400163f3  xor     cl, cl
0x1400163f5  test    sil, sil
0x1400163f8  jz      short loc_140016402
0x1400163fa  test    cl, cl
0x1400163fc  jnz     short loc_140016402
0x1400163fe  btr     dword ptr [rbx], 0Ah
0x140016402  mov     eax, [rbx]
0x140016404  test    bpl, al
0x140016407  jz      short loc_14001640D
0x140016409  test    cl, cl
0x14001640b  jnz     short loc_14001640F
0x14001640d  xor     edi, edi
0x14001640f  and     eax, 0FFFFFFFEh
0x140016412  or      eax, edi
0x140016414  mov     [rbx], eax
0x140016416  mov     rax, rbx
0x140016419  add     rsp, 28h
0x14001641d  pop     rdi
0x14001641e  pop     rsi
0x14001641f  pop     rbp
0x140016420  pop     rbx
0x140016421  retn
```
