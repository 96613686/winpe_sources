# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x180007240`
- end: `0x180007480`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `576`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800071a0`

## callees

- `0x1800015b0`
- `0x180002088`
- `0x180007240`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000732e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000732e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180007307`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180007307`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000734c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000734c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073af`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1800073e7`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1800073e7`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x1800072b4`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x1800072b4`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180007398`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180007398`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180007453`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180019192`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180007453`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180019192`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x180007428`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x180007428`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000743f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000743f`

## string_xrefs

- `0x180007419`: `Comctl32.dll`
- `0x180007438`: `Comctl32.dll`

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
0x180007240  push    rbx
0x180007242  sub     rsp, 2F0h
0x180007249  mov     rax, cs:__security_cookie
0x180007250  xor     rax, rsp
0x180007253  mov     [rsp+2F8h+var_18], rax
0x18000725b  xorps   xmm0, xmm0
0x18000725e  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x180007263  mov     [rsp+2F8h+Cookie], 0
0x18000726c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180007273  jnz     loc_18000745F
0x180007279  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x180007281  jnz     loc_18000745F
0x180007287  xor     ebx, ebx
0x180007289  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18000728e  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x180007297  lea     rax, [rsp+2F8h+hActCtx]
0x18000729c  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x1800072a1  lea     r9d, [rbx+1]; ulInfoClass
0x1800072a5  xor     r8d, r8d; pvSubInstance
0x1800072a8  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x1800072af  mov     ecx, 80000010h; dwFlags
0x1800072b4  call    cs:__imp_QueryActCtxW
0x1800072bb  nop     dword ptr [rax+rax+00h]
0x1800072c0  test    eax, eax
0x1800072c2  jz      loc_180007464
0x1800072c8  mov     rax, [rsp+2F8h+hActCtx]
0x1800072cd  test    rax, rax
0x1800072d0  jnz     loc_1800073D8
0x1800072d6  xorps   xmm0, xmm0
0x1800072d9  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x1800072de  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x1800072e3  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x1800072eb  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x1800072f3  mov     [rsp+2F8h+phModule], rax
0x1800072f8  lea     r8, [rsp+2F8h+phModule]; phModule
0x1800072fd  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x180007304  lea     ecx, [rbx+6]; dwFlags
0x180007307  call    cs:__imp_GetModuleHandleExW
0x18000730e  nop     dword ptr [rax+rax+00h]
0x180007313  test    eax, eax
0x180007315  jz      loc_180007464
0x18000731b  mov     r8d, 105h; nSize
0x180007321  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x180007329  mov     rcx, [rsp+2F8h+phModule]; hModule
0x18000732e  call    cs:__imp_GetModuleFileNameW
0x180007335  nop     dword ptr [rax+rax+00h]
0x18000733a  test    eax, eax
0x18000733c  jz      loc_180007464
0x180007342  cmp     eax, 105h
0x180007347  jb      short loc_18000735D
0x180007349  lea     ecx, [rbx+6Fh]; dwErrCode
0x18000734c  call    cs:__imp_SetLastError
0x180007353  nop     dword ptr [rax+rax+00h]
0x180007358  jmp     loc_180007464
0x18000735d  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x180007365  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x18000736d  lea     rax, [rsp+2F8h+Filename]
0x180007375  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x18000737a  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x180007386  mov     rax, [rsp+2F8h+phModule]
0x18000738b  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180007393  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x180007398  call    cs:__imp_CreateActCtxW
0x18000739f  nop     dword ptr [rax+rax+00h]
0x1800073a4  mov     [rsp+2F8h+hActCtx], rax
0x1800073a9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800073ad  jnz     short loc_1800073D8
0x1800073af  call    cs:__imp_GetLastError
0x1800073b6  nop     dword ptr [rax+rax+00h]
0x1800073bb  lea     ecx, [rax-2]
0x1800073be  cmp     ecx, 1
0x1800073c1  jbe     short loc_1800073D1
0x1800073c3  add     eax, 0FFFFF8ECh
0x1800073c8  cmp     eax, 3
0x1800073cb  ja      loc_180007464
0x1800073d1  xor     eax, eax
0x1800073d3  mov     [rsp+2F8h+hActCtx], rax
0x1800073d8  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x1800073df  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x1800073e4  mov     rcx, rax; hActCtx
0x1800073e7  call    cs:__imp_ActivateActCtx
0x1800073ee  nop     dword ptr [rax+rax+00h]
0x1800073f3  test    eax, eax
0x1800073f5  jz      short loc_18000745F
0x1800073f7  mov     ebx, 70h ; 'p'
0x1800073fc  mov     r8d, ebx; Size
0x1800073ff  xor     edx, edx; Val
0x180007401  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x180007406  call    memset_0
0x18000740b  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x18000740f  lea     rax, [rsp+2F8h+pActCtx]
0x180007414  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x180007419  lea     r9, StringToFind; "Comctl32.dll"
0x180007420  xor     edx, edx; lpExtensionGuid
0x180007422  lea     r8d, [rbx-6Eh]; ulSectionId
0x180007426  xor     ecx, ecx; dwFlags
0x180007428  call    cs:__imp_FindActCtxSectionStringW
0x18000742f  nop     dword ptr [rax+rax+00h]
0x180007434  test    eax, eax
0x180007436  jz      short loc_18000744C
0x180007438  lea     rcx, StringToFind; "Comctl32.dll"
0x18000743f  call    cs:__imp_LoadLibraryW
0x180007446  nop     dword ptr [rax+rax+00h]
0x18000744b  nop
0x18000744c  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x180007451  xor     ecx, ecx; dwFlags
0x180007453  call    cs:__imp_DeactivateActCtx
0x18000745a  nop     dword ptr [rax+rax+00h]
0x18000745f  mov     ebx, 1
0x180007464  mov     eax, ebx
0x180007466  mov     rcx, [rsp+2F8h+var_18]
0x18000746e  xor     rcx, rsp; StackCookie
0x180007471  call    __security_check_cookie
0x180007476  add     rsp, 2F0h
0x18000747d  pop     rbx
0x18000747e  retn
0x180019183  push    rbp
0x180019185  sub     rsp, 40h
0x180019189  mov     rbp, rdx
0x18001918c  mov     rdx, [rbp+48h]; ulCookie
0x180019190  xor     ecx, ecx; dwFlags
0x180019192  call    cs:__imp_DeactivateActCtx
0x180019199  nop     dword ptr [rax+rax+00h]
0x18001919e  nop
0x18001919f  add     rsp, 40h
0x1800191a3  pop     rbp
0x1800191a4  retn
```
