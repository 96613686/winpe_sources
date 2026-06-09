# wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001b7f4`
- end: `0x18001b8ad`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b554`

## callees

- `0x18001b7f4`
- `0x18001beec`
- `0x18001bf54`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // edx
  int v7; // r8d
  int v8; // eax
  int v9; // edi
  char v10; // si
  char IsEnabled; // al
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x35E0AE8, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v8 = 0;
    if ( v6 == 2 )
      v8 = 64;
    v7 |= v8;
  }
  *(_DWORD *)a2 = v7;
  v9 = 1;
  if ( (v7 & 0xC00) == 0xC00 )
  {
    v10 = 1;
  }
  else
  {
    v10 = 0;
    IsEnabled = 0;
    if ( (v7 & 0x40) == 0 )
      goto LABEL_11;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
  if ( v10 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_11:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !IsEnabled )
    v9 = 0;
  result = a2;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x18001b7f4  push    rbx
0x18001b7f6  push    rbp
0x18001b7f7  push    rsi
0x18001b7f8  push    rdi
0x18001b7f9  sub     rsp, 28h
0x18001b7fd  mov     ecx, 35E0AE8h; this
0x18001b802  mov     rbx, rdx
0x18001b805  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001b80a  mov     edx, eax
0x18001b80c  mov     qword ptr [rbx], 0
0x18001b813  and     edx, 0FFFFFF3Fh
0x18001b819  mov     ecx, eax
0x18001b81b  and     eax, 80h
0x18001b820  mov     r8d, edx
0x18001b823  and     r8d, 3
0x18001b827  mov     ebp, 40h ; '@'
0x18001b82c  shl     r8d, 2
0x18001b830  and     ecx, ebp
0x18001b832  or      r8d, ecx
0x18001b835  shl     r8d, 2
0x18001b839  or      r8d, eax
0x18001b83c  shl     r8d, 3
0x18001b840  test    edx, edx
0x18001b842  jz      short loc_18001B84F
0x18001b844  xor     eax, eax
0x18001b846  cmp     edx, 2
0x18001b849  cmovz   eax, ebp
0x18001b84c  or      r8d, eax
0x18001b84f  mov     ecx, 0C00h
0x18001b854  mov     [rbx], r8d
0x18001b857  mov     eax, r8d
0x18001b85a  mov     edi, 1
0x18001b85f  and     eax, ecx
0x18001b861  cmp     eax, ecx
0x18001b863  jnz     short loc_18001B86A
0x18001b865  mov     sil, dil
0x18001b868  jmp     short loc_18001B874
0x18001b86a  xor     sil, sil
0x18001b86d  xor     al, al
0x18001b86f  test    bpl, r8b
0x18001b872  jz      short loc_18001B88D
0x18001b874  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18001b87b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18001b880  test    sil, sil
0x18001b883  jz      short loc_18001B88D
0x18001b885  test    al, al
0x18001b887  jnz     short loc_18001B88D
0x18001b889  btr     dword ptr [rbx], 0Ah
0x18001b88d  mov     ecx, [rbx]
0x18001b88f  test    bpl, cl
0x18001b892  jz      short loc_18001B898
0x18001b894  test    al, al
0x18001b896  jnz     short loc_18001B89A
0x18001b898  xor     edi, edi
0x18001b89a  and     ecx, 0FFFFFFFEh
0x18001b89d  mov     rax, rbx
0x18001b8a0  or      ecx, edi
0x18001b8a2  mov     [rbx], ecx
0x18001b8a4  add     rsp, 28h
0x18001b8a8  pop     rdi
0x18001b8a9  pop     rsi
0x18001b8aa  pop     rbp
0x18001b8ab  pop     rbx
0x18001b8ac  retn
```
