# wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000c9c0`
- end: `0x18000cab1`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `241`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c384`

## callees

- `0x18000c9c0`
- `0x1800115a0`
- `0x180015804`
- `0x180023010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  char v6; // al
  unsigned int v7; // edx
  wil::details *v8; // rcx
  int v9; // eax
  bool ShouldBeEnabledFromConfigAndDefault; // al
  unsigned int v11; // ecx
  int v12; // ecx
  int v13; // edi
  char v14; // si
  char IsEnabled; // al
  _QWORD *result; // rax

  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(57054134, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = v4;
  v7 = v4 & 0x80;
  v8 = (wil::details *)(v7 | (4 * (v6 & 0x40 | (4 * (v5 & 3)))));
  v9 = 8 * (_DWORD)v8;
  *(_DWORD *)a2 = 8 * (_DWORD)v8;
  if ( v5 )
  {
    v11 = 0;
    if ( v5 == 2 )
      v11 = 64;
  }
  else
  {
    ShouldBeEnabledFromConfigAndDefault = wil::details::ShouldBeEnabledFromConfigAndDefault(v8, v7, 0);
    v11 = *(_DWORD *)a2 & 0xFFFFFFBF;
    v9 = ShouldBeEnabledFromConfigAndDefault << 6;
  }
  v12 = v9 | v11;
  *(_DWORD *)a2 = v12;
  v13 = 1;
  if ( (v12 & 0xC00) == 0xC00 )
  {
    v14 = 1;
  }
  else
  {
    v14 = 0;
    IsEnabled = 0;
    if ( (v12 & 0x40) == 0 )
      goto LABEL_15;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
  if ( v14 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_15:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !IsEnabled )
    v13 = 0;
  result = a2;
  *(_DWORD *)a2 = v13 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x18000c9c0  push    rbx
0x18000c9c2  push    rbp
0x18000c9c3  push    rsi
0x18000c9c4  push    rdi
0x18000c9c5  sub     rsp, 28h
0x18000c9c9  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000c9d0  mov     rbx, rdx
0x18000c9d3  mov     edi, 3
0x18000c9d8  test    rax, rax
0x18000c9db  jz      short loc_18000C9ED
0x18000c9dd  mov     edx, edi
0x18000c9df  mov     ecx, 36693B6h
0x18000c9e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9e9  mov     edx, eax
0x18000c9eb  jmp     short loc_18000C9FB
0x18000c9ed  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000c9f4  test    rax, rax
0x18000c9f7  jnz     short loc_18000C9DD
0x18000c9f9  xor     edx, edx
0x18000c9fb  mov     r8d, edx
0x18000c9fe  mov     qword ptr [rbx], 0
0x18000ca05  and     r8d, 0FFFFFF3Fh; bool
0x18000ca0c  mov     eax, edx
0x18000ca0e  and     edx, 80h; unsigned int
0x18000ca14  mov     ecx, r8d
0x18000ca17  and     ecx, edi
0x18000ca19  mov     ebp, 40h ; '@'
0x18000ca1e  shl     ecx, 2
0x18000ca21  and     eax, ebp
0x18000ca23  or      ecx, eax
0x18000ca25  shl     ecx, 2
0x18000ca28  or      ecx, edx; this
0x18000ca2a  lea     eax, ds:0[rcx*8]
0x18000ca31  mov     [rbx], eax
0x18000ca33  test    r8d, r8d
0x18000ca36  jnz     short loc_18000CA4A
0x18000ca38  call    ?ShouldBeEnabledFromConfigAndDefault@details@wil@@YA_NI_N@Z; wil::details::ShouldBeEnabledFromConfigAndDefault(uint,bool)
0x18000ca3d  mov     ecx, [rbx]
0x18000ca3f  and     ecx, 0FFFFFFBFh
0x18000ca42  movzx   eax, al
0x18000ca45  shl     eax, 6
0x18000ca48  jmp     short loc_18000CA53
0x18000ca4a  xor     ecx, ecx
0x18000ca4c  cmp     r8d, 2
0x18000ca50  cmovz   ecx, ebp
0x18000ca53  or      ecx, eax
0x18000ca55  mov     edx, 0C00h
0x18000ca5a  mov     eax, ecx
0x18000ca5c  mov     [rbx], ecx
0x18000ca5e  and     eax, edx
0x18000ca60  mov     edi, 1
0x18000ca65  cmp     eax, edx
0x18000ca67  jnz     short loc_18000CA6E
0x18000ca69  mov     sil, dil
0x18000ca6c  jmp     short loc_18000CA78
0x18000ca6e  xor     sil, sil
0x18000ca71  xor     al, al
0x18000ca73  test    bpl, cl
0x18000ca76  jz      short loc_18000CA91
0x18000ca78  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18000ca7f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18000ca84  test    sil, sil
0x18000ca87  jz      short loc_18000CA91
0x18000ca89  test    al, al
0x18000ca8b  jnz     short loc_18000CA91
0x18000ca8d  btr     dword ptr [rbx], 0Ah
0x18000ca91  mov     ecx, [rbx]
0x18000ca93  test    bpl, cl
0x18000ca96  jz      short loc_18000CA9C
0x18000ca98  test    al, al
0x18000ca9a  jnz     short loc_18000CA9E
0x18000ca9c  xor     edi, edi
0x18000ca9e  and     ecx, 0FFFFFFFEh
0x18000caa1  mov     rax, rbx
0x18000caa4  or      ecx, edi
0x18000caa6  mov     [rbx], ecx
0x18000caa8  add     rsp, 28h
0x18000caac  pop     rdi
0x18000caad  pop     rsi
0x18000caae  pop     rbp
0x18000caaf  pop     rbx
0x18000cab0  retn
```
