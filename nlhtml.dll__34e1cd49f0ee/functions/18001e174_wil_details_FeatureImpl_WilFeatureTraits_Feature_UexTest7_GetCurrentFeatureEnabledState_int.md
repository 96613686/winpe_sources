# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001e174`
- end: `0x18001e252`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001d87c`

## callees

- `0x18001beec`
- `0x18001e174`
- `0x18001eb1c`
- `0x18001ef50`

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
  int v7; // ecx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // si
  char v13; // cl

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
    v13 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_16;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetImpl'::`2'::impl);
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
0x18001e174  push    rbx
0x18001e176  push    rbp
0x18001e177  push    rsi
0x18001e178  push    rdi
0x18001e179  sub     rsp, 28h
0x18001e17d  mov     ecx, 38419DDh; this
0x18001e182  mov     rbx, rdx
0x18001e185  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001e18a  mov     edx, eax
0x18001e18c  mov     qword ptr [rbx], 0
0x18001e193  and     edx, 0FFFFFF3Fh
0x18001e199  mov     ecx, eax
0x18001e19b  and     eax, 80h
0x18001e1a0  mov     r8d, edx
0x18001e1a3  and     r8d, 3
0x18001e1a7  mov     ebp, 40h ; '@'
0x18001e1ac  shl     r8d, 2
0x18001e1b0  and     ecx, ebp
0x18001e1b2  or      r8d, ecx
0x18001e1b5  shl     r8d, 2
0x18001e1b9  or      r8d, eax
0x18001e1bc  shl     r8d, 3
0x18001e1c0  test    edx, edx
0x18001e1c2  jnz     short loc_18001E1CA
0x18001e1c4  mov     ecx, ebp
0x18001e1c6  mov     edx, ebp
0x18001e1c8  jmp     short loc_18001E1D4
0x18001e1ca  xor     ecx, ecx
0x18001e1cc  cmp     edx, 2
0x18001e1cf  cmovz   ecx, ebp
0x18001e1d2  mov     edx, ecx
0x18001e1d4  mov     eax, r8d
0x18001e1d7  mov     edi, 1
0x18001e1dc  or      eax, edx
0x18001e1de  or      r8d, ecx
0x18001e1e1  mov     [rbx], eax
0x18001e1e3  bt      r8d, 0Ah
0x18001e1e8  jnb     short loc_18001E1F8
0x18001e1ea  cmp     r8d, 800h
0x18001e1f1  jb      short loc_18001E1F8
0x18001e1f3  mov     sil, dil
0x18001e1f6  jmp     short loc_18001E202
0x18001e1f8  xor     sil, sil
0x18001e1fb  xor     cl, cl
0x18001e1fd  test    bpl, r8b
0x18001e200  jz      short loc_18001E232
0x18001e202  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x18001e209  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x18001e20e  test    al, al
0x18001e210  jz      short loc_18001E223
0x18001e212  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetImpl(void)'::`2'::impl
0x18001e219  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001e21e  mov     cl, dil
0x18001e221  jmp     short loc_18001E225
0x18001e223  xor     cl, cl
0x18001e225  test    sil, sil
0x18001e228  jz      short loc_18001E232
0x18001e22a  test    cl, cl
0x18001e22c  jnz     short loc_18001E232
0x18001e22e  btr     dword ptr [rbx], 0Ah
0x18001e232  mov     eax, [rbx]
0x18001e234  test    bpl, al
0x18001e237  jz      short loc_18001E23D
0x18001e239  test    cl, cl
0x18001e23b  jnz     short loc_18001E23F
0x18001e23d  xor     edi, edi
0x18001e23f  and     eax, 0FFFFFFFEh
0x18001e242  or      eax, edi
0x18001e244  mov     [rbx], eax
0x18001e246  mov     rax, rbx
0x18001e249  add     rsp, 28h
0x18001e24d  pop     rdi
0x18001e24e  pop     rsi
0x18001e24f  pop     rbp
0x18001e250  pop     rbx
0x18001e251  retn
```
