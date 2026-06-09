# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x14000c288`
- end: `0x14000c487`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000b7d0`
- `0x14000c084`
- `0x14000c1fc`

## callees

- `0x14000c288`
- `0x140062455`
- `0x1400e9e10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14000c36a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14000c36a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x14000c349`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x14000c349`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c382`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c3d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c3d9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14000c453`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14000c453`
- `KERNEL32!DeactivateActCtx` at `0x14000c461`
- `KERNEL32!DeactivateActCtx` at `0x1400ea3f7`
- `KERNEL32!DeactivateActCtx` at `0x14000c461`
- `KERNEL32!DeactivateActCtx` at `0x1400ea3f7`
- `KERNEL32!ActivateActCtx` at `0x14000c407`
- `KERNEL32!ActivateActCtx` at `0x14000c407`
- `KERNEL32!FindActCtxSectionStringW` at `0x14000c442`
- `KERNEL32!FindActCtxSectionStringW` at `0x14000c442`
- `KERNEL32!CreateActCtxW` at `0x14000c3c8`
- `KERNEL32!CreateActCtxW` at `0x14000c3c8`
- `KERNEL32!QueryActCtxW` at `0x14000c2fc`
- `KERNEL32!QueryActCtxW` at `0x14000c2fc`

## string_xrefs

- `0x14000c433`: `Comctl32.dll`
- `0x14000c44c`: `Comctl32.dll`

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
  if ( WinbaseIsolationAwarePrivateT_UnPgpgk != (HANDLE)-1LL || IsolationAwarePrivateT_SqbjaYRiRY )
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
0x14000c288  push    rbx
0x14000c28a  sub     rsp, 2F0h
0x14000c291  mov     rax, cs:__security_cookie
0x14000c298  xor     rax, rsp
0x14000c29b  mov     [rsp+2F8h+var_18], rax
0x14000c2a3  xorps   xmm0, xmm0
0x14000c2a6  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x14000c2ab  mov     [rsp+2F8h+Cookie], 0
0x14000c2b4  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x14000c2bc  jnz     loc_14000C467
0x14000c2c2  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x14000c2c9  jnz     loc_14000C467
0x14000c2cf  xor     ebx, ebx
0x14000c2d1  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x14000c2d6  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x14000c2df  lea     rax, [rsp+2F8h+hActCtx]
0x14000c2e4  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x14000c2e9  lea     r9d, [rbx+1]; ulInfoClass
0x14000c2ed  xor     r8d, r8d; pvSubInstance
0x14000c2f0  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x14000c2f7  mov     ecx, 80000010h; dwFlags
0x14000c2fc  call    cs:__imp_QueryActCtxW
0x14000c302  test    eax, eax
0x14000c304  jz      loc_14000C46C
0x14000c30a  mov     rax, [rsp+2F8h+hActCtx]
0x14000c30f  test    rax, rax
0x14000c312  jnz     loc_14000C3F8
0x14000c318  xorps   xmm0, xmm0
0x14000c31b  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x14000c320  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x14000c325  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x14000c32d  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x14000c335  mov     [rsp+2F8h+phModule], rax
0x14000c33a  lea     r8, [rsp+2F8h+phModule]; phModule
0x14000c33f  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x14000c346  lea     ecx, [rbx+6]; dwFlags
0x14000c349  call    cs:__imp_GetModuleHandleExW
0x14000c34f  test    eax, eax
0x14000c351  jz      loc_14000C46C
0x14000c357  mov     r8d, 105h; nSize
0x14000c35d  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x14000c365  mov     rcx, [rsp+2F8h+phModule]; hModule
0x14000c36a  call    cs:__imp_GetModuleFileNameW
0x14000c370  test    eax, eax
0x14000c372  jz      loc_14000C46C
0x14000c378  cmp     eax, 105h
0x14000c37d  jb      short loc_14000C38D
0x14000c37f  lea     ecx, [rbx+6Fh]; dwErrCode
0x14000c382  call    cs:__imp_SetLastError
0x14000c388  jmp     loc_14000C46C
0x14000c38d  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x14000c395  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x14000c39d  lea     rax, [rsp+2F8h+Filename]
0x14000c3a5  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x14000c3aa  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x14000c3b6  mov     rax, [rsp+2F8h+phModule]
0x14000c3bb  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x14000c3c3  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x14000c3c8  call    cs:__imp_CreateActCtxW
0x14000c3ce  mov     [rsp+2F8h+hActCtx], rax
0x14000c3d3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000c3d7  jnz     short loc_14000C3F8
0x14000c3d9  call    cs:__imp_GetLastError
0x14000c3df  lea     ecx, [rax-2]
0x14000c3e2  cmp     ecx, 1
0x14000c3e5  jbe     short loc_14000C3F1
0x14000c3e7  add     eax, 0FFFFF8ECh
0x14000c3ec  cmp     eax, 3
0x14000c3ef  ja      short loc_14000C46C
0x14000c3f1  xor     eax, eax
0x14000c3f3  mov     [rsp+2F8h+hActCtx], rax
0x14000c3f8  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x14000c3ff  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x14000c404  mov     rcx, rax; hActCtx
0x14000c407  call    cs:__imp_ActivateActCtx
0x14000c40d  test    eax, eax
0x14000c40f  jz      short loc_14000C467
0x14000c411  mov     ebx, 70h ; 'p'
0x14000c416  mov     r8d, ebx; Size
0x14000c419  xor     edx, edx; Val
0x14000c41b  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x14000c420  call    memset_0
0x14000c425  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x14000c429  lea     rax, [rsp+2F8h+pActCtx]
0x14000c42e  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x14000c433  lea     r9, LibFileName; "Comctl32.dll"
0x14000c43a  xor     edx, edx; lpExtensionGuid
0x14000c43c  lea     r8d, [rbx-6Eh]; ulSectionId
0x14000c440  xor     ecx, ecx; dwFlags
0x14000c442  call    cs:__imp_FindActCtxSectionStringW
0x14000c448  test    eax, eax
0x14000c44a  jz      short loc_14000C45A
0x14000c44c  lea     rcx, LibFileName; "Comctl32.dll"
0x14000c453  call    cs:__imp_LoadLibraryW
0x14000c459  nop
0x14000c45a  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x14000c45f  xor     ecx, ecx; dwFlags
0x14000c461  call    cs:__imp_DeactivateActCtx
0x14000c467  mov     ebx, 1
0x14000c46c  mov     eax, ebx
0x14000c46e  mov     rcx, [rsp+2F8h+var_18]
0x14000c476  xor     rcx, rsp; StackCookie
0x14000c479  call    __security_check_cookie
0x14000c47e  add     rsp, 2F0h
0x14000c485  pop     rbx
0x14000c486  retn
0x1400ea3e8  push    rbp
0x1400ea3ea  sub     rsp, 40h
0x1400ea3ee  mov     rbp, rdx
0x1400ea3f1  mov     rdx, [rbp+48h]; ulCookie
0x1400ea3f5  xor     ecx, ecx; dwFlags
0x1400ea3f7  call    cs:__imp_DeactivateActCtx
0x1400ea3fd  nop
0x1400ea3fe  add     rsp, 40h
0x1400ea402  pop     rbp
0x1400ea403  retn
```
