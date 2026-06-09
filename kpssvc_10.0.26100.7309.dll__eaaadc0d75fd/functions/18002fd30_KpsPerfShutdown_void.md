# KpsPerfShutdown(void)

- ea: `0x18002fd30`
- end: `0x18002fe01`
- name: `?KpsPerfShutdown@@YAXXZ`
- size: `209`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002ccd0`
- `0x18002cf60`

## callees

- `0x18001ae0c`
- `0x18002fd30`
- `0x18003100e`

## import_xrefs

- `ADVAPI32!PerfDeleteInstance` at `0x18002fd82`
- `ADVAPI32!PerfDeleteInstance` at `0x18002fd82`
- `ADVAPI32!PerfStopProvider` at `0x18002fd9a`
- `ADVAPI32!PerfStopProvider` at `0x18002fd9a`
- `ntdll!RtlDeleteCriticalSection` at `0x18002fdb5`
- `ntdll!RtlDeleteCriticalSection` at `0x18002fdb5`

## pseudocode

```c
void KpsPerfShutdown(void)
{
  _QWORD *v0; // rcx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_d7d92ff6f8843d103aaec7ed415865b2_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  if ( KpsPerfData )
  {
    PerfDeleteInstance(KpsSvcPerfProvider, InstanceBlock);
    if ( KpsSvcPerfProvider )
    {
      PerfStopProvider(KpsSvcPerfProvider);
      KpsSvcPerfProvider = 0;
    }
    RtlDeleteCriticalSection(&stru_18003ADA8);
    memset_0(&KpsPerfData, 0, 0x48u);
    v0 = WPP_GLOBAL_Control;
  }
  if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 0x20) != 0 )
    WPP_SF_(v0[2], 23, WPP_d7d92ff6f8843d103aaec7ed415865b2_Traceguids);
}

```

## disassembly

```asm
0x18002fd30  push    rbx
0x18002fd32  sub     rsp, 20h
0x18002fd36  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fd3d  lea     rbx, WPP_GLOBAL_Control
0x18002fd44  cmp     rcx, rbx
0x18002fd47  jz      short loc_18002FD6B
0x18002fd49  test    byte ptr [rcx+1Ch], 20h
0x18002fd4d  jz      short loc_18002FD6B
0x18002fd4f  mov     rcx, [rcx+10h]
0x18002fd53  lea     r8, WPP_d7d92ff6f8843d103aaec7ed415865b2_Traceguids
0x18002fd5a  mov     edx, 16h
0x18002fd5f  call    WPP_SF_
0x18002fd64  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fd6b  cmp     cs:?KpsPerfData@@3U_KPS_PERF_DATA@@A, 0; _KPS_PERF_DATA KpsPerfData
0x18002fd72  jz      short loc_18002FDDA
0x18002fd74  mov     rdx, cs:InstanceBlock; InstanceBlock
0x18002fd7b  mov     rcx, cs:KpsSvcPerfProvider; Provider
0x18002fd82  call    cs:__imp_PerfDeleteInstance
0x18002fd89  nop     dword ptr [rax+rax+00h]
0x18002fd8e  mov     rcx, cs:KpsSvcPerfProvider; ProviderHandle
0x18002fd95  test    rcx, rcx
0x18002fd98  jz      short loc_18002FDAE
0x18002fd9a  call    cs:__imp_PerfStopProvider
0x18002fda1  nop     dword ptr [rax+rax+00h]
0x18002fda6  and     cs:KpsSvcPerfProvider, 0
0x18002fdae  lea     rcx, stru_18003ADA8; CriticalSection
0x18002fdb5  call    cs:__imp_RtlDeleteCriticalSection
0x18002fdbc  nop     dword ptr [rax+rax+00h]
0x18002fdc1  xor     edx, edx; Val
0x18002fdc3  lea     rcx, ?KpsPerfData@@3U_KPS_PERF_DATA@@A; void *
0x18002fdca  lea     r8d, [rdx+48h]; Size
0x18002fdce  call    memset_0
0x18002fdd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fdda  cmp     rcx, rbx
0x18002fddd  jz      short loc_18002FDFA
0x18002fddf  test    byte ptr [rcx+1Ch], 20h
0x18002fde3  jz      short loc_18002FDFA
0x18002fde5  mov     rcx, [rcx+10h]
0x18002fde9  lea     r8, WPP_d7d92ff6f8843d103aaec7ed415865b2_Traceguids
0x18002fdf0  mov     edx, 17h
0x18002fdf5  call    WPP_SF_
0x18002fdfa  add     rsp, 20h
0x18002fdfe  pop     rbx
0x18002fdff  retn
```
