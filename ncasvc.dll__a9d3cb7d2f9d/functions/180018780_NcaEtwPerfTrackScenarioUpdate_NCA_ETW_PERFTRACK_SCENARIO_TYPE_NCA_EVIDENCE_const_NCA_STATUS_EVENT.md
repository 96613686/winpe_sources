# NcaEtwPerfTrackScenarioUpdate(NCA_ETW_PERFTRACK_SCENARIO_TYPE_,NCA_EVIDENCE_ const *,NCA_STATUS_EVENT_)

- ea: `0x180018780`
- end: `0x1800188fe`
- name: `?NcaEtwPerfTrackScenarioUpdate@@YAXW4NCA_ETW_PERFTRACK_SCENARIO_TYPE_@@PEBUNCA_EVIDENCE_@@UNCA_STATUS_EVENT_@@@Z`
- size: `382`
- prototype: `void __fastcall(int, _DWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180018d84`

## callees

- `0x180018588`
- `0x180018670`
- `0x180018780`

## pseudocode

```c
void __fastcall NcaEtwPerfTrackScenarioUpdate(int a1, _DWORD *a2, unsigned int *a3)
{
  unsigned int *v3; // r9
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  unsigned int v9; // eax
  unsigned int v10; // ecx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int v15; // ecx
  unsigned int v16; // eax

  v3 = a3;
  if ( !a1 )
  {
    if ( (_DWORD)gNcaEtwPerfTrackScenarioState != 1 )
      return;
    if ( *a3 == 3 )
    {
      v11 = a3[1];
      v12 = 3;
    }
    else
    {
      if ( *a3 != 2 )
        return;
      v11 = 0;
      v12 = 0;
    }
    v13 = 0;
    goto LABEL_39;
  }
  v4 = a1 - 1;
  if ( !v4 )
  {
    if ( dword_180029ACC != 1 || a2[45] != 1 )
      return;
    v11 = a3[1];
    v13 = 1;
    v12 = *v3;
    goto LABEL_39;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    if ( dword_180029AD0 != 1 || *a3 != 2 )
      return;
    v11 = a3[1];
    v12 = 2;
    v13 = 2;
    goto LABEL_39;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    if ( dword_180029AD4 != 1 || a2[90] != 1 )
      return;
    v11 = a3[1];
    v13 = 3;
    v12 = *v3;
    goto LABEL_39;
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      if ( v8 != 1 )
        return;
      v9 = *a3;
      v10 = a3[1];
      if ( dword_180029AE0 == 1 )
      {
        if ( v9 != 2 )
          return;
        v11 = v10;
        v12 = 2;
        v13 = 6;
        goto LABEL_39;
      }
      if ( v9 == 3 && v10 == 2 )
      {
        v14 = 6;
LABEL_23:
        NcaEtwPerfTrackScenarioPublishStartEvent(v14, a2, a3, v3);
        return;
      }
      return;
    }
    if ( dword_180029ADC != 1 || *a3 != 2 )
      return;
    v11 = a3[1];
    v12 = 2;
    v13 = 5;
LABEL_39:
    NcaEtwPerfTrackScenarioPublishStopEvent(v13, v12, v11, v3);
    return;
  }
  v15 = *a3;
  v16 = a3[1];
  if ( dword_180029AD8 == 1 )
  {
    if ( a2[25] )
      return;
    NcaEtwPerfTrackScenarioPublishStopEvent(4, v15, v16, a3);
    v14 = 5;
    goto LABEL_23;
  }
  if ( v15 == 3 && v16 == 3 )
  {
    v14 = 4;
    goto LABEL_23;
  }
}

```

## disassembly

