# PAL_System_Win32_ThreadProcWrapper(void *)

- ea: `0x18001eef0`
- end: `0x18001ef3c`
- name: `?PAL_System_Win32_ThreadProcWrapper@@YAKPEAX@Z`
- size: `76`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001eef0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18001ef25`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18001ef25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ef0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ef0a`

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
0x18001eef0  mov     [rsp+arg_0], rbx
0x18001eef5  mov     [rsp+arg_8], rsi
0x18001eefa  push    rdi
0x18001eefb  sub     rsp, 20h
0x18001eeff  mov     rbx, [rcx+8]
0x18001ef03  mov     rdi, [rcx]
0x18001ef06  mov     rsi, [rcx+10h]
0x18001ef0a  call    cs:__imp_LocalFree
0x18001ef10  mov     rcx, rbx
0x18001ef13  mov     rax, rdi
0x18001ef16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef1b  test    rsi, rsi
0x18001ef1e  jz      short loc_18001EF2C
0x18001ef20  mov     edx, eax; dwExitCode
0x18001ef22  mov     rcx, rsi; hLibModule
0x18001ef25  call    cs:__imp_FreeLibraryAndExitThread
0x18001ef2b  int     3; Trap to Debugger
0x18001ef2c  mov     rbx, [rsp+28h+arg_0]
0x18001ef31  mov     rsi, [rsp+28h+arg_8]
0x18001ef36  add     rsp, 20h
0x18001ef3a  pop     rdi
0x18001ef3b  retn
```
