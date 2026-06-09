# LoadOpenGL

- ea: `0x180057ba8`
- end: `0x180057cbf`
- name: `LoadOpenGL`
- size: `279`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180057710`
- `0x180062a84`
- `0x180085b80`

## callees

- `0x180057ba8`
- `0x180080604`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180057c44`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180057c44`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180057bf0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180057bf0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057c25`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057c25`
- `ntdll!RtlEnterCriticalSection` at `0x180057bc8`
- `ntdll!RtlEnterCriticalSection` at `0x180057bc8`
- `ntdll!RtlLeaveCriticalSection` at `0x180057ca7`
- `ntdll!RtlLeaveCriticalSection` at `0x180057ca7`

## string_xrefs

- `0x180057be5`: `opengl32.dll`

## pseudocode

```c
__int64 LoadOpenGL()
{
  unsigned int v0; // ebp
  HMODULE Library; // rdi
  FARPROC *v2; // rsi
  unsigned int i; // ebx
  FARPROC ProcAddress; // rax
  _OWORD v6[7]; // [rsp+20h] [rbp-78h] BYREF

  memset_0(v6, 0, 0x50u);
  RtlEnterCriticalSection(&semGlLoad);
  if ( qword_1800FD7F8 )
  {
LABEL_9:
    ++dword_1800FD7F0;
    v0 = 1;
    goto LABEL_10;
  }
  v0 = 0;
  Library = LoadLibraryExW(L"opengl32.dll", 0, 0);
  if ( Library )
  {
    v2 = (FARPROC *)v6;
    for ( i = 0; i < 0xA; ++i )
    {
      ProcAddress = GetProcAddress(Library, off_1800AF760[i]);
      *v2 = ProcAddress;
      if ( !ProcAddress )
      {
        FreeLibrary(Library);
        goto LABEL_10;
      }
      ++v2;
    }
    xmmword_1800FD800 = v6[0];
    xmmword_1800FD820 = v6[2];
    xmmword_1800FD810 = v6[1];
    xmmword_1800FD840 = v6[4];
    xmmword_1800FD830 = v6[3];
    qword_1800FD7F8 = (__int64)Library;
    goto LABEL_9;
  }
LABEL_10:
  RtlLeaveCriticalSection(&semGlLoad);
  return v0;
}

```

## disassembly

```asm
0x180057ba8  push    rbx
0x180057baa  push    rbp
0x180057bab  push    rsi
0x180057bac  push    rdi
0x180057bad  sub     rsp, 78h
0x180057bb1  xor     edx, edx; Val
0x180057bb3  lea     rcx, [rsp+98h+var_78]; void *
0x180057bb8  lea     r8d, [rdx+50h]; Size
0x180057bbc  call    memset_0
0x180057bc1  lea     rcx, semGlLoad; CriticalSection
0x180057bc8  call    cs:__imp_RtlEnterCriticalSection
0x180057bcf  nop     dword ptr [rax+rax+00h]
0x180057bd4  cmp     cs:qword_1800FD7F8, 0
0x180057bdc  jnz     loc_180057C95
0x180057be2  xor     r8d, r8d; dwFlags
0x180057be5  lea     rcx, aOpengl32Dll; "opengl32.dll"
0x180057bec  xor     edx, edx; hFile
0x180057bee  xor     ebp, ebp
0x180057bf0  call    cs:__imp_LoadLibraryExW
0x180057bf7  nop     dword ptr [rax+rax+00h]
0x180057bfc  mov     rdi, rax
0x180057bff  test    rax, rax
0x180057c02  jz      loc_180057CA0
0x180057c08  lea     rsi, [rsp+98h+var_78]
0x180057c0d  xor     ebx, ebx
0x180057c0f  cmp     ebx, 0Ah
0x180057c12  jnb     short loc_180057C52
0x180057c14  lea     rax, off_1800AF760; "GlmfInitPlayback"
0x180057c1b  movsxd  rdx, ebx
0x180057c1e  mov     rcx, rdi; hModule
0x180057c21  mov     rdx, [rax+rdx*8]; lpProcName
0x180057c25  call    cs:__imp_GetProcAddress
0x180057c2c  nop     dword ptr [rax+rax+00h]
0x180057c31  mov     [rsi], rax
0x180057c34  test    rax, rax
0x180057c37  jz      short loc_180057C41
0x180057c39  add     rsi, 8
0x180057c3d  inc     ebx
0x180057c3f  jmp     short loc_180057C0F
0x180057c41  mov     rcx, rdi; hLibModule
0x180057c44  call    cs:__imp_FreeLibrary
0x180057c4b  nop     dword ptr [rax+rax+00h]
0x180057c50  jmp     short loc_180057CA0
0x180057c52  movaps  xmm0, [rsp+98h+var_78]
0x180057c57  movaps  xmm1, [rsp+98h+var_68]
0x180057c5c  movaps  cs:xmmword_1800FD800, xmm0
0x180057c63  movaps  xmm0, [rsp+98h+var_58]
0x180057c68  movaps  cs:xmmword_1800FD820, xmm0
0x180057c6f  movaps  xmm0, [rsp+98h+var_38]
0x180057c74  movaps  cs:xmmword_1800FD810, xmm1
0x180057c7b  movaps  xmm1, [rsp+98h+var_48]
0x180057c80  movaps  cs:xmmword_1800FD840, xmm0
0x180057c87  movaps  cs:xmmword_1800FD830, xmm1
0x180057c8e  mov     cs:qword_1800FD7F8, rdi
0x180057c95  inc     cs:dword_1800FD7F0
0x180057c9b  mov     ebp, 1
0x180057ca0  lea     rcx, semGlLoad; CriticalSection
0x180057ca7  call    cs:__imp_RtlLeaveCriticalSection
0x180057cae  nop     dword ptr [rax+rax+00h]
0x180057cb3  mov     eax, ebp
0x180057cb5  add     rsp, 78h
0x180057cb9  pop     rdi
0x180057cba  pop     rsi
0x180057cbb  pop     rbp
0x180057cbc  pop     rbx
0x180057cbd  retn
```
