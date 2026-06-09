# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000f9e8`
- end: `0x18000faf5`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f338`

## callees

- `0x18000e874`
- `0x18000f418`
- `0x18000f9e8`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // edx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // ecx
  char v12; // dl
  wil::details *v13; // rcx
  wil::details *v14; // rcx
  __int64 v16; // [rsp+30h] [rbp+8h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(57048231, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) != 0 )
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
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 || (v12 = 0, (v11 & 0x40) != 0) )
  {
    v13 = (wil::details *)*(unsigned int *)Feature_ValLabTest__descriptor;
    if ( ((unsigned __int8)v13 & 4) == 0 )
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(v13, &v16);
    v14 = (wil::details *)*(unsigned int *)Feature_Standalone_25_10_NonSec__descriptor;
    if ( ((unsigned __int8)v14 & 4) == 0 )
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
        v14,
        &v16);
    v12 = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v12 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18000f9e8  mov     [rsp+arg_8], rbx
0x18000f9ed  mov     [rsp+arg_10], rsi
0x18000f9f2  mov     [rsp+arg_0], rcx
0x18000f9f7  push    rdi
0x18000f9f8  sub     rsp, 20h
0x18000f9fc  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000fa03  mov     rbx, rdx
0x18000fa06  mov     edi, 3
0x18000fa0b  test    rax, rax
0x18000fa0e  jz      short loc_18000FA20
0x18000fa10  mov     edx, edi
0x18000fa12  mov     ecx, 3667CA7h
0x18000fa17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa1c  mov     edx, eax
0x18000fa1e  jmp     short loc_18000FA2E
0x18000fa20  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000fa27  test    rax, rax
0x18000fa2a  jnz     short loc_18000FA10
0x18000fa2c  xor     edx, edx
0x18000fa2e  mov     r8d, edx
0x18000fa31  mov     qword ptr [rbx], 0
0x18000fa38  and     r8d, 0FFFFFF3Fh
0x18000fa3f  mov     eax, edx
0x18000fa41  and     edx, 80h
0x18000fa47  mov     ecx, r8d
0x18000fa4a  and     ecx, edi
0x18000fa4c  mov     esi, 40h ; '@'
0x18000fa51  shl     ecx, 2
0x18000fa54  and     eax, esi
0x18000fa56  or      ecx, eax
0x18000fa58  shl     ecx, 2
0x18000fa5b  or      ecx, edx
0x18000fa5d  shl     ecx, 3
0x18000fa60  test    r8d, r8d
0x18000fa63  jnz     short loc_18000FA6C
0x18000fa65  mov     edx, esi
0x18000fa67  mov     r8d, esi
0x18000fa6a  jmp     short loc_18000FA78
0x18000fa6c  xor     edx, edx
0x18000fa6e  cmp     r8d, 2
0x18000fa72  cmovz   edx, esi
0x18000fa75  mov     r8d, edx
0x18000fa78  mov     eax, ecx
0x18000fa7a  mov     edi, 1
0x18000fa7f  or      eax, r8d
0x18000fa82  or      ecx, edx
0x18000fa84  mov     [rbx], eax
0x18000fa86  bt      ecx, 0Ah
0x18000fa8a  jnb     short loc_18000FA94
0x18000fa8c  cmp     ecx, 800h
0x18000fa92  jnb     short loc_18000FA9B
0x18000fa94  xor     dl, dl
0x18000fa96  test    sil, cl
0x18000fa99  jz      short loc_18000FACE
0x18000fa9b  mov     rax, cs:Feature_ValLabTest__descriptor
0x18000faa2  mov     ecx, [rax]
0x18000faa4  test    cl, 4
0x18000faa7  jnz     short loc_18000FAB3
0x18000faa9  lea     rdx, [rsp+28h+arg_0]
0x18000faae  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x18000fab3  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18000faba  mov     ecx, [rax]
0x18000fabc  test    cl, 4
0x18000fabf  jnz     short loc_18000FACB
0x18000fac1  lea     rdx, [rsp+28h+arg_0]
0x18000fac6  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x18000facb  mov     dl, dil
0x18000face  mov     eax, [rbx]
0x18000fad0  test    sil, al
0x18000fad3  jz      short loc_18000FAD9
0x18000fad5  test    dl, dl
0x18000fad7  jnz     short loc_18000FADB
0x18000fad9  xor     edi, edi
0x18000fadb  mov     rsi, [rsp+28h+arg_10]
0x18000fae0  and     eax, 0FFFFFFFEh
0x18000fae3  or      eax, edi
0x18000fae5  mov     [rbx], eax
0x18000fae7  mov     rax, rbx
0x18000faea  mov     rbx, [rsp+28h+arg_8]
0x18000faef  add     rsp, 20h
0x18000faf3  pop     rdi
0x18000faf4  retn
```
