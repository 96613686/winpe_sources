# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180012c68`
- end: `0x180012dd1`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800129c8`

## callees

- `0x180009670`
- `0x1800126e0`
- `0x180012c68`
- `0x180013bdc`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
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
    v4 = v2(57048237, 3);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_180022F08, 45036797, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x180012c68  mov     [rsp+arg_10], rbx
0x180012c6d  mov     [rsp+arg_0], rcx
0x180012c72  push    rbp
0x180012c73  push    rsi
0x180012c74  push    rdi
0x180012c75  sub     rsp, 40h
0x180012c79  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012c80  mov     rbx, rdx
0x180012c83  test    rax, rax
0x180012c86  jz      short loc_180012C9B
0x180012c88  mov     edx, 3
0x180012c8d  mov     ecx, 3667CADh
0x180012c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c97  mov     edx, eax
0x180012c99  jmp     short loc_180012CA9
0x180012c9b  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012ca2  test    rax, rax
0x180012ca5  jnz     short loc_180012C88
0x180012ca7  xor     edx, edx
0x180012ca9  mov     r8d, edx
0x180012cac  mov     qword ptr [rbx], 0
0x180012cb3  and     r8d, 0FFFFFF3Fh
0x180012cba  mov     eax, edx
0x180012cbc  and     edx, 80h
0x180012cc2  mov     ecx, r8d
0x180012cc5  and     ecx, 3
0x180012cc8  mov     ebp, 40h ; '@'
0x180012ccd  shl     ecx, 2
0x180012cd0  and     eax, ebp
0x180012cd2  or      ecx, eax
0x180012cd4  shl     ecx, 2
0x180012cd7  or      ecx, edx
0x180012cd9  shl     ecx, 3
0x180012cdc  test    r8d, r8d
0x180012cdf  jnz     short loc_180012CE8
0x180012ce1  mov     edx, ebp
0x180012ce3  mov     r8d, ebp
0x180012ce6  jmp     short loc_180012CF4
0x180012ce8  xor     edx, edx
0x180012cea  cmp     r8d, 2
0x180012cee  cmovz   edx, ebp
0x180012cf1  mov     r8d, edx
0x180012cf4  mov     eax, ecx
0x180012cf6  mov     edi, 1
0x180012cfb  or      eax, r8d
0x180012cfe  or      ecx, edx
0x180012d00  mov     [rbx], eax
0x180012d02  bt      ecx, 0Ah
0x180012d06  jnb     short loc_180012D15
0x180012d08  cmp     ecx, 800h
0x180012d0e  jb      short loc_180012D15
0x180012d10  mov     sil, dil
0x180012d13  jmp     short loc_180012D23
0x180012d15  xor     sil, sil
0x180012d18  xor     dl, dl
0x180012d1a  test    bpl, cl
0x180012d1d  jz      loc_180012DAD
0x180012d23  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x180012d2a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x180012d2f  test    al, al
0x180012d31  jz      short loc_180012D9E
0x180012d33  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180012d3a  mov     r8d, [rax]
0x180012d3d  test    r8b, 4
0x180012d41  jnz     short loc_180012D58
0x180012d43  lea     rdx, [rsp+58h+arg_8]
0x180012d48  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x180012d4d  mov     rcx, [rax]
0x180012d50  mov     [rsp+58h+arg_8], rcx
0x180012d55  mov     r8d, ecx
0x180012d58  xor     eax, eax
0x180012d5a  mov     word ptr [rsp+58h+arg_0+4], 3
0x180012d61  mov     r9d, r8d
0x180012d64  mov     [rsp+58h+var_28], eax
0x180012d68  mov     dword ptr [rsp+58h+arg_0], eax
0x180012d6c  lea     rcx, qword_180022F08
0x180012d73  shr     r9d, 0Bh
0x180012d77  lea     rax, [rsp+58h+arg_0]
0x180012d7c  shr     r8d, 0Ah
0x180012d80  and     r9d, edi
0x180012d83  and     r8d, edi
0x180012d86  mov     [rsp+58h+var_30], edi
0x180012d8a  mov     edx, 2AF34FDh
0x180012d8f  mov     [rsp+58h+var_38], rax
0x180012d94  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180012d99  mov     dl, dil
0x180012d9c  jmp     short loc_180012DA0
0x180012d9e  xor     dl, dl
0x180012da0  test    sil, sil
0x180012da3  jz      short loc_180012DAD
0x180012da5  test    dl, dl
0x180012da7  jnz     short loc_180012DAD
0x180012da9  btr     dword ptr [rbx], 0Ah
0x180012dad  mov     eax, [rbx]
0x180012daf  test    bpl, al
0x180012db2  jz      short loc_180012DB8
0x180012db4  test    dl, dl
0x180012db6  jnz     short loc_180012DBA
0x180012db8  xor     edi, edi
0x180012dba  and     eax, 0FFFFFFFEh
0x180012dbd  or      eax, edi
0x180012dbf  mov     [rbx], eax
0x180012dc1  mov     rax, rbx
0x180012dc4  mov     rbx, [rsp+58h+arg_10]
0x180012dc9  add     rsp, 40h
0x180012dcd  pop     rdi
0x180012dce  pop     rsi
0x180012dcf  pop     rbp
0x180012dd0  retn
```
