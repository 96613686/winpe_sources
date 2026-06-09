# CheckIfOfficeIsCallingMsdrmWithWHR(void)

- ea: `0x1800193e4`
- end: `0x18001959c`
- name: `?CheckIfOfficeIsCallingMsdrmWithWHR@@YA_NXZ`
- size: `440`
- prototype: `bool __fastcall(HKEY)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001991c`

## callees

- `0x180001244`
- `0x180001284`
- `0x1800046c8`
- `0x1800193e4`
- `0x180019eac`
- `0x180039970`
- `0x18005bdc0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800194ce`
- `msvcrt!wcscpy_s` at `0x1800194ce`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001947a`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001947a`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x180019454`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x180019454`

## string_xrefs

- `0x180019556`: `[msdrm]:IsProcessNameInRegistry %S reg key not found\n`
- `0x1800194f8`: `[msdrm]: GetProcessName. Error. GetFullPathNameW returned %d and fileName %S\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall CheckIfOfficeIsCallingMsdrmWithWHR(HKEY a1)
{
  bool v1; // si
  wchar_t *v2; // rbx
  DWORD FullPathNameW; // eax
  __int64 v4; // rax
  rsize_t v5; // rdi
  wchar_t *v6; // rax
  HKEY v7; // rcx
  const wchar_t *v8; // r8
  int RegistryKey; // eax
  void *v10; // rdi
  LPWSTR FilePart; // [rsp+20h] [rbp-E0h] BYREF
  void *Block; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v14; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Filename[520]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[520]; // [rsp+450h] [rbp+350h] BYREF

  v14 = 0;
  v1 = 0;
  v2 = 0;
  if ( GetRegistryKey(a1, L"SOFTWARE\\Microsoft\\MSDRM\\Federation", L"FederationHomeRealm", &v14) < 0 )
    goto LABEL_18;
  _RTLTRACE("[msdrm]: Entered GetProcessName\n");
  if ( !GetModuleFileNameW(0, Filename, 0x208u) )
  {
    _RTLTRACE("[msdrm]: GetProcessName: GetModuleFileNameW call error, returned length %d\n", 0);
    goto LABEL_13;
  }
  FilePart = 0;
  FullPathNameW = GetFullPathNameW(Filename, 0x208u, Buffer, &FilePart);
  if ( FullPathNameW )
  {
    if ( FilePart )
    {
      v4 = -1;
      do
        ++v4;
      while ( FilePart[v4] );
      v5 = v4 + 1;
      v6 = (wchar_t *)operator new(saturated_mul(v4 + 1, 2u));
      v2 = v6;
      if ( !v6 )
        goto LABEL_18;
      wcscpy_s(v6, v5, FilePart);
      _RTLTRACE("[msdrm]: GetProcessName will return %S\n", v2);
      goto LABEL_13;
    }
    goto LABEL_10;
  }
  v8 = FilePart;
  if ( !FilePart )
LABEL_10:
    v8 = L"NULL";
  _RTLTRACE("[msdrm]: GetProcessName. Error. GetFullPathNameW returned %d and fileName %S\n", FullPathNameW, v8);
LABEL_13:
  Block = 0;
  RegistryKey = GetRegistryKey(v7, L"SOFTWARE\\Microsoft\\MSDRM\\AppList", L"AppList", (unsigned __int16 **)&Block);
  v10 = Block;
  if ( RegistryKey < 0 )
  {
    _RTLTRACE("[msdrm]:IsProcessNameInRegistry %S reg key not found\n", L"AppList");
  }
  else if ( Block )
  {
    v1 = IsProcessNameInString(v2, (wchar_t *)Block);
  }
  operator delete(v10);
LABEL_18:
  operator delete(v14);
  operator delete(v2);
  return v1;
}

```

## disassembly

