# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000f598`
- end: `0x18000f6a5`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000efb8`

## callees

- `0x18000ecd0`
- `0x18000f598`
- `0x180011660`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(
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
    v4 = v2(58989002, 3);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(v7) )
  {
    v13 = (wil::details *)*(unsigned int *)Feature_Standalone_26_02_NonSec__descriptor;
    if ( ((unsigned __int8)v13 & 4) == 0 )
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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
0x18000f598  mov     [rsp+arg_0], rcx
0x18000f59d  push    rbx
0x18000f59e  push    rbp
0x18000f59f  push    rsi
0x18000f5a0  push    rdi
0x18000f5a1  sub     rsp, 28h
0x18000f5a5  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000f5ac  mov     rbx, rdx
0x18000f5af  mov     edi, 3
0x18000f5b4  test    rax, rax
0x18000f5b7  jz      short loc_18000F5C9
0x18000f5b9  mov     edx, edi
0x18000f5bb  mov     ecx, 38419CAh
0x18000f5c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5c5  mov     edx, eax
0x18000f5c7  jmp     short loc_18000F5D7
0x18000f5c9  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000f5d0  test    rax, rax
0x18000f5d3  jnz     short loc_18000F5B9
0x18000f5d5  xor     edx, edx
0x18000f5d7  mov     r8d, edx
0x18000f5da  mov     qword ptr [rbx], 0
0x18000f5e1  mov     eax, edx
0x18000f5e3  and     r8d, 0FFFFFF3Fh
0x18000f5ea  and     edx, 80h
0x18000f5f0  mov     ecx, r8d
0x18000f5f3  and     ecx, edi
0x18000f5f5  mov     ebp, 40h ; '@'
0x18000f5fa  shl     ecx, 2
0x18000f5fd  and     eax, ebp
0x18000f5ff  or      ecx, eax
0x18000f601  shl     ecx, 2
0x18000f604  or      ecx, edx
0x18000f606  lea     edx, ds:0[rcx*8]
0x18000f60d  test    r8d, r8d
0x18000f610  jnz     short loc_18000F619
0x18000f612  mov     ecx, ebp
0x18000f614  mov     r8d, ebp
0x18000f617  jmp     short loc_18000F625
0x18000f619  xor     ecx, ecx
0x18000f61b  cmp     r8d, 2
0x18000f61f  cmovz   ecx, ebp
0x18000f622  mov     r8d, ecx
0x18000f625  mov     eax, edx
0x18000f627  mov     edi, 1
0x18000f62c  or      eax, r8d
0x18000f62f  or      edx, ecx
0x18000f631  mov     [rbx], eax
0x18000f633  bt      edx, 0Ah
0x18000f637  jnb     short loc_18000F646
0x18000f639  cmp     edx, 800h
0x18000f63f  jb      short loc_18000F646
0x18000f641  mov     sil, dil
0x18000f644  jmp     short loc_18000F650
0x18000f646  xor     sil, sil
0x18000f649  xor     cl, cl
0x18000f64b  test    bpl, dl
0x18000f64e  jz      short loc_18000F685
0x18000f650  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x18000f655  test    al, al
0x18000f657  jz      short loc_18000F676
0x18000f659  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18000f660  mov     ecx, [rax]
0x18000f662  test    cl, 4
0x18000f665  jnz     short loc_18000F671
0x18000f667  lea     rdx, [rsp+48h+arg_0]
0x18000f66c  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x18000f671  mov     cl, dil
0x18000f674  jmp     short loc_18000F678
0x18000f676  xor     cl, cl
0x18000f678  test    sil, sil
0x18000f67b  jz      short loc_18000F685
0x18000f67d  test    cl, cl
0x18000f67f  jnz     short loc_18000F685
0x18000f681  btr     dword ptr [rbx], 0Ah
0x18000f685  mov     eax, [rbx]
0x18000f687  test    bpl, al
0x18000f68a  jz      short loc_18000F690
0x18000f68c  test    cl, cl
0x18000f68e  jnz     short loc_18000F692
0x18000f690  xor     edi, edi
0x18000f692  and     eax, 0FFFFFFFEh
0x18000f695  or      eax, edi
0x18000f697  mov     [rbx], eax
0x18000f699  mov     rax, rbx
0x18000f69c  add     rsp, 28h
0x18000f6a0  pop     rdi
0x18000f6a1  pop     rsi
0x18000f6a2  pop     rbp
0x18000f6a3  pop     rbx
0x18000f6a4  retn
```
