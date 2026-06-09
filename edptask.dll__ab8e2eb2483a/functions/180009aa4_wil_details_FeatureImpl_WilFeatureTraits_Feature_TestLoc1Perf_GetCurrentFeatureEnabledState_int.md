# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180009aa4`
- end: `0x180009c0d`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180009410`

## callees

- `0x18000903c`
- `0x180009aa4`
- `0x180010330`
- `0x180012130`
- `0x180014010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  __int64 v7; // rdx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // ecx
  char v12; // si
  wil::details *v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(58988972, 3);
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
      goto LABEL_22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_18001DD10, 58599532, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
    LOBYTE(v7) = 1;
  }
  else
  {
    LOBYTE(v7) = 0;
  }
  if ( v12 && !(_BYTE)v7 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_22:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180009aa4  mov     [rsp+arg_10], rbx
0x180009aa9  mov     [rsp+arg_0], rcx
0x180009aae  push    rbp
0x180009aaf  push    rsi
0x180009ab0  push    rdi
0x180009ab1  sub     rsp, 40h
0x180009ab5  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180009abc  mov     rbx, rdx
0x180009abf  test    rax, rax
0x180009ac2  jz      short loc_180009AD7
0x180009ac4  mov     edx, 3
0x180009ac9  mov     ecx, 38419ACh
0x180009ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ad3  mov     edx, eax
0x180009ad5  jmp     short loc_180009AE5
0x180009ad7  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180009ade  test    rax, rax
0x180009ae1  jnz     short loc_180009AC4
0x180009ae3  xor     edx, edx
0x180009ae5  mov     r8d, edx
0x180009ae8  mov     qword ptr [rbx], 0
0x180009aef  and     r8d, 0FFFFFF3Fh
0x180009af6  mov     eax, edx
0x180009af8  and     edx, 80h
0x180009afe  mov     ecx, r8d
0x180009b01  and     ecx, 3
0x180009b04  mov     ebp, 40h ; '@'
0x180009b09  shl     ecx, 2
0x180009b0c  and     eax, ebp
0x180009b0e  or      ecx, eax
0x180009b10  shl     ecx, 2
0x180009b13  or      ecx, edx
0x180009b15  shl     ecx, 3
0x180009b18  test    r8d, r8d
0x180009b1b  jnz     short loc_180009B24
0x180009b1d  mov     edx, ebp
0x180009b1f  mov     r8d, ebp
0x180009b22  jmp     short loc_180009B30
0x180009b24  xor     edx, edx
0x180009b26  cmp     r8d, 2
0x180009b2a  cmovz   edx, ebp
0x180009b2d  mov     r8d, edx
0x180009b30  mov     eax, ecx
0x180009b32  mov     edi, 1
0x180009b37  or      eax, r8d
0x180009b3a  or      ecx, edx
0x180009b3c  mov     [rbx], eax
0x180009b3e  bt      ecx, 0Ah
0x180009b42  jnb     short loc_180009B51
0x180009b44  cmp     ecx, 800h
0x180009b4a  jb      short loc_180009B51
0x180009b4c  mov     sil, dil
0x180009b4f  jmp     short loc_180009B5F
0x180009b51  xor     sil, sil
0x180009b54  xor     dl, dl
0x180009b56  test    bpl, cl
0x180009b59  jz      loc_180009BE9
0x180009b5f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x180009b66  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x180009b6b  test    al, al
0x180009b6d  jz      short loc_180009BDA
0x180009b6f  mov     rax, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180009b76  mov     r8d, [rax]
0x180009b79  test    r8b, 4
0x180009b7d  jnz     short loc_180009B94
0x180009b7f  lea     rdx, [rsp+58h+arg_8]
0x180009b84  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x180009b89  mov     rcx, [rax]
0x180009b8c  mov     [rsp+58h+arg_8], rcx
0x180009b91  mov     r8d, ecx
0x180009b94  xor     eax, eax
0x180009b96  mov     word ptr [rsp+58h+arg_0+4], 3
0x180009b9d  mov     r9d, r8d
0x180009ba0  mov     [rsp+58h+var_28], eax
0x180009ba4  mov     dword ptr [rsp+58h+arg_0], eax
0x180009ba8  lea     rcx, qword_18001DD10
0x180009baf  shr     r9d, 0Bh
0x180009bb3  lea     rax, [rsp+58h+arg_0]
0x180009bb8  shr     r8d, 0Ah
0x180009bbc  and     r9d, edi
0x180009bbf  and     r8d, edi
0x180009bc2  mov     [rsp+58h+var_30], edi
0x180009bc6  mov     edx, 37E286Ch
0x180009bcb  mov     [rsp+58h+var_38], rax
0x180009bd0  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180009bd5  mov     dl, dil
0x180009bd8  jmp     short loc_180009BDC
0x180009bda  xor     dl, dl
0x180009bdc  test    sil, sil
0x180009bdf  jz      short loc_180009BE9
0x180009be1  test    dl, dl
0x180009be3  jnz     short loc_180009BE9
0x180009be5  btr     dword ptr [rbx], 0Ah
0x180009be9  mov     eax, [rbx]
0x180009beb  test    bpl, al
0x180009bee  jz      short loc_180009BF4
0x180009bf0  test    dl, dl
0x180009bf2  jnz     short loc_180009BF6
0x180009bf4  xor     edi, edi
0x180009bf6  and     eax, 0FFFFFFFEh
0x180009bf9  or      eax, edi
0x180009bfb  mov     [rbx], eax
0x180009bfd  mov     rax, rbx
0x180009c00  mov     rbx, [rsp+58h+arg_10]
0x180009c05  add     rsp, 40h
0x180009c09  pop     rdi
0x180009c0a  pop     rsi
0x180009c0b  pop     rbp
0x180009c0c  retn
```
