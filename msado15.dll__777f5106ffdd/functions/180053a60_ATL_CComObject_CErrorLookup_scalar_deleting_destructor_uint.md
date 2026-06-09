# ATL::CComObject<CErrorLookup>::`scalar deleting destructor'(uint)

- ea: `0x180053a60`
- end: `0x180053ab1`
- name: `??_G?$CComObject@VCErrorLookup@@@ATL@@QEAAPEAXI@Z`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180050f40`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x180053a85`
- `MSDART!MPDeleteCriticalSection` at `0x180053a85`
- `MSDART!MpHeapFree` at `0x180053a9b`
- `MSDART!MpHeapFree` at `0x180053a9b`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CErrorLookup>::`scalar deleting destructor'(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComObject<CErrorLookup>::`vftable';
  _InterlockedDecrement(&dword_180122C88);
  MPDeleteCriticalSection(a1 + 16);
  MpHeapFree(g_hHeapHandle, a1);
  return a1;
}

```

## disassembly

```asm
0x180053a60  push    rbx
0x180053a62  sub     rsp, 20h
0x180053a66  mov     dword ptr [rcx+8], 1
0x180053a6d  lea     rax, ??_7?$CComObject@VCErrorLookup@@@ATL@@6B@; const ATL::CComObject<CErrorLookup>::`vftable'
0x180053a74  mov     [rcx], rax
0x180053a77  mov     rbx, rcx
0x180053a7a  lock dec cs:dword_180122C88
0x180053a81  add     rcx, 10h
0x180053a85  call    cs:__imp_MPDeleteCriticalSection
0x180053a8c  nop     dword ptr [rax+rax+00h]
0x180053a91  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180053a98  mov     rdx, rbx
0x180053a9b  call    cs:__imp_MpHeapFree
0x180053aa2  nop     dword ptr [rax+rax+00h]
0x180053aa7  mov     rax, rbx
0x180053aaa  add     rsp, 20h
0x180053aae  pop     rbx
0x180053aaf  retn
```
