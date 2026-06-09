# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001433c`
- end: `0x180014423`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `231`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800139a8`

## callees

- `0x1800134a8`
- `0x18001433c`
- `0x1800157f4`
- `0x180015a20`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  __int64 v7; // rcx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // si
  wil::details *v13; // rcx
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF

  v15 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419DD, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( (FeatureEnabledState & 0xFFFFFF3F) == 2 )
      v7 = 64;
    v8 = v7;
  }
  else
  {
    v7 = 64;
    v8 = 64;
  }
  v9 = 1;
  v10 = v8 | v6;
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    LOBYTE(v7) = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_18;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(v7) )
  {
    v13 = (wil::details *)*(unsigned int *)Feature_Standalone_26_03_NonSec__descriptor;
    if ( ((unsigned __int8)v13 & 4) == 0 )
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(
        v13,
        &v15);
    LOBYTE(v7) = 1;
  }
  else
  {
    LOBYTE(v7) = 0;
  }
  if ( v12 && !(_BYTE)v7 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_18:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18001433c  mov     [rsp+arg_0], rcx
0x180014341  push    rbx
0x180014342  push    rbp
0x180014343  push    rsi
0x180014344  push    rdi
0x180014345  sub     rsp, 28h
0x180014349  mov     ecx, 38419DDh; this
0x18001434e  mov     rbx, rdx
0x180014351  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180014356  mov     edx, eax
0x180014358  mov     qword ptr [rbx], 0
0x18001435f  and     edx, 0FFFFFF3Fh
0x180014365  mov     ecx, eax
0x180014367  and     eax, 80h
0x18001436c  mov     r8d, edx
0x18001436f  and     r8d, 3
0x180014373  mov     ebp, 40h ; '@'
0x180014378  shl     r8d, 2
0x18001437c  and     ecx, ebp
0x18001437e  or      r8d, ecx
0x180014381  shl     r8d, 2
0x180014385  or      r8d, eax
0x180014388  shl     r8d, 3
0x18001438c  test    edx, edx
0x18001438e  jnz     short loc_180014396
0x180014390  mov     ecx, ebp
0x180014392  mov     edx, ebp
0x180014394  jmp     short loc_1800143A0
0x180014396  xor     ecx, ecx
0x180014398  cmp     edx, 2
0x18001439b  cmovz   ecx, ebp
0x18001439e  mov     edx, ecx
0x1800143a0  mov     eax, r8d
0x1800143a3  mov     edi, 1
0x1800143a8  or      eax, edx
0x1800143aa  or      r8d, ecx
0x1800143ad  mov     [rbx], eax
0x1800143af  bt      r8d, 0Ah
0x1800143b4  jnb     short loc_1800143C4
0x1800143b6  cmp     r8d, 800h
0x1800143bd  jb      short loc_1800143C4
0x1800143bf  mov     sil, dil
0x1800143c2  jmp     short loc_1800143CE
0x1800143c4  xor     sil, sil
0x1800143c7  xor     cl, cl
0x1800143c9  test    bpl, r8b
0x1800143cc  jz      short loc_180014403
0x1800143ce  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x1800143d3  test    al, al
0x1800143d5  jz      short loc_1800143F4
0x1800143d7  mov     rax, cs:Feature_Standalone_26_03_NonSec__descriptor
0x1800143de  mov     ecx, [rax]
0x1800143e0  test    cl, 4
0x1800143e3  jnz     short loc_1800143EF
0x1800143e5  lea     rdx, [rsp+48h+arg_0]
0x1800143ea  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)
0x1800143ef  mov     cl, dil
0x1800143f2  jmp     short loc_1800143F6
0x1800143f4  xor     cl, cl
0x1800143f6  test    sil, sil
0x1800143f9  jz      short loc_180014403
0x1800143fb  test    cl, cl
0x1800143fd  jnz     short loc_180014403
0x1800143ff  btr     dword ptr [rbx], 0Ah
0x180014403  mov     eax, [rbx]
0x180014405  test    bpl, al
0x180014408  jz      short loc_18001440E
0x18001440a  test    cl, cl
0x18001440c  jnz     short loc_180014410
0x18001440e  xor     edi, edi
0x180014410  and     eax, 0FFFFFFFEh
0x180014413  or      eax, edi
0x180014415  mov     [rbx], eax
0x180014417  mov     rax, rbx
0x18001441a  add     rsp, 28h
0x18001441e  pop     rdi
0x18001441f  pop     rsi
0x180014420  pop     rbp
0x180014421  pop     rbx
0x180014422  retn
```
