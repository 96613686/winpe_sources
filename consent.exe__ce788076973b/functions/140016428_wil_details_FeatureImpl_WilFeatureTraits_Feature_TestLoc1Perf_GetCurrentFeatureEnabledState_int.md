# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x140016428`
- end: `0x140016506`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140015768`

## callees

- `0x140016428`
- `0x140017490`
- `0x140017d24`
- `0x140017f40`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419AC, (unsigned int)a2, a3, a4);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl'::`2'::impl);
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
0x140016428  push    rbx
0x14001642a  push    rbp
0x14001642b  push    rsi
0x14001642c  push    rdi
0x14001642d  sub     rsp, 28h
0x140016431  mov     ecx, 38419ACh; this
0x140016436  mov     rbx, rdx
0x140016439  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14001643e  mov     edx, eax
0x140016440  mov     qword ptr [rbx], 0
0x140016447  and     edx, 0FFFFFF3Fh
0x14001644d  mov     ecx, eax
0x14001644f  and     eax, 80h
0x140016454  mov     r8d, edx
0x140016457  and     r8d, 3
0x14001645b  mov     ebp, 40h ; '@'
0x140016460  shl     r8d, 2
0x140016464  and     ecx, ebp
0x140016466  or      r8d, ecx
0x140016469  shl     r8d, 2
0x14001646d  or      r8d, eax
0x140016470  shl     r8d, 3
0x140016474  test    edx, edx
0x140016476  jnz     short loc_14001647E
0x140016478  mov     ecx, ebp
0x14001647a  mov     edx, ebp
0x14001647c  jmp     short loc_140016488
0x14001647e  xor     ecx, ecx
0x140016480  cmp     edx, 2
0x140016483  cmovz   ecx, ebp
0x140016486  mov     edx, ecx
0x140016488  mov     eax, r8d
0x14001648b  mov     edi, 1
0x140016490  or      eax, edx
0x140016492  or      r8d, ecx
0x140016495  mov     [rbx], eax
0x140016497  bt      r8d, 0Ah
0x14001649c  jnb     short loc_1400164AC
0x14001649e  cmp     r8d, 800h
0x1400164a5  jb      short loc_1400164AC
0x1400164a7  mov     sil, dil
0x1400164aa  jmp     short loc_1400164B6
0x1400164ac  xor     sil, sil
0x1400164af  xor     cl, cl
0x1400164b1  test    bpl, r8b
0x1400164b4  jz      short loc_1400164E6
0x1400164b6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x1400164bd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x1400164c2  test    al, al
0x1400164c4  jz      short loc_1400164D7
0x1400164c6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl(void)'::`2'::impl
0x1400164cd  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1400164d2  mov     cl, dil
0x1400164d5  jmp     short loc_1400164D9
0x1400164d7  xor     cl, cl
0x1400164d9  test    sil, sil
0x1400164dc  jz      short loc_1400164E6
0x1400164de  test    cl, cl
0x1400164e0  jnz     short loc_1400164E6
0x1400164e2  btr     dword ptr [rbx], 0Ah
0x1400164e6  mov     eax, [rbx]
0x1400164e8  test    bpl, al
0x1400164eb  jz      short loc_1400164F1
0x1400164ed  test    cl, cl
0x1400164ef  jnz     short loc_1400164F3
0x1400164f1  xor     edi, edi
0x1400164f3  and     eax, 0FFFFFFFEh
0x1400164f6  or      eax, edi
0x1400164f8  mov     [rbx], eax
0x1400164fa  mov     rax, rbx
0x1400164fd  add     rsp, 28h
0x140016501  pop     rdi
0x140016502  pop     rsi
0x140016503  pop     rbp
0x140016504  pop     rbx
0x140016505  retn
```
