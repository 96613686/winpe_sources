# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001442c`
- end: `0x180014517`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `235`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180013ae8`

## callees

- `0x180012fa8`
- `0x180013c28`
- `0x18001442c`
- `0x1800157f4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  int v7; // ecx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // cl
  wil::details *v13; // rcx
  wil::details *v14; // rcx
  __int64 v16; // [rsp+30h] [rbp+8h] BYREF

  v16 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CA7, (unsigned int)a2, a3, a4);
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
0x18001442c  mov     [rsp+arg_8], rbx
0x180014431  mov     [rsp+arg_10], rsi
0x180014436  mov     [rsp+arg_0], rcx
0x18001443b  push    rdi
0x18001443c  sub     rsp, 20h
0x180014440  mov     ecx, 3667CA7h; this
0x180014445  mov     rbx, rdx
0x180014448  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001444d  mov     edx, eax
0x18001444f  mov     qword ptr [rbx], 0
0x180014456  and     edx, 0FFFFFF3Fh
0x18001445c  mov     ecx, eax
0x18001445e  and     eax, 80h
0x180014463  mov     r8d, edx
0x180014466  and     r8d, 3
0x18001446a  mov     esi, 40h ; '@'
0x18001446f  shl     r8d, 2
0x180014473  and     ecx, esi
0x180014475  or      r8d, ecx
0x180014478  shl     r8d, 2
0x18001447c  or      r8d, eax
0x18001447f  shl     r8d, 3
0x180014483  test    edx, edx
0x180014485  jnz     short loc_18001448D
0x180014487  mov     ecx, esi
0x180014489  mov     edx, esi
0x18001448b  jmp     short loc_180014497
0x18001448d  xor     ecx, ecx
0x18001448f  cmp     edx, 2
0x180014492  cmovz   ecx, esi
0x180014495  mov     edx, ecx
0x180014497  mov     eax, r8d
0x18001449a  mov     edi, 1
0x18001449f  or      eax, edx
0x1800144a1  or      r8d, ecx
0x1800144a4  mov     [rbx], eax
0x1800144a6  bt      r8d, 0Ah
0x1800144ab  jnb     short loc_1800144B6
0x1800144ad  cmp     r8d, 800h
0x1800144b4  jnb     short loc_1800144BD
0x1800144b6  xor     cl, cl
0x1800144b8  test    sil, r8b
0x1800144bb  jz      short loc_1800144F0
0x1800144bd  mov     rax, cs:Feature_ValLabTest__descriptor
0x1800144c4  mov     ecx, [rax]
0x1800144c6  test    cl, 4
0x1800144c9  jnz     short loc_1800144D5
0x1800144cb  lea     rdx, [rsp+28h+arg_0]
0x1800144d0  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x1800144d5  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x1800144dc  mov     ecx, [rax]
0x1800144de  test    cl, 4
0x1800144e1  jnz     short loc_1800144ED
0x1800144e3  lea     rdx, [rsp+28h+arg_0]
0x1800144e8  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x1800144ed  mov     cl, dil
0x1800144f0  mov     eax, [rbx]
0x1800144f2  test    sil, al
0x1800144f5  jz      short loc_1800144FB
0x1800144f7  test    cl, cl
0x1800144f9  jnz     short loc_1800144FD
0x1800144fb  xor     edi, edi
0x1800144fd  mov     rsi, [rsp+28h+arg_10]
0x180014502  and     eax, 0FFFFFFFEh
0x180014505  or      eax, edi
0x180014507  mov     [rbx], eax
0x180014509  mov     rax, rbx
0x18001450c  mov     rbx, [rsp+28h+arg_8]
0x180014511  add     rsp, 20h
0x180014515  pop     rdi
0x180014516  retn
```
