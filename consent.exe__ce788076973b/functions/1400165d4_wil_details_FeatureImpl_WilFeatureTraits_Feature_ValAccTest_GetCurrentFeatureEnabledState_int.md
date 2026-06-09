# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1400165d4`
- end: `0x1400166a2`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `206`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400159c8`

## callees

- `0x1400165d4`
- `0x140017388`
- `0x1400177b8`
- `0x140017d24`

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
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl'::`2'::impl);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetImpl'::`2'::impl);
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
0x1400165d4  mov     [rsp+arg_0], rbx
0x1400165d9  mov     [rsp+arg_8], rsi
0x1400165de  push    rdi
0x1400165df  sub     rsp, 20h
0x1400165e3  mov     ecx, 3667CA7h; this
0x1400165e8  mov     rbx, rdx
0x1400165eb  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1400165f0  mov     edx, eax
0x1400165f2  mov     qword ptr [rbx], 0
0x1400165f9  and     edx, 0FFFFFF3Fh
0x1400165ff  mov     ecx, eax
0x140016601  and     eax, 80h
0x140016606  mov     r8d, edx
0x140016609  and     r8d, 3
0x14001660d  mov     esi, 40h ; '@'
0x140016612  shl     r8d, 2
0x140016616  and     ecx, esi
0x140016618  or      r8d, ecx
0x14001661b  shl     r8d, 2
0x14001661f  or      r8d, eax
0x140016622  shl     r8d, 3
0x140016626  test    edx, edx
0x140016628  jnz     short loc_140016630
0x14001662a  mov     ecx, esi
0x14001662c  mov     edx, esi
0x14001662e  jmp     short loc_14001663A
0x140016630  xor     ecx, ecx
0x140016632  cmp     edx, 2
0x140016635  cmovz   ecx, esi
0x140016638  mov     edx, ecx
0x14001663a  mov     eax, r8d
0x14001663d  mov     edi, 1
0x140016642  or      eax, edx
0x140016644  or      r8d, ecx
0x140016647  mov     [rbx], eax
0x140016649  bt      r8d, 0Ah
0x14001664e  jnb     short loc_140016659
0x140016650  cmp     r8d, 800h
0x140016657  jnb     short loc_140016660
0x140016659  xor     cl, cl
0x14001665b  test    sil, r8b
0x14001665e  jz      short loc_14001667B
0x140016660  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValLabTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest> `wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl(void)'::`2'::impl
0x140016667  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14001666c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetImpl(void)'::`2'::impl
0x140016673  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140016678  mov     cl, dil
0x14001667b  mov     eax, [rbx]
0x14001667d  test    sil, al
0x140016680  jz      short loc_140016686
0x140016682  test    cl, cl
0x140016684  jnz     short loc_140016688
0x140016686  xor     edi, edi
0x140016688  mov     rsi, [rsp+28h+arg_8]
0x14001668d  and     eax, 0FFFFFFFEh
0x140016690  or      eax, edi
0x140016692  mov     [rbx], eax
0x140016694  mov     rax, rbx
0x140016697  mov     rbx, [rsp+28h+arg_0]
0x14001669c  add     rsp, 20h
0x1400166a0  pop     rdi
0x1400166a1  retn
```
