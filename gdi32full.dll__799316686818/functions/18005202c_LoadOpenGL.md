# LoadOpenGL

- ea: `0x18005202c`
- end: `0x180052124`
- name: `LoadOpenGL`
- size: `248`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180051bac`
- `0x18005ec9c`
- `0x180080c34`

## callees

- `0x18005202c`
- `0x18007ba24`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800520b6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800520b6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005206e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005206e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005209d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005209d`
- `ntdll!RtlEnterCriticalSection` at `0x18005204c`
- `ntdll!RtlEnterCriticalSection` at `0x18005204c`
- `ntdll!RtlLeaveCriticalSection` at `0x180052113`
- `ntdll!RtlLeaveCriticalSection` at `0x180052113`

## string_xrefs

- `0x180052063`: `opengl32.dll`

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
  if ( qword_1800FA700 )
  {
LABEL_9:
    ++dword_1800FA6F8;
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
      ProcAddress = GetProcAddress(Library, off_1800AC750[i]);
      *v2 = ProcAddress;
      if ( !ProcAddress )
      {
        FreeLibrary(Library);
        goto LABEL_10;
      }
      ++v2;
    }
    xmmword_1800FA710 = v6[0];
    xmmword_1800FA730 = v6[2];
    xmmword_1800FA720 = v6[1];
    xmmword_1800FA750 = v6[4];
    xmmword_1800FA740 = v6[3];
    qword_1800FA700 = (__int64)Library;
    goto LABEL_9;
  }
LABEL_10:
  RtlLeaveCriticalSection(&semGlLoad);
  return v0;
}

```

## disassembly

```asm
0x18005202c  push    rbx
0x18005202e  push    rbp
0x18005202f  push    rsi
0x180052030  push    rdi
0x180052031  sub     rsp, 78h
0x180052035  xor     edx, edx; Val
0x180052037  lea     rcx, [rsp+98h+var_78]; void *
0x18005203c  lea     r8d, [rdx+50h]; Size
0x180052040  call    memset_0
0x180052045  lea     rcx, semGlLoad; CriticalSection
0x18005204c  call    cs:__imp_RtlEnterCriticalSection
0x180052052  cmp     cs:qword_1800FA700, 0
0x18005205a  jnz     loc_180052101
0x180052060  xor     r8d, r8d; dwFlags
0x180052063  lea     rcx, aOpengl32Dll; "opengl32.dll"
0x18005206a  xor     edx, edx; hFile
0x18005206c  xor     ebp, ebp
0x18005206e  call    cs:__imp_LoadLibraryExW
0x180052074  mov     rdi, rax
0x180052077  test    rax, rax
0x18005207a  jz      loc_18005210C
0x180052080  lea     rsi, [rsp+98h+var_78]
0x180052085  xor     ebx, ebx
0x180052087  cmp     ebx, 0Ah
0x18005208a  jnb     short loc_1800520BE
0x18005208c  lea     rax, off_1800AC750; "GlmfInitPlayback"
0x180052093  movsxd  rdx, ebx
0x180052096  mov     rcx, rdi; hModule
0x180052099  mov     rdx, [rax+rdx*8]; lpProcName
0x18005209d  call    cs:__imp_GetProcAddress
0x1800520a3  mov     [rsi], rax
0x1800520a6  test    rax, rax
0x1800520a9  jz      short loc_1800520B3
0x1800520ab  add     rsi, 8
0x1800520af  inc     ebx
0x1800520b1  jmp     short loc_180052087
0x1800520b3  mov     rcx, rdi; hLibModule
0x1800520b6  call    cs:__imp_FreeLibrary
0x1800520bc  jmp     short loc_18005210C
0x1800520be  movaps  xmm0, [rsp+98h+var_78]
0x1800520c3  movaps  xmm1, [rsp+98h+var_68]
0x1800520c8  movaps  cs:xmmword_1800FA710, xmm0
0x1800520cf  movaps  xmm0, [rsp+98h+var_58]
0x1800520d4  movaps  cs:xmmword_1800FA730, xmm0
0x1800520db  movaps  xmm0, [rsp+98h+var_38]
0x1800520e0  movaps  cs:xmmword_1800FA720, xmm1
0x1800520e7  movaps  xmm1, [rsp+98h+var_48]
0x1800520ec  movaps  cs:xmmword_1800FA750, xmm0
0x1800520f3  movaps  cs:xmmword_1800FA740, xmm1
0x1800520fa  mov     cs:qword_1800FA700, rdi
0x180052101  inc     cs:dword_1800FA6F8
0x180052107  mov     ebp, 1
0x18005210c  lea     rcx, semGlLoad; CriticalSection
0x180052113  call    cs:__imp_RtlLeaveCriticalSection
0x180052119  mov     eax, ebp
0x18005211b  add     rsp, 78h
0x18005211f  pop     rdi
0x180052120  pop     rsi
0x180052121  pop     rbp
0x180052122  pop     rbx
0x180052123  retn
```
