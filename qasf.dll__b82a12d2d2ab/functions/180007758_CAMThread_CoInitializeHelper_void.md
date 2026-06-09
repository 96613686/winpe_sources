# CAMThread::CoInitializeHelper(void)

- ea: `0x180007758`
- end: `0x1800077a0`
- name: `?CoInitializeHelper@CAMThread@@SAJXZ`
- size: `72`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001c360`

## callees

- `0x180007758`
- `0x18001f010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000776a`
- `KERNEL32!GetModuleHandleW` at `0x18000776a`
- `KERNEL32!GetProcAddress` at `0x18000777f`
- `KERNEL32!GetProcAddress` at `0x18000777f`

## string_xrefs

- `0x18000775e`: `ole32.dll`

## pseudocode

```c
__int64 CAMThread::CoInitializeHelper(void)
{
  unsigned int v0; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v0 = -2147467259;
  ModuleHandleW = GetModuleHandleW(L"ole32.dll");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "CoInitializeEx");
    if ( ProcAddress )
      return ((unsigned int (__fastcall *)(_QWORD, __int64))ProcAddress)(0, 4);
  }
  return v0;
}

```

## disassembly

```asm
0x180007758  push    rbx
0x18000775a  sub     rsp, 20h
0x18000775e  lea     rcx, ModuleName; "ole32.dll"
0x180007765  mov     ebx, 80004005h
0x18000776a  call    cs:__imp_GetModuleHandleW
0x180007770  test    rax, rax
0x180007773  jz      short loc_180007798
0x180007775  lea     rdx, ProcName; "CoInitializeEx"
0x18000777c  mov     rcx, rax; hModule
0x18000777f  call    cs:__imp_GetProcAddress
0x180007785  test    rax, rax
0x180007788  jz      short loc_180007798
0x18000778a  mov     edx, 4
0x18000778f  xor     ecx, ecx
0x180007791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007796  mov     ebx, eax
0x180007798  mov     eax, ebx
0x18000779a  add     rsp, 20h
0x18000779e  pop     rbx
0x18000779f  retn
```
