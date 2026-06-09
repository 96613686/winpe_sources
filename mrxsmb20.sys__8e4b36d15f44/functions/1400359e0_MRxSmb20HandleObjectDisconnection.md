# MRxSmb20HandleObjectDisconnection

- ea: `0x1400359e0`
- end: `0x140035a0f`
- name: `MRxSmb20HandleObjectDisconnection`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `mrxsmb!MRxSmbActivateRecurrentService` at `0x1400359fd`
- `mrxsmb!MRxSmbActivateRecurrentService` at `0x1400359fd`

## pseudocode

```c
__int64 __fastcall MRxSmb20HandleObjectDisconnection(__int64 a1)
{
  __int64 v1; // rcx
  __int64 v2; // rdx

  v1 = *(_QWORD *)(a1 + 24);
  v2 = *(_QWORD *)(v1 + 2336);
  _InterlockedIncrement((volatile signed __int32 *)(v2 + 128));
  return MRxSmbActivateRecurrentService(v1, v2 + 136);
}

```

## disassembly

```asm
0x1400359e0  sub     rsp, 28h
0x1400359e4  mov     rcx, [rcx+18h]
0x1400359e8  mov     rdx, [rcx+920h]
0x1400359ef  lock inc dword ptr [rdx+80h]
0x1400359f6  add     rdx, 88h
0x1400359fd  call    cs:__imp_MRxSmbActivateRecurrentService
0x140035a04  nop     dword ptr [rax+rax+00h]
0x140035a09  add     rsp, 28h
0x140035a0d  retn
```
