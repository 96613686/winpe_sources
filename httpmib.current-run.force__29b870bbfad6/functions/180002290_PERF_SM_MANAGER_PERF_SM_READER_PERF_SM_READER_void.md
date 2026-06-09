# PERF_SM_MANAGER::PERF_SM_READER::~PERF_SM_READER(void)

- ea: `0x180002290`
- end: `0x18000230c`
- name: `??1PERF_SM_READER@PERF_SM_MANAGER@@UEAA@XZ`
- size: `124`
- prototype: `void __fastcall(PERF_SM_MANAGER::PERF_SM_READER *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002320`

## callees

- `0x180002290`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800022b3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800022e1`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800022b3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800022e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800022ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800022f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800022ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800022f8`

## pseudocode

```c
void __fastcall PERF_SM_MANAGER::PERF_SM_READER::~PERF_SM_READER(PERF_SM_MANAGER::PERF_SM_READER *this)
{
  const void *v2; // rcx
  void *v3; // rcx
  const void *v4; // rcx
  void *v5; // rcx

  *((_DWORD *)this + 2) = 1483894131;
  *(_QWORD *)this = &PERF_SM_MANAGER::PERF_SM_READER::`vftable';
  v2 = (const void *)*((_QWORD *)this + 6);
  if ( v2 )
  {
    UnmapViewOfFile(v2);
    *((_QWORD *)this + 6) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 5);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 5) = 0;
  }
  v4 = (const void *)*((_QWORD *)this + 8);
  if ( v4 )
  {
    UnmapViewOfFile(v4);
    *((_QWORD *)this + 8) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 7);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 7) = 0;
  }
}

```

## disassembly

```asm
0x180002290  push    rbx
0x180002292  sub     rsp, 20h
0x180002296  lea     rax, ??_7PERF_SM_READER@PERF_SM_MANAGER@@6B@; const PERF_SM_MANAGER::PERF_SM_READER::`vftable'
0x18000229d  mov     dword ptr [rcx+8], 58726D73h
0x1800022a4  mov     [rcx], rax
0x1800022a7  mov     rbx, rcx
0x1800022aa  mov     rcx, [rcx+30h]; lpBaseAddress
0x1800022ae  test    rcx, rcx
0x1800022b1  jz      short loc_1800022C1
0x1800022b3  call    cs:__imp_UnmapViewOfFile
0x1800022b9  mov     qword ptr [rbx+30h], 0
0x1800022c1  mov     rcx, [rbx+28h]; hObject
0x1800022c5  test    rcx, rcx
0x1800022c8  jz      short loc_1800022D8
0x1800022ca  call    cs:__imp_CloseHandle
0x1800022d0  mov     qword ptr [rbx+28h], 0
0x1800022d8  mov     rcx, [rbx+40h]; lpBaseAddress
0x1800022dc  test    rcx, rcx
0x1800022df  jz      short loc_1800022EF
0x1800022e1  call    cs:__imp_UnmapViewOfFile
0x1800022e7  mov     qword ptr [rbx+40h], 0
0x1800022ef  mov     rcx, [rbx+38h]; hObject
0x1800022f3  test    rcx, rcx
0x1800022f6  jz      short loc_180002306
0x1800022f8  call    cs:__imp_CloseHandle
0x1800022fe  mov     qword ptr [rbx+38h], 0
0x180002306  add     rsp, 20h
0x18000230a  pop     rbx
0x18000230b  retn
```
