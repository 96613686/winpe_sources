# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ZeroInitGAlloc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000b9b8`
- end: `0x18000ba3a`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ZeroInitGAlloc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b70c`

## callees

- `0x180009604`
- `0x18000b9b8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ZeroInitGAlloc>::GetCurrentFeatureEnabledState(
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
  int v10; // r8d
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3723937, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3))));
  v8 = 0;
  v9 = 8 * v7;
  if ( v6 == 2 )
    v8 = 64;
  v10 = v8 | v9;
  result = a2;
  *(_DWORD *)a2 = ((v10 & 0x40) != 0) | v10;
  return result;
}

```

## disassembly

```asm
0x18000b9b8  push    rbx
0x18000b9ba  sub     rsp, 20h
0x18000b9be  mov     ecx, 3723937h; this
0x18000b9c3  mov     rbx, rdx
0x18000b9c6  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000b9cb  mov     edx, eax
0x18000b9cd  mov     qword ptr [rbx], 0
0x18000b9d4  mov     ecx, eax
0x18000b9d6  and     edx, 0FFFFFF3Fh
0x18000b9dc  and     eax, 80h
0x18000b9e1  mov     r8d, edx
0x18000b9e4  and     r8d, 3
0x18000b9e8  mov     r9d, 40h ; '@'
0x18000b9ee  shl     r8d, 2
0x18000b9f2  and     ecx, r9d
0x18000b9f5  or      r8d, ecx
0x18000b9f8  shl     r8d, 2
0x18000b9fc  or      r8d, eax
0x18000b9ff  xor     eax, eax
0x18000ba01  shl     r8d, 3
0x18000ba05  test    edx, edx
0x18000ba07  jz      short loc_18000BA10
0x18000ba09  cmp     edx, 2
0x18000ba0c  cmovz   eax, r9d
0x18000ba10  or      r8d, eax
0x18000ba13  mov     ecx, 0C00h
0x18000ba18  mov     eax, r8d
0x18000ba1b  and     eax, ecx
0x18000ba1d  test    r9b, r8b
0x18000ba20  jz      short loc_18000BA29
0x18000ba22  mov     eax, 1
0x18000ba27  jmp     short loc_18000BA2B
0x18000ba29  xor     eax, eax
0x18000ba2b  or      r8d, eax
0x18000ba2e  mov     rax, rbx
0x18000ba31  mov     [rbx], r8d
0x18000ba34  add     rsp, 20h
0x18000ba38  pop     rbx
0x18000ba39  retn
```
