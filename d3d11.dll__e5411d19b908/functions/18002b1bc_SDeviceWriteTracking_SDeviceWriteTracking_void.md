# SDeviceWriteTracking::~SDeviceWriteTracking(void)

- ea: `0x18002b1bc`
- end: `0x18002b212`
- name: `??1SDeviceWriteTracking@@QEAA@XZ`
- size: `86`
- prototype: `void __fastcall(SDeviceWriteTracking *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18002b56c`
- `0x18008811c`

## callees

- `0x18002b1bc`
- `0x18004f47c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b20b`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18002b1e3`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18002b1e3`

## pseudocode

```c
void __fastcall SDeviceWriteTracking::~SDeviceWriteTracking(SDeviceWriteTracking *this)
{
  LPVOID *i; // rbx

  for ( i = (LPVOID *)*((_QWORD *)this + 6); i != *((LPVOID **)this + 7); ++i )
    VirtualFree(*i, 0, 0x8000u);
  std::vector<void *>::_Tidy((char *)this + 48);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18002b1bc  mov     [rsp+arg_0], rbx
0x18002b1c1  mov     [rsp+arg_8], rsi
0x18002b1c6  push    rdi
0x18002b1c7  sub     rsp, 20h
0x18002b1cb  mov     rbx, [rcx+30h]
0x18002b1cf  mov     rdi, rcx
0x18002b1d2  cmp     rbx, [rdi+38h]
0x18002b1d6  jz      short loc_18002B1EF
0x18002b1d8  mov     rcx, [rbx]; lpAddress
0x18002b1db  xor     edx, edx; dwSize
0x18002b1dd  mov     r8d, 8000h; dwFreeType
0x18002b1e3  call    cs:__imp_VirtualFree
0x18002b1e9  add     rbx, 8
0x18002b1ed  jmp     short loc_18002B1D2
0x18002b1ef  lea     rcx, [rdi+30h]
0x18002b1f3  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18002b1f8  lea     rcx, [rdi+8]
0x18002b1fc  mov     rbx, [rsp+28h+arg_0]
0x18002b201  mov     rsi, [rsp+28h+arg_8]
0x18002b206  add     rsp, 20h
0x18002b20a  pop     rdi
0x18002b20b  jmp     cs:__imp_DeleteCriticalSection
```
