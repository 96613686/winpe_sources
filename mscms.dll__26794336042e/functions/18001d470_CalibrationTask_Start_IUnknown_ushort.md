# CalibrationTask::Start(IUnknown *,ushort *)

- ea: `0x18001d470`
- end: `0x18001d5c2`
- name: `?Start@CalibrationTask@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `338`
- prototype: `__int64 __fastcall(CalibrationTask *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x18001d470`
- `0x18002e614`
- `0x18002ea90`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001d57d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001d57d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001d4e3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001d4e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d485`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d485`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d5af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d5af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d4f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d55c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d4f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d55c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001d54d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001d54d`

## string_xrefs

- `0x18001d4d1`: `mscms.dll`

## pseudocode

```c
__int64 __fastcall CalibrationTask::Start(
        struct _RTL_CRITICAL_SECTION *this,
        struct IUnknown *a2,
        unsigned __int16 *a3)
{
  signed int v5; // ebx
  HMODULE *v6; // rax
  HMODULE *v7; // rsi
  HMODULE Library; // rax
  signed int LastError; // eax
  _QWORD *v10; // rdi
  HANDLE Thread; // rax
  signed int v12; // eax

  EnterCriticalSection(this + 2);
  if ( !a2 )
  {
    v5 = -2147024809;
    goto LABEL_21;
  }
  if ( LODWORD(this[1].SpinCount) )
  {
    v5 = -2147467259;
    goto LABEL_21;
  }
  LODWORD(this[1].SpinCount) = 1;
  v6 = (HMODULE *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( !v6 )
  {
    v5 = -2147024882;
    goto LABEL_21;
  }
  *(_OWORD *)v6 = 0;
  Library = LoadLibraryExW(gszMSCMS, 0, 0x800u);
  *v7 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v10 = v7 + 1;
    goto LABEL_14;
  }
  v10 = v7 + 1;
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, HMODULE *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_ITaskHandlerStatus,
         v7 + 1);
  if ( v5 >= 0 )
  {
    Thread = CreateThread(0, 0, CalibrationTask::ThreadProc, v7, 0, 0);
    this[1].LockSemaphore = Thread;
    if ( !Thread )
    {
      v12 = GetLastError();
      v5 = v12;
      if ( v12 > 0 )
        v5 = (unsigned __int16)v12 | 0x80070000;
    }
LABEL_14:
    if ( v5 >= 0 )
      goto LABEL_21;
  }
  if ( *v7 )
    FreeLibrary(*v7);
  if ( *v10 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 16LL))(*v10);
  operator delete(v7);
LABEL_21:
  LeaveCriticalSection(this + 2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001d470  push    rbx
0x18001d472  push    rbp
0x18001d473  push    rsi
0x18001d474  push    rdi
0x18001d475  push    r14
0x18001d477  sub     rsp, 30h
0x18001d47b  mov     rbp, rcx
0x18001d47e  mov     rbx, rdx
0x18001d481  add     rcx, 50h ; 'P'; lpCriticalSection
0x18001d485  call    cs:__imp_EnterCriticalSection
0x18001d48b  test    rbx, rbx
0x18001d48e  jnz     short loc_18001D49A
0x18001d490  mov     ebx, 80070057h
0x18001d495  jmp     loc_18001D5AB
0x18001d49a  cmp     dword ptr [rbp+48h], 0
0x18001d49e  jz      short loc_18001D4AA
0x18001d4a0  mov     ebx, 80004005h
0x18001d4a5  jmp     loc_18001D5AB
0x18001d4aa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d4b1  mov     dword ptr [rbp+48h], 1
0x18001d4b8  mov     ecx, 10h; unsigned __int64
0x18001d4bd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001d4c2  mov     rsi, rax
0x18001d4c5  test    rax, rax
0x18001d4c8  jz      loc_18001D5A6
0x18001d4ce  xorps   xmm1, xmm1
0x18001d4d1  lea     rcx, gszMSCMS; "mscms.dll"
0x18001d4d8  xor     edx, edx; hFile
0x18001d4da  mov     r8d, 800h; dwFlags
0x18001d4e0  movups  xmmword ptr [rax], xmm1
0x18001d4e3  call    cs:__imp_LoadLibraryExW
0x18001d4e9  mov     [rsi], rax
0x18001d4ec  test    rax, rax
0x18001d4ef  jnz     short loc_18001D50C
0x18001d4f1  call    cs:__imp_GetLastError
0x18001d4f7  mov     ebx, eax
0x18001d4f9  test    eax, eax
0x18001d4fb  jle     short loc_18001D506
0x18001d4fd  movzx   ebx, ax
0x18001d500  or      ebx, 80070000h
0x18001d506  lea     rdi, [rsi+8]
0x18001d50a  jmp     short loc_18001D571
0x18001d50c  mov     rax, [rbx]
0x18001d50f  lea     rdi, [rsi+8]
0x18001d513  mov     r8, rdi
0x18001d516  lea     rdx, IID_ITaskHandlerStatus
0x18001d51d  mov     rcx, rbx
0x18001d520  mov     rax, [rax]
0x18001d523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d528  mov     ebx, eax
0x18001d52a  test    eax, eax
0x18001d52c  js      short loc_18001D575
0x18001d52e  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x18001d537  lea     r8, ?ThreadProc@CalibrationTask@@CAKPEAX@Z; lpStartAddress
0x18001d53e  mov     r9, rsi; lpParameter
0x18001d541  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18001d549  xor     edx, edx; dwStackSize
0x18001d54b  xor     ecx, ecx; lpThreadAttributes
0x18001d54d  call    cs:__imp_CreateThread
0x18001d553  mov     [rbp+40h], rax
0x18001d557  test    rax, rax
0x18001d55a  jnz     short loc_18001D571
0x18001d55c  call    cs:__imp_GetLastError
0x18001d562  mov     ebx, eax
0x18001d564  test    eax, eax
0x18001d566  jle     short loc_18001D571
0x18001d568  movzx   ebx, ax
0x18001d56b  or      ebx, 80070000h
0x18001d571  test    ebx, ebx
0x18001d573  jns     short loc_18001D5AB
0x18001d575  mov     rcx, [rsi]; hLibModule
0x18001d578  test    rcx, rcx
0x18001d57b  jz      short loc_18001D583
0x18001d57d  call    cs:__imp_FreeLibrary
0x18001d583  mov     rcx, [rdi]
0x18001d586  test    rcx, rcx
0x18001d589  jz      short loc_18001D597
0x18001d58b  mov     rax, [rcx]
0x18001d58e  mov     rax, [rax+10h]
0x18001d592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d597  mov     edx, 10h; unsigned __int64
0x18001d59c  mov     rcx, rsi; void *
0x18001d59f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d5a4  jmp     short loc_18001D5AB
0x18001d5a6  mov     ebx, 8007000Eh
0x18001d5ab  lea     rcx, [rbp+50h]; lpCriticalSection
0x18001d5af  call    cs:__imp_LeaveCriticalSection
0x18001d5b5  mov     eax, ebx
0x18001d5b7  add     rsp, 30h
0x18001d5bb  pop     r14
0x18001d5bd  pop     rdi
0x18001d5be  pop     rsi
0x18001d5bf  pop     rbp
0x18001d5c0  pop     rbx
0x18001d5c1  retn
```
