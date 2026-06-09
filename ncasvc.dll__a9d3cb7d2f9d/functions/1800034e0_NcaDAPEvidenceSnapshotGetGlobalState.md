# NcaDAPEvidenceSnapshotGetGlobalState

- ea: `0x1800034e0`
- end: `0x180003533`
- name: `NcaDAPEvidenceSnapshotGetGlobalState`
- size: `83`
- prototype: `void __fastcall(int, _DWORD *)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001400`
- `0x1800025c0`
- `0x180009714`
- `0x180012d78`
- `0x180013b40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003527`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800034ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800034ff`

## pseudocode

```c
void __fastcall NcaDAPEvidenceSnapshotGetGlobalState(int a1, _DWORD *a2)
{
  __int64 v2; // rbx

  v2 = a1;
  EnterCriticalSection(&gNcaDapEvSnpshot);
  *a2 = *((_DWORD *)&gNcaDapEvSnpshot + 5 * v2 + 12);
  LeaveCriticalSection(&gNcaDapEvSnpshot);
}

```

## disassembly

```asm
0x1800034e0  mov     [rsp+arg_0], rbx
0x1800034e5  mov     [rsp+arg_8], rsi
0x1800034ea  push    rdi
0x1800034eb  sub     rsp, 20h
0x1800034ef  movsxd  rbx, ecx
0x1800034f2  lea     rsi, ?gNcaDapEvSnpshot@@3UNCA_DAP_EVSNPSHT_COMPONENT_@@A; NCA_DAP_EVSNPSHT_COMPONENT_ gNcaDapEvSnpshot
0x1800034f9  mov     rcx, rsi; lpCriticalSection
0x1800034fc  mov     rdi, rdx
0x1800034ff  call    cs:__imp_EnterCriticalSection
0x180003506  nop     dword ptr [rax+rax+00h]
0x18000350b  lea     rax, [rbx+rbx*4]
0x18000350f  mov     rcx, rsi
0x180003512  mov     eax, [rsi+rax*4+30h]
0x180003516  mov     [rdi], eax
0x180003518  mov     rbx, [rsp+28h+arg_0]
0x18000351d  mov     rsi, [rsp+28h+arg_8]
0x180003522  add     rsp, 20h
0x180003526  pop     rdi
0x180003527  jmp     cs:__imp_LeaveCriticalSection
```
