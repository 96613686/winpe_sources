# Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *(void)

- ea: `0x18001f9a4`
- end: `0x18001f9e0`
- name: `??BCNtDllModuleHandle@RtlCompression@Performance@@QEAAPEAUHINSTANCE__@@XZ`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f6fc`
- `0x18001f740`

## callees

- `0x18001f9a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f9b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f9b8`

## string_xrefs

- `0x18001f9b1`: `ntdll.dll`

## pseudocode

```c
__int64 Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *()
{
  if ( !Performance::RtlCompression::g_hNtDllModule )
  {
    qword_180035190 = (__int64)GetModuleHandleW(L"ntdll.dll");
    Performance::RtlCompression::g_hNtDllModule = 1;
  }
  return qword_180035190;
}

```

## disassembly

```asm
0x18001f9a4  sub     rsp, 28h
0x18001f9a8  cmp     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 0; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18001f9af  jnz     short loc_18001F9D3
0x18001f9b1  lea     rcx, LibFileName; "ntdll.dll"
0x18001f9b8  call    cs:__imp_GetModuleHandleW
0x18001f9bf  nop     dword ptr [rax+rax+00h]
0x18001f9c4  mov     cs:qword_180035190, rax
0x18001f9cb  nop
0x18001f9cc  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 1; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18001f9d3  mov     rax, cs:qword_180035190
0x18001f9da  add     rsp, 28h
0x18001f9de  retn
```
