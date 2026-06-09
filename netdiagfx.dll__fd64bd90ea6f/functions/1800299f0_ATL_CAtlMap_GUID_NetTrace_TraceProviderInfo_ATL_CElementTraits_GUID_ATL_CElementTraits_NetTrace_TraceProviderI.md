# ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::RemoveAll(void)

- ea: `0x1800299f0`
- end: `0x180029a86`
- name: `?RemoveAll@?$CAtlMap@U_GUID@@UTraceProviderInfo@NetTrace@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@UTraceProviderInfo@NetTrace@@@5@@ATL@@QEAAXXZ`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180028940`

## callees

- `0x180015ae0`
- `0x180015d90`
- `0x1800161b0`
- `0x18002930c`
- `0x1800299f0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180029a39`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180029a39`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::RemoveAll(
        __int64 a1)
{
  __int64 i; // rdi
  __int64 v3; // rsi
  __int64 v4; // rdx
  unsigned int v5; // eax
  __int64 result; // rax

  ++*(_DWORD *)(a1 + 48);
  if ( *(_QWORD *)a1 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 16); i = (unsigned int)(i + 1) )
    {
      v3 = *(_QWORD *)(*(_QWORD *)a1 + 8 * i);
      while ( v3 )
      {
        v4 = v3;
        v3 = *(_QWORD *)(v3 + 64);
        ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::FreeNode(
          a1,
          v4);
      }
    }
  }
  operator delete[](*(void **)a1);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  if ( !*(_DWORD *)(a1 + 48) )
  {
    v5 = ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::PickSize(
           a1,
           0);
    ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::InitHashTable(
      a1,
      v5);
  }
  result = ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::FreePlexes(a1);
  --*(_DWORD *)(a1 + 48);
  return result;
}

```

## disassembly

```asm
0x1800299f0  mov     [rsp+arg_0], rbx
0x1800299f5  mov     [rsp+arg_8], rsi
0x1800299fa  push    rdi
0x1800299fb  sub     rsp, 20h
0x1800299ff  mov     rbx, rcx
0x180029a02  inc     dword ptr [rcx+30h]
0x180029a05  cmp     qword ptr [rcx], 0
0x180029a09  jz      short loc_180029A36
0x180029a0b  xor     edi, edi
0x180029a0d  cmp     [rcx+10h], edi
0x180029a10  jbe     short loc_180029A36
0x180029a12  mov     rax, [rbx]
0x180029a15  mov     rsi, [rax+rdi*8]
0x180029a19  jmp     short loc_180029A2A
0x180029a1b  mov     rdx, rsi
0x180029a1e  mov     rsi, [rsi+40h]
0x180029a22  mov     rcx, rbx
0x180029a25  call    ?FreeNode@?$CAtlMap@U_GUID@@UTraceProviderInfo@NetTrace@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@UTraceProviderInfo@NetTrace@@@5@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::FreeNode(ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::CNode *)
0x180029a2a  test    rsi, rsi
0x180029a2d  jnz     short loc_180029A1B
0x180029a2f  inc     edi
0x180029a31  cmp     edi, [rbx+10h]
0x180029a34  jb      short loc_180029A12
0x180029a36  mov     rcx, [rbx]
0x180029a39  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180029a3f  mov     qword ptr [rbx], 0
0x180029a46  mov     qword ptr [rbx+8], 0
0x180029a4e  cmp     dword ptr [rbx+30h], 0
0x180029a52  jnz     short loc_180029A6B
0x180029a54  xor     edx, edx
0x180029a56  mov     rcx, rbx
0x180029a59  call    ?PickSize@?$CAtlMap@VCProblemInstanceKey@@PEAVProblemInstance@@V?$CElementTraits@VCProblemInstanceKey@@@ATL@@V?$CElementTraits@PEAVProblemInstance@@@4@@ATL@@AEBAI_K@Z; ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::PickSize(unsigned __int64)
0x180029a5e  mov     edx, eax
0x180029a60  xor     r8d, r8d
0x180029a63  mov     rcx, rbx
0x180029a66  call    ?InitHashTable@?$CAtlMap@U_GUID@@UTraceProviderInfo@NetTrace@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@UTraceProviderInfo@NetTrace@@@5@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::InitHashTable(uint,bool)
0x180029a6b  mov     rcx, rbx
0x180029a6e  call    ?FreePlexes@?$CAtlMap@U_GUID@@UTraceProviderInfo@NetTrace@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@UTraceProviderInfo@NetTrace@@@5@@ATL@@AEAAXXZ; ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::FreePlexes(void)
0x180029a73  dec     dword ptr [rbx+30h]
0x180029a76  mov     rbx, [rsp+28h+arg_0]
0x180029a7b  mov     rsi, [rsp+28h+arg_8]
0x180029a80  add     rsp, 20h
0x180029a84  pop     rdi
0x180029a85  retn
```
