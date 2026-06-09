# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000f7c0`
- end: `0x18000f8cd`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f178`

## callees

- `0x18000eb5c`
- `0x18000f7c0`
- `0x18001161c`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // edx
  __int64 v7; // rcx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // edx
  char v12; // si
  wil::details *v13; // rcx
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF

  v15 = a1;
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
  if ( v5 )
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(v7) )
  {
    v13 = (wil::details *)*(unsigned int *)Feature_Standalone_26_01_NonSec__descriptor;
    if ( ((unsigned __int8)v13 & 4) == 0 )
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
        v13,
        &v15);
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
0x18000f7c0  mov     [rsp+arg_0], rcx
0x18000f7c5  push    rbx
0x18000f7c6  push    rbp
0x18000f7c7  push    rsi
0x18000f7c8  push    rdi
0x18000f7c9  sub     rsp, 28h
0x18000f7cd  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000f7d4  mov     rbx, rdx
0x18000f7d7  mov     edi, 3
0x18000f7dc  test    rax, rax
0x18000f7df  jz      short loc_18000F7F1
0x18000f7e1  mov     edx, edi
0x18000f7e3  mov     ecx, 38419ACh
0x18000f7e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7ed  mov     edx, eax
0x18000f7ef  jmp     short loc_18000F7FF
0x18000f7f1  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000f7f8  test    rax, rax
0x18000f7fb  jnz     short loc_18000F7E1
0x18000f7fd  xor     edx, edx
0x18000f7ff  mov     r8d, edx
0x18000f802  mov     qword ptr [rbx], 0
0x18000f809  mov     eax, edx
0x18000f80b  and     r8d, 0FFFFFF3Fh
0x18000f812  and     edx, 80h
0x18000f818  mov     ecx, r8d
0x18000f81b  and     ecx, edi
0x18000f81d  mov     ebp, 40h ; '@'
0x18000f822  shl     ecx, 2
0x18000f825  and     eax, ebp
0x18000f827  or      ecx, eax
0x18000f829  shl     ecx, 2
0x18000f82c  or      ecx, edx
0x18000f82e  lea     edx, ds:0[rcx*8]
0x18000f835  test    r8d, r8d
0x18000f838  jnz     short loc_18000F841
0x18000f83a  mov     ecx, ebp
0x18000f83c  mov     r8d, ebp
0x18000f83f  jmp     short loc_18000F84D
0x18000f841  xor     ecx, ecx
0x18000f843  cmp     r8d, 2
0x18000f847  cmovz   ecx, ebp
0x18000f84a  mov     r8d, ecx
0x18000f84d  mov     eax, edx
0x18000f84f  mov     edi, 1
0x18000f854  or      eax, r8d
0x18000f857  or      edx, ecx
0x18000f859  mov     [rbx], eax
0x18000f85b  bt      edx, 0Ah
0x18000f85f  jnb     short loc_18000F86E
0x18000f861  cmp     edx, 800h
0x18000f867  jb      short loc_18000F86E
0x18000f869  mov     sil, dil
0x18000f86c  jmp     short loc_18000F878
0x18000f86e  xor     sil, sil
0x18000f871  xor     cl, cl
0x18000f873  test    bpl, dl
0x18000f876  jz      short loc_18000F8AD
0x18000f878  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x18000f87d  test    al, al
0x18000f87f  jz      short loc_18000F89E
0x18000f881  mov     rax, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18000f888  mov     ecx, [rax]
0x18000f88a  test    cl, 4
0x18000f88d  jnz     short loc_18000F899
0x18000f88f  lea     rdx, [rsp+48h+arg_0]
0x18000f894  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x18000f899  mov     cl, dil
0x18000f89c  jmp     short loc_18000F8A0
0x18000f89e  xor     cl, cl
0x18000f8a0  test    sil, sil
0x18000f8a3  jz      short loc_18000F8AD
0x18000f8a5  test    cl, cl
0x18000f8a7  jnz     short loc_18000F8AD
0x18000f8a9  btr     dword ptr [rbx], 0Ah
0x18000f8ad  mov     eax, [rbx]
0x18000f8af  test    bpl, al
0x18000f8b2  jz      short loc_18000F8B8
0x18000f8b4  test    cl, cl
0x18000f8b6  jnz     short loc_18000F8BA
0x18000f8b8  xor     edi, edi
0x18000f8ba  and     eax, 0FFFFFFFEh
0x18000f8bd  or      eax, edi
0x18000f8bf  mov     [rbx], eax
0x18000f8c1  mov     rax, rbx
0x18000f8c4  add     rsp, 28h
0x18000f8c8  pop     rdi
0x18000f8c9  pop     rsi
0x18000f8ca  pop     rbp
0x18000f8cb  pop     rbx
0x18000f8cc  retn
```
