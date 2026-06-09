# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000b384`
- end: `0x18000b4c6`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000b2a4`

## callees

- `0x18000b124`
- `0x18000b384`
- `0x18000b8ac`
- `0x180017010`

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
    wil::details::ReportUsageToService(&qword_180021170, 49453572, (v13 >> 10) & 1, (v13 >> 11) & 1, &v15, 1, 0);
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
0x18000b384  mov     [rsp+arg_10], rbx
0x18000b389  mov     [rsp+arg_18], rsi
0x18000b38e  mov     [rsp+arg_0], rcx
0x18000b393  push    rdi
0x18000b394  sub     rsp, 40h
0x18000b398  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000b39f  mov     rbx, rdx
0x18000b3a2  test    rax, rax
0x18000b3a5  jz      short loc_18000B3BA
0x18000b3a7  mov     edx, 3
0x18000b3ac  mov     ecx, 2E30A37h
0x18000b3b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3b6  mov     edx, eax
0x18000b3b8  jmp     short loc_18000B3C8
0x18000b3ba  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000b3c1  test    rax, rax
0x18000b3c4  jnz     short loc_18000B3A7
0x18000b3c6  xor     edx, edx
0x18000b3c8  mov     r8d, edx
0x18000b3cb  mov     qword ptr [rbx], 0
0x18000b3d2  and     r8d, 0FFFFFF3Fh
0x18000b3d9  mov     eax, edx
0x18000b3db  and     edx, 80h
0x18000b3e1  mov     ecx, r8d
0x18000b3e4  and     ecx, 3
0x18000b3e7  mov     esi, 40h ; '@'
0x18000b3ec  shl     ecx, 2
0x18000b3ef  and     eax, esi
0x18000b3f1  or      ecx, eax
0x18000b3f3  shl     ecx, 2
0x18000b3f6  or      ecx, edx
0x18000b3f8  shl     ecx, 3
0x18000b3fb  test    r8d, r8d
0x18000b3fe  jnz     short loc_18000B407
0x18000b400  mov     edx, esi
0x18000b402  mov     r8d, esi
0x18000b405  jmp     short loc_18000B413
0x18000b407  xor     edx, edx
0x18000b409  cmp     r8d, 2
0x18000b40d  cmovz   edx, esi
0x18000b410  mov     r8d, edx
0x18000b413  mov     eax, ecx
0x18000b415  mov     edi, 1
0x18000b41a  or      eax, r8d
0x18000b41d  or      ecx, edx
0x18000b41f  mov     [rbx], eax
0x18000b421  bt      ecx, 0Ah
0x18000b425  jnb     short loc_18000B42F
0x18000b427  cmp     ecx, 800h
0x18000b42d  jnb     short loc_18000B436
0x18000b42f  xor     dl, dl
0x18000b431  test    sil, cl
0x18000b434  jz      short loc_18000B49F
0x18000b436  mov     rax, cs:Feature_Standalone_Future__descriptor
0x18000b43d  mov     r8d, [rax]
0x18000b440  test    r8b, 4
0x18000b444  jnz     short loc_18000B45B
0x18000b446  lea     rdx, [rsp+48h+arg_8]
0x18000b44b  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x18000b450  mov     rcx, [rax]
0x18000b453  mov     [rsp+48h+arg_8], rcx
0x18000b458  mov     r8d, ecx
0x18000b45b  xor     eax, eax
0x18000b45d  mov     word ptr [rsp+48h+arg_0+4], 3
0x18000b464  mov     r9d, r8d
0x18000b467  mov     [rsp+48h+var_18], eax
0x18000b46b  mov     dword ptr [rsp+48h+arg_0], eax
0x18000b46f  lea     rcx, qword_180021170
0x18000b476  shr     r9d, 0Bh
0x18000b47a  lea     rax, [rsp+48h+arg_0]
0x18000b47f  shr     r8d, 0Ah
0x18000b483  and     r9d, edi
0x18000b486  and     r8d, edi
0x18000b489  mov     [rsp+48h+var_20], edi
0x18000b48d  mov     edx, 2F29A04h
0x18000b492  mov     [rsp+48h+var_28], rax
0x18000b497  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000b49c  mov     dl, dil
0x18000b49f  mov     eax, [rbx]
0x18000b4a1  test    sil, al
0x18000b4a4  jz      short loc_18000B4AA
0x18000b4a6  test    dl, dl
0x18000b4a8  jnz     short loc_18000B4AC
0x18000b4aa  xor     edi, edi
0x18000b4ac  mov     rsi, [rsp+48h+arg_18]
0x18000b4b1  and     eax, 0FFFFFFFEh
0x18000b4b4  or      eax, edi
0x18000b4b6  mov     [rbx], eax
0x18000b4b8  mov     rax, rbx
0x18000b4bb  mov     rbx, [rsp+48h+arg_10]
0x18000b4c0  add     rsp, 40h
0x18000b4c4  pop     rdi
0x18000b4c5  retn
```
