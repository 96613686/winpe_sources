# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x18002da00`
- end: `0x18002dc00`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002d87c`

## callees

- `0x18002da00`
- `0x18005bd72`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dafa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dafa`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18002dac1`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18002dac1`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18002dae2`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18002dae2`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x18002dbbb`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x18002dbbb`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18002db40`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18002db40`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18002dbda`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18005cfe5`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18002dbda`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18005cfe5`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x18002db80`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x18002db80`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x18002da74`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x18002da74`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18002dbcc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18002dbcc`

## string_xrefs

- `0x18002dbac`: `Comctl32.dll`
- `0x18002dbc5`: `Comctl32.dll`

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
0x18002da00  push    rbx
0x18002da02  sub     rsp, 2F0h
0x18002da09  mov     rax, cs:__security_cookie
0x18002da10  xor     rax, rsp
0x18002da13  mov     [rsp+2F8h+var_18], rax
0x18002da1b  xorps   xmm0, xmm0
0x18002da1e  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x18002da23  mov     [rsp+2F8h+Cookie], 0
0x18002da2c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002da33  jnz     loc_18002DBE0
0x18002da39  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x18002da41  jnz     loc_18002DBE0
0x18002da47  xor     ebx, ebx
0x18002da49  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18002da4e  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x18002da57  lea     rax, [rsp+2F8h+hActCtx]
0x18002da5c  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x18002da61  lea     r9d, [rbx+1]; ulInfoClass
0x18002da65  xor     r8d, r8d; pvSubInstance
0x18002da68  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18002da6f  mov     ecx, 80000010h; dwFlags
0x18002da74  call    cs:__imp_QueryActCtxW
0x18002da7a  test    eax, eax
0x18002da7c  jz      loc_18002DBE5
0x18002da82  mov     rax, [rsp+2F8h+hActCtx]
0x18002da87  test    rax, rax
0x18002da8a  jnz     loc_18002DB71
0x18002da90  xorps   xmm0, xmm0
0x18002da93  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x18002da98  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x18002da9d  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x18002daa5  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18002daad  mov     [rsp+2F8h+phModule], rax
0x18002dab2  lea     r8, [rsp+2F8h+phModule]; phModule
0x18002dab7  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x18002dabe  lea     ecx, [rbx+6]; dwFlags
0x18002dac1  call    cs:__imp_GetModuleHandleExW
0x18002dac7  test    eax, eax
0x18002dac9  jz      loc_18002DBE5
0x18002dacf  mov     r8d, 105h; nSize
0x18002dad5  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x18002dadd  mov     rcx, [rsp+2F8h+phModule]; hModule
0x18002dae2  call    cs:__imp_GetModuleFileNameW
0x18002dae8  test    eax, eax
0x18002daea  jz      loc_18002DBE5
0x18002daf0  cmp     eax, 105h
0x18002daf5  jb      short loc_18002DB05
0x18002daf7  lea     ecx, [rbx+6Fh]; dwErrCode
0x18002dafa  call    cs:__imp_SetLastError
0x18002db00  jmp     loc_18002DBE5
0x18002db05  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x18002db0d  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x18002db15  lea     rax, [rsp+2F8h+Filename]
0x18002db1d  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x18002db22  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x18002db2e  mov     rax, [rsp+2F8h+phModule]
0x18002db33  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18002db3b  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x18002db40  call    cs:__imp_CreateActCtxW
0x18002db46  mov     [rsp+2F8h+hActCtx], rax
0x18002db4b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002db4f  jnz     short loc_18002DB71
0x18002db51  call    cs:__imp_GetLastError
0x18002db57  lea     ecx, [rax-714h]
0x18002db5d  cmp     ecx, 3
0x18002db60  jbe     short loc_18002DB6A
0x18002db62  add     eax, 0FFFFFFFEh
0x18002db65  cmp     eax, 1
0x18002db68  ja      short loc_18002DBE5
0x18002db6a  xor     eax, eax
0x18002db6c  mov     [rsp+2F8h+hActCtx], rax
0x18002db71  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x18002db78  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x18002db7d  mov     rcx, rax; hActCtx
0x18002db80  call    cs:__imp_ActivateActCtx
0x18002db86  test    eax, eax
0x18002db88  jz      short loc_18002DBE0
0x18002db8a  mov     ebx, 70h ; 'p'
0x18002db8f  mov     r8d, ebx; Size
0x18002db92  xor     edx, edx; Val
0x18002db94  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x18002db99  call    memset_0
0x18002db9e  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x18002dba2  lea     rax, [rsp+2F8h+pActCtx]
0x18002dba7  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x18002dbac  lea     r9, StringToFind; "Comctl32.dll"
0x18002dbb3  xor     edx, edx; lpExtensionGuid
0x18002dbb5  lea     r8d, [rbx-6Eh]; ulSectionId
0x18002dbb9  xor     ecx, ecx; dwFlags
0x18002dbbb  call    cs:__imp_FindActCtxSectionStringW
0x18002dbc1  test    eax, eax
0x18002dbc3  jz      short loc_18002DBD3
0x18002dbc5  lea     rcx, StringToFind; "Comctl32.dll"
0x18002dbcc  call    cs:__imp_LoadLibraryW
0x18002dbd2  nop
0x18002dbd3  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x18002dbd8  xor     ecx, ecx; dwFlags
0x18002dbda  call    cs:__imp_DeactivateActCtx
0x18002dbe0  mov     ebx, 1
0x18002dbe5  mov     eax, ebx
0x18002dbe7  mov     rcx, [rsp+2F8h+var_18]
0x18002dbef  xor     rcx, rsp; StackCookie
0x18002dbf2  call    __security_check_cookie
0x18002dbf7  add     rsp, 2F0h
0x18002dbfe  pop     rbx
0x18002dbff  retn
0x18005cfd6  push    rbp
0x18005cfd8  sub     rsp, 40h
0x18005cfdc  mov     rbp, rdx
0x18005cfdf  mov     rdx, [rbp+48h]; ulCookie
0x18005cfe3  xor     ecx, ecx; dwFlags
0x18005cfe5  call    cs:__imp_DeactivateActCtx
0x18005cfeb  nop
0x18005cfec  add     rsp, 40h
0x18005cff0  pop     rbp
0x18005cff1  retn
```
