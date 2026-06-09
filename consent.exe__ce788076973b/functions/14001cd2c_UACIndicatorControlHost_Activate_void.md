# UACIndicatorControlHost::Activate(void)

- ea: `0x14001cd2c`
- end: `0x14001cdb6`
- name: `?Activate@UACIndicatorControlHost@@QEAAXXZ`
- size: `138`
- prototype: `void __fastcall(UACIndicatorControlHost *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140006bb0`

## callees

- `0x14001cd2c`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001cd60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001cd60`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x14001cd4b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x14001cd4b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14001cda3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14001cda3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001cd3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001cd3c`

## string_xrefs

- `0x14001cd42`: `user32.dll`
- `0x14001cd56`: `GetThreadDesktop`

## pseudocode

```c
void __fastcall UACIndicatorControlHost::Activate(UACIndicatorControlHost *this)
{
  DWORD CurrentThreadId; // ebx
  HMODULE ModuleHandleA; // rax
  FARPROC ProcAddress; // rax
  __int64 v4; // rax

  if ( !qword_140029E90 )
  {
    CurrentThreadId = GetCurrentThreadId();
    ModuleHandleA = GetModuleHandleA("user32.dll");
    if ( ModuleHandleA && (ProcAddress = GetProcAddress(ModuleHandleA, "GetThreadDesktop")) != 0 )
      v4 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(CurrentThreadId);
    else
      v4 = 0;
    g_uacIndicatorControlHost = v4;
    qword_140029E90 = (__int64)CreateThread(
                                 0,
                                 0,
                                 _lambda_1681166c52878bc0dc3a671f341fafcc_::_lambda_invoker_cdecl_,
                                 &g_uacIndicatorControlHost,
                                 0,
                                 &ThreadId);
  }
}

```

## disassembly

```asm
0x14001cd2c  push    rbx
0x14001cd2e  sub     rsp, 30h
0x14001cd32  cmp     cs:qword_140029E90, 0
0x14001cd3a  jnz     short loc_14001CDB0
0x14001cd3c  call    cs:__imp_GetCurrentThreadId
0x14001cd42  lea     rcx, aUser32Dll_0; "user32.dll"
0x14001cd49  mov     ebx, eax
0x14001cd4b  call    cs:__imp_GetModuleHandleA
0x14001cd51  test    rax, rax
0x14001cd54  jz      short loc_14001CD74
0x14001cd56  lea     rdx, aGetthreaddeskt; "GetThreadDesktop"
0x14001cd5d  mov     rcx, rax; hModule
0x14001cd60  call    cs:__imp_GetProcAddress
0x14001cd66  test    rax, rax
0x14001cd69  jz      short loc_14001CD74
0x14001cd6b  mov     ecx, ebx
0x14001cd6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cd72  jmp     short loc_14001CD76
0x14001cd74  xor     eax, eax
0x14001cd76  mov     cs:?g_uacIndicatorControlHost@@3VUACIndicatorControlHost@@A, rax; UACIndicatorControlHost g_uacIndicatorControlHost
0x14001cd7d  lea     r9, ?g_uacIndicatorControlHost@@3VUACIndicatorControlHost@@A; lpParameter
0x14001cd84  lea     rax, ThreadId
0x14001cd8b  xor     edx, edx; dwStackSize
0x14001cd8d  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x14001cd92  lea     r8, ?_lambda_invoker_cdecl_@_lambda_1681166c52878bc0dc3a671f341fafcc_@@CAKPEAX@Z; lpStartAddress
0x14001cd99  xor     ecx, ecx; lpThreadAttributes
0x14001cd9b  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x14001cda3  call    cs:__imp_CreateThread
0x14001cda9  mov     cs:qword_140029E90, rax
0x14001cdb0  add     rsp, 30h
0x14001cdb4  pop     rbx
0x14001cdb5  retn
```
