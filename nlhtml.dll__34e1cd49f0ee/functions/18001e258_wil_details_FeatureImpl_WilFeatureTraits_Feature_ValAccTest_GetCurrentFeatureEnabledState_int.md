# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001e258`
- end: `0x18001e326`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001d95c`

## callees

- `0x18001beec`
- `0x18001e258`
- `0x18001e90c`
- `0x18001ee48`

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
0x18001e258  mov     [rsp+arg_0], rbx
0x18001e25d  mov     [rsp+arg_8], rsi
0x18001e262  push    rdi
0x18001e263  sub     rsp, 20h
0x18001e267  mov     ecx, 3667CA7h; this
0x18001e26c  mov     rbx, rdx
0x18001e26f  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001e274  mov     edx, eax
0x18001e276  mov     qword ptr [rbx], 0
0x18001e27d  and     edx, 0FFFFFF3Fh
0x18001e283  mov     ecx, eax
0x18001e285  and     eax, 80h
0x18001e28a  mov     r8d, edx
0x18001e28d  and     r8d, 3
0x18001e291  mov     esi, 40h ; '@'
0x18001e296  shl     r8d, 2
0x18001e29a  and     ecx, esi
0x18001e29c  or      r8d, ecx
0x18001e29f  shl     r8d, 2
0x18001e2a3  or      r8d, eax
0x18001e2a6  shl     r8d, 3
0x18001e2aa  test    edx, edx
0x18001e2ac  jnz     short loc_18001E2B4
0x18001e2ae  mov     ecx, esi
0x18001e2b0  mov     edx, esi
0x18001e2b2  jmp     short loc_18001E2BE
0x18001e2b4  xor     ecx, ecx
0x18001e2b6  cmp     edx, 2
0x18001e2b9  cmovz   ecx, esi
0x18001e2bc  mov     edx, ecx
0x18001e2be  mov     eax, r8d
0x18001e2c1  mov     edi, 1
0x18001e2c6  or      eax, edx
0x18001e2c8  or      r8d, ecx
0x18001e2cb  mov     [rbx], eax
0x18001e2cd  bt      r8d, 0Ah
0x18001e2d2  jnb     short loc_18001E2DD
0x18001e2d4  cmp     r8d, 800h
0x18001e2db  jnb     short loc_18001E2E4
0x18001e2dd  xor     cl, cl
0x18001e2df  test    sil, r8b
0x18001e2e2  jz      short loc_18001E2FF
0x18001e2e4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValLabTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest> `wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl(void)'::`2'::impl
0x18001e2eb  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001e2f0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetImpl(void)'::`2'::impl
0x18001e2f7  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001e2fc  mov     cl, dil
0x18001e2ff  mov     eax, [rbx]
0x18001e301  test    sil, al
0x18001e304  jz      short loc_18001E30A
0x18001e306  test    cl, cl
0x18001e308  jnz     short loc_18001E30C
0x18001e30a  xor     edi, edi
0x18001e30c  mov     rsi, [rsp+28h+arg_8]
0x18001e311  and     eax, 0FFFFFFFEh
0x18001e314  or      eax, edi
0x18001e316  mov     [rbx], eax
0x18001e318  mov     rax, rbx
0x18001e31b  mov     rbx, [rsp+28h+arg_0]
0x18001e320  add     rsp, 20h
0x18001e324  pop     rdi
0x18001e325  retn
```
