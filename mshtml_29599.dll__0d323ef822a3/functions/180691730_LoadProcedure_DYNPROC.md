# LoadProcedure(DYNPROC *)

- ea: `0x180691730`
- end: `0x1806918e0`
- name: `?LoadProcedure@@YAJPEAUDYNPROC@@@Z`
- size: `432`
- prototype: `__int64 __fastcall(struct DYNPROC *)`
- caller_count: `33`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180439d10`
- `0x1805611d8`
- `0x180561254`
- `0x180561fd8`
- `0x1807218c0`
- `0x180849ab0`
- `0x1808c8a60`
- `0x180a7f8e4`
- `0x180ab0594`
- `0x180b0feec`
- `0x180b44720`
- `0x180b447bc`
- `0x180b44854`
- `0x180b448d4`
- `0x180b44954`
- `0x180b449c8`
- `0x180b44a54`
- `0x180b44ac8`
- `0x180b44b74`
- `0x180b44c20`
- `0x180b44c94`
- `0x180b44d14`
- `0x180b44d8c`
- `0x180f6d98c`
- `0x180f6da54`
- `0x180f6daa4`
- `0x180f6f700`
- `0x180f7e2e0`
- `0x180f80820`
- `0x180ff1c1c`
- `0x180ffe790`
- `0x180fff0e4`
- `0x181021418`

## callees

- `0x180691730`
- `0x1807d659c`
- `0x180842c6c`
- `0x1810c2d60`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180691856`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180691856`
- `KERNEL32!GetProcAddress` at `0x180691883`
- `KERNEL32!GetProcAddress` at `0x180691883`
- `KERNEL32!GetLastError` at `0x180691793`
- `KERNEL32!GetLastError` at `0x180691793`
- `KERNEL32!GetModuleFileNameA` at `0x1806917c6`
- `KERNEL32!GetModuleFileNameA` at `0x1806917c6`
- `KERNEL32!FreeLibrary` at `0x18069186a`
- `KERNEL32!FreeLibrary` at `0x18069186a`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1806917e4`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1806917e4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180691781`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180691834`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180691781`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180691834`
- `api-ms-win-core-processenvironment-l1-2-0!SearchPathA` at `0x18069181b`
- `api-ms-win-core-processenvironment-l1-2-0!SearchPathA` at `0x18069181b`

## pseudocode

```c
__int64 __fastcall LoadProcedure(struct DYNPROC *a1)
{
  __int64 v2; // rbx
  HMODULE Library; // rdi
  DWORD LastError; // eax
  FARPROC ProcAddress; // rax
  __int64 result; // rax
  char v7[8]; // [rsp+30h] [rbp-D0h] BYREF
  LPSTR FilePart; // [rsp+38h] [rbp-C8h] BYREF
  CHAR Filename[272]; // [rsp+40h] [rbp-C0h] BYREF
  CHAR Buffer[272]; // [rsp+150h] [rbp+50h] BYREF

  v2 = *((_QWORD *)a1 + 1);
  if ( *(_QWORD *)a1 )
  {
    if ( *(_QWORD *)v2 )
      return 0;
  }
  else if ( *(_QWORD *)v2 )
  {
    goto LABEL_15;
  }
  Library = LoadLibraryExA(*(LPCSTR *)(v2 + 16), 0, 0);
  if ( !Library )
  {
    LastError = GetLastError();
    if ( LastError != 126 && LastError != 1157 )
      goto LABEL_19;
    FilePart = 0;
    if ( !GetModuleFileNameA(g_hInstCore, Filename, 0x104u) )
      goto LABEL_19;
    if ( !GetFullPathNameA(Filename, 0x104u, Buffer, &FilePart) )
      goto LABEL_19;
    *FilePart = 0;
    if ( !SearchPathA(Buffer, *(LPCSTR *)(v2 + 16), 0, 0x104u, Filename, 0) )
      goto LABEL_19;
    Library = LoadLibraryExA(Filename, 0, 8u);
    if ( !Library )
      goto LABEL_19;
  }
  if ( CLocks_pdynlibHead::m_fInit )
  {
    AcquireSRWLockExclusive(&CLocks_pdynlibHead::m_srwLock);
    v7[0] = 1;
  }
  if ( *(_QWORD *)v2 )
  {
    FreeLibrary(Library);
  }
  else
  {
    *(_QWORD *)(v2 + 8) = qword_181590548;
    *(_QWORD *)v2 = Library;
    qword_181590548 = v2;
  }
  CLocks_pdynlibHead::~CLocks_pdynlibHead((CLocks_pdynlibHead *)v7);
LABEL_15:
  ProcAddress = GetProcAddress(*(HMODULE *)v2, *((LPCSTR *)a1 + 2));
  *(_QWORD *)a1 = ProcAddress;
  if ( ProcAddress )
    return 0;
LABEL_19:
  result = GetLastWin32Error();
  if ( !(_DWORD)result )
    return 2147500037LL;
  return result;
}

```

## disassembly

