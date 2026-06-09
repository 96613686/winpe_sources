# CreateServer(void)

- ea: `0x140004870`
- end: `0x14000499d`
- name: `?CreateServer@@YAPEAUIUnknown@@XZ`
- size: `301`
- prototype: `struct IUnknown *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1400045f0`

## callees

- `0x140004870`
- `0x14000a010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x14000489b`
- `KERNEL32!LoadLibraryW` at `0x14000489b`
- `KERNEL32!GetProcAddress` at `0x1400048bb`
- `KERNEL32!GetProcAddress` at `0x1400048bb`

## string_xrefs

- `0x140004894`: `Msi.dll`
- `0x1400048b1`: `DllGetClassObject`

## pseudocode

```c
struct IUnknown *CreateServer(void)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  __int64 v2; // rbx
  __int64 v4; // [rsp+40h] [rbp+8h] BYREF
  __int64 v5; // [rsp+48h] [rbp+10h] BYREF

  LibraryW = g_hKernel;
  v4 = 0;
  v5 = 0;
  if ( !g_hKernel )
  {
    LibraryW = LoadLibraryW(L"Msi.dll");
    g_hKernel = LibraryW;
    if ( !LibraryW )
      return 0;
  }
  ProcAddress = GetProcAddress(LibraryW, "DllGetClassObject");
  if ( !ProcAddress )
    return 0;
  if ( ((unsigned int (__fastcall *)(__int64 *, GUID *, __int64 *))ProcAddress)(qword_14000CC28, &IID_IUnknown, &v5) )
    return 0;
  (*(void (__fastcall **)(__int64, _QWORD, __int64 *, __int64 *))(*(_QWORD *)v5 + 24LL))(v5, 0, qword_14000CC28, &v4);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( !v4 )
    return 0;
  v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 232LL))(v4);
  (*(void (__fastcall **)(__int64, HANDLE *, HANDLE *, HANDLE *, struct _RTL_CRITICAL_SECTION *))(*(_QWORD *)v4 + 384LL))(
    v4,
    &g_hShutdownTimer,
    &g_hFatalShutdownEvent,
    &g_hCallbackEvent,
    &g_csServiceHandles);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 400LL))(v4);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  return (struct IUnknown *)v4;
}

```

## disassembly

```asm
0x140004870  push    rbx
0x140004872  sub     rsp, 30h
0x140004876  mov     rax, cs:?g_hKernel@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hKernel
0x14000487d  mov     [rsp+38h+arg_0], 0
0x140004886  mov     [rsp+38h+arg_8], 0
0x14000488f  test    rax, rax
0x140004892  jnz     short loc_1400048B1
0x140004894  lea     rcx, ModuleName; "Msi.dll"
0x14000489b  call    cs:__imp_LoadLibraryW
0x1400048a1  mov     cs:?g_hKernel@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hKernel
0x1400048a8  test    rax, rax
0x1400048ab  jz      loc_140004995
0x1400048b1  lea     rdx, ProcName; "DllGetClassObject"
0x1400048b8  mov     rcx, rax; hModule
0x1400048bb  call    cs:__imp_GetProcAddress
0x1400048c1  test    rax, rax
0x1400048c4  jz      loc_140004995
0x1400048ca  lea     r8, [rsp+38h+arg_8]
0x1400048cf  lea     rdx, IID_IUnknown
0x1400048d6  lea     rcx, qword_14000CC28
0x1400048dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048e2  test    eax, eax
0x1400048e4  jnz     loc_140004995
0x1400048ea  mov     rcx, [rsp+38h+arg_8]
0x1400048ef  lea     r9, [rsp+38h+arg_0]
0x1400048f4  lea     r8, qword_14000CC28
0x1400048fb  xor     edx, edx
0x1400048fd  mov     rax, [rcx]
0x140004900  mov     rax, [rax+18h]
0x140004904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004909  mov     rcx, [rsp+38h+arg_8]
0x14000490e  mov     rax, [rcx]
0x140004911  mov     rax, [rax+10h]
0x140004915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000491a  mov     rcx, [rsp+38h+arg_0]
0x14000491f  test    rcx, rcx
0x140004922  jz      short loc_140004995
0x140004924  mov     rax, [rcx]
0x140004927  mov     rax, [rax+0E8h]
0x14000492e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004933  mov     rcx, [rsp+38h+arg_0]
0x140004938  lea     r9, ?g_hCallbackEvent@@3PEAXEA; void * g_hCallbackEvent
0x14000493f  mov     rbx, rax
0x140004942  lea     r8, ?g_hFatalShutdownEvent@@3PEAXEA; void * g_hFatalShutdownEvent
0x140004949  mov     rdx, [rcx]
0x14000494c  mov     rax, [rdx+180h]
0x140004953  lea     rdx, ?g_csServiceHandles@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csServiceHandles
0x14000495a  mov     [rsp+38h+var_18], rdx
0x14000495f  lea     rdx, ?g_hShutdownTimer@@3PEAXEA; void * g_hShutdownTimer
0x140004966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000496b  mov     rcx, [rsp+38h+arg_0]
0x140004970  mov     rdx, [rcx]
0x140004973  mov     rax, [rdx+190h]
0x14000497a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000497f  mov     rax, [rbx]
0x140004982  mov     rcx, rbx
0x140004985  mov     rax, [rax+10h]
0x140004989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000498e  mov     rax, [rsp+38h+arg_0]
0x140004993  jmp     short loc_140004997
0x140004995  xor     eax, eax
0x140004997  add     rsp, 30h
0x14000499b  pop     rbx
0x14000499c  retn
```
