# NcaDAPEvidenceSnapshotGetUserState

- ea: `0x180016468`
- end: `0x1800164ce`
- name: `NcaDAPEvidenceSnapshotGetUserState`
- size: `102`
- prototype: `void __fastcall(int, unsigned int, _DWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001400`
- `0x1800025c0`
- `0x180007f10`
- `0x180012fe0`

## callees

- `0x180003540`
- `0x180016c08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800164c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016486`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016486`

## pseudocode

```c
void __fastcall NcaDAPEvidenceSnapshotGetUserState(int a1, unsigned int a2, _DWORD *a3)
{
  __int64 v3; // rdi
  _DWORD *v6; // rax

  v3 = a1;
  EnterCriticalSection(&gNcaDapEvSnpshot);
  v6 = (_DWORD *)NcaDAPEvidenceUserSnapshotFind(a2);
  *a3 = v6[5 * v3 + 28];
  NcaDAPEvidenceUserSnapshotRelease(v6);
  LeaveCriticalSection(&gNcaDapEvSnpshot);
}

```

## disassembly

```asm
0x180016468  mov     [rsp+arg_0], rbx
0x18001646d  mov     [rsp+arg_8], rsi
0x180016472  push    rdi
0x180016473  sub     rsp, 20h
0x180016477  movsxd  rdi, ecx
0x18001647a  mov     rsi, r8
0x18001647d  lea     rcx, ?gNcaDapEvSnpshot@@3UNCA_DAP_EVSNPSHT_COMPONENT_@@A; lpCriticalSection
0x180016484  mov     ebx, edx
0x180016486  call    cs:__imp_EnterCriticalSection
0x18001648d  nop     dword ptr [rax+rax+00h]
0x180016492  mov     ecx, ebx
0x180016494  call    NcaDAPEvidenceUserSnapshotFind
0x180016499  lea     r9, [rdi+rdi*4]
0x18001649d  mov     rcx, rax; lpMem
0x1800164a0  mov     edx, [rax+r9*4+70h]
0x1800164a5  mov     [rsi], edx
0x1800164a7  call    NcaDAPEvidenceUserSnapshotRelease
0x1800164ac  lea     rcx, ?gNcaDapEvSnpshot@@3UNCA_DAP_EVSNPSHT_COMPONENT_@@A; NCA_DAP_EVSNPSHT_COMPONENT_ gNcaDapEvSnpshot
0x1800164b3  mov     rbx, [rsp+28h+arg_0]
0x1800164b8  mov     rsi, [rsp+28h+arg_8]
0x1800164bd  add     rsp, 20h
0x1800164c1  pop     rdi
0x1800164c2  jmp     cs:__imp_LeaveCriticalSection
```