```asm
0x180018780  sub     rsp, 28h
0x180018784  mov     r9, r8
0x180018787  test    ecx, ecx
0x180018789  jz      loc_1800188CE
0x18001878f  sub     ecx, 1
0x180018792  jz      loc_1800188AE
0x180018798  sub     ecx, 1
0x18001879b  jz      loc_180018892
0x1800187a1  sub     ecx, 1
0x1800187a4  jz      loc_180018872
0x1800187aa  sub     ecx, 1
0x1800187ad  jz      short loc_180018822
0x1800187af  sub     ecx, 1
0x1800187b2  jz      short loc_1800187FA
0x1800187b4  cmp     ecx, 1
0x1800187b7  jnz     loc_1800188F8
0x1800187bd  cmp     cs:dword_180029AE0, 1
0x1800187c4  mov     eax, [r8]
0x1800187c7  mov     ecx, [r8+4]
0x1800187cb  jnz     short loc_1800187E3
0x1800187cd  cmp     eax, 2
0x1800187d0  jnz     loc_1800188F8
0x1800187d6  mov     r8d, ecx
0x1800187d9  mov     edx, eax
0x1800187db  lea     ecx, [rax+4]
0x1800187de  jmp     loc_1800188F3
0x1800187e3  cmp     eax, 3
0x1800187e6  jnz     loc_1800188F8
0x1800187ec  cmp     ecx, 2
0x1800187ef  jnz     loc_1800188F8
0x1800187f5  lea     ecx, [rax+3]
0x1800187f8  jmp     short loc_180018868
0x1800187fa  cmp     cs:dword_180029ADC, 1
0x180018801  jnz     loc_1800188F8
0x180018807  cmp     dword ptr [r8], 2
0x18001880b  jnz     loc_1800188F8
0x180018811  mov     r8d, [r8+4]
0x180018815  mov     edx, 2
0x18001881a  lea     ecx, [rdx+3]
0x18001881d  jmp     loc_1800188F3
0x180018822  cmp     cs:dword_180029AD8, 1
0x180018829  mov     ecx, [r8]
0x18001882c  mov     eax, [r8+4]
0x180018830  jnz     short loc_180018852
0x180018832  cmp     dword ptr [rdx+64h], 0
0x180018836  jnz     loc_1800188F8
0x18001883c  mov     edx, ecx
0x18001883e  mov     r8d, eax
0x180018841  mov     ecx, 4
0x180018846  call    ?NcaEtwPerfTrackScenarioPublishStopEvent@@YAXW4NCA_ETW_PERFTRACK_SCENARIO_TYPE_@@W4NCA_STATUS_EVENT_TYPE_@@W4NCA_STATUS_EVENT_SUBTYPE_@@@Z; NcaEtwPerfTrackScenarioPublishStopEvent(NCA_ETW_PERFTRACK_SCENARIO_TYPE_,NCA_STATUS_EVENT_TYPE_,NCA_STATUS_EVENT_SUBTYPE_)
0x18001884b  mov     ecx, 5
0x180018850  jmp     short loc_180018868
0x180018852  cmp     ecx, 3
0x180018855  jnz     loc_1800188F8
0x18001885b  cmp     eax, ecx
0x18001885d  jnz     loc_1800188F8
0x180018863  mov     ecx, 4
0x180018868  call    ?NcaEtwPerfTrackScenarioPublishStartEvent@@YAXW4NCA_ETW_PERFTRACK_SCENARIO_TYPE_@@@Z; NcaEtwPerfTrackScenarioPublishStartEvent(NCA_ETW_PERFTRACK_SCENARIO_TYPE_)
0x18001886d  jmp     loc_1800188F8
0x180018872  cmp     cs:dword_180029AD4, 1
0x180018879  jnz     short loc_1800188F8
0x18001887b  cmp     dword ptr [rdx+168h], 1
0x180018882  jnz     short loc_1800188F8
0x180018884  mov     r8d, [r8+4]
0x180018888  mov     ecx, 3
0x18001888d  mov     edx, [r9]
0x180018890  jmp     short loc_1800188F3
0x180018892  cmp     cs:dword_180029AD0, 1
0x180018899  jnz     short loc_1800188F8
0x18001889b  cmp     dword ptr [r8], 2
0x18001889f  jnz     short loc_1800188F8
0x1800188a1  mov     r8d, [r8+4]
0x1800188a5  mov     edx, 2
0x1800188aa  mov     ecx, edx
0x1800188ac  jmp     short loc_1800188F3
0x1800188ae  cmp     cs:dword_180029ACC, 1
0x1800188b5  jnz     short loc_1800188F8
0x1800188b7  cmp     dword ptr [rdx+0B4h], 1
0x1800188be  jnz     short loc_1800188F8
0x1800188c0  mov     r8d, [r8+4]
0x1800188c4  mov     ecx, 1
0x1800188c9  mov     edx, [r9]
0x1800188cc  jmp     short loc_1800188F3
0x1800188ce  cmp     cs:?gNcaEtwPerfTrackScenarioState@@3PAHA, 1; int near * gNcaEtwPerfTrackScenarioState
0x1800188d5  jnz     short loc_1800188F8
0x1800188d7  mov     eax, [r8]
0x1800188da  cmp     eax, 3
0x1800188dd  jnz     short loc_1800188E7
0x1800188df  mov     r8d, [r8+4]
0x1800188e3  mov     edx, eax
0x1800188e5  jmp     short loc_1800188F1
0x1800188e7  cmp     eax, 2
0x1800188ea  jnz     short loc_1800188F8
0x1800188ec  xor     r8d, r8d
0x1800188ef  xor     edx, edx
0x1800188f1  xor     ecx, ecx
0x1800188f3  call    ?NcaEtwPerfTrackScenarioPublishStopEvent@@YAXW4NCA_ETW_PERFTRACK_SCENARIO_TYPE_@@W4NCA_STATUS_EVENT_TYPE_@@W4NCA_STATUS_EVENT_SUBTYPE_@@@Z; NcaEtwPerfTrackScenarioPublishStopEvent(NCA_ETW_PERFTRACK_SCENARIO_TYPE_,NCA_STATUS_EVENT_TYPE_,NCA_STATUS_EVENT_SUBTYPE_)
0x1800188f8  add     rsp, 28h
0x1800188fc  retn
```
