# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180011d88`
- end: `0x180011e47`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800118f0`

## callees

- `0x180011d88`
- `0x180012420`
- `0x180012488`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x385DB47, (unsigned int)a2, a3, a4);
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
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl'::`2'::impl);
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
0x180011d88  push    rbx
0x180011d8a  push    rbp
0x180011d8b  push    rsi
0x180011d8c  push    rdi
0x180011d8d  sub     rsp, 28h
0x180011d91  mov     ecx, 385DB47h; this
0x180011d96  mov     rbx, rdx
0x180011d99  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180011d9e  mov     edx, eax
0x180011da0  mov     qword ptr [rbx], 0
0x180011da7  and     edx, 0FFFFFF3Fh
0x180011dad  mov     ecx, eax
0x180011daf  and     eax, 80h
0x180011db4  mov     r8d, edx
0x180011db7  and     r8d, 3
0x180011dbb  mov     ebp, 40h ; '@'
0x180011dc0  shl     r8d, 2
0x180011dc4  and     ecx, ebp
0x180011dc6  or      r8d, ecx
0x180011dc9  shl     r8d, 2
0x180011dcd  or      r8d, eax
0x180011dd0  shl     r8d, 3
0x180011dd4  test    edx, edx
0x180011dd6  jnz     short loc_180011DDC
0x180011dd8  mov     eax, ebp
0x180011dda  jmp     short loc_180011DE4
0x180011ddc  xor     eax, eax
0x180011dde  cmp     edx, 2
0x180011de1  cmovz   eax, ebp
0x180011de4  or      r8d, eax
0x180011de7  mov     edi, 1
0x180011dec  mov     [rbx], r8d
0x180011def  bt      r8d, 0Ah
0x180011df4  jnb     short loc_180011E04
0x180011df6  cmp     r8d, 800h
0x180011dfd  jb      short loc_180011E04
0x180011dff  mov     sil, dil
0x180011e02  jmp     short loc_180011E0E
0x180011e04  xor     sil, sil
0x180011e07  xor     al, al
0x180011e09  test    bpl, r8b
0x180011e0c  jz      short loc_180011E27
0x180011e0e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x180011e15  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x180011e1a  test    sil, sil
0x180011e1d  jz      short loc_180011E27
0x180011e1f  test    al, al
0x180011e21  jnz     short loc_180011E27
0x180011e23  btr     dword ptr [rbx], 0Ah
0x180011e27  mov     ecx, [rbx]
0x180011e29  test    bpl, cl
0x180011e2c  jz      short loc_180011E32
0x180011e2e  test    al, al
0x180011e30  jnz     short loc_180011E34
0x180011e32  xor     edi, edi
0x180011e34  and     ecx, 0FFFFFFFEh
0x180011e37  mov     rax, rbx
0x180011e3a  or      ecx, edi
0x180011e3c  mov     [rbx], ecx
0x180011e3e  add     rsp, 28h
0x180011e42  pop     rdi
0x180011e43  pop     rsi
0x180011e44  pop     rbp
0x180011e45  pop     rbx
0x180011e46  retn
```
