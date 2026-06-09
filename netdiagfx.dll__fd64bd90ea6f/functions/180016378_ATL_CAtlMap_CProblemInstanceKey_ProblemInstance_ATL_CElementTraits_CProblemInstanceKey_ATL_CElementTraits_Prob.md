# ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::RemoveAll(void)

- ea: `0x180016378`
- end: `0x18001640e`
- name: `?RemoveAll@?$CAtlMap@VCProblemInstanceKey@@PEAVProblemInstance@@V?$CElementTraits@VCProblemInstanceKey@@@ATL@@V?$CElementTraits@PEAVProblemInstance@@@4@@ATL@@QEAAXXZ`
- size: `150`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180014ef8`
- `0x180017ed8`

## callees

- `0x180015a64`
- `0x180015ae0`
- `0x180015d90`
- `0x1800161b0`
- `0x180016378`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800163c1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800163c1`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::RemoveAll(
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
        v3 = *(_QWORD *)(v3 + 32);
        ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::FreeNode(
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
0x180016378  mov     [rsp+arg_0], rbx
0x18001637d  mov     [rsp+arg_8], rsi
0x180016382  push    rdi
0x180016383  sub     rsp, 20h
0x180016387  mov     rbx, rcx
0x18001638a  inc     dword ptr [rcx+30h]
0x18001638d  cmp     qword ptr [rcx], 0
0x180016391  jz      short loc_1800163BE
0x180016393  xor     edi, edi
0x180016395  cmp     [rcx+10h], edi
0x180016398  jbe     short loc_1800163BE
0x18001639a  mov     rax, [rbx]
0x18001639d  mov     rsi, [rax+rdi*8]
0x1800163a1  jmp     short loc_1800163B2
0x1800163a3  mov     rdx, rsi
0x1800163a6  mov     rsi, [rsi+20h]
0x1800163aa  mov     rcx, rbx
0x1800163ad  call    ?FreeNode@?$CAtlMap@VCProblemInstanceKey@@PEAVProblemInstance@@V?$CElementTraits@VCProblemInstanceKey@@@ATL@@V?$CElementTraits@PEAVProblemInstance@@@4@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::FreeNode(ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::CNode *)
0x1800163b2  test    rsi, rsi
0x1800163b5  jnz     short loc_1800163A3
0x1800163b7  inc     edi
0x1800163b9  cmp     edi, [rbx+10h]
0x1800163bc  jb      short loc_18001639A
0x1800163be  mov     rcx, [rbx]
0x1800163c1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800163c7  mov     qword ptr [rbx], 0
0x1800163ce  mov     qword ptr [rbx+8], 0
0x1800163d6  cmp     dword ptr [rbx+30h], 0
0x1800163da  jnz     short loc_1800163F3
0x1800163dc  xor     edx, edx
0x1800163de  mov     rcx, rbx
0x1800163e1  call    ?PickSize@?$CAtlMap@VCProblemInstanceKey@@PEAVProblemInstance@@V?$CElementTraits@VCProblemInstanceKey@@@ATL@@V?$CElementTraits@PEAVProblemInstance@@@4@@ATL@@AEBAI_K@Z; ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::PickSize(unsigned __int64)
0x1800163e6  mov     edx, eax
0x1800163e8  xor     r8d, r8d
0x1800163eb  mov     rcx, rbx
0x1800163ee  call    ?InitHashTable@?$CAtlMap@U_GUID@@UTraceProviderInfo@NetTrace@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@UTraceProviderInfo@NetTrace@@@5@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::InitHashTable(uint,bool)
0x1800163f3  mov     rcx, rbx
0x1800163f6  call    ?FreePlexes@?$CAtlMap@U_GUID@@UTraceProviderInfo@NetTrace@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@UTraceProviderInfo@NetTrace@@@5@@ATL@@AEAAXXZ; ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::FreePlexes(void)
0x1800163fb  dec     dword ptr [rbx+30h]
0x1800163fe  mov     rbx, [rsp+28h+arg_0]
0x180016403  mov     rsi, [rsp+28h+arg_8]
0x180016408  add     rsp, 20h
0x18001640c  pop     rdi
0x18001640d  retn
```
