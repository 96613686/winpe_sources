# DelayLoadedModule::Load(HINSTANCE__ * *)

- ea: `0x1801ae2d8`
- end: `0x1801ae369`
- name: `?Load@DelayLoadedModule@@QEAAJPEAPEAUHINSTANCE__@@@Z`
- size: `145`
- prototype: `__int64 __fastcall(DelayLoadedModule *__hidden this, HINSTANCE *)`
- caller_count: `12`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a6aa0`
- `0x1800cc12c`
- `0x1800ccb44`
- `0x1801a3f20`
- `0x1801ad6a8`
- `0x1801adcb4`
- `0x1801ae0f8`
- `0x1801ae23c`
- `0x1801b43cc`
- `0x1801ebed0`
- `0x1801edab0`
- `0x1802d1100`

## callees

- `0x1801ae2d8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801ae332`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801ae332`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801ae313`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801ae313`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ae33a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ae33a`

## pseudocode

```c
__int64 __fastcall DelayLoadedModule::Load(DelayLoadedModule *this, HINSTANCE *a2)
{
  HINSTANCE v2; // rsi
  unsigned int v5; // ecx
  HMODULE Library; // rax
  HMODULE v8; // rcx
  signed int LastError; // eax

  v2 = (HINSTANCE)*((_QWORD *)this + 1);
  if ( v2 != (HINSTANCE)-1LL )
  {
    if ( !v2 )
    {
      v5 = *(_DWORD *)this;
      goto LABEL_4;
    }
    goto LABEL_3;
  }
  Library = LoadLibraryExW(*((LPCWSTR *)this + 2), 0, 0);
  v8 = Library;
  if ( Library )
  {
    v2 = (HINSTANCE)_InterlockedCompareExchange64((volatile signed __int64 *)this + 1, (signed __int64)Library, -1);
    if ( v2 == (HINSTANCE)-1LL )
    {
      v2 = Library;
      v8 = 0;
    }
    FreeLibrary(v8);
LABEL_3:
    v5 = 0;
    goto LABEL_4;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  *(_DWORD *)this = v5;
  _InterlockedCompareExchange64((volatile signed __int64 *)this + 1, 0, -1);
LABEL_4:
  *a2 = v2;
  return v5;
}

```

## disassembly

```asm
0x1801ae2d8  push    rbx
0x1801ae2da  push    rsi
0x1801ae2db  push    rdi
0x1801ae2dc  push    r14
0x1801ae2de  sub     rsp, 28h
0x1801ae2e2  mov     rsi, [rcx+8]
0x1801ae2e6  mov     r14, rdx
0x1801ae2e9  mov     rdi, rcx
0x1801ae2ec  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1801ae2f0  jz      short loc_1801AE30A
0x1801ae2f2  xor     ebx, ebx
0x1801ae2f4  test    rsi, rsi
0x1801ae2f7  jz      short loc_1801AE365
0x1801ae2f9  mov     ecx, ebx
0x1801ae2fb  mov     [r14], rsi
0x1801ae2fe  mov     eax, ecx
0x1801ae300  add     rsp, 28h
0x1801ae304  pop     r14
0x1801ae306  pop     rdi
0x1801ae307  pop     rsi
0x1801ae308  pop     rbx
0x1801ae309  retn
0x1801ae30a  mov     rcx, [rcx+10h]; lpLibFileName
0x1801ae30e  xor     r8d, r8d; dwFlags
0x1801ae311  xor     edx, edx; hFile
0x1801ae313  call    cs:__imp_LoadLibraryExW
0x1801ae319  xor     ebx, ebx
0x1801ae31b  mov     rcx, rax; hLibModule
0x1801ae31e  test    rax, rax
0x1801ae321  jz      short loc_1801AE33A
0x1801ae323  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801ae327  lock cmpxchg [rdi+8], rcx
0x1801ae32d  mov     rsi, rax
0x1801ae330  jz      short loc_1801AE35D
0x1801ae332  call    cs:__imp_FreeLibrary
0x1801ae338  jmp     short loc_1801AE2F9
0x1801ae33a  call    cs:__imp_GetLastError
0x1801ae340  mov     ecx, eax
0x1801ae342  test    eax, eax
0x1801ae344  jle     short loc_1801AE34F
0x1801ae346  movzx   ecx, ax
0x1801ae349  or      ecx, 80070000h
0x1801ae34f  mov     [rdi], ecx
0x1801ae351  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801ae355  lock cmpxchg [rdi+8], rbx
0x1801ae35b  jmp     short loc_1801AE2FB
0x1801ae35d  mov     rsi, rcx
0x1801ae360  mov     rcx, rbx
0x1801ae363  jmp     short loc_1801AE332
0x1801ae365  mov     ecx, [rcx]
0x1801ae367  jmp     short loc_1801AE2FB
```
