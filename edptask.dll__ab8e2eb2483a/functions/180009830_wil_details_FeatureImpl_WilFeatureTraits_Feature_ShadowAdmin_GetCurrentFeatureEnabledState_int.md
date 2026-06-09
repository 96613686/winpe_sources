# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180009830`
- end: `0x18000992c`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `252`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008c74`

## callees

- `0x180009830`
- `0x180011ff4`
- `0x180012268`
- `0x180014010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // eax
  int v7; // edx
  int v8; // ecx
  __int16 v9; // dx
  int v10; // edi
  char v11; // si
  bool v12; // cl

  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(60288851, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 0;
  v7 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  v8 = v7;
  if ( v5 )
  {
    if ( v5 == 2 )
      v6 = 64;
    v8 = v6 | v7;
  }
  v9 = v6 | v7;
  *(_DWORD *)a2 = v8;
  v10 = 1;
  if ( (v9 & 0xC00) == 0xC00 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    v12 = 0;
    if ( (v9 & 0x40) == 0 )
      goto LABEL_19;
  }
  v12 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmersiveColorFight>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ImmersiveColorFight>::GetImpl'::`2'::impl)
     && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
  if ( v11 && !v12 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_19:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v12 )
    v10 = 0;
  *(_DWORD *)a2 = v10 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180009830  push    rbx
0x180009832  push    rbp
0x180009833  push    rsi
0x180009834  push    rdi
0x180009835  sub     rsp, 28h
0x180009839  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180009840  mov     rbx, rdx
0x180009843  mov     edi, 3
0x180009848  test    rax, rax
0x18000984b  jz      short loc_18000985D
0x18000984d  mov     edx, edi
0x18000984f  mov     ecx, 397EF53h
0x180009854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009859  mov     edx, eax
0x18000985b  jmp     short loc_18000986B
0x18000985d  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180009864  test    rax, rax
0x180009867  jnz     short loc_18000984D
0x180009869  xor     edx, edx
0x18000986b  mov     r8d, edx
0x18000986e  mov     qword ptr [rbx], 0
0x180009875  mov     eax, edx
0x180009877  and     r8d, 0FFFFFF3Fh
0x18000987e  and     edx, 80h
0x180009884  mov     ecx, r8d
0x180009887  and     ecx, edi
0x180009889  mov     ebp, 40h ; '@'
0x18000988e  shl     ecx, 2
0x180009891  and     eax, ebp
0x180009893  or      ecx, eax
0x180009895  xor     eax, eax
0x180009897  shl     ecx, 2
0x18000989a  or      ecx, edx
0x18000989c  lea     edx, ds:0[rcx*8]
0x1800098a3  mov     ecx, edx
0x1800098a5  test    r8d, r8d
0x1800098a8  jz      short loc_1800098B3
0x1800098aa  cmp     r8d, 2
0x1800098ae  cmovz   eax, ebp
0x1800098b1  or      ecx, eax
0x1800098b3  or      edx, eax
0x1800098b5  mov     [rbx], ecx
0x1800098b7  mov     ecx, 0C00h
0x1800098bc  mov     eax, edx
0x1800098be  and     eax, ecx
0x1800098c0  mov     edi, 1
0x1800098c5  cmp     eax, ecx
0x1800098c7  jnz     short loc_1800098CE
0x1800098c9  mov     sil, dil
0x1800098cc  jmp     short loc_1800098D8
0x1800098ce  xor     sil, sil
0x1800098d1  xor     cl, cl
0x1800098d3  test    bpl, dl
0x1800098d6  jz      short loc_18000990C
0x1800098d8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ImmersiveColorFight@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ImmersiveColorFight@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmersiveColorFight> `wil::Feature<__WilFeatureTraits_Feature_ImmersiveColorFight>::GetImpl(void)'::`2'::impl
0x1800098df  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ImmersiveColorFight@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmersiveColorFight>::__private_IsEnabled(wil::ReportingKind)
0x1800098e4  test    al, al
0x1800098e6  jz      short loc_1800098FD
0x1800098e8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x1800098ef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x1800098f4  test    al, al
0x1800098f6  jz      short loc_1800098FD
0x1800098f8  mov     cl, dil
0x1800098fb  jmp     short loc_1800098FF
0x1800098fd  xor     cl, cl
0x1800098ff  test    sil, sil
0x180009902  jz      short loc_18000990C
0x180009904  test    cl, cl
0x180009906  jnz     short loc_18000990C
0x180009908  btr     dword ptr [rbx], 0Ah
0x18000990c  mov     eax, [rbx]
0x18000990e  test    bpl, al
0x180009911  jz      short loc_180009917
0x180009913  test    cl, cl
0x180009915  jnz     short loc_180009919
0x180009917  xor     edi, edi
0x180009919  and     eax, 0FFFFFFFEh
0x18000991c  or      eax, edi
0x18000991e  mov     [rbx], eax
0x180009920  mov     rax, rbx
0x180009923  add     rsp, 28h
0x180009927  pop     rdi
0x180009928  pop     rsi
0x180009929  pop     rbp
0x18000992a  pop     rbx
0x18000992b  retn
```
