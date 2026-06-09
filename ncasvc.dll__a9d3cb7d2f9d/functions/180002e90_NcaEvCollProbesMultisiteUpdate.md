# NcaEvCollProbesMultisiteUpdate

- ea: `0x180002e90`
- end: `0x180002fc0`
- name: `NcaEvCollProbesMultisiteUpdate`
- size: `304`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180005180`
- `0x180005c20`

## callees

- `0x180002e90`
- `0x180004f34`
- `0x1800050d8`
- `0x180006da0`
- `0x180019100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002f6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002f6c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180002f09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180002f09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ebb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ebb`

## pseudocode

```c
__int64 NcaEvCollProbesMultisiteUpdate()
{
  unsigned int v0; // edi
  struct NCA_EVCOLL_USER_PROBES_ *i; // rbx
  unsigned int j; // esi
  __int64 v3; // rbp
  __int128 v5; // [rsp+20h] [rbp-28h] BYREF
  __int64 v6; // [rsp+30h] [rbp-18h]

  v0 = 0;
  v6 = 0;
  v5 = 0;
  EnterCriticalSection(&CriticalSection);
  for ( i = gNcaEvCollProbes;
        i != (struct NCA_EVCOLL_USER_PROBES_ *)&gNcaEvCollProbes;
        i = *(struct NCA_EVCOLL_USER_PROBES_ **)i )
  {
    for ( j = 0; j < *((_DWORD *)i + 4); ++j )
    {
      v3 = *((_QWORD *)i + 3) + 392LL * j;
      if ( *(_DWORD *)(v3 + 24) == 1 )
      {
        AcquireSRWLockShared(&SRWLock);
        NcaConfigMgrGetProbeObjectCopy(v0, (struct NCA_PROBE_LIST_ *)&xmmword_180028BD8, (struct NCA_PROBE_ *)&v5);
        NcaExcludeShareLockLeave(1, &SRWLock);
        *(_DWORD *)(v3 + 16) = v6;
        NcaProbeEmpty(&v5);
        ++v0;
      }
    }
  }
  LeaveCriticalSection(&CriticalSection);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180002e90  sub     rsp, 48h
0x180002e94  mov     [rsp+48h+arg_0], rbx
0x180002e99  lea     rcx, CriticalSection; lpCriticalSection
0x180002ea0  xorps   xmm0, xmm0
0x180002ea3  mov     [rsp+48h+arg_18], rdi
0x180002ea8  xor     eax, eax
0x180002eaa  mov     [rsp+48h+var_8], r14
0x180002eaf  xor     edi, edi
0x180002eb1  mov     [rsp+48h+var_18], rax
0x180002eb6  movups  [rsp+48h+var_28], xmm0
0x180002ebb  call    cs:__imp_EnterCriticalSection
0x180002ec2  nop     dword ptr [rax+rax+00h]
0x180002ec7  mov     rbx, cs:?gNcaEvCollProbes@@3UNCA_EVCOLL_PROBES_COMPONENT_@@A; NCA_EVCOLL_PROBES_COMPONENT_ gNcaEvCollProbes
0x180002ece  lea     r14, ?gNcaEvCollProbes@@3UNCA_EVCOLL_PROBES_COMPONENT_@@A; NCA_EVCOLL_PROBES_COMPONENT_ gNcaEvCollProbes
0x180002ed5  cmp     rbx, r14
0x180002ed8  jz      loc_180002F65
0x180002ede  mov     [rsp+48h+arg_8], rbp
0x180002ee3  mov     [rsp+48h+arg_10], rsi
0x180002ee8  xor     esi, esi
0x180002eea  cmp     [rbx+10h], esi
0x180002eed  jbe     short loc_180002F53
0x180002eef  mov     eax, esi
0x180002ef1  imul    rbp, rax, 188h
0x180002ef8  add     rbp, [rbx+18h]
0x180002efc  cmp     dword ptr [rbp+18h], 1
0x180002f00  jnz     short loc_180002F4C
0x180002f02  lea     rcx, SRWLock; SRWLock
0x180002f09  call    cs:__imp_AcquireSRWLockShared
0x180002f10  nop     dword ptr [rax+rax+00h]
0x180002f15  lea     r8, [rsp+48h+var_28]; struct NCA_PROBE_ *
0x180002f1a  mov     ecx, edi; unsigned int
0x180002f1c  lea     rdx, xmmword_180028BD8; struct NCA_PROBE_LIST_ *
0x180002f23  call    ?NcaConfigMgrGetProbeObjectCopy@@YAKKPEAUNCA_PROBE_LIST_@@PEAUNCA_PROBE_@@@Z; NcaConfigMgrGetProbeObjectCopy(ulong,NCA_PROBE_LIST_ *,NCA_PROBE_ *)
0x180002f28  lea     rdx, SRWLock
0x180002f2f  mov     ecx, 1
0x180002f34  call    NcaExcludeShareLockLeave
0x180002f39  mov     eax, dword ptr [rsp+48h+var_18]
0x180002f3d  lea     rcx, [rsp+48h+var_28]
0x180002f42  mov     [rbp+10h], eax
0x180002f45  call    NcaProbeEmpty
0x180002f4a  inc     edi
0x180002f4c  inc     esi
0x180002f4e  cmp     esi, [rbx+10h]
0x180002f51  jb      short loc_180002EEF
0x180002f53  mov     rbx, [rbx]
0x180002f56  cmp     rbx, r14
0x180002f59  jnz     short loc_180002EE8
0x180002f5b  mov     rsi, [rsp+48h+arg_10]
0x180002f60  mov     rbp, [rsp+48h+arg_8]
0x180002f65  lea     rcx, CriticalSection; lpCriticalSection
0x180002f6c  call    cs:__imp_LeaveCriticalSection
0x180002f73  nop     dword ptr [rax+rax+00h]
0x180002f78  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f7f  lea     rax, WPP_GLOBAL_Control
0x180002f86  mov     r14, [rsp+48h+var_8]
0x180002f8b  mov     rdi, [rsp+48h+arg_18]
0x180002f90  mov     rbx, [rsp+48h+arg_0]
0x180002f95  cmp     rcx, rax
0x180002f98  jz      short loc_180002FB8
0x180002f9a  test    byte ptr [rcx+1Ch], 8
0x180002f9e  jz      short loc_180002FB8
0x180002fa0  mov     rcx, [rcx+10h]
0x180002fa4  lea     r8, WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids
0x180002fab  mov     edx, 34h ; '4'
0x180002fb0  xor     r9d, r9d
0x180002fb3  call    WPP_SF_d
0x180002fb8  xor     eax, eax
0x180002fba  add     rsp, 48h
0x180002fbe  retn
```
