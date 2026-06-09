# IsShortcutAllowed(char const *)

- ea: `0x180069550`
- end: `0x180069681`
- name: `?IsShortcutAllowed@@YAJPEBD@Z`
- size: `305`
- prototype: `__int64 __fastcall(LPCSTR lpString2)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800470d8`

## callees

- `0x18001a094`
- `0x180065b90`
- `0x180068410`
- `0x180069550`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18006960c`
- `KERNEL32!CloseHandle` at `0x18006960c`
- `KERNEL32!CreateFileA` at `0x1800695ef`
- `KERNEL32!CreateFileA` at `0x1800695ef`
- `KERNEL32!GetFileType` at `0x180069601`
- `KERNEL32!GetFileType` at `0x180069601`
- `ADVAPI32!RegCloseKey` at `0x18006965e`
- `ADVAPI32!RegCloseKey` at `0x18006965e`
- `ADVAPI32!RegOpenKeyExA` at `0x180069638`
- `ADVAPI32!RegOpenKeyExA` at `0x180069638`

## pseudocode

```c
__int64 __fastcall IsShortcutAllowed(LPCSTR lpString2)
{
  unsigned __int64 v2; // rax
  HANDLE FileA; // rax
  void *v4; // rsi
  DWORD FileType; // ebx
  unsigned int v6; // ebx
  HKEY phkResult; // [rsp+58h] [rbp+10h] BYREF

  phkResult = 0;
  if ( (unsigned int)IsEmptyString(lpString2) )
    return 2147500037LL;
  if ( !g_phmData )
    return 2147500037LL;
  if ( !*(_QWORD *)g_phmData )
    return 2147500037LL;
  if ( (int)IsChmInSafeDir(*(const char **)(*(_QWORD *)g_phmData + 136LL), 0) < 0 )
    return 2147500037LL;
  v2 = -1;
  do
    ++v2;
  while ( lpString2[v2] );
  if ( v2 >= 2 && *lpString2 == 92 && lpString2[1] == 92 )
    return 2147500037LL;
  FileA = CreateFileA(lpString2, 0, 1u, 0, 3u, 0x80u, 0);
  v4 = FileA;
  if ( FileA != (HANDLE)-1LL )
  {
    FileType = GetFileType(FileA);
    CloseHandle(v4);
    if ( FileType != 1 )
      return 2147500037LL;
  }
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Policies\\Microsoft\\Windows\\System", 0, 0x20019u, &phkResult)
    || !phkResult )
  {
    return 0;
  }
  v6 = CheckSecurityAgainstRegistryKey(lpString2, &phkResult);
  RegCloseKey(phkResult);
  return v6;
}

```

## disassembly

```asm
0x180069550  mov     [rsp+arg_0], rbx
0x180069555  mov     [rsp+arg_10], rsi
0x18006955a  push    rdi
0x18006955b  sub     rsp, 40h
0x18006955f  xor     ebx, ebx
0x180069561  mov     rdi, rcx
0x180069564  mov     [rsp+48h+phkResult], rbx
0x180069569  call    ?IsEmptyString@@YAHPEBD@Z; IsEmptyString(char const *)
0x18006956e  test    eax, eax
0x180069570  jnz     loc_18006966C
0x180069576  mov     rax, cs:?g_phmData@@3PEAPEAVCHmData@@EA; CHmData * * g_phmData
0x18006957d  test    rax, rax
0x180069580  jz      loc_18006966C
0x180069586  mov     rcx, [rax]
0x180069589  test    rcx, rcx
0x18006958c  jz      loc_18006966C
0x180069592  mov     rcx, [rcx+88h]; char *
0x180069599  xor     edx, edx; int
0x18006959b  call    ?IsChmInSafeDir@@YAJPEBDH@Z; IsChmInSafeDir(char const *,int)
0x1800695a0  test    eax, eax
0x1800695a2  js      loc_18006966C
0x1800695a8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800695af  inc     rax
0x1800695b2  cmp     [rdi+rax], bl
0x1800695b5  jnz     short loc_1800695AF
0x1800695b7  cmp     rax, 2
0x1800695bb  jb      short loc_1800695CC
0x1800695bd  cmp     byte ptr [rdi], 5Ch ; '\'
0x1800695c0  jnz     short loc_1800695CC
0x1800695c2  cmp     byte ptr [rdi+1], 5Ch ; '\'
0x1800695c6  jz      loc_18006966C
0x1800695cc  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x1800695d1  xor     r9d, r9d; lpSecurityAttributes
0x1800695d4  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800695dc  xor     edx, edx; dwDesiredAccess
0x1800695de  mov     r8d, 1; dwShareMode
0x1800695e4  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800695ec  mov     rcx, rdi; lpFileName
0x1800695ef  call    cs:__imp_CreateFileA
0x1800695f5  mov     rsi, rax
0x1800695f8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800695fc  jz      short loc_180069617
0x1800695fe  mov     rcx, rax; hFile
0x180069601  call    cs:__imp_GetFileType
0x180069607  mov     rcx, rsi; hObject
0x18006960a  mov     ebx, eax
0x18006960c  call    cs:__imp_CloseHandle
0x180069612  cmp     ebx, 1
0x180069615  jnz     short loc_18006966C
0x180069617  lea     rax, [rsp+48h+phkResult]
0x18006961c  mov     r9d, 20019h; samDesired
0x180069622  xor     r8d, r8d; ulOptions
0x180069625  mov     qword ptr [rsp+48h+dwCreationDisposition], rax; phkResult
0x18006962a  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180069631  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180069638  call    cs:__imp_RegOpenKeyExA
0x18006963e  test    eax, eax
0x180069640  jnz     short loc_180069668
0x180069642  cmp     [rsp+48h+phkResult], 0
0x180069648  jz      short loc_180069668
0x18006964a  lea     rdx, [rsp+48h+phkResult]; HKEY *
0x18006964f  mov     rcx, rdi; lpString2
0x180069652  call    ?CheckSecurityAgainstRegistryKey@@YAJPEBDPEAPEAUHKEY__@@@Z; CheckSecurityAgainstRegistryKey(char const *,HKEY__ * *)
0x180069657  mov     rcx, [rsp+48h+phkResult]; hKey
0x18006965c  mov     ebx, eax
0x18006965e  call    cs:__imp_RegCloseKey
0x180069664  mov     eax, ebx
0x180069666  jmp     short loc_180069671
0x180069668  xor     eax, eax
0x18006966a  jmp     short loc_180069671
0x18006966c  mov     eax, 80004005h
0x180069671  mov     rbx, [rsp+48h+arg_0]
0x180069676  mov     rsi, [rsp+48h+arg_10]
0x18006967b  add     rsp, 40h
0x18006967f  pop     rdi
0x180069680  retn
```
