# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800105b4`
- end: `0x180010678`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_COMApartmentFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000fe34`

## callees

- `0x1800105b4`
- `0x180012298`
- `0x18001237c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38A3681, 3u, a3, a4);
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
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl);
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
0x1800105b4  push    rbx
0x1800105b6  push    rbp
0x1800105b7  push    rsi
0x1800105b8  push    rdi
0x1800105b9  sub     rsp, 28h
0x1800105bd  mov     rbx, rdx
0x1800105c0  mov     ecx, 38A3681h; this
0x1800105c5  mov     edx, 3; unsigned int
0x1800105ca  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800105cf  mov     edx, eax
0x1800105d1  mov     qword ptr [rbx], 0
0x1800105d8  and     edx, 0FFFFFF3Fh
0x1800105de  mov     ecx, eax
0x1800105e0  and     eax, 80h
0x1800105e5  mov     r8d, edx
0x1800105e8  and     r8d, 3
0x1800105ec  mov     ebp, 40h ; '@'
0x1800105f1  shl     r8d, 2
0x1800105f5  and     ecx, ebp
0x1800105f7  or      r8d, ecx
0x1800105fa  shl     r8d, 2
0x1800105fe  or      r8d, eax
0x180010601  shl     r8d, 3
0x180010605  test    edx, edx
0x180010607  jnz     short loc_18001060D
0x180010609  mov     eax, ebp
0x18001060b  jmp     short loc_180010615
0x18001060d  xor     eax, eax
0x18001060f  cmp     edx, 2
0x180010612  cmovz   eax, ebp
0x180010615  or      r8d, eax
0x180010618  mov     edi, 1
0x18001061d  mov     [rbx], r8d
0x180010620  bt      r8d, 0Ah
0x180010625  jnb     short loc_180010635
0x180010627  cmp     r8d, 800h
0x18001062e  jb      short loc_180010635
0x180010630  mov     sil, dil
0x180010633  jmp     short loc_18001063F
0x180010635  xor     sil, sil
0x180010638  xor     al, al
0x18001063a  test    bpl, r8b
0x18001063d  jz      short loc_180010658
0x18001063f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x180010646  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x18001064b  test    sil, sil
0x18001064e  jz      short loc_180010658
0x180010650  test    al, al
0x180010652  jnz     short loc_180010658
0x180010654  btr     dword ptr [rbx], 0Ah
0x180010658  mov     ecx, [rbx]
0x18001065a  test    bpl, cl
0x18001065d  jz      short loc_180010663
0x18001065f  test    al, al
0x180010661  jnz     short loc_180010665
0x180010663  xor     edi, edi
0x180010665  and     ecx, 0FFFFFFFEh
0x180010668  mov     rax, rbx
0x18001066b  or      ecx, edi
0x18001066d  mov     [rbx], ecx
0x18001066f  add     rsp, 28h
0x180010673  pop     rdi
0x180010674  pop     rsi
0x180010675  pop     rbp
0x180010676  pop     rbx
0x180010677  retn
```
