# PAL_System_Win32_ThreadProcWrapper(void *)

- ea: `0x1400183b0`
- end: `0x1400183fc`
- name: `?PAL_System_Win32_ThreadProcWrapper@@YAKPEAX@Z`
- size: `76`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400183b0`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1400183e5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1400183e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400183ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400183ca`

## pseudocode

```c
__int64 __fastcall PAL_System_Win32_ThreadProcWrapper(__int64 (__fastcall **Parameter)(__int64))
{
  __int64 (__fastcall *v1)(__int64); // rbx
  __int64 (__fastcall *v2)(__int64); // rdi
  HMODULE v3; // rsi
  __int64 result; // rax

  v1 = Parameter[1];
  v2 = *Parameter;
  v3 = (HMODULE)Parameter[2];
  LocalFree(Parameter);
  result = v2((__int64)v1);
  if ( v3 )
    FreeLibraryAndExitThread(v3, result);
  return result;
}

```

## disassembly

```asm
0x1400183b0  mov     [rsp+arg_0], rbx
0x1400183b5  mov     [rsp+arg_8], rsi
0x1400183ba  push    rdi
0x1400183bb  sub     rsp, 20h
0x1400183bf  mov     rbx, [rcx+8]
0x1400183c3  mov     rdi, [rcx]
0x1400183c6  mov     rsi, [rcx+10h]
0x1400183ca  call    cs:__imp_LocalFree
0x1400183d0  mov     rcx, rbx
0x1400183d3  mov     rax, rdi
0x1400183d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400183db  test    rsi, rsi
0x1400183de  jz      short loc_1400183EC
0x1400183e0  mov     edx, eax; dwExitCode
0x1400183e2  mov     rcx, rsi; hLibModule
0x1400183e5  call    cs:__imp_FreeLibraryAndExitThread
0x1400183eb  int     3; Trap to Debugger
0x1400183ec  mov     rbx, [rsp+28h+arg_0]
0x1400183f1  mov     rsi, [rsp+28h+arg_8]
0x1400183f6  add     rsp, 20h
0x1400183fa  pop     rdi
0x1400183fb  retn
```
