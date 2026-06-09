# Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *(void)

- ea: `0x18001edc8`
- end: `0x18001edfd`
- name: `??BCNtDllModuleHandle@RtlCompression@Performance@@QEAAPEAUHINSTANCE__@@XZ`
- size: `53`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001eb5c`
- `0x18001eb98`

## callees

- `0x18001edc8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001eddc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001eddc`

## string_xrefs

- `0x18001edd5`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *()
{
  if ( !Performance::RtlCompression::g_hNtDllModule )
  {
    qword_180034190 = (__int64)GetModuleHandleW(L"ntdll.dll");
    Performance::RtlCompression::g_hNtDllModule = 1;
  }
  return qword_180034190;
}

```

## disassembly

```asm
0x18001edc8  sub     rsp, 28h
0x18001edcc  cmp     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 0; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18001edd3  jnz     short loc_18001EDF1
0x18001edd5  lea     rcx, LibFileName; "ntdll.dll"
0x18001eddc  call    cs:__imp_GetModuleHandleW
0x18001ede2  mov     cs:qword_180034190, rax
0x18001ede9  nop
0x18001edea  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 1; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18001edf1  mov     rax, cs:qword_180034190
0x18001edf8  add     rsp, 28h
0x18001edfc  retn
```
