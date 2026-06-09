# UalOpenSession

- ea: `0x140081508`
- end: `0x14008166c`
- name: `UalOpenSession`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400236a0`

## callees

- `0x140002c43`
- `0x140081508`
- `0x1400818b0`
- `0x140085010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x140081540`
- `KERNEL32!LoadLibraryExW` at `0x140081540`
- `KERNEL32!FreeLibrary` at `0x1400815e5`
- `KERNEL32!FreeLibrary` at `0x1400815e5`
- `KERNEL32!GetLastError` at `0x140081552`
- `KERNEL32!GetLastError` at `0x1400815c9`
- `KERNEL32!GetLastError` at `0x140081552`
- `KERNEL32!GetLastError` at `0x1400815c9`
- `KERNEL32!GetProcAddress` at `0x140081577`
- `KERNEL32!GetProcAddress` at `0x140081597`
- `KERNEL32!GetProcAddress` at `0x1400815b7`
- `KERNEL32!GetProcAddress` at `0x140081577`
- `KERNEL32!GetProcAddress` at `0x140081597`
- `KERNEL32!GetProcAddress` at `0x1400815b7`

## string_xrefs

- `0x140081533`: `ualapi.dll`

## pseudocode

```c
signed int UalOpenSession()
{
  HMODULE Library; // rax
  signed int result; // eax
  signed int LastError; // eax
  unsigned int v3; // ebx
  int v4; // [rsp+20h] [rbp-2C8h] BYREF
  __int128 v5; // [rsp+24h] [rbp-2C4h]
  _BYTE v6[668]; // [rsp+34h] [rbp-2B4h] BYREF

  if ( ualapiModule )
    goto LABEL_11;
  Library = LoadLibraryExW(L"ualapi.dll", 0, 0x800u);
  ualapiModule = Library;
  if ( !Library )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  fnUalInstrument = (int (*)(struct tagUAL_DATA_BLOB *))GetProcAddress(Library, "UalInstrument");
  if ( fnUalInstrument )
  {
    fnUalStart = (int (*)(struct tagUAL_DATA_BLOB *))GetProcAddress(ualapiModule, "UalStart");
    if ( fnUalStart )
    {
      fnUalStop = (int (*)(struct tagUAL_DATA_BLOB *))GetProcAddress(ualapiModule, "UalStop");
      if ( fnUalStop )
      {
LABEL_11:
        memset_0(v6, 0, sizeof(v6));
        v4 = 688;
        v5 = SumGuid_FAX;
        return ((__int64 (__fastcall *)(int *))fnUalStart)(&v4);
      }
    }
  }
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  FreeLibrary(ualapiModule);
  result = v3;
  ualapiModule = 0;
  fnUalInstrument = 0;
  fnUalStart = 0;
  fnUalStop = 0;
  return result;
}

```

## disassembly

```asm
0x140081508  push    rbx
0x14008150a  sub     rsp, 2E0h
0x140081511  mov     rax, cs:__security_cookie
0x140081518  xor     rax, rsp
0x14008151b  mov     [rsp+2E8h+var_18], rax
0x140081523  cmp     cs:?ualapiModule@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ualapiModule
0x14008152b  jnz     loc_14008161B
0x140081531  xor     edx, edx; hFile
0x140081533  lea     rcx, aUalapiDll; "ualapi.dll"
0x14008153a  mov     r8d, 800h; dwFlags
0x140081540  call    cs:__imp_LoadLibraryExW
0x140081546  mov     cs:?ualapiModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ualapiModule
0x14008154d  test    rax, rax
0x140081550  jnz     short loc_14008156D
0x140081552  call    cs:__imp_GetLastError
0x140081558  test    eax, eax
0x14008155a  jle     loc_140081653
0x140081560  movzx   eax, ax
0x140081563  or      eax, 80070000h
0x140081568  jmp     loc_140081653
0x14008156d  lea     rdx, aUalinstrument; "UalInstrument"
0x140081574  mov     rcx, rax; hModule
0x140081577  call    cs:__imp_GetProcAddress
0x14008157d  mov     cs:?fnUalInstrument@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, rax; long (*fnUalInstrument)(tagUAL_DATA_BLOB *)
0x140081584  test    rax, rax
0x140081587  jz      short loc_1400815C9
0x140081589  mov     rcx, cs:?ualapiModule@@3PEAUHINSTANCE__@@EA; hModule
0x140081590  lea     rdx, aUalstart; "UalStart"
0x140081597  call    cs:__imp_GetProcAddress
0x14008159d  mov     cs:?fnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, rax; long (*fnUalStart)(tagUAL_DATA_BLOB *)
0x1400815a4  test    rax, rax
0x1400815a7  jz      short loc_1400815C9
0x1400815a9  mov     rcx, cs:?ualapiModule@@3PEAUHINSTANCE__@@EA; hModule
0x1400815b0  lea     rdx, aUalstop; "UalStop"
0x1400815b7  call    cs:__imp_GetProcAddress
0x1400815bd  mov     cs:?fnUalStop@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, rax; long (*fnUalStop)(tagUAL_DATA_BLOB *)
0x1400815c4  test    rax, rax
0x1400815c7  jnz     short loc_14008161B
0x1400815c9  call    cs:__imp_GetLastError
0x1400815cf  mov     ebx, eax
0x1400815d1  test    eax, eax
0x1400815d3  jle     short loc_1400815DE
0x1400815d5  movzx   ebx, ax
0x1400815d8  or      ebx, 80070000h
0x1400815de  mov     rcx, cs:?ualapiModule@@3PEAUHINSTANCE__@@EA; hLibModule
0x1400815e5  call    cs:__imp_FreeLibrary
0x1400815eb  mov     eax, ebx
0x1400815ed  mov     cs:?ualapiModule@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ualapiModule
0x1400815f8  mov     cs:?fnUalInstrument@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, 0; long (*fnUalInstrument)(tagUAL_DATA_BLOB *)
0x140081603  mov     cs:?fnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, 0; long (*fnUalStart)(tagUAL_DATA_BLOB *)
0x14008160e  mov     cs:?fnUalStop@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, 0; long (*fnUalStop)(tagUAL_DATA_BLOB *)
0x140081619  jmp     short loc_140081653
0x14008161b  xor     edx, edx; Val
0x14008161d  lea     rcx, [rsp+2E8h+var_2B4]; void *
0x140081622  mov     r8d, 29Ch; Size
0x140081628  call    memset_0
0x14008162d  movups  xmm0, cs:SumGuid_FAX
0x140081634  mov     rax, cs:?fnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA; long (*fnUalStart)(tagUAL_DATA_BLOB *)
0x14008163b  lea     rcx, [rsp+2E8h+var_2C8]
0x140081640  mov     [rsp+2E8h+var_2C8], 2B0h
0x140081648  movdqu  [rsp+2E8h+var_2C4], xmm0
0x14008164e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081653  mov     rcx, [rsp+2E8h+var_18]
0x14008165b  xor     rcx, rsp; StackCookie
0x14008165e  call    __security_check_cookie
0x140081663  add     rsp, 2E0h
0x14008166a  pop     rbx
0x14008166b  retn
```
