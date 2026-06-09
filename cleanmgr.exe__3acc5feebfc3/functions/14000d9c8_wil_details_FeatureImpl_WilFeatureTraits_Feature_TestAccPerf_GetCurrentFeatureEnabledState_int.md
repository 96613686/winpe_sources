# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14000d9c8`
- end: `0x14000daab`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `227`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000d144`

## callees

- `0x140009c64`
- `0x14000d9c8`
- `0x14000e56c`
- `0x14000ed10`

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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CAD, 3u, a3, a4);
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
0x14000d9c8  push    rbx
0x14000d9ca  push    rbp
0x14000d9cb  push    rsi
0x14000d9cc  push    rdi
0x14000d9cd  sub     rsp, 28h
0x14000d9d1  mov     rbx, rdx
0x14000d9d4  mov     ecx, 3667CADh; this
0x14000d9d9  mov     edx, 3; unsigned int
0x14000d9de  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14000d9e3  mov     edx, eax
0x14000d9e5  mov     qword ptr [rbx], 0
0x14000d9ec  and     edx, 0FFFFFF3Fh
0x14000d9f2  mov     ecx, eax
0x14000d9f4  and     eax, 80h
0x14000d9f9  mov     r8d, edx
0x14000d9fc  and     r8d, 3
0x14000da00  mov     ebp, 40h ; '@'
0x14000da05  shl     r8d, 2
0x14000da09  and     ecx, ebp
0x14000da0b  or      r8d, ecx
0x14000da0e  shl     r8d, 2
0x14000da12  or      r8d, eax
0x14000da15  shl     r8d, 3
0x14000da19  test    edx, edx
0x14000da1b  jnz     short loc_14000DA23
0x14000da1d  mov     ecx, ebp
0x14000da1f  mov     edx, ebp
0x14000da21  jmp     short loc_14000DA2D
0x14000da23  xor     ecx, ecx
0x14000da25  cmp     edx, 2
0x14000da28  cmovz   ecx, ebp
0x14000da2b  mov     edx, ecx
0x14000da2d  mov     eax, r8d
0x14000da30  mov     edi, 1
0x14000da35  or      eax, edx
0x14000da37  or      r8d, ecx
0x14000da3a  mov     [rbx], eax
0x14000da3c  bt      r8d, 0Ah
0x14000da41  jnb     short loc_14000DA51
0x14000da43  cmp     r8d, 800h
0x14000da4a  jb      short loc_14000DA51
0x14000da4c  mov     sil, dil
0x14000da4f  jmp     short loc_14000DA5B
0x14000da51  xor     sil, sil
0x14000da54  xor     cl, cl
0x14000da56  test    bpl, r8b
0x14000da59  jz      short loc_14000DA8B
0x14000da5b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x14000da62  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x14000da67  test    al, al
0x14000da69  jz      short loc_14000DA7C
0x14000da6b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetImpl(void)'::`2'::impl
0x14000da72  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14000da77  mov     cl, dil
0x14000da7a  jmp     short loc_14000DA7E
0x14000da7c  xor     cl, cl
0x14000da7e  test    sil, sil
0x14000da81  jz      short loc_14000DA8B
0x14000da83  test    cl, cl
0x14000da85  jnz     short loc_14000DA8B
0x14000da87  btr     dword ptr [rbx], 0Ah
0x14000da8b  mov     eax, [rbx]
0x14000da8d  test    bpl, al
0x14000da90  jz      short loc_14000DA96
0x14000da92  test    cl, cl
0x14000da94  jnz     short loc_14000DA98
0x14000da96  xor     edi, edi
0x14000da98  and     eax, 0FFFFFFFEh
0x14000da9b  or      eax, edi
0x14000da9d  mov     [rbx], eax
0x14000da9f  mov     rax, rbx
0x14000daa2  add     rsp, 28h
0x14000daa6  pop     rdi
0x14000daa7  pop     rsi
0x14000daa8  pop     rbp
0x14000daa9  pop     rbx
0x14000daaa  retn
```
