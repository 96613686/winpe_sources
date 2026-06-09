# Performance::RtlCompression::CRtlCompressBuffer::CRtlCompressBuffer(void)

- ea: `0x18001eb5c`
- end: `0x18001eb90`
- name: `??0CRtlCompressBuffer@RtlCompression@Performance@@QEAA@XZ`
- size: `52`
- prototype: `Performance::RtlCompression::CRtlCompressBuffer *__fastcall(Performance::RtlCompression::CRtlCompressBuffer *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e9f0`
- `0x18001ff20`

## callees

- `0x18001eb5c`
- `0x18001edc8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001eb7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001eb7e`

## string_xrefs

- `0x18001eb77`: `RtlCompressBuffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18001eb5c  push    rbx
0x18001eb5e  sub     rsp, 20h
0x18001eb62  mov     rbx, rcx
0x18001eb65  call    ??BCNtDllModuleHandle@RtlCompression@Performance@@QEAAPEAUHINSTANCE__@@XZ; Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *(void)
0x18001eb6a  test    rax, rax
0x18001eb6d  jz      short loc_18001EB84
0x18001eb6f  call    ??BCNtDllModuleHandle@RtlCompression@Performance@@QEAAPEAUHINSTANCE__@@XZ; Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *(void)
0x18001eb74  mov     rcx, rax; hModule
0x18001eb77  lea     rdx, aRtlcompressbuf; "RtlCompressBuffer"
0x18001eb7e  call    cs:__imp_GetProcAddress
0x18001eb84  mov     [rbx], rax
0x18001eb87  mov     rax, rbx
0x18001eb8a  add     rsp, 20h
0x18001eb8e  pop     rbx
0x18001eb8f  retn
```
