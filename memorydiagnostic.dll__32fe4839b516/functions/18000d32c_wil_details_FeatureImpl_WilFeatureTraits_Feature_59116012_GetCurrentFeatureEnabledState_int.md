# wil::details::FeatureImpl<__WilFeatureTraits_Feature_59116012>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000d32c`
- end: `0x18000d41b`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_59116012@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ce08`

## callees

- `0x18000d32c`
- `0x180016464`
- `0x180024010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_59116012>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, _QWORD); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // edx
  int v7; // eax
  char v8; // cl
  int v9; // edi
  char v10; // si
  char IsEnabled; // al

  v2 = (__int64 (__fastcall *)(__int64, _QWORD))g_wil_details_internalGetFeatureEnabledState;
  v4 = 0;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, _QWORD))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(59116012, 0);
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( v5 )
  {
    v7 = 0;
    if ( v5 == 2 )
      v7 = 64;
    v6 |= v7;
  }
  *(_DWORD *)a2 = v6;
  v8 = 0;
  v9 = 1;
  if ( (v6 & 0xC00) == 0xC00 )
  {
    v10 = 1;
  }
  else
  {
    v10 = 0;
    if ( (v6 & 0x40) == 0 )
      goto LABEL_14;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_57054134>::GetImpl'::`2'::impl);
  v8 = IsEnabled;
  if ( v10 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_14:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v8 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18000d32c  mov     [rsp+arg_0], rbx
0x18000d331  mov     [rsp+arg_8], rbp
0x18000d336  mov     [rsp+arg_10], rsi
0x18000d33b  push    rdi
0x18000d33c  sub     rsp, 20h
0x18000d340  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000d347  mov     rbx, rdx
0x18000d34a  xor     edx, edx
0x18000d34c  test    rax, rax
0x18000d34f  jnz     short loc_18000D35D
0x18000d351  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000d358  test    rax, rax
0x18000d35b  jz      short loc_18000D369
0x18000d35d  mov     ecx, 38609ECh
0x18000d362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d367  mov     edx, eax
0x18000d369  and     qword ptr [rbx], 0
0x18000d36d  mov     r8d, edx
0x18000d370  mov     eax, edx
0x18000d372  and     r8d, 0FFFFFF3Fh
0x18000d379  and     edx, 80h
0x18000d37f  mov     ecx, r8d
0x18000d382  and     ecx, 3
0x18000d385  mov     ebp, 40h ; '@'
0x18000d38a  shl     ecx, 2
0x18000d38d  and     eax, ebp
0x18000d38f  or      ecx, eax
0x18000d391  shl     ecx, 2
0x18000d394  or      ecx, edx
0x18000d396  lea     edx, ds:0[rcx*8]
0x18000d39d  test    r8d, r8d
0x18000d3a0  jz      short loc_18000D3AD
0x18000d3a2  xor     eax, eax
0x18000d3a4  cmp     r8d, 2
0x18000d3a8  cmovz   eax, ebp
0x18000d3ab  or      edx, eax
0x18000d3ad  mov     r8d, 0C00h
0x18000d3b3  mov     [rbx], edx
0x18000d3b5  mov     eax, edx
0x18000d3b7  xor     cl, cl
0x18000d3b9  and     eax, r8d
0x18000d3bc  mov     edi, 1
0x18000d3c1  cmp     eax, r8d
0x18000d3c4  jnz     short loc_18000D3CB
0x18000d3c6  mov     sil, dil
0x18000d3c9  jmp     short loc_18000D3D3
0x18000d3cb  xor     sil, sil
0x18000d3ce  test    bpl, dl
0x18000d3d1  jz      short loc_18000D3EE
0x18000d3d3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57054134@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134> `wil::Feature<__WilFeatureTraits_Feature_57054134>::GetImpl(void)'::`2'::impl
0x18000d3da  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::__private_IsEnabled(wil::ReportingKind)
0x18000d3df  mov     cl, al
0x18000d3e1  test    sil, sil
0x18000d3e4  jz      short loc_18000D3EE
0x18000d3e6  test    al, al
0x18000d3e8  jnz     short loc_18000D3EE
0x18000d3ea  btr     dword ptr [rbx], 0Ah
0x18000d3ee  mov     eax, [rbx]
0x18000d3f0  test    bpl, al
0x18000d3f3  jz      short loc_18000D3F9
0x18000d3f5  test    cl, cl
0x18000d3f7  jnz     short loc_18000D3FB
0x18000d3f9  xor     edi, edi
0x18000d3fb  mov     rbp, [rsp+28h+arg_8]
0x18000d400  and     eax, 0FFFFFFFEh
0x18000d403  mov     rsi, [rsp+28h+arg_10]
0x18000d408  or      eax, edi
0x18000d40a  mov     [rbx], eax
0x18000d40c  mov     rax, rbx
0x18000d40f  mov     rbx, [rsp+28h+arg_0]
0x18000d414  add     rsp, 20h
0x18000d418  pop     rdi
0x18000d419  retn
```
