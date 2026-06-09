# wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001183c`
- end: `0x1800118be`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011488`

## callees

- `0x18001183c`
- `0x180014da4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // edx
  int v7; // r8d
  int v8; // eax
  int v9; // r8d
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x16D0B7E, 3u, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v8 = 0;
    if ( v6 == 2 )
      v8 = 64;
  }
  else
  {
    v8 = 64;
  }
  v9 = v8 | v7;
  result = a2;
  *(_DWORD *)a2 = ((v9 & 0x40) != 0) | v9;
  return result;
}

```

## disassembly

```asm
0x18001183c  push    rbx
0x18001183e  sub     rsp, 20h
0x180011842  mov     rbx, rdx
0x180011845  mov     ecx, 16D0B7Eh; this
0x18001184a  mov     edx, 3; unsigned int
0x18001184f  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180011854  mov     edx, eax
0x180011856  mov     qword ptr [rbx], 0
0x18001185d  and     edx, 0FFFFFF3Fh
0x180011863  mov     ecx, eax
0x180011865  and     eax, 80h
0x18001186a  mov     r8d, edx
0x18001186d  and     r8d, 3
0x180011871  mov     r9d, 40h ; '@'
0x180011877  shl     r8d, 2
0x18001187b  and     ecx, r9d
0x18001187e  or      r8d, ecx
0x180011881  shl     r8d, 2
0x180011885  or      r8d, eax
0x180011888  shl     r8d, 3
0x18001188c  test    edx, edx
0x18001188e  jnz     short loc_180011895
0x180011890  mov     eax, r9d
0x180011893  jmp     short loc_18001189E
0x180011895  xor     eax, eax
0x180011897  cmp     edx, 2
0x18001189a  cmovz   eax, r9d
0x18001189e  or      r8d, eax
0x1800118a1  test    r9b, r8b
0x1800118a4  jz      short loc_1800118AD
0x1800118a6  mov     eax, 1
0x1800118ab  jmp     short loc_1800118AF
0x1800118ad  xor     eax, eax
0x1800118af  or      r8d, eax
0x1800118b2  mov     rax, rbx
0x1800118b5  mov     [rbx], r8d
0x1800118b8  add     rsp, 20h
0x1800118bc  pop     rbx
0x1800118bd  retn
```
