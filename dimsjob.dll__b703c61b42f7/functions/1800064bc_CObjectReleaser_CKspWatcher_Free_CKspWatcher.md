# _CObjectReleaser<CKspWatcher>::Free(CKspWatcher *)

- ea: `0x1800064bc`
- end: `0x1800064dd`
- name: `?Free@?$_CObjectReleaser@VCKspWatcher@@@@SAXPEAVCKspWatcher@@@Z`
- size: `33`
- prototype: `HLOCAL __fastcall(CKspWatcher *hMem)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002380`
- `0x180002530`
- `0x180003320`

## callees

- `0x1800064bc`
- `0x18000aa04`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800064d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800064d1`

## pseudocode

```c
HLOCAL __fastcall _CObjectReleaser<CKspWatcher>::Free(CKspWatcher *hMem)
{
  HLOCAL result; // rax

  if ( hMem )
  {
    CKspWatcher::~CKspWatcher(hMem);
    return LocalFree(hMem);
  }
  return result;
}

```

## disassembly

```asm
0x1800064bc  test    rcx, rcx
0x1800064bf  jz      short locret_1800064DC
0x1800064c1  push    rbx
0x1800064c2  sub     rsp, 20h
0x1800064c6  mov     rbx, rcx
0x1800064c9  call    ??1CKspWatcher@@QEAA@XZ; CKspWatcher::~CKspWatcher(void)
0x1800064ce  mov     rcx, rbx; hMem
0x1800064d1  call    cs:__imp_LocalFree
0x1800064d7  add     rsp, 20h
0x1800064db  pop     rbx
0x1800064dc  retn
```
