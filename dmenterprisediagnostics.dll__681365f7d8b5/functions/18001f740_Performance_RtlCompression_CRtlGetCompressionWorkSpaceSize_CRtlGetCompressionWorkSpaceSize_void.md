# Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize::CRtlGetCompressionWorkSpaceSize(void)

- ea: `0x18001f740`
- end: `0x18001f77b`
- name: `??0CRtlGetCompressionWorkSpaceSize@RtlCompression@Performance@@QEAA@XZ`
- size: `59`
- prototype: `__int64 __fastcall(Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f58c`
- `0x180020be0`

## callees

- `0x18001f740`
- `0x18001f9a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f762`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f762`

## string_xrefs

- `0x18001f75b`: `RtlGetCompressionWorkSpaceSize`

## pseudocode

```c
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
0x18001f740  push    rbx
0x18001f742  sub     rsp, 20h
0x18001f746  mov     rbx, rcx
0x18001f749  call    ??BCNtDllModuleHandle@RtlCompression@Performance@@QEAAPEAUHINSTANCE__@@XZ; Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *(void)
0x18001f74e  test    rax, rax
0x18001f751  jz      short loc_18001F76E
0x18001f753  call    ??BCNtDllModuleHandle@RtlCompression@Performance@@QEAAPEAUHINSTANCE__@@XZ; Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *(void)
0x18001f758  mov     rcx, rax; hModule
0x18001f75b  lea     rdx, aRtlgetcompress; "RtlGetCompressionWorkSpaceSize"
0x18001f762  call    cs:__imp_GetProcAddress
0x18001f769  nop     dword ptr [rax+rax+00h]
0x18001f76e  mov     [rbx], rax
0x18001f771  mov     rax, rbx
0x18001f774  add     rsp, 20h
0x18001f778  pop     rbx
0x18001f779  retn
```
