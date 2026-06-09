# wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12IndependentDevices>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000eddc`
- end: `0x18000ee63`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12IndependentDevices@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ecf0`

## callees

- `0x18000eddc`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12IndependentDevices>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, _QWORD); // rax
  int v4; // edx
  int v5; // r8d
  int v6; // eax
  _QWORD *result; // rax

  v2 = (__int64 (__fastcall *)(__int64, _QWORD))g_wil_details_internalGetFeatureEnabledState;
  v4 = 0;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, _QWORD))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(39847774, 0);
  }
  *a2 = 0;
  v5 = 64;
  if ( (v4 & 0xFFFFFF3F) != 0 )
  {
    v6 = 0;
    if ( (v4 & 0xFFFFFF3F) == 2 )
      v6 = 64;
    v5 = v6;
  }
  result = a2;
  *(_DWORD *)a2 = v5 | (8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))))) | 1;
  return result;
}

```

## disassembly

```asm
0x18000eddc  push    rbx
0x18000edde  sub     rsp, 20h
0x18000ede2  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ede9  mov     rbx, rdx
0x18000edec  xor     edx, edx
0x18000edee  test    rax, rax
0x18000edf1  jnz     short loc_18000EDFF
0x18000edf3  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000edfa  test    rax, rax
0x18000edfd  jz      short loc_18000EE0B
0x18000edff  mov     ecx, 260075Eh
0x18000ee04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee09  mov     edx, eax
0x18000ee0b  mov     r9d, edx
0x18000ee0e  mov     qword ptr [rbx], 0
0x18000ee15  and     r9d, 0FFFFFF3Fh
0x18000ee1c  mov     eax, edx
0x18000ee1e  and     edx, 80h
0x18000ee24  mov     ecx, r9d
0x18000ee27  and     ecx, 3
0x18000ee2a  mov     r8d, 40h ; '@'
0x18000ee30  shl     ecx, 2
0x18000ee33  and     eax, r8d
0x18000ee36  or      ecx, eax
0x18000ee38  shl     ecx, 2
0x18000ee3b  or      ecx, edx
0x18000ee3d  shl     ecx, 3
0x18000ee40  test    r9d, r9d
0x18000ee43  jz      short loc_18000EE52
0x18000ee45  xor     eax, eax
0x18000ee47  cmp     r9d, 2
0x18000ee4b  cmovz   eax, r8d
0x18000ee4f  mov     r8d, eax
0x18000ee52  or      ecx, r8d
0x18000ee55  mov     rax, rbx
0x18000ee58  or      ecx, 1
0x18000ee5b  mov     [rbx], ecx
0x18000ee5d  add     rsp, 20h
0x18000ee61  pop     rbx
0x18000ee62  retn
```
