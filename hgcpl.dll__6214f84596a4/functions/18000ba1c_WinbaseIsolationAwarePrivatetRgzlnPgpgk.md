# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x18000ba1c`
- end: `0x18000bc1b`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b990`

## callees

- `0x18000ba1c`
- `0x180018a52`
- `0x180018a80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000badd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000badd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000bafe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000bafe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb16`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000bbe7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000bbe7`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x18000bbd6`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x18000bbd6`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18000bb5c`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18000bb5c`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x18000bb9b`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x18000bb9b`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x18000ba90`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x18000ba90`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000bbf5`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180018ea5`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000bbf5`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180018ea5`

## string_xrefs

- `0x18000bbc7`: `Comctl32.dll`
- `0x18000bbe0`: `Comctl32.dll`

## pseudocode

```c
__int64 WinbaseIsolationAwarePrivatetRgzlnPgpgk()
{
  unsigned int v0; // ebx
  HANDLE ActCtxW; // rax
  DWORD ModuleFileNameW; // eax
  DWORD LastError; // eax
  HMODULE phModule; // [rsp+40h] [rbp-2B8h] BYREF
  ULONG_PTR Cookie; // [rsp+48h] [rbp-2B0h] BYREF
  HANDLE hActCtx[2]; // [rsp+50h] [rbp-2A8h] BYREF
  struct tagACTCTX_SECTION_KEYED_DATA pActCtx; // [rsp+60h] [rbp-298h] BYREF
  WCHAR Filename[264]; // [rsp+D0h] [rbp-228h] BYREF

  *(_OWORD *)hActCtx = 0;
  Cookie = 0;
  if ( IsolationAwarePrivateT_SqbjaYRiRY || WinbaseIsolationAwarePrivateT_UnPgpgk != (HANDLE)-1LL )
    return 1;
  v0 = 0;
  if ( QueryActCtxW(0x80000010, &WinbaseIsolationAwarePrivateT_UnPgpgk, 0, 1u, hActCtx, 0x10u, 0) )
  {
    ActCtxW = hActCtx[0];
    if ( hActCtx[0] )
      goto LABEL_13;
    memset(&pActCtx, 0, 56);
    phModule = 0;
    if ( GetModuleHandleExW(6u, (LPCWSTR)&WinbaseIsolationAwarePrivateT_UnPgpgk, &phModule) )
    {
      ModuleFileNameW = GetModuleFileNameW(phModule, Filename, 0x105u);
      if ( ModuleFileNameW )
      {
        if ( ModuleFileNameW >= 0x105 )
        {
          SetLastError(0x6Fu);
          return v0;
        }
        pActCtx.cbSize = 56;
        pActCtx.ulDataFormatVersion = 136;
        pActCtx.lpData = Filename;
        *(_QWORD *)&pActCtx.ulSectionGlobalDataLength = 3;
        *(_QWORD *)&pActCtx.ulSectionTotalLength = phModule;
        ActCtxW = CreateActCtxW((PCACTCTXW)&pActCtx);
        hActCtx[0] = ActCtxW;
        if ( ActCtxW != (HANDLE)-1LL )
          goto LABEL_13;
        LastError = GetLastError();
        if ( LastError - 2 <= 1 || LastError - 1812 <= 3 )
        {
          ActCtxW = 0;
          hActCtx[0] = 0;
LABEL_13:
          WinbaseIsolationAwarePrivateT_UnPgpgk = ActCtxW;
          if ( ActivateActCtx(ActCtxW, &Cookie) )
          {
            memset_0(&pActCtx, 0, sizeof(pActCtx));
            pActCtx.cbSize = 112;
            if ( FindActCtxSectionStringW(0, 0, 2u, L"Comctl32.dll", &pActCtx) )
              LoadLibraryW(L"Comctl32.dll");
            DeactivateActCtx(0, Cookie);
          }
          return 1;
        }
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18000ba1c  push    rbx
0x18000ba1e  sub     rsp, 2F0h
0x18000ba25  mov     rax, cs:__security_cookie
0x18000ba2c  xor     rax, rsp
0x18000ba2f  mov     [rsp+2F8h+var_18], rax
0x18000ba37  xorps   xmm0, xmm0
0x18000ba3a  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x18000ba3f  mov     [rsp+2F8h+Cookie], 0
0x18000ba48  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000ba4f  jnz     loc_18000BBFB
0x18000ba55  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x18000ba5d  jnz     loc_18000BBFB
0x18000ba63  xor     ebx, ebx
0x18000ba65  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18000ba6a  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x18000ba73  lea     rax, [rsp+2F8h+hActCtx]
0x18000ba78  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x18000ba7d  lea     r9d, [rbx+1]; ulInfoClass
0x18000ba81  xor     r8d, r8d; pvSubInstance
0x18000ba84  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18000ba8b  mov     ecx, 80000010h; dwFlags
0x18000ba90  call    cs:__imp_QueryActCtxW
0x18000ba96  test    eax, eax
0x18000ba98  jz      loc_18000BC00
0x18000ba9e  mov     rax, [rsp+2F8h+hActCtx]
0x18000baa3  test    rax, rax
0x18000baa6  jnz     loc_18000BB8C
0x18000baac  xorps   xmm0, xmm0
0x18000baaf  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x18000bab4  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x18000bab9  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x18000bac1  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18000bac9  mov     [rsp+2F8h+phModule], rax
0x18000bace  lea     r8, [rsp+2F8h+phModule]; phModule
0x18000bad3  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x18000bada  lea     ecx, [rbx+6]; dwFlags
0x18000badd  call    cs:__imp_GetModuleHandleExW
0x18000bae3  test    eax, eax
0x18000bae5  jz      loc_18000BC00
0x18000baeb  mov     r8d, 105h; nSize
0x18000baf1  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x18000baf9  mov     rcx, [rsp+2F8h+phModule]; hModule
0x18000bafe  call    cs:__imp_GetModuleFileNameW
0x18000bb04  test    eax, eax
0x18000bb06  jz      loc_18000BC00
0x18000bb0c  cmp     eax, 105h
0x18000bb11  jb      short loc_18000BB21
0x18000bb13  lea     ecx, [rbx+6Fh]; dwErrCode
0x18000bb16  call    cs:__imp_SetLastError
0x18000bb1c  jmp     loc_18000BC00
0x18000bb21  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x18000bb29  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x18000bb31  lea     rax, [rsp+2F8h+Filename]
0x18000bb39  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x18000bb3e  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x18000bb4a  mov     rax, [rsp+2F8h+phModule]
0x18000bb4f  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18000bb57  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x18000bb5c  call    cs:__imp_CreateActCtxW
0x18000bb62  mov     [rsp+2F8h+hActCtx], rax
0x18000bb67  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000bb6b  jnz     short loc_18000BB8C
0x18000bb6d  call    cs:__imp_GetLastError
0x18000bb73  lea     ecx, [rax-2]
0x18000bb76  cmp     ecx, 1
0x18000bb79  jbe     short loc_18000BB85
0x18000bb7b  add     eax, 0FFFFF8ECh
0x18000bb80  cmp     eax, 3
0x18000bb83  ja      short loc_18000BC00
0x18000bb85  xor     eax, eax
0x18000bb87  mov     [rsp+2F8h+hActCtx], rax
0x18000bb8c  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x18000bb93  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x18000bb98  mov     rcx, rax; hActCtx
0x18000bb9b  call    cs:__imp_ActivateActCtx
0x18000bba1  test    eax, eax
0x18000bba3  jz      short loc_18000BBFB
0x18000bba5  mov     ebx, 70h ; 'p'
0x18000bbaa  mov     r8d, ebx; Size
0x18000bbad  xor     edx, edx; Val
0x18000bbaf  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x18000bbb4  call    memset_0
0x18000bbb9  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x18000bbbd  lea     rax, [rsp+2F8h+pActCtx]
0x18000bbc2  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x18000bbc7  lea     r9, LibFileName; "Comctl32.dll"
0x18000bbce  xor     edx, edx; lpExtensionGuid
0x18000bbd0  lea     r8d, [rbx-6Eh]; ulSectionId
0x18000bbd4  xor     ecx, ecx; dwFlags
0x18000bbd6  call    cs:__imp_FindActCtxSectionStringW
0x18000bbdc  test    eax, eax
0x18000bbde  jz      short loc_18000BBEE
0x18000bbe0  lea     rcx, LibFileName; "Comctl32.dll"
0x18000bbe7  call    cs:__imp_LoadLibraryW
0x18000bbed  nop
0x18000bbee  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x18000bbf3  xor     ecx, ecx; dwFlags
0x18000bbf5  call    cs:__imp_DeactivateActCtx
0x18000bbfb  mov     ebx, 1
0x18000bc00  mov     eax, ebx
0x18000bc02  mov     rcx, [rsp+2F8h+var_18]
0x18000bc0a  xor     rcx, rsp; StackCookie
0x18000bc0d  call    __security_check_cookie
0x18000bc12  add     rsp, 2F0h
0x18000bc19  pop     rbx
0x18000bc1a  retn
0x180018e96  push    rbp
0x180018e98  sub     rsp, 40h
0x180018e9c  mov     rbp, rdx
0x180018e9f  mov     rdx, [rbp+48h]; ulCookie
0x180018ea3  xor     ecx, ecx; dwFlags
0x180018ea5  call    cs:__imp_DeactivateActCtx
0x180018eab  nop
0x180018eac  add     rsp, 40h
0x180018eb0  pop     rbp
0x180018eb1  retn
```
