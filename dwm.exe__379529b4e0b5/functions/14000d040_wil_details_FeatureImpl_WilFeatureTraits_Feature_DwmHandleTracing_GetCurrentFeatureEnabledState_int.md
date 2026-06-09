# wil::details::FeatureImpl<__WilFeatureTraits_Feature_DwmHandleTracing>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14000d040`
- end: `0x14000d0c7`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DwmHandleTracing@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000cf54`

## callees

- `0x14000d040`
- `0x140010010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_DwmHandleTracing>::GetCurrentFeatureEnabledState(
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
    v4 = v2(24159631, 0);
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
0x14000d040  push    rbx
0x14000d042  sub     rsp, 20h
0x14000d046  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x14000d04d  mov     rbx, rdx
0x14000d050  xor     edx, edx
0x14000d052  test    rax, rax
0x14000d055  jnz     short loc_14000D063
0x14000d057  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x14000d05e  test    rax, rax
0x14000d061  jz      short loc_14000D06F
0x14000d063  mov     ecx, 170A58Fh
0x14000d068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d06d  mov     edx, eax
0x14000d06f  mov     r9d, edx
0x14000d072  mov     qword ptr [rbx], 0
0x14000d079  and     r9d, 0FFFFFF3Fh
0x14000d080  mov     eax, edx
0x14000d082  and     edx, 80h
0x14000d088  mov     ecx, r9d
0x14000d08b  and     ecx, 3
0x14000d08e  mov     r8d, 40h ; '@'
0x14000d094  shl     ecx, 2
0x14000d097  and     eax, r8d
0x14000d09a  or      ecx, eax
0x14000d09c  shl     ecx, 2
0x14000d09f  or      ecx, edx
0x14000d0a1  shl     ecx, 3
0x14000d0a4  test    r9d, r9d
0x14000d0a7  jz      short loc_14000D0B6
0x14000d0a9  xor     eax, eax
0x14000d0ab  cmp     r9d, 2
0x14000d0af  cmovz   eax, r8d
0x14000d0b3  mov     r8d, eax
0x14000d0b6  or      ecx, r8d
0x14000d0b9  mov     rax, rbx
0x14000d0bc  or      ecx, 1
0x14000d0bf  mov     [rbx], ecx
0x14000d0c1  add     rsp, 20h
0x14000d0c5  pop     rbx
0x14000d0c6  retn
```
