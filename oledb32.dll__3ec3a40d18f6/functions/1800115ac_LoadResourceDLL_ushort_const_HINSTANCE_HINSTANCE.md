# LoadResourceDLL(ushort const *,HINSTANCE__ *,HINSTANCE__ * *)

- ea: `0x1800115ac`
- end: `0x1800116d4`
- name: `?LoadResourceDLL@@YAJPEBGPEAUHINSTANCE__@@PEAPEAU1@@Z`
- size: `296`
- prototype: `int(const unsigned __int16 *, HINSTANCE, HINSTANCE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180011370`

## callees

- `0x1800115ac`
- `0x1800116dc`
- `0x180011bcc`
- `0x180013870`
- `0x180029414`
- `0x180029560`
- `0x180029c30`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x1800115e2`
- `MSDART!MpHeapAlloc` at `0x1800115e2`

## string_xrefs

- `0x180011601`: `OLEDB32R.DLL`
- `0x18001160d`: `Failed to load resource DLL %s`
- `0x18001162b`: `<LoadResourceDLL|OLEDB|ERR> `
- `0x180011679`: `<LoadResourceDLL|Trace|HR> `
- `0x1800116b1`: `<LoadResourceDLL|Trace|HR> `

## pseudocode

```c

```

## disassembly

```asm
0x1800115ac  mov     [rsp+arg_0], rbx
0x1800115b1  push    rdi
0x1800115b2  sub     rsp, 20h
0x1800115b6  mov     rcx, rdx; HINSTANCE
0x1800115b9  xor     edi, edi
0x1800115bb  call    ?LoadResourceLibrary@@YAPEAUHINSTANCE__@@PEAU1@PEBG@Z; LoadResourceLibrary(HINSTANCE__ *,ushort const *)
0x1800115c0  mov     cs:hLibModule, rax
0x1800115c7  test    rax, rax
0x1800115ca  jnz     loc_1800116A1
0x1800115d0  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800115d7  mov     edx, 1300000h
0x1800115dc  mov     r8d, 0A8h
0x1800115e2  call    cs:__imp_MpHeapAlloc
0x1800115e8  mov     rbx, rax
0x1800115eb  test    rax, rax
0x1800115ee  jnz     short loc_180011601
0x1800115f0  xor     ecx, ecx; void *
0x1800115f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800115f7  mov     eax, 8007000Eh
0x1800115fc  jmp     loc_1800116C9
0x180011601  lea     r9, aOledb32rDll; "OLEDB32R.DLL"
0x180011608  mov     edx, 2Ah ; '*'; unsigned __int64
0x18001160d  lea     r8, aFailedToLoadRe; "Failed to load resource DLL %s"
0x180011614  mov     rcx, rbx; unsigned __int16 *
0x180011617  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001161c  test    byte ptr cs:_bidGblFlags, 2
0x180011623  jz      short loc_180011694
0x180011625  mov     r8d, 267h; unsigned int
0x18001162b  lea     rdx, aLoadresourcedl; "<LoadResourceDLL|OLEDB|ERR> "
0x180011632  mov     ecx, eax; int
0x180011634  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180011639  test    byte ptr cs:_bidGblFlags, 2
0x180011640  jz      short loc_180011694
0x180011642  mov     rax, cs:off_1800C93F0; "<LoadResourceDLL|ERR> %s\n"
0x180011649  test    rax, rax
0x18001164c  jz      short loc_180011669
0x18001164e  mov     r8, cs:off_1800C93F0; "<LoadResourceDLL|ERR> %s\n"
0x180011655  mov     r9, rbx
0x180011658  mov     rcx, cs:off_1800C8530; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001165f  mov     edx, 9A800h
0x180011664  call    _bidTraceW
0x180011669  test    byte ptr cs:_bidGblFlags, 2
0x180011670  jz      short loc_180011694
0x180011672  mov     rcx, cs:off_1800C8530; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180011679  lea     r8, aLoadresourcedl_1; "<LoadResourceDLL|Trace|HR> "
0x180011680  mov     r9d, 80004005h
0x180011686  mov     edx, 9B009h
0x18001168b  call    _bidTraceHR
0x180011690  mov     edi, eax
0x180011692  jmp     short loc_180011699
0x180011694  mov     edi, 80004005h
0x180011699  mov     rcx, rbx; void *
0x18001169c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800116a1  test    byte ptr cs:_bidGblFlags, 2
0x1800116a8  jz      short loc_1800116C7
0x1800116aa  mov     rcx, cs:off_1800C8530; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800116b1  lea     r8, aLoadresourcedl_1; "<LoadResourceDLL|Trace|HR> "
0x1800116b8  mov     r9d, edi
0x1800116bb  mov     edx, 9BC09h
0x1800116c0  call    _bidTraceHR
0x1800116c5  mov     edi, eax
0x1800116c7  mov     eax, edi
0x1800116c9  mov     rbx, [rsp+28h+arg_0]
0x1800116ce  add     rsp, 20h
0x1800116d2  pop     rdi
0x1800116d3  retn
```
