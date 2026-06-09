# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_BufferCollection>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800232bc`
- end: `0x180023380`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_BufferCollection@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180022ef8`

## callees

- `0x180012298`
- `0x1800232bc`
- `0x18002410c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_BufferCollection>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3174252, 3u, a3, a4);
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
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID45522024>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID45522024>::GetImpl'::`2'::impl);
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
0x1800232bc  push    rbx
0x1800232be  push    rbp
0x1800232bf  push    rsi
0x1800232c0  push    rdi
0x1800232c1  sub     rsp, 28h
0x1800232c5  mov     rbx, rdx
0x1800232c8  mov     ecx, 3174252h; this
0x1800232cd  mov     edx, 3; unsigned int
0x1800232d2  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800232d7  mov     edx, eax
0x1800232d9  mov     qword ptr [rbx], 0
0x1800232e0  and     edx, 0FFFFFF3Fh
0x1800232e6  mov     ecx, eax
0x1800232e8  and     eax, 80h
0x1800232ed  mov     r8d, edx
0x1800232f0  and     r8d, 3
0x1800232f4  mov     ebp, 40h ; '@'
0x1800232f9  shl     r8d, 2
0x1800232fd  and     ecx, ebp
0x1800232ff  or      r8d, ecx
0x180023302  shl     r8d, 2
0x180023306  or      r8d, eax
0x180023309  shl     r8d, 3
0x18002330d  test    edx, edx
0x18002330f  jnz     short loc_180023315
0x180023311  mov     eax, ebp
0x180023313  jmp     short loc_18002331D
0x180023315  xor     eax, eax
0x180023317  cmp     edx, 2
0x18002331a  cmovz   eax, ebp
0x18002331d  or      r8d, eax
0x180023320  mov     edi, 1
0x180023325  mov     [rbx], r8d
0x180023328  bt      r8d, 0Ah
0x18002332d  jnb     short loc_18002333D
0x18002332f  cmp     r8d, 800h
0x180023336  jb      short loc_18002333D
0x180023338  mov     sil, dil
0x18002333b  jmp     short loc_180023347
0x18002333d  xor     sil, sil
0x180023340  xor     al, al
0x180023342  test    bpl, r8b
0x180023345  jz      short loc_180023360
0x180023347  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID45522024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID45522024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID45522024> `wil::Feature<__WilFeatureTraits_Feature_ID45522024>::GetImpl(void)'::`2'::impl
0x18002334e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID45522024@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID45522024>::__private_IsEnabled(wil::ReportingKind)
0x180023353  test    sil, sil
0x180023356  jz      short loc_180023360
0x180023358  test    al, al
0x18002335a  jnz     short loc_180023360
0x18002335c  btr     dword ptr [rbx], 0Ah
0x180023360  mov     ecx, [rbx]
0x180023362  test    bpl, cl
0x180023365  jz      short loc_18002336B
0x180023367  test    al, al
0x180023369  jnz     short loc_18002336D
0x18002336b  xor     edi, edi
0x18002336d  and     ecx, 0FFFFFFFEh
0x180023370  mov     rax, rbx
0x180023373  or      ecx, edi
0x180023375  mov     [rbx], ecx
0x180023377  add     rsp, 28h
0x18002337b  pop     rdi
0x18002337c  pop     rsi
0x18002337d  pop     rbp
0x18002337e  pop     rbx
0x18002337f  retn
```
