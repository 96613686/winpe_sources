# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2505>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180059f1c`
- end: `0x18005a03c`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2505@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180059afc`

## callees

- `0x18003cfdc`
- `0x18003d8e0`
- `0x180059998`
- `0x180059f1c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2505>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  __int64 v7; // rcx
  int v8; // edx
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF

  v14 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x34A568F, (unsigned int)a2, a3, a4);
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
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 || (LOBYTE(v7) = 0, (v11 & 0x40) != 0) )
  {
    v12 = *(_DWORD *)Feature_ImplVal__descriptor;
    if ( (*(_DWORD *)Feature_ImplVal__descriptor & 4) == 0 )
    {
      v15 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImplVal>::GetCachedFeatureEnabledState(
               (wil::details *)v7,
               &v15);
      v12 = v15;
    }
    WORD2(v14) = 3;
    LODWORD(v14) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18009D988,
      0x33B9B29u,
      (v12 >> 10) & 1,
      (v12 >> 11) & 1,
      (__int64)&v14,
      1u,
      0);
    LOBYTE(v7) = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180059f1c  mov     [rsp+arg_10], rbx
0x180059f21  mov     [rsp+arg_18], rsi
0x180059f26  mov     [rsp+arg_0], rcx
0x180059f2b  push    rdi
0x180059f2c  sub     rsp, 40h
0x180059f30  mov     ecx, 34A568Fh; this
0x180059f35  mov     rdi, rdx
0x180059f38  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180059f3d  mov     edx, eax
0x180059f3f  mov     qword ptr [rdi], 0
0x180059f46  and     edx, 0FFFFFF3Fh
0x180059f4c  mov     ecx, eax
0x180059f4e  and     eax, 80h
0x180059f53  mov     r8d, edx
0x180059f56  and     r8d, 3
0x180059f5a  mov     esi, 40h ; '@'
0x180059f5f  shl     r8d, 2
0x180059f63  and     ecx, esi
0x180059f65  or      r8d, ecx
0x180059f68  shl     r8d, 2
0x180059f6c  or      r8d, eax
0x180059f6f  shl     r8d, 3
0x180059f73  test    edx, edx
0x180059f75  jnz     short loc_180059F7D
0x180059f77  mov     ecx, esi
0x180059f79  mov     edx, esi
0x180059f7b  jmp     short loc_180059F87
0x180059f7d  xor     ecx, ecx
0x180059f7f  cmp     edx, 2
0x180059f82  cmovz   ecx, esi
0x180059f85  mov     edx, ecx
0x180059f87  mov     eax, r8d
0x180059f8a  mov     ebx, 1
0x180059f8f  or      eax, edx
0x180059f91  or      r8d, ecx
0x180059f94  mov     [rdi], eax
0x180059f96  bt      r8d, 0Ah
0x180059f9b  jnb     short loc_180059FA6
0x180059f9d  cmp     r8d, 800h
0x180059fa4  jnb     short loc_180059FAD
0x180059fa6  xor     cl, cl
0x180059fa8  test    sil, r8b
0x180059fab  jz      short loc_18005A015
0x180059fad  mov     rax, cs:Feature_ImplVal__descriptor
0x180059fb4  mov     r8d, [rax]
0x180059fb7  test    r8b, 4
0x180059fbb  jnz     short loc_180059FD2
0x180059fbd  lea     rdx, [rsp+48h+arg_8]
0x180059fc2  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ImplVal@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImplVal>::GetCachedFeatureEnabledState(void)
0x180059fc7  mov     rcx, [rax]
0x180059fca  mov     [rsp+48h+arg_8], rcx
0x180059fcf  mov     r8d, ecx
0x180059fd2  xor     eax, eax
0x180059fd4  mov     word ptr [rsp+48h+arg_0+4], 3
0x180059fdb  mov     r9d, r8d
0x180059fde  mov     [rsp+48h+var_18], eax
0x180059fe2  mov     dword ptr [rsp+48h+arg_0], eax
0x180059fe6  lea     rcx, qword_18009D988
0x180059fed  shr     r9d, 0Bh
0x180059ff1  lea     rax, [rsp+48h+arg_0]
0x180059ff6  shr     r8d, 0Ah
0x180059ffa  and     r9d, ebx
0x180059ffd  and     r8d, ebx
0x18005a000  mov     [rsp+48h+var_20], ebx
0x18005a004  mov     edx, 33B9B29h
0x18005a009  mov     [rsp+48h+var_28], rax
0x18005a00e  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18005a013  mov     cl, bl
0x18005a015  mov     eax, [rdi]
0x18005a017  test    sil, al
0x18005a01a  jz      short loc_18005A020
0x18005a01c  test    cl, cl
0x18005a01e  jnz     short loc_18005A022
0x18005a020  xor     ebx, ebx
0x18005a022  mov     rsi, [rsp+48h+arg_18]
0x18005a027  and     eax, 0FFFFFFFEh
0x18005a02a  or      eax, ebx
0x18005a02c  mov     rbx, [rsp+48h+arg_10]
0x18005a031  mov     [rdi], eax
0x18005a033  mov     rax, rdi
0x18005a036  add     rsp, 40h
0x18005a03a  pop     rdi
0x18005a03b  retn
```
