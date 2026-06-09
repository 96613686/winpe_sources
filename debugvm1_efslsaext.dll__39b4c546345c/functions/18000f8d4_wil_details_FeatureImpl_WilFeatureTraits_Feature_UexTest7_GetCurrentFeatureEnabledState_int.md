# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000f8d4`
- end: `0x18000f9e1`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f258`

## callees

- `0x18000ee44`
- `0x18000f8d4`
- `0x1800115d8`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // edx
  __int64 v7; // rcx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // edx
  char v12; // si
  wil::details *v13; // rcx
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF

  v15 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(58989021, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( v5 )
  {
    v7 = 0;
    if ( v5 == 2 )
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
      goto LABEL_22;
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
LABEL_22:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18000f8d4  mov     [rsp+arg_0], rcx
0x18000f8d9  push    rbx
0x18000f8da  push    rbp
0x18000f8db  push    rsi
0x18000f8dc  push    rdi
0x18000f8dd  sub     rsp, 28h
0x18000f8e1  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000f8e8  mov     rbx, rdx
0x18000f8eb  mov     edi, 3
0x18000f8f0  test    rax, rax
0x18000f8f3  jz      short loc_18000F905
0x18000f8f5  mov     edx, edi
0x18000f8f7  mov     ecx, 38419DDh
0x18000f8fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f901  mov     edx, eax
0x18000f903  jmp     short loc_18000F913
0x18000f905  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000f90c  test    rax, rax
0x18000f90f  jnz     short loc_18000F8F5
0x18000f911  xor     edx, edx
0x18000f913  mov     r8d, edx
0x18000f916  mov     qword ptr [rbx], 0
0x18000f91d  mov     eax, edx
0x18000f91f  and     r8d, 0FFFFFF3Fh
0x18000f926  and     edx, 80h
0x18000f92c  mov     ecx, r8d
0x18000f92f  and     ecx, edi
0x18000f931  mov     ebp, 40h ; '@'
0x18000f936  shl     ecx, 2
0x18000f939  and     eax, ebp
0x18000f93b  or      ecx, eax
0x18000f93d  shl     ecx, 2
0x18000f940  or      ecx, edx
0x18000f942  lea     edx, ds:0[rcx*8]
0x18000f949  test    r8d, r8d
0x18000f94c  jnz     short loc_18000F955
0x18000f94e  mov     ecx, ebp
0x18000f950  mov     r8d, ebp
0x18000f953  jmp     short loc_18000F961
0x18000f955  xor     ecx, ecx
0x18000f957  cmp     r8d, 2
0x18000f95b  cmovz   ecx, ebp
0x18000f95e  mov     r8d, ecx
0x18000f961  mov     eax, edx
0x18000f963  mov     edi, 1
0x18000f968  or      eax, r8d
0x18000f96b  or      edx, ecx
0x18000f96d  mov     [rbx], eax
0x18000f96f  bt      edx, 0Ah
0x18000f973  jnb     short loc_18000F982
0x18000f975  cmp     edx, 800h
0x18000f97b  jb      short loc_18000F982
0x18000f97d  mov     sil, dil
0x18000f980  jmp     short loc_18000F98C
0x18000f982  xor     sil, sil
0x18000f985  xor     cl, cl
0x18000f987  test    bpl, dl
0x18000f98a  jz      short loc_18000F9C1
0x18000f98c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x18000f991  test    al, al
0x18000f993  jz      short loc_18000F9B2
0x18000f995  mov     rax, cs:Feature_Standalone_26_03_NonSec__descriptor
0x18000f99c  mov     ecx, [rax]
0x18000f99e  test    cl, 4
0x18000f9a1  jnz     short loc_18000F9AD
0x18000f9a3  lea     rdx, [rsp+48h+arg_0]
0x18000f9a8  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)
0x18000f9ad  mov     cl, dil
0x18000f9b0  jmp     short loc_18000F9B4
0x18000f9b2  xor     cl, cl
0x18000f9b4  test    sil, sil
0x18000f9b7  jz      short loc_18000F9C1
0x18000f9b9  test    cl, cl
0x18000f9bb  jnz     short loc_18000F9C1
0x18000f9bd  btr     dword ptr [rbx], 0Ah
0x18000f9c1  mov     eax, [rbx]
0x18000f9c3  test    bpl, al
0x18000f9c6  jz      short loc_18000F9CC
0x18000f9c8  test    cl, cl
0x18000f9ca  jnz     short loc_18000F9CE
0x18000f9cc  xor     edi, edi
0x18000f9ce  and     eax, 0FFFFFFFEh
0x18000f9d1  or      eax, edi
0x18000f9d3  mov     [rbx], eax
0x18000f9d5  mov     rax, rbx
0x18000f9d8  add     rsp, 28h
0x18000f9dc  pop     rdi
0x18000f9dd  pop     rsi
0x18000f9de  pop     rbp
0x18000f9df  pop     rbx
0x18000f9e0  retn
```
