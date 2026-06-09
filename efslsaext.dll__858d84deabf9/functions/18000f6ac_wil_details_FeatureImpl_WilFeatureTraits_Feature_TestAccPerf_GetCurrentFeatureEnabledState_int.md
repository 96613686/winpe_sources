# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000f6ac`
- end: `0x18000f7b9`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f098`

## callees

- `0x18000e9e8`
- `0x18000f6ac`
- `0x1800116e8`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
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
    v4 = v2(57048237, 3);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(v7) )
  {
    v13 = (wil::details *)*(unsigned int *)Feature_Standalone_25_11_NonSec__descriptor;
    if ( ((unsigned __int8)v13 & 4) == 0 )
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
0x18000f6ac  mov     [rsp+arg_0], rcx
0x18000f6b1  push    rbx
0x18000f6b2  push    rbp
0x18000f6b3  push    rsi
0x18000f6b4  push    rdi
0x18000f6b5  sub     rsp, 28h
0x18000f6b9  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000f6c0  mov     rbx, rdx
0x18000f6c3  mov     edi, 3
0x18000f6c8  test    rax, rax
0x18000f6cb  jz      short loc_18000F6DD
0x18000f6cd  mov     edx, edi
0x18000f6cf  mov     ecx, 3667CADh
0x18000f6d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6d9  mov     edx, eax
0x18000f6db  jmp     short loc_18000F6EB
0x18000f6dd  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000f6e4  test    rax, rax
0x18000f6e7  jnz     short loc_18000F6CD
0x18000f6e9  xor     edx, edx
0x18000f6eb  mov     r8d, edx
0x18000f6ee  mov     qword ptr [rbx], 0
0x18000f6f5  mov     eax, edx
0x18000f6f7  and     r8d, 0FFFFFF3Fh
0x18000f6fe  and     edx, 80h
0x18000f704  mov     ecx, r8d
0x18000f707  and     ecx, edi
0x18000f709  mov     ebp, 40h ; '@'
0x18000f70e  shl     ecx, 2
0x18000f711  and     eax, ebp
0x18000f713  or      ecx, eax
0x18000f715  shl     ecx, 2
0x18000f718  or      ecx, edx
0x18000f71a  lea     edx, ds:0[rcx*8]
0x18000f721  test    r8d, r8d
0x18000f724  jnz     short loc_18000F72D
0x18000f726  mov     ecx, ebp
0x18000f728  mov     r8d, ebp
0x18000f72b  jmp     short loc_18000F739
0x18000f72d  xor     ecx, ecx
0x18000f72f  cmp     r8d, 2
0x18000f733  cmovz   ecx, ebp
0x18000f736  mov     r8d, ecx
0x18000f739  mov     eax, edx
0x18000f73b  mov     edi, 1
0x18000f740  or      eax, r8d
0x18000f743  or      edx, ecx
0x18000f745  mov     [rbx], eax
0x18000f747  bt      edx, 0Ah
0x18000f74b  jnb     short loc_18000F75A
0x18000f74d  cmp     edx, 800h
0x18000f753  jb      short loc_18000F75A
0x18000f755  mov     sil, dil
0x18000f758  jmp     short loc_18000F764
0x18000f75a  xor     sil, sil
0x18000f75d  xor     cl, cl
0x18000f75f  test    bpl, dl
0x18000f762  jz      short loc_18000F799
0x18000f764  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x18000f769  test    al, al
0x18000f76b  jz      short loc_18000F78A
0x18000f76d  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18000f774  mov     ecx, [rax]
0x18000f776  test    cl, 4
0x18000f779  jnz     short loc_18000F785
0x18000f77b  lea     rdx, [rsp+48h+arg_0]
0x18000f780  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x18000f785  mov     cl, dil
0x18000f788  jmp     short loc_18000F78C
0x18000f78a  xor     cl, cl
0x18000f78c  test    sil, sil
0x18000f78f  jz      short loc_18000F799
0x18000f791  test    cl, cl
0x18000f793  jnz     short loc_18000F799
0x18000f795  btr     dword ptr [rbx], 0Ah
0x18000f799  mov     eax, [rbx]
0x18000f79b  test    bpl, al
0x18000f79e  jz      short loc_18000F7A4
0x18000f7a0  test    cl, cl
0x18000f7a2  jnz     short loc_18000F7A6
0x18000f7a4  xor     edi, edi
0x18000f7a6  and     eax, 0FFFFFFFEh
0x18000f7a9  or      eax, edi
0x18000f7ab  mov     [rbx], eax
0x18000f7ad  mov     rax, rbx
0x18000f7b0  add     rsp, 28h
0x18000f7b4  pop     rdi
0x18000f7b5  pop     rsi
0x18000f7b6  pop     rbp
0x18000f7b7  pop     rbx
0x18000f7b8  retn
```