```asm
0x1800193e4  push    rbp
0x1800193e6  push    rbx
0x1800193e7  push    rsi
0x1800193e8  push    rdi
0x1800193e9  push    r14
0x1800193eb  lea     rbp, [rsp-770h]
0x1800193f3  sub     rsp, 870h
0x1800193fa  mov     rax, cs:__security_cookie
0x180019401  xor     rax, rsp
0x180019404  mov     [rbp+790h+var_30], rax
0x18001940b  xor     r14d, r14d
0x18001940e  lea     r9, [rsp+890h+var_860]; unsigned __int16 **
0x180019413  lea     r8, ?g_wszFederationHomeRealmKey@@3QBGB; "FederationHomeRealm"
0x18001941a  mov     [rsp+890h+var_860], r14
0x18001941f  lea     rdx, ?g_wszMSDRMFederationKey@@3QBGB; "SOFTWARE\\Microsoft\\MSDRM\\Federation"
0x180019426  mov     sil, r14b
0x180019429  call    ?GetRegistryKey@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; GetRegistryKey(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x18001942e  mov     ebx, r14d
0x180019431  test    eax, eax
0x180019433  js      loc_18001956A
0x180019439  lea     rcx, aMsdrmEnteredGe; "[msdrm]: Entered GetProcessName\n"
0x180019440  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180019445  mov     edi, 208h
0x18001944a  lea     rdx, [rsp+890h+Filename]; lpFilename
0x18001944f  mov     r8d, edi; nSize
0x180019452  xor     ecx, ecx; hModule
0x180019454  call    cs:__imp_GetModuleFileNameW
0x18001945a  test    eax, eax
0x18001945c  jz      loc_180019506
0x180019462  lea     r9, [rsp+890h+FilePart]; lpFilePart
0x180019467  mov     [rsp+890h+FilePart], r14
0x18001946c  lea     r8, [rbp+790h+Buffer]; lpBuffer
0x180019473  mov     edx, edi; nBufferLength
0x180019475  lea     rcx, [rsp+890h+Filename]; lpFileName
0x18001947a  call    cs:__imp_GetFullPathNameW
0x180019480  test    eax, eax
0x180019482  jz      short loc_1800194E5
0x180019484  mov     rcx, [rsp+890h+FilePart]
0x180019489  test    rcx, rcx
0x18001948c  jz      short loc_1800194EF
0x18001948e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180019492  mov     rax, r8
0x180019495  inc     rax
0x180019498  cmp     [rcx+rax*2], r14w
0x18001949d  jnz     short loc_180019495
0x18001949f  lea     rdi, [rax+1]
0x1800194a3  mov     eax, 2
0x1800194a8  mul     rdi
0x1800194ab  cmovb   rax, r8
0x1800194af  mov     rcx, rax; Size
0x1800194b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800194b7  mov     rbx, rax
0x1800194ba  test    rax, rax
0x1800194bd  jz      loc_18001956A
0x1800194c3  mov     r8, [rsp+890h+FilePart]; Source
0x1800194c8  mov     rdx, rdi; SizeInWords
0x1800194cb  mov     rcx, rax; Destination
0x1800194ce  call    cs:__imp_wcscpy_s
0x1800194d4  mov     rdx, rbx
0x1800194d7  lea     rcx, aMsdrmGetproces; "[msdrm]: GetProcessName will return %S"...
0x1800194de  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x1800194e3  jmp     short loc_180019514
0x1800194e5  mov     r8, [rsp+890h+FilePart]
0x1800194ea  test    r8, r8
0x1800194ed  jnz     short loc_1800194F6
0x1800194ef  lea     r8, aNull; "NULL"
0x1800194f6  mov     edx, eax
0x1800194f8  lea     rcx, aMsdrmGetproces_0; "[msdrm]: GetProcessName. Error. GetFull"...
0x1800194ff  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180019504  jmp     short loc_180019514
0x180019506  mov     edx, eax
0x180019508  lea     rcx, aMsdrmGetproces_1; "[msdrm]: GetProcessName: GetModuleFileN"...
0x18001950f  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180019514  lea     r9, [rsp+890h+Block]; unsigned __int16 **
0x180019519  mov     [rsp+890h+Block], r14
0x18001951e  lea     r8, aApplist; "AppList"
0x180019525  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\MSDRM\\AppList"
0x18001952c  call    ?GetRegistryKey@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; GetRegistryKey(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180019531  mov     rdi, [rsp+890h+Block]
0x180019536  test    eax, eax
0x180019538  js      short loc_18001954F
0x18001953a  test    rdi, rdi
0x18001953d  jz      short loc_180019562
0x18001953f  mov     rdx, rdi; wchar_t *
0x180019542  mov     rcx, rbx; Source
0x180019545  call    ?IsProcessNameInString@@YA_NPEBG0@Z; IsProcessNameInString(ushort const *,ushort const *)
0x18001954a  mov     sil, al
0x18001954d  jmp     short loc_180019562
0x18001954f  lea     rdx, aApplist; "AppList"
0x180019556  lea     rcx, aMsdrmIsprocess; "[msdrm]:IsProcessNameInRegistry %S reg "...
0x18001955d  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180019562  mov     rcx, rdi; Block
0x180019565  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001956a  mov     rcx, [rsp+890h+var_860]; Block
0x18001956f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019574  mov     rcx, rbx; Block
0x180019577  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001957c  mov     al, sil
0x18001957f  mov     rcx, [rbp+790h+var_30]
0x180019586  xor     rcx, rsp; StackCookie
0x180019589  call    __security_check_cookie
0x18001958e  add     rsp, 870h
0x180019595  pop     r14
0x180019597  pop     rdi
0x180019598  pop     rsi
0x180019599  pop     rbx
0x18001959a  pop     rbp
0x18001959b  retn
```
