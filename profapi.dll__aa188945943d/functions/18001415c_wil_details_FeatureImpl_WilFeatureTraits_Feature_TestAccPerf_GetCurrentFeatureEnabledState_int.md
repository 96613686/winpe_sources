# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001415c`
- end: `0x180014243`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `231`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180013728`

## callees

- `0x1800130e8`
- `0x18001415c`
- `0x1800157f4`
- `0x180015ad0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
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
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CAD, (unsigned int)a2, a3, a4);
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
LABEL_18:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18001415c  mov     [rsp+arg_0], rcx
0x180014161  push    rbx
0x180014162  push    rbp
0x180014163  push    rsi
0x180014164  push    rdi
0x180014165  sub     rsp, 28h
0x180014169  mov     ecx, 3667CADh; this
0x18001416e  mov     rbx, rdx
0x180014171  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180014176  mov     edx, eax
0x180014178  mov     qword ptr [rbx], 0
0x18001417f  and     edx, 0FFFFFF3Fh
0x180014185  mov     ecx, eax
0x180014187  and     eax, 80h
0x18001418c  mov     r8d, edx
0x18001418f  and     r8d, 3
0x180014193  mov     ebp, 40h ; '@'
0x180014198  shl     r8d, 2
0x18001419c  and     ecx, ebp
0x18001419e  or      r8d, ecx
0x1800141a1  shl     r8d, 2
0x1800141a5  or      r8d, eax
0x1800141a8  shl     r8d, 3
0x1800141ac  test    edx, edx
0x1800141ae  jnz     short loc_1800141B6
0x1800141b0  mov     ecx, ebp
0x1800141b2  mov     edx, ebp
0x1800141b4  jmp     short loc_1800141C0
0x1800141b6  xor     ecx, ecx
0x1800141b8  cmp     edx, 2
0x1800141bb  cmovz   ecx, ebp
0x1800141be  mov     edx, ecx
0x1800141c0  mov     eax, r8d
0x1800141c3  mov     edi, 1
0x1800141c8  or      eax, edx
0x1800141ca  or      r8d, ecx
0x1800141cd  mov     [rbx], eax
0x1800141cf  bt      r8d, 0Ah
0x1800141d4  jnb     short loc_1800141E4
0x1800141d6  cmp     r8d, 800h
0x1800141dd  jb      short loc_1800141E4
0x1800141df  mov     sil, dil
0x1800141e2  jmp     short loc_1800141EE
0x1800141e4  xor     sil, sil
0x1800141e7  xor     cl, cl
0x1800141e9  test    bpl, r8b
0x1800141ec  jz      short loc_180014223
0x1800141ee  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x1800141f3  test    al, al
0x1800141f5  jz      short loc_180014214
0x1800141f7  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x1800141fe  mov     ecx, [rax]
0x180014200  test    cl, 4
0x180014203  jnz     short loc_18001420F
0x180014205  lea     rdx, [rsp+48h+arg_0]
0x18001420a  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x18001420f  mov     cl, dil
0x180014212  jmp     short loc_180014216
0x180014214  xor     cl, cl
0x180014216  test    sil, sil
0x180014219  jz      short loc_180014223
0x18001421b  test    cl, cl
0x18001421d  jnz     short loc_180014223
0x18001421f  btr     dword ptr [rbx], 0Ah
0x180014223  mov     eax, [rbx]
0x180014225  test    bpl, al
0x180014228  jz      short loc_18001422E
0x18001422a  test    cl, cl
0x18001422c  jnz     short loc_180014230
0x18001422e  xor     edi, edi
0x180014230  and     eax, 0FFFFFFFEh
0x180014233  or      eax, edi
0x180014235  mov     [rbx], eax
0x180014237  mov     rax, rbx
0x18001423a  add     rsp, 28h
0x18001423e  pop     rdi
0x18001423f  pop     rsi
0x180014240  pop     rbp
0x180014241  pop     rbx
0x180014242  retn
```
