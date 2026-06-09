# Performance::RtlCompression::CRtlCompressBuffer::CRtlCompressBuffer(void)

- ea: `0x18001f6fc`
- end: `0x18001f737`
- name: `??0CRtlCompressBuffer@RtlCompression@Performance@@QEAA@XZ`
- size: `59`
- prototype: `__int64 __fastcall(Performance::RtlCompression::CRtlCompressBuffer *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f58c`
- `0x180020be0`

## callees

- `0x18001f6fc`
- `0x18001f9a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f71e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f71e`

## string_xrefs

- `0x18001f717`: `RtlCompressBuffer`

## pseudocode

```c
Performance::RtlCompression::CRtlCompressBuffer *__fastcall Performance::RtlCompression::CRtlCompressBuffer::CRtlCompressBuffer(
        Performance::RtlCompression::CRtlCompressBuffer *this)
{
  FARPROC ProcAddress; // rax
  HMODULE v3; // rax

  ProcAddress = (FARPROC)Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *();
  if ( ProcAddress )
  {
    v3 = (HMODULE)Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *();
    ProcAddress = GetProcAddress(v3, "RtlCompressBuffer");
  }
  *(_QWORD *)this = ProcAddress;
  return this;
}

```

## disassembly

```asm
0x18001f6fc  push    rbx
0x18001f6fe  sub     rsp, 20h
0x18001f702  mov     rbx, rcx
0x18001f705  call    ??BCNtDllModuleHandle@RtlCompression@Performance@@QEAAPEAUHINSTANCE__@@XZ; Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *(void)
0x18001f70a  test    rax, rax
0x18001f70d  jz      short loc_18001F72A
0x18001f70f  call    ??BCNtDllModuleHandle@RtlCompression@Performance@@QEAAPEAUHINSTANCE__@@XZ; Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *(void)
0x18001f714  mov     rcx, rax; hModule
0x18001f717  lea     rdx, aRtlcompressbuf; "RtlCompressBuffer"
0x18001f71e  call    cs:__imp_GetProcAddress
0x18001f725  nop     dword ptr [rax+rax+00h]
0x18001f72a  mov     [rbx], rax
0x18001f72d  mov     rax, rbx
0x18001f730  add     rsp, 20h
0x18001f734  pop     rbx
0x18001f735  retn
```
