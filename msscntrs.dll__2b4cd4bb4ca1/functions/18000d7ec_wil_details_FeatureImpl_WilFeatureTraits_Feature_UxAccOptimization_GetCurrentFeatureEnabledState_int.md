# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000d7ec`
- end: `0x18000d92e`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000d464`

## callees

- `0x18000d2e4`
- `0x18000d7ec`
- `0x18000fa2c`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
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
  wil::details *v11; // rcx
  char v12; // dl
  unsigned int v13; // r8d
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(48433719, 3);
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
  v11 = (wil::details *)(v7 | (unsigned int)v6);
  *(_DWORD *)a2 = v10;
  if ( ((unsigned __int16)v11 & 0x400) != 0 && (unsigned int)v11 >= 0x800
    || (v12 = 0, ((unsigned __int8)v11 & 0x40) != 0) )
  {
    v13 = *(_DWORD *)Feature_Standalone_Future__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_Future__descriptor & 4) == 0 )
    {
      v16 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
               v11,
               &v16);
      v13 = v16;
    }
    WORD2(v15) = 3;
    LODWORD(v15) = 0;
    wil::details::ReportUsageToService(&qword_180022168, 49453572, (v13 >> 10) & 1, (v13 >> 11) & 1, &v15, 1, 0);
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
0x18000d7ec  mov     [rsp+arg_10], rbx
0x18000d7f1  mov     [rsp+arg_18], rsi
0x18000d7f6  mov     [rsp+arg_0], rcx
0x18000d7fb  push    rdi
0x18000d7fc  sub     rsp, 40h
0x18000d800  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000d807  mov     rbx, rdx
0x18000d80a  test    rax, rax
0x18000d80d  jz      short loc_18000D822
0x18000d80f  mov     edx, 3
0x18000d814  mov     ecx, 2E30A37h
0x18000d819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d81e  mov     edx, eax
0x18000d820  jmp     short loc_18000D830
0x18000d822  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000d829  test    rax, rax
0x18000d82c  jnz     short loc_18000D80F
0x18000d82e  xor     edx, edx
0x18000d830  mov     r8d, edx
0x18000d833  mov     qword ptr [rbx], 0
0x18000d83a  and     r8d, 0FFFFFF3Fh
0x18000d841  mov     eax, edx
0x18000d843  and     edx, 80h
0x18000d849  mov     ecx, r8d
0x18000d84c  and     ecx, 3
0x18000d84f  mov     esi, 40h ; '@'
0x18000d854  shl     ecx, 2
0x18000d857  and     eax, esi
0x18000d859  or      ecx, eax
0x18000d85b  shl     ecx, 2
0x18000d85e  or      ecx, edx
0x18000d860  shl     ecx, 3
0x18000d863  test    r8d, r8d
0x18000d866  jnz     short loc_18000D86F
0x18000d868  mov     edx, esi
0x18000d86a  mov     r8d, esi
0x18000d86d  jmp     short loc_18000D87B
0x18000d86f  xor     edx, edx
0x18000d871  cmp     r8d, 2
0x18000d875  cmovz   edx, esi
0x18000d878  mov     r8d, edx
0x18000d87b  mov     eax, ecx
0x18000d87d  mov     edi, 1
0x18000d882  or      eax, r8d
0x18000d885  or      ecx, edx
0x18000d887  mov     [rbx], eax
0x18000d889  bt      ecx, 0Ah
0x18000d88d  jnb     short loc_18000D897
0x18000d88f  cmp     ecx, 800h
0x18000d895  jnb     short loc_18000D89E
0x18000d897  xor     dl, dl
0x18000d899  test    sil, cl
0x18000d89c  jz      short loc_18000D907
0x18000d89e  mov     rax, cs:Feature_Standalone_Future__descriptor
0x18000d8a5  mov     r8d, [rax]
0x18000d8a8  test    r8b, 4
0x18000d8ac  jnz     short loc_18000D8C3
0x18000d8ae  lea     rdx, [rsp+48h+arg_8]
0x18000d8b3  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x18000d8b8  mov     rcx, [rax]
0x18000d8bb  mov     [rsp+48h+arg_8], rcx
0x18000d8c0  mov     r8d, ecx
0x18000d8c3  xor     eax, eax
0x18000d8c5  mov     word ptr [rsp+48h+arg_0+4], 3
0x18000d8cc  mov     r9d, r8d
0x18000d8cf  mov     [rsp+48h+var_18], eax
0x18000d8d3  mov     dword ptr [rsp+48h+arg_0], eax
0x18000d8d7  lea     rcx, qword_180022168
0x18000d8de  shr     r9d, 0Bh
0x18000d8e2  lea     rax, [rsp+48h+arg_0]
0x18000d8e7  shr     r8d, 0Ah
0x18000d8eb  and     r9d, edi
0x18000d8ee  and     r8d, edi
0x18000d8f1  mov     [rsp+48h+var_20], edi
0x18000d8f5  mov     edx, 2F29A04h
0x18000d8fa  mov     [rsp+48h+var_28], rax
0x18000d8ff  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000d904  mov     dl, dil
0x18000d907  mov     eax, [rbx]
0x18000d909  test    sil, al
0x18000d90c  jz      short loc_18000D912
0x18000d90e  test    dl, dl
0x18000d910  jnz     short loc_18000D914
0x18000d912  xor     edi, edi
0x18000d914  mov     rsi, [rsp+48h+arg_18]
0x18000d919  and     eax, 0FFFFFFFEh
0x18000d91c  or      eax, edi
0x18000d91e  mov     [rbx], eax
0x18000d920  mov     rax, rbx
0x18000d923  mov     rbx, [rsp+48h+arg_10]
0x18000d928  add     rsp, 40h
0x18000d92c  pop     rdi
0x18000d92d  retn
```
