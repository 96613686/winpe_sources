# wil::details::FeatureImpl<__WilFeatureTraits_Feature_59116012>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000cab8`
- end: `0x18000cbb4`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_59116012@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `252`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c464`

## callees

- `0x18000cab8`
- `0x180015724`
- `0x180015804`
- `0x180023010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_59116012>::GetCurrentFeatureEnabledState(
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
    v4 = v2(59116012, 3);
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
  v12 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl)
     && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57054134>::GetImpl'::`2'::impl);
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
0x18000cab8  push    rbx
0x18000caba  push    rbp
0x18000cabb  push    rsi
0x18000cabc  push    rdi
0x18000cabd  sub     rsp, 28h
0x18000cac1  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000cac8  mov     rbx, rdx
0x18000cacb  mov     edi, 3
0x18000cad0  test    rax, rax
0x18000cad3  jz      short loc_18000CAE5
0x18000cad5  mov     edx, edi
0x18000cad7  mov     ecx, 38609ECh
0x18000cadc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cae1  mov     edx, eax
0x18000cae3  jmp     short loc_18000CAF3
0x18000cae5  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000caec  test    rax, rax
0x18000caef  jnz     short loc_18000CAD5
0x18000caf1  xor     edx, edx
0x18000caf3  mov     r8d, edx
0x18000caf6  mov     qword ptr [rbx], 0
0x18000cafd  mov     eax, edx
0x18000caff  and     r8d, 0FFFFFF3Fh
0x18000cb06  and     edx, 80h
0x18000cb0c  mov     ecx, r8d
0x18000cb0f  and     ecx, edi
0x18000cb11  mov     ebp, 40h ; '@'
0x18000cb16  shl     ecx, 2
0x18000cb19  and     eax, ebp
0x18000cb1b  or      ecx, eax
0x18000cb1d  xor     eax, eax
0x18000cb1f  shl     ecx, 2
0x18000cb22  or      ecx, edx
0x18000cb24  lea     edx, ds:0[rcx*8]
0x18000cb2b  mov     ecx, edx
0x18000cb2d  test    r8d, r8d
0x18000cb30  jz      short loc_18000CB3B
0x18000cb32  cmp     r8d, 2
0x18000cb36  cmovz   eax, ebp
0x18000cb39  or      ecx, eax
0x18000cb3b  or      edx, eax
0x18000cb3d  mov     [rbx], ecx
0x18000cb3f  mov     ecx, 0C00h
0x18000cb44  mov     eax, edx
0x18000cb46  and     eax, ecx
0x18000cb48  mov     edi, 1
0x18000cb4d  cmp     eax, ecx
0x18000cb4f  jnz     short loc_18000CB56
0x18000cb51  mov     sil, dil
0x18000cb54  jmp     short loc_18000CB60
0x18000cb56  xor     sil, sil
0x18000cb59  xor     cl, cl
0x18000cb5b  test    bpl, dl
0x18000cb5e  jz      short loc_18000CB94
0x18000cb60  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18000cb67  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18000cb6c  test    al, al
0x18000cb6e  jz      short loc_18000CB85
0x18000cb70  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57054134@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134> `wil::Feature<__WilFeatureTraits_Feature_57054134>::GetImpl(void)'::`2'::impl
0x18000cb77  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::__private_IsEnabled(wil::ReportingKind)
0x18000cb7c  test    al, al
0x18000cb7e  jz      short loc_18000CB85
0x18000cb80  mov     cl, dil
0x18000cb83  jmp     short loc_18000CB87
0x18000cb85  xor     cl, cl
0x18000cb87  test    sil, sil
0x18000cb8a  jz      short loc_18000CB94
0x18000cb8c  test    cl, cl
0x18000cb8e  jnz     short loc_18000CB94
0x18000cb90  btr     dword ptr [rbx], 0Ah
0x18000cb94  mov     eax, [rbx]
0x18000cb96  test    bpl, al
0x18000cb99  jz      short loc_18000CB9F
0x18000cb9b  test    cl, cl
0x18000cb9d  jnz     short loc_18000CBA1
0x18000cb9f  xor     edi, edi
0x18000cba1  and     eax, 0FFFFFFFEh
0x18000cba4  or      eax, edi
0x18000cba6  mov     [rbx], eax
0x18000cba8  mov     rax, rbx
0x18000cbab  add     rsp, 28h
0x18000cbaf  pop     rdi
0x18000cbb0  pop     rsi
0x18000cbb1  pop     rbp
0x18000cbb2  pop     rbx
0x18000cbb3  retn
```
