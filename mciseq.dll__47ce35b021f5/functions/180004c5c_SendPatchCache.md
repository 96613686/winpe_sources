# SendPatchCache

- ea: `0x180004c5c`
- end: `0x180004cb8`
- name: `SendPatchCache`
- size: `92`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180005270`
- `0x180005a1c`

## callees

- `0x180004c5c`

## import_xrefs

- `WINMM!midiOutCachePatches` at `0x180004c82`
- `WINMM!midiOutCachePatches` at `0x180004c82`
- `WINMM!midiOutCacheDrumPatches` at `0x180004ca2`
- `WINMM!midiOutCacheDrumPatches` at `0x180004ca2`

## pseudocode

```c
__int64 __fastcall SendPatchCache(__int64 a1)
{
  HMIDIOUT v2; // rcx
  __int64 result; // rax
  MMRESULT v4; // ecx

  v2 = *(HMIDIOUT *)(a1 + 168);
  if ( !v2 )
    return 0;
  v4 = midiOutCachePatches(v2, 0, (LPWORD)(a1 + 196), 2u);
  if ( !v4 )
    v4 = midiOutCacheDrumPatches(*(HMIDIOUT *)(a1 + 168), 0, (LPWORD)(a1 + 452), 2u);
  result = 0;
  if ( v4 != 8 )
    return v4;
  return result;
}

```

## disassembly

```asm
0x180004c5c  push    rbx
0x180004c5e  sub     rsp, 20h
0x180004c62  mov     rbx, rcx
0x180004c65  mov     rcx, [rcx+0A8h]; hmo
0x180004c6c  test    rcx, rcx
0x180004c6f  jnz     short loc_180004C75
0x180004c71  xor     eax, eax
0x180004c73  jmp     short loc_180004CB2
0x180004c75  xor     edx, edx; uBank
0x180004c77  lea     r8, [rbx+0C4h]; pwpa
0x180004c7e  lea     r9d, [rdx+2]; fuCache
0x180004c82  call    cs:__imp_midiOutCachePatches
0x180004c88  mov     ecx, eax
0x180004c8a  test    eax, eax
0x180004c8c  jnz     short loc_180004CAA
0x180004c8e  mov     rcx, [rbx+0A8h]; hmo
0x180004c95  lea     r8, [rbx+1C4h]; pwkya
0x180004c9c  xor     edx, edx; uPatch
0x180004c9e  lea     r9d, [rax+2]; fuCache
0x180004ca2  call    cs:__imp_midiOutCacheDrumPatches
0x180004ca8  mov     ecx, eax
0x180004caa  xor     eax, eax
0x180004cac  cmp     ecx, 8
0x180004caf  cmovnz  eax, ecx
0x180004cb2  add     rsp, 20h
0x180004cb6  pop     rbx
0x180004cb7  retn
```
