# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x180005590`
- end: `0x18000578f`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005160`

## callees

- `0x180005590`
- `0x18003e582`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000568a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000568a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180005672`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180005672`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180005651`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180005651`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000575b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000575b`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x180005604`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x180005604`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800056d0`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800056d0`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x18000570f`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x18000570f`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180005769`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18003ea83`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180005769`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18003ea83`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x18000574a`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x18000574a`

## string_xrefs

- `0x18000573b`: `Comctl32.dll`
- `0x180005754`: `Comctl32.dll`

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
0x180005590  push    rbx
0x180005592  sub     rsp, 2F0h
0x180005599  mov     rax, cs:__security_cookie
0x1800055a0  xor     rax, rsp
0x1800055a3  mov     [rsp+2F8h+var_18], rax
0x1800055ab  xorps   xmm0, xmm0
0x1800055ae  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x1800055b3  mov     [rsp+2F8h+Cookie], 0
0x1800055bc  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800055c3  jnz     loc_18000576F
0x1800055c9  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x1800055d1  jnz     loc_18000576F
0x1800055d7  xor     ebx, ebx
0x1800055d9  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x1800055de  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x1800055e7  lea     rax, [rsp+2F8h+hActCtx]
0x1800055ec  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x1800055f1  lea     r9d, [rbx+1]; ulInfoClass
0x1800055f5  xor     r8d, r8d; pvSubInstance
0x1800055f8  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x1800055ff  mov     ecx, 80000010h; dwFlags
0x180005604  call    cs:__imp_QueryActCtxW
0x18000560a  test    eax, eax
0x18000560c  jz      loc_180005774
0x180005612  mov     rax, [rsp+2F8h+hActCtx]
0x180005617  test    rax, rax
0x18000561a  jnz     loc_180005700
0x180005620  xorps   xmm0, xmm0
0x180005623  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x180005628  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x18000562d  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x180005635  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18000563d  mov     [rsp+2F8h+phModule], rax
0x180005642  lea     r8, [rsp+2F8h+phModule]; phModule
0x180005647  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x18000564e  lea     ecx, [rbx+6]; dwFlags
0x180005651  call    cs:__imp_GetModuleHandleExW
0x180005657  test    eax, eax
0x180005659  jz      loc_180005774
0x18000565f  mov     r8d, 105h; nSize
0x180005665  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x18000566d  mov     rcx, [rsp+2F8h+phModule]; hModule
0x180005672  call    cs:__imp_GetModuleFileNameW
0x180005678  test    eax, eax
0x18000567a  jz      loc_180005774
0x180005680  cmp     eax, 105h
0x180005685  jb      short loc_180005695
0x180005687  lea     ecx, [rbx+6Fh]; dwErrCode
0x18000568a  call    cs:__imp_SetLastError
0x180005690  jmp     loc_180005774
0x180005695  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x18000569d  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x1800056a5  lea     rax, [rsp+2F8h+Filename]
0x1800056ad  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x1800056b2  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x1800056be  mov     rax, [rsp+2F8h+phModule]
0x1800056c3  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x1800056cb  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x1800056d0  call    cs:__imp_CreateActCtxW
0x1800056d6  mov     [rsp+2F8h+hActCtx], rax
0x1800056db  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800056df  jnz     short loc_180005700
0x1800056e1  call    cs:__imp_GetLastError
0x1800056e7  lea     ecx, [rax-2]
0x1800056ea  cmp     ecx, 1
0x1800056ed  jbe     short loc_1800056F9
0x1800056ef  add     eax, 0FFFFF8ECh
0x1800056f4  cmp     eax, 3
0x1800056f7  ja      short loc_180005774
0x1800056f9  xor     eax, eax
0x1800056fb  mov     [rsp+2F8h+hActCtx], rax
0x180005700  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x180005707  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x18000570c  mov     rcx, rax; hActCtx
0x18000570f  call    cs:__imp_ActivateActCtx
0x180005715  test    eax, eax
0x180005717  jz      short loc_18000576F
0x180005719  mov     ebx, 70h ; 'p'
0x18000571e  mov     r8d, ebx; Size
0x180005721  xor     edx, edx; Val
0x180005723  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x180005728  call    memset_0
0x18000572d  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x180005731  lea     rax, [rsp+2F8h+pActCtx]
0x180005736  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x18000573b  lea     r9, LibFileName; "Comctl32.dll"
0x180005742  xor     edx, edx; lpExtensionGuid
0x180005744  lea     r8d, [rbx-6Eh]; ulSectionId
0x180005748  xor     ecx, ecx; dwFlags
0x18000574a  call    cs:__imp_FindActCtxSectionStringW
0x180005750  test    eax, eax
0x180005752  jz      short loc_180005762
0x180005754  lea     rcx, LibFileName; "Comctl32.dll"
0x18000575b  call    cs:__imp_LoadLibraryW
0x180005761  nop
0x180005762  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x180005767  xor     ecx, ecx; dwFlags
0x180005769  call    cs:__imp_DeactivateActCtx
0x18000576f  mov     ebx, 1
0x180005774  mov     eax, ebx
0x180005776  mov     rcx, [rsp+2F8h+var_18]
0x18000577e  xor     rcx, rsp; StackCookie
0x180005781  call    __security_check_cookie
0x180005786  add     rsp, 2F0h
0x18000578d  pop     rbx
0x18000578e  retn
0x18003ea74  push    rbp
0x18003ea76  sub     rsp, 40h
0x18003ea7a  mov     rbp, rdx
0x18003ea7d  mov     rdx, [rbp+48h]; ulCookie
0x18003ea81  xor     ecx, ecx; dwFlags
0x18003ea83  call    cs:__imp_DeactivateActCtx
0x18003ea89  nop
0x18003ea8a  add     rsp, 40h
0x18003ea8e  pop     rbp
0x18003ea8f  retn
```
