# NcaEtwPerfTrackUpdate

- ea: `0x180018d84`
- end: `0x180018e54`
- name: `NcaEtwPerfTrackUpdate`
- size: `208`
- prototype: `void __fastcall(_DWORD *, _OWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180015f20`

## callees

- `0x180018588`
- `0x180018780`
- `0x180018904`
- `0x180018c40`
- `0x180018d84`

## pseudocode

```c
void __fastcall NcaEtwPerfTrackUpdate(_DWORD *a1, _OWORD *a2)
{
  int v2; // eax
  _DWORD *v3; // rsi
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  int i; // edi
  int j; // edi
  unsigned int v11[14]; // [rsp+20h] [rbp-38h] BYREF

  v2 = gNcaEtwPerfTrackInitialized;
  v3 = a1 + 120;
  if ( !gNcaEtwPerfTrackInitialized )
  {
    if ( *v3 || a1[35] != 1 || a1[20] != gNcaEtwPerfTrackInitialized )
      return;
    gNcaEtwPerfTrackDeploymentID = NcaEtwPerfTrackGetHashId(gNcaEtwPerfTrackInitialized + 2);
    gNcaEtwPerfTrackSessionID = NcaEtwPerfTrackGetHashId(1);
    for ( i = 0; i < 7; ++i )
    {
      if ( (unsigned int)i <= 3 )
        NcaEtwPerfTrackScenarioPublishStartEvent((unsigned int)i, v6, v7, v8);
    }
    v2 = 1;
    gNcaEtwPerfTrackInitialized = 1;
  }
  if ( v2 == 1 )
  {
    if ( *v3 == 1 || !a1[35] || a1[20] == 1 )
    {
      NcaEtwPerfTrackStopScenarios();
      gNcaEtwPerfTrackInitialized = 0;
    }
    else
    {
      for ( j = 0; j < 7; ++j )
      {
        *(_OWORD *)v11 = *a2;
        NcaEtwPerfTrackScenarioUpdate(j, a1, v11);
      }
    }
  }
}

```

## disassembly

```asm
0x180018d84  push    rbx
0x180018d86  push    rbp
0x180018d87  push    rsi
0x180018d88  push    rdi
0x180018d89  sub     rsp, 38h
0x180018d8d  mov     eax, cs:?gNcaEtwPerfTrackInitialized@@3HA; int gNcaEtwPerfTrackInitialized
0x180018d93  lea     rsi, [rcx+1E0h]
0x180018d9a  mov     rbp, rdx
0x180018d9d  mov     rbx, rcx
0x180018da0  test    eax, eax
0x180018da2  jnz     short loc_180018E00
0x180018da4  cmp     [rsi], eax
0x180018da6  jnz     loc_180018E4A
0x180018dac  cmp     dword ptr [rcx+8Ch], 1
0x180018db3  jnz     loc_180018E4A
0x180018db9  cmp     [rcx+50h], eax
0x180018dbc  jnz     loc_180018E4A
0x180018dc2  lea     ecx, [rax+2]
0x180018dc5  call    NcaEtwPerfTrackGetHashId
0x180018dca  mov     ecx, 1
0x180018dcf  mov     cs:?gNcaEtwPerfTrackDeploymentID@@3KA, eax; ulong gNcaEtwPerfTrackDeploymentID
0x180018dd5  call    NcaEtwPerfTrackGetHashId
0x180018dda  mov     cs:?gNcaEtwPerfTrackSessionID@@3KA, eax; ulong gNcaEtwPerfTrackSessionID
0x180018de0  xor     edi, edi
0x180018de2  cmp     edi, 3
0x180018de5  ja      short loc_180018DEE
0x180018de7  mov     ecx, edi
0x180018de9  call    ?NcaEtwPerfTrackScenarioPublishStartEvent@@YAXW4NCA_ETW_PERFTRACK_SCENARIO_TYPE_@@@Z; NcaEtwPerfTrackScenarioPublishStartEvent(NCA_ETW_PERFTRACK_SCENARIO_TYPE_)
0x180018dee  inc     edi
0x180018df0  cmp     edi, 7
0x180018df3  jl      short loc_180018DE2
0x180018df5  mov     eax, 1
0x180018dfa  mov     cs:?gNcaEtwPerfTrackInitialized@@3HA, eax; int gNcaEtwPerfTrackInitialized
0x180018e00  cmp     eax, 1
0x180018e03  jnz     short loc_180018E4A
0x180018e05  cmp     [rsi], eax
0x180018e07  jz      short loc_180018E3B
0x180018e09  cmp     dword ptr [rbx+8Ch], 0
0x180018e10  jz      short loc_180018E3B
0x180018e12  cmp     [rbx+50h], eax
0x180018e15  jz      short loc_180018E3B
0x180018e17  xor     edi, edi
0x180018e19  movaps  xmm0, xmmword ptr [rbp+0]
0x180018e1d  lea     r8, [rsp+58h+var_38]
0x180018e22  mov     rdx, rbx
0x180018e25  movdqa  xmmword ptr [rsp+58h+var_38], xmm0
0x180018e2b  mov     ecx, edi
0x180018e2d  call    ?NcaEtwPerfTrackScenarioUpdate@@YAXW4NCA_ETW_PERFTRACK_SCENARIO_TYPE_@@PEBUNCA_EVIDENCE_@@UNCA_STATUS_EVENT_@@@Z; NcaEtwPerfTrackScenarioUpdate(NCA_ETW_PERFTRACK_SCENARIO_TYPE_,NCA_EVIDENCE_ const *,NCA_STATUS_EVENT_)
0x180018e32  inc     edi
0x180018e34  cmp     edi, 7
0x180018e37  jl      short loc_180018E19
0x180018e39  jmp     short loc_180018E4A
0x180018e3b  call    ?NcaEtwPerfTrackStopScenarios@@YAXXZ; NcaEtwPerfTrackStopScenarios(void)
0x180018e40  mov     cs:?gNcaEtwPerfTrackInitialized@@3HA, 0; int gNcaEtwPerfTrackInitialized
0x180018e4a  add     rsp, 38h
0x180018e4e  pop     rdi
0x180018e4f  pop     rsi
0x180018e50  pop     rbp
0x180018e51  pop     rbx
0x180018e52  retn
```
