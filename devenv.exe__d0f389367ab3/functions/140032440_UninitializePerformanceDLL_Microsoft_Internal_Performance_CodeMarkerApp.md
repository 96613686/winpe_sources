# UninitializePerformanceDLL(Microsoft::Internal::Performance::CodeMarkerApp)

- ea: `0x140032440`
- end: `0x1400324f8`
- name: `?UninitializePerformanceDLL@@YAXW4CodeMarkerApp@Performance@Internal@Microsoft@@@Z`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140032420`

## callees

- `0x140032440`

## import_xrefs

- `KERNEL32!FindAtomW` at `0x140032462`
- `KERNEL32!FindAtomW` at `0x14003247d`
- `KERNEL32!FindAtomW` at `0x140032462`
- `KERNEL32!FindAtomW` at `0x14003247d`
- `KERNEL32!DeleteAtom` at `0x140032470`
- `KERNEL32!DeleteAtom` at `0x14003248b`
- `KERNEL32!DeleteAtom` at `0x140032470`
- `KERNEL32!DeleteAtom` at `0x14003248b`
- `KERNEL32!FreeLibrary` at `0x1400324e0`
- `KERNEL32!FreeLibrary` at `0x1400324e0`

## pseudocode

```c
void __fastcall UninitializePerformanceDLL(int a1)
{
  ATOM AtomW; // ax
  ATOM v3; // ax

  if ( ghInstPerf )
  {
    AtomW = FindAtomW(lpString);
    if ( AtomW )
      DeleteAtom(AtomW);
    v3 = FindAtomW(off_14009D6F0);
    if ( v3 )
      DeleteAtom(v3);
    if ( gpfUnInitPerf )
      gpfUnInitPerf(a1);
    gpfInitPerf = 0;
    gpfInitPerf2 = 0;
    gpfUnInitPerf = 0;
    gpfCodeMarker = 0;
    gpSetPerformanceRegRoot = 0;
    gpfBeginLogging = 0;
    gpfWriteLog = 0;
    gfTriedToAttachPerformanceDll = 0;
    FreeLibrary(ghInstPerf);
    ghInstPerf = 0;
  }
}

```

## disassembly

```asm
0x140032440  mov     [rsp+arg_0], rbx
0x140032445  push    rdi
0x140032446  sub     rsp, 20h
0x14003244a  xor     edi, edi
0x14003244c  mov     ebx, ecx
0x14003244e  cmp     cs:?ghInstPerf@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * ghInstPerf
0x140032455  jz      loc_1400324ED
0x14003245b  mov     rcx, cs:lpString; lpString
0x140032462  call    cs:__imp_FindAtomW
0x140032468  test    ax, ax
0x14003246b  jz      short loc_140032476
0x14003246d  movzx   ecx, ax; nAtom
0x140032470  call    cs:__imp_DeleteAtom
0x140032476  mov     rcx, cs:off_14009D6F0; lpString
0x14003247d  call    cs:__imp_FindAtomW
0x140032483  test    ax, ax
0x140032486  jz      short loc_140032491
0x140032488  movzx   ecx, ax; nAtom
0x14003248b  call    cs:__imp_DeleteAtom
0x140032491  mov     rax, cs:?gpfUnInitPerf@@3P6AXH@ZEA; void (*gpfUnInitPerf)(int)
0x140032498  test    rax, rax
0x14003249b  jz      short loc_1400324A1
0x14003249d  mov     ecx, ebx
0x14003249f  call    rax ; void (*gpfUnInitPerf)(int)
0x1400324a1  mov     rcx, cs:?ghInstPerf@@3PEAUHINSTANCE__@@EA; hLibModule
0x1400324a8  mov     cs:?gpfInitPerf@@3P6AXH@ZEA, rdi; void (*gpfInitPerf)(int)
0x1400324af  mov     cs:?gpfInitPerf2@@3P6AXHPEBG@ZEA, rdi; void (*gpfInitPerf2)(int,ushort const *)
0x1400324b6  mov     cs:?gpfUnInitPerf@@3P6AXH@ZEA, rdi; void (*gpfUnInitPerf)(int)
0x1400324bd  mov     cs:?gpfCodeMarker@@3P6AXHPEBXK@ZEA, rdi; void (*gpfCodeMarker)(int,void const *,ulong)
0x1400324c4  mov     cs:?gpSetPerformanceRegRoot@@3P6AXPEBG@ZEA, rdi; void (*gpSetPerformanceRegRoot)(ushort const *)
0x1400324cb  mov     cs:?gpfBeginLogging@@3P6AJH@ZEA, rdi; long (*gpfBeginLogging)(int)
0x1400324d2  mov     cs:?gpfWriteLog@@3P6AJPEAUIStream@@@ZEA, rdi; long (*gpfWriteLog)(IStream *)
0x1400324d9  mov     cs:?gfTriedToAttachPerformanceDll@@3_NA, dil; bool gfTriedToAttachPerformanceDll
0x1400324e0  call    cs:__imp_FreeLibrary
0x1400324e6  mov     cs:?ghInstPerf@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * ghInstPerf
0x1400324ed  mov     rbx, [rsp+28h+arg_0]
0x1400324f2  add     rsp, 20h
0x1400324f6  pop     rdi
0x1400324f7  retn
```
