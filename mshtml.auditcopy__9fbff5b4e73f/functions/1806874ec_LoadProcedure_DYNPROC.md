# LoadProcedure(DYNPROC *)

- ea: `0x1806874ec`
- end: `0x1806876d3`
- name: `?LoadProcedure@@YAJPEAUDYNPROC@@@Z`
- size: `487`
- prototype: `__int64 __fastcall(struct DYNPROC *)`
- caller_count: `33`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800e7d80`
- `0x180687384`
- `0x180687404`
- `0x180687478`
- `0x180728c74`
- `0x18084cb88`
- `0x1808d303c`
- `0x180a94234`
- `0x180ac5948`
- `0x180b26a40`
- `0x180b5d070`
- `0x180b5d10c`
- `0x180b5d1a8`
- `0x180b5d228`
- `0x180b5d2a8`
- `0x180b5d31c`
- `0x180b5d3a8`
- `0x180b5d41c`
- `0x180b5d4c8`
- `0x180b5d574`
- `0x180b5d5e8`
- `0x180b5d668`
- `0x180b5d6e0`
- `0x180f98828`
- `0x180f988f0`
- `0x180f98944`
- `0x180f9a640`
- `0x180fa9470`
- `0x180faba30`
- `0x18101f61c`
- `0x18102c470`
- `0x18102cdd4`
- `0x18104f5c4`

## callees

- `0x1806874ec`
- `0x1807e1ba4`
- `0x180845974`
- `0x1810f65c0`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180687636`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180687636`
- `KERNEL32!GetProcAddress` at `0x18068766f`
- `KERNEL32!GetProcAddress` at `0x18068766f`
- `KERNEL32!GetLastError` at `0x180687555`
- `KERNEL32!GetLastError` at `0x180687555`
- `KERNEL32!GetModuleFileNameA` at `0x18068758e`
- `KERNEL32!GetModuleFileNameA` at `0x18068758e`
- `KERNEL32!FreeLibrary` at `0x180687650`
- `KERNEL32!FreeLibrary` at `0x180687650`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1806875b2`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1806875b2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18068753d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18068760e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18068753d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18068760e`
- `api-ms-win-core-processenvironment-l1-2-0!SearchPathA` at `0x1806875ef`
- `api-ms-win-core-processenvironment-l1-2-0!SearchPathA` at `0x1806875ef`

## pseudocode

```c
signed int __fastcall LoadProcedure(struct DYNPROC *a1)
{
  __int64 v2; // rbx
  HMODULE Library; // rdi
  DWORD LastError; // eax
  FARPROC ProcAddress; // rax
  signed int result; // eax
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
    *(_QWORD *)(v2 + 8) = qword_1815C3648;
    *(_QWORD *)v2 = Library;
    qword_1815C3648 = v2;
  }
  CLocks_pdynlibHead::~CLocks_pdynlibHead((CLocks_pdynlibHead *)v7);
LABEL_15:
  ProcAddress = GetProcAddress(*(HMODULE *)v2, *((LPCSTR *)a1 + 2));
  *(_QWORD *)a1 = ProcAddress;
  if ( ProcAddress )
    return 0;
LABEL_19:
  result = GetLastWin32Error();
  if ( !result )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x1806874ec  mov     [rsp-8+arg_0], rcx
