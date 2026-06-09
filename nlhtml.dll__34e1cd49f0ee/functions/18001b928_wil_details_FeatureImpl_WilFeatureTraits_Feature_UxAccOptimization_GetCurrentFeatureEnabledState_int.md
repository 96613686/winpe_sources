# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001b928`
- end: `0x18001b9ea`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b714`

## callees

- `0x18001b928`
- `0x18001bc1c`
- `0x18001beec`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  int v7; // ecx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // cl

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x2E30A37, (unsigned int)a2, a3, a4);
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
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 || (v12 = 0, (v11 & 0x40) != 0) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_Future>::GetImpl'::`2'::impl);
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
0x18001b928  mov     [rsp+arg_0], rbx
0x18001b92d  mov     [rsp+arg_8], rsi
0x18001b932  push    rdi
0x18001b933  sub     rsp, 20h
0x18001b937  mov     ecx, 2E30A37h; this
0x18001b93c  mov     rbx, rdx
0x18001b93f  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001b944  mov     edx, eax
0x18001b946  mov     qword ptr [rbx], 0
0x18001b94d  and     edx, 0FFFFFF3Fh
0x18001b953  mov     ecx, eax
0x18001b955  and     eax, 80h
0x18001b95a  mov     r8d, edx
0x18001b95d  and     r8d, 3
0x18001b961  mov     esi, 40h ; '@'
0x18001b966  shl     r8d, 2
0x18001b96a  and     ecx, esi
0x18001b96c  or      r8d, ecx
0x18001b96f  shl     r8d, 2
0x18001b973  or      r8d, eax
0x18001b976  shl     r8d, 3
0x18001b97a  test    edx, edx
0x18001b97c  jnz     short loc_18001B984
0x18001b97e  mov     ecx, esi
0x18001b980  mov     edx, esi
0x18001b982  jmp     short loc_18001B98E
0x18001b984  xor     ecx, ecx
0x18001b986  cmp     edx, 2
0x18001b989  cmovz   ecx, esi
0x18001b98c  mov     edx, ecx
0x18001b98e  mov     eax, r8d
0x18001b991  mov     edi, 1
0x18001b996  or      eax, edx
0x18001b998  or      r8d, ecx
0x18001b99b  mov     [rbx], eax
0x18001b99d  bt      r8d, 0Ah
0x18001b9a2  jnb     short loc_18001B9AD
0x18001b9a4  cmp     r8d, 800h
0x18001b9ab  jnb     short loc_18001B9B4
0x18001b9ad  xor     cl, cl
0x18001b9af  test    sil, r8b
0x18001b9b2  jz      short loc_18001B9C3
0x18001b9b4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_Future@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future> `wil::Feature<__WilFeatureTraits_Feature_Standalone_Future>::GetImpl(void)'::`2'::impl
0x18001b9bb  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001b9c0  mov     cl, dil
0x18001b9c3  mov     eax, [rbx]
0x18001b9c5  test    sil, al
0x18001b9c8  jz      short loc_18001B9CE
0x18001b9ca  test    cl, cl
0x18001b9cc  jnz     short loc_18001B9D0
0x18001b9ce  xor     edi, edi
0x18001b9d0  mov     rsi, [rsp+28h+arg_8]
0x18001b9d5  and     eax, 0FFFFFFFEh
0x18001b9d8  or      eax, edi
0x18001b9da  mov     [rbx], eax
0x18001b9dc  mov     rax, rbx
0x18001b9df  mov     rbx, [rsp+28h+arg_0]
0x18001b9e4  add     rsp, 20h
0x18001b9e8  pop     rdi
0x18001b9e9  retn
```
