# FreeRetrievalPreFetchJobInfo(_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO *)

- ea: `0x18000f924`
- end: `0x18000f945`
- name: `?FreeRetrievalPreFetchJobInfo@@YAXPEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@@Z`
- size: `33`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *hMem)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d134`
- `0x18000f950`

## callees

- `0x1800068b0`
- `0x18000f924`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f931`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f931`

## pseudocode

```c
void __fastcall FreeRetrievalPreFetchJobInfo(struct _RTL_CRITICAL_SECTION *hMem)
{
  if ( hMem )
  {
    DeleteCriticalSection(hMem);
    PkiFree(hMem);
  }
}

```

## disassembly

```asm
0x18000f924  test    rcx, rcx
0x18000f927  jz      short locret_18000F944
0x18000f929  push    rbx
0x18000f92a  sub     rsp, 20h
0x18000f92e  mov     rbx, rcx
0x18000f931  call    cs:__imp_DeleteCriticalSection
0x18000f937  mov     rcx, rbx; hMem
0x18000f93a  call    PkiFree
0x18000f93f  add     rsp, 20h
0x18000f943  pop     rbx
0x18000f944  retn
```
