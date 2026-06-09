# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180012df0`
- end: `0x180012ed4`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `228`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012ae4`

## callees

- `0x180012df0`
- `0x1800147f4`
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
  __int64 v7; // rdx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // ecx

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
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 || (LOBYTE(v7) = 0, (v11 & 0x40) != 0) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_Standalone_Future>::GetImpl'::`2'::impl,
      v7);
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
0x180012df0  mov     [rsp+arg_0], rbx
0x180012df5  mov     [rsp+arg_8], rsi
0x180012dfa  push    rdi
0x180012dfb  sub     rsp, 20h
0x180012dff  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012e06  mov     rbx, rdx
0x180012e09  mov     edi, 3
0x180012e0e  test    rax, rax
0x180012e11  jz      short loc_180012E23
0x180012e13  mov     edx, edi
0x180012e15  mov     ecx, 2E30A37h
0x180012e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e1f  mov     edx, eax
0x180012e21  jmp     short loc_180012E31
0x180012e23  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012e2a  test    rax, rax
0x180012e2d  jnz     short loc_180012E13
0x180012e2f  xor     edx, edx
0x180012e31  mov     r8d, edx
0x180012e34  mov     qword ptr [rbx], 0
0x180012e3b  and     r8d, 0FFFFFF3Fh
0x180012e42  mov     eax, edx
0x180012e44  and     edx, 80h
0x180012e4a  mov     ecx, r8d
0x180012e4d  and     ecx, edi
0x180012e4f  mov     esi, 40h ; '@'
0x180012e54  shl     ecx, 2
0x180012e57  and     eax, esi
0x180012e59  or      ecx, eax
0x180012e5b  shl     ecx, 2
0x180012e5e  or      ecx, edx
0x180012e60  shl     ecx, 3
0x180012e63  test    r8d, r8d
0x180012e66  jnz     short loc_180012E6F
0x180012e68  mov     edx, esi
0x180012e6a  mov     r8d, esi
0x180012e6d  jmp     short loc_180012E7B
0x180012e6f  xor     edx, edx
0x180012e71  cmp     r8d, 2
0x180012e75  cmovz   edx, esi
0x180012e78  mov     r8d, edx
0x180012e7b  mov     eax, ecx
0x180012e7d  mov     edi, 1
0x180012e82  or      eax, r8d
0x180012e85  or      ecx, edx
0x180012e87  mov     [rbx], eax
0x180012e89  bt      ecx, 0Ah
0x180012e8d  jnb     short loc_180012E97
0x180012e8f  cmp     ecx, 800h
0x180012e95  jnb     short loc_180012E9E
0x180012e97  xor     dl, dl
0x180012e99  test    sil, cl
0x180012e9c  jz      short loc_180012EAD
0x180012e9e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_Future@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future> `wil::Feature<__WilFeatureTraits_Feature_Standalone_Future>::GetImpl(void)'::`2'::impl
0x180012ea5  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180012eaa  mov     dl, dil
0x180012ead  mov     eax, [rbx]
0x180012eaf  test    sil, al
0x180012eb2  jz      short loc_180012EB8
0x180012eb4  test    dl, dl
0x180012eb6  jnz     short loc_180012EBA
0x180012eb8  xor     edi, edi
0x180012eba  mov     rsi, [rsp+28h+arg_8]
0x180012ebf  and     eax, 0FFFFFFFEh
0x180012ec2  or      eax, edi
0x180012ec4  mov     [rbx], eax
0x180012ec6  mov     rax, rbx
0x180012ec9  mov     rbx, [rsp+28h+arg_0]
0x180012ece  add     rsp, 20h
0x180012ed2  pop     rdi
0x180012ed3  retn
```
