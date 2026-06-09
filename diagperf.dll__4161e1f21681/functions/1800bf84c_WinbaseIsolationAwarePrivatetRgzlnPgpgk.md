# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x1800bf84c`
- end: `0x1800bfa4b`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800bf6f0`

## callees

- `0x1800bf84c`
- `0x1800cf032`
- `0x1800cf080`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf99d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf99d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bf946`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bf946`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800bf90d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800bf90d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800bf92e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800bf92e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800bfa17`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800bfa17`
- `KERNEL32!QueryActCtxW` at `0x1800bf8c0`
- `KERNEL32!QueryActCtxW` at `0x1800bf8c0`
- `KERNEL32!CreateActCtxW` at `0x1800bf98c`
- `KERNEL32!CreateActCtxW` at `0x1800bf98c`
- `KERNEL32!FindActCtxSectionStringW` at `0x1800bfa06`
- `KERNEL32!FindActCtxSectionStringW` at `0x1800bfa06`
- `KERNEL32!ActivateActCtx` at `0x1800bf9cb`
- `KERNEL32!ActivateActCtx` at `0x1800bf9cb`
- `KERNEL32!DeactivateActCtx` at `0x1800bfa25`
- `KERNEL32!DeactivateActCtx` at `0x1800d53fb`
- `KERNEL32!DeactivateActCtx` at `0x1800bfa25`
- `KERNEL32!DeactivateActCtx` at `0x1800d53fb`

## string_xrefs

- `0x1800bf9f7`: `Comctl32.dll`
- `0x1800bfa10`: `Comctl32.dll`

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
0x1800bf84c  push    rbx
0x1800bf84e  sub     rsp, 2F0h
0x1800bf855  mov     rax, cs:__security_cookie
0x1800bf85c  xor     rax, rsp
0x1800bf85f  mov     [rsp+2F8h+var_18], rax
0x1800bf867  xorps   xmm0, xmm0
0x1800bf86a  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x1800bf86f  mov     [rsp+2F8h+Cookie], 0
0x1800bf878  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800bf87f  jnz     loc_1800BFA2B
0x1800bf885  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x1800bf88d  jnz     loc_1800BFA2B
0x1800bf893  xor     ebx, ebx
0x1800bf895  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x1800bf89a  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x1800bf8a3  lea     rax, [rsp+2F8h+hActCtx]
0x1800bf8a8  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x1800bf8ad  lea     r9d, [rbx+1]; ulInfoClass
0x1800bf8b1  xor     r8d, r8d; pvSubInstance
0x1800bf8b4  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x1800bf8bb  mov     ecx, 80000010h; dwFlags
0x1800bf8c0  call    cs:__imp_QueryActCtxW
0x1800bf8c6  test    eax, eax
0x1800bf8c8  jz      loc_1800BFA30
0x1800bf8ce  mov     rax, [rsp+2F8h+hActCtx]
0x1800bf8d3  test    rax, rax
0x1800bf8d6  jnz     loc_1800BF9BC
0x1800bf8dc  xorps   xmm0, xmm0
0x1800bf8df  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x1800bf8e4  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x1800bf8e9  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x1800bf8f1  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x1800bf8f9  mov     [rsp+2F8h+phModule], rax
0x1800bf8fe  lea     r8, [rsp+2F8h+phModule]; phModule
0x1800bf903  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x1800bf90a  lea     ecx, [rbx+6]; dwFlags
0x1800bf90d  call    cs:__imp_GetModuleHandleExW
0x1800bf913  test    eax, eax
0x1800bf915  jz      loc_1800BFA30
0x1800bf91b  mov     r8d, 105h; nSize
0x1800bf921  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x1800bf929  mov     rcx, [rsp+2F8h+phModule]; hModule
0x1800bf92e  call    cs:__imp_GetModuleFileNameW
0x1800bf934  test    eax, eax
0x1800bf936  jz      loc_1800BFA30
0x1800bf93c  cmp     eax, 105h
0x1800bf941  jb      short loc_1800BF951
0x1800bf943  lea     ecx, [rbx+6Fh]; dwErrCode
0x1800bf946  call    cs:__imp_SetLastError
0x1800bf94c  jmp     loc_1800BFA30
0x1800bf951  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x1800bf959  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x1800bf961  lea     rax, [rsp+2F8h+Filename]
0x1800bf969  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x1800bf96e  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x1800bf97a  mov     rax, [rsp+2F8h+phModule]
0x1800bf97f  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x1800bf987  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x1800bf98c  call    cs:__imp_CreateActCtxW
0x1800bf992  mov     [rsp+2F8h+hActCtx], rax
0x1800bf997  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bf99b  jnz     short loc_1800BF9BC
0x1800bf99d  call    cs:__imp_GetLastError
0x1800bf9a3  lea     ecx, [rax-2]
0x1800bf9a6  cmp     ecx, 1
0x1800bf9a9  jbe     short loc_1800BF9B5
0x1800bf9ab  add     eax, 0FFFFF8ECh
0x1800bf9b0  cmp     eax, 3
0x1800bf9b3  ja      short loc_1800BFA30
0x1800bf9b5  xor     eax, eax
0x1800bf9b7  mov     [rsp+2F8h+hActCtx], rax
0x1800bf9bc  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x1800bf9c3  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x1800bf9c8  mov     rcx, rax; hActCtx
0x1800bf9cb  call    cs:__imp_ActivateActCtx
0x1800bf9d1  test    eax, eax
0x1800bf9d3  jz      short loc_1800BFA2B
0x1800bf9d5  mov     ebx, 70h ; 'p'
0x1800bf9da  mov     r8d, ebx; Size
0x1800bf9dd  xor     edx, edx; Val
0x1800bf9df  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x1800bf9e4  call    memset_0
0x1800bf9e9  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x1800bf9ed  lea     rax, [rsp+2F8h+pActCtx]
0x1800bf9f2  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x1800bf9f7  lea     r9, LibFileName; "Comctl32.dll"
0x1800bf9fe  xor     edx, edx; lpExtensionGuid
0x1800bfa00  lea     r8d, [rbx-6Eh]; ulSectionId
0x1800bfa04  xor     ecx, ecx; dwFlags
0x1800bfa06  call    cs:__imp_FindActCtxSectionStringW
0x1800bfa0c  test    eax, eax
0x1800bfa0e  jz      short loc_1800BFA1E
0x1800bfa10  lea     rcx, LibFileName; "Comctl32.dll"
0x1800bfa17  call    cs:__imp_LoadLibraryW
0x1800bfa1d  nop
0x1800bfa1e  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x1800bfa23  xor     ecx, ecx; dwFlags
0x1800bfa25  call    cs:__imp_DeactivateActCtx
0x1800bfa2b  mov     ebx, 1
0x1800bfa30  mov     eax, ebx
0x1800bfa32  mov     rcx, [rsp+2F8h+var_18]
0x1800bfa3a  xor     rcx, rsp; StackCookie
0x1800bfa3d  call    __security_check_cookie
0x1800bfa42  add     rsp, 2F0h
0x1800bfa49  pop     rbx
0x1800bfa4a  retn
0x1800d53ec  push    rbp
0x1800d53ee  sub     rsp, 40h
0x1800d53f2  mov     rbp, rdx
0x1800d53f5  mov     rdx, [rbp+48h]; ulCookie
0x1800d53f9  xor     ecx, ecx; dwFlags
0x1800d53fb  call    cs:__imp_DeactivateActCtx
0x1800d5401  nop
0x1800d5402  add     rsp, 40h
0x1800d5406  pop     rbp
0x1800d5407  retn
```
