# NcaEvCollProbesShutdown

- ea: `0x180012c20`
- end: `0x180012d6f`
- name: `NcaEvCollProbesShutdown`
- size: `335`
- prototype: `void()`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012950`

## callees

- `0x180003770`
- `0x180004f04`
- `0x180006544`
- `0x180011f10`
- `0x180012c20`
- `0x1800190a0`
- `0x180019368`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012c7b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012c7b`
- `WS2_32!__imp_WSACleanup` at `0x180012d08`
- `WS2_32!__imp_WSACleanup` at `0x180012d08`

## pseudocode

```c
void NcaEvCollProbesShutdown()
{
  PVOID v0; // rcx
  struct NCA_EVCOLL_USER_PROBES_ *v1; // rbx
  __int64 v2; // rax
  struct NCA_EVCOLL_USER_PROBES_ **v3; // rcx
  __int64 v4; // rcx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer((__int64)v0, (const EVENT_DESCRIPTOR *)ModuleShutdownStart, L"EvCollProbes");
  SetEvent(gNcaMain);
  while ( 1 )
  {
    v1 = gNcaEvCollProbes;
    if ( gNcaEvCollProbes == (struct NCA_EVCOLL_USER_PROBES_ *)&gNcaEvCollProbes )
      break;
    v2 = *(_QWORD *)gNcaEvCollProbes;
    if ( *(struct NCA_EVCOLL_USER_PROBES_ **)(*(_QWORD *)gNcaEvCollProbes + 8LL) != gNcaEvCollProbes
      || (v3 = (struct NCA_EVCOLL_USER_PROBES_ **)*((_QWORD *)gNcaEvCollProbes + 1), *v3 != gNcaEvCollProbes) )
    {
      __fastfail(3u);
    }
    *v3 = (struct NCA_EVCOLL_USER_PROBES_ *)v2;
    *(_QWORD *)(v2 + 8) = v3;
    NcaEvCollProbesInnerDelete(v1);
    NcaFree(v1);
  }
  NcaFreeMuiStringTable(6, &wszNcaProbeType);
  NcaFreeMuiStringTable(4, &wszNcaProbeResult);
  NcaFreeMuiStringTable(2, &wszNcaProbeOrigin);
  if ( dword_1800290C0 == 1 )
    WSACleanup();
  NcaCriticalSectionDestroy(&CriticalSection);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v4, (const EVENT_DESCRIPTOR *)ModuleShutdownEnd, L"EvCollProbes");
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids);
}

```

## disassembly

```asm
0x180012c20  mov     [rsp+arg_0], rbx
0x180012c25  push    rdi
0x180012c26  sub     rsp, 20h
0x180012c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c31  lea     rdi, WPP_GLOBAL_Control
0x180012c38  cmp     rcx, rdi
0x180012c3b  jz      short loc_180012C58
0x180012c3d  test    byte ptr [rcx+1Ch], 8
0x180012c41  jz      short loc_180012C58
0x180012c43  mov     rcx, [rcx+10h]
0x180012c47  lea     r8, WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids
0x180012c4e  mov     edx, 0Eh
0x180012c53  call    WPP_SF_
0x180012c58  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180012c5f  jz      short loc_180012C74
0x180012c61  lea     r8, aEvcollprobes; "EvCollProbes"
0x180012c68  lea     rdx, ModuleShutdownStart
0x180012c6f  call    McTemplateU0z_EventWriteTransfer
0x180012c74  mov     rcx, cs:?gNcaMain@@3UNCA_MAIN_COMPONENT_@@A; hEvent
0x180012c7b  call    cs:__imp_SetEvent
0x180012c82  nop     dword ptr [rax+rax+00h]
0x180012c87  mov     rbx, cs:?gNcaEvCollProbes@@3UNCA_EVCOLL_PROBES_COMPONENT_@@A; NCA_EVCOLL_PROBES_COMPONENT_ gNcaEvCollProbes
0x180012c8e  lea     rax, ?gNcaEvCollProbes@@3UNCA_EVCOLL_PROBES_COMPONENT_@@A; NCA_EVCOLL_PROBES_COMPONENT_ gNcaEvCollProbes
0x180012c95  cmp     rbx, rax
0x180012c98  jz      short loc_180012CCC
0x180012c9a  mov     rax, [rbx]
0x180012c9d  cmp     [rax+8], rbx
0x180012ca1  jnz     short loc_180012CC5
0x180012ca3  mov     rcx, [rbx+8]
0x180012ca7  cmp     [rcx], rbx
0x180012caa  jnz     short loc_180012CC5
0x180012cac  mov     [rcx], rax
0x180012caf  mov     [rax+8], rcx
0x180012cb3  mov     rcx, rbx; struct NCA_EVCOLL_USER_PROBES_ *
0x180012cb6  call    ?NcaEvCollProbesInnerDelete@@YAXPEAUNCA_EVCOLL_USER_PROBES_@@@Z; NcaEvCollProbesInnerDelete(NCA_EVCOLL_USER_PROBES_ *)
0x180012cbb  mov     rcx, rbx; lpMem
0x180012cbe  call    NcaFree
0x180012cc3  jmp     short loc_180012C87
0x180012cc5  mov     ecx, 3
0x180012cca  int     29h; Win8: RtlFailFast(ecx)
0x180012ccc  lea     rdx, ?wszNcaProbeType@@3PAPEAGA; ushort * near * wszNcaProbeType
0x180012cd3  mov     ecx, 6
0x180012cd8  call    NcaFreeMuiStringTable
0x180012cdd  lea     rdx, ?wszNcaProbeResult@@3PAPEAGA; ushort * near * wszNcaProbeResult
0x180012ce4  mov     ecx, 4
0x180012ce9  call    NcaFreeMuiStringTable
0x180012cee  lea     rdx, ?wszNcaProbeOrigin@@3PAPEAGA; ushort * near * wszNcaProbeOrigin
0x180012cf5  mov     ecx, 2
0x180012cfa  call    NcaFreeMuiStringTable
0x180012cff  cmp     cs:dword_1800290C0, 1
0x180012d06  jnz     short loc_180012D14
0x180012d08  call    cs:__imp_WSACleanup
0x180012d0f  nop     dword ptr [rax+rax+00h]
0x180012d14  lea     rcx, CriticalSection; lpCriticalSection
0x180012d1b  call    NcaCriticalSectionDestroy
0x180012d20  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180012d27  jz      short loc_180012D3C
0x180012d29  lea     r8, aEvcollprobes; "EvCollProbes"
0x180012d30  lea     rdx, ModuleShutdownEnd
0x180012d37  call    McTemplateU0z_EventWriteTransfer
0x180012d3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d43  cmp     rcx, rdi
0x180012d46  jz      short loc_180012D63
0x180012d48  test    byte ptr [rcx+1Ch], 8
0x180012d4c  jz      short loc_180012D63
0x180012d4e  mov     rcx, [rcx+10h]
0x180012d52  lea     r8, WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids
0x180012d59  mov     edx, 0Fh
0x180012d5e  call    WPP_SF_
0x180012d63  mov     rbx, [rsp+28h+arg_0]
0x180012d68  add     rsp, 20h
0x180012d6c  pop     rdi
0x180012d6d  retn
```