```asm
0x180691730  mov     [rsp-8+arg_0], rcx
0x180691735  push    rbp
0x180691736  push    rbx
0x180691737  push    rsi
0x180691738  push    rdi
0x180691739  lea     rbp, [rsp-178h]
0x180691741  sub     rsp, 278h
0x180691748  mov     rax, cs:__security_cookie
0x18069174f  xor     rax, rsp
0x180691752  mov     [rbp+190h+var_30], rax
0x180691759  mov     rsi, [rbp+190h+arg_0]
0x180691760  cmp     qword ptr [rsi], 0
0x180691764  mov     rbx, [rsi+8]
0x180691768  jz      loc_180691872
0x18069176e  cmp     qword ptr [rbx], 0
0x180691772  jnz     loc_180691891
0x180691778  mov     rcx, [rbx+10h]; lpLibFileName
0x18069177c  xor     r8d, r8d; dwFlags
0x18069177f  xor     edx, edx; hFile
0x180691781  call    cs:__imp_LoadLibraryExA
0x180691787  mov     rdi, rax
0x18069178a  test    rax, rax
0x18069178d  jnz     loc_180691846
0x180691793  call    cs:__imp_GetLastError
0x180691799  cmp     eax, 7Eh ; '~'
0x18069179c  jz      short loc_1806917A9
0x18069179e  cmp     eax, 485h
0x1806917a3  jnz     loc_1806918CF
0x1806917a9  mov     rcx, cs:?g_hInstCore@@3PEAUHINSTANCE__@@EA; hModule
0x1806917b0  lea     rdx, [rsp+290h+Filename]; lpFilename
0x1806917b5  mov     edi, 104h
0x1806917ba  mov     [rsp+290h+FilePart], 0
0x1806917c3  mov     r8d, edi; nSize
0x1806917c6  call    cs:__imp_GetModuleFileNameA
0x1806917cc  test    eax, eax
0x1806917ce  jz      loc_1806918CF
0x1806917d4  lea     r9, [rsp+290h+FilePart]; lpFilePart
0x1806917d9  mov     edx, edi; nBufferLength
0x1806917db  lea     r8, [rbp+190h+Buffer]; lpBuffer
0x1806917df  lea     rcx, [rsp+290h+Filename]; lpFileName
0x1806917e4  call    cs:__imp_GetFullPathNameA
0x1806917ea  test    eax, eax
0x1806917ec  jz      loc_1806918CF
0x1806917f2  mov     rax, [rsp+290h+FilePart]
0x1806917f7  lea     rcx, [rbp+190h+Buffer]; lpPath
0x1806917fb  mov     [rsp+290h+lpFilePart], 0; lpFilePart
0x180691804  mov     r9d, edi; nBufferLength
0x180691807  xor     r8d, r8d; lpExtension
0x18069180a  mov     byte ptr [rax], 0
0x18069180d  lea     rax, [rsp+290h+Filename]
0x180691812  mov     rdx, [rbx+10h]; lpFileName
0x180691816  mov     [rsp+290h+lpBuffer], rax; lpBuffer
0x18069181b  call    cs:__imp_SearchPathA
0x180691821  test    eax, eax
0x180691823  jz      loc_1806918CF
0x180691829  xor     edx, edx; hFile
0x18069182b  lea     rcx, [rsp+290h+Filename]; lpLibFileName
0x180691830  lea     r8d, [rdx+8]; dwFlags
0x180691834  call    cs:__imp_LoadLibraryExA
0x18069183a  mov     rdi, rax
0x18069183d  test    rax, rax
0x180691840  jz      loc_1806918CF
0x180691846  cmp     cs:?m_fInit@CLocks_pdynlibHead@@0_NA, 0; bool CLocks_pdynlibHead::m_fInit
0x18069184d  jz      short loc_180691861
0x18069184f  lea     rcx, ?m_srwLock@CLocks_pdynlibHead@@0U_RTL_SRWLOCK@@A; SRWLock
0x180691856  call    cs:__imp_AcquireSRWLockExclusive
0x18069185c  mov     [rsp+290h+var_260], 1
0x180691861  cmp     qword ptr [rbx], 0
0x180691865  jz      short loc_1806918AE
0x180691867  mov     rcx, rdi; hLibModule
0x18069186a  call    cs:__imp_FreeLibrary
0x180691870  jmp     short loc_1806918C3
0x180691872  cmp     qword ptr [rbx], 0
0x180691876  jz      loc_180691778
0x18069187c  mov     rdx, [rsi+10h]; lpProcName
0x180691880  mov     rcx, [rbx]; hModule
0x180691883  call    cs:__imp_GetProcAddress
0x180691889  mov     [rsi], rax
0x18069188c  test    rax, rax
0x18069188f  jz      short loc_1806918CF
0x180691891  xor     eax, eax
0x180691893  mov     rcx, [rbp+190h+var_30]
0x18069189a  xor     rcx, rsp; StackCookie
0x18069189d  call    __security_check_cookie
0x1806918a2  add     rsp, 278h
0x1806918a9  pop     rdi
0x1806918aa  pop     rsi
0x1806918ab  pop     rbx
0x1806918ac  pop     rbp
0x1806918ad  retn
0x1806918ae  mov     rax, cs:qword_181590548
0x1806918b5  mov     [rbx+8], rax
0x1806918b9  mov     [rbx], rdi
0x1806918bc  mov     cs:qword_181590548, rbx
0x1806918c3  lea     rcx, [rsp+290h+var_260]; this
0x1806918c8  call    ??1CLocks_pdynlibHead@@QEAA@XZ; CLocks_pdynlibHead::~CLocks_pdynlibHead(void)
0x1806918cd  jmp     short loc_18069187C
0x1806918cf  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1806918d4  test    eax, eax
0x1806918d6  mov     ecx, 80004005h
0x1806918db  cmovz   eax, ecx
0x1806918de  jmp     short loc_180691893
```