0x1806874f1  push    rbp
0x1806874f2  push    rbx
0x1806874f3  push    rsi
0x1806874f4  push    rdi
0x1806874f5  lea     rbp, [rsp-178h]
0x1806874fd  sub     rsp, 278h
0x180687504  mov     rax, cs:__security_cookie
0x18068750b  xor     rax, rsp
0x18068750e  mov     [rbp+190h+var_30], rax
0x180687515  mov     rsi, [rbp+190h+arg_0]
0x18068751c  cmp     qword ptr [rsi], 0
0x180687520  mov     rbx, [rsi+8]
0x180687524  jz      loc_18068765E
0x18068752a  cmp     qword ptr [rbx], 0
0x18068752e  jnz     loc_180687683
0x180687534  mov     rcx, [rbx+10h]; lpLibFileName
0x180687538  xor     r8d, r8d; dwFlags
0x18068753b  xor     edx, edx; hFile
0x18068753d  call    cs:__imp_LoadLibraryExA
0x180687544  nop     dword ptr [rax+rax+00h]
0x180687549  mov     rdi, rax
0x18068754c  test    rax, rax
0x18068754f  jnz     loc_180687626
0x180687555  call    cs:__imp_GetLastError
0x18068755c  nop     dword ptr [rax+rax+00h]
0x180687561  cmp     eax, 7Eh ; '~'
0x180687564  jz      short loc_180687571
0x180687566  cmp     eax, 485h
0x18068756b  jnz     loc_1806876C2
0x180687571  mov     rcx, cs:?g_hInstCore@@3PEAUHINSTANCE__@@EA; hModule
0x180687578  lea     rdx, [rsp+290h+Filename]; lpFilename
0x18068757d  mov     edi, 104h
0x180687582  mov     [rsp+290h+FilePart], 0
0x18068758b  mov     r8d, edi; nSize
0x18068758e  call    cs:__imp_GetModuleFileNameA
0x180687595  nop     dword ptr [rax+rax+00h]
0x18068759a  test    eax, eax
0x18068759c  jz      loc_1806876C2
0x1806875a2  lea     r9, [rsp+290h+FilePart]; lpFilePart
0x1806875a7  mov     edx, edi; nBufferLength
0x1806875a9  lea     r8, [rbp+190h+Buffer]; lpBuffer
0x1806875ad  lea     rcx, [rsp+290h+Filename]; lpFileName
0x1806875b2  call    cs:__imp_GetFullPathNameA
0x1806875b9  nop     dword ptr [rax+rax+00h]
0x1806875be  test    eax, eax
0x1806875c0  jz      loc_1806876C2
0x1806875c6  mov     rax, [rsp+290h+FilePart]
0x1806875cb  lea     rcx, [rbp+190h+Buffer]; lpPath
0x1806875cf  mov     [rsp+290h+lpFilePart], 0; lpFilePart
0x1806875d8  mov     r9d, edi; nBufferLength
0x1806875db  xor     r8d, r8d; lpExtension
0x1806875de  mov     byte ptr [rax], 0
0x1806875e1  lea     rax, [rsp+290h+Filename]
0x1806875e6  mov     rdx, [rbx+10h]; lpFileName
0x1806875ea  mov     [rsp+290h+lpBuffer], rax; lpBuffer
0x1806875ef  call    cs:__imp_SearchPathA
0x1806875f6  nop     dword ptr [rax+rax+00h]
0x1806875fb  test    eax, eax
0x1806875fd  jz      loc_1806876C2
0x180687603  xor     edx, edx; hFile
0x180687605  lea     rcx, [rsp+290h+Filename]; lpLibFileName
0x18068760a  lea     r8d, [rdx+8]; dwFlags
0x18068760e  call    cs:__imp_LoadLibraryExA
0x180687615  nop     dword ptr [rax+rax+00h]
0x18068761a  mov     rdi, rax
0x18068761d  test    rax, rax
0x180687620  jz      loc_1806876C2
0x180687626  cmp     cs:?m_fInit@CLocks_pdynlibHead@@0_NA, 0; bool CLocks_pdynlibHead::m_fInit
0x18068762d  jz      short loc_180687647
0x18068762f  lea     rcx, ?m_srwLock@CLocks_pdynlibHead@@0U_RTL_SRWLOCK@@A; SRWLock
0x180687636  call    cs:__imp_AcquireSRWLockExclusive
0x18068763d  nop     dword ptr [rax+rax+00h]
0x180687642  mov     [rsp+290h+var_260], 1
0x180687647  cmp     qword ptr [rbx], 0
0x18068764b  jz      short loc_1806876A1
0x18068764d  mov     rcx, rdi; hLibModule
0x180687650  call    cs:__imp_FreeLibrary
0x180687657  nop     dword ptr [rax+rax+00h]
0x18068765c  jmp     short loc_1806876B6
0x18068765e  cmp     qword ptr [rbx], 0
0x180687662  jz      loc_180687534
0x180687668  mov     rdx, [rsi+10h]; lpProcName
0x18068766c  mov     rcx, [rbx]; hModule
0x18068766f  call    cs:__imp_GetProcAddress
0x180687676  nop     dword ptr [rax+rax+00h]
0x18068767b  mov     [rsi], rax
0x18068767e  test    rax, rax
0x180687681  jz      short loc_1806876C2
0x180687683  xor     eax, eax
0x180687685  mov     rcx, [rbp+190h+var_30]
0x18068768c  xor     rcx, rsp; StackCookie
0x18068768f  call    __security_check_cookie
0x180687694  add     rsp, 278h
0x18068769b  pop     rdi
0x18068769c  pop     rsi
0x18068769d  pop     rbx
0x18068769e  pop     rbp
0x18068769f  retn
0x1806876a1  mov     rax, cs:qword_1815C3648
0x1806876a8  mov     [rbx+8], rax
0x1806876ac  mov     [rbx], rdi
0x1806876af  mov     cs:qword_1815C3648, rbx
0x1806876b6  lea     rcx, [rsp+290h+var_260]; this
0x1806876bb  call    ??1CLocks_pdynlibHead@@QEAA@XZ; CLocks_pdynlibHead::~CLocks_pdynlibHead(void)
0x1806876c0  jmp     short loc_180687668
0x1806876c2  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1806876c7  test    eax, eax
0x1806876c9  mov     ecx, 80004005h
0x1806876ce  cmovz   eax, ecx
0x1806876d1  jmp     short loc_180687685
```
