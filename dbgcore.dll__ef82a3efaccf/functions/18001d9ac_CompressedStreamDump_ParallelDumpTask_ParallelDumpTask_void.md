# CompressedStreamDump::ParallelDumpTask::~ParallelDumpTask(void)

- ea: `0x18001d9ac`
- end: `0x18001da89`
- name: `??1ParallelDumpTask@CompressedStreamDump@@QEAA@XZ`
- size: `221`
- prototype: `void __fastcall(CompressedStreamDump::ParallelDumpTask *__hidden this)`
- caller_count: `5`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d7e8`
- `0x18001d8f8`
- `0x18001da90`
- `0x18001e114`
- `0x18001f04c`

## callees

- `0x1800021c4`
- `0x18000449c`
- `0x18000f34c`
- `0x18001d888`
- `0x18001d9ac`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18001da0a`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18001da29`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18001da48`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18001da67`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18001da0a`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18001da29`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18001da48`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18001da67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d9ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d9ce`

## pseudocode

```c
void __fastcall CompressedStreamDump::ParallelDumpTask::~ParallelDumpTask(CompressedStreamDump::ParallelDumpTask *this)
{
  void *v2; // rcx
  unsigned int v3; // r8d
  const char *v4; // r9
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 78) )
    _std_terminate();
  v2 = (void *)*((_QWORD *)this + 29);
  if ( v2 && !CloseHandle(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v3, v4);
  std::vector<MemoryRegion>::~vector<MemoryRegion>((char *)this + 200);
  std::vector<MemoryBucket *>::~vector<MemoryBucket *>((char *)this + 72);
  v5 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v5 )
    VirtualFree(v5, 0, 0x8000u);
  v6 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v6 )
    VirtualFree(v6, 0, 0x8000u);
  v7 = (void *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v7 )
    VirtualFree(v7, 0, 0x8000u);
  v8 = (void *)*((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v8 )
    VirtualFree(v8, 0, 0x8000u);
}

```

## disassembly

```asm
0x18001d9ac  push    rbx
0x18001d9ae  sub     rsp, 20h
0x18001d9b2  cmp     dword ptr [rcx+138h], 0
0x18001d9b9  mov     rbx, rcx
0x18001d9bc  jnz     loc_18001DA83
0x18001d9c2  mov     rcx, [rcx+0E8h]; hObject
0x18001d9c9  test    rcx, rcx
0x18001d9cc  jz      short loc_18001D9DC
0x18001d9ce  call    cs:__imp_CloseHandle
0x18001d9d4  test    eax, eax
0x18001d9d6  jz      loc_18001DA73
0x18001d9dc  lea     rcx, [rbx+0C8h]
0x18001d9e3  call    ??1?$vector@UMemoryRegion@@V?$allocator@UMemoryRegion@@@std@@@std@@QEAA@XZ; std::vector<MemoryRegion>::~vector<MemoryRegion>(void)
0x18001d9e8  lea     rcx, [rbx+48h]
0x18001d9ec  call    ??1?$vector@PEAUMemoryBucket@@V?$allocator@PEAUMemoryBucket@@@std@@@std@@QEAA@XZ; std::vector<MemoryBucket *>::~vector<MemoryBucket *>(void)
0x18001d9f1  mov     rcx, [rbx+38h]; lpAddress
0x18001d9f5  mov     qword ptr [rbx+38h], 0
0x18001d9fd  test    rcx, rcx
0x18001da00  jz      short loc_18001DA10
0x18001da02  xor     edx, edx; dwSize
0x18001da04  mov     r8d, 8000h; dwFreeType
0x18001da0a  call    cs:__imp_VirtualFree
0x18001da10  mov     rcx, [rbx+30h]; lpAddress
0x18001da14  mov     qword ptr [rbx+30h], 0
0x18001da1c  test    rcx, rcx
0x18001da1f  jz      short loc_18001DA2F
0x18001da21  xor     edx, edx; dwSize
0x18001da23  mov     r8d, 8000h; dwFreeType
0x18001da29  call    cs:__imp_VirtualFree
0x18001da2f  mov     rcx, [rbx+28h]; lpAddress
0x18001da33  mov     qword ptr [rbx+28h], 0
0x18001da3b  test    rcx, rcx
0x18001da3e  jz      short loc_18001DA4E
0x18001da40  xor     edx, edx; dwSize
0x18001da42  mov     r8d, 8000h; dwFreeType
0x18001da48  call    cs:__imp_VirtualFree
0x18001da4e  mov     rcx, [rbx+20h]; lpAddress
0x18001da52  mov     qword ptr [rbx+20h], 0
0x18001da5a  test    rcx, rcx
0x18001da5d  jz      short loc_18001DA6D
0x18001da5f  xor     edx, edx; dwSize
0x18001da61  mov     r8d, 8000h; dwFreeType
0x18001da67  call    cs:__imp_VirtualFree
0x18001da6d  add     rsp, 20h
0x18001da71  pop     rbx
0x18001da72  retn
0x18001da73  mov     rcx, [rsp+28h]; this
0x18001da78  mov     edx, 0A0Bh; void *
0x18001da7d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001da83  call    __std_terminate
```
