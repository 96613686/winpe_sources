# wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180013d68`
- end: `0x180013e20`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `184`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012ec0`

## callees

- `0x180013d68`
- `0x1800157f4`
- `0x180015aa4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x313424C, (unsigned int)a2, a3, a4);
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
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled();
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
0x180013d68  push    rbx
0x180013d6a  push    rbp
0x180013d6b  push    rsi
0x180013d6c  push    rdi
0x180013d6d  sub     rsp, 28h
0x180013d71  mov     ecx, 313424Ch; this
0x180013d76  mov     rbx, rdx
0x180013d79  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180013d7e  mov     edx, eax
0x180013d80  mov     qword ptr [rbx], 0
0x180013d87  and     edx, 0FFFFFF3Fh
0x180013d8d  mov     ecx, eax
0x180013d8f  and     eax, 80h
0x180013d94  mov     r8d, edx
0x180013d97  and     r8d, 3
0x180013d9b  mov     ebp, 40h ; '@'
0x180013da0  shl     r8d, 2
0x180013da4  and     ecx, ebp
0x180013da6  or      r8d, ecx
0x180013da9  shl     r8d, 2
0x180013dad  or      r8d, eax
0x180013db0  shl     r8d, 3
0x180013db4  test    edx, edx
0x180013db6  jnz     short loc_180013DBC
0x180013db8  mov     eax, ebp
0x180013dba  jmp     short loc_180013DC4
0x180013dbc  xor     eax, eax
0x180013dbe  cmp     edx, 2
0x180013dc1  cmovz   eax, ebp
0x180013dc4  or      r8d, eax
0x180013dc7  mov     edi, 1
0x180013dcc  mov     [rbx], r8d
0x180013dcf  bt      r8d, 0Ah
0x180013dd4  jnb     short loc_180013DE4
0x180013dd6  cmp     r8d, 800h
0x180013ddd  jb      short loc_180013DE4
0x180013ddf  mov     sil, dil
0x180013de2  jmp     short loc_180013DEE
0x180013de4  xor     sil, sil
0x180013de7  xor     al, al
0x180013de9  test    bpl, r8b
0x180013dec  jz      short loc_180013E00
0x180013dee  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x180013df3  test    sil, sil
0x180013df6  jz      short loc_180013E00
0x180013df8  test    al, al
0x180013dfa  jnz     short loc_180013E00
0x180013dfc  btr     dword ptr [rbx], 0Ah
0x180013e00  mov     ecx, [rbx]
0x180013e02  test    bpl, cl
0x180013e05  jz      short loc_180013E0B
0x180013e07  test    al, al
0x180013e09  jnz     short loc_180013E0D
0x180013e0b  xor     edi, edi
0x180013e0d  and     ecx, 0FFFFFFFEh
0x180013e10  mov     rax, rbx
0x180013e13  or      ecx, edi
0x180013e15  mov     [rbx], ecx
0x180013e17  add     rsp, 28h
0x180013e1b  pop     rdi
0x180013e1c  pop     rsi
0x180013e1d  pop     rbp
0x180013e1e  pop     rbx
0x180013e1f  retn
```
