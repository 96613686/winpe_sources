# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x180002b70`
- end: `0x180002d70`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800029e0`

## callees

- `0x180002b70`
- `0x18000ccde`
- `0x18000cd10`

## import_xrefs

- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180002cf0`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180002cf0`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180002d4a`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000d192`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180002d4a`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000d192`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x180002be4`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x180002be4`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180002cb0`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180002cb0`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x180002d2b`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x180002d2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c6a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180002c52`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180002c52`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180002c31`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180002c31`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180002d3c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180002d3c`

## string_xrefs

- `0x180002d1c`: `Comctl32.dll`
- `0x180002d35`: `Comctl32.dll`

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
        if ( LastError - 1812 <= 3 || LastError - 2 <= 1 )
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
0x180002b70  push    rbx
0x180002b72  sub     rsp, 2F0h
0x180002b79  mov     rax, cs:__security_cookie
0x180002b80  xor     rax, rsp
0x180002b83  mov     [rsp+2F8h+var_18], rax
0x180002b8b  xorps   xmm0, xmm0
0x180002b8e  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x180002b93  mov     [rsp+2F8h+Cookie], 0
0x180002b9c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180002ba3  jnz     loc_180002D50
0x180002ba9  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x180002bb1  jnz     loc_180002D50
0x180002bb7  xor     ebx, ebx
0x180002bb9  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x180002bbe  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x180002bc7  lea     rax, [rsp+2F8h+hActCtx]
0x180002bcc  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x180002bd1  lea     r9d, [rbx+1]; ulInfoClass
0x180002bd5  xor     r8d, r8d; pvSubInstance
0x180002bd8  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x180002bdf  mov     ecx, 80000010h; dwFlags
0x180002be4  call    cs:__imp_QueryActCtxW
0x180002bea  test    eax, eax
0x180002bec  jz      loc_180002D55
0x180002bf2  mov     rax, [rsp+2F8h+hActCtx]
0x180002bf7  test    rax, rax
0x180002bfa  jnz     loc_180002CE1
0x180002c00  xorps   xmm0, xmm0
0x180002c03  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x180002c08  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x180002c0d  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x180002c15  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180002c1d  mov     [rsp+2F8h+phModule], rax
0x180002c22  lea     r8, [rsp+2F8h+phModule]; phModule
0x180002c27  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x180002c2e  lea     ecx, [rbx+6]; dwFlags
0x180002c31  call    cs:__imp_GetModuleHandleExW
0x180002c37  test    eax, eax
0x180002c39  jz      loc_180002D55
0x180002c3f  mov     r8d, 105h; nSize
0x180002c45  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x180002c4d  mov     rcx, [rsp+2F8h+phModule]; hModule
0x180002c52  call    cs:__imp_GetModuleFileNameW
0x180002c58  test    eax, eax
0x180002c5a  jz      loc_180002D55
0x180002c60  cmp     eax, 105h
0x180002c65  jb      short loc_180002C75
0x180002c67  lea     ecx, [rbx+6Fh]; dwErrCode
0x180002c6a  call    cs:__imp_SetLastError
0x180002c70  jmp     loc_180002D55
0x180002c75  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x180002c7d  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x180002c85  lea     rax, [rsp+2F8h+Filename]
0x180002c8d  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x180002c92  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x180002c9e  mov     rax, [rsp+2F8h+phModule]
0x180002ca3  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180002cab  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x180002cb0  call    cs:__imp_CreateActCtxW
0x180002cb6  mov     [rsp+2F8h+hActCtx], rax
0x180002cbb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002cbf  jnz     short loc_180002CE1
0x180002cc1  call    cs:__imp_GetLastError
0x180002cc7  lea     ecx, [rax-714h]
0x180002ccd  cmp     ecx, 3
0x180002cd0  jbe     short loc_180002CDA
0x180002cd2  add     eax, 0FFFFFFFEh
0x180002cd5  cmp     eax, 1
0x180002cd8  ja      short loc_180002D55
0x180002cda  xor     eax, eax
0x180002cdc  mov     [rsp+2F8h+hActCtx], rax
0x180002ce1  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x180002ce8  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x180002ced  mov     rcx, rax; hActCtx
0x180002cf0  call    cs:__imp_ActivateActCtx
0x180002cf6  test    eax, eax
0x180002cf8  jz      short loc_180002D50
0x180002cfa  mov     ebx, 70h ; 'p'
0x180002cff  mov     r8d, ebx; Size
0x180002d02  xor     edx, edx; Val
0x180002d04  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x180002d09  call    memset_0
0x180002d0e  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x180002d12  lea     rax, [rsp+2F8h+pActCtx]
0x180002d17  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x180002d1c  lea     r9, LibFileName; "Comctl32.dll"
0x180002d23  xor     edx, edx; lpExtensionGuid
0x180002d25  lea     r8d, [rbx-6Eh]; ulSectionId
0x180002d29  xor     ecx, ecx; dwFlags
0x180002d2b  call    cs:__imp_FindActCtxSectionStringW
0x180002d31  test    eax, eax
0x180002d33  jz      short loc_180002D43
0x180002d35  lea     rcx, LibFileName; "Comctl32.dll"
0x180002d3c  call    cs:__imp_LoadLibraryW
0x180002d42  nop
0x180002d43  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x180002d48  xor     ecx, ecx; dwFlags
0x180002d4a  call    cs:__imp_DeactivateActCtx
0x180002d50  mov     ebx, 1
0x180002d55  mov     eax, ebx
0x180002d57  mov     rcx, [rsp+2F8h+var_18]
0x180002d5f  xor     rcx, rsp; StackCookie
0x180002d62  call    __security_check_cookie
0x180002d67  add     rsp, 2F0h
0x180002d6e  pop     rbx
0x180002d6f  retn
0x18000d183  push    rbp
0x18000d185  sub     rsp, 40h
0x18000d189  mov     rbp, rdx
0x18000d18c  mov     rdx, [rbp+48h]; ulCookie
0x18000d190  xor     ecx, ecx; dwFlags
0x18000d192  call    cs:__imp_DeactivateActCtx
0x18000d198  nop
0x18000d199  add     rsp, 40h
0x18000d19d  pop     rbp
0x18000d19e  retn
```
