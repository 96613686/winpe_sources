# NcaEvCollHttpProbeCollectUpdateEvidence(NCA_EVCOLL_PROBE_ *,int,NCA_PROBE_TEST_TYPE_,NCA_EVCOLL_PROBE_PRV_RESULT_,int)

- ea: `0x180003720`
- end: `0x18000375c`
- name: `?NcaEvCollHttpProbeCollectUpdateEvidence@@YAXPEAUNCA_EVCOLL_PROBE_@@HW4NCA_PROBE_TEST_TYPE_@@W4NCA_EVCOLL_PROBE_PRV_RESULT_@@H@Z`
- size: `60`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180010ec4`

## callees

- `0x180001c70`
- `0x180003720`

## pseudocode

```c
__int64 __fastcall NcaEvCollHttpProbeCollectUpdateEvidence(__int64 a1, __int64 a2, unsigned int a3, int a4, int a5)
{
  __int64 result; // rax
  __int64 v6; // r8

  result = a3;
  if ( a5 || *(_DWORD *)(a1 + 224) != a4 || (_DWORD)a2 == 1 && a3 == 2 && a4 == 2 )
  {
    v6 = *(_QWORD *)(a1 + 32);
    *(_DWORD *)(a1 + 224) = a4;
    return NcaEvCollProbesUpdateEvidenceSummary((unsigned int)result, a2, *(unsigned int *)(v6 + 32), v6);
  }
  return result;
}

```

## disassembly

```asm
0x180003720  cmp     [rsp+arg_20], 0
0x180003725  mov     eax, r8d
0x180003728  jnz     short loc_180003742
0x18000372a  cmp     [rcx+0E0h], r9d
0x180003731  jnz     short loc_180003742
0x180003733  cmp     edx, 1
0x180003736  jnz     short locret_18000375B
0x180003738  cmp     eax, 2
0x18000373b  jnz     short locret_18000375B
0x18000373d  cmp     r9d, r8d
0x180003740  jnz     short locret_18000375B
0x180003742  mov     r8, [rcx+20h]
0x180003746  mov     [rcx+0E0h], r9d
0x18000374d  mov     r9, r8
0x180003750  mov     ecx, eax
0x180003752  mov     r8d, [r8+20h]
0x180003756  jmp     ?NcaEvCollProbesUpdateEvidenceSummary@@YAXW4NCA_PROBE_TEST_TYPE_@@HKPEAUNCA_EVCOLL_USER_PROBES_@@@Z; NcaEvCollProbesUpdateEvidenceSummary(NCA_PROBE_TEST_TYPE_,int,ulong,NCA_EVCOLL_USER_PROBES_ *)
0x18000375b  retn
```
