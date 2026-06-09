# wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000d1e4`
- end: `0x18000d326`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000cd18`

## callees

- `0x18000cef8`
- `0x18000d1e4`
- `0x180010fcc`
- `0x180011fd0`
- `0x180024010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, _QWORD); // rax
  int v4; // edx
  unsigned int v5; // r8d
  char v6; // al
  unsigned int v7; // edx
  wil::details *v8; // rcx
  unsigned int v9; // eax
  int v10; // ecx
  __int64 v11; // rcx
  char v12; // dl
  int v13; // edi
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h]
  char v18; // [rsp+78h] [rbp+20h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, _QWORD))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, _QWORD))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(57054134, 0);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = v4;
  v7 = v4 & 0x80;
  v8 = (wil::details *)(v7 | (4 * (v6 & 0x40 | (4 * (v5 & 3)))));
  v9 = 8 * (_DWORD)v8;
  *(_DWORD *)a2 = 8 * (_DWORD)v8;
  if ( v5 )
  {
    v10 = 0;
    if ( v5 == 2 )
      v10 = 64;
  }
  else
  {
    v10 = wil::details::ShouldBeEnabledFromConfigAndDefault(v8, v7, 0) << 6;
    v9 = *(_DWORD *)a2 & 0xFFFFFFBF;
  }
  v11 = v9 | v10;
  *(_DWORD *)a2 = v11;
  v12 = 0;
  v13 = 1;
  if ( (v11 & 0xC00) == 0xC00 || (v11 & 0x40) != 0 )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_05_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_05_NonSec__descriptor & 4) == 0 )
    {
      v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_05_NonSec>::GetCachedFeatureEnabledState(
                         v11,
                         &v18);
      v14 = v17;
    }
    LODWORD(v16) = 0;
    WORD2(v16) = 3;
    wil::details::ReportUsageToService(&unk_180030CE8, 58599563, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
    v12 = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v12 )
    v13 = 0;
  *(_DWORD *)a2 = v13 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18000d1e4  mov     [rsp+arg_10], rbx
0x18000d1e9  mov     [rsp+arg_0], rcx
0x18000d1ee  push    rbp
0x18000d1ef  push    rsi
0x18000d1f0  push    rdi
0x18000d1f1  sub     rsp, 40h
0x18000d1f5  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000d1fc  xor     esi, esi
0x18000d1fe  mov     rbx, rdx
0x18000d201  test    rax, rax
0x18000d204  jz      short loc_18000D216
0x18000d206  xor     edx, edx
0x18000d208  mov     ecx, 36693B6h
0x18000d20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d212  mov     edx, eax
0x18000d214  jmp     short loc_18000D224
0x18000d216  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000d21d  test    rax, rax
0x18000d220  jnz     short loc_18000D206
0x18000d222  mov     edx, esi
0x18000d224  mov     r8d, edx
0x18000d227  mov     [rbx], rsi
0x18000d22a  and     r8d, 0FFFFFF3Fh; bool
0x18000d231  mov     eax, edx
0x18000d233  and     edx, 80h; unsigned int
0x18000d239  mov     ecx, r8d
0x18000d23c  and     ecx, 3
0x18000d23f  mov     ebp, 40h ; '@'
0x18000d244  shl     ecx, 2
0x18000d247  and     eax, ebp
0x18000d249  or      ecx, eax
0x18000d24b  shl     ecx, 2
0x18000d24e  or      ecx, edx; this
0x18000d250  lea     eax, ds:0[rcx*8]
0x18000d257  mov     [rbx], eax
0x18000d259  test    r8d, r8d
0x18000d25c  jnz     short loc_18000D270
0x18000d25e  call    ?ShouldBeEnabledFromConfigAndDefault@details@wil@@YA_NI_N@Z; wil::details::ShouldBeEnabledFromConfigAndDefault(uint,bool)
0x18000d263  movzx   ecx, al
0x18000d266  mov     eax, [rbx]
0x18000d268  shl     ecx, 6
0x18000d26b  and     eax, 0FFFFFFBFh
0x18000d26e  jmp     short loc_18000D279
0x18000d270  cmp     r8d, 2
0x18000d274  mov     ecx, esi
0x18000d276  cmovz   ecx, ebp
0x18000d279  or      ecx, eax
0x18000d27b  mov     r8d, 0C00h
0x18000d281  mov     eax, ecx
0x18000d283  mov     [rbx], ecx
0x18000d285  and     eax, r8d
0x18000d288  mov     dl, sil
0x18000d28b  mov     edi, 1
0x18000d290  cmp     eax, r8d
0x18000d293  jz      short loc_18000D29A
0x18000d295  test    bpl, cl
0x18000d298  jz      short loc_18000D301
0x18000d29a  mov     rax, cs:Feature_Standalone_26_05_NonSec__descriptor
0x18000d2a1  mov     r8d, [rax]
0x18000d2a4  test    r8b, 4
0x18000d2a8  jnz     short loc_18000D2BF
0x18000d2aa  lea     rdx, [rsp+58h+arg_18]
0x18000d2af  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_05_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_05_NonSec>::GetCachedFeatureEnabledState(void)
0x18000d2b4  mov     rcx, [rax]
0x18000d2b7  mov     [rsp+58h+arg_8], rcx
0x18000d2bc  mov     r8d, ecx
0x18000d2bf  mov     r9d, r8d
0x18000d2c2  mov     [rsp+58h+var_28], esi
0x18000d2c6  shr     r9d, 0Bh
0x18000d2ca  lea     rax, [rsp+58h+arg_0]
0x18000d2cf  shr     r8d, 0Ah
0x18000d2d3  lea     rcx, unk_180030CE8
0x18000d2da  and     r9d, edi
0x18000d2dd  mov     [rsp+58h+var_30], edi
0x18000d2e1  and     r8d, edi
0x18000d2e4  mov     dword ptr [rsp+58h+arg_0], esi
0x18000d2e8  mov     edx, 37E288Bh
0x18000d2ed  mov     word ptr [rsp+58h+arg_0+4], 3
0x18000d2f4  mov     [rsp+58h+var_38], rax
0x18000d2f9  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000d2fe  mov     dl, dil
0x18000d301  mov     eax, [rbx]
0x18000d303  test    bpl, al
0x18000d306  jz      short loc_18000D30C
0x18000d308  test    dl, dl
0x18000d30a  jnz     short loc_18000D30E
0x18000d30c  mov     edi, esi
0x18000d30e  and     eax, 0FFFFFFFEh
0x18000d311  or      eax, edi
0x18000d313  mov     [rbx], eax
0x18000d315  mov     rax, rbx
0x18000d318  mov     rbx, [rsp+58h+arg_10]
0x18000d31d  add     rsp, 40h
0x18000d321  pop     rdi
0x18000d322  pop     rsi
0x18000d323  pop     rbp
0x18000d324  retn
```
