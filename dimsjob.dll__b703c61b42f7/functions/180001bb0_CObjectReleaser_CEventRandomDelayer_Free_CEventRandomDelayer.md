# _CObjectReleaser<CEventRandomDelayer>::Free(CEventRandomDelayer *)

- ea: `0x180001bb0`
- end: `0x180001c01`
- name: `?Free@?$_CObjectReleaser@UCEventRandomDelayer@@@@SAXPEAUCEventRandomDelayer@@@Z`
- size: `81`
- prototype: `HLOCAL __fastcall(_QWORD *hMem)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001190`
- `0x180002380`
- `0x180003300`

## callees

- `0x180001bb0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001bf5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001bf5`
- `ntdll!TpReleaseTimer` at `0x180001bec`
- `ntdll!TpReleaseTimer` at `0x180001bec`
- `ntdll!TpSetTimer` at `0x180001bd3`
- `ntdll!TpSetTimer` at `0x180001bd3`
- `ntdll!TpWaitForTimer` at `0x180001be2`
- `ntdll!TpWaitForTimer` at `0x180001be2`

## pseudocode

```c
HLOCAL __fastcall _CObjectReleaser<CEventRandomDelayer>::Free(_QWORD *hMem)
{
  HLOCAL result; // rax

  if ( hMem )
  {
    *hMem = &CEventRandomDelayer::`vftable';
    TpSetTimer(hMem[3], 0, 0, 0);
    TpWaitForTimer(hMem[3], 1);
    TpReleaseTimer(hMem[3]);
    return LocalFree(hMem);
  }
  return result;
}

```

## disassembly

```asm
0x180001bb0  test    rcx, rcx
0x180001bb3  jz      short locret_180001C00
0x180001bb5  push    rbx
0x180001bb6  sub     rsp, 20h
0x180001bba  lea     rax, ??_7CEventRandomDelayer@@6B@; const CEventRandomDelayer::`vftable'
0x180001bc1  mov     rbx, rcx
0x180001bc4  mov     [rcx], rax
0x180001bc7  xor     r9d, r9d
0x180001bca  mov     rcx, [rcx+18h]
0x180001bce  xor     r8d, r8d
0x180001bd1  xor     edx, edx
0x180001bd3  call    cs:__imp_TpSetTimer
0x180001bd9  mov     rcx, [rbx+18h]
0x180001bdd  mov     edx, 1
0x180001be2  call    cs:__imp_TpWaitForTimer
0x180001be8  mov     rcx, [rbx+18h]
0x180001bec  call    cs:__imp_TpReleaseTimer
0x180001bf2  mov     rcx, rbx; hMem
0x180001bf5  call    cs:__imp_LocalFree
0x180001bfb  add     rsp, 20h
0x180001bff  pop     rbx
0x180001c00  retn
```
