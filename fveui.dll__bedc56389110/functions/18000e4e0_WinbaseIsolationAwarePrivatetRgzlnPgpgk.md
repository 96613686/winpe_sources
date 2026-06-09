# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x18000e4e0`
- end: `0x18000e6df`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e1e8`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x18000e4e0`

## import_xrefs

- `KERNEL32!QueryActCtxW` at `0x18000e554`
- `KERNEL32!QueryActCtxW` at `0x18000e554`
- `KERNEL32!CreateActCtxW` at `0x18000e620`
- `KERNEL32!CreateActCtxW` at `0x18000e620`
- `KERNEL32!FindActCtxSectionStringW` at `0x18000e69a`
- `KERNEL32!FindActCtxSectionStringW` at `0x18000e69a`
- `KERNEL32!LoadLibraryW` at `0x18000e6ab`
- `KERNEL32!LoadLibraryW` at `0x18000e6ab`
- `KERNEL32!ActivateActCtx` at `0x18000e65f`
- `KERNEL32!ActivateActCtx` at `0x18000e65f`
- `KERNEL32!DeactivateActCtx` at `0x18000e6b9`
- `KERNEL32!DeactivateActCtx` at `0x18002c782`
- `KERNEL32!DeactivateActCtx` at `0x18000e6b9`
- `KERNEL32!DeactivateActCtx` at `0x18002c782`
- `KERNEL32!SetLastError` at `0x18000e5da`
- `KERNEL32!SetLastError` at `0x18000e5da`
- `KERNEL32!GetModuleHandleExW` at `0x18000e5a1`
- `KERNEL32!GetModuleHandleExW` at `0x18000e5a1`
- `KERNEL32!GetLastError` at `0x18000e631`
- `KERNEL32!GetLastError` at `0x18000e631`
- `KERNEL32!GetModuleFileNameW` at `0x18000e5c2`
- `KERNEL32!GetModuleFileNameW` at `0x18000e5c2`

## string_xrefs

