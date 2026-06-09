# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::GetCurrentFeatureEnabledState(int *)

- ea: `0x140016090`
- end: `0x14001616d`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `221`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140015090`

## callees

- `0x140016090`
- `0x140017d24`
- `0x140017f04`
- `0x140017fb8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // edx
  int v7; // r8d
  int v8; // eax
  int v9; // r8d
  int v10; // ecx
  __int16 v11; // r8
  int v12; // edi
  char v13; // si
  bool v14; // cl

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x397EF53, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3))));
  v8 = 0;
  v9 = 8 * v7;
  if ( v6 )
  {
    if ( v6 == 2 )
      v8 = 64;
    v10 = v9 | v8;
  }
  else
  {
    v10 = v9;
  }
  v11 = v8 | v9;
  *(_DWORD *)a2 = v10;
  v12 = 1;
  if ( (v11 & 0xC00) == 0xC00 )
  {
    v13 = 1;
  }
  else
  {
    v13 = 0;
    v14 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_16;
  }
  v14 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmersiveColorFight>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ImmersiveColorFight>::GetImpl'::`2'::impl)
     && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
  if ( v13 && !v14 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_16:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v14 )
    v12 = 0;
  *(_DWORD *)a2 = v12 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x140016090  push    rbx
0x140016092  push    rbp
0x140016093  push    rsi
0x140016094  push    rdi
0x140016095  sub     rsp, 28h
0x140016099  mov     ecx, 397EF53h; this
0x14001609e  mov     rbx, rdx
0x1400160a1  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1400160a6  mov     edx, eax
0x1400160a8  mov     qword ptr [rbx], 0
0x1400160af  mov     ecx, eax
0x1400160b1  and     edx, 0FFFFFF3Fh
0x1400160b7  and     eax, 80h
0x1400160bc  mov     r8d, edx
0x1400160bf  and     r8d, 3
0x1400160c3  mov     ebp, 40h ; '@'
0x1400160c8  shl     r8d, 2
0x1400160cc  and     ecx, ebp
0x1400160ce  or      r8d, ecx
0x1400160d1  shl     r8d, 2
0x1400160d5  or      r8d, eax
0x1400160d8  xor     eax, eax
0x1400160da  shl     r8d, 3
0x1400160de  test    edx, edx
0x1400160e0  jnz     short loc_1400160E7
0x1400160e2  mov     ecx, r8d
0x1400160e5  jmp     short loc_1400160F2
0x1400160e7  cmp     edx, 2
0x1400160ea  cmovz   eax, ebp
0x1400160ed  mov     ecx, eax
0x1400160ef  or      ecx, r8d
0x1400160f2  or      r8d, eax
0x1400160f5  mov     [rbx], ecx
0x1400160f7  mov     ecx, 0C00h
0x1400160fc  mov     eax, r8d
0x1400160ff  and     eax, ecx
0x140016101  mov     edi, 1
0x140016106  cmp     eax, ecx
0x140016108  jnz     short loc_14001610F
0x14001610a  mov     sil, dil
0x14001610d  jmp     short loc_140016119
0x14001610f  xor     sil, sil
0x140016112  xor     cl, cl
0x140016114  test    bpl, r8b
0x140016117  jz      short loc_14001614D
0x140016119  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ImmersiveColorFight@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ImmersiveColorFight@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmersiveColorFight> `wil::Feature<__WilFeatureTraits_Feature_ImmersiveColorFight>::GetImpl(void)'::`2'::impl
0x140016120  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ImmersiveColorFight@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmersiveColorFight>::__private_IsEnabled(wil::ReportingKind)
0x140016125  test    al, al
0x140016127  jz      short loc_14001613E
0x140016129  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x140016130  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x140016135  test    al, al
0x140016137  jz      short loc_14001613E
0x140016139  mov     cl, dil
0x14001613c  jmp     short loc_140016140
0x14001613e  xor     cl, cl
0x140016140  test    sil, sil
0x140016143  jz      short loc_14001614D
0x140016145  test    cl, cl
0x140016147  jnz     short loc_14001614D
0x140016149  btr     dword ptr [rbx], 0Ah
0x14001614d  mov     eax, [rbx]
0x14001614f  test    bpl, al
0x140016152  jz      short loc_140016158
0x140016154  test    cl, cl
0x140016156  jnz     short loc_14001615A
0x140016158  xor     edi, edi
0x14001615a  and     eax, 0FFFFFFFEh
0x14001615d  or      eax, edi
0x14001615f  mov     [rbx], eax
0x140016161  mov     rax, rbx
0x140016164  add     rsp, 28h
0x140016168  pop     rdi
0x140016169  pop     rsi
0x14001616a  pop     rbp
0x14001616b  pop     rbx
0x14001616c  retn
```
