# wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800118c4`
- end: `0x180011988`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_NegoLateFallback@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800115c8`

## callees

- `0x1800118c4`
- `0x180014da4`
- `0x180015114`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // edx
  int v7; // r8d
  int v8; // eax
  unsigned int v9; // r8d
  int v10; // edi
  char v11; // si
  char IsEnabled; // al
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0xA2CB25, 3u, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v8 = 0;
    if ( v6 == 2 )
      v8 = 64;
  }
  else
  {
    v8 = 64;
  }
  v9 = v8 | v7;
  v10 = 1;
  *(_DWORD *)a2 = v9;
  if ( (v9 & 0x400) != 0 && v9 >= 0x800 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    IsEnabled = 0;
    if ( (v9 & 0x40) == 0 )
      goto LABEL_12;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NTLMless>::GetImpl'::`2'::impl);
  if ( v11 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_12:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !IsEnabled )
    v10 = 0;
  result = a2;
  *(_DWORD *)a2 = v10 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x1800118c4  push    rbx
0x1800118c6  push    rbp
0x1800118c7  push    rsi
0x1800118c8  push    rdi
0x1800118c9  sub     rsp, 28h
0x1800118cd  mov     rbx, rdx
0x1800118d0  mov     ecx, 0A2CB25h; this
0x1800118d5  mov     edx, 3; unsigned int
0x1800118da  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800118df  mov     edx, eax
0x1800118e1  mov     qword ptr [rbx], 0
0x1800118e8  and     edx, 0FFFFFF3Fh
0x1800118ee  mov     ecx, eax
0x1800118f0  and     eax, 80h
0x1800118f5  mov     r8d, edx
0x1800118f8  and     r8d, 3
0x1800118fc  mov     ebp, 40h ; '@'
0x180011901  shl     r8d, 2
0x180011905  and     ecx, ebp
0x180011907  or      r8d, ecx
0x18001190a  shl     r8d, 2
0x18001190e  or      r8d, eax
0x180011911  shl     r8d, 3
0x180011915  test    edx, edx
0x180011917  jnz     short loc_18001191D
0x180011919  mov     eax, ebp
0x18001191b  jmp     short loc_180011925
0x18001191d  xor     eax, eax
0x18001191f  cmp     edx, 2
0x180011922  cmovz   eax, ebp
0x180011925  or      r8d, eax
0x180011928  mov     edi, 1
0x18001192d  mov     [rbx], r8d
0x180011930  bt      r8d, 0Ah
0x180011935  jnb     short loc_180011945
0x180011937  cmp     r8d, 800h
0x18001193e  jb      short loc_180011945
0x180011940  mov     sil, dil
0x180011943  jmp     short loc_18001194F
0x180011945  xor     sil, sil
0x180011948  xor     al, al
0x18001194a  test    bpl, r8b
0x18001194d  jz      short loc_180011968
0x18001194f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NTLMless@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless> `wil::Feature<__WilFeatureTraits_Feature_NTLMless>::GetImpl(void)'::`2'::impl
0x180011956  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless>::__private_IsEnabled(wil::ReportingKind)
0x18001195b  test    sil, sil
0x18001195e  jz      short loc_180011968
0x180011960  test    al, al
0x180011962  jnz     short loc_180011968
0x180011964  btr     dword ptr [rbx], 0Ah
0x180011968  mov     ecx, [rbx]
0x18001196a  test    bpl, cl
0x18001196d  jz      short loc_180011973
0x18001196f  test    al, al
0x180011971  jnz     short loc_180011975
0x180011973  xor     edi, edi
0x180011975  and     ecx, 0FFFFFFFEh
0x180011978  mov     rax, rbx
0x18001197b  or      ecx, edi
0x18001197d  mov     [rbx], ecx
0x18001197f  add     rsp, 28h
0x180011983  pop     rdi
0x180011984  pop     rsi
0x180011985  pop     rbp
0x180011986  pop     rbx
0x180011987  retn
```
