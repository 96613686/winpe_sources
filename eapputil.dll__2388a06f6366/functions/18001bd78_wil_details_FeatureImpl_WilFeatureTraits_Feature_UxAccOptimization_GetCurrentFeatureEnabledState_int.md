# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001bd78`
- end: `0x18001beba`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001bb0c`

## callees

- `0x18001b7d0`
- `0x18001bd78`
- `0x18001dd0c`
- `0x180033010`

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
    wil::details::ReportUsageToService(&qword_180043F08, 49453572, (v13 >> 10) & 1, (v13 >> 11) & 1, &v15, 1, 0);
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
0x18001bd78  mov     [rsp+arg_10], rbx
0x18001bd7d  mov     [rsp+arg_18], rsi
0x18001bd82  mov     [rsp+arg_0], rcx
0x18001bd87  push    rdi
0x18001bd88  sub     rsp, 40h
0x18001bd8c  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001bd93  mov     rbx, rdx
0x18001bd96  test    rax, rax
0x18001bd99  jz      short loc_18001BDAE
0x18001bd9b  mov     edx, 3
0x18001bda0  mov     ecx, 2E30A37h
0x18001bda5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdaa  mov     edx, eax
0x18001bdac  jmp     short loc_18001BDBC
0x18001bdae  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001bdb5  test    rax, rax
0x18001bdb8  jnz     short loc_18001BD9B
0x18001bdba  xor     edx, edx
0x18001bdbc  mov     r8d, edx
0x18001bdbf  mov     qword ptr [rbx], 0
0x18001bdc6  and     r8d, 0FFFFFF3Fh
0x18001bdcd  mov     eax, edx
0x18001bdcf  and     edx, 80h
0x18001bdd5  mov     ecx, r8d
0x18001bdd8  and     ecx, 3
0x18001bddb  mov     esi, 40h ; '@'
0x18001bde0  shl     ecx, 2
0x18001bde3  and     eax, esi
0x18001bde5  or      ecx, eax
0x18001bde7  shl     ecx, 2
0x18001bdea  or      ecx, edx
0x18001bdec  shl     ecx, 3
0x18001bdef  test    r8d, r8d
0x18001bdf2  jnz     short loc_18001BDFB
0x18001bdf4  mov     edx, esi
0x18001bdf6  mov     r8d, esi
0x18001bdf9  jmp     short loc_18001BE07
0x18001bdfb  xor     edx, edx
0x18001bdfd  cmp     r8d, 2
0x18001be01  cmovz   edx, esi
0x18001be04  mov     r8d, edx
0x18001be07  mov     eax, ecx
0x18001be09  mov     edi, 1
0x18001be0e  or      eax, r8d
0x18001be11  or      ecx, edx
0x18001be13  mov     [rbx], eax
0x18001be15  bt      ecx, 0Ah
0x18001be19  jnb     short loc_18001BE23
0x18001be1b  cmp     ecx, 800h
0x18001be21  jnb     short loc_18001BE2A
0x18001be23  xor     dl, dl
0x18001be25  test    sil, cl
0x18001be28  jz      short loc_18001BE93
0x18001be2a  mov     rax, cs:Feature_Standalone_Future__descriptor
0x18001be31  mov     r8d, [rax]
0x18001be34  test    r8b, 4
0x18001be38  jnz     short loc_18001BE4F
0x18001be3a  lea     rdx, [rsp+48h+arg_8]
0x18001be3f  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x18001be44  mov     rcx, [rax]
0x18001be47  mov     [rsp+48h+arg_8], rcx
0x18001be4c  mov     r8d, ecx
0x18001be4f  xor     eax, eax
0x18001be51  mov     word ptr [rsp+48h+arg_0+4], 3
0x18001be58  mov     r9d, r8d
0x18001be5b  mov     [rsp+48h+var_18], eax
0x18001be5f  mov     dword ptr [rsp+48h+arg_0], eax
0x18001be63  lea     rcx, qword_180043F08
0x18001be6a  shr     r9d, 0Bh
0x18001be6e  lea     rax, [rsp+48h+arg_0]
0x18001be73  shr     r8d, 0Ah
0x18001be77  and     r9d, edi
0x18001be7a  and     r8d, edi
0x18001be7d  mov     [rsp+48h+var_20], edi
0x18001be81  mov     edx, 2F29A04h
0x18001be86  mov     [rsp+48h+var_28], rax
0x18001be8b  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18001be90  mov     dl, dil
0x18001be93  mov     eax, [rbx]
0x18001be95  test    sil, al
0x18001be98  jz      short loc_18001BE9E
0x18001be9a  test    dl, dl
0x18001be9c  jnz     short loc_18001BEA0
0x18001be9e  xor     edi, edi
0x18001bea0  mov     rsi, [rsp+48h+arg_18]
0x18001bea5  and     eax, 0FFFFFFFEh
0x18001bea8  or      eax, edi
0x18001beaa  mov     [rbx], eax
0x18001beac  mov     rax, rbx
0x18001beaf  mov     rbx, [rsp+48h+arg_10]
0x18001beb4  add     rsp, 40h
0x18001beb8  pop     rdi
0x18001beb9  retn
```
