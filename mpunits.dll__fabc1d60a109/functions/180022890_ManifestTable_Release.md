# ManifestTable_Release

- ea: `0x180022890`
- end: `0x1800228bc`
- name: `ManifestTable_Release`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `msvcrt!free` at `0x1800228a7`
- `msvcrt!free` at `0x1800228a7`
- `msvcrt!free` at `0x1800228b5`
- `tdh!TdhUnloadManifest` at `0x18002289d`
- `tdh!TdhUnloadManifest` at `0x18002289d`

## pseudocode

```c
void __fastcall ManifestTable_Release(PWSTR *a1)
{
  TdhUnloadManifest(a1[3]);
  free(a1[3]);
  free(a1);
}

```

## disassembly

```asm
0x180022890  push    rbx
0x180022892  sub     rsp, 20h
0x180022896  mov     rbx, rcx
0x180022899  mov     rcx, [rcx+18h]; Manifest
0x18002289d  call    cs:__imp_TdhUnloadManifest
0x1800228a3  mov     rcx, [rbx+18h]; Block
0x1800228a7  call    cs:__imp_free
0x1800228ad  mov     rcx, rbx
0x1800228b0  add     rsp, 20h
0x1800228b4  pop     rbx
0x1800228b5  jmp     cs:__imp_free
```
