# Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize::CRtlGetCompressionWorkSpaceSize(void)

- ea: `0x18001eb98`
- end: `0x18001ebcc`
- name: `??0CRtlGetCompressionWorkSpaceSize@RtlCompression@Performance@@QEAA@XZ`
- size: `52`
- prototype: `Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize *__fastcall(Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e9f0`
- `0x18001ff20`

## callees

- `0x18001eb98`
- `0x18001edc8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ebba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ebba`

## string_xrefs

- `0x18001ebb3`: `RtlGetCompressionWorkSpaceSize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize *__fastcall Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize::CRtlGetCompressionWorkSpaceSize(
        Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize *this)
{
  FARPROC ProcAddress; // rax
  HMODULE v3; // rax

  ProcAddress = (FARPROC)Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *();
  if ( ProcAddress )
  {
    v3 = (HMODULE)Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *();
    ProcAddress = GetProcAddress(v3, "RtlGetCompressionWorkSpaceSize");
  }
  *(_QWORD *)this = ProcAddress;
  return this;
}

```

## disassembly

```asm
0x18001eb98  push    rbx
0x18001eb9a  sub     rsp, 20h
0x18001eb9e  mov     rbx, rcx
0x18001eba1  call    ??BCNtDllModuleHandle@RtlCompression@Performance@@QEAAPEAUHINSTANCE__@@XZ; Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *(void)
0x18001eba6  test    rax, rax
0x18001eba9  jz      short loc_18001EBC0
0x18001ebab  call    ??BCNtDllModuleHandle@RtlCompression@Performance@@QEAAPEAUHINSTANCE__@@XZ; Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *(void)
0x18001ebb0  mov     rcx, rax; hModule
0x18001ebb3  lea     rdx, aRtlgetcompress; "RtlGetCompressionWorkSpaceSize"
0x18001ebba  call    cs:__imp_GetProcAddress
0x18001ebc0  mov     [rbx], rax
0x18001ebc3  mov     rax, rbx
0x18001ebc6  add     rsp, 20h
0x18001ebca  pop     rbx
0x18001ebcb  retn
```
