# CleanUpIsoArtifactsForCurrentThread(void)

- ea: `0x180018ca4`
- end: `0x180018cc3`
- name: `?CleanUpIsoArtifactsForCurrentThread@@YAXXZ`
- size: `31`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180018710`

## import_xrefs

- `edgeIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x180018cbc`
- `edgeIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x180018cb0`
- `edgeIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x180018cb0`
- `edgeIso!__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z` at `0x180018caa`
- `edgeIso!__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z` at `0x180018caa`

## pseudocode

```c
void CleanUpIsoArtifactsForCurrentThread(void)
{
  unsigned int CurrentThreadHandle; // eax

  IsoUninitializeThread(0);
  CurrentThreadHandle = IsoGetCurrentThreadHandle();
  IsoRemoveArtifact(CurrentThreadHandle);
}

```

## disassembly

```asm
0x180018ca4  sub     rsp, 28h
0x180018ca8  xor     ecx, ecx
0x180018caa  call    cs:__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z; IsoUninitializeThread(IsoScope *)
0x180018cb0  call    cs:__imp_?IsoGetCurrentThreadHandle@@YAKXZ; IsoGetCurrentThreadHandle(void)
0x180018cb6  mov     ecx, eax
0x180018cb8  add     rsp, 28h
0x180018cbc  jmp     cs:__imp_?IsoRemoveArtifact@@YAJK@Z; IsoRemoveArtifact(ulong)
```
