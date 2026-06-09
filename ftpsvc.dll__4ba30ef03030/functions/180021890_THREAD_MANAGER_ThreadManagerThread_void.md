# THREAD_MANAGER::ThreadManagerThread(void *)

- ea: `0x180021890`
- end: `0x180021912`
- name: `?ThreadManagerThread@THREAD_MANAGER@@CAKPEAX@Z`
- size: `130`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180020458`
- `0x180020800`
- `0x1800213d8`
- `0x180021890`
- `0x180049010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800218bc`
- `KERNEL32!GetLastError` at `0x1800218bc`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18002190b`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18002190b`
- `KERNEL32!LoadLibraryExW` at `0x1800218ae`
- `KERNEL32!LoadLibraryExW` at `0x1800218ae`
- `ole32!CoUninitialize` at `0x180021900`
- `ole32!CoUninitialize` at `0x180021900`
- `ole32!CoInitializeEx` at `0x1800218c8`
- `ole32!CoInitializeEx` at `0x1800218c8`

## pseudocode

```c
void __fastcall __noreturn THREAD_MANAGER::ThreadManagerThread(THREAD_MANAGER **Parameter)
{
  HMODULE Library; // rsi
  DWORD LastError; // eax
  struct THREAD_MANAGER::THREAD_PARAM *v4; // rdx
  DWORD v5; // edi

  Library = LoadLibraryExW(&g_szModuleName, 0, 0);
  if ( Library )
  {
    CoInitializeEx(0, 0);
    if ( *((_DWORD *)Parameter + 9) )
      THREAD_MANAGER::CreatedSuccessfully(Parameter[3], v4);
    LastError = ((__int64 (__fastcall *)(THREAD_MANAGER *))Parameter[1])(Parameter[2]);
  }
  else
  {
    LastError = GetLastError();
  }
  v5 = LastError;
  THREAD_MANAGER::RemoveThread(Parameter[3], (struct THREAD_MANAGER::THREAD_PARAM *)Parameter);
  THREAD_MANAGER::THREAD_PARAM::`scalar deleting destructor'((THREAD_MANAGER::THREAD_PARAM *)Parameter);
  CoUninitialize();
  FreeLibraryAndExitThread(Library, v5);
}

```

## disassembly

```asm
0x180021890  mov     [rsp+arg_0], rbx
0x180021895  mov     [rsp+arg_8], rsi
0x18002189a  push    rdi
0x18002189b  sub     rsp, 20h
0x18002189f  mov     rbx, rcx
0x1800218a2  xor     r8d, r8d; dwFlags
0x1800218a5  lea     rcx, ?g_szModuleName@@3PAGA; lpLibFileName
0x1800218ac  xor     edx, edx; hFile
0x1800218ae  call    cs:__imp_LoadLibraryExW
0x1800218b4  mov     rsi, rax
0x1800218b7  test    rax, rax
0x1800218ba  jnz     short loc_1800218C4
0x1800218bc  call    cs:__imp_GetLastError
0x1800218c2  jmp     short loc_1800218EA
0x1800218c4  xor     edx, edx; dwCoInit
0x1800218c6  xor     ecx, ecx; pvReserved
0x1800218c8  call    cs:__imp_CoInitializeEx
0x1800218ce  cmp     dword ptr [rbx+24h], 0
0x1800218d2  jz      short loc_1800218DD
0x1800218d4  mov     rcx, [rbx+18h]; this
0x1800218d8  call    ?CreatedSuccessfully@THREAD_MANAGER@@AEAAXPEAUTHREAD_PARAM@1@@Z; THREAD_MANAGER::CreatedSuccessfully(THREAD_MANAGER::THREAD_PARAM *)
0x1800218dd  mov     rcx, [rbx+10h]
0x1800218e1  mov     rax, [rbx+8]
0x1800218e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218ea  mov     edi, eax
0x1800218ec  mov     rcx, [rbx+18h]; this
0x1800218f0  mov     rdx, rbx; struct THREAD_MANAGER::THREAD_PARAM *
0x1800218f3  call    ?RemoveThread@THREAD_MANAGER@@AEAAXPEAUTHREAD_PARAM@1@@Z; THREAD_MANAGER::RemoveThread(THREAD_MANAGER::THREAD_PARAM *)
0x1800218f8  mov     rcx, rbx; this
0x1800218fb  call    ??_GTHREAD_PARAM@THREAD_MANAGER@@QEAAPEAXI@Z; THREAD_MANAGER::THREAD_PARAM::`scalar deleting destructor'(uint)
0x180021900  call    cs:__imp_CoUninitialize
0x180021906  mov     edx, edi; dwExitCode
0x180021908  mov     rcx, rsi; hLibModule
0x18002190b  call    cs:__imp_FreeLibraryAndExitThread
```
