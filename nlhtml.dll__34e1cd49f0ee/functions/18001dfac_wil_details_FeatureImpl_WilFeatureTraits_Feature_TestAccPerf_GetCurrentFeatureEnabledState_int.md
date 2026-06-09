# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001dfac`
- end: `0x18001e08a`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001d6bc`

## callees

- `0x18001beec`
- `0x18001dfac`
- `0x18001e990`
- `0x18001f040`

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
  int v7; // ecx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // si
  char v13; // cl

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
    v13 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_16;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetImpl'::`2'::impl);
    v13 = 1;
  }
  else
  {
    v13 = 0;
  }
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_16:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18001dfac  push    rbx
0x18001dfae  push    rbp
0x18001dfaf  push    rsi
0x18001dfb0  push    rdi
0x18001dfb1  sub     rsp, 28h
0x18001dfb5  mov     ecx, 3667CADh; this
0x18001dfba  mov     rbx, rdx
0x18001dfbd  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001dfc2  mov     edx, eax
0x18001dfc4  mov     qword ptr [rbx], 0
0x18001dfcb  and     edx, 0FFFFFF3Fh
0x18001dfd1  mov     ecx, eax
0x18001dfd3  and     eax, 80h
0x18001dfd8  mov     r8d, edx
0x18001dfdb  and     r8d, 3
0x18001dfdf  mov     ebp, 40h ; '@'
0x18001dfe4  shl     r8d, 2
0x18001dfe8  and     ecx, ebp
0x18001dfea  or      r8d, ecx
0x18001dfed  shl     r8d, 2
0x18001dff1  or      r8d, eax
0x18001dff4  shl     r8d, 3
0x18001dff8  test    edx, edx
0x18001dffa  jnz     short loc_18001E002
0x18001dffc  mov     ecx, ebp
0x18001dffe  mov     edx, ebp
0x18001e000  jmp     short loc_18001E00C
0x18001e002  xor     ecx, ecx
0x18001e004  cmp     edx, 2
0x18001e007  cmovz   ecx, ebp
0x18001e00a  mov     edx, ecx
0x18001e00c  mov     eax, r8d
0x18001e00f  mov     edi, 1
0x18001e014  or      eax, edx
0x18001e016  or      r8d, ecx
0x18001e019  mov     [rbx], eax
0x18001e01b  bt      r8d, 0Ah
0x18001e020  jnb     short loc_18001E030
0x18001e022  cmp     r8d, 800h
0x18001e029  jb      short loc_18001E030
0x18001e02b  mov     sil, dil
0x18001e02e  jmp     short loc_18001E03A
0x18001e030  xor     sil, sil
0x18001e033  xor     cl, cl
0x18001e035  test    bpl, r8b
0x18001e038  jz      short loc_18001E06A
0x18001e03a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x18001e041  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x18001e046  test    al, al
0x18001e048  jz      short loc_18001E05B
0x18001e04a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetImpl(void)'::`2'::impl
0x18001e051  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001e056  mov     cl, dil
0x18001e059  jmp     short loc_18001E05D
0x18001e05b  xor     cl, cl
0x18001e05d  test    sil, sil
0x18001e060  jz      short loc_18001E06A
0x18001e062  test    cl, cl
0x18001e064  jnz     short loc_18001E06A
0x18001e066  btr     dword ptr [rbx], 0Ah
0x18001e06a  mov     eax, [rbx]
0x18001e06c  test    bpl, al
0x18001e06f  jz      short loc_18001E075
0x18001e071  test    cl, cl
0x18001e073  jnz     short loc_18001E077
0x18001e075  xor     edi, edi
0x18001e077  and     eax, 0FFFFFFFEh
0x18001e07a  or      eax, edi
0x18001e07c  mov     [rbx], eax
0x18001e07e  mov     rax, rbx
0x18001e081  add     rsp, 28h
0x18001e085  pop     rdi
0x18001e086  pop     rsi
0x18001e087  pop     rbp
0x18001e088  pop     rbx
0x18001e089  retn
```
