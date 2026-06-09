# wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixDiskCleanupOn200Zoom>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14000d5a4`
- end: `0x14000d668`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_FixDiskCleanupOn200Zoom@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `196`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000cb24`

## callees

- `0x140009c64`
- `0x14000d5a4`
- `0x14000ecd4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixDiskCleanupOn200Zoom>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38EEC9D, 3u, a3, a4);
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
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl'::`2'::impl);
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
0x14000d5a4  push    rbx
0x14000d5a6  push    rbp
0x14000d5a7  push    rsi
0x14000d5a8  push    rdi
0x14000d5a9  sub     rsp, 28h
0x14000d5ad  mov     rbx, rdx
0x14000d5b0  mov     ecx, 38EEC9Dh; this
0x14000d5b5  mov     edx, 3; unsigned int
0x14000d5ba  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14000d5bf  mov     edx, eax
0x14000d5c1  mov     qword ptr [rbx], 0
0x14000d5c8  and     edx, 0FFFFFF3Fh
0x14000d5ce  mov     ecx, eax
0x14000d5d0  and     eax, 80h
0x14000d5d5  mov     r8d, edx
0x14000d5d8  and     r8d, 3
0x14000d5dc  mov     ebp, 40h ; '@'
0x14000d5e1  shl     r8d, 2
0x14000d5e5  and     ecx, ebp
0x14000d5e7  or      r8d, ecx
0x14000d5ea  shl     r8d, 2
0x14000d5ee  or      r8d, eax
0x14000d5f1  shl     r8d, 3
0x14000d5f5  test    edx, edx
0x14000d5f7  jnz     short loc_14000D5FD
0x14000d5f9  mov     eax, ebp
0x14000d5fb  jmp     short loc_14000D605
0x14000d5fd  xor     eax, eax
0x14000d5ff  cmp     edx, 2
0x14000d602  cmovz   eax, ebp
0x14000d605  or      r8d, eax
0x14000d608  mov     edi, 1
0x14000d60d  mov     [rbx], r8d
0x14000d610  bt      r8d, 0Ah
0x14000d615  jnb     short loc_14000D625
0x14000d617  cmp     r8d, 800h
0x14000d61e  jb      short loc_14000D625
0x14000d620  mov     sil, dil
0x14000d623  jmp     short loc_14000D62F
0x14000d625  xor     sil, sil
0x14000d628  xor     al, al
0x14000d62a  test    bpl, r8b
0x14000d62d  jz      short loc_14000D648
0x14000d62f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UexTest7@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7> `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl(void)'::`2'::impl
0x14000d636  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x14000d63b  test    sil, sil
0x14000d63e  jz      short loc_14000D648
0x14000d640  test    al, al
0x14000d642  jnz     short loc_14000D648
0x14000d644  btr     dword ptr [rbx], 0Ah
0x14000d648  mov     ecx, [rbx]
0x14000d64a  test    bpl, cl
0x14000d64d  jz      short loc_14000D653
0x14000d64f  test    al, al
0x14000d651  jnz     short loc_14000D655
0x14000d653  xor     edi, edi
0x14000d655  and     ecx, 0FFFFFFFEh
0x14000d658  mov     rax, rbx
0x14000d65b  or      ecx, edi
0x14000d65d  mov     [rbx], ecx
0x14000d65f  add     rsp, 28h
0x14000d663  pop     rdi
0x14000d664  pop     rsi
0x14000d665  pop     rbp
0x14000d666  pop     rbx
0x14000d667  retn
```