- `0x18000e68b`: `Comctl32.dll`
- `0x18000e6a4`: `Comctl32.dll`

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
0x18000e4e0  push    rbx
0x18000e4e2  sub     rsp, 2F0h
0x18000e4e9  mov     rax, cs:__security_cookie
0x18000e4f0  xor     rax, rsp
0x18000e4f3  mov     [rsp+2F8h+var_18], rax
0x18000e4fb  xorps   xmm0, xmm0
0x18000e4fe  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x18000e503  mov     [rsp+2F8h+Cookie], 0
0x18000e50c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000e513  jnz     loc_18000E6BF
0x18000e519  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x18000e521  jnz     loc_18000E6BF
0x18000e527  xor     ebx, ebx
0x18000e529  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18000e52e  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x18000e537  lea     rax, [rsp+2F8h+hActCtx]
0x18000e53c  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x18000e541  lea     r9d, [rbx+1]; ulInfoClass
0x18000e545  xor     r8d, r8d; pvSubInstance
0x18000e548  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18000e54f  mov     ecx, 80000010h; dwFlags
0x18000e554  call    cs:__imp_QueryActCtxW
0x18000e55a  test    eax, eax
0x18000e55c  jz      loc_18000E6C4
0x18000e562  mov     rax, [rsp+2F8h+hActCtx]
0x18000e567  test    rax, rax
0x18000e56a  jnz     loc_18000E650
0x18000e570  xorps   xmm0, xmm0
0x18000e573  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x18000e578  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x18000e57d  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x18000e585  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18000e58d  mov     [rsp+2F8h+phModule], rax
0x18000e592  lea     r8, [rsp+2F8h+phModule]; phModule
0x18000e597  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x18000e59e  lea     ecx, [rbx+6]; dwFlags
0x18000e5a1  call    cs:__imp_GetModuleHandleExW
0x18000e5a7  test    eax, eax
0x18000e5a9  jz      loc_18000E6C4
0x18000e5af  mov     r8d, 105h; nSize
0x18000e5b5  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x18000e5bd  mov     rcx, [rsp+2F8h+phModule]; hModule
0x18000e5c2  call    cs:__imp_GetModuleFileNameW
0x18000e5c8  test    eax, eax
0x18000e5ca  jz      loc_18000E6C4
0x18000e5d0  cmp     eax, 105h
0x18000e5d5  jb      short loc_18000E5E5
0x18000e5d7  lea     ecx, [rbx+6Fh]; dwErrCode
0x18000e5da  call    cs:__imp_SetLastError
0x18000e5e0  jmp     loc_18000E6C4
0x18000e5e5  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x18000e5ed  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x18000e5f5  lea     rax, [rsp+2F8h+Filename]
0x18000e5fd  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x18000e602  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x18000e60e  mov     rax, [rsp+2F8h+phModule]
0x18000e613  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18000e61b  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x18000e620  call    cs:__imp_CreateActCtxW
0x18000e626  mov     [rsp+2F8h+hActCtx], rax
0x18000e62b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e62f  jnz     short loc_18000E650
0x18000e631  call    cs:__imp_GetLastError
0x18000e637  lea     ecx, [rax-2]
0x18000e63a  cmp     ecx, 1
0x18000e63d  jbe     short loc_18000E649
0x18000e63f  add     eax, 0FFFFF8ECh
0x18000e644  cmp     eax, 3
0x18000e647  ja      short loc_18000E6C4
0x18000e649  xor     eax, eax
0x18000e64b  mov     [rsp+2F8h+hActCtx], rax
0x18000e650  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x18000e657  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x18000e65c  mov     rcx, rax; hActCtx
0x18000e65f  call    cs:__imp_ActivateActCtx
0x18000e665  test    eax, eax
0x18000e667  jz      short loc_18000E6BF
0x18000e669  mov     ebx, 70h ; 'p'
0x18000e66e  mov     r8d, ebx; Size
0x18000e671  xor     edx, edx; Val
0x18000e673  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x18000e678  call    memset_0
0x18000e67d  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x18000e681  lea     rax, [rsp+2F8h+pActCtx]
0x18000e686  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x18000e68b  lea     r9, StringToFind; "Comctl32.dll"
0x18000e692  xor     edx, edx; lpExtensionGuid
0x18000e694  lea     r8d, [rbx-6Eh]; ulSectionId
0x18000e698  xor     ecx, ecx; dwFlags
0x18000e69a  call    cs:__imp_FindActCtxSectionStringW
0x18000e6a0  test    eax, eax
0x18000e6a2  jz      short loc_18000E6B2
0x18000e6a4  lea     rcx, StringToFind; "Comctl32.dll"
0x18000e6ab  call    cs:__imp_LoadLibraryW
0x18000e6b1  nop
0x18000e6b2  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x18000e6b7  xor     ecx, ecx; dwFlags
0x18000e6b9  call    cs:__imp_DeactivateActCtx
0x18000e6bf  mov     ebx, 1
0x18000e6c4  mov     eax, ebx
0x18000e6c6  mov     rcx, [rsp+2F8h+var_18]
0x18000e6ce  xor     rcx, rsp; StackCookie
0x18000e6d1  call    __security_check_cookie
0x18000e6d6  add     rsp, 2F0h
0x18000e6dd  pop     rbx
0x18000e6de  retn
0x18002c773  push    rbp
0x18002c775  sub     rsp, 40h
0x18002c779  mov     rbp, rdx
0x18002c77c  mov     rdx, [rbp+48h]; ulCookie
0x18002c780  xor     ecx, ecx; dwFlags
0x18002c782  call    cs:__imp_DeactivateActCtx
0x18002c788  nop
0x18002c789  add     rsp, 40h
0x18002c78d  pop     rbp
0x18002c78e  retn
```
